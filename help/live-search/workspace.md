---
title: 'Live zoeken instellen'
description: De [!DNL Live Search] de werkruimte wordt gebruikt om onderzoeksprestaties te vormen, te beheren en te controleren.
exl-id: fb85974a-a5f9-4e6c-bd03-451e6457f2d2
source-git-commit: 099a4b9ce3ab71bc3c7ae181be242863a55d0ca9
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 0%

---

# Live zoeken instellen

In de werkruimte kunt u de prestaties van [!DNL Live Search]. Het menu boven biedt toegang tot de gereedschappen in elk functioneel gebied. De beschikbare functies weerspiegelen de huidige menuselectie.

![Werkruimte](assets/workspace.png)

## Bereik instellen

In eerste instantie [bereik](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) van alle [!DNL Live Search] instellingen zijn ingesteld op `Default Store View`. Als uw [!DNL Commerce] installatie bevat meerdere winkelweergaven, set **Toepassingsgebied** aan de [winkelweergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html) waar uw facetinstellingen van toepassing zijn.

## Menuopties

| Optie | Beschrijving |
|--- |--- |
| [Prestaties](performance.md) | Het dashboard biedt inzicht in de zoekprestaties van producten. |
| [Faceting](facets.md) | Krachtig filteren waarbij meerdere dimensies van kenmerkwaarden worden gebruikt om zoekcriteria te verfijnen. |
| [Synoniemen](synonyms.md) | Breid het bereik van de zoekopdracht uit tot woorden die kopers kunnen gebruiken om producten te zoeken die afwijken van de producten in uw catalogus. |
| [Merchandising zoeken](rules.md) | Vorm de onderzoekservaring met logische regels die geplande acties teweegbrengen. Verhoog, bury, speld, of verberg producten om onderzoeksresultaten te kalibreren om uw bedrijfsdoelstellingen te steunen. |
| [Categorieverhandeling](category-merch.md) | Pas regels en Intelligent Merchandising op het niveau van de Categorie toe. |
| [GraphQL](graphql.md) | Ontwikkelaars die zijn aangemeld bij de beheerder van uw winkel, kunnen query&#39;s samenstellen en testen met werkelijke catalogusgegevens. Ga voor meer informatie naar [GraphQL - Overzicht](https://developer.adobe.com/commerce/webapi/graphql/) in de [!DNL Live Search] ontwikkelaarsdocumentatie. |
| [Instellingen](settings.md) | Bepaal hoe prijsfacetwaarden worden gegroepeerd op prijsbereik in de winkel en stel de indextaal in. |

## Kenmerken instellen als doorzoekbaar

Als u gerichte resultaten wilt bereiken, kunt u de set [doorzoekbaar](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) (`searchable=true`) productkenmerken. Om relevantie te verzekeren, maak attributen doorzoekbaar slechts als zij inhoud bevatten die een duidelijke en beknopte betekenis heeft. Gebruik geen kenmerken die minder nauwkeurige, lange tekst bevatten, zoals `description`Deze optie is standaard ingeschakeld, maar hierdoor kan de precisie van zoekresultaten afnemen. Als iemand bijvoorbeeld zoekt naar &quot;korte broeken&quot; en er overhemden zijn met een beschrijving die de term &quot;korte mouwen&quot; bevat, worden de overhemden opgenomen in de zoekresultaten.

Voer de volgende stappen uit om te zorgen dat kenmerken doorzoekbaar zijn:

1. Ga in Beheer naar **Winkels** > *Kenmerk* > **Product**.
1. Selecteer het kenmerk dat u wilt doorzoeken, bijvoorbeeld `color`.
1. Selecteren **Eigenschappen van Storefront** en instellen **Gebruiken in Zoeken** tot `yes`.

   ![Werkruimte](assets/attribute-searchable.png)

