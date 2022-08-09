---
title: Gebeurtenissen
description: Leer welke gebeurtenissen gegevens vangen en de volledige schemadefinitie zien.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: 2b735c292920bb0e9052d86bf152748e7ce96079
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Verbindingsgebeurtenissen Experience Platform

De volgende lijst maakt een lijst van de gebeurtenissen van de Handel beschikbaar wanneer u de de schakelaaruitbreiding van het Experience Platform installeert. De gegevens die door deze gebeurtenissen worden verzameld, worden naar de Adobe Experience Platform-rand verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

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
| [Zoekverzoek verzonden](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchRequestSentAEP.ts) | Zoeken |
| [Respons zoeken ontvangen](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchResponseReceivedAEP.ts) | Zoeken |

>[!NOTE]
>
> De `Sign In`, `Sign Out`, `Create Account`, en `Update Account` gebeurtenissen worden geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.
