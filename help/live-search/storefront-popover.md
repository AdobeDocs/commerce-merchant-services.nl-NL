---
title: "[!DNL Storefront Popover]"
description: "De [!DNL Live Search storefront popover] Geeft dynamisch voorgestelde producten en miniaturen."
exl-id: 88fdc3ed-b606-40de-94b7-435be09c4072
source-git-commit: e375404a50dd4972ab584f69d7953aba2c8f4566
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Storefront Popover]

Wanneer [!DNL Live Search] is [geïnstalleerd](install.md), [!DNL popover] wordt weergegeven in de winkel wanneer kopers tekst typen in het vak [Zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#quick-search) doos. Als elk teken is getypt, wordt het [!DNL popover] wordt bijgewerkt met voorgestelde producten en duimnagelbeelden van de hoogste onderzoeksresultaten.

[!DNL Live Search] retourneert resultaten voor een query van twee tekens of meer. Voor een gedeeltelijke overeenkomst, is het maximumaantal karakters per woord 20. Het aantal karakters in een &quot;onderzoek aangezien u&quot;vraag typt is niet configureerbaar.

Standaard, [!DNL Live Search] supports [heroriëntering van zoektermen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html).

![[!DNL Live Search popover]](assets/storefront-search-as-you-type.png)

>[!TIP]
>
>Leer hoe u productkenmerken kunt instellen als doorzoekbaar in het dialoogvenster [Live zoeken instellen](workspace.md) artikel.

## [!DNL Popover] paginaformaat

De paginagrootte van de [!DNL popover] bepaalt hoeveel lijnen van autocompleted producten kunnen worden teruggekeerd. Tijdens de installatie van Live zoeken worden de `page_size` wijzigt de huidige waarde van de [Catalogus zoeken](https://experienceleague.adobe.com/docs/commerce-admin/config/catalog/catalog.html) - `Autocomplete Limit` instellen.

Standaard is de waarde voor Zoeken in catalogus - automatisch aanvullen van limiet ingesteld op acht regels (of rijen). Het paginaformaat wijzigen van het dialoogvenster [!DNL popover]Ga als volgt te werk:

1. Op de *Beheerder* zijbalk, ga naar **Winkels** > Instellingen > **Configuratie**.
1. Vouw in het linkerdeelvenster uit **Catalogus** en kiest u **Catalogus** in de lijst met instellingen.
1. Breid uit *Catalogus zoeken* sectie.
1. Stel de **Limiet automatisch aanvullen** op het aantal regels dat u wilt toestaan in het dialoogvenster [!DNL popover].
1. Klik op **Config opslaan**.

## Stijlen [!DNL Popover] voorbeeld

U kunt het uiterlijk van de [!DNL Popover] widget aanpassen aan de stijl en merkrichtlijnen van uw bedrijf.

De [!DNL storefront popover] geeft altijd het product weer `name` en `price`en de selectie van velden kan niet worden geconfigureerd. Maar [!DNL popover] elementen kunnen worden opgemaakt met [CSS](https://developer.adobe.com/commerce/frontend-core/guide/css/) klassen. Met de volgende declaraties wijzigt u bijvoorbeeld de achtergrondkleur van de [!DNL popover] container en voettekst.

```css
.livesearch.popover-container {
    background-color: lavender;
}

.livesearch.view-all-footer {
    background-color: magenta;
}
```

## Zichtbaarheid container

De bovenliggende component van de component `.livesearch.popover-container` is `.search-autocomplete`.  De `.active` -klasse geeft de zichtbaarheid van de container aan. De `.active` wordt voorwaardelijk toegevoegd wanneer [!DNL popover] is geopend.

```css
.search-autocomplete.active   /* visible */
.search-autocomplete          /* not visible */
```

Raadpleeg voor meer informatie over opmaakelementen voor winkelobjecten de [Cascading Style Sheets (CSS)](https://developer.adobe.com/commerce/frontend-core/guide/css/) in de [Frontend Developer Guide](https://developer.adobe.com/commerce/frontend-core/guide/).

## Klasse-kiezers

U kunt de volgende klassenkiezers gebruiken om de container- en productelementen in het deelvenster [!DNL popover].

- `.livesearch.popover-container`
- `.livesearch.view-all-footer`
- `.livesearch.products-container`
- `.livesearch.product-result`
- `.livesearch.product-name`
- `.livesearch.product-price`

### Containerklassekiezers

#### .livessearch.popover-container

![[!DNL Popover] container](assets/livesearch-popover-container.png)

#### .livessearch.view-all-footer

![Alle voetteksten weergeven](assets/livesearch-view-all-footer.png)

### Kiezers voor productklassen

#### .livessearch.products-container

![Productcontainer](assets/livesearch-product-container.png)

#### .livessearch.product-result

![Product-resultaat](assets/livesearch-product-result.png)

#### .livessearch.product-name

![Productnaam](assets/livesearch-product-name.png)

#### .livessearch.product-price

![Productprijs](assets/livesearch-product-price.png)

#### .livessearch product-link

![Product-resultaat](assets/livesearch-product-link.png)

## Werken met een gewijzigd thema {#working-with-modified-theme}

U kunt de [!DNL storefront popover] met een aangepaste [thema](https://developer.adobe.com/commerce/frontend-core/guide/themes/) dat de vereiste bestanden overneemt van *Luminantie*. De `top.search` in de `header-wrapper` van de `Magento_Search` mag niet worden gewijzigd.

```html
<referenceContainer name="header-wrapper">
   <block class="Magento\Framework\View\Element\Template" name="top.search" as="topSearch" template="Magento_Search::form.mini.phtml">
      <arguments>
         <argument name="configProvider" xsi:type="object">Magento\Search\ViewModel\ConfigProvider</argument>
      </arguments>
   </block>
</referenceContainer>
```

## Het onbruikbaar maken van [!DNL popover]

Om het [!DNL popover] en herstel de standaard [Snel zoeken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search.html#quick-search) voert u de volgende opdracht in:

```bash
bin/magento module:disable Magento_LiveSearchStorefrontPopover
```

## Implementaties zonder kop

Voor gebruikers met een headless-implementatie kunt u de [!DNL Live Search popover] met een [npm-pakket](https://www.npmjs.com/package/@magento/ds-livesearch-storefront-utils).
