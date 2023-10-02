---
title: Extensie Catalogusadapter
description: Het gebruiken van de Adapter van de Catalogus om prijzen van de Diensten van de Handel terug te geven
seo-title: Catalog Adapter Extension
seo-description: Using Catalog Adapter to render prices from Commerce Services
source-git-commit: 6b578e7113c278a05a64f2db5e032bccc4a9580a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---


# Catalogusadapter

De `Catalog Adapter` De extensie schakelt de standaard Adobe Commerce Product Price-index uit en gebruikt in plaats daarvan de prijzen die worden opgegeven via de [Catalogusservice](../catalog-service/overview.md).
De Adobe Commerce Product Price-index is uitgeschakeld en kan niet worden ingeschakeld als deze uitbreidingsmodules zijn geïnstalleerd. Alleen door deze extensie te verwijderen of uit te schakelen, kan de standaardindexeerfunctie voor de productprijs opnieuw worden ingeschakeld.

## Vereisten

* Adobe Commerce 2.4.4+
* Één van de volgende geïnstalleerde Diensten van de Handel:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/guide-overview.md)

## Installatie

Als u de opdracht `catalog-adapter` module, [!DNL Live Search] en [!DNL Catalog Service] moet eerst worden geïnstalleerd en geconfigureerd. Volg de [Installeren [!DNL Live Search]](../live-search/install.md) en [Installatie van catalogusservice](../catalog-service/installation.md) instructies voordat u verdergaat.

Zodra die diensten worden geïnstalleerd, stel het volgende bevel in werking:

```bash
composer require adobe-commerce/catalog-adapter
```

## De Adobe Commerce-productprijsindex inschakelen

Als u toepassingen van derden hebt die zich op de standaardIndex van de Prijs van het Product van Adobe Commerce baseren, kan het met de volgende bevelen opnieuw worden toegelaten:

```bash
# re-enable Product Price indexer
bin/magento module:disable Magento_PriceIndexerDisabler
# reindex Product Price indexer 
bin/magento index:reindex catalog_product_price
```

## De indexator van de Prijs van het Product voor Hoofdloze scenario onbruikbaar maken

Als je een instantie zonder kop Commerce hebt, moet je mogelijk de Adobe Commerce Product Price-index uitschakelen om de belasting op je Adobe Commerce-exemplaar te verminderen.
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

### Koploze handel-instanties

* Een handelaar met een headless instantie van de Handel met de vereiste geïnstalleerde diensten (Levend Onderzoek, Product Recommendations, de Dienst van de Catalogus)
* Geen vertrouwen op de standaard Adobe Commerce Product Price Index

1. &quot;Prijsdisabler&quot; installeren uit het pakket voor de catalogusadapter
