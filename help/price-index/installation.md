---
title: Handmatige installatie van SaaS-prijsindexering
description: Prijsindexering SaaS voor oudere versie installeren
seo-title: SaaS Price Indexing installation
seo-description: Installing SaaS Price indexing
exl-id: a607e852-aa04-4be3-9576-a6bf45f8751f
role: Admin, Developer
source-git-commit: be0b8f4c26f11c31da3e5422bb4f4c4af10f2a00
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Handmatige installatie van SaaS-prijsindexering

Prijsindexering SaaS is beschikbaar in het vak voor ondersteuning [nieuwste versie](index.md#Requirements) van Commerce Services.
Gebruik deze minigids als je niet over de nieuwste versie beschikt en de prijsindexering voor SaaS voor je Adobe Commerce-exemplaar wilt inschakelen.

## Vereisten

* Adobe Commerce 2.4.4+
* Ten minste een van de volgende geïnstalleerde SaaS-services:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/guide-overview.md)
   * [Product Recommendations](../product-recommendations/guide-overview.md)

## Vereiste modules installeren

Afhankelijk van uw installatie kan het installatieproces iets anders zijn.
Er zijn extensies die de nieuwe feeds en ondersteunende code toevoegen en er is een extensie die de standaardprijsfeed verwijdert.

1. Voeg de volgende modules aan uw toe `composer.json` bestand:

   ```json
   "magento/module-saas-price": "^102.2.0",
   "magento/module-saas-scopes": ^"102.2.0",
   "magento/module-product-override-price-remover": "^102.2.0",
   "magento/module-bundle-product-override-data-exporter": "^102.2.0",
   ```

1. Voer de upgrade-opdracht uit:

   ```bash
   bin/magento setup:upgrade
   ```

Na de upgrade zijn drie nieuwe feeds beschikbaar:

* `prices` - verantwoordelijk voor het verstrekken van prijsgegevens aan de dienst
* `scopesCustomerGroup` - is verantwoordelijk voor het leveren van Klantengroepen aan de service
* `scopesWebsite` - verantwoordelijk voor het leveren van websites, winkelgroepen en winkelweergaven aan de service


1. Vorm de nieuwe te plaatsen voer aan &quot;Update op de wijze van het Programma&quot;:

   ```bash
   bin/magento indexer:set-mode schedule catalog_data_exporter_product_prices scopes_customergroup_data_exporter scopes_website_data_exporter
   ```

1. De nieuwe feeds opnieuw indexeren:

   ```bash
   bin/magento saas:resync --feed=scopesCustomerGroup
   bin/magento saas:resync --feed=scopesWebsite
   bin/magento saas:resync --feed=prices
   ```

Voer de bovenstaande indexen indien nodig handmatig uit. Anders worden de gegevens in het standaardsynchronisatieproces vernieuwd. Meer informatie over de [Catalogus synchroniseren](../landing/catalog-sync.md) service.


Gebruikers van Luma en Adobe Commerce Core GraphQL kunnen de [`Catalog Adapter`](catalog-adapter.md) extensie die Luma en Core GraphQl-compatibiliteit biedt en de Adobe Commerce Product Price-index uitschakelt.

## Caveats

Voor `103.0.0` versie, SaaS-prijsindexering ondersteund Eenvoudig, Gegroepeerd, Virtueel, Configurable en Bundle Dynamic-producttypen.
Ondersteuning voor Downloadbare, Cadeautjes en Vaste bundel is beschikbaar vanaf `magento/module-saas-price:103.0.0` versie en beschikbaar uit de doos voor de gesteunde Diensten van de Handel.

Nieuwe feeds moeten handmatig worden gesynchroniseerd met de `resync` [CLI, opdracht](../landing/catalog-sync.md#resynccmdline). Anders worden de gegevens in het standaardsynchronisatieproces vernieuwd. Meer informatie over de [Catalogus synchroniseren](../landing/catalog-sync.md) proces.