---
title: Overzicht van hulplijnen
description: Leer hoe u Adobe Commerce-gegevens met Adobe Experience Platform kunt integreren via de aansluiting van het Experience Platform.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
source-git-commit: 0d5bbe7d4e2070173930df66c4f159d65c7383ea
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Overzicht van de Experience Platform-aansluiting

Met de uitbreiding van de aansluiting van het Experience Platform kunnen Adobe Commerce-handelaren gegevens verzenden [storefront](events.md#storefront-events) en [achterkantoor](events.md#back-office-events) gegevens aan de Adobe Experience Platform edge zodat andere Adobe Experience Cloud producten, zoals Adobe Analytics en Adobe Target, die gegevens van de Handel kunnen gebruiken. Door uw gegevens van de Handel met andere producten in Adobe Experience Cloud te verbinden, kunt u taken uitvoeren, zoals gebruikersgedrag op uw plaats analyseren, het testen van AB uitvoeren, en gepersonaliseerde campagnes creëren.

[Gebeurtenissen van Storefront](events.md#storefront-events) interacties met opnamesoftware, zoals `View Page`, `View Product`, `Add to Cart`, en [aanvraaglijst](events.md#b2b-events) informatie (voor B2B-handelaren). [Back Office](events.md#back-office-events) gebeurtenissen leggen informatie vast over de status van een bestelling, zoals of een bestelling is geplaatst, geannuleerd, terugbetaald, verzonden of voltooid. Vastgelegde gegevens bevatten geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [Meer informatie](https://www.adobe.com/privacy/experience-cloud.html).

De verbindingslijn van het Experience Platform verschijnt in Commerce Admin onder **Systeem** > Services > **Experience Platform Connector**.

![Admin-weergave Experience Platform-aansluiting](assets/epc-adminui.png)

## Vereisten {#prereqs}

Om de schakelaar van het Experience Platform te gebruiken, moet u het volgende hebben:

- Adobe Commerce 2.4.3 of hoger
- Adobe ID- en organisatie-id
- [Adobe Client Data Layer (ACDL)](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/client-data-layer/overview.html). ACDL is vereist om storefront-gebeurtenisgegevens te verzamelen.
- Rechten op andere Adobe DX-producten

## Stappen aan boord

1. [Installeren](install.md) de verbindingsuitbreiding van het Experience Platform.
1. [Aanmelden](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) naar uw Adobe-account en [bevestiging bekijken](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) uw organisatie-id. De organisatie-id is de id die is gekoppeld aan uw Experience Cloud-bedrijf waarvoor u een provisioning uitvoert. Deze id bestaat uit een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet worden opgenomen) `@AdobeOrg`.
1. [Maken of bijwerken](update-xdm.md) uw schema XDM met handel-specifieke gebiedsgroepen.
1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt of bijgewerkt. Deze dataset zal de gegevens bevatten van de Handel u verzendt.
1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) en selecteer het XDM-schema dat de handel-specifieke gebiedsgroepen bevat.
1. [Verbinden met de Diensten van de Handel](../landing/saas.md).
1. [Verbinding maken met Adobe Experience Platform](connect-data.md).

## Publiek

Deze handleiding is ontworpen voor de Adobe Commerce-handelaar die zijn Adobe Commerce-gegevens wil koppelen aan andere Adobe DX-producten.

### Ondersteuning voor PWA Studio&#39;s

Zie de [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/) documentatie voor informatie over hoe te om de schakelaar van het Experience Platform in een PWA Studio opslagront te gebruiken.

### AEM {#aem-support}

Zie de [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html) documentatie om te leren hoe te om storefront gebeurtenisgegevens van een AEM-teruggegeven productpagina naar het Experience Platform te verzenden gebruikend CIF - de Schakelaar van het Experience Platform.

Gebruik de volgende bronnen als u informatie nodig hebt of vragen hebt die niet in deze handleiding worden behandeld:

- [Help Center](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html){target="_blank"}
- [Ondersteuningstickets](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket){target="_blank"}—Verstuur een ticket voor extra hulp.
