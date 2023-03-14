---
title: '''[!DNL Live Search] Opmerkingen bij de release'
description: "De meest recente releasegegevens voor [!DNL Live Search] uit Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
source-git-commit: a589956b5594283d7ceb620abc76b2c352f8f524
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 0%

---

# [!DNL Live Search] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Live Search] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen

## [!DNL Live Search] 3.0.1 {#301}

_14 maart 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

### Nieuwe functies

* Productitemkaart in voorbeeld met regels
* [Widget pagina met productaanbiedingen](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-storefront/plp-styling.html)
* [Categoriefilteropties](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/#facets)
* Mogelijkheid toegevoegd om pengebeurtenissen te maken door slepen en neerzetten
* Nieuwe vastzetacties:
   * Vastzetten op steun - Knop Vastzetten om met één klik een vastpingebeurtenis te maken
   * Aan bovenkant vastzetten - Het product wordt op de eerste positie geplaatst
   * Aan onderzijde vastzetten - Hiermee plaatst u het product onder aan de resultaten
   * Een gebeurtenis met één klik vrijmaken
* [Intelligente classificatie voor regels](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-admin/rules/rules-add.html#ranking-type)

### Updates

* Regels configureren sorteert posities nu automatisch uniek
* Een bestaande gebeurtenis verwijderen werkt nu de voorvertoning bij
* Regels zonder gebeurtenissen kunnen worden opgeslagen
* Selector Type selecteren verwijderen
* Nieuwe bewerkingsstatus voor niet-opgeslagen regels toegevoegd

### Oplossingen

* Fout met vaste server als er een onvoltooide gebeurtenis plaatsvindt tijdens opslaan
* Correcte verwijdering van specifieke gebeurtenis bij meerdere gebeurtenissen opgelost
* Gebeurtenis met bestaande regel is niet bijgewerkt wanneer een nieuwe gebeurtenis is toegevoegd. Dit probleem is nu opgelost.
* Correctie voor tweede klik op Bewerken uit details. [!DNL Live Search] pagina die opnieuw moet worden geladen
* Synoniemen: Probleem verholpen waarbij een gebruiker buiten de invoer klikte en de focus niet naar het veld kon terugzetten.
* Andere kleine insectenmoeilijke situaties en prestatiesupdates


* ![Bug](../assets/bug.svg) - Rangschikken op &quot;Aanbevolen voor u&quot; wordt alleen ondersteund in de widgets Live zoeken. Deze functie wordt niet ondersteund met de standaardzoekfunctionaliteit LUMA en PWA.
* ![Bug](../assets/bug.svg) - Aangepaste facetten van prijskenmerken worden niet correct weergegeven in LUMA, maar de API filtert er op.

Handelaren moeten de [!DNL Live Search] extensie >= 3.0.1 gebruiken om deze functies te openen.

U wordt aangeraden een upgrade uit te voeren en te testen voordat u naar de productie gaat. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

## Vorige versies

+++2.0.4 en eerder

### [!DNL Live Search] 2.0.4 {#204}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Live zoeken ondersteunt nu filteren met de instelling &#39;Producten uit voorraad weergeven&#39; in de beheerder. Als &#39;Display Out of Stock Products&#39; is ingesteld op false, `inStock = true` wordt toegevoegd aan het filter.
![Repareren](../assets/fix.svg) Om de prestaties te verbeteren, is het blok &#39;Suggestions&#39; verwijderd uit het pop-upmenu Live zoeken. De gegevens worden nog steeds doorgegeven via GraphQL, voor het geval u de functie wilt vervangen.
![Repareren](../assets/fix.svg) `categories` en `categoryPath` vervangen `categoryIds` voor filteren van categorieën. Lees meer in de [productSearch](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) onderwerp.
![Repareren](../assets/fix.svg) Eerder, zou een gebruiker verbonden aan een bedrijf B2B een onjuiste Code van de Groep van de Klant ontvangen wanneer het doen van onderzoeken. Live zoeken retourneert nu de juiste waarde.
![Repareren](../assets/fix.svg) Als u een term zoekt die niet bestaat, wordt een fout geretourneerd door Live zoeken. Die bug is nu opgelost.

Handelaren moeten de [!DNL Live Search] extensie >= 2.0.4 om toegang te krijgen tot deze functies.

De gebruikers worden geadviseerd om te bevorderen en te testen alvorens aan productie te duwen. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### [!DNL Live Search] 2.0.3 {#203}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Live zoeken ondersteunt nu B2B-functies door categorietoestemmingen, gedeelde catalogi en klantspecifieke prijzen te respecteren.

Handelaren moeten de [!DNL Live Search] extensie >= 2.0.3 gebruiken om deze functies te openen.

De gebruikers worden geadviseerd om te bevorderen en te testen alvorens aan productie te duwen. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### [!DNL Live Search] 2.0 {#20}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Bestaande [!DNL Live Search] de installaties moeten worden geüpgraded tot [!DNL Live Search] 2.0.0 om voordeel te halen uit de volgende nieuwe eigenschappen, moeilijke situaties, en verbeteringen:

![Nieuw](../assets/new.svg) [!DNL Live Search] ondersteunt nu PHP 8.1 voor installaties met Adobe Commerce 2.4.4.
![Nieuw](../assets/new.svg) De `Magento_ElasticsearchCatalogPermissionsGraphQl` wordt toegevoegd aan de lijst met modules die tijdens de installatie zijn uitgeschakeld.
![Nieuw](../assets/new.svg) Het aantal beschikbare regels in de [[!DNL storefront popover]](quick-tour.md) kan van worden gevormd *Beheer*.
![Nieuw](../assets/new.svg) Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibiliteit voor [!DNL Live Search].
![Nieuw](../assets/new.svg) De [!DNL Live Search] Het installatieproces wordt bijgewerkt met geavanceerde proceswijzigingen.
![Repareren](../assets/fix.svg) [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) koppeling verwijderd uit de voettekst van de winkel.
![Bug](../assets/bug.svg) De volgende productkenmerken worden niet ondersteund door [Commerce GraphQL API](https://developer.adobe.com/commerce/webapi/graphql/) bij gebruik in verband met de bètaversie van PWA: `description`, `name`, `short_description`
![Bug](../assets/bug.svg) De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).

### [!DNL Live Search] 1.3.1 {#131}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Repareren](../assets/fix.svg) [Aangepast prijskenmerk](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) keert niet meer een fout terug wanneer gevormd als a [facet]({% koppeling live-search/facets-add.md %}).
![Repareren](../assets/fix.svg) Er heeft zich een fout voorgedaan als er geen fout was opgetreden. Dit probleem is nu opgelost. [valutasymbool](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html#step-5%3A-customize-currency-symbols-(optional)) (`data-currency-symbol`) is beschikbaar.
![Repareren](../assets/fix.svg) [[!DNL Storefront popover]](storefront-popover.md) toont nu [Speciale prijs](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-special.html) (minimumprijs) indien beschikbaar.

### [!DNL Live Search] 1.3.0 {#130}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) [Prestaties](performance.md) het rapporteringsdashboard geeft inzicht in zoektermen die kopers gebruiken.
![Nieuw](../assets/new.svg) [!DNL Live Search] [Storefront Events SDK](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) verleent toegang tot een gemeenschappelijke gegevenslaag van gebeurtenis het publiceren en de abonnementendiensten, en metriek.
![Repareren](../assets/fix.svg) De [[!DNL Storefront popover]](storefront-popover.md) heeft een nieuwe `active` klasse voor de `.search-autocomplete` container die de zichtbaarheid bepaalt.
![Repareren](../assets/fix.svg) In de winkel [Zoekvoorwaarden](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html#popular-search-terms) voettekstkoppeling wordt verwijderd en de bijbehorende cache wordt uitgeschakeld voor [!DNL Live Search] installaties.
![Bug](../assets/bug.svg) Patch for Search adapter verwerkt dubbele producten.
![Bug](../assets/bug.svg) [!DNL Live Search] supports [uit één bron](https://experienceleague.adobe.com/docs/commerce-admin/inventory/sources/sources-manage.html) (fysieke) inventarislocaties met meerdere (virtuele) [voorraden](https://experienceleague.adobe.com/docs/commerce-admin/inventory/stocks/stocks-manage.html). Meerdere inventarisbronnen worden nu niet ondersteund.

### [!DNL Live Search] 1.2.0 {#120}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) [[!DNL Storefront popover]](storefront-popover.md) Hiermee geeft u voorgestelde producten en miniatuurafbeeldingen van de zoekresultaten van het hoogste niveau weer als kopers vragen typen in het vak Zoeken.
![Nieuw](../assets/new.svg) Handel *Beheer* sessie blijft geopend tijdens lange perioden van inactiviteit op het toetsenbord
![Nieuw](../assets/new.svg) [!DNL Live Search] wordt automatisch ingeschakeld na het instappen
![Repareren](../assets/fix.svg) De aanvankelijke indexeertijd is minder dan een uur
![Repareren](../assets/fix.svg) Incrementele productupdates bijna realtime (na installatie en installatie)
![Repareren](../assets/fix.svg) Sorteerbare kolommen in Synonym-editor
![Repareren](../assets/fix.svg) [!DNL Live Search] genereert niet langer een fout als zoekcriteria een lege sorteervolgordewaarde bevatten
![Repareren](../assets/fix.svg) Het filtreren van de waaier breekt niet meer als de attributencodes koorden &quot;aan&quot;of &quot;van&quot;bevatten

### [!DNL Live Search] 1.1.0 {#110}

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Bug](../assets/bug.svg) De [!DNL Live Search] de dienst steunt slechts de [basisvaluta](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html) van de Adobe Commerce-installatie.
![Bug](../assets/bug.svg) Wanneer u een facet toevoegt, wordt de feed Productkenmerken niet correct bijgewerkt wanneer deze is ingesteld op `Update on Save`. Ga om dit probleem te voorkomen naar [Indexbeheer](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html) en stel Productkenmerken in op Feed `Update by Schedule`.
![Bug](../assets/bug.svg) [!DNL Live Search] synoniemen worden gedefinieerd per winkelweergave, maar worden momenteel opgeslagen per website en geïdentificeerd met een combinatie van `environmentId` en `storeViewCode`. Dit heeft tot gevolg dat alle websites en winkelweergaven in de Adobe Commerce-installatie synoniemen delen. De meest recente reeks synoniemen voor de archiefmening krijgt belangrijkheid.
![Bug](../assets/bug.svg) Als een synoniem term meerdere woorden bevat, wordt elk woord behandeld als een afzonderlijk synoniem. Als u bijvoorbeeld &#39;tijdstuk&#39; definieert als een synoniem van &#39;watch&#39;, worden zowel &#39;time&#39; als &#39;piece&#39; beschouwd als synoniemen van &#39;watch&#39;.

+++

## Documentatie

Meer informatie:

* [Adobe Commerce Developer Documentation](https://developer.adobe.com/commerce/docs)
* [Adobe Commerce-gebruikershandleiding](https://experienceleague.adobe.com/docs/commerce.html)
* [[!DNL Live Search] op Marketplace](https://marketplace.magento.com/magento-live-search.html)
