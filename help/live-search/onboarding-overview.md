---
title: "Overzicht aan boord"
description: "[!DNL Live Search] instapkaartstroom, systeemvereisten, grenzen en beperkingen"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
recommendations: noCatalog
source-git-commit: a6d8c259f232ab27d7ed64558d5d193d59d23cad
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# Onboarding-overzicht

Aan de slag met [!DNL Live Search] voor Adobe Commerce: voltooi het instapproces om de extensie te installeren, configureer uw API-sleutels en synchroniseer uw catalogus.

## Vereisten {#requirements}

* [Adobe Commerce](https://business.adobe.com/products/magento/magento-commerce.html) 2.4.4+
* PHP 8.1 / 8.2
* [!DNL Composer]

### Ondersteunde platforms

* Adobe Commerce on-prem (EE) : 2.4.4+
* Adobe Commerce on Cloud (ECE) : 2.4.4+

## Endpoint

[!DNL Live Search] communiceert door het eindpunt bij `https://catalog-service.adobe.io/graphql`.

## Grenzen en drempels

Op dit moment wordt [!DNL Live Search] zoek-/Categorie-API heeft de volgende ondersteunde limieten en statische grenzen:

### Indexeren

* Indexeert maximaal 300 productkenmerken per winkelweergave.
* Hiermee indexeert u alleen producten uit de Adobe Commerce-database.
* CMS-pagina&#39;s worden niet geïndexeerd.

### Query

* [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
* [!DNL Live Search] gebruikt een uniek GraphQL eindpunt voor vragen om eigenschappen zoals dynamisch facetten en onderzoek-als-u-type te steunen. Hoewel vergelijkbaar met de [GRAPHQL API](https://developer.adobe.com/commerce/webapi/graphql/)Er zijn echter enkele verschillen en sommige gebieden zijn mogelijk niet volledig compatibel.

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

## Categorieverhandeling

Met Categorie Merchandising kunt u configureren [!DNL Live Search] werken aan het niveau van de productcategorieën.

Deze video is een inleiding op Categorie Merchandising.

>[!VIDEO](https://video.tv.adobe.com/v/3424617)

## Inventory management

[!DNL Live Search] supports [Inventory management](https://experienceleague.adobe.com/docs/commerce-admin/inventory/introduction.html) De mogelijkheden in Handel (vroeger kent als Multisource Inventory, of MSI). Om volledige steun toe te laten, moet u [update](install.md#update) de afhankelijkheidsmodule `commerce-data-export` naar versie 102.2.0+.

[!DNL Live Search] Geeft een Booleaanse waarde die aangeeft of een product beschikbaar is in Inventory management, maar geen informatie bevat over de bron van de voorraad.

## Prijsindexering

Klanten met Live zoeken kunnen de nieuwe [SaaS-prijsindexer](../price-index/index.md), die snellere updates van prijswijzigingen en synchronisatietijd biedt.

## PWA-ondersteuning

[!DNL Live Search] werkt met PWA Studio, maar de gebruikers kunnen kleine verschillen zien ten opzichte van andere uitvoeringen van de Handel. De basisfunctionaliteit zoals zoeken en pagina met productlijsten werkt in Venia, maar sommige permutaties van Graphql werken mogelijk niet correct. Er kunnen ook prestatieverschillen zijn.

* De huidige PWA-uitvoering van [!DNL Live Search] vereist meer verwerkingstijd om zoekresultaten te retourneren dan [!DNL Live Search] met de native Commerce-winkel.
* [!DNL Live Search] in PWA ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/). Intelligente handel werkt dus niet.
* Rechtstreeks filteren op `description`, `name`, `short_description` wordt niet ondersteund door GraphQL bij gebruik met [PWA](https://developer.adobe.com/commerce/pwa-studio/), maar ze krijgen een meer algemeen filter.

Te gebruiken [!DNL Live Search] met PWA Studio moeten de integrators ook :

1. Installeren [livessearch-storefront-utils](https://www.npmjs.com/package/@magento/ds-livesearch-storefront-utils).
1. Stel de `environmentId` in de `storeDetails` object.

   ```javascript
   const storeDetails: StoreDetailsProps = {
       environmentId: <Storefront_ID>,
       websiteCode: "base",
       storeCode: "main_website_store",
       storeViewCode: "default",
       searchUnitId: searchUnitId,
       config: {
           minQueryLength: 5,
           pageSize: 8,
           currencySymbol: "$",
           },
       };
   ```

## Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
* [Tier-prijs](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-tier.html) wordt niet ondersteund in de pop-up Live zoeken en de widget pagina met productaanbiedingen.

## Cookies

[!DNL Live Search] verzamelt gegevens over gebruikersinteractie als onderdeel van de basisfunctionaliteit en cookies worden gebruikt om deze gegevens op te slaan. Wanneer de gebruiker om het even welke gebruikersinformatie verzamelt, moet de gebruiker ermee instemmen om koekjes op te slaan. [!DNL Live Search] en [!DNL Product Recommendations] delen de gegevensstroom en daarom het zelfde koekjesmechanisme. Meer informatie hierover vindt u in [Cookie-beperkingen verwerken](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/setting-cookie.html).
