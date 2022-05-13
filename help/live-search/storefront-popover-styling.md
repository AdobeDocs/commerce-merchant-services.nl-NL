---
title: Popup-elementen opmaken
description: Technische notities over het aanpassen van de pop-up Live zoeken in de winkel.
exl-id: 033049f2-976e-4299-b026-333ac4b481a3
source-git-commit: 65126f10574801f7ea8d0a863e9bb512dca13f39
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Stijlen [!DNL Popover] Elementen

De [[!DNL storefront popover]](storefront-popover.md) geeft altijd het product weer `name` en `price`en de selectie van velden kan niet worden geconfigureerd. Maar [!DNL popover] elementen kunnen worden vormgegeven met gebruik van CSS-klassen. Met de volgende declaraties wijzigt u bijvoorbeeld de achtergrondkleur van de [!DNL popover] container en voettekst.

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

Raadpleeg voor meer informatie over opmaakelementen voor winkelobjecten de [Cascading Style Sheets (CSS)](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/css-topics/css-overview.html) in de [Frontend Developer Guide](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/bk-frontend-dev-guide.html).

## Klasse-kiezers

De volgende klassenkiezers kunnen worden gebruikt om de container, suggestie en productelementen in de [!DNL popover].

* `.livesearch.popover-container`
* `.livesearch.view-all-footer`
* `.livesearch.suggestions-container`
* `.livesearch.suggestions-header`
* `.livesearch.suggestion`
* `.livesearch.products-container`
* `.livesearch.product-result`
* `.livesearch.product-name`
* `.livesearch.product-price`

### Containerklassekiezers

`.livesearch.popover-container`

![[!DNL Popover] container](assets/livesearch-popover-container.png)

`.livesearch.view-all-footer`

![Alle voetteksten weergeven](assets/livesearch-view-all-footer.png)

### Kiezers voor de klasse Suggestie

`.livesearch.suggestions-container`
![Container met suggesties](assets/livesearch-suggestions-container.png)

`.livesearch.suggestions-header`
![Koptekst van suggesties](assets/livesearch-suggestions-header.png)

`.livesearch.suggestion`
![Suggestie](assets/livesearch-suggestion.png)

### Kiezers voor productklassen

`.livesearch.products-container`
![Productcontainer](assets/livesearch-product-container.png)

`.livesearch.product-result`
![Resultaat van product](assets/livesearch-product-result.png)

`.livesearch.product-name`
![Productnaam](assets/livesearch-product-name.png)

`.livesearch.product-price`
![Productprijs](assets/livesearch-product-price.png)

## Werken met een gewijzigd thema {#working-with-modified-theme}

De [!DNL storefront popover] kan worden gebruikt met een aangepaste [thema](https://devdocs.magento.com/guides/v2.3/frontend-dev-guide/themes/theme-overview.html) dat de vereiste bestanden overneemt van *Luminantie*. De `top.search` in de `header-wrapper` van de `Magento_Search` mag niet worden gewijzigd.

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

Om het [!DNL popover] en herstel de standaard [Snel zoeken](https://docs.magento.com/user-guide/catalog/search-quick.html) voert u de volgende opdracht in:

```bash
bin/magento module:disable Magento_LiveSearchStorefrontPopover
```