[!DNL Live Search] eerbiedigt tevens de [gewicht](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-results.html#weighted-search) van een productkenmerk, zoals ingesteld in Adobe Commerce. Kenmerken met een hogere dikte worden hoger weergegeven in de zoekresultaten.

De volgende kenmerken kunnen altijd worden doorzocht:

* `sku`
* `name`
* `categories`

[Facetten](facets.md) zijn productkenmerken die worden gedefinieerd in [!DNL Live Search] filterbaar zijn. U kunt elk filterbaar kenmerk als facet instellen in [!DNL Live Search], maar er zijn [limieten](boundaries-limits.md) aan hoeveel facetten u naar in één keer kunt zoeken.

[Synoniemen](synonyms.md) Dit zijn termen die u kunt definiëren om gebruikers te helpen bij het vinden van het juiste product. Gebruikers die op zoek zijn naar een broek kunnen &#39;broek&#39; of &#39;slacks&#39; typen. U kunt synoniemen zodanig instellen dat deze zoektermen gebruikers naar de resultaten van de &#39;&#39;broek&#39;&#39; brengen.

## Commerce-configuratie-instellingen

In de volgende sectie worden de ondersteunde en niet-ondersteunde Commerce-configuratie-instellingen beschreven voor [!DNL Live Search].

### Ondersteunde configuratiewaarden

| Commerce-configuratie-instelling | Beschrijving | Ondersteund door Popover | Ondersteund door adapter |
|---|---|---|---|
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Alle producten per pagina toestaan | Indien ingesteld op `Yes`, inclusief de `ALL` in het besturingselement &#39;Tonen per pagina&#39;. | Ja. Maximaal 500 producten | Ja. Maximaal 500 producten |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Minimale lengte query | Het minimale aantal tekens dat is toegestaan in een cataloguszoekopdracht. | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op toegestane rasterwaarden | Hiermee bepaalt u het aantal producten dat wordt weergegeven in de rasterweergave. | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op standaardrasterwaarde | Hiermee bepaalt u het aantal producten dat standaard per pagina wordt weergegeven in de rasterweergave. | Ja. Maximaal 500 producten | Ja. Maximaal 500 producten |
| Winkels > Configuratie > Catalogus > Inventaris > Producten uit voorraad weergeven | Hiermee geeft u producten weer die uit voorraad zijn. | Ja met v2.0.4+ | Ja met v2.0.4+ |
| Stores > Configuration > Currency > Default Display Currency | De primaire valuta die wordt gebruikt om prijzen weer te geven. | Ja met 3.1.0+ | Ja met 3.1.0+ |
| Storingen > Configuratie > Algemeen > Valuta-instelling > Valuta-opties > Basisvaluta | De primaire valuta die wordt gebruikt voor alle online betalingstransacties. | Ja | Ja |

Prijzen in de aanbiedingspagina van het widgetproduct en in de pop-upmenu&#39;s worden met de geconfigureerde valutakoersen omgezet in de standaardweergavemunt.

### Niet-ondersteunde configuratiewaarden

| Commerce-configuratie-instelling | Beschrijving | Notities |
|---|---|---|
| Storingen > Configuratie > Catalogus > Storefront > Lijstmodus | Bepaalt de indeling van de lijst met zoekresultaten. | Rendering is correct, maar gebeurtenissen worden niet verzonden voor bepaalde paginainteracties |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Maximale lengte query | Het maximum aantal tekens dat is toegestaan in een cataloguszoekopdracht. | Niet geïmplementeerd; zoekservices accepteren maximaal 255 tekens |
| Configuration > Sales > Tax > Price Display Settings > Display Product Prices in Catalog | Bepaalt of de productprijzen die in de catalogus worden gepubliceerd belasting omvatten of uitsluiten, of twee versies van de prijs tonen; één met, en andere zonder belasting |  |
| Winkels > Configuratie > Catalogus > Storefront > Productaanbieding sorteren op | Hiermee bepaalt u de sorteervolgorde van de lijst met zoekresultaten. | Is niet van toepassing op [!DNL Live Search] [Widget pagina met productaanbiedingen](plp-styling.md) |

### Zoektermen

[!DNL Live Search] supports [heroriëntering van zoektermen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html) op implementaties waar Adobe Commerce het verpletteren behandelt, zoals op Luma en andere op php gebaseerde thema&#39;s.
