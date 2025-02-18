---
title: GraphQL
description: De  [!DNL Live Search]  werkruimte van GraphQL laat u vragen met uw levende gegevens bouwen.
exl-id: f7b17c5a-a97b-4724-a50e-83e28a4c4c38
source-git-commit: cf94623fd4a87c13d15c81ac62243a508cb1d14d
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 0%

---

# GraphQL

De *werkruimte van GraphQL* staat beheerders toe om de vragen van GraphQL te bouwen en te testen gebruikend hun eigen gegevens.

Deze werkruimte steunt [`productSearch` ](https://developer.adobe.com/commerce/services/graphql/live-search/product-search/) en [`attributeMetadata` ](https://developer.adobe.com/commerce/services/graphql/live-search/attribute-metadata/) vragen.

![ de werkruimte van GraphQL ](assets/graphql.png)

```graphql
query productSearch {
  productSearch(phrase: "a306") {
    total_count
    items {
      product {
        sku
		name
      }
    }
    facets {
      title
    }
  }
}
```

Variabelen:

```json
{
  "Magento-Environment-Id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "Magento-Website-Code": "base",
  "Magento-Store-Code": "base",
  "Magento-Store-View-Code": "default",
  "X-Api-Key": "search_gql"
}
```

