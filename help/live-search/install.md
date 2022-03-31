---
title: Live zoeken installeren
description: Leer hoe u Live Search kunt installeren, bijwerken en verwijderen vanuit Adobe Commerce.
exl-id: aa251bb0-d52c-4cff-bccb-76a08ae2a3b2
source-git-commit: c70d08b90d7584559fd69cdeece0220015ae8523
workflow-type: tm+mt
source-wordcount: '1199'
ht-degree: 0%

---

# Installeren [!DNL Live Search]

Live zoeken wordt als extensie van Adobe Marketplace geïnstalleerd. Na de [!DNL Live Search] module (met catalogusmodules als afhankelijkheden) is geïnstalleerd en geconfigureerd, [!DNL Commerce] begint onderzoek en catalogusgegevens met de diensten te delen SaaS. Op dit punt *Beheer* gebruikers kunnen zoekfacetten, synoniemen en regels voor het wijzigen van handelsversies instellen, aanpassen en beheren.

Dit onderwerp verstrekt instructies om het volgende te doen:

* [Installeren [!DNL Live Search]](#before-you-begin) (Methoden 1 en 2)
* [Bijwerken [!DNL Live Search]](#update)
* [Verwijderen [!DNL Live Search]](#uninstall)

## Voordat u begint {#before-you-begin}

Ga als volgt te werk:

1. Bevestig dat [kroonbanen](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html) en [indexeerders](https://docs.magento.com/user-guide/system/index-management.html) worden uitgevoerd.

1. Kies de instapmethode die aan uw vereisten voldoet en volg de instructies.

   * [Methode 1](#method-1): Installeren zonder [!DNL Elasticsearch]
   * [Methode 2](#method-2): Installeren met [!DNL Elasticsearch] (Geen downtime)

## Methode 1: Installeren zonder Elasticsearch {#method-1}

Deze instapmethode wordt aanbevolen bij de installatie [!DNL Live Search] tot en met a:

* Nieuw [!DNL Commerce] installatie
* Stationele omgeving

In dit scenario worden storefront-bewerkingen onderbroken terwijl de [!DNL Live Search] de dienst indexeert alle producten in de catalogus. Tijdens de installatie [!DNL Live Search] modules worden ingeschakeld en [!DNL Elasticsearch] modules zijn uitgeschakeld.

>[!TIP]
>
>Als u typefouten wilt voorkomen, houdt u de muisaanwijzer helemaal rechts van het codevak ingedrukt en klikt u op de knop [!UICONTROL **Kopiëren**] en plak deze in de opdrachtregel.

1. Adobe Commerce 2.4.x installeren zonder [!DNL Live Search].

1. Als u het dialoogvenster `live-search` pakket, voer het volgende uit vanaf de bevellijn:

   ```bash
   composer require magento/DNL live-search
   ```

   Raadpleeg de lijst met [!DNL Live Search] [afhankelijkheden](#dependencies) die zijn vastgelegd door [!DNL Composer].

1. Voer de volgende opdrachten uit om uit te schakelen [!DNL Elasticsearch] en bijbehorende modules, en installeren [!DNL Live Search]:

   ```bash
   bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch6 Magento_Elasticsearch7 Magento_ElasticsearchCatalogPermissions Magento_InventoryElasticsearch
   ```

   ```bash
   bin/magento setup:upgrade
   ```

   >[!WARNING]
   >
   > Terwijl de gegevens worden geïndexeerd en gesynchroniseerd, zijn de zoek en de categorie doorbladerbewerkingen niet beschikbaar in de winkel. Afhankelijk van de grootte van de catalogus kan het proces minstens een uur duren `cron` wordt uitgevoerd om uw gegevens te synchroniseren naar [!DNL Live Search] diensten.

1. Controleer of het volgende [indexeerders](https://docs.magento.com/user-guide/system/index-management.html) zijn ingesteld op `Update by Schedule`:

   * Productfeed
   * Diervoeders voor productvarianten
   * Feed voor cataloguskenmerken

1. Configureer uw [API-sleutels](#configure-api-keys) en controleer of de catalogusgegevens [gesynchroniseerd](#synchronize-catalog-data) with [!DNL Live Search] diensten.

1. Als u facetten als filters in de winkel beschikbaar wilt maken, voegt u de opdracht [facetten](facets-add.md) u, volgens [eisen inzake facetten](facets.md).

   U moet facetten kunnen toevoegen na `cron` Hiermee worden de metagegevens van kenmerkfeeds en exportkenmerken uitgevoerd.

1. Wacht minstens een uur na `cron` wordt uitgevoerd om gegevens te synchroniseren. Vervolgens [verifiëren](#verify-export) of de gegevens zijn geëxporteerd.

1. [Testen](#test-the-connection) de verbinding van de storefront.

## Methode 2: Installeren met Elasticsearch {#method-2}

Deze instapmethode wordt aanbevolen bij de installatie [!DNL Live Search] tot:

* Een bestaande productie [!DNL Commerce] installatie

In dit scenario: [!DNL Elasticsearch] beheert tijdelijk zoekverzoeken van de winkel terwijl de [!DNL Live Search] de dienst indexeert alle producten op de achtergrond, zonder enige onderbreking aan normale opslagverrichtingen. [!DNL Elasticsearch] is uitgeschakeld en [!DNL Live Search] ingeschakeld nadat alle catalogusgegevens zijn geïndexeerd en gesynchroniseerd.

>[!TIP]
>
>Als u typefouten wilt voorkomen, houdt u de muisaanwijzer helemaal rechts van het codevak ingedrukt en klikt u op de knop [!UICONTROL **Kopiëren**] en plak deze in de opdrachtregel.

1. Als u het dialoogvenster `live-search` pakket, voer het volgende uit vanaf de bevellijn:

   ```bash
   composer require magento/live-search
   ```

   Raadpleeg de lijst met [!DNL Live Search] [afhankelijkheden](#live-search-dependencies) die zijn vastgelegd door [!DNL Composer].

1. Voer de volgende opdracht uit om de opdracht tijdelijk uit te schakelen [!DNL Live Search] modules die zoekresultaten leveren.

   ```bash
   bin/magento module:disable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover
   ```

   ```bash
   bin/magento setup:upgrade
   ```

   [!DNL Elasticsearch] blijft zoekverzoeken van de winkel beheren terwijl de [!DNL Live Search] De dienst synchroniseert catalogusgegevens en indexeert producten op de achtergrond.

1. Controleer of het volgende [indexeerders](https://docs.magento.com/user-guide/system/index-management.html) zijn ingesteld op `Update by Schedule`:

   * Productfeed
   * Diervoeders voor productvarianten
   * Feed voor cataloguskenmerken

1. Configureer uw [API-sleutels](#configure-api-keys) en controleer of de catalogusgegevens [gesynchroniseerd](#synchronize-catalog-data) with [!DNL Live Search] diensten.

1. Als u facetten als filters in de winkel beschikbaar wilt maken, voegt u de opdracht [facetten](facets-add.md) u, volgens [eisen inzake facetten](facets.md).

   U moet facetten kunnen toevoegen na `cron` Hiermee worden de metagegevens van het product en het kenmerk uitgevoerd en geëxporteerd naar [!DNL Live Search] diensten.

1. Wacht minstens een uur tot de gegevens worden geïndexeerd en worden gesynchroniseerd. Gebruik vervolgens de [GraphQL-speelplaats](https://devdocs.magento.com/live-search/graphql-support.html) met de standaardvraag om het volgende te verifiëren:

   * Het aantal geretourneerde producten ligt dicht bij wat u voor de winkelweergave verwacht.
   * Facet(s) worden geretourneerd.

1. Voer de volgende opdrachten uit om [!DNL Live Search] modules, uitschakelen [!DNL Elasticsearch]en uitvoeren `setup`.

   ```bash
   bin/magento module:enable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover
   ```

   ```bash
   bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch6 Magento_Elasticsearch7 Magento_ElasticsearchCatalogPermissions Magento_InventoryElasticsearch
   ```

   ```bash
   bin/magento setup:upgrade
   ```

1. [Testen](#test-the-connection) de verbinding van de storefront.

## API-sleutels configureren {#configure-api-keys}

De Adobe Commerce API-sleutel en de bijbehorende persoonlijke sleutel zijn vereist om verbinding te maken [!DNL Live Search] naar een installatie van Adobe Commerce. De API-sleutel wordt gegenereerd en onderhouden in de account van de [!DNL Commerce] vergunninghouder, die het met de ontwikkelaar of SI kan delen. De ontwikkelaar kan vervolgens de SaaS-gegevensruimten maken en beheren namens de licentiehouder.

### Adobe Commerce-vergunninghouder

Als u een API-sleutel en een persoonlijke sleutel wilt genereren, raadpleegt u [Commerce Services Connector](https://docs.magento.com/user-guide/system/saas.html).

### Adobe Commerce-ontwikkelaar of SI

De ontwikkelaar of SI vormt de SaaS gegevensruimte zoals die in de sectie van de Diensten van de Handel van de configuratie wordt beschreven. In de *Beheer*, wordt de Diensten van de Handel beschikbaar in sidebar van de Configuratie wanneer een module SaaS wordt geïnstalleerd.

## Catalogusgegevens synchroniseren {#synchronize-catalog-data}

[!DNL Live Search] vereist gesynchroniseerde productgegevens voor onderzoeksverrichtingen, en gesynchroniseerde attributengegevens om facetten te vormen. De eerste synchronisatie tussen de productcatalogus en de catalogusservice begint wanneer [!DNL Live Search] is eerst verbonden. Afhankelijk van de installatiemethode en de grootte van de catalogus kan het maximaal acht uur duren voordat de gegevens zijn geëxporteerd en geïndexeerd door [!DNL Live Search]. De lijst met gegevens die met de catalogusservice worden gesynchroniseerd en gedeeld, vindt u in het schema, dat wordt gedefinieerd in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

### Exporteren verifiëren {#verify-export}

Om te controleren of de catalogusgegevens uit uw Adobe Commerce-exemplaar zijn geëxporteerd en zijn gesynchroniseerd voor [!DNL Live Search], zoekt u naar items in de volgende tabellen:

* `catalog_data_exporter_products`
* `catalog_data_exporter_product_attributes`

Raadpleeg voor meer informatie [[!DNL Live Search] catalogus niet gesynchroniseerd](https://support.magento.com/hc/en-us/articles/4405637804301-Live-search-catalog-not-synchronized) in de Support Knowledge Base.

### Toekomstige productupdates

Na de eerste synchronisatie kan het tot 15 minuten duren voordat incrementele productupdates beschikbaar komen voor het zoeken naar winkelinformatie. Ga voor meer informatie naar [Streaming productupdates](indexing.md).

## De verbinding testen {#test-connection}

Controleer in de winkel het volgende:

* De [!UICONTROL Search] geeft de resultaten correct weer
* Met bladeren door categorie worden de resultaten correct geretourneerd
* Facet(s) zijn als filters beschikbaar op pagina&#39;s met zoekresultaten

Als alles goed werkt, gefeliciteerd! [!DNL Live Search] is geïnstalleerd, verbonden en gebruiksklaar.

Als er problemen optreden in de winkel, controleert u de `var/log/system.log` bestand voor API-communicatiefouten of -fouten aan de kant van de services.

## Bijwerken [!DNL Live Search] {#update}

Bijwerken [!DNL Live Search], voert u de volgende handelingen uit vanaf de opdrachtregel:

```bash
composer update magento/live-search --with-dependencies
```

Als u wilt bijwerken naar een hoofdversie zoals 1.0.0 tot 2.0.0, bewerkt u de hoofdmap van het project [!DNL Composer] `.json` bestand als volgt:

1. De hoofdmap openen `composer.json` bestand en zoek naar `magento/live-search`.

1. In de `require` het versienummer als volgt bijwerken:

   ```json
   "require": {
      ...
      "magento/live-search": "^2.0",
      ...
    }
   ```

1. **Opslaan** `composer.json`. Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/live-search –-with-dependencies
   ```

## Verwijderen [!DNL Live Search] {#uninstall}

Om te verwijderen [!DNL Live Search], zie [Modules verwijderen](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html).

## [!DNL Live Search] pakketten {#packages}

| Pakket | Beschrijving |
|--- |--- |
| `module-live-search` | Staat verkopers toe om hun onderzoeksmontages voor faceting, synoniemen, vraagregels, enz. te vormen, en verleent toegang tot read-only playground GraphQL om vragen van te testen *Beheer*. |
| `module-live-search-adapter` | Routes onderzoeksverzoeken van de storefront aan [!DNL Live Search] en geeft de resultaten weer in de winkel. <br />- Rubriekbrowse - Routaanvragen van de winkel [topnavigatie](https://docs.magento.com/user-guide/catalog/navigation-top.html) aan de zoekdienst.<br />- Globale zoekactie - Routverzoeken van de [snel zoeken](https://docs.magento.com/user-guide/catalog/search-quick.html) in de rechterbovenhoek van de winkel [!DNL Live Search] service. |
| `module-live-search-storefront-popover` | De pop-up &#39;&#39;Zoeken terwijl u typt&#39;&#39; vervangt de standaard snelle zoekopdracht en retourneert dynamische productsuggesties en miniaturen van de bovenste zoekresultaten. |

## [!DNL Live Search] afhankelijkheden {#dependencies}

Het volgende [!DNL Live Search] afhankelijkheden worden vastgelegd door [!DNL Composer]:

| Afhankelijkheid | Beschrijving |
|--- |--- |
| Exportmodules | In de volgende modules worden catalogusgegevens verzameld en gesynchroniseerd:<br />`saas-export`<br />`module-bundle-product-exporter`<br />`module-catalog-data-exporter`<br />`module-catalog-inventory-data-exporter`<br />`module-catalog-url-rewrite-data-exporter`<br />`module-configurable-product-data-exporter`<br />`module-data-exporter`<br />`module-parent-product-data-exporter` |
| `services-connector` | Vereist om uw verbinding aan de Diensten van de Handel te vormen. |
| `module-services-id` | Vereist om uw verbinding aan de Diensten van de Handel te vormen. |
