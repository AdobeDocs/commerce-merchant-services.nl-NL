---
title: "Indexing"
description: "Leer hoe  [!DNL Live Search]  de eigenschappen van het productattribuut van indexen."
exl-id: 04441e58-ffac-4335-aa26-893988a89720
source-git-commit: 4978bdb5549f5df911863a23fdfbfc9ab9ad05df
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# Indexeren

Het [!DNL Live Search] indexeringsproces leest door de catalogus voor productattributen en bouwt een index zodat de producten kunnen worden gezocht, worden gefiltreerd en snel worden voorgesteld.

Eigenschappen van productkenmerken (metagegevens) bepalen:

* Hoe een attribuut in de catalogus kan worden gebruikt
* De vormgeving en het gedrag van de winkel
* De gegevens die zijn opgenomen in gegevensoverdrachtsbewerkingen

Het bereik van kenmerkmetagegevens is `website/store/store view` .

[!DNL Live Search] API staat een cliënt toe om door om het even welk productattribuut te sorteren dat het [ storefront bezit ](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) `Use in Search` heeft die aan `Yes` in Adobe Commerce Admin wordt geplaatst. Indien ingeschakeld, kunnen `Search Weight` en `Visible in Advanced Search` worden ingesteld voor het kenmerk.

[!DNL Live Search] indexeert geen verwijderde producten of producten die zijn ingesteld op `Not Visible Individually` .

>[!NOTE]
>
> De klanten van Commerce met [!DNL Live Search] kunnen uit snellere prijsveranderingen en synchronisatietijd op hun websites met [ SaaS prijsindexer ](../price-index/price-indexing.md) voordeel halen.

## Indexeringsleiding

De client roept de zoekservice van de storefront aan om (filterbare, sorteerbare) indexmetagegevens op te halen. Slechts doorzoekbare productattributen met het *Gebruik in Gelaagd die bezit van de Navigatie* aan `Filterable (with results)` wordt geplaatst en *Gebruik voor het Sorteren in het Lijst van het Product* aan `Yes` wordt geplaatst kan door de onderzoeksdienst worden geroepen.
Om een dynamische vraag te construeren, moet de onderzoeksdienst weten welke attributen doorzoekbaar en hun [ gewicht ](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-results.html#weighted-search) zijn. [!DNL Live Search] geeft Adobe Commerce-zoekdikten (1-10, waarbij 10 de hoogste prioriteit heeft). De lijst met gegevens die met de catalogusservice worden gesynchroniseerd en gedeeld, vindt u in het schema, dat wordt gedefinieerd in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

![[!DNL Live Search] het indexeren diagram van het cliëntonderzoek ](assets/indexing-pipeline.svg)

1. Controleer de handelaar op [!DNL Live Search] machtiging.
1. Winkelweergaven ophalen met wijzigingen in kenmerkmetagegevens.
1. Kenmerken voor indexering opslaan.
1. Zoekindex opnieuw indexeren.

### Volledige index

Wanneer [!DNL Live Search] tijdens het instappen wordt gevormd en gesynchroniseerd, kan het tot 60 minuten duren om de aanvankelijke index te bouwen. De index van grote catalogi kan langer duren. Het proces begint nadat `cron` de feed heeft verzonden en de bewerking heeft voltooid.

De volgende gebeurtenissen activeren een volledige synchronisatie en de opbouw van de index:

* Onboarding [ synchronisatie van catalogusgegevens ](install.md#synchronize-catalog-data)
* Wijzigingen in metagegevens voor kenmerken

Als u bijvoorbeeld de eigenschap `Use in Search` van het kenmerk `color` wijzigt van `No` in `Yes` , worden de metagegevens van het kenmerk gewijzigd in `searchable=true` en wordt een volledige synchronisatie en herindex geactiveerd. De volgende kenmerkmetagegevens activeren een volledige synchronisatie en worden opnieuw geordend wanneer ze worden gewijzigd:

* `filterableInSearch`
* `searchable`
* `sortable`
* `visibleInSearch`

### Streaming productupdates

Nadat de aanvankelijke index tijdens [ onboarding ](install.md#synchronize-catalog-data) wordt gebouwd, worden de volgende stijgende productupdates onophoudelijk gesynchroniseerd en opnieuw bepaald:

* Nieuwe producten toegevoegd aan de catalogus
* Wijzigingen in productkenmerkwaarden

Het toevoegen van een nieuwe staalwaarde aan het kenmerk `color` wordt bijvoorbeeld verwerkt als een streaming productupdate.
Workflow voor gestreamde updates:

1. Bijgewerkte producten worden gesynchroniseerd van de Adobe Commerce-instantie naar de catalogusservice.
1. De indexerende dienst zoekt onophoudelijk productupdates van de catalogusdienst. Bijgewerkte producten worden geïndexeerd wanneer ze in de catalogusservice worden geleverd.
1. Het kan tot 15 minuten duren voordat een productupdate beschikbaar wordt in [!DNL Live Search].

## Clientzoekopdracht

[!DNL Live Search] API staat een cliënt toe om door om het even welk sorteerbaar productattribuut te sorteren door het [ storefront bezit ](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) te plaatsen, *Gebruikt voor het sorteren in productlijsten* aan `Yes`. Afhankelijk van het thema, veroorzaakt dit het plaatsen de attributen om als optie in de [ Soort door ](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/navigation/navigation.html) pagineringscontrole op cataloguspagina&#39;s worden omvat. Tot 200 productattributen kunnen door [!DNL Live Search] worden geïndexeerd, met [ storefront eigenschappen ](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) die doorzoekbaar en filterbaar zijn.
De indexmeta-gegevens worden opgeslagen in de indexerende pijpleiding en door de onderzoeksdienst toegankelijk.

![[!DNL Live Search] API-diagram voor indexmetagegevens ](assets/index-metadata-api.svg)

### Workflow voor sorteerbare kenmerken

1. Client roept de Dienst van het Onderzoek.
1. Zoekservice roept Search Admin Service aan.
1. De Vraag van de Dienst van het onderzoek het Indexeren Pijpleiding.

## Geïndexeerd voor alle producten

De volgorde van de velden in deze lijst geeft de typische volgorde van kolommen in geëxporteerde productgegevens weer.

* `environment_id`
* `website_code`
* `store_code`
* `store_view_code`
* `product_id`
* `sku`
* `name`
* `type`
* `displayable`
* `deleted`
* `url`
* `currency`
* `meta_description`
* `meta_keyword`
* `meta_title`
* `description`
* `short_description`
* `weight`
* `image`
* `small_image`
* `thumbnail_image`
* `prices`
* `in_stock`
* `low_stock`

Het volgende gebied wordt geïndexeerd voor alle configureerbare producten:

* `childrenSkus`
