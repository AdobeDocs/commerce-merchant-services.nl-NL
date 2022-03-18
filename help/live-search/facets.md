---
title: Facetten
description: In facetten van Live zoeken worden meerdere afmetingen van kenmerkwaarden gebruikt als zoekcriteria.
exl-id: 63c0b255-6be9-41ad-b4bf-13bb7ff098fd
source-git-commit: 19f0c987ab6b43b6fac1cad266b5fd47a7168e73
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---

# Facetten

Faceting is een methode voor het filteren van hoge prestaties waarbij meerdere dimensies van kenmerkwaarden worden gebruikt als zoekcriteria. Gefactureerde zoekopdracht is vergelijkbaar, maar aanzienlijk &quot;slimmer&quot; dan de standaard [gelaagde navigatie](https://docs.magento.com/user-guide/catalog/navigation-layered.html). De lijst met beschikbare filters wordt bepaald door de [filterbare kenmerken](https://docs.magento.com/user-guide/catalog/navigation-layered-filterable-attributes.html) van producten die in de zoekresultaten worden geretourneerd. Er kunnen maximaal 100 facetten worden geconfigureerd met [!DNL Live Search].

![Gefilterde zoekresultaten](assets/storefront-search-results-run.png)

## Faciliteitseisen

De categorie- en productkenmerkvereisten voor facetten zijn vergelijkbaar met de filterbare kenmerken die worden gebruikt voor gelaagde navigatie. De storefront-eigenschappen van elk kenmerk moeten zijn ingesteld op `filterable (with results)`.

| Instelling | Beschrijving |
|--- |--- |
| [Weergave-instellingen voor categorie](https://docs.magento.com/user-guide/catalog/categories-display-settings.html) | Anker - `Yes` |
| [Eigenschappen van kenmerk](https://docs.magento.com/user-guide/stores/attribute-product-create.html) | [Invoertype catalogus](https://docs.magento.com/user-guide/stores/attributes-input-types.html) - `Yes/No`, `Dropdown`, `Multiple Select`, `Price` |
| Eigenschappen van kenmerkarchief | Gebruiken in gelaagde navigatie - `Filterable (with results)` |

## Standaardeigenschappen van niet-systeemkenmerken

In de volgende tabel worden de standaardzoekeigenschappen en filterbare eigenschappen van niet-systeemkenmerken weergegeven, inclusief de eigenschappen die specifiek zijn voor de Luminantiemonsteringsgegevens. De instelling *Gebruiken in Zoeken* eigenschap attribute to `Yes` maakt het kenmerk doorzoekbaar in beide [!DNL Live Search] en native Adobe Commerce.

| Kenmerkcode | Doorzoekbaar | Gebruiken in gelaagde navigatie |
|--- |--- |--- |
| activiteit | Ja | Filterbaar (met resultaten) |
| attributes_brand | Ja | Nee |
| merk | Ja | Nee |
| klimaat | Ja | Filterbaar (met resultaten) |
| kraag | Ja | Filterbaar (met resultaten) |
| kleur | Ja | Filterbaar (met resultaten) |
| kosten | Ja | Nee |
| eco_collection | Ja | Filterbaar (met resultaten) |
| sekse | Ja | Filterbaar (met resultaten) |
| fabrikant | Ja | Filterbaar (met resultaten) |
| materiaal | Ja | Filterbaar (met resultaten) |
| doel | Ja | Filterbaar (met resultaten) |
| riem_tassen | Ja | Filterbaar (met resultaten) |
| style_general | Ja | Filterbaar (met resultaten) |

## Standaardsysteemkenmerkeigenschappen

In de volgende tabel worden de standaardzoekeigenschappen en filterbare eigenschappen van systeemkenmerken weergegeven.

| Kenmerkcode | Doorzoekbaar | Gebruiken in gelaagde navigatie |
|--- |--- |--- |
| allow_open_amount | Ja | Filterbaar (met resultaten) |
| beschrijving | Ja | Nee |
| name | Ja | Nee |
| prijs | Ja | Filterbaar (met resultaten) |
| short_description | Ja | Nee |
| sku | Ja | Nee |
| status | Ja | Nee |
| tax_class_id | Ja | Nee |
| url_key | Ja | Nee |
| gewicht | Ja | Nee |
