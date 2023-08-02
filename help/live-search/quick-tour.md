---
title: "Snelle rondleiding"
description: "Maak een snelle rondleiding door [!DNL Live Search] uit de winkel."
exl-id: bcb19506-6617-4c8a-83df-9d961f81e9e8
source-git-commit: 9cf48f6f900385a5cb772adee8834ec9cfe5ee13
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---

# Snelle rondleiding

Met de nadruk op snelheid, relevantie en gebruiksgemak, [!DNL Live Search] is een spelwisselaar voor zowel winkeliers als handelaren . Volg de rondleiding van [!DNL Live Search] van de opslagplaats.

## Zoeken terwijl u typt

[!DNL Live Search] reageert met voorgestelde producten en een miniatuurafbeelding van de bovenste zoekresultaten in een [popup](storefront-popover.md) als type query&#39;s voor kopers in de [Zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#quick-search) doos. De [productdetails](https://experienceleague.adobe.com/docs/commerce-admin/start/storefront/storefront.html#product-page) wordt weergegeven wanneer kopers op een voorgesteld of aanbevolen product klikken. A _Alles weergeven_ de koppeling in de voettekst van de pop-up geeft de pagina met zoekresultaten weer.

[!DNL Live Search] retourneert de resultaten &quot;search as you type&quot; voor een query van twee of meer tekens. Voor een gedeeltelijke overeenkomst, is het maximumaantal karakters per woord 20. Het aantal karakters in de vraag is niet configureerbaar. De pop-up bevat de volgende velden: `name`, `sku`, en `category_ids`.

![Voorbeeld van winkel - zoeken terwijl u typt](assets/storefront-search-as-you-type.png)

## Alle zoekresultaten weergeven

Als u alle producten wilt weergeven die door de query &quot;search as you type&quot; worden geretourneerd, klikt u op _Alles weergeven_ in de voettekst van de pop-up.

![Voorbeeld van een winkel - prijsfactoren](assets/storefront-view-all-search-results.png)

## Gefilterde zoekopdracht met facetten

Bij gefilterde zoekopdracht worden meerdere afmetingen van kenmerkwaarden gebruikt, of [facetten](facets.md), als zoekcriteria. De selectie van filters wordt gedefinieerd door de handelaar en verandert afhankelijk van de geretourneerde producten, waarbij de meest gebruikte facetten boven aan de lijst worden vastgezet.

Facetten gebruiken als URL-parameters:`http://yourwebsite.com?color=red`en de resultaten van de filters Live Search op basis van deze kenmerkwaarden.

## Synoniemen

[Synoniemen](synonyms.md) breid het bereik uit en verscherp de focus van query&#39;s door woorden op te nemen die anders zijn dan die in de catalogus. U kunt het synoniem woordenboek perfectioneren om consumenten betrokken te houden en op de weg aan aankoop.

## Handelsregels

Merchandising [regels](rules.md) Vorm de het winkelen ervaring met als-dan verklaringen die logica en gebeurtenissen toevoegen aan onderzoek. U kunt producten eenvoudig verhogen of begraven voor een promotie, seizoen, of een andere periode.
