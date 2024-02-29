---
title: Inleiding tot [!DNL Live Search]
description: "[!DNL Live Search] van Adobe Commerce biedt een snelle, relevante en intuïtieve zoekervaring."
exl-id: aca0ef19-ead1-4c79-90c3-db5ec48cb3c1
recommendations: noCatalog
source-git-commit: 51ff52eba117fe438d592ca886dbca25304a0d15
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Inleiding tot [!DNL Live Search]

[!DNL Live Search] is een service voor Adobe Commerce die de standaardzoekmogelijkheden vervangt. De [!DNL Live Search] wordt geïnstalleerd met Composer en maakt verbinding met uw [!DNL Commerce] installatie aan de [!DNL Live Search] [service](../landing/saas.md). Wanneer het wordt gevormd, wordt het standaardonderzoekstekstgebied vervangen met [!DNL Live Search] tekstveld. [!DNL Live Search] Hiermee installeert u ook de widget PLOP (Product Listing Page), die bij het bladeren in zoekresultaten robuuste filtermogelijkheden biedt.

[!DNL Live Search] verschijnt op de *Marketing* menu onder *SEO &amp; Search* in de [!DNL Commerce] *Beheerder*.

De Adobe Commerce-zijde van de architectuur bevat hosting van de zoekopdracht *Beheerder*, catalogusgegevens synchroniseren en de queryservice uitvoeren. Na [!DNL Live Search] is geïnstalleerd en geconfigureerd, begint Adobe Commerce met het delen van zoek- en catalogusgegevens met SaaS-services. Op dit moment kunnen Admin-gebruikers de zoekopdracht instellen, aanpassen en beheren [facetten](facets.md), [synoniemen](synonyms.md), en [handelsregels](category-merch.md).

## Componenten Live zoeken

* [!DNL Live Search] [widget pop-up](storefront-popover.md) Dit is het vak dat wordt geopend onder het zoekveld dat de zoekresultaten bevat.
* [Widget pagina met productaanbiedingen](plp-styling.md) biedt ondersteuning voor zoekbare productlijsten met facetten en synoniemen.
* AEM CIF componenten: [Pop-overwidget](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/live-search-popover.html?lang=en) en de [PLP-widget](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/live-search-plp.html) AEM sites laten profiteren van [!DNL Live Search].
* [[!DNL Live Search] Beheerder](workspace.md) Hier worden regels, facetten en synoniemen geconfigureerd.

## Workflowoverzicht

[!DNL Live Search] werkt door catalogusgegevens naar de Adobe Commerce SaaS-infrastructuur te verplaatsen en indexen samen te stellen die worden gebruikt voor het snel leveren van zoekresultaten als gebruikerstype.

### 1. Installatie

