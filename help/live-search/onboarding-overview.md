---
title: Onboarding-overzicht
description: Live zoeken in instapkaartstromen, systeemvereisten, grenzen en beperkingen
source-git-commit: 6220824c6032a33a760fe5c2bb5d2346e00a074b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Overzicht van onboarding

Als u aan de slag wilt gaan met Live zoeken naar Adobe Commerce, moet u een aantal instapstappen uitvoeren om de extensie te installeren, de API-sleutels te configureren en de catalogus te synchroniseren.

## Stroom aan boord

![Actief zoeken op instapkaartdiagram](assets/onboarding-flow.svg)

## Vereisten {#requirements}

* [Adobe Commerce](https://magento.com/products/magento-commerce) 2,4 x
* PHP 7.3 / 7.4
* [!DNL Composer]

### Ondersteunde platforms

* Adobe Commerce on prem (EE) : 2,4 x
* Adobe Commerce on Cloud (ECE) : 2,4 x

## Grenzen en drempels

Op dit moment heeft de API voor Live zoeken/categorieën de volgende ondersteunde limieten en statische grenzen:

### Indexeren

* Indexen tot 300 productkenmerken per winkelweergave
* Alleen producten indexeren uit de Adobe Commerce-database
* CMS-pagina&#39;s niet indexeren

### Zoeklimieten

* Live zoeken heeft geen toegang tot de volledige taxonomie van de categoriestructuur, waardoor sommige gelaagde navigatiescenario&#39;s buiten zijn bereik vallen.
* Het levende Onderzoek gebruikt een uniek eindpunt GraphQL voor vragen om eigenschappen zoals intelligente facetings en onderzoek-als-u-type te steunen. Hoewel vergelijkbaar met de [Magento GraphQL API](https://devdocs.magento.com/guides/v2.4/graphql)Er zijn echter enkele verschillen en sommige gebieden zijn momenteel wellicht niet volledig compatibel.

### PWA bèta-release

* De bètaversie van PWA for Live Search biedt geen ondersteuning voor [gebeurtenisafhandeling](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).
* De volgende productkenmerken worden niet ondersteund door GraphQL bij gebruik in relatie tot de bètaversie van [PWA](https://developer.adobe.com/commerce/pwa-studio/): `description`, `name`, `short_description`

### Momenteel niet ondersteund

* De [Geavanceerd zoeken](https://docs.magento.com/user-guide/catalog/search-advanced.html) wordt uitgeschakeld wanneer Live zoeken is geïnstalleerd en de koppeling Geavanceerd zoeken in de voettekst van de winkel wordt verwijderd.
* [Klantengroepen](https://docs.magento.com/user-guide/customers/customer-groups.html)
* [Aangepaste prijsgroepen](https://docs.magento.com/user-guide/catalog/product-price-group.html)
* Meerdere voorraadlocaties zoals gebruikt door [MCOM](https://docs.magento.com/user-guide/mcom.html) of andere OMS-extensies
* [Geïntegreerde B2B-mogelijkheden](https://business.adobe.com/products/magento/b2b-ecommerce.html)
