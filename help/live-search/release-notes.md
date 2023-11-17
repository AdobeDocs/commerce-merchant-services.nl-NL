---
title: "[!DNL Live Search] Aanvullende informatie"
description: "De meest recente releasegegevens voor [!DNL Live Search] uit Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
feature: Services, Search, Release Notes
source-git-commit: ff7a2549893eab63f552a2a866939adc90de4a78
workflow-type: tm+mt
source-wordcount: '1869'
ht-degree: 0%

---

# [!DNL Live Search] Aanvullende informatie

In deze releaseopmerkingen worden de meest recente versies van [!DNL Live Search].
Er wordt ondersteuning geboden voor de belangrijkste uitgebrachte versie. Opmerkingen bij de release voor oudere versies worden ter referentie verschaft.
Updates zijn:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen

## Gehoste service-updates

Deze nota&#39;s beschrijven updates die buiten een versioned versie of verbeteringen aan de ontvangen dienst werden gepubliceerd.

_27 oktober 2023_

![Nieuw](../assets/new.svg) De [!DNL Live Search] De PLP-widget ondersteunt nu kleurstalen.

_12 oktober 2023_

![Nieuw](../assets/new.svg) De beheerders van de handel kunnen nu de taal van de index voor specificeren [!DNL Live Search]. Zie [Instellingen](settings.md).
![Repareren](../assets/fix.svg) Het tabblad Zoekregels is hernoemd naar &#39;Zoeken in wijzigingen&#39;.

_13 juni 2023_

![Repareren](../assets/fix.svg) Probleem verholpen waarbij bepaalde tekens, zoals aanhalingstekens of apostroffen, klasseringsproblemen veroorzaakten. Deze problemen worden opgelost door opnieuw te indexeren.

_25 april 2023_

![Nieuw](../assets/new.svg) [!DNL Live Search] klanten kunnen nu profiteren van de nieuwe [SaaS-prijsindexer](../price-index/index.md).

## [!DNL Live Search] 4.0.0 {#400}

_13 nov. 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

### Nieuwe functies

![Nieuw](../assets/new.svg) [!DNL Live Search] ondersteunt nu kleurstalen in de PLP-widget.
![Nieuw](../assets/new.svg) [!DNL Live Search] geeft nu de categorienaam weer in plaats van de categorie-id.
![Nieuw](../assets/new.svg) [!DNL Live Search] ondersteunt nu doorhaalprijzen in de PLP-widget.
![Nieuw](../assets/new.svg) Introduceerde de knop &quot;Filters verbergen&quot; om het deelvenster Filters te verbergen.


### Updates

![Repareren](../assets/fix.svg) De [!DNL Live Search] PLP-widget is nu standaard ingeschakeld voor nieuwe installaties.
![Repareren](../assets/fix.svg) CSS-stijlen opnieuw geconfigureerd om widgetklassen beter te isoleren.
![Repareren](../assets/fix.svg) Kleine oplossingen voor problemen

Handelaren moeten de [!DNL Live Search] extensie >= 4.0.0 voor toegang tot deze functies.

Nadat u versie 3.1.1 of hoger hebt geïnstalleerd, schakelt u de nieuwe indexen in:

* Diervoeders productprijzen
* Websitegegevensinvoer
* Scopes klant groepeert gegevenstoevoer

Na bevordering, test de bijgewerkte configuratie in QA of het Opvoeren alvorens de veranderingen in productie te duwen.

## Vorige versies

+++3.1.1 en eerdere versies

## [!DNL Live Search] 3.1.1 {#311}

_15 sep. 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}



