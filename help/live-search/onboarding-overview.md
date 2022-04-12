---
title: Onboarding-overzicht
description: Live zoeken in instapkaartstromen, systeemvereisten, grenzen en beperkingen
exl-id: 45f6c1ae-544b-47ef-9feb-c1a05f93108a
source-git-commit: f33f02fa15b6250970bda3302d3403b6fcec5786
workflow-type: tm+mt
source-wordcount: '282'
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

* Indexen tot 300 productkenmerken per winkelweergave
* Alleen producten indexeren uit de Adobe Commerce-database
* CMS-pagina&#39;s niet indexeren

### Zoeklimieten

* [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
* [!DNL Live Search] gebruikt een uniek eindpunt GraphQL voor vragen om eigenschappen zoals intelligente facettering en onderzoek-zoals-u-type te steunen. Hoewel vergelijkbaar met de [Magento GraphQL API](https://devdocs.magento.com/guides/v2.4/graphql)Er zijn echter enkele verschillen en sommige gebieden zijn momenteel wellicht niet volledig compatibel.

### PWA bèta-release

* De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).
* De volgende productkenmerken worden niet ondersteund door GraphQL bij gebruik in relatie tot de bètaversie van [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://docs.magento.com/user-guide/catalog/search-advanced.html) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
* [Klantengroepen](https://docs.magento.com/user-guide/customers/customer-groups.html)
* [Aangepaste prijsgroepen](https://docs.magento.com/user-guide/catalog/product-price-group.html)
* Meerdere voorraadlocaties zoals gebruikt door [MCOM](https://docs.magento.com/user-guide/mcom.html) of andere OMS-extensies
* [Geïntegreerde B2B-mogelijkheden](https://business.adobe.com/products/magento/b2b-ecommerce.html)
