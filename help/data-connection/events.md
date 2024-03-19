---
title: Gedragsgebeurtenissen
description: Leer welke gegevens elke gedraggebeurtenis vastlegt.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
role: Admin, Developer
feature: Personalization, Integration, Eventing
source-git-commit: ace61fa579404962a9ca3eb97f61ed50bc43db52
workflow-type: tm+mt
source-wordcount: '4516'
ht-degree: 0%

---

# [!DNL Data Connection] Gedragsgebeurtenissen

De volgende lijst bevat de gedragsgebeurtenissen van de Handel die beschikbaar zijn wanneer u de [!DNL Data Connection] extensie. De gegevens die deze gebeurtenissen verzamelen, worden naar de Adobe Experience Platform verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

Naast de gegevens die door de volgende gebeurtenissen worden verzameld, wordt ook [overige gegevens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) verstrekt door de Adobe Experience Platform Web SDK.

De gedragsgebeurtenissen verzamelen geanonimiseerde gedragsgegevens van uw kopers wanneer ze door uw site bladeren. U kunt de gegevens die deze gebeurtenissen verzamelen gebruiken om promoties en campagnes te maken voor een specifieke groep kopers.

>[!NOTE]
>
>Alle gedragsgebeurtenissen omvatten de [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) veld, dat het e-mailadres van de verkoper, indien beschikbaar, en de ECID bevat.

## Gebeurtenissen van Storefront