![Nieuw](../assets/new.svg) Het nieuwe tabblad Categorieomzetting is toegevoegd. Gebruikers kunnen nu intelligente waarderingen en handmatige waarderingen (speld, boost, bury, hide) per categorie toevoegen
![Nieuw](../assets/new.svg) Gebruikers kunnen één categorieregel toevoegen met een intelligente of handmatige classificatie
![Nieuw](../assets/new.svg) Gebruikers kunnen nu intelligente volgregels toevoegen aan subcategorieën
![Nieuw](../assets/new.svg) Gedetailleerde informatie wordt gegeven wanneer het schrappen van subcategorieën met intelligente rangschikking
![Nieuw](../assets/new.svg) De mogelijkheid toegevoegd om regels voor overgeërfde classificatiestrategieën te verwijderen
![Nieuw](../assets/new.svg) De mogelijkheid toegevoegd om regels voor één categorie te verwijderen
![Nieuw](../assets/new.svg) Gebruikers kunnen nu op categorienaam zoeken wanneer zij een regel toevoegen
![Nieuw](../assets/new.svg) In de weergave Categoriestructuur kunnen gebruikers nu zien welke categorie regels heeft toegepast.
![Nieuw](../assets/new.svg) In Voorvertoning categorie wordt alleen de geselecteerde categorie weergegeven.
![Nieuw](../assets/new.svg) AEM CIF [Pop-overwidget](https://github.com/adobe/aem-cif-guides-venia/pull/319) en [PLP-widget](https://github.com/adobe/aem-cif-guides-venia/pull/320) de componenten staan AEM plaatsen toe om voordeel te halen uit [!DNL Live Search].

### Updates

![Repareren](../assets/fix.svg) De tabelgrootte van de producten en de prijsvoeding is sterk afgenomen. Tabellen `catalog_data_exporter_products` en `catalog_data_exporter_product_prices` moet een aanzienlijke vermindering van de omvang zien.
![Repareren](../assets/fix.svg) Het tabblad &#39;Regels&#39; krijgt een andere naam dan &#39;Zoekregels&#39;
![Repareren](../assets/fix.svg) Wanneer u op &#39;trending&#39; rangschikt, kunt u nu kiezen tussen: * 3 dagen (standaardwaarde) * 14 dagen * 30 dagen
![Repareren](../assets/fix.svg) &#39;Gebeurtenissen&#39; (Boost/Pin/Bury/Hide) is hernoemd naar &#39;Handmatige volgorde&#39;
![Repareren](../assets/fix.svg) &#39;Type classificatie&#39; is hernoemd naar &#39;Intelligente classificatie&#39;
![Repareren](../assets/fix.svg) Kleine oplossingen voor problemen

## [!DNL Live Search] 3.1.0 {#310}

_1 sep. 2023_

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

### Updates

![Repareren](../assets/fix.svg) De widget voor productaanbiedingen is bijgewerkt om de [Catalogusservice-API](https://developer.adobe.com/commerce/services/graphql/catalog-service/product-search/).

## [!DNL Live Search] 3.0.2 {#302}

_7 augustus 2023_

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

### Nieuwe functies

![Nieuw](../assets/new.svg) De volgende waarden zijn toegevoegd aan de `storeDetails` object:

* &quot;Alle producten per pagina toestaan&quot;
* Valuta
* &quot;Producten per pagina op raster Toegestane waarden&quot;
* &quot;Producten per pagina op standaardwaarde van raster&quot;
* Winkeltaal

### Updates

![Repareren](../assets/fix.svg) De modules van de Dienst van de Catalogus zijn toegevoegd aan het metapakket om geavanceerde gegevensherwinning te steunen.
![Repareren](../assets/fix.svg) De **Mijn account** paginanavigatie verdwijnt niet meer wanneer u de widget pagina met productaanbiedingen gebruikt.

Handelaren moeten de [!DNL Live Search] extensie versie >= 3.0.2 gebruiken om deze functies te openen.

U wordt aangeraden een upgrade uit te voeren en te testen voordat u naar de productie gaat. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### Beperkingen

Als u de widget pagina met aanbiedingen van producten voor live zoeken gebruikt, mislukt Google Tag Manager. Gebruik de standaardzoekadapter als Google-tagbeheer nodig is.

## [!DNL Live Search] 3.0.1 {#301}

_14 maart 2023_

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

### Nieuwe functies

![Nieuw](../assets/new.svg) Productitemkaart in voorbeeld met regels
![Nieuw](../assets/new.svg) [Widget pagina met productaanbiedingen](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-storefront/plp-styling.html)
![Nieuw](../assets/new.svg) [Categoriefilteropties](https://developer.adobe.com/commerce/services/graphql/live-search/product-search/#facets)
![Nieuw](../assets/new.svg) Mogelijkheid toegevoegd om pengebeurtenissen te maken door slepen en neerzetten
![Nieuw](../assets/new.svg) Nieuwe vastzetacties: * Vastzetten op steun - De knop Vastzetten om een vastpingebeurtenis te maken met één klik * Aan de bovenkant vastzetten - Het product wordt op de eerste positie geplaatst * Aan de onderkant vastzetten - Het product wordt onder aan de resultaten geplaatst * Een gebeurtenis vrijmaken met één klik
![Nieuw](../assets/new.svg) [Intelligente classificatie voor regels](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/live-search-admin/rules/rules-add.html#ranking-type)
![Nieuw](../assets/new.svg) [!DNL Live Search] ondersteunt nu volledig [Inventory management](https://experienceleague.adobe.com/docs/commerce-admin/inventory/introduction.html) De mogelijkheden in Handel (vroeger kent als Multisource Inventory, of MSI). Om volledige steun toe te laten, moet u [update](install.md#update) de afhankelijkheidsmodule `commerce-data-export` naar versie 102.2.0+.

### Updates

![Repareren](../assets/fix.svg) Regels configureren sorteert posities nu automatisch uniek
![Repareren](../assets/fix.svg) Een bestaande gebeurtenis verwijderen werkt nu de voorvertoning bij
![Repareren](../assets/fix.svg) Regels zonder gebeurtenissen kunnen worden opgeslagen
![Repareren](../assets/fix.svg) Selector Type selecteren verwijderen
![Repareren](../assets/fix.svg) Nieuwe bewerkingsstatus toegevoegd voor niet-opgeslagen regels

### Oplossingen

![Repareren](../assets/fix.svg) Fout met vaste server als er een onvoltooide gebeurtenis is opgetreden tijdens opslaan
![Repareren](../assets/fix.svg) Correcte verwijdering van specifieke gebeurtenis bij meerdere gebeurtenissen opgelost
![Repareren](../assets/fix.svg) Gebeurtenis met bestaande regel is niet bijgewerkt wanneer een nieuwe gebeurtenis is toegevoegd. Dit probleem is nu opgelost.
![Repareren](../assets/fix.svg) Correctie voor tweede klik op Bewerken uit details. [!DNL Live Search] pagina die opnieuw moet worden geladen
![Repareren](../assets/fix.svg) Synoniemen: Probleem verholpen waarbij een gebruiker buiten invoer klikte en de focus niet naar het veld kon terugzetten
![Repareren](../assets/fix.svg) Andere kleine insectenmoeilijke situaties en prestatiesupdates


![Bug](../assets/bug.svg) - Rangschikken op &quot;Aanbevolen voor u&quot; wordt alleen ondersteund in de widgets Live zoeken. Deze functie wordt niet ondersteund met de standaardzoekfunctie voor Luma en PWA.
![Bug](../assets/bug.svg) - Aangepaste facetten van prijskenmerken worden niet correct weergegeven in Luma, maar de API filtert er op.

Handelaren moeten de [!DNL Live Search] extensie >= 3.0.1 gebruiken om deze functies te openen.

U wordt aangeraden een upgrade uit te voeren en te testen voordat u naar de productie gaat. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

## [!DNL Live Search] 2.0.5 {#205}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) - Live zoeken zou een fout veroorzaken als SDK-bronnen niet beschikbaar waren vanwege netwerkproblemen. Deze fout is opgelost.

Handelaars moeten de Live Search extensie versie >= 2.0.5 bevorderen om tot deze eigenschappen toegang te hebben.

U wordt aangeraden een upgrade uit te voeren en te testen voordat u naar de productie gaat. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### [!DNL Live Search] 2.0.4 {#204}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Live zoeken ondersteunt nu filteren met de instelling &#39;Producten uit voorraad weergeven&#39; in de beheerder. Als &#39;Display Out of Stock Products&#39; is ingesteld op false, `inStock = true` wordt toegevoegd aan het filter.
![Repareren](../assets/fix.svg) Om de prestaties te verbeteren, is het blok &#39;Suggestions&#39; verwijderd uit het pop-upmenu Live zoeken. De gegevens worden nog steeds doorgegeven via GraphQL, voor het geval u de functie wilt vervangen.
![Repareren](../assets/fix.svg) `categories` en `categoryPath` vervangen `categoryIds` voor filteren van categorieën. Lees meer in de [productSearch](https://developer.adobe.com/commerce/services/graphql/live-search/product-search/) onderwerp.
![Repareren](../assets/fix.svg) Eerder, zou een gebruiker verbonden aan een bedrijf B2B een onjuiste Code van de Groep van de Klant ontvangen wanneer het doen van onderzoeken. Live zoeken retourneert nu de juiste waarde.
![Repareren](../assets/fix.svg) Als u een term zoekt die niet bestaat, wordt een fout geretourneerd door Live zoeken. Die bug is nu opgelost.

Handelaren moeten de [!DNL Live Search] extensie >= 2.0.4 om toegang te krijgen tot deze functies.

De gebruikers worden geadviseerd om te bevorderen en te testen alvorens aan productie te duwen. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### [!DNL Live Search] 2.0.3 {#203}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Live zoeken ondersteunt nu B2B-functies door categorietoestemmingen, gedeelde catalogi en klantspecifieke prijzen te respecteren.

Handelaren moeten de [!DNL Live Search] extensie >= 2.0.3 gebruiken om deze functies te openen.

De gebruikers worden geadviseerd om te bevorderen en te testen alvorens aan productie te duwen. Overweeg om de productieomgeving tijdens niet-piekuren te upgraden nadat de resultaten van de testomgeving zijn gecontroleerd.

### [!DNL Live Search] 2.0 {#20}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

Bestaande [!DNL Live Search] de installaties moeten worden aangepast aan [!DNL Live Search] 2.0.0 om voordeel te halen uit de volgende nieuwe eigenschappen, moeilijke situaties, en verbeteringen:

![Nieuw](../assets/new.svg) [!DNL Live Search] ondersteunt nu PHP 8.1 voor installaties met Adobe Commerce 2.4.4.
![Nieuw](../assets/new.svg) De `Magento_ElasticsearchCatalogPermissionsGraphQl` wordt toegevoegd aan de lijst met modules die tijdens de installatie zijn uitgeschakeld.
![Nieuw](../assets/new.svg) Het aantal beschikbare regels in de [[!DNL storefront popover]](quick-tour.md) kan van worden gevormd *Beheerder*.
![Nieuw](../assets/new.svg) Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) ondersteund voor [!DNL Live Search].
![Nieuw](../assets/new.svg) De [!DNL Live Search] Het installatieproces wordt bijgewerkt met geavanceerde proceswijzigingen.
![Repareren](../assets/fix.svg) [Geavanceerd zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#advanced-search) koppeling verwijderd uit de voettekst van de winkel.
![Bug](../assets/bug.svg) De volgende productkenmerken worden niet ondersteund door [Commerce GraphQL API](https://developer.adobe.com/commerce/services/graphql/live-search/) bij gebruik in verband met de bètaversie van PWA: `description`, `name`, `short_description`
![Bug](../assets/bug.svg) De bètaversie van PWA voor [!DNL Live Search] ondersteunt niet [gebeurtenisafhandeling](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/).

### [!DNL Live Search] 1.3.1 {#131}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) [Aangepast prijskenmerk](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/attributes-input-types.html) keert niet meer een fout terug wanneer gevormd als a [facet]({% koppeling live-search/facets-add.md %}).
![Repareren](../assets/fix.svg) Er heeft zich een fout voorgedaan als er geen fout was opgetreden. Dit probleem is nu opgelost. [valutasymbool](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html#step-5%3A-customize-currency-symbols-(optional)) (`data-currency-symbol`) is beschikbaar.
![Repareren](../assets/fix.svg) [[!DNL Storefront popover]](storefront-popover.md) toont nu [Speciale prijs](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/product-price-special.html) (minimumverkoopprijs), indien beschikbaar.

### [!DNL Live Search] 1.3.0 {#130}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) [Prestaties](performance.md) het rapporteringsdashboard geeft inzicht in zoektermen die kopers gebruiken.
![Nieuw](../assets/new.svg) [!DNL Live Search] [Storefront Events SDK](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) verleent toegang tot een gemeenschappelijke gegevenslaag van gebeurtenis het publiceren en de abonnementendiensten, en metriek.
![Repareren](../assets/fix.svg) De [[!DNL Storefront popover]](storefront-popover.md) heeft een nieuwe `active` klasse voor de `.search-autocomplete` container die de zichtbaarheid bepaalt.
![Repareren](../assets/fix.svg) In de winkel [Zoekvoorwaarden](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html#popular-search-terms) voettekstkoppeling wordt verwijderd en de bijbehorende cache wordt uitgeschakeld voor [!DNL Live Search] installaties.
![Bug](../assets/bug.svg) Patch for Search adapter verwerkt dubbele producten.
![Bug](../assets/bug.svg) [!DNL Live Search] supports [uit één bron](https://experienceleague.adobe.com/docs/commerce-admin/inventory/sources/sources-manage.html) (fysieke) inventarislocaties met meerdere (virtuele) [voorraden](https://experienceleague.adobe.com/docs/commerce-admin/inventory/stocks/stocks-manage.html). Meerdere inventarisbronnen worden nu niet ondersteund.

### [!DNL Live Search] 1.2.0 {#120}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) [[!DNL Storefront popover]](storefront-popover.md) Hiermee geeft u voorgestelde producten en miniatuurafbeeldingen van de zoekresultaten van het hoogste niveau weer als kopers vragen typen in het vak Zoeken.
![Nieuw](../assets/new.svg) Handel *Beheerder* sessie blijft geopend tijdens lange perioden van inactiviteit op het toetsenbord
![Nieuw](../assets/new.svg) [!DNL Live Search] wordt automatisch ingeschakeld na het instappen
![Repareren](../assets/fix.svg) De aanvankelijke indexeertijd is minder dan een uur
![Repareren](../assets/fix.svg) Incrementele productupdates bijna realtime (na installatie en installatie)
![Repareren](../assets/fix.svg) Sorteerbare kolommen in Synoniemeditor
![Repareren](../assets/fix.svg) [!DNL Live Search] genereert niet langer een fout als zoekcriteria een lege sorteervolgordewaarde bevatten
![Repareren](../assets/fix.svg) Het filtreren van de waaier breekt niet meer als de attributencodes koorden &quot;aan&quot;of &quot;van&quot;bevatten

### [!DNL Live Search] 1.1.0 {#110}

[!BADGE Ondersteund]{type="Informatief" tooltip="Ondersteund"}

![Bug](../assets/bug.svg) De [!DNL Live Search] de dienst steunt slechts de [basisvaluta](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/site-store/currency/currency-configuration.html) van de Adobe Commerce-installatie.
![Bug](../assets/bug.svg) Wanneer u een facet toevoegt, wordt de feed Productkenmerken niet correct bijgewerkt wanneer deze is ingesteld op `Update on Save`. Ga om dit probleem te voorkomen naar [Indexbeheer](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html) en stel Productkenmerken in op Feed `Update by Schedule`.
![Bug](../assets/bug.svg) [!DNL Live Search] synoniemen worden gedefinieerd per winkelweergave, maar worden momenteel opgeslagen per website en geïdentificeerd met een combinatie van `environmentId` en `storeViewCode`. Dit heeft tot gevolg dat alle websites en winkelweergaven in de Adobe Commerce-installatie synoniemen delen. De meest recente reeks synoniemen voor de archiefmening krijgt belangrijkheid.
![Bug](../assets/bug.svg) Als een synoniem term meerdere woorden bevat, wordt elk woord behandeld als een afzonderlijk synoniem. Als u bijvoorbeeld &#39;tijdstuk&#39; definieert als een synoniem van &#39;watch&#39;, worden zowel &#39;time&#39; als &#39;piece&#39; beschouwd als synoniemen van &#39;watch&#39;.

+++

## Documentatie

Meer informatie:

* [Adobe Commerce Developer Documentation](https://developer.adobe.com/commerce/docs)
* [Adobe Commerce-gebruikershandleiding](https://experienceleague.adobe.com/docs/commerce.html)
* [[!DNL Live Search] op Marketplace](https://commercemarketplace.adobe.com/magento-live-search.html)
