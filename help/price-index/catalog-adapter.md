---
title: Extensie Catalogusadapter
description: Catalogusadapter gebruiken om prijzen te renderen van Commerce Services
seo-title: Catalog Adapter Extension
seo-description: Using Catalog Adapter to render prices from Commerce Services
exl-id: 2c9120eb-aa51-48e9-b6a4-fffe25fc31f2
source-git-commit: 8230756c203cb2b4bdb4949f116c398fcaab84ff
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Catalogusadapter

De `[!DNL Catalog Adapter]` met de extensie wordt de standaardproductprijsindexer in de Commerce-toepassing uitgeschakeld en worden de prijzen gebruikt die door de [Catalogusservice](../catalog-service/overview.md) in plaats daarvan.

De adapter is ontworpen voor gebruik met de [SaaS-gegevens exporteren](../data-export/overview.md) en de Adobe Commerce Service. De SaaS-gegevensexport is verantwoordelijk voor het indienen van de prijzen en de [!DNL Catalog Adapter] wint alle prijzen van de Dienst van Adobe Commerce terug.

Wanneer u de optie [!DNL Catalog Adapter]De indexering van de prijzen en de transacties worden op de volgende manieren beïnvloed:

- De prijsindex die in de Adobe Commerce-toepassing is opgenomen, is uitgeschakeld.
- Prijzen worden beheerd met behulp van de SaaS-gegevensexport en de [SaaS-prijsindexer](price-indexing.md).
- Wanneer een klant een product, categorie of andere pagina opent waarop de productprijzen worden weergegeven, worden de prijzen opgehaald van de Adobe Commerce Service.
- Prijzen worden naar de Adobe Commerce Service verzonden door gegevens van de [SaaS-gegevens exporteren](../data-export/overview.md).
- Met Afhandeling worden de prijzen dynamisch opnieuw berekend.

U kunt prijsindexering in de toepassing van Commerce opnieuw toelaten door de uitbreiding van de Adapter van de Catalogus te verwijderen of onbruikbaar te maken.

## Vereisten

- Adobe Commerce 2.4.4+
- Een van de volgende Commerce Services hebben geïnstalleerd:

   - [Live zoeken](../live-search/install.md)
   - [Product Recommendations](../product-recommendations/install-configure.md)
   - [Catalogusservice](../catalog-service/installation.md)

## Installatie

De uitbreiding van de Adapter van de Catalogus is een metapakket Composer dat de volgende modules installeert:

- **Prijsindexering uitgeschakeld**- Deze module schakelt de prijsindex in de Commerce-toepassing uit, zodat prijzen worden geleverd via prijsindexering in SaaS. De indexeerfunctie van de productprijs in de Commerce-toepassing kan niet worden ingeschakeld wanneer de extensie voor indexering van de SaaS-prijs is geïnstalleerd.
- **Prijsprovider**- Deze module biedt prijzen voor producten van de Adobe Commerce Service. Het vormt de onderzoeksvraag en verkrijgt de prijzen voor de producten op het front.
- **Zoekadapter voor catalogusservice**- Deze module brengt de prijzen van de Adobe Commerce-toepassing over naar een Adobe Commerce-service in reactie op een aanvraag voor het zoeken van producten.

## Installatiestappen

>[!BEGINTABS]

>[!TAB Cloud-infrastructuur]

Gebruik deze methode om de [!DNL Catalog Adapter] voor een Commerce Cloud-instantie.

1. Schakel op uw lokale werkstation de projectmap voor uw Adobe Commerce over het infrastructuurproject voor de cloud in.

   >[!NOTE]
   >
   >Voor informatie over het lokale beheer van Commerce-projectomgevingen raadpleegt u [Het leiden van takken met CLI](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/cli-branches) in de _Gebruikershandleiding Adobe Commerce on Cloud Infrastructure_.

1. Bekijk de omgevingsvertakking die u wilt bijwerken met de Adobe Commerce Cloud CLI.

   ```shell
   magento-cloud environment:checkout <environment-id>
   ```

1. Voeg de module Catalogusadapter toe.

   ```bash
   composer require magento/catalog-adapter --no-update
   ```

1. Pakketafhankelijkheden bijwerken.

   ```bash
   composer update "magento/catalog-adapter"
   ```

1. Wijzigingen in de code vastleggen en doorvoeren voor de `composer.json` en `composer.lock` bestanden.

1. De codewijzigingen toevoegen, toewijzen en doorvoeren voor de `composer.json` en `composer.lock` bestanden naar de cloud-omgeving.

   ```shell
   git add -A
   git commit -m "Add catalog adapter module"
   git push origin <branch-name>
   ```

   Als u de updates naar de cloudomgeving doorvoert, wordt het [Commerce-implementatieproces voor cloud](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/deploy/process) om de wijzigingen toe te passen. Controleer de implementatiestatus via de [logboek implementeren](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/test/log-locations#deploy-log).

>[!TAB In de bedrijfsruimten]

Gebruik deze methode om de [!DNL Catalog Adapter] voor een instantie ter plaatse.

1. Voeg de Adapter van de Catalogus aan uw project toe gebruikend Composer:

   ```bash
   composer require magento/catalog-adapter --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update  "magento/catalog-adapter"
   ```

1. Upgrade Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

   >[!TIP]
   >
   >In sommige gevallen, vooral wanneer het opstellen aan productie, zou u gecompileerde code kunnen willen vermijden omdat het wat tijd kan vergen. Zorg ervoor dat u een back-up van het systeem maakt voordat u wijzigingen aanbrengt.

>[!ENDTABS]


## De Adobe Commerce-productprijsindexator opnieuw inschakelen

Als u toepassingen van derden hebt die op de standaard het productprijsindexer van Adobe Commerce vertrouwen, kunt u het met de volgende bevelen opnieuw toelaten:

```bash
# re-enable Product Price indexer
bin/magento module:disable Magento_PriceIndexerDisabler
# re-index Product Price indexer
bin/magento index:reindex catalog_product_price
```

## De indexator van de Prijs van het Product voor Hoofdloze scenario onbruikbaar maken

Als u een Commerce-instantie zonder kop hebt, moet u mogelijk de Adobe Commerce-productprijsindexer uitschakelen om de belasting op uw Adobe Commerce-exemplaar te verminderen. U kunt deze taak uitvoeren door het `magento/module-price-indexer-disabler` module:

```bash
composer require magento/module-price-indexer-disabler
```

## Gebruiksscenario&#39;s

Hier volgen enkele voorbeelden `[!DNL Catalog Adapter]` scenario&#39;s.

### Geen afhankelijkheid van Adobe Commerce-productprijsindexator

- U bent een Luma- of Adobe Commerce Core GraphQL-handelaar die een vereiste service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
- Geen integratie met extensies van derden die afhankelijk zijn van de Adobe Commerce-productprijsindexer

1. Installeer de [!DNL Catalog Adapter].

### Met afhankelijkheid van Adobe Commerce product price indexer

- U bent een Luma- of Adobe Commerce Core GraphQL-handelaar die een ondersteunde service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
- U gebruikt een extensie van derden die afhankelijk is van de Adobe Commerce-productprijsindexer

1. Installeer de [!DNL Catalog Adapter].
1. Schakel de standaardindexeerfunctie voor Adobe Commerce-productprijzen opnieuw in.

### Headless Commerce-instanties

- Een bedrijf met een Commerce-exemplaar zonder kop waarop de vereiste services zijn geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
- Geen beroep op de standaard Adobe Commerce-productprijsindexer

1. Installeer de `magento/module-price-indexer-disabler` van de [!DNL Catalog Adapter] pakket.

