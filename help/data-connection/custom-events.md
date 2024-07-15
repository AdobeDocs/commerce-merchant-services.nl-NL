---
title: Aangepaste gebeurtenissen maken
description: Leer hoe u aangepaste gebeurtenissen maakt om uw Adobe Commerce-gegevens te koppelen aan andere DX-producten voor Adobe.
exl-id: 5a754106-c66a-4280-9896-6d065df8a841
role: Admin, Developer
feature: Personalization, Integration, Eventing
source-git-commit: 4a5877d6e1a5c7d840e36f4913306b0c440bbac5
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Aangepaste gebeurtenissen maken

U kunt het [ gebeurtenisplatform ](events.md) uitbreiden door uw eigen storefront gebeurtenissen te creëren om gegevens te verzamelen uniek aan uw industrie. Wanneer u creeert en een douanegebeurtenis vormt, wordt het verzonden naar de [ Collector van de Gebeurtenissen van Adobe Commerce ](https://github.com/adobe/commerce-events/tree/main/packages/storefront-events-collector).

## Aangepaste gebeurtenissen afhandelen

Aangepaste gebeurtenissen worden alleen ondersteund voor de Adobe Experience Platform. Aangepaste gegevens worden niet doorgestuurd naar Adobe Commerce-dashboards en metrieke trackers.

Voor elke `custom` -gebeurtenis:

- Voegt `identityMap` met `ECID` toe als primaire identiteit
- Omvat `email` in `identityMap` als secundaire identiteit _als_ `personalEmail.address` in de gebeurtenis wordt geplaatst
- Hiermee wordt de volledige gebeurtenis binnen een `xdm` -object geprononceerd voordat deze naar de Edge wordt doorgestuurd

Voorbeeld:

Aangepaste gebeurtenis gepubliceerd via Adobe Commerce Events SDK:

```javascript
mse.publish.custom({
    commerce: {
        saveForLaters: {
            value: 1,
        },
    },
});
```

In Experience Platform Edge:

```javascript
{
  xdm: {
    identityMap: {
      ECID: [
        {
          id: 'ecid1234',
          primary: true
        }
      ],
      email: [
        {
          id: "runs@safari.ke",
          primary: false
        }
      ]
    },
    commerce: {
        saveForLaters: {
            value: 1
        }
    }
  }
}
```

>[!NOTE]
>
> Het gebruik van aangepaste gebeurtenissen kan invloed hebben op standaard Adobe Analytics-rapporten.

## Overschrijvingen van gebeurtenissen afhandelen (aangepaste kenmerken)

Overschrijvingen van kenmerken voor standaardgebeurtenissen worden alleen ondersteund voor het Experience Platform. Aangepaste gegevens worden niet doorgestuurd naar Commerce-dashboards en metrieke trackers.

Voor elke gebeurtenis met `customContext` overschrijft de verzamelaar de samenvoegingsvelden die in de relevante context zijn ingesteld met velden in `customContext` . Het gebruik van overschrijvingen is mogelijk wanneer een ontwikkelaar contexten die door andere delen van de pagina zijn ingesteld, opnieuw wil gebruiken en uitbreiden in gebeurtenissen die al worden ondersteund.

>[!NOTE]
>
>Wanneer het met voeten treden van douanegebeurtenissen, zou de gebeurtenis die aan Experience Platform door:sturen voor dat gebeurtenistype moeten worden uitgezet om dubbel tellen te vermijden.

Voorbeelden:

De mening van het product met met voeten getreden die door Adobe Commerce Events SDK wordt gepubliceerd:

```javascript
mse.publish.productPageView({
    productListItems: [
        {
            productCategories: [
                {
                    categoryID: "cat_15",
                    categoryName: "summer pants",
                    categoryPath: "pants/mens/summer",
                },
            ],
        },
    ],
});
```

In Experience Platform Edge:

```javascript
{
  xdm: {
    eventType: 'commerce.productViews',
    identityMap: {
      ECID: [
        {
          id: 'ecid1234',
          primary: true,
        }
      ]
    },
    commerce: {
      productViews: {
        value : 1,
      }
    },
    productListItems: [{
        SKU: "1234",
        name: "leora summer pants",
        productCategories: [{
            categoryID: "cat_15",
            categoryName: "summer pants",
            categoryPath: "pants/mens/summer",
        }],
    }],
  }
}
```

>[!NOTE]
>
> Het overschrijven van gebeurtenissen met aangepaste kenmerken kan van invloed zijn op standaard Adobe Analytics-rapporten.
