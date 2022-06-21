---
title: Gebeurtenissen
description: Leer welke gebeurtenissen gegevens vangen en de volledige schemadefinitie zien.
source-git-commit: 566abe09b8c1b0837a833b2f8fcfe1e81bb6963d
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Gebeurtenissen projectbaken

De volgende lijst bevat de [!DNL Commerce] -gebeurtenissen beschikbaar wanneer u de verbindingsextensie van het Experience Platform installeert. De gegevens die door deze gebeurtenissen worden verzameld, worden naar de Adobe Experience Platform-rand verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

Klik op de naam van de gebeurtenis om de volledige schemadefinitie weer te geven.

| Gebeurtenis | Type |
|---|---|
| [Toevoegen aan winkelwagentje](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/addToCartAEP.ts) | Storefront |
| [Winkelwagentje weergeven](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/viewAEP.ts) | Storefront |
| [Pagina weergeven](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/page/viewAEP.ts) | Storefront |
| [Product weergeven](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/viewAEP.ts) | Storefront |
| [Afhandeling starten](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/initiateCheckoutAEP.ts) | Storefront |
| [Afhandeling voltooien](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/checkout/placeOrderAEP.ts) | Storefront |
| [Aanmelden](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signInAEP.ts) | Profiel |
| [Afmelden](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signOutAEP.ts) | Profiel |
| [Account maken](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/createAccountAEP.ts) | Profiel |
| [Account bewerken](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/editAccountAEP.ts) | Profiel |

>[!NOTE]
>
> De `Sign In`, `Sign Out`, `Create Account`, en `Update Account` gebeurtenissen worden geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.
