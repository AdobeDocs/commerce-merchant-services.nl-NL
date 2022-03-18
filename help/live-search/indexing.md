---
title: Indexering van Live zoeken
description: Leer hoe Live zoeken de eigenschappen van productkenmerken indexeert
exl-id: 04441e58-ffac-4335-aa26-893988a89720
source-git-commit: 8cc10feccda91fc1d9ead35f9b2b1e8ea19d4c95
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---

# Indexeren

Eigenschappen van productkenmerken (metagegevens) bepalen hoe een kenmerk in de catalogus kan worden gebruikt, hoe dit kenmerk er uitziet en hoe het in de winkel functioneert, en welke gegevens in gegevensoverdrachtsbewerkingen worden opgenomen. Het bereik van kenmerkmetagegevens is `website/store/store view`.

De [!DNL Live Search] API staat een cliënt toe om op om het even welk productattribuut te sorteren dat heeft [storefront, eigenschap](https://docs.magento.com/user-guide/stores/attributes-product.html) `Use in Search` instellen op `Yes` in Adobe Commerce Admin.

>[!NOTE]
>
>[!DNL Live Search] geen verwijderde producten indexeert of producten die zijn ingesteld op `Not Visible Individually`.

## Indexeringspijplijn

De client roept de zoekservice van de storefront aan om (filterbare, sorteerbare) indexmetagegevens op te halen. Alleen doorzoekbare productkenmerken met de *Gebruiken in gelaagde navigatie* eigenschap ingesteld op `Filterable (with results)` en *Gebruiken voor sorteren in productaanbieding* instellen op `Yes` kan door de onderzoeksdienst worden geroepen.
Om een dynamische vraag te construeren, moet de onderzoeksdienst weten welke attributen doorzoekbaar en hun gewicht zijn. [!DNL Live Search] geeft Adobe Commerce-zoekgewichten weer (1-10, waarbij 10 de hoogste prioriteit heeft). De lijst met gegevens die met de catalogusservice worden gesynchroniseerd en gedeeld, vindt u in het schema, dat wordt gedefinieerd in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

![[!DNL Live Search] indexeren, clientzoekdiagram](assets/indexing-pipeline.svg)

1. Handelaar controleren op [!DNL Live Search] machtiging.
1. Winkelweergaven ophalen met wijzigingen in kenmerkmetagegevens.
1. Kenmerken voor indexering opslaan.
1. Zoekindex opnieuw indexeren.

### Volledige index

Wanneer [!DNL Live Search] is geconfigureerd en gesynchroniseerd tijdens het instappen, kan het maximaal acht uur duren voordat de eerste index is gegenereerd. Het proces begint na `cron` verzendt het diervoeder en eindigt het lopen.

De volgende gebeurtenissen activeren een volledige synchronisatie en de opbouw van de index:

* Onboarding [catalogusgegevenssync](install.md#synchronize-catalog-data)
* Wijzigingen in metagegevens voor kenmerken

Als u bijvoorbeeld het dialoogvenster `Use in Search` eigendom van de `color` kenmerk van `No` tot `Yes` wijzigt de metagegevens van het kenmerk in `searchable=true`en wordt een volledige synchronisatie en herindex geactiveerd. De volgende kenmerkmetagegevens activeren een volledige synchronisatie en worden opnieuw geordend wanneer ze worden gewijzigd:

* `filterableInSearch`
* `searchable`
* `sortable`
* `visibleInSearch`

### Streaming van productupdates

Nadat de eerste index tijdens [onboarding](install.md#synchronize-catalog-data), worden de volgende incrementele productupdates voortdurend gesynchroniseerd en opnieuw geïndexeerd:

* Nieuw(e) product(en) toegevoegd aan catalogus
* Wijzigingen in productkenmerkwaarden

U kunt bijvoorbeeld een nieuwe staalwaarde toevoegen aan de opdracht `color` -kenmerk wordt afgehandeld als een streaming product-update.
Workflow voor gestreamde updates:

1. Bijgewerkte producten worden gesynchroniseerd van de Adobe Commerce-instantie naar de catalogusservice.
1. De indexerende dienst zoekt onophoudelijk productupdates van de catalogusdienst. Bijgewerkte producten worden geïndexeerd wanneer ze in de catalogusservice worden geleverd.
1. Het kan 15 minuten duren voordat een productupdate beschikbaar is in [!DNL Live Search].

## Clientzoekopdracht

De [!DNL Live Search] Met API kan een client op elk sorteerbaar productkenmerk sorteren door het instellen van de [storefront, eigenschap](https://docs.magento.com/user-guide/catalog/product-attributes.html), *Wordt gebruikt voor sorteren in productaanbiedingen* tot `Yes`. Afhankelijk van het thema zorgt deze instelling ervoor dat het kenmerk als optie wordt opgenomen in het dialoogvenster [Sorteren op](https://docs.magento.com/user-guide/catalog/navigation.html) Pagineringsbesturingselement op cataloguspagina&#39;s. Tot 300 productkenmerken kunnen worden geïndexeerd door [!DNL Live Search], met [storefront, eigenschappen](https://docs.magento.com/user-guide/stores/attributes-product.html) die doorzoekbaar en filterbaar zijn.
De indexmeta-gegevens worden opgeslagen in de indexerende pijpleiding en door de onderzoeksdienst toegankelijk.

![[!DNL Live Search] API-diagram voor indexmetagegevens](assets/index-metadata-api.svg)

### Workflow voor sorteerbare kenmerken

1. Client roept de Dienst van het Onderzoek.
1. De Dienst van het onderzoek roept de Dienst van Admin van het Onderzoek.
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
