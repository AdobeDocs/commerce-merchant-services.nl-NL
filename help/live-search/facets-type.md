---
title: '"Typen factoren"'
description: '"[!DNL Live Search] De facetten zijn dynamisch, en verschijnen in de lijst van Filters wanneer relevant."'
exl-id: 49fb7609-64b3-4ae8-928d-54c99032d919
source-git-commit: bffbede99865e9085f60392e474065a454446370
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Typen facetten

Alles [!DNL Live Search] facetten zijn dynamisch en verschijnen in de *Filters* alleen indien relevant. De lijst met beschikbare facetten verandert afhankelijk van de geretourneerde producten. De volgende kenmerken beïnvloeden hun presentatie en gedrag:

* Vastgezette facetten - De meest gebruikte facetten kunnen aan de bovenkant van de lijst worden vastgezet. De resterende facetten worden vermeld in *Tekst sorteren* volgorde na de vastgezette facetten.
* Intelligente facetten - Productkenmerken die [Adobe Sensei](https://www.adobe.com/sensei.html) vindt het meest relevant voor een productreeks en vraag. De berekening houdt rekening met de attributenmeta-gegevens van de volledige catalogus en bepaalt bij vraagtijd de meest relevante facetten voor de vraag.
* Populaire facetten - Productkenmerken die het vaakst in onderzoeksresultaten aanwezig zijn.
* Prijsfactoren - Retourproducten per prijsklasse. U kunt het aantal selecties en het prijsinterval opgeven op het tabblad [*Instellingen*](settings.md) tab.

Tijdens het opvragen [!DNL Live Search] Hiermee genereert u de zoekresultaten in groepen van intelligente en populaire facetten.

![Facetten - Prijs](assets/storefront-search-results-run-price.png)

## Opties voor Storefront en headless

Facetten die worden gerenderd voor de [!DNL Commerce] storefront wordt verwerkt door de zoekadapter, die de resultaten in de winkel opvraagt en rendert. Alles [!DNL Commerce] storefront-facetten worden alfabetisch gesorteerd met opties voor één keuze, ongeacht het invoertype dat aan het overeenkomstige kenmerk is toegewezen. Facetten die beschikbaar zijn in de winkel, worden weergegeven volgens het huidige thema en weerspiegelen eventuele aanpassingen aan de presentatie van gelaagde navigatie.

Daarentegen [koploos](https://devdocs.magento.com/guides/v2.4/architecture/archi_perspectives/webapi-vision.html) implementaties worden verwerkt door de API en ondersteunen extra opties. Koploze facetten kunnen alfabetisch of op aantal worden gesorteerd en kunnen opties voor één of meerdere selecties hebben.

### Tekst selecteren

Voor implementaties zonder kop kunnen facetten worden gedefinieerd als `single select` of `multi-select` met logische operatoren die de geretourneerde productset bepalen. Bijvoorbeeld: `green AND blue` of `green OR blue`.

![Facetten - Type selecteren](assets/facets-select-type.png)

| Tekst selecteren | Beschrijving |
|--- |--- |
| Enkel selecteren | Een enkel-uitgezocht facet biedt veelvoudige opties, maar staat de verkoopster toe om slechts één waarde te kiezen. |
| Meerdere selecties (of) | (Alleen koptekst) Klanten kunnen meerdere opties kiezen en geretourneerde producten kunnen overeenkomen met elke geselecteerde waarde. Voorbeeld: `green OR blue` |
| Meerdere selecties (en) | (Alleen koptekst) Klanten kunnen meerdere opties kiezen en geretourneerde producten moeten overeenkomen met alle geselecteerde waarden. Voorbeeld: `green AND blue` |

### Facet-labels

Voor [!DNL Commerce] opslagplaatsen, wordt het facetetiket bepaald door [*Eigenschappen van kenmerk*](https://docs.magento.com/user-guide/stores/attribute-product-create.html). Voor winkels met meerdere weergaven kunt u aanvullende labels definiëren onder *Labels beheren*. Voor implementaties zonder kop worden labels bewerkt vanuit de [facetwerkruimte](faceting-workspace.md).

### Tekst sorteren

Alle facetten die voor de storefront worden weergegeven, worden alfabetisch gesorteerd. Voor implementaties zonder kop kunnen elementen alfabetisch of op aantal worden gesorteerd.

| Tekst sorteren | Beschrijving |
|--- |--- |
| Alfabetisch | In de winkel *Filters* lijst, worden de facetten alfabetisch gesorteerd. |
| Aantal | (Alleen koptekst) Bij implementaties zonder kop kunnen facetten ook worden gesorteerd op het aantal waarden per facet in de huidige set geretourneerde producten. |
