---
title: "[!DNL Live Search] Indexeren"
description: "Meer informatie [!DNL Live Search] indexes product attribute properties."
exl-id: 04441e58-ffac-4335-aa26-893988a89720
source-git-commit: 7eece9b341a27637d7ac00216f18b7fad7c50740
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Indexeren

Eigenschappen van productkenmerken (metagegevens) bepalen:

* Hoe een attribuut in de catalogus kan worden gebruikt
* De vormgeving en het gedrag van de winkel
* De gegevens die zijn opgenomen in gegevensoverdrachtsbewerkingen

Het bereik van kenmerkmetagegevens is `website/store/store view`.

De [!DNL Live Search] API staat een cliënt toe om op om het even welk productattribuut te sorteren dat heeft [storefront, eigenschap](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) `Use in Search` instellen op `Yes` in Adobe Commerce Admin. Indien ingeschakeld, `Search Weight` en `Visible in Advanced Search` kan worden ingesteld voor het kenmerk.

[!DNL Live Search] geen verwijderde producten indexeert of producten die zijn ingesteld op `Not Visible Individually`.

>[!NOTE]
>
> Koophandel met afnemers [!DNL Live Search] kan profiteren van snellere prijswijzigingen en synchronisatietijd op hun websites met de [SaaS-prijsindexer](../price-index/index.md).

## Indexeringsleiding

De client roept de zoekservice van de storefront aan om (filterbare, sorteerbare) indexmetagegevens op te halen. Alleen doorzoekbare productkenmerken met *Gebruiken in gelaagde navigatie* eigenschap ingesteld op `Filterable (with results)` en *Gebruiken voor sorteren in productaanbieding* instellen op `Yes` kan door de onderzoeksdienst worden geroepen.
Om een dynamische vraag te construeren, moet de onderzoeksdienst weten welke attributen doorzoekbaar en hun gewicht zijn. [!DNL Live Search] geeft Adobe Commerce-zoekgewichten weer (1-10, waarbij 10 de hoogste prioriteit heeft). De lijst met gegevens die met de catalogusservice worden gesynchroniseerd en gedeeld, vindt u in het schema, dat wordt gedefinieerd in:

`vendor/magento/module-catalog-data-exporter/etc/et_schema.xml`

![[!DNL Live Search] indexeren, clientzoekdiagram](assets/indexing-pipeline.svg)

1. Handelaar controleren op [!DNL Live Search] machtiging.
1. Winkelweergaven ophalen met wijzigingen in kenmerkmetagegevens.
1. Kenmerken voor indexering opslaan.
1. Zoekindex opnieuw indexeren.

### Volledige index

Wanneer [!DNL Live Search] is geconfigureerd en gesynchroniseerd tijdens het instappen, kan het tot 30 minuten duren om de eerste index te genereren. De index van grote catalogi kan langer duren. Het proces begint na `cron` verzendt het diervoeder en eindigt het lopen.

De volgende gebeurtenissen activeren een volledige synchronisatie en de opbouw van de index:

* Onboarding [catalogusgegevenssync](install.md#synchronize-catalog-data)
* Wijzigingen in metagegevens voor kenmerken

Als u bijvoorbeeld het dialoogvenster `Use in Search` eigendom van de `color` kenmerk van `No` tot `Yes` wijzigt de metagegevens van het kenmerk in `searchable=true`en wordt een volledige synchronisatie en herindex geactiveerd. De volgende kenmerkmetagegevens activeren een volledige synchronisatie en worden opnieuw geordend wanneer ze worden gewijzigd:

* `filterableInSearch`
* `searchable`
* `sortable`
* `visibleInSearch`

### Streaming productupdates

Nadat de eerste index is samengesteld tijdens [onboarding](install.md#synchronize-catalog-data), worden de volgende incrementele productupdates voortdurend gesynchroniseerd en opnieuw geïndexeerd:

* Nieuwe producten toegevoegd aan de catalogus
* Wijzigingen in productkenmerkwaarden

U kunt bijvoorbeeld een nieuwe staalwaarde toevoegen aan de opdracht `color` -kenmerk wordt afgehandeld als een streaming product-update.
Workflow voor gestreamde updates:

1. Bijgewerkte producten worden gesynchroniseerd van de Adobe Commerce-instantie naar de catalogusservice.
1. De indexerende dienst zoekt onophoudelijk productupdates van de catalogusdienst. Bijgewerkte producten worden geïndexeerd wanneer ze in de catalogusservice worden geleverd.
1. Het kan tot 15 minuten duren voordat een productupdate beschikbaar wordt in [!DNL Live Search].

## Clientzoekopdracht

De [!DNL Live Search] Met API kan een client op elk sorteerbaar productkenmerk sorteren door het instellen van de [storefront, eigenschap](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html), *Wordt gebruikt voor sorteren in productaanbiedingen* tot `Yes`. Afhankelijk van het thema zorgt deze instelling ervoor dat het kenmerk als optie wordt opgenomen in het dialoogvenster [Sorteren op](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/navigation/navigation.html) Pagineringsbesturingselement op cataloguspagina&#39;s. Maximaal 200 productkenmerken kunnen worden geïndexeerd door [!DNL Live Search], met [storefront, eigenschappen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) die doorzoekbaar en filterbaar zijn.
De indexmeta-gegevens worden opgeslagen in de indexerende pijpleiding en door de onderzoeksdienst toegankelijk.

![[!DNL Live Search] API-diagram voor indexmetagegevens](assets/index-metadata-api.svg)

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
