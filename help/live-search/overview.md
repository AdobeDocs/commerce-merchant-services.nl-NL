---
title: Wat is [!DNL Live Search]?
description: "[!DNL Live Search] van Adobe Commerce biedt een snelle, relevante en intuïtieve zoekervaring."
exl-id: aca0ef19-ead1-4c79-90c3-db5ec48cb3c1
recommendations: noCatalog
source-git-commit: aba552808ea7af540f64f00a2ae4aeaf2b9cc52e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Wat is [!DNL Live Search]?

[!DNL Live Search] is een extensie die de standaardzoekmogelijkheden in Adobe Commerce vervangt. De [!DNL Live Search] is geïnstalleerd met Composer en maakt verbinding met uw [!DNL Commerce] installatie aan de [!DNL Live Search] [service](../landing/saas.md). Wanneer het wordt gevormd, wordt het standaardonderzoekstekstgebied vervangen met [!DNL Live Search] tekstveld. [!DNL Live Search] Hiermee installeert u ook de widget PLOP (Product Listing Page), die bij het bladeren in zoekresultaten robuuste filtermogelijkheden biedt.

Met [!DNL Live Search]kunt u:

- Creëer zinvolle zoekervaringen om kopers te helpen bij het vinden van wat ze willen, zo weinig mogelijk.
- Profiteer van dynamische facettering op basis van AI en herrangschikking van zoekresultaten als reactie op winkelgedrag tijdens een sessie.
- Gebruik een eenvoudige SaaS-gebaseerde service die eenvoudige updates biedt en in uw licentie is opgenomen, waardoor de totale eigendomskosten dalen.
- Krijg technisch door graphQL API, headless flexibiliteit, API zandbakmilieu&#39;s, en ultrasnelle SaaS toe te laten.

>[!IMPORTANT]
>
>Adobe Commerce biedt opties voor het zoeken naar sites. Zorg ervoor dat u het document [Grenzen en grenzen](boundaries-limits.md) vóór de uitvoering [!DNL Live Search] is geschikt voor uw bedrijfsbehoeften.

## Architectuur

De Adobe Commerce-zijde van de architectuur bevat hosting van de zoekopdracht *Beheerder*, catalogusgegevens synchroniseren en de queryservice uitvoeren. Na [!DNL Live Search] is geïnstalleerd en geconfigureerd, begint Adobe Commerce met het delen van zoek- en catalogusgegevens met SaaS-services. Op dit moment kunnen Admin-gebruikers de zoekopdracht instellen, aanpassen en beheren [facetten](facets.md), [synoniemen](synonyms.md), en [handelsregels](category-merch.md).

![Live Search Data Flow](assets/ls-cs-data-flow.png)

## Snelle rondleiding

Met de nadruk op snelheid, relevantie en gebruiksgemak, [!DNL Live Search] is een spelwisselaar voor zowel winkeliers als handelaren . Bekijk de volgende video en bekijk een snelle rondleiding van [!DNL Live Search] van de opslagplaats.

>[!VIDEO](https://video.tv.adobe.com/v/3418679?quality=12&learn=on)

Voor een meer diepgaande video over het gebruiken en vormen van Levend Onderzoek, zie [Volledige demonstratie op [!DNL Live Search]](https://experienceleague.adobe.com/docs/commerce-learn/tutorials/getting-started/capabilities/live-search-full-demonstration.html) onderwerp.

### Zoeken terwijl u typt

[!DNL Live Search] reageert met voorgestelde producten en een miniatuurafbeelding van de bovenste zoekresultaten in een [popup](storefront-popover.md) als type query&#39;s voor kopers in de [Zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#quick-search) doos. De [productdetails](https://experienceleague.adobe.com/docs/commerce-admin/start/storefront/storefront.html#product-page) wordt weergegeven wanneer kopers op een voorgesteld of aanbevolen product klikken. A _Alles weergeven_ de koppeling in de voettekst van de pop-up geeft de pagina met zoekresultaten weer.

[!DNL Live Search] retourneert de resultaten &quot;search as you type&quot; voor een query van twee of meer tekens. Voor een gedeeltelijke overeenkomst, is het maximumaantal karakters per woord 20. Het aantal karakters in de vraag is niet configureerbaar. De popover bevat de`name`, `sku`, en `category_ids` velden.

![Voorbeeld van winkel - zoeken terwijl u typt](assets/storefront-search-as-you-type.png)

### Alle zoekresultaten weergeven

Als u alle producten wilt weergeven die door de query &quot;search as you type&quot; worden geretourneerd, klikt u op _Alles weergeven_ in de voettekst van de pop-up.

![Voorbeeld van een winkel - prijsfactoren](assets/storefront-view-all-search-results.png)

### Gefilterde zoekopdracht met facetten

Bij gefilterde zoekopdracht worden meerdere afmetingen van kenmerkwaarden gebruikt, of [facetten](facets.md), als zoekcriteria. De selectie van filters wordt gedefinieerd door de handelaar en verandert afhankelijk van de geretourneerde producten, waarbij de meest gebruikte facetten boven aan de lijst worden vastgezet.

Facetten gebruiken als URL-parameters:`http://yourwebsite.com?color=red`en de resultaten van de filters Live Search op basis van deze kenmerkwaarden.

### Synoniemen

[Synoniemen](synonyms.md) breid het bereik uit en verscherp de focus van query&#39;s door woorden op te nemen die anders zijn dan die in de catalogus. U kunt het synoniem woordenboek perfectioneren om consumenten betrokken te houden en op de weg aan aankoop.

### Handelsregels

Merchandising [regels](rules.md) Vorm de het winkelen ervaring met als-dan verklaringen die logica en gebeurtenissen toevoegen aan onderzoek. U kunt producten eenvoudig verhogen of begraven voor een promotie, seizoen, of een andere periode.

### Ondersteuning voor zoektermen

[!DNL Live Search] supports Commerce [heroriëntering van zoektermen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html). Gebruikers kunnen bijvoorbeeld zoeken naar een term zoals &quot;Verzendkosten&quot; en deze rechtstreeks doorsturen naar de pagina Verzendkosten.

## Componenten Live zoeken

- [!DNL Live Search] [widget pop-up](storefront-popover.md) Dit is het vak dat wordt geopend onder het zoekveld dat de zoekresultaten bevat.
- [Widget pagina met productaanbiedingen](plp-styling.md) biedt ondersteuning voor zoekbare productlijsten met facetten en synoniemen.
- [[!DNL Live Search] Beheerder](workspace.md) Hier worden regels, facetten en synoniemen geconfigureerd.

## [!DNL Live Search] werkruimte

De [!DNL Live Search] [werkruimte](workspace.md) is het gebied in Admin waar u vormt [!DNL Live Search] functies zoals synoniemen, facetten en Categorie Merchandising.

## Gebeurtenissen

[!DNL Live Search] gebruik [gebeurtenissen](events.md) om te berekenen [Intelligente handel](category-merch.md) en [prestaties](performance.md) dashboards. Eventing wordt voorzien van standaardimplementaties. Eventing voor hoofdloze winkelcentra moet handmatig worden ingeschakeld.
