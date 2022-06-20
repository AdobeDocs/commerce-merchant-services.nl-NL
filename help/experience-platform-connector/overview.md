---
title: Overzicht van hulplijnen
description: Adobe Experience Platform-connector voor Adobe Commerce sluit uw [!DNL Commerce] naar andere Adobe Experience Cloud-producten.
source-git-commit: 9b5f2da08167e22bbba504009bccc87d0ab02c48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Overzicht van de Experience Platform-aansluiting

Met de uitbreiding van de aansluiting van het Experience Platform kunnen Adobe Commerce-handelaren gegevens verzenden naar Adobe Experience Platform edge, zodat andere Adobe Experience Cloud-producten, zoals Adobe Analytics en Adobe Target, kunnen gebruiken dat [!DNL Commerce] gegevens. Door uw [!DNL Commerce] gegevens aan andere producten in Adobe Experience Cloud, kunt u taken uitvoeren, zoals het gebruikersgedrag op uw plaats analyseren, het testen van AB uitvoeren, en gepersonaliseerde campagnes creëren.

Met Storefront-gebeurtenissen worden winkelinteracties vastgelegd, zoals `View Page`, `View Product`, `Add to Cart`, enzovoort. Vastgelegde gegevens bevatten geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [Meer informatie](https://www.adobe.com/privacy/experience-cloud.html). Zie de volledige lijst met storefront-gebeurtenissen aan het einde van deze pagina.

## Vereisten voor het gebruik van de aansluiting van het Experience Platform {#prereqs}

Om de schakelaar van het Experience Platform te gebruiken, moet u eerst:

- Vul het volgende in [formulier](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4VH_dtG9hJVAk_TqGkZC2DxUM1FSWkdJOE41UVpUWUw0M1JWV0RKS1VXQi4u) en Adobe krijgt u toegang tot gegevensstreams en de Adobe Experience Platform (indien nodig).

Wanneer toegang wordt verleend:

1. [Aanmelden](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) naar uw Adobe-account.
1. Kijk naar je [organisatie](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en#concept_EA8AEE5B02CF46ACBDAD6A8508646255). De organisatie-id is de id die is gekoppeld aan uw Experience Cloud-bedrijf waarvoor u een provisioning uitvoert. Deze id is een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet bevatten) @AdobeOrg.
1. Toegang tot de werkruimte van de gegevensstroom en [een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en).

De organisatie-id en de gegevensstroom worden gebruikt wanneer u uw Adobe Commerce-instantie verbindt met de Adobe Experience Platform.

## Volgende stappen

- Installeer de [Experience Platform connector-extensie](install.md).

   De verbindingsuitbreiding van het Experience Platform wordt geïnstalleerd vanaf de bevellijn van de server en verbindt met uw installatie van Adobe Commerce als a [service](../landing/saas.md). Wanneer het proces is voltooid, verschijnt de verbindingslijn van het Experience Platform op **Systeem** menu onder **Services** in de [!DNL Commerce] _Beheer_.

## Publiek

Deze handleiding is bedoeld voor de Adobe Commerce-handelaar die zijn Adobe Commerce-winkelgegevens moet verbinden met andere Adobe DX-producten.

## Bekende problemen

Momenteel heeft de aansluiting van het Experience Platform de volgende bekende problemen:

- Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.
- De gegevens van de opslag nemen een paar uren om van Handel aan de diverse bestemmingen na het verbinden met de rand van Adobe Experience Platform te krijgen.

## Ondersteuning

Als u informatie nodig hebt of vragen hebt die niet in deze gids worden behandeld, post aan het volgende kanaal van Slack:

- `#beacon-ama`