[!DNL Live Search] is [geïnstalleerd](install.md) in je Adobe Commerce-exemplaar via [Composer](https://getcomposer.org/). Dit installeert de vereiste modules die met de dienst verbinden en vormt de instantie van de Handel om het standaardonderzoeksgebied met voeten te treden. Het installeert ook de opties van Admin van de Handel voor het vormen van de dienst.

### 2. Gegevens synchroniseren

[!DNL Live Search] Hiermee verplaatst u catalogusgegevens naar de SaaS-infrastructuur van de Adobe. De gegevens worden geïndexeerd en de zoekresultaten worden vanuit deze index rechtstreeks aan de winkel geleverd. Afhankelijk van de grootte en complexiteit kan het indexeren 30 minuten tot een paar uur duren.

### 3. Gegevens configureren

Als u uw productgegevens correct configureert, bent u verzekerd van goede zoekresultaten voor uw klanten. Er zijn een paar vereiste opstellingsstappen: het toewijzen van categorieën en het vormen van attributen.

#### Categorieën toewijzen

Product geretourneerd in [!DNL Live Search] moet een [categorie](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/categories.html). In Luma worden producten bijvoorbeeld ingedeeld in categorieën zoals &quot;Mannen&quot;, &quot;Vrouwen&quot; en &quot;Luma&quot;. Subcategorieën worden ook ingesteld voor Tops, Bottoms en Watches. Hierdoor wordt de korreligheid bij het filteren verbeterd.

#### Doorzoekbare en filterbare velden

Producten worden toegewezen [attributes](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) die kunnen worden gebruikt voor zoeken en filteren. Kenmerken zijn dingen als &quot;Kleur&quot;, &quot;Grootte&quot; en &quot;Materiaaltype&quot;. Met deze kenmerken kunnen gebruikers zoeken naar &quot;groene toppen&quot;. Elk product kan vele eigenschappen hebben die in Commerce admin worden bepaald.

Elk van deze kenmerken kan worden gedefinieerd als [&quot;doorzoekbaar&quot;](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html) in de beheerder. Wanneer deze worden ingesteld als &quot;doorzoekbaar&quot;, kunnen deze kenmerken worden doorzocht door [!DNL Live Search].

[Facetten](facets.md) zijn productkenmerken die worden gedefinieerd in [!DNL Live Search] filterbaar zijn. Elk filterbaar kenmerk kan als een facet worden ingesteld in [!DNL Live Search] maar er zijn grenzen aan het aantal facetten dat tegelijk kan worden doorzocht .

[Synoniemen](synonyms.md) Dit zijn termen die u kunt definiëren om gebruikers te helpen bij het vinden van het juiste product. Gebruikers die op zoek zijn naar een broek kunnen &#39;broek&#39; of &#39;slacks&#39; typen. U kunt synoniemen zodanig instellen dat deze zoektermen gebruikers naar de resultaten van de &#39;&#39;broek&#39;&#39; brengen.

## [!DNL Live Search] werkruimte

De [!DNL Live Search] [werkruimte](workspace.md) is het gebied in Admin waar u vormt [!DNL Live Search] functies zoals synoniemen, facetten en Categorie Merchandising.

## Gebeurtenissen

[!DNL Live Search] gebruik [gebeurtenissen](events.md) om te berekenen [Intelligente handel](category-merch.md) en [prestaties](performance.md) dashboards. Eventing wordt voorzien van standaardimplementaties. Eventing voor hoofdloze winkelcentra moet handmatig worden ingeschakeld.

## Widgets aanpassen

De meeste winkeleigenaars willen ervoor zorgen dat de [!DNL Live Search] widgets passen zich aan hun winkeluiterlijk aan.

De popover- en PLP-widgets kunnen zo nodig worden vormgegeven door aangepaste CSS-regels te definiëren. Zie [Popup-elementen opmaken](storefront-popover-styling.md) en [Widget pagina met productaanbiedingen](plp-styling.md).

Als u de functionaliteit van de widgets wilt uitbreiden, is de broncode voor elke widget beschikbaar in een openbare reactie.
In dit scenario, kunt u JavaScript voor uw eigen behoeften aanpassen en dan uw douanecode op uw CDN ontvangen. Dit aangepaste script communiceert met het [!DNL Live Search] De dienst en keert de resultaten als normaal terug, toestaand u om de functionaliteit van widget te controleren.

* [PLP-widgetreactie](https://github.com/adobe/storefront-product-listing-page)
* [Reactie op zoekbalk](https://github.com/adobe/storefront-search-as-you-type)

Meer informatie over [!DNL Live Search] in de [Technisch overzicht](technical-overview.md).

## [!DNL Live Search] demo

Bekijk deze video voor meer informatie over [!DNL Live Search]:

>[!VIDEO](https://video.tv.adobe.com/v/3418679?quality=12&learn=on)

Voor een meer diepgaande video over het gebruiken en vormen van Levend Onderzoek, zie [Volledige demonstratie op [!DNL Live Search]](https://experienceleague.adobe.com/docs/commerce-learn/tutorials/getting-started/capabilities/live-search-full-demonstration.html) onderwerp.
