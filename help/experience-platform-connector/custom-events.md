---
title: Aangepaste gebeurtenissen maken
description: Leer hoe u aangepaste gebeurtenissen maakt, uw Adobe Commerce-gegevens aansluiten op andere Adobe DX-producten.
exl-id: 5a754106-c66a-4280-9896-6d065df8a841
source-git-commit: ce437d7a991affd2665c86c9e91bb7f39ec626c0
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# Aangepaste gebeurtenissen maken

U kunt de [uitvalplatform](events.md) door uw eigen winkelgebeurtenissen te maken om gegevens te verzamelen die uniek zijn voor uw branche. Wanneer u een douanegebeurtenis creeert en vormt, wordt het verzonden naar [Adobe Commerce Event Collector](https://www.npmjs.com/package/@adobe/magento-storefront-event-collector).

## Aangepaste gebeurtenissen verwerken

Aangepaste gebeurtenissen worden alleen ondersteund voor de Adobe Experience Platform. Aangepaste gegevens worden niet doorgestuurd naar Adobe Commerce-dashboards en metrieke trackers.

Voor alle `custom` gebeurtenis, voegt de verzamelaar een `personId` (`ecid`) naar `customContext` en omhult een `xdm` het voorwerp rond het alvorens aan de Rand door:sturen.

Voorbeeld:

Aangepaste gebeurtenis gepubliceerd via MSE SDK:

```javascript
mse.publish.custom({
    customContext: { customStrAttr: "cheetah", customNumAttr: 128 },
});
```

In Experience Platform rand:

```javascript
{
    xdm: {
        personId: 'ecid1234',
        customStrAttr: 'cheetah',
        customNumAttr: 128
    }
}
```

>[!NOTE]
>
> Het gebruik van aangepaste gebeurtenissen kan invloed hebben op standaard Adobe Analytics-rapporten.

## Overschrijvingen van gebeurtenissen afhandelen (aangepaste kenmerken)

Overschrijvingen van kenmerken voor standaardgebeurtenissen worden alleen ondersteund voor het Experience Platform. De gegevens van de douane worden niet doorgestuurd aan de dashboards van de Handel en metrieke Trackers.

Voor elke gebeurtenis met een set `customContext`, overschrijft de verzamelaar `personId` en Adobe Analytics tellers, en door:sturen alle andere eigenschappen die in `customContext`.

Voorbeelden:

De mening van het product met met voeten getreden die door MSE SDK wordt gepubliceerd:

```javascript
mse.publish.productPageView({
    customContext: { customCode: "okapi" },
});
```

In Experience Platform rand:

```javascript
{
    xdm: {
        eventType: 'commerce.productViews',
        personId: 'ecid1234',
        customCode: 'okapi',
        commerce: {
            productViews: {
                value : 1
            }
        }
    }
}
```

De mening van het product met de met Adobe Commerce met voeten getreden die door MSE SDK wordt gepubliceerd:

```javascript
mse.publish.productPageView({
    customContext: { commerce: { customCode: "mongoose" } },
});
```

In Experience Platform rand:

```javascript
{
    xdm: {
        eventType: 'commerce.productViews',
        personId: 'ecid1234',
        commerce: {
            customCode: 'mongoose',
            productViews: {
                value : 1
            }
        }
    }
}
```

>[!NOTE]
>
> Het overschrijven van gebeurtenissen met aangepaste kenmerken kan van invloed zijn op standaard Adobe Analytics-rapporten.
