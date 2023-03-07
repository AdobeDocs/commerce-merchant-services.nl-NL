---
title: "Overzicht aan boord"
description: "[!DNL Live Search] instapkaartstroom, systeemvereisten, grenzen en beperkingen"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 484319fc1df6c29c972b57c13bd0ed711e374e99
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Onboarding-overzicht

Aan de slag met [!DNL Live Search] voor Adobe Commerce: voltooi het instapproces om de extensie te installeren, configureer uw API-sleutels en synchroniseer uw catalogus.

## Stroom aan boord

![[!DNL Live Search] instapkaartschema](assets/onboarding-flow.svg)

## Vereisten {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2.4.4+
* PHP 8.1, 8.2
* [!DNL Composer]

### Ondersteunde platforms

* Adobe Commerce on prem (EE) : 2.4.4+
* Adobe Commerce on Cloud (ECE) : 2.4.4+

## Grenzen en drempels

Op dit moment wordt [!DNL Live Search] zoek-/Categorie-API heeft de volgende ondersteunde limieten en statische grenzen:

### Indexeren

* Indexeert maximaal 300 productkenmerken per winkelweergave.
* Hiermee indexeert u alleen producten uit de Adobe Commerce-database.
* CMS-pagina&#39;s worden niet geïndexeerd.

### Query

* [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
* [!DNL Live Search] gebruikt een uniek GraphQL eindpunt voor vragen om eigenschappen zoals intelligente facettering en onderzoek-zoals-u-type te steunen. Hoewel vergelijkbaar met de [Magento GraphQL API](https://developer.adobe.com/commerce/webapi/graphql/)Er zijn echter enkele verschillen en sommige gebieden zijn momenteel wellicht niet volledig compatibel.

### Regels

* Het maximumaantal regels per winkelweergave is 50.
* Het maximum aantal voorwaarden per regel is 10.
* Het maximum aantal gebeurtenissen per regel is 25.

### Synoniemen

* [!DNL Live Search] U kunt maximaal 200 synoniemen per winkelweergave beheren.

### PWA bèta-release

* De huidige bèta-PWA-implementatie van Live Search vereist meer verwerkingstijd om zoekresultaten te retourneren dan Live Search met de native Commerce-winkel.
* De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).
* De volgende productkenmerken worden niet door GraphQL ondersteund bij gebruik in verband met de bètaversie van [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
* [Aangepaste prijsgroepen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-group.html)
* Meerdere voorraadlocaties zoals gebruikt door [MCOM](https://experienceleague.adobe.com/docs/commerce-admin/systems/integrations/mcom.html) of andere OMS-extensies
* De productprijzen omvatten niet [btw](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/taxes/vat.html) (BTW).
