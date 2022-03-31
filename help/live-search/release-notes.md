---
title: Opmerkingen bij de release Live zoeken
description: De meest recente release-informatie voor Live Search vanuit Adobe Commerce.
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: c70d08b90d7584559fd69cdeece0220015ae8523
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# [!DNL Live Search] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Live Search] en omvatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) - Bekende problemen

## [!DNL Live Search] 2,0

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - Het aantal beschikbare regels in de [storefront popover](quick-tour.md) kan van worden gevormd *Beheer*.
* ![Nieuw](../assets/new.svg) - Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibiliteit voor Live zoeken.
* ![Nieuw](../assets/new.svg) - Het installatieproces van Live zoeken wordt bijgewerkt met geavanceerde proceswijzigingen.
* ![Repareren](../assets/fix.svg) - [Geavanceerd zoeken](https://docs.magento.com/user-guide/catalog/search-advanced.html) koppeling verwijderd uit de voettekst van de winkel.
* ![Bug](../assets/bug.svg) - De volgende productkenmerken worden niet ondersteund door [Magento GraphQL API](https://devdocs.magento.com/guides/v2.4/graphql) bij gebruik in verband met de bètaversie van PWA: `description`, `name`, `short_description`
* ![Bug](../assets/bug.svg) - De bètaversie van PWA for Live Search biedt geen ondersteuning voor [gebeurtenisafhandeling](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).

## [!DNL Live Search] 1.3.1.

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Repareren](../assets/fix.svg) - [Aangepast prijskenmerk](https://docs.magento.com/user-guide/stores/attributes-input-types.html) keert niet meer een fout terug wanneer gevormd als a [facet]({% koppeling live-search/facets-add.md %}).
* ![Repareren](../assets/fix.svg) - Het probleem dat een fout veroorzaakte die er niet was, is opgelost. [valutasymbool](https://docs.magento.com/user-guide/stores/currency-symbols.html) (`data-currency-symbol`) is beschikbaar.
* ![Repareren](../assets/fix.svg) - [Storefront popover](storefront-popover.md) toont nu [Speciale prijs](https://docs.magento.com/user-guide/catalog/product-price-special.html) (minimumprijs) indien beschikbaar.

## [!DNL Live Search] 1.3.0.

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - [Prestaties](performance.md) het rapporteringsdashboard geeft inzicht in zoektermen die kopers gebruiken.
* ![Nieuw](../assets/new.svg) - [!DNL Live Search] [Storefront Events SDK](https://devdocs.magento.com/shared-services/storefront-events-sdk.html) verleent toegang tot een gemeenschappelijke gegevenslaag van gebeurtenis het publiceren en de abonnementendiensten, en metriek.
* ![Repareren](../assets/fix.svg) - de [Storefront Popover](https://devdocs.magento.com/live-search/storefront-popover.html) heeft een nieuwe `active` klasse voor de `.search-autocomplete` container die de zichtbaarheid bepaalt.
* ![Repareren](../assets/fix.svg) - In de winkel [Zoekvoorwaarden](https://docs.magento.com/user-guide/marketing/search-terms-popular.html) voettekstkoppeling wordt verwijderd en de bijbehorende cache wordt uitgeschakeld voor [!DNL Live Search] installaties.
* ![Bug](../assets/bug.svg) - Patch for Search adapter verwerkt dubbele producten.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] supports [uit één bron](https://docs.magento.com/user-guide/catalog/inventory-sources.html) (fysieke) inventarislocaties met meerdere (virtuele) [voorraden](https://docs.magento.com/user-guide/catalog/inventory-stock.html). Meerdere inventarisbronnen worden momenteel niet ondersteund.

## [!DNL Live Search] 1.2.0.

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - Storefront [popup](storefront-popover.md) Hiermee geeft u voorgestelde producten en miniatuurafbeeldingen van de zoekresultaten van het hoogste niveau weer als kopers vragen typen in het vak Zoeken.
* ![Nieuw](../assets/new.svg) - Handel *Beheer* sessie blijft geopend tijdens lange perioden van inactiviteit op het toetsenbord
* ![Nieuw](../assets/new.svg) - [!DNL Live Search] wordt automatisch ingeschakeld na het instappen
* ![Repareren](../assets/fix.svg) - Oorspronkelijke indexeertijd is minder dan een uur
* ![Repareren](../assets/fix.svg) - Incrementele productupdates bijna realtime (na installatie en installatie)
* ![Repareren](../assets/fix.svg) - Sorteerbare kolommen in Synonym-editor
* ![Repareren](../assets/fix.svg) - [!DNL Live Search] genereert niet langer een fout als zoekcriteria een lege sorteervolgordewaarde bevatten
* ![Repareren](../assets/fix.svg) - Het filteren van het bereik wordt niet langer onderbroken als kenmerkcodes tekenreeksen &quot;aan&quot; of &quot;from&quot; bevatten

## [!DNL Live Search] 1.1.0.

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Bug](../assets/bug.svg) - de [!DNL Live Search] de dienst steunt slechts de [basisvaluta](https://docs.magento.com/user-guide/stores/currency-configuration.html) van de Adobe Commerce-installatie.
* ![Bug](../assets/bug.svg) - Als u een facet toevoegt, wordt de feed Productkenmerken niet correct bijgewerkt als deze is ingesteld op `Update on Save`. Ga om dit probleem te voorkomen naar [Indexbeheer](https://docs.magento.com/user-guide/system/index-management.html) en stel Productkenmerken in op Feed `Update by Schedule`.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] synoniemen worden gedefinieerd per winkelweergave, maar worden momenteel opgeslagen per website en geïdentificeerd met een combinatie van `environmentId` + `storeViewCode`. Dit heeft tot gevolg dat alle websites en winkelweergaven in de Adobe Commerce-installatie dezelfde synoniemenreeks delen. De meest recente reeks synoniemen voor de archiefmening krijgt belangrijkheid.
* ![Bug](../assets/bug.svg) - Als een synoniem term meerdere woorden bevat, wordt elk woord behandeld als een afzonderlijk synoniem. Als u bijvoorbeeld &#39;tijdstuk&#39; definieert als een synoniem van &#39;watch&#39;, worden zowel &#39;time&#39; als &#39;piece&#39; beschouwd als synoniemen van &#39;watch&#39;.

## Documentatie

Meer informatie:

* [Adobe Commerce Developer Documentation](https://devdocs.magento.com/)
* [Adobe Commerce-gebruikershandleiding](https://docs.magento.com/user-guide/)
* [[!DNL Live Search] op Marketplace](https://marketplace.magento.com/magento-live-search.html)
