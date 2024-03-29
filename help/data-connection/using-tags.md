---
title: Gegevens voor handel verzamelen met Adobe Experience Platform-tags
description: Leer hoe u gegevens over handel kunt verzamelen met Adobe Experience Platform-tags.
exl-id: 852fc7d2-5a5f-4b09-8949-e9607a928b44
role: Admin, Developer
feature: Personalization, Integration
source-git-commit: 71e73b900db024eee6e7e11cbddbabf332acf70a
workflow-type: tm+mt
source-wordcount: '2635'
ht-degree: 0%

---

# Gegevens voor handel verzamelen met Adobe Experience Platform-tags

Terwijl u [!DNL Data Connection] uitbreiding om te publiceren en aan storefront gebeurtenissen in te tekenen, zouden sommige handelaren reeds een oplossing van de gegevensinzameling kunnen gebruiken, zoals [Adobe Experience Platform-tags](https://experienceleague.adobe.com/docs/platform-learn/data-collection/tags/create-a-property.html). Voor deze handelaren biedt Adobe Commerce in het dialoogvenster [!DNL Data Connection] extensie die gebruikmaakt van de Adobe Commerce Event SDK.

![[!DNL Data Connection] Extensiegegevensstroom](assets/tags-data-flow.png)
_[!DNL Data Connection]Gegevensstroom van extensies met labels_

In dit onderwerp, zult u leren hoe te om de waarden in kaart te brengen van de storefront gebeurtenis die door worden verstrekt [!DNL Data Connection] een extensie voor de Adobe Experience Platform-tagoplossing die u al gebruikt.

## Gebeurtenisgegevens verzamelen vanuit Adobe Commerce

Gegevens over Commerce-gebeurtenissen verzamelen:

- Installeer de [Adobe Commerce Events SDK](https://github.com/adobe/commerce-events/tree/main/packages/storefront-events-sdk). Voor PHP-winkels raadpleegt u de [installeren](install.md) onderwerp. Voor PWA Studio-winkels raadpleegt u de [Hulplijn PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/).

  >[!NOTE]
  >
  > Do **niet** [vormen](connect-data.md) de organisatie-id en de gegevensstroom-id.

## Opslaggegevens voor Handel toewijzen aan Adobe Experience Platform

Als u de gegevens van de Commerce-winkel wilt toewijzen aan Adobe Experience Platform, configureert en installeert u het volgende binnen Adobe Experience Platform-tags:

1. [Een eigenschap voor een tag instellen](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html) in Adobe Experience Platform Data Collection.

1. Onder **Authoring**, selecteert u **Extensies** en installeer en vorm de volgende uitbreidingen:

   - [Gegevenslaag client-Adobe](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/client-data-layer/overview.html)

   - [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)

1. [Tag voor publiceren](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) naar uw ontwikkelomgeving.

1. Volg de **Gebeurtenistoewijzing** de stappen hieronder om gegevenselementen en regels voor specifieke gebeurtenissen te vormen.

### Gebeurtenistoewijzing

Omdat gegevensverzameling met tags verschilt van het gebruik van de Adobe Commerce Event SDK, is het belangrijk dat u de equivalente termen begrijpt die in beide frameworks worden gebruikt.

| Adobe Experience Platform-tagterm | Adobe Commerce Event SDK term |
|---|---|
| _gegevenselementen_ | context |
| _regels_ | event |
|  | _algemene voorwaarden_ - gebeurtenislisteners (van ACDL)<br><br>_handelingen voor regel_ - gebeurtenishandlers (verzenden naar Adobe Experience Platform) |

Wanneer u de gegevenselementen en regels in Adobe Experience Platform-tags bijwerkt met Adobe Commerce-specifieke gebeurtenisgegevens, worden een aantal veelvoorkomende stappen uitgevoerd.

Laten we bijvoorbeeld de Adobe Commerce toevoegen `signOut` -gebeurtenis naar Adobe Experience Platform-tags. In de onderstaande stappen wordt beschreven, behalve voor specifieke waarden die u instelt, hoe u kunt toevoegen [gegevenselementen](https://experienceleague.adobe.com/docs/experience-platform/collection/e2e.html#data-element) en [regels](https://experienceleague.adobe.com/docs/experience-platform/collection/e2e.html#create-a-rule), die van toepassing zijn op alle Adobe Commerce-gebeurtenissen die u aan tags toevoegt.

1. Een gegevenselement maken:

   ![Nieuw gegevenselement maken](assets/create-new-data-elements.png)
   _Nieuw gegevenselement maken_

1. Set **Naam** tot `sign out`.

1. Set **Extensie** tot `Adobe Experience Platform Web SDK`.

1. Set **Type gegevenselement** tot `XDM object`.

1. Selecteer de **Sandbox** en **Schema** die u wilt bijwerken.

1. Onder **userAccount** > **afmelden**, stelt u de **value** in **Afmelden bij bezoeker** tot `1`.

   ![Waarde voor afmelden bijwerken](assets/signout-value.png)
   _Waarde voor afmelden bijwerken_

1. Selecteren **Opslaan**.

1. Een regel maken:

   ![Nieuwe regel maken](assets/create-new-rule.png)
   _Nieuwe regel maken_

1. Selecteren **Toevoegen** krachtens **EVENTS**.

1. Set **Extensie** tot `Adobe Client Data Layer`.

1. Set **Type gebeurtenis** tot `Data Pushed`.

1. Selecteren **Specifieke gebeurtenis** en stelt de **Gebeurtenis/sleutel waarvoor u zich wilt registreren** tot `sign-out`.

1. Selecteren **Wijzigingen behouden** om de nieuwe regel op te slaan.

1. Voeg een handeling toe.

1. Set **Extensie** tot `Adobe Experience Platform Web SDK`.

1. Set **Type handeling** tot `Send Event`.

1. Set **Instantie** tot `Alloy`.

1. Set **Type** tot `userAccount.logout`.

1. Set **XDM-gegevens** tot `%sign out%`.

1. Klikken **Opslaan**.

   U hebt een gegevenselement in uw schema gemaakt voor de `signOut` uit Adobe Commerce. U hebt ook een regel gemaakt met een specifieke actie die moet worden uitgevoerd wanneer die gebeurtenis vanuit de Adobe Commerce-storefront wordt geactiveerd.

Herhaal bovenstaande stappen in tags voor elk van de Adobe Commerce-gebeurtenissen die hieronder worden beschreven.

## Beschikbare gebeurtenissen

Wijs voor elk van de volgende gebeurtenissen de Adobe Commerce-gebeurtenissen toe aan uw XDM door de bovenstaande stappen uit te voeren.

- [` signOut`](#signout)
- [` signIn`](#signin)
- [` createAccount`](#createaccount)
- [` editAccount`](#editaccount)
- [` pageView`](#pageview)
- [` productView`](#productview)
- [` searchRequestSent`](#searchrequestsent)
- [` searchResponseReceived`](#searchresponsereceived)
- [` addToCart`](#addtocart)
- [` openCart`](#opencart)
- [` viewCart`](#viewcart)
- [` removeFromCart`](#removefromcart)
- [&quot;initilCheckout&quot;](#initiatecheckout)
- [` placeOrder`](#placeorder)

### signOut

Wordt geactiveerd wanneer een winkelier zich afmeldt.

#### Gegevenselementen

Maak het volgende gegevenselement:

1. Afmelden:

   - **Naam**: `Sign out`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `userAccount` > `logout`
   - **Afmelden bij bezoeker**: **Waarde** = `1`

#### Regels 

- **Naam**: `Sign out`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `sign-out`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `userAccount.logout`
- **XDM-gegevens**: `%sign-out%`

### signIn

Wordt geactiveerd wanneer een winkelier zich aanmeldt.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. E-mailadres account:

   - **Naam**: `account email`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.emailAddress`

1. Accounttype:

   - **Naam**: `account type`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.accountType`

1. Account-id:

   - **Naam**: `account id`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad***: `accountContext.accountId`

1. Aanmelden:

   - **Naam**: `sign in`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `person` > `accountID`
   - **Account-id**: **Waarde** = `%account id%`
   - **Veldgroep**: `person` > `accountType`
   - **Accounttype**: **Waarde** = `%account type%`
   - **Veldgroep**: `person` > `personalEmailID`
   - **Persoonlijk e-mailadres**: **Waarde** = `%account email%`
   - **Veldgroep**: `personalEmail` > `address`
   - **Adres**: **Waarde** = `%account email%`
   - **Veldgroep**: `userAccount` > `login`
   - **Aanmelden bij bezoeker**: **Waarde** = `1`

#### Regels 

- **Naam**: `sign in`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `sign-in`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `userAccount.login`
- **XDM-gegevens**: `%sign in%`

### createAccount

Wordt geactiveerd wanneer een winkelier een account probeert te maken.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. E-mailadres account:

   - **Naam**: `account email`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.emailAddress`

1. Accounttype:

   - **Naam**: `account type`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.accountType`

1. Account-id:

   - **Naam**: `account id`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.accountId`

1. Account maken:

   - **Naam**: `Create account`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `person` > `accountID`
   - **Account-id**: **Waarde** = `%account id%`
   - **Veldgroep**: `person` > `accountType`
   - **Accounttype**: **Waarde** = `%account type%`
   - **Veldgroep**: `person` > `personalEmailID`
   - **Persoonlijk e-mailadres**: **Waarde** = `%account email%`
   - **Veldgroep**: `personalEmail` > `address`
   - **Adres**: **Waarde** = `%account email%`
   - **Veldgroep**: `userAccount` > `createProfile`
   - **Accountprofiel maken**: **Waarde** = `1`

#### Regels 

- **Naam**: `Create account`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `create-account`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `userAccount.createProfile`
- **XDM-gegevens**: `%create account%`

### editAccount

Wordt geactiveerd wanneer een gebruiker een account probeert te bewerken.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. E-mailadres account:

   - **Naam**: `account email`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.emailAddress`

1. Accounttype:

   - **Naam**: `account type`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.accountType`

1. Account-id:

   - **Naam**: `account id`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.accountId`

1. Account bewerken:

   - **Naam**: `Edit account`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `person` > `accountID`
   - **Account-id**: **Waarde** = `%account id%`
   - **Veldgroep**: `person` > `accountType`
   - **Accounttype**: **Waarde** = `%account type%`
   - **Veldgroep**: `person` > `personalEmailID`
   - **Persoonlijk e-mailadres**: **Waarde** = `%account email%`
   - **Veldgroep**: `personalEmail` > `address`
   - **Adres**: **Waarde** = `%account email%`
   - **Veldgroep**: `userAccount` > `updateProfile`
   - **Accountprofiel maken**: **Waarde** = `1`

#### Regels

- **Naam**: `Edit account`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `edit-account`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `userAccount.updateProfile`
- **XDM-gegevens**: `%edit account%`

### pageView

Wordt geactiveerd wanneer een pagina wordt geladen.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Paginanaam:

   - **Naam**: `page name`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `pageContext.pageName`

#### Regels 

- **Naam**: `page view`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `page-view`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `web.webPageDetails.pageViews`
- **XDM-gegevens**: `%page view%`

### productView

Wordt geactiveerd wanneer een productpagina wordt geladen.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Productnaam:

   - **Naam**: `product name`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.name`

1. Product SKU:

   - **Naam**: `product sku`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.sku`

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

1. Productvaluta:

   - **Naam**: `product currency`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.currencyCode`

1. Valuta:

   - **Naam**: `currency code`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('product currency') || _satellite.getVar('storefront').storeViewCurrencyCode
   ```

1. Speciale prijs:

   - **Naam**: `special price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.specialPrice`

1. Gewone prijs:

   - **Naam**: `regular price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.regularPrice`

1. Productprijs:

   - **Naam**: `product price`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('product regular price') || _satellite.getVar('product special price')
   ```

1. Productweergave:

   - **Naam**: `product view`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Selecteren **Afzonderlijke items opgeven** en klik op de knop **Item toevoegen** knop. Omdat deze weergave voor een PDP is, kunt u één item vullen.
   - **Veldgroep**: `productListItems` > `name`
   - **Naam**: **Waarde** = `%product name%`
   - **Veldgroep**: `productListItems` > `SKU`
   - **SKU**: **Waarde** = `%product sku%`
   - **Veldgroep**: `productListItems` > `priceTotal`
   - **Prijstotaal**: **Waarde** = `%product price%`
   - **Veldgroep**: `productListItems` > `currencyCode`
   - **Valutacode**: **Waarde** = `%currency code%`
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Veldgroep**: `commerce` > `productViews` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `product view`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `product-page-view`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.productViews`
- **XDM-gegevens**: `%product view%`

### searchRequestSent

Wordt geactiveerd door gebeurtenissen in het pop-upvenster &quot;Zoeken terwijl u typt&quot; en door gebeurtenissen op pagina&#39;s met zoekresultaten.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Zoeken in invoer

   - **Naam**: `search input`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `searchInputContext.units[0]`

1. Invoeruitdrukking zoeken

   - **Naam**: `search input phrase`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('search input').phrase;
   ```

1. Invoersortering zoeken

   - **Naam**: `search input sort`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const searchInput = _satellite.getVar('search input');
   const sortFromInput = searchInput ? searchInput.sort : [];
   const sort = sortFromInput.map((searchSort) => {
       return {
           attribute: searchSort.attribute,
           order: searchSort.direction,
       };
   });
   return sort;
   ```

1. Invoerfilters zoeken

   - **Naam**: `search input filters`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const searchInput = _satellite.getVar('search input');
   const filtersFromInput = searchInput ? searchInput.filter : [];
   const filters = filtersFromInput.map(
       (searchFilter) => {
           let value = [];
           let isRange = false;
           if (searchFilter.eq) {
               value.push(searchFilter.eq);
           } else if (searchFilter.in) {
               value = searchFilter.in;
           } else if (searchFilter.range) {
               isRange = true;
               value.push(String(searchFilter.range.from));
               value.push(String(searchFilter.range.to));
           }
           return {
               attribute: searchFilter.attribute,
               value,
               isRange,
           };
       }
   );
   
   return filters;
   ```

1. Zoekverzoek:

   - **Naam**: `search request`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `siteSearch` > `phrase`
   - **value**: Nog niet beschikbaar
   - **Veldgroep**: `siteSearch` > `sort`. Selecteren **Geheel object opgeven**.
   - **Veldgroep**: `siteSearch` > `filter`. Selecteren **Geheel object opgeven**.
   - **Veldgroep**: `searchRequest` > `id`
   - **Unieke id**: **Waarde** = `%search request ID%`
   - **Veldgroep**: `searchRequest` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `search request sent`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `search-request-sent`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `searchRequest`
- **XDM-gegevens**: `%search request%`

### searchResponseReceived

Wordt geactiveerd wanneer Live zoeken resultaten oplevert voor de popover- of zoekresultatenpagina &quot;Zoeken zoals u typt&quot;.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Zoekresultaten:

   - **Naam**: `search results`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `searchResultsContext.units[0]`

1. Zoekresultaat aantal producten:

   - **Naam**: `search result number of products`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('search result').products.length;
   ```

1. Producten zoekresultaten:

   - **Naam**: `search result products`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const searchResult = _satellite.getVar('search result');
   const productsFromResult = searchResult.products ? searchResult.products : [];
   const products = productsFromResult.map(
       (product) => {
           return { SKU: product.sku, name: product.name };
       }
   );
   return products;
   ```

1. Suggesties voor zoekresultaten:

   - **Naam**: `search result products`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const searchResult = _satellite.getVar('search result');
   const suggestionsFromResult = searchResult.suggestions ? searchResult.suggestions : [];
   const suggestions = suggestionsFromResult.map((suggestion) => suggestion.suggestion);
   return suggestions;
   ```

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

1. Zoeken in reactie:

   - **Naam**: `search response`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `siteSearch` > `suggestions`. Selecteren **Geheel object opgeven**.
   - **Gegevenselement**: `%search result suggestions%`
   - **Veldgroep**: `siteSearch` > `numberOfResults`
   - **value**: `%search result number of products%`
   - **Veldgroep**: `productListItems`. Selecteren **Geheel object opgeven**.
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Gegevenselement**: `%search result products%`
   - **Veldgroep**: `searchResponse` > `id`
   - **Unieke id**: **Waarde** = `%search response ID%`
   - **Veldgroep**: `searchResponse` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `search response received`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `search-response-received`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `searchResponse`
- **XDM-gegevens**: `%search response%`

### addToCart

Wordt geactiveerd wanneer een product aan een winkelwagen wordt toegevoegd of telkens wanneer de hoeveelheid van een product in het winkelwagentje wordt verhoogd.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Productnaam:

   - **Naam**: `product name`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.name`

1. Productsku:

   - **Naam**: `product sku`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.sku`

1. Valuta:

   - **Naam**: `currency code`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.currencyCode`

1. Speciale prijs product:

   - **Naam**: `product special price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.specialPrice`

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

1. Gewone prijs product:

   - **Naam**: `product regular price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.regularPrice`

1. Productprijs:

   - **Naam**: `product price`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('product regular price') || _satellite.getVar('product special price') 
   ```

1. Kar:

   - **Naam**: `cart`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `shoppingCartContext`

1. Kart-id:

   - **Naam**: `cart id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('cart').id
   ```

1. Toevoegen aan winkelwagen:

   - **Naam**: `add to cart`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Selecteren **Afzonderlijke items opgeven** en klik op de knop **Item toevoegen** knop. Omdat deze weergave voor een PDP is, kunt u één item vullen.
   - **Veldgroep**: `productListItems` > `name`
   - **Naam**: **Waarde** = `%product name%`
   - **Veldgroep**: `productListItems` > `SKU`
   - **SKU**: **Waarde** = `%product sku%`
   - **Veldgroep**: `productListItems` > `priceTotal`
   - **Prijstotaal**: **Waarde** = `%product price%`
   - **Veldgroep**: `productListItems` > `currencyCode`
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Valutacode**: **Waarde** = `%currency code%`
   - **Veldgroep**: `commerce` > `cart` > `cartID`
   - **Winkelwagentje**: **Waarde** = `%cart id%`
   - **Veldgroep**: `commerce` > `productListAdds` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `add to cart`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `add-to-cart`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.productListAdds`
- **XDM-gegevens**: `%add to cart%`

### openCart

Wordt geactiveerd wanneer een nieuw winkelwagentje wordt gemaakt, wat gebeurt wanneer een product aan een leeg winkelwagentje wordt toegevoegd.

#### Gegevenselementen

Maak het volgende gegevenselement:

1. Open kar:

   - **Naam**: `open cart`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `commerce` > `productListOpens` > `value`
   - **value**: **Waarde** = `1`
   - **Veldgroep**: `commerce` > `cart` > `cartID`
   - **Winkelwagentje**: **Waarde** = `%cart id%`
   - **Veldgroep**: `productListItems`. Voor `productListItems`, meerdere items kunnen vooraf worden berekend. Selecteren **productListItems** > **Volledige array opgeven**.

#### Regels 

- **Naam**: `open cart`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `open-cart`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.productListOpens`
- **XDM-gegevens**: `%open cart%`

### viewCart

Wordt geactiveerd wanneer een winkelwagenpagina wordt geladen.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Storefront:

   - **Naam**: `storefront`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `storefrontInstanceContext`

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

   1. Kar:

   - **Naam**: `cart`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `shoppingCartContext`

1. Kart-id:

   - **Naam**: `cart id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('cart').id
   ```

1. Objecten in de productlijst:

   - **Naam**: `product list items:`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const storefrontContext = _satellite.getVar('storefront');
   const cart = _satellite.getVar('cart');
   
   const returnList = [];
   cart.items.forEach(item => {
       const selectedOptions = [];
       item.configurableOptions?.forEach(option => {
           selectedOptions.push({
               attribute: option.optionLabel,
               value: option.valueLabel,
           });
       });
   
       const productListItem = {
           SKU: item.product.sku,
           name: item.product.name,
           quantity: item.quantity,
           priceTotal: item.prices.price.value * item.quantity,
           currencyCode: item.prices.price.currency ? item.prices.price.currency : storefrontContext.storeViewCurrencyCode,
           selectedOptions: selectedOptions,
       };
   
       returnList.push(productListItem);
   });
   return returnList;
   ```

1. Kaart weergeven:

   - **Naam**: `view cart`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Voor `productListItems`Er kunnen meerdere vooraf berekende items zijn. Selecteren **productListItems** > **Volledige array vullen**.
   - **Gegevenselement**: `%product list items%`
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Veldgroep**: `commerce` > `cart` > `cartID`
   - **Winkelwagentje**: **Waarde** = `%cart id%`
   - **Veldgroep**: `commerce` > `productListViews` > `value`
   - **value**: **Waarde** = `1`

#### Regels

- **Naam**: `view cart`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `shopping-cart-view`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.productListViews`
- **XDM-gegevens**: `%view cart%`

### removeFromCart

Wordt geactiveerd wanneer een product uit een winkelwagentje wordt verwijderd of telkens wanneer de hoeveelheid van een product in het winkelwagentje wordt verlaagd.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Productnaam:

   - **Naam**: `product name`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.name`

1. Productsku:

   - **Naam**: `product sku`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.sku`

1. Valuta:

   - **Naam**: `currency code`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.currencyCode`

1. Speciale prijs product:

   - **Naam**: `product special price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.specialPrice`

1. Gewone prijs product:

   - **Naam**: `product regular price`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.pricing.regularPrice`

1. Productprijs:

   - **Naam**: `product price`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('product regular price') || _satellite.getVar('product special price') 
   ```

1. Kar:

   - **Naam**: `cart`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `shoppingCartContext`

1. Kart-id:

   - **Naam**: `cart id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('cart').id
   ```

1. Verwijderen uit winkelwagen:

   - **Naam**: `remove from cart`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Selecteren **Afzonderlijke items opgeven** en klik op de knop **Item toevoegen** knop. Omdat deze weergave voor een PDP is, kunt u één item vullen.
   - **Veldgroep**: `productListItems` > `name`
   - **Naam**: **Waarde** = `%product name%`
   - **Veldgroep**: `productListItems` > `SKU`
   - **SKU**: **Waarde** = `%product sku%`
   - **Veldgroep**: `productListItems` > `priceTotal`
   - **Prijstotaal**: **Waarde** = `%product price%`
   - **Veldgroep**: `productListItems` > `currencyCode`
   - **Valutacode**: **Waarde** = `%currency code%`
   - **Veldgroep**: `commerce` > `cart` > `cartID`
   - **Winkelwagentje**: **Waarde** = `%cart id%`
   - **Veldgroep**: `commerce` > `productListRemovals` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `remove from cart`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `remove-from-cart`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.productListRemovals`
- **XDM-gegevens**: `%remove from cart%`

### initikout

Wordt geactiveerd wanneer de gebruiker op een uitcheckknop klikt.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. Storefront:

   - **Naam**: `storefront`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `storefrontInstanceContext`

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

1. Kar:

   - **Naam**: `cart`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `shoppingCartContext`

1. Kart-id:

   - **Naam**: `cart id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('cart').id
   ```

1. Objecten in de productlijst:

   - **Naam**: `product list items`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const storefrontContext = _satellite.getVar('storefront');
   const cart = _satellite.getVar('cart');
   
   const returnList = [];
   cart.items.forEach(item => {
       const selectedOptions = [];
       item.configurableOptions?.forEach(option => {
           selectedOptions.push({
               attribute: option.optionLabel,
               value: option.valueLabel,
           });
       });
   
       const productListItem = {
           SKU: item.product.sku,
           name: item.product.name,
           quantity: item.quantity,
           priceTotal: item.prices.price.value * item.quantity,
           currencyCode: item.prices.price.currency ? item.prices.price.currency : storefrontContext.storeViewCurrencyCode,
           selectedOptions: selectedOptions,
       };
   
       returnList.push(productListItem);
   });
   return returnList;
   ```

1. Afhandeling starten:

   - **Naam**: `initiate checkout`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Voor `productListItems`Er kunnen meerdere vooraf berekende items zijn. Selecteren **productListItems** > **Volledige array vullen**.
   - **Gegevenselement**: `%product list items%`
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Veldgroep**: `commerce` > `cart` > `cartID`
   - **Winkelwagentje**: **Waarde** = `%cart id%`
   - **Veldgroep**: `commerce` > `checkouts` > `value`
   - **value**: **Waarde** = `1`

#### Regels 

- **Naam**: `initiate checkout`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `initiate-checkout`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.checkouts`
- **XDM-gegevens**: `%initiate checkout%`

### placeOrder

Wordt geactiveerd wanneer de gebruiker een bestelling plaatst.

#### Gegevenselementen

Maak de volgende gegevenselementen:

1. E-mailadres account:

   - **Naam**: `account email`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `accountContext.emailAddress`

1. Storefront:

   - **Naam**: `storefront`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `storefrontInstanceContext`

1. URL van productafbeelding:

   - **Naam**: `product image`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `productContext.mainImageUrl`

1. Kar:

   - **Naam**: `cart`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `shoppingCartContext`

1. Kart-id:

   - **Naam**: `cart id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('cart').id
   ```

1. Volgorde:

   - **Naam**: `order`
   - **Extensie**: `Adobe Client Data Layer`
   - **Type gegevenselement**: `Data Layer Computed State`
   - **[Optioneel] pad**: `orderContext`

1. Handelsorder:

   - **Naam**: `commerce order`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const order = _satellite.getVar('order');
   const storefront = _satellite.getVar('storefront');
   
   if (order.payments && order.payments.length) {
       payments = order.payments.map(payment => {
           return {
               paymentAmount: payment.total,
               paymentType: payment.paymentMethodCode,
               transactionID: order.orderId.toString(),
           };
       });
   } else {
       payments = [
           {
               paymentAmount: order.grandTotal,
               paymentType: order.paymentMethodCode,
               transactionID: order.orderId.toString(),
           },
       ];
   }
   
   return {
       purchaseID: order.orderId.toString(),
       currencyCode: storefront.storeViewCurrencyCode,
       payments,
   };
   ```

1. Verzending bestellen:

   - **Naam**: `order shipping`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const order = _satellite.getVar('order');
   return {
       shippingMethod: order.shipping.shippingMethod,
       shippingAmount: order.shipping.shippingAmount || 0,
   }
   ```

1. Promotie-id:

   - **Naam**: `promotion id`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   return _satellite.getVar('order').appliedCouponCode
   ```

1. Objecten in de productlijst:

   - **Naam**: `product list items`
   - **Extensie**: `Core`
   - **Type gegevenselement**: `Custom Code`
   - **Editor openen**:

   ```bash
   const storefrontContext = _satellite.getVar('storefront');
   const cart = _satellite.getVar('cart');
   
   const returnList = [];
   cart.items.forEach(item => {
       const selectedOptions = [];
       item.configurableOptions?.forEach(option => {
           selectedOptions.push({
               attribute: option.optionLabel,
               value: option.valueLabel,
           });
       });
   
       const productListItem = {
           SKU: item.product.sku,
           name: item.product.name,
           quantity: item.quantity,
           priceTotal: item.prices.price.value * item.quantity,
           currencyCode: item.prices.price.currency ? item.prices.price.currency : storefrontContext.storeViewCurrencyCode,
           selectedOptions: selectedOptions,
       };
   
       returnList.push(productListItem);
   });
   return returnList;
   ```

1. Plaatsingsvolgorde:

   - **Naam**: `place order`
   - **Extensie**: `Adobe Experience Platform Web SDK`
   - **Type gegevenselement**: `XDM object`
   - **Veldgroep**: `productListItems`. Voor `productListItems`Er kunnen meerdere vooraf berekende items zijn. Selecteren **productListItems** > **Volledige array vullen**.
   - **Gegevenselement**: `%product list items%`
   - **Veldgroep**: `productListItems` > `ProductImageUrl`
   - **ProductImageUrl**: **Waarde** = `%product image%`
   - **Veldgroep**: `commerce` > `order`
   - **Unieke id**: **Waarde** = `%commerce order%`
   - **Veldgroep**: `commerce` > `shipping`
   - **Unieke id**: **Waarde** = `%order shipping%`
   - **Veldgroep**: `commerce` > `promotionID`
   - **Promotie-id**: **Waarde** = `%promotion id%`
   - **Veldgroep**: `commerce` > `purchases` > `value`
   - **value**: **Waarde** = `1`
   - **Persoonlijk e-mailadres**: **Waarde** = `%account email%`
   - **Veldgroep**: `personalEmail` > `address`
   - **Adres**: **Waarde** = `%account email%`

#### Regels 

- **Naam**: `place order`
- **Extensie**: `Adobe Client Data Layer`
- **Type gebeurtenis**: `Data Pushed`
- **Specifieke gebeurtenis**: `place-order`

##### Handelingen

- **Extensie**: `Adobe Experience Platform Web SDK`
- **Type handeling**: `Send event`
- **Type**: `commerce.order`
- **XDM-gegevens**: `%place order%`

## Identiteit instellen in storefront-gebeurtenissen

Storefront-gebeurtenissen bevatten profielgegevens op basis van de `personalEmail` (voor accountgebeurtenissen) en `identityMap` (voor alle andere storefront-gebeurtenissen) velden. De [!DNL Data Connection] wordt op basis van deze twee velden profielen gemaakt en samengevoegd. Voor elk veld zijn echter verschillende stappen nodig om profielen te maken:

>[!NOTE]
>
>Als u een vorige instelling hebt die afhankelijk is van verschillende velden, kunt u deze instellingen blijven gebruiken.

- `personalEmail` - Alleen van toepassing op accountgebeurtenissen. Volg de stappen, regels en acties die worden beschreven [boven](#createaccount)
- `identityMap` - Is van toepassing op alle andere storefront-gebeurtenissen. Zie het volgende voorbeeld.

### Voorbeeld

De volgende stappen tonen hoe te om een te vormen `pageView` gebeurtenis met `identityMap` in [!DNL Data Connection] extensie:

1. Gegevenselement configureren met aangepaste code voor ECID:

   ![Gegevenselement configureren met aangepaste code](assets/set-custom-code-ecid.png)
   _Gegevenselement configureren met aangepaste code_

1. Selecteren [!UICONTROL Open Editor] en voeg de volgende aangepaste code toe:

   ```javascript
   return alloy("getIdentity").then((result) => {
       var identityMap = {
           ECID: [
           {
               id: ecid,
               primary: true
           }
           ],
           email: [
           {
               id: email,
               primary: false
           }
           ]
       };
     _satelite.setVar("identityMap", identityMap);
   });
   ```

1. XDM-schema bijwerken met `identityMap` ingesteld als ECID:

   ![Identiteitskaart instellen als ECID](assets/identity-map-data-element.png)
   _Identiteitskaart instellen als ECID_

1. Bepaal regelacties die ECID terugwinnen:

   ![ECID ophalen](assets/rule-retrieve-ecid.png)
   _ECID ophalen_

## Identiteit instellen in back office-gebeurtenissen

In tegenstelling tot storefront-gebeurtenissen die ECID gebruiken om profielinformatie te identificeren en te koppelen, zijn de gegevens van de back office gebeurtenis gebaseerd op SaaS en daarom is geen ECID beschikbaar. Voor backoffice-gebeurtenissen moet u e-mail gebruiken om kopers op unieke wijze te identificeren. In deze sectie leert u hoe u via e-mail gegevens van kantoorgebeurtenissen kunt koppelen aan een ECID.

1. Maak een identiteitskaartelement.

   ![Identiteitskaart van het achterkantoor](assets/custom-code-backoffice.png)
   _Identiteitskaart voor back-office maken_

1. Selecteren [!UICONTROL Open Editor] en voeg de volgende aangepaste code toe:

```javascript
const IdentityMap = {
  "ECID": [
    {
      id:  _satellite.getVar('ECID'),
      primary: true,
    },
  ],
};
 
if (_satellite.getVar('account email')) {
    IdentityMap.email = [
        {
            id: _satellite.getVar('account email'),
            primary: false,
        },
    ];
}
return IdentityMap;
```

1. Dit nieuwe element toevoegen aan elk `identityMap` veld.

   ![Elke identityMap bijwerken](assets/add-element-back-office.png)
   _Elke identityMap bijwerken_

## Vaststelling van de toestemming

Wanneer u de [!DNL Data Connection] in Adobe Commerce is de toestemming voor gegevensverzameling standaard ingeschakeld. Uitschakelen wordt beheerd via de [`mg_dnt` koekje](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html). U kunt de hier beschreven stappen volgen als u verkiest te gebruiken `mg_dnt` om de toestemming te beheren. De [Adobe Experience Platform Web SDK-documentatie](https://experienceleague.adobe.com/docs/experience-platform/edge/consent/supporting-consent.html) beschikt over verschillende aanvullende opties voor het beheer van de toestemming.

1. Een **Aangepaste kerncode** gegevenselement (`%do not track cookie%`) voor de `mg_dnt` cookie:

   ![Maken houdt geen gegevenselement bij](assets/element-dnt-cookie.png)
   _Maken houdt geen gegevenselement bij_

1. Een **Aangepaste kerncode** gegevenselement (`%consent%`) die wordt geretourneerd `out` als cookie is ingesteld en `in` anders:

   ![Gegevenselement voor toestemming maken](assets/element-consent-dnt-cookie.png)
   _Gegevenselement voor toestemming maken_

1. Adobe Experience Platform Web SDK Extension configureren met `%consent%` gegevenselement:

   ![SDK bijwerken met toestemming](assets/config-sdk-consent.png)
   _SDK bijwerken met toestemming_

## Waarschuwingen

- Als u geen stappen uitvoert om het verzamelen van Experience Platforms uit te schakelen, worden gebeurtenissen dubbel geteld
- Het niet instellen van toewijzingen/gebeurtenissen zoals beschreven in dit onderwerp kan gevolgen hebben voor Adobe Analytics-borden
- U kunt Target niet instellen via de [!DNL Data Connection] extensie als gegevensverzameling is uitgeschakeld
