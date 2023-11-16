---
title: Aangepaste gebeurtenissen maken
description: Leer hoe u aangepaste gebeurtenissen maakt om uw Adobe Commerce-gegevens te koppelen aan andere DX-producten voor Adobe.
exl-id: 5a754106-c66a-4280-9896-6d065df8a841
role: Admin, Developer
feature: Personalization, Integration, Eventing
source-git-commit: 4a5877d6e1a5c7d840e36f4913306b0c440bbac5
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Aangepaste gebeurtenissen maken

U kunt de [uitvalplatform](events.md) door uw eigen winkelgebeurtenissen te maken om gegevens te verzamelen die uniek zijn voor uw branche. Wanneer u een douanegebeurtenis creeert en vormt, wordt het verzonden naar [Adobe Commerce Events Collector](https://github.com/adobe/commerce-events/tree/main/packages/storefront-events-collector).

## Aangepaste gebeurtenissen afhandelen

Aangepaste gebeurtenissen worden alleen ondersteund voor de Adobe Experience Platform. Aangepaste gegevens worden niet doorgestuurd naar Adobe Commerce-dashboards en metrieke trackers.

Voor alle `custom` gebeurtenis, de verzamelaar:

- Toevoegingen `identityMap` with `ECID` als primaire identiteit
- Inclusief `email` in `identityMap` als secundaire identiteit _indien_ `personalEmail.address` is ingesteld in de gebeurtenis
- Hiermee plaatst u de volledige gebeurtenis in een `xdm` object voordat het naar Edge wordt doorgestuurd

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

In Experience Platform rand:

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

Overschrijvingen van kenmerken voor standaardgebeurtenissen worden alleen ondersteund voor het Experience Platform. De gegevens van de douane worden niet doorgestuurd aan de dashboards van de Handel en metrieke Trackers.

Voor elke gebeurtenis met `customContext`, treedt de inzamelaar met voeten treedt treedt verbindingen in de relevante contexten met gebieden in `customContext`. Het gebruik van overschrijvingen is mogelijk wanneer een ontwikkelaar contexten die door andere delen van de pagina zijn ingesteld, opnieuw wil gebruiken en uitbreiden in gebeurtenissen die al worden ondersteund.

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

In Experience Platform rand:

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
