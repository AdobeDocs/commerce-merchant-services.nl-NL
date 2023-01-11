---
title: "[!DNL Live Search] Opmerkingen bij de release"
description: "De meest recente releasegegevens voor [!DNL Live Search] uit Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# [!DNL Live Search] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Live Search] en omvatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) - Bekende problemen

## [!DNL Live Search] 2.0.5 {#205}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Repareren](../assets/fix.svg) - Live zoeken zou een fout veroorzaken als SDK-bronnen niet beschikbaar waren vanwege netwerkproblemen. Deze bug is nu opgelost.

Handelaars moeten de Live Search extensie versie >= 2.0.5 bevorderen om tot deze eigenschappen toegang te hebben.

U wordt aangeraden een upgrade uit te voeren en te testen voordat u naar de productie gaat. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

## [!DNL Live Search] 2.0.4 {#204}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - Live zoeken ondersteunt nu filteren met de instelling &#39;Producten uit voorraad weergeven&#39; in de beheerder. Als &#39;Display Out of Stock Products&#39; is ingesteld op false, `inStock = true` wordt toegevoegd aan het filter.
* ![Repareren](../assets/fix.svg) - Om de prestaties te verbeteren, is het blok Suggestions verwijderd uit het pop-upmenu Live zoeken. De gegevens worden nog overgegaan door GraphQL, voor het geval u de eigenschap wilt vervangen.
* ![Repareren](../assets/fix.svg) - `categories` en `categoryPath` vervangen `categoryIds` voor filteren van categorieën. Lees meer in de [productSearch](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) onderwerp.
* ![Repareren](../assets/fix.svg) - Eerder zou een gebruiker die aan een B2B-bedrijf gebonden is een onjuiste code van de Groep van de Klant ontvangen wanneer het doen van onderzoeken. Live zoeken retourneert nu de juiste waarde.
* ![Repareren](../assets/fix.svg) - Als u eerder zoekt naar een term die niet bestaat, retourneert Live zoeken een fout. Die bug is nu opgelost.

Handelaars moeten de Live Search extensie versie >= 2.0.4 upgraden om toegang te krijgen tot deze functies.

We raden gebruikers aan een upgrade uit te voeren en te testen voordat ze naar de productie gaan. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

## [!DNL Live Search] 2.0.3 {#203}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - Live zoeken ondersteunt nu B2B-functies door categorietoestemmingen, gedeelde catalogi en klantspecifieke prijzen te respecteren.

Handelaars moeten de Live Search extensie versie >= 2.0.3 upgraden om toegang te krijgen tot deze functies.

We raden gebruikers aan een upgrade uit te voeren en te testen voordat ze naar de productie gaan. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

## [!DNL Live Search] 2.0 {#20}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

Bestaande [!DNL Live Search] de installaties moeten worden geüpgraded tot [!DNL Live Search] 2.0.0 om voordeel te halen uit de volgende nieuwe eigenschappen, moeilijke situaties, en verbeteringen:

* ![Nieuw](../assets/new.svg) - [!DNL Live Search] ondersteunt nu PHP 8.1 voor installaties met Adobe Commerce 2.4.4.
* ![Nieuw](../assets/new.svg) - de `Magento_ElasticsearchCatalogPermissionsGraphQl` wordt toegevoegd aan de lijst met modules die tijdens de installatie zijn uitgeschakeld.
* ![Nieuw](../assets/new.svg) - Het aantal beschikbare regels in de [[!DNL storefront popover]](quick-tour.md) kan van worden gevormd *Beheer*.
* ![Nieuw](../assets/new.svg) - Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibiliteit voor [!DNL Live Search].
* ![Nieuw](../assets/new.svg) - de [!DNL Live Search] Het installatieproces wordt bijgewerkt met geavanceerde proceswijzigingen.
* ![Repareren](../assets/fix.svg) - [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) koppeling verwijderd uit de voettekst van de winkel.
* ![Bug](../assets/bug.svg) - De volgende productkenmerken worden niet ondersteund door [Magento GraphQL API](https://developer.adobe.com/commerce/webapi/graphql/) bij gebruik in verband met de bètaversie van PWA: `description`, `name`, `short_description`
* ![Bug](../assets/bug.svg) - De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).

