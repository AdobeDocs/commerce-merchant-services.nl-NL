---
title: Inleiding tot [!DNL Live Search]
description: "[!DNL Live Search] van Adobe Commerce biedt een bliksemsnelle, superrelevante en intuïtieve zoekervaring."
exl-id: aca0ef19-ead1-4c79-90c3-db5ec48cb3c1
recommendations: noCatalog
source-git-commit: c77b2f9cb55d3eb339dcc900ce606b94c592f559
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 0%

---

# Inleiding tot [!DNL Live Search]

[!DNL Live Search] is een service voor Adobe Commerce die de standaardzoekmogelijkheden vervangt. De [!DNL Live Search] wordt geïnstalleerd met Composer en maakt verbinding met uw [!DNL Commerce] installatie aan de [!DNL Live Search] [service](../landing/saas.md). Wanneer het wordt gevormd, wordt het standaardonderzoekstekstgebied vervangen met [!DNL Live Search] tekstveld. [!DNL Live Search] Hiermee installeert u ook de widget PLOP (Product Listing Page), die bij het bladeren in zoekresultaten robuuste filtermogelijkheden biedt.

[!DNL Live Search] verschijnt op de *Marketing* menu onder *SEO &amp; Search* in de [!DNL Commerce] *Beheerder*.

De Adobe Commerce-zijde van de architectuur bevat hosting van de zoekopdracht *Beheerder*, catalogusgegevens synchroniseren en de queryservice uitvoeren. Na [!DNL Live Search] is geïnstalleerd en geconfigureerd, begint Adobe Commerce met het delen van zoek- en catalogusgegevens met SaaS-services. Op dit moment kunnen Admin-gebruikers de zoekopdracht instellen, aanpassen en beheren [facetten](facets.md), [synoniemen](synonyms.md), en [handelsregels](category-merch.md).

![Architectuurdiagram van Live Search](assets/architecture-diagram.svg)

## Componenten Live zoeken

* [!DNL Live Search] [popup](storefront-popover.md) Dit is het vak dat wordt geopend onder het zoekveld dat de zoekresultaten bevat.
* [Widget pagina met productaanbiedingen](plp-styling.md) biedt ondersteuning voor zoekbare productlijsten met facetten en synoniemen.
* AEM CIF componenten: [Pop-overwidget](https://github.com/adobe/aem-cif-guides-venia/pull/319) en de [PLP-widget](https://github.com/adobe/aem-cif-guides-venia/pull/320) AEM sites laten profiteren van [!DNL Live Search].
* [[!DNL Live Search] Beheerder](workspace.md) Hier worden regels, facetten en synoniemen geconfigureerd.
* De Adapter van het Onderzoek is de standaardimplementatie van [!DNL Live Search]. Aanbevolen voor headless- en aangepaste implementaties.

## [!DNL Live Search] demo

Bekijk deze video voor meer informatie over [!DNL Live Search]:

>[!VIDEO](https://video.tv.adobe.com/v/3418679?quality=12&learn=on)

Voor een meer diepgaande video over het gebruiken en vormen van Levend Onderzoek, zie [Volledige demonstratie op [!DNL Live Search]](https://experienceleague.adobe.com/docs/commerce-learn/tutorials/marketing/live-search-full-demonstration.html) onderwerp.
