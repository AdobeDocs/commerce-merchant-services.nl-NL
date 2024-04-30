---
title: Extensie Catalogusadapter
description: Catalogusadapter gebruiken om prijzen te renderen van Commerce Services
seo-title: Catalog Adapter Extension
seo-description: Using Catalog Adapter to render prices from Commerce Services
exl-id: 2c9120eb-aa51-48e9-b6a4-fffe25fc31f2
source-git-commit: 7d62f8d5539cd744e98d8d6c072d77a2a7c5a256
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Catalogusadapter

De `Catalog Adapter` De extensie schakelt de standaard Adobe Commerce Product Price-index uit en gebruikt in plaats daarvan de prijzen die worden opgegeven via de [Catalogusservice](../catalog-service/overview.md).
De Adobe Commerce Product Price-index is uitgeschakeld en kan niet worden ingeschakeld als deze uitbreidingsmodules zijn geïnstalleerd. Alleen door deze extensie te verwijderen of uit te schakelen, kan de standaardindexeerfunctie voor de productprijs opnieuw worden ingeschakeld.

## Vereisten

* Adobe Commerce 2.4.4+
* Beide van de volgende Commerce Services hebben geïnstalleerd:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/overview.md)

## Installatie

Als u de opdracht `catalog-adapter` module, [!DNL Live Search] en [!DNL Catalog Service] moet eerst worden geïnstalleerd en geconfigureerd. Volg de [Installeren [!DNL Live Search]](../live-search/install.md) en [Installatie van catalogusservice](../catalog-service/installation.md) instructies voordat u verdergaat.

Zodra die diensten worden geïnstalleerd, stel het volgende bevel in werking:

```bash
composer require adobe-commerce/catalog-adapter
```

## De Adobe Commerce-productprijsindex opnieuw inschakelen

Als u toepassingen van derden hebt die zich op de standaardIndex van de Prijs van het Product van Adobe Commerce baseren, kan het met de volgende bevelen opnieuw worden toegelaten:

```bash
# re-enable Product Price indexer
bin/magento module:disable Magento_PriceIndexerDisabler
# re-index Product Price indexer 
bin/magento index:reindex catalog_product_price
```

## De indexator van de Prijs van het Product voor Hoofdloze scenario onbruikbaar maken

Als u een Commerce-instantie zonder kop hebt, moet u mogelijk de Adobe Commerce Product Price-index uitschakelen om de belasting van uw Adobe Commerce-exemplaar te verminderen.
Dit wordt gedaan door te installeren `magento/module-price-indexer-disabler` module:

```bash
composer require magento/module-price-indexer-disabler
```

## Gebruiksscenario&#39;s

Hier volgen enkele voorbeelden `Catalog Adapter` scenario&#39;s.

### Geen afhankelijkheid van Adobe Commerce Product Price Index

* U bent een Luma- of Adobe Commerce Core GraphQL-handelaar die een vereiste service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* Geen extensies van derden die afhankelijk zijn van de Adobe Commerce Product Price Index

1. Installeer de catalogusadapter.

### Met afhankelijkheid van Adobe Commerce Product Price Index

* U bent een Luma- of Adobe Commerce Core GraphQL-handelaar die een ondersteunde service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* U gebruikt een extensie van derden die afhankelijk is van de Adobe Commerce Product Price-indexer

1. Installeer de catalogusadapter.
1. Schakel de standaard Adobe Commerce-productprijsindex opnieuw in.

### Headless Commerce-instanties

* Een bedrijf met een Commerce-exemplaar zonder kop waarop de vereiste services zijn geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* Geen vertrouwen op de standaard Adobe Commerce Product Price Index

1. Installeer de `magento/module-price-indexer-disabler` uit het pakket voor de catalogusadapter.