De gebeurtenissen van Storefront vangen gegevens van de interactie van kopers op de plaats en omvatten gebeurtenissen zoals [`addToCart`](#addtocart), [`pageView`](#pageview), [`createAccount`](#createaccount), [`editAccount`](#editaccount), [`startCheckout`](#startcheckout), [`completeCheckout`](#completecheckout), [`signIn`](#signin), [`signOut`](#signout), enzovoort. De gebeurtenissen van het winkelfront zijn op eenvoudige en configureerbare slechts producten van toepassing.

### addToCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een product aan het winkelwagentje wordt toegevoegd of wanneer de hoeveelheid van een product in het winkelwagentje wordt verhoogd. | `commerce.productListAdds` |

#### Gegevens verzameld van addToCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.productListAdds` | Geeft aan of een product aan een winkelwagentje is toegevoegd. Een waarde van `1` geeft aan dat een product is toegevoegd. |
| `commerce.cart.cartID` | De unieke id die het winkelwagentje van de klant identificeert. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### openCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een nieuw winkelwagentje wordt gemaakt, dat wil zeggen wanneer een product aan een leeg winkelwagentje wordt toegevoegd. | `commerce.productListOpens` |

#### Gegevens verzameld van openCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.productListOpens` | Geeft aan of een winkelwagentje is gemaakt. Een waarde van `1` geeft aan dat er een winkelwagentje is gemaakt. |
| `commerce.cart.cartID` | De unieke id die het winkelwagentje van de klant identificeert. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### removeFromCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Deze activering wordt telkens uitgevoerd wanneer een product wordt verwijderd of telkens wanneer de hoeveelheid van een product in het winkelwagentje wordt verlaagd. | `commerce.productListRemovals` |

#### Gegevens verzameld uit removeFromCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.productListRemovals` | Geeft aan of een product uit het winkelwagentje is verwijderd. Een waarde van `1` geeft aan dat een product uit het winkelwagentje is verwijderd. |
| `commerce.cart.cartID` | De unieke id die het winkelwagentje van de klant identificeert. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### shoppingCartView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelwagenpagina wordt geladen. | `commerce.productListViews` |

#### Gegevens verzameld bij shoppingCartView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.productListViews` | Geeft aan of een productlijst is weergegeven. |
| `commerce.cart.cartID` | De unieke id die het winkelwagentje van de klant identificeert. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `commerce.order` | Bevat informatie over de in behandeling zijnde orde voor één of meerdere producten. |
| `commerce.order.discountAmount` | Geeft het kortingsbedrag aan dat op de hele volgorde wordt toegepast. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### pageView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een pagina wordt geladen. | `web.webpagedetails.pageViews` |

#### Gegevens verzameld van pageView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `web.webPageDetails.pageViews` | Geeft aan of een pagina is geladen. A `value` van `1` Hiermee wordt aangegeven dat de pagina is geladen. |
| `web.webPageDetails.URL` | De normatieve of gebruikelijke URL van de webpagina. Dit kan de daadwerkelijke URL zijn die wordt gebruikt om de pagina te bereiken, die zou worden geregistreerd gebruikend `Web Link`. |
| `web.webPageDetails.name` | De normatieve naam van de webpagina. Deze naam is niet noodzakelijkerwijs de paginatitel of is rechtstreeks gekoppeld aan pagina-inhoud, maar wordt gebruikt om de pagina&#39;s van een site te ordenen voor classificatiedoeleinden. |
| `web.webReferrer.URL` | De URL van de webpagina die een winkel heeft bezocht voordat deze op een koppeling naar uw site heeft geklikt. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### productPageView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een productpagina wordt geladen. | `commerce.productViews` |

#### Gegevens verzameld bij productPageView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.productViews` | Geeft aan of het product is weergegeven. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### startCheckout

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer de gebruiker op een uitcheckknop klikt. | `commerce.checkouts` |

#### Gegevens verzameld van startCheckout

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.checkouts` | Hiermee wordt aangegeven of een actie is uitgevoerd tijdens het uitcheckproces. |
| `commerce.cart.cartID` | De unieke id die het winkelwagentje van de klant identificeert. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### completeCheckout

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer de gebruiker een bestelling plaatst. | `commerce.purchases` |

#### Gegevens verzameld bij completeCheckout

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.purchases` | Geeft aan of een bestelling is geaccepteerd. |
| `commerce.order` | Bevat informatie over de geplaatste order voor een of meer producten. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.payments` | De lijst met betalingen voor deze bestelling. |
| `commerce.order.payments.paymentTransactionID` | Unieke identificatiecode voor deze betalingstransactie. |
| `commerce.order.payments.paymentAmount` | De waarde van de betaling. |
| `commerce.order.payments.paymentType` | De betalingsmethode voor deze bestelling. De opties zijn: `cash`, `credit_card`, `debit_card`, `gift_card`, `check`, `paypal`, `wire_transfer`, `credit_card_reference`, `other`. |
| `commerce.order.payments.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.taxAmount` | Het belastingbedrag dat de koper in het kader van de eindbetaling heeft betaald. |
| `commerce.order.discountAmount` | Geeft het kortingsbedrag aan dat op de hele volgorde wordt toegepast. |
| `commerce.order.createdDate` | De tijd en de datum waarop een nieuwe orde in het handelssysteem wordt gecreeerd. Bijvoorbeeld: `2022-10-15T20:20:39+00:00`. |
| `commerce.shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort. |
| `commerce.shipping.shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |  | `shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

## Klantprofielgebeurtenissen

Profielgebeurtenissen die zijn vastgelegd vanuit de opslagruimte, bevatten accountgegevens, zoals `signIn`, `signOut`, `createAccount`, en `editAccount`. Deze gegevens worden gebruikt om belangrijke klantendetails te bevolken die nodig zijn om segmenten beter te bepalen of marketing campagnes, zoals het verzenden van aanbiedingen van de inschrijvingskorting, bevestigingen van de rekeningsverandering, etc. uitvoeren. Er zijn vergelijkbare profielgebeurtenissen vastgelegd van de [server-kant](events-backoffice.md#customer-profile-events).

### signIn

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier zich aanmeldt. | `userAccount.login` |

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

#### Gegevens verzameld van signIn

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `person` | Een individuele actor, contactpersoon of eigenaar. |
| `person.accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast. |
| `person.accountType` | Hiermee legt u het type gebruikersaccount vast, zoals `Personal` of `Company`, indien van toepassing. |
| `person.personalEmailID` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `personalEmail` | Leg contactgegevens vast - een e-mail en bijbehorende informatie. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.login` | Geeft aan of een bezoeker zich heeft aangemeld. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### signOut

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier zich afmeldt. | `userAccount.logout` |

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

#### Gegevens verzameld uit signOut

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.logout` | Geeft aan of een bezoeker zich heeft afgemeld. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### createAccount

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een account probeert te maken. | `userAccount.createProfile` |

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

#### Gegevens verzameld van createAccount

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `person` | Een individuele actor, contactpersoon of eigenaar. |
| `person.accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast. |
| `person.accountType` | Hiermee legt u het type gebruikersaccount vast, zoals `Personal` of `Company`, indien van toepassing. |
| `person.personalEmailID` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `personalEmail` | Leg contactgegevens vast - een e-mail en bijbehorende informatie. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.updateProfile` | Hiermee geeft u aan of een gebruiker zijn accountprofiel heeft bijgewerkt. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### editAccount

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een gebruiker een account probeert te bewerken. | `userAccount.updateProfile` |

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

#### Gegevens verzameld van editAccount

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `person` | Een individuele actor, contactpersoon of eigenaar. |
| `person.accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast. |
| `person.accountType` | Hiermee legt u het type gebruikersaccount vast, zoals `Personal` of `Company`, indien van toepassing. |
| `person.personalEmailID` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `personalEmail` | Leg contactgegevens vast - een e-mail en bijbehorende informatie. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.updateProfile` | Hiermee geeft u aan of een gebruiker zijn accountprofiel heeft bijgewerkt. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

## Zoeken in gebeurtenissen

De zoekgebeurtenissen bevatten gegevens die relevant zijn voor de intentie van de klant. Als winkeliers inzien hoe kopers objecten zoeken, waarop ze klikken en die ze uiteindelijk kopen of opgeven, kunnen ze zien hoe kopers objecten zoeken. Een voorbeeld van hoe u deze gegevens kunt gebruiken is als u bestaande kopers wilt richten die naar uw topproduct zoeken, maar nooit het product kopen. U moet de [[!DNL Live Search]](../live-search/install.md) toegang tot deze gebeurtenissen.

Gebruik de `searchRequest.id` en `searchResponse.id` velden in beide `searchRequestSent` en `searchResponseReceived` gebeurtenissen om een zoekverzoek te doorverwijzen naar de corresponderende zoekreactie.

### searchRequestSent

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd door de volgende gebeurtenissen in het pop-upvenster &quot;Zoeken terwijl u typt&quot;:<br><br>Druk op Enter, klik op _Alles weergeven_<br><br> Wordt geactiveerd door de volgende gebeurtenissen op pagina&#39;s met zoekresultaten:<br><br>Selecteer een filter, wijzig de sorteervolgorde (_Sorteren op_), wijzigt u de sorteerrichting (oplopend of aflopend), wijzigt u het aantal resultaten per pagina (_Aantal per pagina tonen_), naar de volgende pagina gaan, naar de vorige pagina navigeren, naar een andere pagina navigeren | `searchRequest` |

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-extensie geïnstalleerd.

#### Gegevens verzameld van searchRequestSent

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `searchRequest` | Geeft aan of een zoekaanvraag is verzonden. |
| `searchRequest.id` | De unieke id voor deze zoekopdracht. |
| `searchRequest.value` | De kwantificeerbare waarde van het verzoek. |
| `siteSearch` | Bevat informatie over de zoekopdracht. |
| `siteSearch.filter` | Geeft aan of er filters zijn toegepast om de zoekresultaten te beperken. |
| `siteSearch.filter.attribute` (filter) | De facet van een item dat wordt gebruikt om te bepalen of het moet worden opgenomen in zoekresultaten. |
| `siteSearch.filter.isRange` | Wanneer waar, wijzen de waarden op eindpunten van een aanvaardbare waaier van waarden. |
| `siteSearch.filter.value` | Kenmerkwaarde die wordt gebruikt om te bepalen welke items worden opgenomen in de zoekresultaten. |
| `siteSearch.sort` | Geeft aan hoe de zoekresultaten moeten worden gesorteerd. |
| `siteSearch.sort.attribute` (sorteren) | An attribute used to sort items in search results. |
| `siteSearch.sort.order` | De volgorde waarin de zoekresultaten moeten worden geretourneerd. |
| `siteSearch.query` | De zoektermen. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### searchResponseReceived

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer Live zoeken resultaten oplevert voor de popover- of zoekresultatenpagina &quot;Zoeken zoals u typt&quot;. | `searchResponse` |

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-extensie geïnstalleerd.

#### Gegevens verzameld van searchResponseReceived

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `searchResponse` | Geeft aan of een zoekreactie is ontvangen. |
| `searchResponse.id` | De unieke id voor deze specifieke zoekreactie. |
| `searchResponse.value` | De kwantificeerbare waarde van de respons. |
| `siteSearch.numberOfResults` | Het aantal geretourneerde producten. |
| `siteSearch.suggestions` | Een array van tekenreeksen met de namen van producten en categorieën die in de catalogus staan en die vergelijkbaar zijn met de zoekquery. |
| `productListItems` | Een reeks producten die aan het winkelwagentje zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

## B2B-gebeurtenissen

![B2B voor Adobe Commerce](../assets/b2b.svg) Voor B2B-handelaren moet u [installeren](install.md#install-the-b2b-extension) de `experience-platform-connector-b2b` toegang tot deze gebeurtenissen.

De B2B-gebeurtenissen bevatten [aanvraaglijst](https://experienceleague.adobe.com/docs/commerce-admin/b2b/requisition-lists/requisition-lists.html) informatie, zoals of een aanvraaglijst werd gecreeerd, toegevoegd aan, of geschrapt van. Door gebeurtenissen te volgen specifiek voor aanvraaglijsten, kunt u zien welke producten uw klanten vaak kopen en campagnes tot stand brengen die op die gegevens worden gebaseerd.

### createRequisitionList

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een aanvraaglijst maakt. | `commerce.requisitionListOpens` |

#### Gegevens verzameld uit createRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.requisitionListOpens` | Geeft initialisatie van een nieuwe aanvraaglijst aan. |
| `commerce.requisitionList` | De eigenschappen van de aanvraaglijst die door de klant is gemaakt. |
| `commerce.requisitionList.ID` | Unieke id van de aanvraaglijst. |
| `commerce.requisitionList.name` | Naam van de aanvraaglijst die door de klant is opgegeven. |
| `commerce.requisitionList.description` | Beschrijving van de door de klant opgegeven aanvraaglijst. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |

### addToRequisitionList

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een product aan een bestaande aanvraaglijst toevoegt of wanneer een lijst wordt gemaakt. | `commerce.requisitionListAdds` |

#### Gegevens verzameld uit addToRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.requisitionListAdds` | Hiermee wordt de toevoeging van een of meer producten aan een aanvraaglijst aangegeven. |
| `commerce.requisitionList` | De eigenschappen van de aanvraaglijst die door de klant is gemaakt. |
| `commerce.requisitionList.ID` | Unieke id van de aanvraaglijst. |
| `commerce.requisitionList.name` | Naam van de aanvraaglijst die door de klant is opgegeven. |
| `commerce.requisitionList.description` | Beschrijving van de door de klant opgegeven aanvraaglijst. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een array met producten die aan de aanvraaglijst zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### removeFromRequisitionList

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een product uit een aanvraaglijst verwijdert. | `commerce.requisitionListRemovals` |

#### Gegevens verzameld uit removeFromRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.requsitionListRemovals` | Geeft aan of een of meer producten uit een aanvraaglijst zijn verwijderd. |
| `commerce.requisitionList` | De eigenschappen van de aanvraaglijst die door de klant is gemaakt. |
| `commerce.requisitionList.ID` | Unieke id van de aanvraaglijst. |
| `commerce.requisitionList.name` | Naam van de aanvraaglijst die door de klant is opgegeven. |
| `commerce.requisitionList.description` | Beschrijving van de door de klant opgegeven aanvraaglijst. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `productListItems` | Een array met producten die aan de aanvraaglijst zijn toegevoegd. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |

### deleteRequisitionList

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een aanvraaglijst verwijdert. | `commerce.requisitionListDeletes` |

#### Gegevens verzameld uit deleteRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `commerce.requisitionListDeletes` | Geeft aan dat een aanvraaglijst is verwijderd. |
| `commerce.requisitionList` | De eigenschappen van de aanvraaglijst die door de klant is gemaakt. |
| `commerce.requisitionList.ID` | Unieke id van de aanvraaglijst. |
| `commerce.requisitionList.name` | Naam van de aanvraaglijst die door de klant is opgegeven. |
| `commerce.requisitionList.description` | Beschrijving van de door de klant opgegeven aanvraaglijst. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
