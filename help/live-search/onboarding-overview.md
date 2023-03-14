---
title: "Overzicht aan boord"
description: "[!DNL Live Search] instapkaartstroom, systeemvereisten, grenzen en beperkingen"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 41d6bed30769d3864d93d6b3d077987a810890cc
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 0%

---

# Onboarding-overzicht

Aan de slag met [!DNL Live Search] voor Adobe Commerce: voltooi het instapproces om de extensie te installeren, configureer uw API-sleutels en synchroniseer uw catalogus.

## Stroom aan boord

![[!DNL Live Search] instapkaartschema](assets/onboarding-flow.svg)

## Vereisten {#requirements}

* [Adobe Commerce](https://business.adobe.com/products/magento/magento-commerce.html) 2.4.4+
* PHP 8.1 / 8.2
* [!DNL Composer]

### Ondersteunde platforms

* Adobe Commerce on-prem (EE) : 2.4.4+
* Adobe Commerce on Cloud (ECE) : 2.4.4+

## Grenzen en drempels

Op dit moment worden de [!DNL Live Search] zoek-/Categorie-API heeft de volgende ondersteunde limieten en statische grenzen:

### Indexeren

* Indexeert maximaal 300 productkenmerken per winkelweergave.
* Hiermee indexeert u alleen producten uit de Adobe Commerce-database.
* De producten moeten in de Standaard Gedeelde Catalogus zijn.
* CMS-pagina&#39;s worden niet geïndexeerd.

### Query

* [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
* [!DNL Live Search] gebruikt een uniek GraphQL eindpunt voor vragen om eigenschappen zoals dynamisch facetten en onderzoek-als-u-type te steunen. Hoewel vergelijkbaar met de [GraphQL API](https://developer.adobe.com/commerce/webapi/graphql/)Er zijn echter enkele verschillen en sommige gebieden zijn mogelijk niet volledig compatibel.

Om klantengroepen te beperken die de toestemmingen van de Catalogus gebruiken:

* De producten moeten aan de categorie van de Wortel worden toegewezen.
* Aan de klantengroep &quot;Niet aangemeld&quot; moeten de machtigingen &quot;Toestaan&quot; worden toegekend.
* Om producten tot niet Gelogd in klantengroep te beperken, ga naar elke categorie en plaats toestemming voor elke klantengroep.

### Regels

* Het maximumaantal regels per winkelweergave is 50.
* Het maximum aantal voorwaarden per regel is 10.
* Het maximum aantal gebeurtenissen per regel is 25.

### Synoniemen

* [!DNL Live Search] U kunt maximaal 200 synoniemen per winkelweergave beheren.

### PWA-ondersteuning

Ondersteuning voor Live zoeken wordt beschouwd als een bètaversie omdat niet alle PWA is getest met [!DNL Live Search]. De basisfunctionaliteit zoals zoeken en pagina met productlijsten werkt in Venia, maar sommige permutaties van Graphql werken mogelijk niet correct.

* De huidige bèta-PWA-implementatie van [!DNL Live Search] vereist meer verwerkingstijd om zoekresultaten te retourneren dan [!DNL Live Search] met de native Commerce-winkel.
* [!DNL Live Search] in PWA ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* Rechtstreeks filteren op `description`, `name`, `short_description` wordt niet ondersteund door GraphQL wanneer het wordt gebruikt met [PWA](https://developer.adobe.com/commerce/pwa-studio/), maar ze krijgen een meer algemeen filter.

### Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
* Meerdere voorraadlocaties zoals gebruikt door [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) of andere OMS-extensies
* De productprijzen omvatten niet [btw](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (BTW).
* [Tier-prijs](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-tier.html) wordt niet ondersteund in de pop-up Live zoeken en de widget pagina met productaanbiedingen.

## Cookies

[!DNL Live Search] verzamelt gegevens over gebruikersinteractie als onderdeel van de basisfunctionaliteit en cookies worden gebruikt om deze gegevens op te slaan. Wanneer de gebruiker om het even welke gebruikersinformatie verzamelt, moet de gebruiker ermee instemmen om koekjes op te slaan. [!DNL Live Search] en [!DNL Product Recommendations] delen de gegevensstroom en daarom het zelfde koekjesmechanisme. Meer informatie hierover vindt u in [Cookie-beperkingen verwerken](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/setting-cookie.html).
