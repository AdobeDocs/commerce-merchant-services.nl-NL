---
title: Storefront Popover
description: Met de pop-up Live zoeken worden dynamisch voorgestelde producten en miniaturen geretourneerd.
exl-id: 88fdc3ed-b606-40de-94b7-435be09c4072
source-git-commit: 7402e97f53b71e488d860215487f4809572b7e6f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# Storefront Popover

Wanneer [!DNL Live Search] is [geïnstalleerd](install.md), wordt een pop-up weergegeven in de winkel wanneer kopers tekst typen in de [Zoeken](https://docs.magento.com/user-guide/catalog/search-quick.html) doos. Als elk teken wordt getypt, wordt de pop-up bijgewerkt met voorgestelde producten en miniatuurafbeeldingen van de bovenste zoekresultaten.

[!DNL Live Search] retourneert resultaten voor een query van twee tekens of meer. Voor een gedeeltelijke overeenkomst, is het maximumaantal karakters per woord 20. Het aantal karakters in een &quot;onderzoek aangezien u&quot;vraag typt is niet configureerbaar.

>[!NOTE]
>
>De [!DNL Live Search] popover van de opslag is beschikbaar slechts voor winkels die gebruiken *Luminantie* thema of een aangepast thema dat is gebaseerd op *Luminantie*. De *Luminantie* thema is opgenomen in het [!DNL Commerce] voorbeeldgegevens. De popover biedt geen ondersteuning voor de *Leeg* thema. Zie [Werken met een gewijzigd thema](#working-with-modified-theme) voor meer informatie .

## Doorzoekbare kenmerken

Als u gerichte resultaten wilt bereiken, kunt u de set [doorzoekbaar](https://docs.magento.com/user-guide/stores/attributes-product.html#storefront-properties) (`searchable=true`) productkenmerken. Om relevantie te verzekeren, maak attributen doorzoekbaar slechts als zij inhoud bevatten die een duidelijke en beknopte betekenis heeft. Gebruik geen kenmerken die minder nauwkeurige, lange tekst bevatten, zoals `description`Deze optie is standaard ingeschakeld, maar hierdoor kan de precisie van zoekresultaten afnemen. Als iemand bijvoorbeeld zoekt naar &quot;korte broeken&quot; en er overhemden zijn met een beschrijving die de term &quot;korte mouwen&quot; bevat, worden de overhemden opgenomen in de zoekresultaten.

De volgende kenmerken kunnen altijd worden doorzocht:

* `sku`
* `name`
* `categories`

![popup Live zoeken](assets/storefront-search-as-you-type.png)
