---
title: Prijsindexeringsinstallatie SaaS
description: SaaS-prijsindexering installeren
seo-title: SaaS Price Indexing installation
seo-description: Installing SaaS Price indexing
exl-id: a607e852-aa04-4be3-9576-a6bf45f8751f
role: Admin, Developer
source-git-commit: 9ae4aff1851e9ce9920c4fbf11d2616d6f0f6307
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Prijsindexeringsinstallatie SaaS

Voor het instellen van de SaaS-prijsindexering moeten nieuwe modules worden geïnstalleerd en moeten CLI-opdrachten worden uitgevoerd. Beheerders hebben opdrachtregeltoegang nodig om deze installatie te voltooien.

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
   "magento/module-saas-price": "102.2.0",
   "magento/module-saas-scopes": "102.2.0",
   "magento/module-product-override-price-remover": "102.2.0",
   "magento/module-bundle-product-override-data-exporter": "102.2.0",
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

Gebruikers van Luma en Adobe Commerce Core GraphQL kunnen de `catalog-adapter` die Luminantiemodule en Core GraphQl-compatibiliteit biedt en de PHP core price indexer uitschakelt.
Als u de opdracht `catalog-adapter` module, [!DNL Live Search] en [!DNL Catalog Service] moet eerst worden geïnstalleerd en geconfigureerd. Volg de [Installeren [!DNL Live Search]](../live-search/install.md) en [Installatie van catalogusservice](../catalog-service/installation.md) instructies voordat u verdergaat.

Om Live zoeken en de Adapter van de Catalogus te vormen, volg [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html?lang=en) instructies.

```bash
composer require adobe-commerce/catalog-adapter
```

Indien nodig kan de PHP index van de kernprijs opnieuw worden ingeschakeld met de volgende opdracht:

```bash
bin/magento module:disable Magento_PriceIndexerDisabler
```
