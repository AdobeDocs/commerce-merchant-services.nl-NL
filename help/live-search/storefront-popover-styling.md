---
title: "Stijlen [!DNL Popover] Elementen"
description: "Technische opmerkingen over het aanpassen van de [!DNL Live Search storefront popover]"
exl-id: 033049f2-976e-4299-b026-333ac4b481a3
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '203'
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

Raadpleeg voor meer informatie over opmaakelementen voor winkelobjecten de [Cascading Style Sheets (CSS)](https://developer.adobe.com/commerce/frontend-core/guide/css/) in de [Frontend Developer Guide](https://developer.adobe.com/commerce/frontend-core/guide/).

## Klasse-kiezers

De volgende klassenkiezers kunnen worden gebruikt om de container- en productelementen in de [!DNL popover].

* `.livesearch.popover-container`
* `.livesearch.view-all-footer`
* `.livesearch.products-container`
* `.livesearch.product-result`
* `.livesearch.product-name`
* `.livesearch.product-price`

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

## Werken met een gewijzigd thema {#working-with-modified-theme}

De [!DNL storefront popover] kan worden gebruikt met een aangepaste [thema](https://developer.adobe.com/commerce/frontend-core/guide/themes/) dat de vereiste bestanden overneemt van *Luminantie*. De `top.search` in de `header-wrapper` van de `Magento_Search` mag niet worden gewijzigd.

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
