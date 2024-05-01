---
title: Widget pagina met productaanbiedingen
description: Het inschakelen en opmaken van de [!DNL Live Search Product Listing Page Widget]
exl-id: f7346a06-a8c7-4a33-8437-ea4f61d9281f
source-git-commit: 1e0baa20defe4e50bd9e45c03ff7c5f758b24e5d
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Widget pagina met productaanbiedingen

De [!DNL Live Search Product Listing Page Widget] (PLP) gebruikt het Commerce Services-platform om een pagina met producten met een presterende, doorzoekbare en facetbare aanbieding te maken. In dit onderwerp wordt beschreven hoe u de PLP-widget kunt inschakelen en opmaken.

## De PLP-widget inschakelen

Wanneer de [!DNL Live Search] de dienst wordt geïnstalleerd, wordt de standaardonderzoeksfunctionaliteit omgezet in [!DNL Live Search] automatisch.

De [!DNL Live Search] PLP-widget is standaard ingeschakeld voor nieuwe installaties. Als u een upgrade uitvoert [!DNL Live Search] en de PLP-widget al is uitgeschakeld, zal dit zo blijven.

>[!IMPORTANT]
>
>Wanneer de [!DNL Live Search Product Listing Page Widget] is ingeschakeld, kan de richting van de sorteervolgorde op een pagina met productlijsten niet worden gewijzigd.

## De PLP-widget uitschakelen

De PLP-widget uitschakelen:

1. Ga naar **Winkels** > Instellingen > **Configuratie** > **[!DNL Live Search]** > **Storefront-functies** en instellen **Widgets productlijst inschakelen** naar &quot;Nee&quot;.
1. Selecteren **Config opslaan** om de instelling op te slaan.

## Widget-functies

De PLP-widget biedt een aantal functies die op een doorzoekbare productpagina worden verwacht. Deze omvatten:

* Filteren op kenmerken
* Ondersteuning voor kleurstalen
* Toevoegen aan winkelwagentje
* Ondersteuning voor meerdere talen
* Prijsschuifregelaars

Zie voor informatie over hoe u de PLP-widget kunt aanpassen aan de bovenstaande functies `storefront-product-listing-page` Lees mij in het volgende [repo](https://github.com/adobe/storefront-product-listing-page/).

## Voorbeeld van stijlen

U kunt het uiterlijk van de PLP-widget aanpassen aan uw site met [CSS](https://developer.adobe.com/commerce/frontend-core/guide/css/).

>[!NOTE]
>
>Elementen met aangepaste klassen binnen een Adobe Commerce-thema worden niet overgeërfd. Deze elementen moeten door hun specifieke klasse worden gericht om de douaneklassen aan te passen; de primaire actieklassen zullen niet aan een widgetknoop werken.
>Algemene doelelementen in de CSS worden overgeërfd; `button` is van toepassing op widgetknoppen.

De gemarkeerde div&#39;s bevatten de doelklasse `ds-sdk-product-item__product-name`.

![Paginering](assets/plp-css-example.png)

Pas de productnaam aan door een regel toe te voegen die in hoofdletters wordt geschreven.

```css
.ds-sdk-product-item__product-name {
 text-transform: uppercase;
}
```

![Paginering](assets/plp-css-example-after.png)

## CSS-klassen

### Productlijst

* `.ds-sdk-product-list`: Div buiten
* `.ds-sdk-product-list__grid`: div binnen

![Paginering](assets/plp-css-product-list.png)

#### Paginering van de productlijst

* `.ds-plp-pagination`

![Paginering](assets/plp-css-pagination.png)

* `.ds-plp-pagination_item`

![Pagineringsitem](assets/plp-css-pagination-item.png)

* `.ds-plp-pagination_item--current`

![Huidig item pagineren](assets/plp-css-pagination-item-current.png)

### Widgets

* `.ds-widgets`: Div buiten
* `.ds-widgets__actions`: binnenste div aan linkerkant
* `.ds-widgets__results`: Div aan rechterkant binnenste div

![Resultaten van widget](assets/plp-css-widgets.png)

### Vervolgkeuzelijst sorteren

* `.ds-sdk-sort-dropdown`

![Vervolgkeuzelijst sorteren](assets/plp-css-dropdown.png)

* `.ds-sdk-sort-dropdown__button`

![Knop Vervolgkeuzelijst](assets/plp-css-dropdown-button.png)

* `.ds-sdk-sort-dropdown__items`

![Vervolgkeuzelijsten](assets/plp-css-dropdown-items.png)

* `.ds-sdk-sort-dropdown__items--item`

![Vervolgitem](assets/plp-css-dropdown-item.png)

* `.ds-sdk-sort-dropdown__items--item-selected`

![Geselecteerd item neerzetten](assets/plp-css-dropdown-selected.png)

* `.ds-sdk-sort-dropdown__items--item-active`

![Actieve selectie verslepen](assets/plp-css-dropdown-active.png)

### Facetten

* `.ds-plp-facets`
* `.ds-plp-facets__header`
* `.ds-plp-facets__header_title`
* `.ds-plp-facets__header__clear-all`

![Titel van koptekst met facetten](assets/plp-css-facets-title-clear.png){width="350"}

* `.ds-plp-facets__pills`
* `.ds-sdk-pill`

![Vullingen met facetten](assets/plp-css-facets-pill.png){width="350"}

* `.ds-sdk-pill__label`
* `.ds-sdk-pill__cta`

![Facets, label](assets/plp-css-pill-label-cta.png){width="350"}

* `.ds-plp-facets__list`

![Lijst met gezichten](assets/plp-css-facets-list.png){width="350"}

* `.ds-sdk-input`
* `.ds-sdk-input__label`
* `.ds-sdk-product-item__product-swatch-group`
* `ds-sdk-product-item__product-swatch-item`
* `.ds-sdk-input_fieldset_show-more`

![Invoer](assets/plp-css-sdk-input.png)

* `.ds-sdk-labelled-input`

![Gelabelde invoer](assets/plp-css-labelled-input.png)

* `.ds-sdk-labelled-input__input`
* `.ds-sdk-labelled-input__label`

![Invoerlabel](assets/plp-css-labelled-input-label.png)

### Product-item

* `.ds-sdk-product-item`
* `.ds-sdk-product-item__image`
* `.ds-sdk-product-item__product-name`
* `.ds-sdk-product-item__product-options`
* `.ds-sdk-product-price`
   * `.ds-sdk-product-price--no-discount`
   * `.ds-sdk-product-price--grouped`
   * `.ds-sdk-product-price--bundle`
   * `.ds-sdk-product-price--discount`

![Product](assets/plp-css-product.png)

### Laden

* `.ds-sdk-loading`
* `.ds-sdk-loading__spinner`
* `.ds-sdk-loading__spinner-label`

![Indicator laden](assets/plp-css-loading.png)
