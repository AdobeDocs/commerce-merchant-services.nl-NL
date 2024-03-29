---
title: "[!DNL Storefront Popover]"
description: "De [!DNL Live Search storefront popover] Geeft dynamisch voorgestelde producten en miniaturen."
exl-id: 88fdc3ed-b606-40de-94b7-435be09c4072
source-git-commit: c77b2f9cb55d3eb339dcc900ce606b94c592f559
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# [!DNL Storefront Popover]

Wanneer [!DNL Live Search] is [geïnstalleerd](install.md), [!DNL popover] wordt weergegeven in de winkel wanneer kopers tekst typen in het vak [Zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#quick-search) doos. Als elk teken is getypt, wordt het [!DNL popover] wordt bijgewerkt met voorgestelde producten en duimnagelbeelden van de hoogste onderzoeksresultaten.

[!DNL Live Search] retourneert resultaten voor een query van twee tekens of meer. Voor een gedeeltelijke overeenkomst, is het maximumaantal karakters per woord 20. Het aantal karakters in een &quot;onderzoek aangezien u&quot;vraag typt is niet configureerbaar.

Standaard, [!DNL Live Search] supports [heroriëntering van zoektermen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html).

![[!DNL Live Search popover]](assets/storefront-search-as-you-type.png)

## Doorzoekbare kenmerken

Als u gerichte resultaten wilt bereiken, kunt u de set [doorzoekbaar](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/product-attributes.html) (`searchable=true`) productkenmerken. Om relevantie te verzekeren, maak attributen doorzoekbaar slechts als zij inhoud bevatten die een duidelijke en beknopte betekenis heeft. Gebruik geen kenmerken die minder nauwkeurige, lange tekst bevatten, zoals `description`Deze optie is standaard ingeschakeld, maar hierdoor kan de precisie van zoekresultaten afnemen.
Als iemand bijvoorbeeld zoekt naar &quot;korte broeken&quot; en er overhemden zijn met een beschrijving die de term &quot;korte mouwen&quot; bevat, worden de overhemden opgenomen in de zoekresultaten.

[!DNL Live Search] eerbiedigt tevens de [gewicht](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-results.html#weighted-search) van een productkenmerk, zoals ingesteld in Adobe Commerce. Kenmerken met een hogere dikte worden hoger weergegeven in de zoekresultaten.

De volgende kenmerken kunnen altijd worden doorzocht:

* `sku`
* `name`
* `categories`

## [!DNL Popover] paginaformaat

De paginagrootte van de [!DNL popover] bepaalt hoeveel lijnen van autocompleted producten kunnen worden teruggekeerd. Eerder was het paginaformaat gecodeerd als zes regels. De `page_size` de waarde is nu een het plaatsen die van kan worden gevormd *Beheerder*. Tijdens de installatie van Live zoeken worden de `page_size` wijzigt de huidige waarde van de [Catalogus zoeken](https://experienceleague.adobe.com/docs/commerce-admin/config/catalog/catalog.html) - `Autocomplete Limit` instellen.

Standaard is de waarde voor Zoeken in catalogus - automatisch aanvullen van limiet ingesteld op acht regels (of rijen). Het paginaformaat wijzigen van het dialoogvenster [!DNL popover]Ga als volgt te werk:

1. Op de *Beheerder* zijbalk, ga naar **Winkels** > Instellingen > **Configuratie**.
1. Vouw in het linkerdeelvenster uit **Catalogus** en kiest u **Catalogus** in de lijst met instellingen.
1. Breid uit *Catalogus zoeken* sectie.
1. Stel de **Limiet automatisch aanvullen** op het aantal regels dat u wilt toestaan in het dialoogvenster [!DNL popover].
1. Klik op **Config opslaan**.

## Catalogusservice

De [Catalogusservice voor Adobe Commerce](../catalog-service/overview.md) de uitbreiding verstrekt rijke mening-model catalogusgegevens om product-gerelateerde storefront ervaringen snel en volledig terug te geven. De Catalog Service kan in combinatie met Live Search worden gebruikt voor functionaliteit die momenteel niet door de native extensie wordt ondersteund:

* Uitgebreide kenmerken
* Andere productinformatie kan worden ingevoerd

Merchants kunnen widgets of winkelelementen aanpassen en uitbreiden door de Dienst van de Catalogus te gebruiken, maar dit is buiten werkingsgebied voor het ondersteuningsteam van de Adobe.

## Implementaties zonder kop

Voor gebruikers met een headless-implementatie is het mogelijk om de Live Search-popover te installeren met een [npm-pakket](https://www.npmjs.com/package/@magento/ds-livesearch-storefront-utils).

## Beperkingen

* De [!DNL Live Search] [!DNL storefront popover] is alleen beschikbaar voor winkels die de *Luminantie* thema of een aangepast thema dat is gebaseerd op *Luminantie*. Broodkruimels op de pagina met zoekresultaten hebben geen *Luminantie* stijlen.
* De [!DNL popover] ondersteunt de *Leeg* thema. Zie [Stijlen [!DNL Popover] Elementen](storefront-popover-styling.md) voor meer informatie.
* De [!DNL popover] wordt niet ondersteund op het formulier Snelle volgorde.
* Schijflijsten en productvergelijkingen worden niet ondersteund.
