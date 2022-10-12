---
title: Overzicht van hulplijnen
description: Leer hoe u Adobe Commerce-gegevens met Adobe Experience Platform kunt integreren via de aansluiting van het Experience Platform.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
source-git-commit: f5d1c39fe1b02d2a661b92f971fba5b3e836dd6a
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# Overzicht van de Experience Platform-aansluiting

De de schakelaaruitbreiding van het Experience Platform staat de handelaars van Adobe Commerce toe om gegevens naar de rand van Adobe Experience Platform te verzenden zodat kunnen andere producten van Adobe Experience Cloud, zoals Adobe Analytics en Adobe Target, die gegevens van de Handel gebruiken. Door uw gegevens van de Handel met andere producten in Adobe Experience Cloud te verbinden, kunt u taken uitvoeren, zoals gebruikersgedrag op uw plaats analyseren, het testen van AB uitvoeren, en gepersonaliseerde campagnes creëren.

[Gebeurtenissen van Storefront](events.md) interacties met opnamesoftware, zoals `View Page`, `View Product`, `Add to Cart`, enzovoort. Vastgelegde gegevens bevatten geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [Meer informatie](https://www.adobe.com/privacy/experience-cloud.html).

De verbindingslijn van het Experience Platform verschijnt in Commerce Admin onder **Systeem** > Services > **Experience Platform Connector**.

![Admin-weergave Experience Platform-aansluiting](assets/epc-adminui.png)

## Vereisten {#prereqs}

Als u de aansluiting van het Experience Platform wilt gebruiken, moet u over het volgende beschikken:

- Adobe Commerce 2.4.3 of hoger
- Adobe ID- en organisatie-id
- Rechten op andere Adobe DX-producten

## Stappen aan boord

1. [Installeren](install.md) de verbindingsuitbreiding van het Experience Platform.
1. [Aanmelden](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) naar uw Adobe-account en [weergave](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en#concept_EA8AEE5B02CF46ACBDAD6A8508646255) uw organisatie-id. De organisatie-id is de id die is gekoppeld aan uw Experience Cloud-bedrijf waarvoor u een provisioning uitvoert. Deze id bestaat uit een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet worden opgenomen) `@AdobeOrg`.
1. [Verbinden](connect-data.md) uw Adobe Commerce-exemplaar naar de Adobe Experience Platform.
1. [Maken of bijwerken](update-xdm.md) uw schema XDM met handel-specifieke gebiedsgroepen.
1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) en selecteer het XDM-schema dat de handel-specifieke gebiedsgroepen bevat.
1. (Optioneel) [Knopprofielen uploaden](profile.md) aan Adobe Experience Platform, zodat gegevens over de winkel kunnen worden toegeschreven aan specifieke kopers om hun winkelervaring te verbeteren.

## Publiek

Deze handleiding is ontworpen voor de Adobe Commerce-handelaar die zijn Adobe Commerce-winkelgegevens wil koppelen aan andere Adobe DX-producten.

### Ondersteuning voor PWA Studio&#39;s

Zie de [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/) documentatie voor informatie over hoe te om de schakelaar van het Experience Platform in een PWA Studio opslagront te gebruiken.

### AEM {#aem-support}

Zie de [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html) documentatie om te leren hoe te om storefront gebeurtenisgegevens van een AEM-teruggegeven productpagina naar het Experience Platform te verzenden gebruikend CIF - de Schakelaar van het Experience Platform.

Gebruik de volgende bronnen als u informatie nodig hebt of vragen hebt die niet in deze handleiding worden behandeld:

- [Help Center](https://support.magento.com/hc/en-us){target=&quot;_blank&quot;}
- [Ondersteuningstickets](https://support.magento.com/hc/en-us/articles/360000913794#submit-ticket){target=&quot;_blank&quot;} - Verstuur een ticket voor extra hulp.