## [!DNL Live Search] 1.3.1 {#131}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Repareren](../assets/fix.svg) - [Aangepast prijskenmerk](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) keert niet meer een fout terug wanneer gevormd als a [facet]({% koppeling live-search/facets-add.md %}).
* ![Repareren](../assets/fix.svg) - Het probleem dat een fout veroorzaakte die er niet was, is opgelost. [valutasymbool](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html#step-5%3A-customize-currency-symbols-(optional)) (`data-currency-symbol`) is beschikbaar.
* ![Repareren](../assets/fix.svg) - [[!DNL Storefront popover]](storefront-popover.md) toont nu [Speciale prijs](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-special.html) (minimumprijs) indien beschikbaar.

## [!DNL Live Search] 1.3.0 {#130}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - [Prestaties](performance.md) het rapporteringsdashboard geeft inzicht in zoektermen die kopers gebruiken.
* ![Nieuw](../assets/new.svg) - [!DNL Live Search] [Storefront Events SDK](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) verleent toegang tot een gemeenschappelijke gegevenslaag van gebeurtenis het publiceren en de abonnementendiensten, en metriek.
* ![Repareren](../assets/fix.svg) - de [[!DNL Storefront popover]](storefront-popover.md) heeft een nieuwe `active` klasse voor de `.search-autocomplete` container die de zichtbaarheid bepaalt.
* ![Repareren](../assets/fix.svg) - In de winkel [Zoekvoorwaarden](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html#popular-search-terms) voettekstkoppeling wordt verwijderd en de bijbehorende cache wordt uitgeschakeld voor [!DNL Live Search] installaties.
* ![Bug](../assets/bug.svg) - Patch for Search adapter verwerkt dubbele producten.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] supports [uit één bron](https://experienceleague.adobe.com/docs/commerce-admin/inventory/sources/sources-manage.html) (fysieke) inventarislocaties met meerdere (virtuele) [voorraden](https://experienceleague.adobe.com/docs/commerce-admin/inventory/stocks/stocks-manage.html). Meerdere inventarisbronnen worden momenteel niet ondersteund.

## [!DNL Live Search] 1.2.0 {#120}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Nieuw](../assets/new.svg) - [[!DNL Storefront popover]](storefront-popover.md) Hiermee geeft u voorgestelde producten en miniatuurafbeeldingen van de zoekresultaten van het hoogste niveau weer als kopers vragen typen in het vak Zoeken.
* ![Nieuw](../assets/new.svg) - Handel *Beheer* sessie blijft geopend tijdens lange perioden van inactiviteit op het toetsenbord
* ![Nieuw](../assets/new.svg) - [!DNL Live Search] wordt automatisch ingeschakeld na het instappen
* ![Repareren](../assets/fix.svg) - Oorspronkelijke indexeertijd is minder dan een uur
* ![Repareren](../assets/fix.svg) - Incrementele productupdates bijna realtime (na installatie en installatie)
* ![Repareren](../assets/fix.svg) - Sorteerbare kolommen in Synonym-editor
* ![Repareren](../assets/fix.svg) - [!DNL Live Search] genereert niet langer een fout als zoekcriteria een lege sorteervolgordewaarde bevatten
* ![Repareren](../assets/fix.svg) - Het filteren van het bereik wordt niet langer onderbroken als kenmerkcodes tekenreeksen &quot;aan&quot; of &quot;from&quot; bevatten

## [!DNL Live Search] 1.1.0 {#110}

* Compatibel met Adobe Commerce (EE): 2,4 x
* Compatibel met Adobe Commerce for Cloud (ECE): 2,4 x
* Stabiliteit: Stabiel

* ![Bug](../assets/bug.svg) - de [!DNL Live Search] de dienst steunt slechts de [basisvaluta](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html) van de Adobe Commerce-installatie.
* ![Bug](../assets/bug.svg) - Als u een facet toevoegt, wordt de feed Productkenmerken niet correct bijgewerkt als deze is ingesteld op `Update on Save`. Ga om dit probleem te voorkomen naar [Indexbeheer](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html) en stel Productkenmerken in op Feed `Update by Schedule`.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] synoniemen worden gedefinieerd per winkelweergave, maar worden momenteel opgeslagen per website en geïdentificeerd met een combinatie van `environmentId` + `storeViewCode`. Dit heeft tot gevolg dat alle websites en winkelweergaven in de Adobe Commerce-installatie dezelfde synoniemenreeks delen. De meest recente reeks synoniemen voor de archiefmening krijgt belangrijkheid.
* ![Bug](../assets/bug.svg) - Als een synoniem term meerdere woorden bevat, wordt elk woord behandeld als een afzonderlijk synoniem. Als u bijvoorbeeld &#39;tijdstuk&#39; definieert als een synoniem van &#39;watch&#39;, worden zowel &#39;time&#39; als &#39;piece&#39; beschouwd als synoniemen van &#39;watch&#39;.

## Documentatie

Meer informatie:

* [Adobe Commerce Developer Documentation](https://developer.adobe.com/commerce/docs)
* [Adobe Commerce-gebruikershandleiding](https://experienceleague.adobe.com/docs/commerce.html)
* [[!DNL Live Search] op Marketplace](https://marketplace.magento.com/magento-live-search.html)
