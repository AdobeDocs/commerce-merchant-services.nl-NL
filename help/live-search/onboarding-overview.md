---
title: "Overzicht aan boord"
description: "[!DNL Live Search] instapkaartstroom, systeemvereisten, grenzen en beperkingen"
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: 1a55f2fb3d56183e5e73d172ebdc40f340e4d520
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Onboarding-overzicht

Aan de slag met [!DNL Live Search] voor Adobe Commerce: voltooi het instapproces om de extensie te installeren, configureer uw API-sleutels en synchroniseer uw catalogus.

## Stroom aan boord

![[!DNL Live Search] instapkaartschema](assets/onboarding-flow.svg)

## Vereisten {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2,4 x
* PHP 7.3 / 7.4 / 8.1
* [!DNL Composer]

### Ondersteunde platforms

* Adobe Commerce on prem (EE) : 2,4 x
* Adobe Commerce on Cloud (ECE) : 2,4 x

## Grenzen en drempels

Op dit moment wordt [!DNL Live Search] zoek-/Categorie-API heeft de volgende ondersteunde limieten en statische grenzen:

### Indexeren

* Indexeert maximaal 300 productkenmerken per winkelweergave.
* Hiermee indexeert u alleen producten uit de Adobe Commerce-database.
* CMS-pagina&#39;s worden niet geïndexeerd.

### Query

* [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
* [!DNL Live Search] gebruikt een uniek eindpunt GraphQL voor vragen om eigenschappen zoals intelligente facettering en onderzoek-zoals-u-type te steunen. Hoewel vergelijkbaar met de [Magento GraphQL API](https://developer.adobe.com/commerce/webapi/graphql/)Er zijn echter enkele verschillen en sommige gebieden zijn momenteel wellicht niet volledig compatibel.

### Regels

* Het maximumaantal regels per winkelweergave is 50.
* Het maximum aantal voorwaarden per regel is 10.
* Het maximum aantal gebeurtenissen per regel is 25.

### Synoniemen

* [!DNL Live Search] U kunt maximaal 200 synoniemen per winkelweergave beheren.

### PWA bèta-release

* De huidige bèta-PWA-implementatie van Live Search vereist meer verwerkingstijd om zoekresultaten te retourneren dan Live Search met de native Commerce-winkel.
* De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).
* De volgende productkenmerken worden niet ondersteund door GraphQL bij gebruik in relatie tot de bètaversie van [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://docs.magento.com/user-guide/catalog/search-advanced.html) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
* [Aangepaste prijsgroepen](https://docs.magento.com/user-guide/catalog/product-price-group.html)
* Meerdere voorraadlocaties zoals gebruikt door [MCOM](https://docs.magento.com/user-guide/mcom.html) of andere OMS-extensies
* De productprijzen omvatten niet [btw](https://docs.magento.com/user-guide/tax/vat.html) (BTW).
