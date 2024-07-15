---
title: "Aan de slag met  [!DNL Live Search]"
description: "Leer de systeemvereisten en installatiestappen voor  [!DNL Live Search]  van Adobe Commerce."
exl-id: aa251bb0-d52c-4cff-bccb-76a08ae2a3b2
role: Admin, Developer
source-git-commit: aba1f41965e6c430f569adcf9d940cf399b50b73
workflow-type: tm+mt
source-wordcount: '2266'
ht-degree: 0%

---

# Instellen voor succes met [!DNL Live Search]

Adobe Commerce [!DNL Live Search] en [[!DNL Catalog Service]](../catalog-service/guide-overview.md) werken samen om een krachtige, relevante en intuïtieve zoekoplossing te bieden, zodat uw klanten snel precies kunnen vinden wat ze nodig hebben. [!DNL Catalog Service] bevat met name de catalogusgegevens die u wilt gebruiken voor SaaS-services, zoals [!DNL Live Search] .

Dit artikel bevat stapsgewijze instructies voor het implementeren van [!DNL Live Search] met [!DNL Catalog Service] .

>[!IMPORTANT]
>
>Adobe Commerce biedt opties voor het zoeken naar sites. Ben zeker om [ Grenzen en Grenswaarden ](boundaries-limits.md) te lezen alvorens uit te voeren, om te verzekeren [!DNL Live Search] geschikt voor uw bedrijfsbehoeften is.

## Publiek

Dit artikel is bedoeld voor de ontwikkelaar of systeemintegrator in uw team die verantwoordelijk is voor de installatie en configuratie van uw Adobe Commerce-exemplaar.

## Vereisten

