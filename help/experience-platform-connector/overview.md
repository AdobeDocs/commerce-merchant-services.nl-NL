---
title: Overzicht van hulplijnen
description: Adobe Experience Platform-connector voor Adobe Commerce sluit je Commerce-exemplaar aan op andere Adobe Experience Cloud-producten.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
source-git-commit: 2fb44e73a76ad4e1433b2abd88be1304e7e10596
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# Overzicht van de Experience Platform-aansluiting

De de schakelaaruitbreiding van het Experience Platform staat de handelaars van Adobe Commerce toe om gegevens naar de rand van Adobe Experience Platform te verzenden zodat kunnen andere producten van Adobe Experience Cloud, zoals Adobe Analytics en Adobe Target, die gegevens van de Handel gebruiken. Door uw gegevens van de Handel met andere producten in Adobe Experience Cloud te verbinden, kunt u taken uitvoeren, zoals gebruikersgedrag op uw plaats analyseren, het testen van AB uitvoeren, en gepersonaliseerde campagnes creëren.

Met Storefront-gebeurtenissen worden winkelinteracties vastgelegd, zoals `View Page`, `View Product`, `Add to Cart`, enzovoort. Vastgelegde gegevens bevatten geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [Meer informatie](https://www.adobe.com/privacy/experience-cloud.html). Zie de volledige lijst met [storefront, gebeurtenissen](events.md).

De verbindingslijn van het Experience Platform verschijnt in Commerce Admin onder **Systeem** > Services > **Experience Platform Connector**.

![Admin-weergave Experience Platform-aansluiting](assets/epc-adminui.png)

## Vereisten voor het gebruik van de aansluiting van het Experience Platform {#prereqs}

Om de schakelaar van het Experience Platform te gebruiken, moet u eerst:

- Vul het volgende in [formulier](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4VH_dtG9hJVAk_TqGkZC2DxUM1FSWkdJOE41UVpUWUw0M1JWV0RKS1VXQi4u) en Adobe krijgt u toegang tot gegevensstreams en de Adobe Experience Platform (indien nodig).

Wanneer toegang wordt verleend:

1. [Aanmelden](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) naar uw Adobe-account.
1. Kijk naar je [organisatie](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en#concept_EA8AEE5B02CF46ACBDAD6A8508646255). De organisatie-id is de id die is gekoppeld aan uw Experience Cloud-bedrijf waarvoor u een provisioning uitvoert. Deze id bestaat uit een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet worden opgenomen) `@AdobeOrg`.
1. Maak uw [XDM-schema](update-xdm.md) met specifieke handelsgroepen.
1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) en selecteer het XDM-schema dat de handel-specifieke **Veldgroepen**.

>[!NOTE]
>
> De organisatie-id en de gegevensstroom worden gebruikt om uw Adobe Commerce-instantie te verbinden met de Adobe Experience Platform.

## Volgende stappen

- Installeer de [Experience Platform connector-extensie](install.md).

   De verbindingsuitbreiding van het Experience Platform wordt geïnstalleerd vanaf de bevellijn van de server en verbindt met uw installatie van Adobe Commerce als a [service](../landing/saas.md). Wanneer het proces is voltooid, verschijnt de verbindingslijn van het Experience Platform op **Systeem** menu onder **Services** in de handel _Beheer_.
- [Knopprofielen uploaden](profile.md) aan Adobe Experience Platform, zodat gegevens over de winkel kunnen worden toegeschreven aan specifieke kopers om hun winkelervaring te verbeteren.

## Publiek

Deze handleiding is bedoeld voor de Adobe Commerce-handelaar die zijn Adobe Commerce-winkelgegevens moet verbinden met andere Adobe DX-producten.

### Ondersteuning voor PWA Studio&#39;s

Zie de [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/) documentatie voor informatie over hoe te om de schakelaar van het Experience Platform in een PWA Studio opslagront te gebruiken.

## Bekende problemen

Momenteel heeft de aansluiting van het Experience Platform de volgende bekende problemen:

- Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.
- Het duurt ongeveer een uur om gegevens op te slaan van Adobe Commerce naar de verschillende doelen nadat u verbinding hebt gemaakt met de Adobe Experience Platform-rand.

Gebruik de volgende bronnen als u informatie nodig hebt of vragen hebt die niet in deze handleiding worden behandeld:

- [Help Center](https://support.magento.com/hc/en-us){target=&quot;_blank&quot;}
- [Ondersteuningstickets](https://support.magento.com/hc/en-us/articles/360000913794#submit-ticket){target=&quot;_blank&quot;} - Verstuur een ticket voor extra hulp.
