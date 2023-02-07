---
title: '[!DNL Catalog Service and API Mesh]'
description: '''[!DNL API Mesh] voor Adobe Commerce biedt een manier om meerdere gegevensbronnen te integreren via een gemeenschappelijk GraphQL-eindpunt. "'
source-git-commit: dd9ba7171cf6a199701b1abb8083a65326e89f5d
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---

# [!DNL Catalog Service and API Mesh]

De [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) laat ontwikkelaars toe om privé of derde APIs en andere interfaces met de producten van Adobe te integreren gebruikend Adobe IO.

![Catalogusarchitectuurdiagram](assets/catalog-service-architecture-mesh.png)

De eerste stap voor het gebruik van het API-net met de Catalogusservice is het verbinden van API-net met uw instantie. Zie gedetailleerde instructies in [Een net maken](https://developer.adobe.com/graphql-mesh-gateway/gateway/create-mesh/).

Als u de installatie wilt voltooien, hebt u de [Adobe IO CLI-pakket](https://developer.adobe.com/runtime/docs/guides/tools/cli_install/) geïnstalleerd.

Zodra het Net op Adobe IO wordt gevormd, stel het volgende bevel in werking dat a toevoegt `CommerceCatalogServiceGraph` bron van het net.

```bash
aio api-mesh:source:install "CommerceCatalogServiceGraph" -f variables.json
```

waar `variables.json` is een afzonderlijk bestand waarin veelgebruikte waarden voor Adobe IO worden opgeslagen.
De API-sleutel kan bijvoorbeeld in het bestand worden opgeslagen:

```json
{
    "CATALOG_SERVICE_API_KEY":"your_api_key"
}
```

Nadat u deze opdracht hebt uitgevoerd, moet de Catalogusservice via het API-net worden uitgevoerd. U kunt de `aio api-mesh:get` bevel om de configuratie van uw bijgewerkt netwerk te bekijken.

## Het API-net gebruiken

Met het API-net kunnen gebruikers externe gegevensbronnen gebruiken om uw Adobe Commerce-instantie te verbeteren. Het kan ook worden gebruikt om bestaande gegevens van de Handel te vormen om nieuwe functionaliteit toe te laten.

In dit voorbeeld wordt het API-net gebruikt om laagprijzen in Adobe Commerce in te schakelen.
Vervang de `name `, `endpoint` en `x-api-key` waarden.

```json
{
  "meshConfig": {
    "sources": [
      {
        "name": "<Commerce Instance Name>",
        "handler": {
          "graphql": {
            "endpoint": "<Adobe Commerce GraphQL endpoint>"
          }
        },
        "transforms": [
            {
                "prefix": {
                    "includeRootOperations": true,
                    "value": "Core_"
                }
            }
        ]
      },
      {
        "name": "CommerceCatalogServiceGraph",
        "handler": {
          "graphql": {
            "endpoint": "https://commerce.adobe.io/catalog-service/graphql/",
            "operationHeaders": {
              "Magento-Store-View-Code": "{context.headers['magento-store-view-code']}",
              "Magento-Website-Code": "{context.headers['magento-website-code']}",
              "Magento-Store-Code": "{context.headers['magento-store-code']}",
              "Magento-Environment-Id": "{context.headers['magento-environment-id']}",
              "x-api-key": "storefront-catalog-apollo",
              "Magento-Customer-Group": "{context.headers['magento-customer-group']}"
            },
            "schemaHeaders": {
              "x-api-key": "<YOUR API-KEY>"
            }
          }
        }
      }
    ],
    "additionalTypeDefs": "extend interface ProductView {\n  price_tiers: [Core_TierPrice]\n}\n extend type SimpleProductView {\n  price_tiers: [Core_TierPrice]\n}\n extend type ComplexProductView {\n  price_tiers: [Core_TierPrice]\n}\n",
    "additionalResolvers": [
        {  
            "targetTypeName": "ProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        },
        {  
            "targetTypeName": "SimpleProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        },
        {  
            "targetTypeName": "ComplexProductView",
            "targetFieldName": "price_tiers",
            "sourceName": "MagentoStageCore",
            "sourceTypeName": "Query",
            "sourceFieldName": "Core_products",
            "requiredSelectionSet": "{\n    items {\n  sku\n    price_tiers {\n        quantity,\n        final_price {\n          value\n          currency\n        }\n      }\n    }\n  }",
            "sourceArgs": {
                "filter.sku.eq": "{root.sku}"
            },
            "result": "items[0].price_tiers"
        }
    ]
   }
}
```

Zodra gevormd, vraag het Net voor gelaagde tarifering:

```json
query {
  products(skus: ["24-MB04"]) {
    sku
    description
    price_tiers {
        quantity
        final_price {
          value
          currency
        }
      }
    ... on SimpleProductView {
      id
       
      price {
        final {
          amount {
            value
          }
        }
      }
    }
  }
}
```