- [ Adobe Commerce ](https://business.adobe.com/products/magento/magento-commerce.html) 2.4.4+
- PHP 8.1 / 8.2 / 8.3
- [!DNL Composer]

## Ondersteunde platforms

- Adobe Commerce on Cloud (ECE) : 2.4.4+
- Adobe Commerce on-prem (EE) : 2.4.4+

## Workflowoverzicht

Op een hoog niveau is het vereist dat u: [!DNL Live Search]

![ Live het Werkschema van het Onderzoek ](assets/livesearch-workflow.png)

## 1. Installeer de extensie [!DNL Live Search]

[!DNL Live Search] is geïnstalleerd als uitbreiding van [ Adobe Marketplace ](https://commercemarketplace.adobe.com/magento-live-search.html) door [ Composer ](https://getcomposer.org/). Nadat u [!DNL Live Search] hebt geïnstalleerd en geconfigureerd, begint Adobe [!DNL Commerce] met het delen van zoek- en catalogusgegevens met SaaS-services. Op dit punt, *Admin* kunnen de gebruikers opstelling, aanpassen, en onderzoeksfacetten, synoniemen, en handelswijzigingsregels beheren.

>[!NOTE]
>
>Vanaf [!DNL Live Search] 3.0.2 wordt de [!DNL Catalog Service] -extensie gebundeld in de [!DNL Live Search] -installatie.

1. Bevestig dat [ gewassenbanen ](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs) en [ indexeerders ](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/tools/index-management) lopen.

   >[!IMPORTANT]
   >
   >Gezien de Elasticsearch 7 eindeaankondiging voor augustus 2023, wordt aanbevolen dat alle Adobe Commerce-klanten naar de OpenSearch 2.x zoekmachine migreren. Voor informatie over het migreren van uw onderzoeksmotor tijdens een productverbetering, zie [ Migrerend aan OpenSearch ](https://experienceleague.adobe.com/en/docs/commerce-operations/upgrade-guide/prepare/opensearch-migration) in de _Gids van de Verbetering_.

1. Download het `live-search` pakket van de [ Marketplace van de Adobe ](https://commercemarketplace.adobe.com/magento-live-search.html).

1. Voer de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer require magento/live-search
   ```

   Als u de [!DNL Live Search] uitbreiding aan a **nieuwe** installatie van Adobe Commerce toevoegt, stel het volgende in werking om [!DNL OpenSearch] en verwante modules onbruikbaar te maken, en te installeren [!DNL Live Search]. Ga vervolgens verder met stap 4.

   ```bash
      bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch7 Magento_OpenSearch Magento_ElasticsearchCatalogPermissions Magento_InventoryElasticsearch Magento_ElasticsearchCatalogPermissionsGraphQl
   ```

   Als u de [!DNL Live Search] uitbreiding aan een **bestaande** installatie van Adobe Commerce toevoegt, stel het volgende in werking om de [!DNL Live Search] modules tijdelijk onbruikbaar te maken die de resultaten van het storefrontonderzoek dienen. Ga vervolgens verder met stap 4:

   ```bash
      bin/magento module:disable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover Magento_LiveSearchProductListing 
   ```

   [!DNL Elasticsearch] blijft zoekverzoeken van de winkel beheren terwijl de [!DNL Live Search] -service catalogusgegevens en indexproducten op de achtergrond synchroniseert.

1. Voer de volgende handelingen uit:

   ```bash
   bin/magento setup:upgrade
   ```

1. Verifieer dat de volgende [ indexeerders ](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/tools/index-management) aan &quot;Update door Programma&quot;worden geplaatst:

   - Productfeed
   - Diervoeders voor productvarianten
   - Feed voor cataloguskenmerken
   - Diervoeders productprijzen
   - Websitegegevensfeed
   - Scopes Klantengroepen Gegevensfeed
   - Diervoeders voor categorieën
   - Diervoeders voor categorierechten

1. Als u [!DNL Live Search] op een nieuwe instantie van Commerce installeert, wordt u gedaan en kunt overslaan aan [ 2. Vorm API sleutels ](#2-configure-api-keys) sectie. Ga door met de volgende stap als u Live Search installeert op een bestaand Commerce-exemplaar.

1. Voer de volgende opdrachten uit om de extensie [!DNL Live Search] in te schakelen, [!DNL OpenSearch] uit te schakelen en `setup` uit te voeren.

   ```bash
   bin/magento module:enable Magento_LiveSearchAdapter Magento_LiveSearchStorefrontPopover  Magento_LiveSearchProductListing 
   ```

   ```bash
   bin/magento module:disable Magento_Elasticsearch Magento_Elasticsearch6 Magento_Elasticsearch7 Magento_ElasticsearchCatalogPermissions Magento_InventoryElasticsearch 
   Magento_ElasticsearchCatalogPermissionsGraphQl
   ```

   ```bash
   bin/magento setup:upgrade
   ```

## 2. API-sleutels configureren

De Adobe Commerce API-sleutel en de bijbehorende persoonlijke sleutel zijn vereist om [!DNL Live Search] te verbinden met een installatie van Adobe Commerce. De API-sleutel wordt gegenereerd en onderhouden in de account van de [!DNL Commerce] -licentienemer, die deze kan delen met de ontwikkelaar of de systeemintegrator. De ontwikkelaar kan vervolgens de SaaS-gegevensruimten maken en beheren namens de licentiehouder. Als u al een set API-sleutels hebt, hoeft u deze niet opnieuw te genereren.

Leer hoe te om uw API sleutels in het [ 1} artikel van de Schakelaar van de Diensten van Commerce te vormen.](../landing/saas.md)

## 3. Synchroniseer uw catalogusgegevens {#synchronize-catalog-data}

[!DNL Live Search] verplaatst catalogusgegevens naar de SaaS-infrastructuur van de Adobe. De gegevens worden geïndexeerd en de zoekresultaten worden vanuit deze index rechtstreeks aan de winkel geleverd. Afhankelijk van de grootte en complexiteit kan het indexeren 30 minuten tot een paar uur duren.

Voer de volgende opdrachten in deze volgorde uit om te beginnen met de eerste synchronisatie van uw catalogusgegevens naar SaaS-services:

```bash
bin/magento saas:resync --feed productattributes
bin/magento saas:resync --feed products
bin/magento saas:resync --feed scopesCustomerGroup
bin/magento saas:resync --feed scopesWebsite
bin/magento saas:resync --feed prices
bin/magento saas:resync --feed productoverrides
bin/magento saas:resync --feed variants
bin/magento saas:resync --feed categories
bin/magento saas:resync --feed categoryPermissions
```

Wanneer u deze opdrachten uitvoert, begint de eerste synchronisatie van de catalogusgegevens met de SaaS-services.

>[!WARNING]
>
> Terwijl de gegevens worden geïndexeerd en gesynchroniseerd, zijn de zoek en de categorie doorbladerbewerkingen niet beschikbaar in de winkel. Afhankelijk van de grootte van uw catalogus kan het proces minstens een uur duren vanaf de tijd dat `cron` wordt uitgevoerd om uw gegevens te synchroniseren met SaaS-services.

### Synchronisatievoortgang controleren

U kunt de gegevens bekijken die worden gesynchroniseerd en worden gedeeld gebruikend het [ Dashboard van het Beheer van Gegevens ](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard). Dit dashboard biedt waardevolle inzichten in de beschikbaarheid van productgegevens voor uw winkel, zodat deze direct aan uw klanten kunnen worden weergegeven.

![ Dashboard van het Beheer van Gegevens ](assets/data-management-dashboard.png)

#### Updates voor toekomstige producten

Na de eerste synchronisatie kan het tot 15 minuten duren voordat de incrementele productupdates beschikbaar komen voor het zoeken naar een winkel. Om meer te leren, zie [ Indexeren - het stromen de Updates van het Product ](indexing.md).

## 4. Controleer of de gegevens zijn geëxporteerd {#verify-export}

U hebt een aantal opties om te controleren of de catalogusgegevens uit uw Adobe Commerce-exemplaar zijn geëxporteerd en voor [!DNL Live Search] zijn gesynchroniseerd:

- Zoek naar ingangen in de volgende lijsten:

   - `catalog_data_exporter_products`
   - `catalog_data_exporter_product_attributes`

- Gebruik [ playground van GraphQL ](https://developer.adobe.com/commerce/services/graphql/live-search/) met de standaardvraag om het volgende te verifiëren:

   - Het aantal geretourneerde producten ligt dicht bij wat u voor de winkelweergave verwacht.
   - Facetten worden geretourneerd.

Voor extra hulp, zie [[!DNL Live Search]  niet gesynchroniseerde catalogus ](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/live-search-catalog-data-sync) in de Kennisbank van de Steun.

## 5. Vorm de gegevens

Als u uw productgegevens correct configureert, bent u verzekerd van goede zoekresultaten voor uw klanten. In deze sectie schakelt u de widgets voor productlijsten in en wijst u categorieën toe.

### Widgets productlijst inschakelen

Wanneer u [!DNL Live Search] 4.0.0+ installeert, worden de Widgets van de Lijst van het Product door gebrek toegelaten. Wanneer widgets zijn ingeschakeld, wordt een andere UI-component gebruikt voor de pagina met zoekresultaten en voor de pagina met productaanbiedingen in de categorie. Deze component UI doet directe vraag aan de [ Dienst API van de Catalogus ](https://developer.adobe.com/commerce/services/graphql/catalog-service/product-search/), die in snellere reactietijden resulteert.

Als u een [!DNL Live Search] -versie hebt die ouder is dan 4.0.0+, moet u de widget Productaanbieding handmatig inschakelen.

1. Van *Admin*, ga **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Selecteer onder **[!UICONTROL Live Search]** de optie **[!UICONTROL Storefront Features]** .
1. Stel **[!UICONTROL Enable Product Listing Widgets]** in op `Yes` .

   ![ laat het Lijst van het Product toe Widgets ](assets/ls-admin-enable-widget.png)

Wanneer u deze configuratie wijzigt, verschijnt het bericht `Page cache is invalidated` . U moet het Geheime voorgeheugen van het Magento leegmaken om uw verandering te bewaren.

1. Heb toegang tot de [ pagina van het Beheer van het Geheime voorgeheugen ](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/tools/cache-management) door één van het volgende te doen:

   - Klik op de koppeling **[!UICONTROL Cache Management]** in het bericht boven de werkruimte.
   - Voor _Admin_ sidebar, ga **[!UICONTROL System]** > _[!UICONTROL Tools]_>**[!UICONTROL Cache Management]**.

1. Selecteer de **Configuratie** [!UICONTROL Cache Type] en klik **[!UICONTROL Flush Magento Cache]**.

   Wijzigingen in de winkel worden direct na het leegmaken van de cache aangebracht.

### Categorieën toewijzen

De producten die in [!DNL Live Search] zijn teruggekeerd moeten aan a [ worden toegewezen categorie ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/categories/categories). In Luma worden producten bijvoorbeeld ingedeeld in categorieën zoals &quot;Mannen&quot;, &quot;Vrouwen&quot; en &quot;Luma&quot;. Subcategorieën worden ook ingesteld voor Tops, Bottoms en Watches. Hierdoor wordt de korreligheid bij het filteren verbeterd.

## 6. Test de verbinding {#test-connection}

Met uw catalogusgegevens nu in SaaS, test om ervoor te zorgen de productgegevens in de volgende scenario&#39;s zijn teruggekeerd:

- Het vak [!UICONTROL Search] retourneert de juiste resultaten
- Met bladeren door categorie worden de resultaten correct geretourneerd
- Factoren zijn als filters beschikbaar op pagina&#39;s met zoekresultaten

Als alles correct werkt, wordt [!DNL Live Search] geïnstalleerd, aangesloten en klaar te gebruiken.

Als u problemen tegenkomt in de winkel, controleert u het bestand `var/log/system.log` op API-communicatiefouten of -fouten aan de kant van de service.

Als u [!DNL Live Search] wilt toestaan via een firewall, voegt u `commerce.adobe.io` toe aan de lijst van gewenste personen.

## 7. Aanpassen voor je winkel

U hebt de extensie [!DNL Live Search] geïnstalleerd, gesynchroniseerd, gevalideerd en geconfigureerd. Nu wilt u ervoor zorgen dat de [!DNL Live Search] -widgets overeenkomen met de vormgeving van uw winkel.

U kunt de popover- en PLP-widgets opmaken door desgewenst aangepaste CSS-regels te definiëren. Zie [ het Stijlen Popover Elementen ](storefront-popover.md#styling-popover-example) en [ van de Lijst van het Product de Widget van de Pagina ](plp-styling.md#styling-example).

Als u de functionaliteit van de widgets wilt uitbreiden, is de broncode voor elke widget beschikbaar in een openbare reactie.
In dit scenario, kunt u JavaScript voor uw eigen behoeften aanpassen en dan uw douanecode ontvangen op uw CDN. Dit aangepaste script communiceert met de service [!DNL Live Search] en retourneert de resultaten zoals normaal, zodat u de functionaliteit van de widget kunt beheren.

- [ PLP widget repo ](https://github.com/adobe/storefront-product-listing-page)
- [ de bar van het Onderzoek repo ](https://github.com/adobe/storefront-search-as-you-type)

## [!DNL Live Search] bijwerken {#update}

Voer voordat u Live zoeken bijwerkt de volgende handelingen uit vanaf de opdrachtregel om de geïnstalleerde versie van Live Search te controleren:

```bash
composer show magento/module-live-search | grep version
```

Voer de volgende handelingen uit vanaf de opdrachtregel om [!DNL Live Search] bij te werken:

```bash
composer update magento/live-search --with-dependencies
```

Als u een update wilt uitvoeren naar een belangrijke versie zoals 3.1.1 en 4.0.0, bewerkt u het hoofdbestand [!DNL Composer] `.json` van het project als volgt:

1. Als de momenteel geïnstalleerde `magento/live-search` versie `3.1.1` of lager is en u een upgrade uitvoert naar versie `4.0.0` of hoger, voert u de volgende opdracht uit vóór de upgrade:

   ```bash
   bin/magento module:enable Magento_AdvancedSearch
   ```

   Voer de volgende opdracht uit voor informatie over de momenteel geïnstalleerde versie van `magento/live-search` :

   ```bash
   composer show magento/live-search
   ```

1. Open het hoofdbestand `composer.json` en zoek naar `magento/live-search` .

1. Werk in de sectie `require` het versienummer als volgt bij:

   ```json
   "require": {
      ...
      "magento/live-search": "^4.0",
      ...
    }
   ```

1. Opslaan `composer.json` . Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/live-search --with-dependencies
   ```

## [!DNL Live Search] verwijderen {#uninstall}

Om [!DNL Live Search] te desinstalleren, verwijs naar [ modules van de Desinstallatie ](https://experienceleague.adobe.com/en/docs/commerce-operations/installation-guide/tutorials/uninstall-modules).

## [!DNL Live Search] pakketten {#packages}

De extensie [!DNL Live Search] bestaat uit de volgende pakketten:

| Pakket | Beschrijving |
|--- |--- |
| `module-live-search` | Staat verkopers toe om hun onderzoeksmontages voor facetting, synoniemen, vraagregels, etc. te vormen, en verleent toegang tot read-only GraphQL playground om vragen van *te testen Admin*. |
| `module-live-search-adapter` | Routes onderzoeksverzoeken van de storefront aan de [!DNL Live Search] dienst en geeft de resultaten in de storefront terug. <br /> - de doorblader van de Categorie - Routes verzoekt van de storefront [ hoogste navigatie ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/catalog/navigation/navigation-top) aan de onderzoeksdienst.<br /> - Globaal onderzoek - Routes verzoekt van de [ snelle onderzoek ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/catalog/search/search) doos in het hoger-recht van de storefront aan de [!DNL Live Search] dienst. |
| `module-live-search-storefront-popover` | De pop-up &#39;&#39;Zoeken terwijl u typt&#39;&#39; vervangt de standaard snelle zoekopdracht en retourneert gegevens en miniaturen van de bovenste zoekresultaten. |

## [!DNL Live Search] afhankelijkheden {#dependencies}

De volgende [!DNL Live Search] afhankelijkheden worden vastgelegd door [!DNL Composer] .

- `magento/module-saas-catalog`
- `magento/module-saas-category`
- `magento/module-saas-category-permissions`
- `magento/module-saas-product-override`
- `magento/module-saas-product-variant`
- `magento/module-saas-price`
- `magento/module-saas-scopes`
- `magento/module-bundle-product-data-exporter`
- `magento/module-catalog-inventory-data-exporter`
- `magento/module-catalog-url-rewrite-data-exporter`
- `magento/module-configurable-product-data-exporter`
- `magento/module-parent-product-data-exporter`
- `magento/module-gift-card-product-data-exporter`
- `magento/module-bundle-product-override-data-exporter`
- `data-services`
- `services-id`

## Geavanceerde concepten

De volgende secties bieden geavanceerdere onderwerpen wanneer u [!DNL Live Search] en [!DNL Catalog Service] gebruikt.

### Endpoint

[!DNL Live Search] communiceert via het eindpunt op `https://catalog-service.adobe.io/graphql` .

Aangezien [!DNL Live Search] geen toegang heeft tot de volledige productdatabase, hebben [!DNL Live Search] GraphQL en Commerce core GraphQL geen volledige pariteit.

Het wordt geadviseerd om SaaS APIs direct te roepen - specifiek het eindpunt van de Dienst van de Catalogus.

- Verhoog de prestaties en verlaag de processorbelasting door het Commerce-database/Graphql-proces te omzeilen
- Haal voordeel uit de [!DNL Catalog Service] -federatie om [!DNL Live Search] , [!DNL Catalog Service] en [!DNL Product Recommendations] vanaf één eindpunt aan te roepen.

In sommige gevallen is het beter om [!DNL Catalog Service] op te roepen voor productdetails en vergelijkbare gevallen. Zie [ refineProduct ](https://developer.adobe.com/commerce/services/graphql/catalog-service/refine-product/) voor meer informatie.

Als u een aangepaste implementatie zonder kop hebt, checkt u de [!DNL Live Search] referentie-implementaties uit:

- [ PLP widget ](https://github.com/adobe/storefront-product-listing-page)
- [ Levend gebied van het Onderzoek ](https://github.com/adobe/storefront-search-as-you-type)

Als u niet de standaardcomponenten, zoals de Adapter of widgets van het Onderzoek op Luma, of AEM widgets gebruikt, zal de gebeurtenis (klikstroomgegevens die Adobe Sensei voor Intelligente Merchandising en prestatiesmetriek van de voer voorzien) niet uit de doos werken en zal de douaneontwikkeling vereisen om hoofdloze gebeurtenis uit te voeren.

De meest recente versie van [!DNL Live Search] gebruikt [!DNL Catalog Service] al.

### Taalondersteuning

[!DNL Live Search] -widgets ondersteunen de volgende talen:

|  |  |  |  |
|--- |--- |--- |--- |
| Taal | Regio | Taalcode | Landinstelling Magento |
| Bulgaars | Bulgarije | bg_BG | bg_BG |
| Catalaans | Spanje | ca_ES | ca_ES |
| Tsjechisch | Tsjechië | cs_CZ | cs_CZ |
| Deens | Denemarken | da_DK | da_DK |
| Duits | Duitsland | de_DE | de_DE |
| Grieks | Griekenland | el_GR | el_GR |
| Engels | Verenigd Koninkrijk | en_GB | en_GB |
| Engels | Verenigde Staten | nl_NL | nl_NL |
| Spaans | Spanje | es_ES | es_ES |
| Ests | Estland | et_EE | et_EE |
| Baskisch | Spanje | eu_ES | eu_ES |
| Perzisch | Iran | fa_IR | fa_IR |
| Fins | Finland | fi_FI | fi_FI |
| Frans | Frankrijk | fr_FR | fr_FR |
| Galicisch | Spanje | gl_ES | gl_ES |
| Hindi | India | hi_IN | hi_IN |
| Hongaars | Hongarije | hu_HU | hu_HU |
| Indonesische | Indonesië | id_ID | id_ID |
| Italiaans | Italië | it_IT | it_IT |
| Koreaans | Zuid-Korea | ko_KR | ko_KR |
| Litouws | Litouwen | lt_LT | lt_LT |
| Lets | Letland | lv_LV | lv_LV |
| Noors | Norway Bokmal | nb_NO | nb_NO |
| Nederlands | Nederland | nl_NL | nl_NL |
| Pools | Polen | pl_PL | pl_PL |
| Portugees | Brazilië | pt_BR | pt_BR |
| Portugees | Portugal | pt_PT | pt_PT |
| Roemeens | Roemenië | ro_RO | ro_RO |
| Russisch | Rusland | ru_RU | ru_RU |
| Zweeds | Zweden | sv_SE | sv_SE |
| Thai | Thailand | th_TH | th_TH |
| Turks | Turkije | tr_TR | tr_TR |
| Chinees | China | zh_CN | zh_Hans_CN |
| Chinees | Taiwan | zh_TW | zh_Hant_TW |

Als widget ontdekt dat de taal die van Commerce Admin (_plaatst opslaat_ > Montages > _Configuratie_ > _Algemene_ > de Opties van het Land) een gesteunde taal aanpast, blijft het aan die taal in gebreke. Anders worden de widgets standaard ingesteld op Engels.

Admins kan de taal van de [ onderzoeksindex ](settings.md#language) ook plaatsen, helpen betere onderzoeksresultaten verzekeren.

### Widget-codeopslagplaats

De widget pagina met productlijsten en de widget veld Live zoeken kunnen beide worden gedownload van hun kleine opslagplaats.

Op deze manier kunnen ontwikkelaars de functionaliteit en opmaak volledig aanpassen. Deze gebruikers hosten de code zelf terwijl het voordeel van de [!DNL Live Search] dienst blijft.

- [ PLP widget ](https://github.com/adobe/storefront-product-listing-page)
- [ bar van het Onderzoek ](https://github.com/adobe/storefront-search-as-you-type)

### Inventory management

[!DNL Live Search] steunt [ Inventory management ](https://experienceleague.adobe.com/en/docs/commerce-admin/inventory/introduction) mogelijkheden in Commerce (weet vroeger als Voorraad Multi-Source, of MSI). Om volledige steun toe te laten, moet u ](install.md#update) de gebiedsdeelmodule `commerce-data-export` aan versie 102.2.0+ bijwerken.[

[!DNL Live Search] retourneert een Booleaanse waarde die aangeeft of een product beschikbaar is in Inventory management, maar die geen informatie bevat over de bron die de voorraad heeft.

### Prijsindexering

De actieve klanten van het Onderzoek kunnen de nieuwe [ prijsindexeerder SaaS ](../price-index/price-indexing.md) gebruiken, die snellere de updates van de prijsverandering en synchronisatietijd verstrekt.

### Prijsondersteuning

Live zoekwidgets bieden ondersteuning voor de meeste, maar niet voor alle typen prijzen die door Adobe Commerce worden ondersteund.

Momenteel worden de basisprijzen ondersteund. Geavanceerde prijzen die niet worden ondersteund zijn:

- Kosten
- Minimale geadverteerde prijs

Kijk naar [ API Net ](../catalog-service/mesh.md) voor complexere prijsberekeningen.

Het prijsformaat steunt de scèneconfiguratie die binnen de instantie van Commerce plaatst: *Slaat* > Montages > *Configuratie* > Algemeen > *Algemene* > Lokale Opties > Scène op.

### Ondersteuning voor headless Storefront

U kunt desgewenst de module `module-data-services-graphql` installeren die de bestaande GraphQL-dekking van de toepassing uitbreidt, zodat deze velden bevat die vereist zijn voor het verzamelen van gedragsgegevens van de winkel.

```bash
composer require magento/module-data-services-graphql
```

Deze module voegt extra contexten aan de vragen van GraphQL toe:

- `dataServicesStorefrontInstanceContext`
- `dataServicesMagentoExtensionContext`
- `dataServicesStoreConfigurationContext`

### B2B-ondersteuning

[!DNL Live Search] steunt [ functionaliteit B2B ](https://experienceleague.adobe.com/en/docs/commerce-admin/b2b/guide-overview) met extra [ beperkingen ](boundaries-limits.md#b2b-and-category-permissions).

### PWA-ondersteuning

[!DNL Live Search] werkt met PWA Studio, maar gebruikers zien mogelijk kleine verschillen ten opzichte van andere Commerce-implementaties. De basisfunctionaliteit zoals zoeken en pagina met productlijsten werkt in Venia, maar sommige permutaties van Graphql werken mogelijk niet correct. Er kunnen ook prestatieverschillen zijn.

- De huidige PWA-implementatie van [!DNL Live Search] vereist meer verwerkingstijd om zoekresultaten te retourneren dan [!DNL Live Search] met de native Commerce-storefront.
- [!DNL Live Search] in PWA steunt [ gebeurtenis behandeling ](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) niet. Zodoende zullen zoekverslagen en intelligente koophandel werken.
- Het filtreren direct op `description`, `name`, `short_description` wordt niet gesteund door GraphQL wanneer gebruikt met [ PWA ](https://developer.adobe.com/commerce/pwa-studio/), maar zij zijn teruggekeerd met een meer algemene filter.

Als u [!DNL Live Search] met PWA Studio wilt gebruiken, moeten integrators ook:

1. Installeer [ livessearch-storefront-utils ](https://www.npmjs.com/package/@magento/ds-livesearch-storefront-utils).
1. Stel de waarde `environmentId` in het `storeDetails` -object in.

   ```javascript
   const storeDetails: StoreDetailsProps = {
       environmentId: <Storefront_ID>,
       websiteCode: "base",
       storeCode: "main_website_store",
       storeViewCode: "default",
       searchUnitId: searchUnitId,
       config: {
           minQueryLength: 5,
           pageSize: 8,
           currencySymbol: "$",
           },
       };
   ```

### Cookies

[!DNL Live Search] verzamelt gegevens over gebruikersinteractie als onderdeel van de basisfunctionaliteit en cookies worden gebruikt om deze gegevens op te slaan. Wanneer de gebruiker om het even welke gebruikersinformatie verzamelt, moet de gebruiker ermee instemmen om koekjes op te slaan. [!DNL Live Search] en [!DNL Product Recommendations] delen de gegevensstroom en dus hetzelfde cookiemechanisme. Lees meer over het in [ de Beperkingen van de Koekjescookie ](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/product-recommendations/developer/setting-cookie).
