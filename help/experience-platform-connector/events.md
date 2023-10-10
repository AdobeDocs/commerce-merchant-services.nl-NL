---
title: Gebeurtenissen
description: Leer welke gegevens elke gebeurtenis vastlegt.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
role: Admin, Developer
feature: Personalization, Integration, Eventing
source-git-commit: 572df7558e825a7a7c442e47af787c209dbe4ee3
workflow-type: tm+mt
source-wordcount: '6906'
ht-degree: 0%

---

# Verbindingsgebeurtenissen Experience Platform

De volgende lijst maakt een lijst van de gebeurtenissen van de Handel beschikbaar wanneer u de de schakelaaruitbreiding van het Experience Platform installeert. De gegevens die door deze gebeurtenissen worden verzameld, worden naar de Adobe Experience Platform-rand verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

Naast de gegevens die door de volgende gebeurtenissen worden verzameld, wordt ook [overige gegevens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) verstrekt door de Adobe Experience Platform Web SDK.

## Gebeurtenissen van Storefront

De storefront-gebeurtenissen verzamelen geanonimiseerde gedragsgegevens van uw kopers wanneer ze door uw site bladeren. U kunt de gegevens die deze gebeurtenissen verzamelen gebruiken om promoties en campagnes te maken voor een specifieke groep kopers. De gebeurtenisgegevens van Storefront omvatten eenvoudige en configureerbare slechts producten.

>[!NOTE]
>
>Alle storefront-gebeurtenissen omvatten de [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) veld, dat het e-mailadres van de verkoper, indien beschikbaar, en de ECID bevat. Als u deze profielgegevens in elke gebeurtenis opneemt, hebt u geen aparte gebruikersaccount-import uit Adobe Commerce nodig.

### addToCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een product aan het winkelwagentje wordt toegevoegd of wanneer de hoeveelheid van een product in het winkelwagentje wordt verhoogd. | `commerce.productListAdds` |

#### Gegevens verzameld van addToCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
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
| `commerce.productListViews` | Geeft aan of een productlijst is weergegeven. |
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

### pageView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een pagina wordt geladen. | `web.webpagedetails.pageViews` |

#### Gegevens verzameld van pageView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
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
| Wordt geactiveerd wanneer de gebruiker een bestelling plaatst. | `commerce.order` |

#### Gegevens verzameld bij completeCheckout

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
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
| `commerce.order.createdDate` | De tijd en de datum waarop een nieuwe orde in het handelssysteem wordt gecreeerd. Bijvoorbeeld, `2022-10-15T20:20:39+00:00`. |
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

## Profielgebeurtenissen

Profielgebeurtenissen bevatten accountgegevens, zoals `signIn`, `signOut`, `createAccount`, en `editAccount`. Deze gegevens worden gebruikt om belangrijke klantendetails te bevolken die nodig zijn om segmenten beter te bepalen of marketing campagnes uit te voeren, zoals als u klanten wilt richten die in New York wonen.

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

De zoekgebeurtenissen bevatten gegevens die relevant zijn voor de intentie van de klant. Als winkeliers inzien hoe kopers objecten zoeken, waarop ze klikken en die ze uiteindelijk kopen of opgeven, kunnen ze zien hoe kopers objecten zoeken. Een voorbeeld van hoe u deze gegevens kunt gebruiken is als u bestaande kopers wilt richten die naar uw topproduct zoeken, maar nooit het product kopen.

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

![B2B voor Adobe Commerce](../assets/b2b.svg) Voor B2B-handelaren moet u [installeren](install.md#install-the-b2b-extension) de `experience-platform-connector-b2b` om deze gebeurtenissen in te schakelen.

De B2B-gebeurtenissen bevatten [aanvraaglijst](https://experienceleague.adobe.com/docs/commerce-admin/b2b/requisition-lists/requisition-lists.html) informatie, zoals of een aanvraaglijst werd gecreeerd, toegevoegd aan, of geschrapt van. Door gebeurtenissen te volgen specifiek voor aanvraaglijsten, kunt u zien welke producten uw klanten vaak kopen en campagnes tot stand brengen die op die gegevens worden gebaseerd.

### createRequisitionList

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een nieuwe aanvraaglijst maakt. | `commerce.requisitionListOpens` |

#### Gegevens verzameld uit createRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.requisitionListOpens` | Geeft initialisatie van een nieuwe aanvraaglijst aan. |
| `commerce.requisitionList` | De eigenschappen van een aanvraaglijst die door de klant is gemaakt. |
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
| Wordt geactiveerd wanneer een winkelier een product aan een bestaande lijst met vereisten toevoegt of wanneer een nieuwe lijst wordt gemaakt. | `commerce.requisitionListAdds` |

#### Gegevens verzameld uit addToRequisitionList

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.requisitionListAdds` | Hiermee wordt de toevoeging van een of meer producten aan een aanvraaglijst aangegeven. |
| `commerce.requisitionList` | De eigenschappen van een aanvraaglijst die door de klant is gemaakt. |
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
| `commerce.requsitionListRemovals` | Geeft aan of een of meer producten uit een aanvraaglijst zijn verwijderd. |
| `commerce.requisitionList` | De eigenschappen van een aanvraaglijst die door de klant is gemaakt. |
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

## Back office evenementen

De back office gebeurtenissen bevatten informatie over de status van een bestelling, zoals of een bestelling is geplaatst, geannuleerd, terugbetaald, verzonden of voltooid. De gegevens die deze server-zijgebeurtenissen verzamelen tonen een 360 mening van de verkooporde. Deze weergave helpt handelaren om bij het ontwikkelen van marketingcampagnes de gehele orderstatus beter te bepalen of te analyseren. U kunt bijvoorbeeld trends waarnemen in bepaalde productcategorieën die goed presteren op verschillende momenten van het jaar. Bijvoorbeeld winterkleding die beter verkoopt tijdens koudere maanden of bepaalde productkleuren waarin consumenten in de loop der jaren geïnteresseerd zijn. Bovendien kunnen de gegevens van de ordestatus u helpen de waarde van de levenklant berekenen door de neiging van een klant te begrijpen om op vorige orden gebaseerd om te zetten.

>[!NOTE]
>
>Alle back office gebeurtenissen omvatten [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) veld, dat het e-mailadres van de verkoper bevat. Als u deze profielgegevens in elke gebeurtenis opneemt, hebt u geen aparte gebruikersaccount-import uit Adobe Commerce nodig.

### orderPlaced

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een bestelling plaatst. | `commerce.backofficeOrderPlaced` |

#### Gegevens verzameld van orderPlaced

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.payments` | De lijst met betalingen voor deze bestelling. |
| `commerce.order.payments.paymentTransactionID` | Unieke identificatiecode voor deze betalingstransactie. |
| `commerce.order.payments.paymentAmount` | De waarde van de betaling. |
| `commerce.order.payments.paymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `commerce.order.payments.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.taxAmount` | Het belastingbedrag dat de koper in het kader van de eindbetaling heeft betaald. |
| `commerce.order.discountAmount` | Geeft het kortingsbedrag aan dat op de hele volgorde wordt toegepast. |
| `commerce.order.createdDate` | De tijd en de datum waarop een nieuwe orde in het handelssysteem wordt gecreeerd. Bijvoorbeeld, `2022-10-15T20:20:39+00:00`. |
| `commerce.order.currencyCode` | De ISO 4217-valutacode die wordt gebruikt voor de totalen van de orders. |
| `commerce.shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort. |
| `commerce.shipping.shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |
| `commerce.shipping.currencyCode` | De ISO 4217-valutacode die wordt gebruikt voor het verzendende totaal. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `commerce.billing.address` | Postadres facturering. |
| `commerce.billing.address.street1` | Informatie op straat, appartementnummer, straatnummer en straatnaam |
| `commerce.billing.address.street2` | Extra veld voor straatinformatie. |
| `commerce.billing.address.city` | De naam van de stad. |
| `commerce.billing.address.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `commerce.billing.address.postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `commerce.billing.address.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.id` | The line item identifier for this product entry. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |
| `productListItems.productImageUrl` | URL van hoofdafbeelding van het product. |

### orderInvoice

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een handelaar een factuur indient om betaling aan te vragen. | `commerce.backofficeOrderInvoiced` |

#### Gegevens verzameld bij orderInvoice

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.priceTotal` | De totale prijs van deze bestelling nadat alle kortingen en belastingen zijn toegepast. |
| `commerce.order.currencyCode` | De ISO 4217-valutacode die wordt gebruikt voor de totalen van de orders. |
| `commerce.order.purchaseOrderNumber` | Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend. |
| `commerce.order.payments` | De lijst met betalingen voor deze bestelling. |
| `commerce.order.payments.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.payments.paymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `commerce.order.payments.paymentAmount` | De waarde van de betaling. |
| `commerce.shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort. |
| `commerce.shipping.shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.id` | The line item identifier for this product entry. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |

### orderItemsShipped

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een bestelling wordt verzonden. | `commerce.backofficeOrderItemsShipped` |

#### Gegevens verzameld van orderItemsShipped

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.payments` | De lijst met betalingen voor deze bestelling. |
| `commerce.order.payments.paymentTransactionID` | Unieke identificatiecode voor deze betalingstransactie. |
| `commerce.order.payments.paymentAmount` | De waarde van de betaling. |
| `commerce.order.payments.paymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `commerce.order.payments.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.priceTotal` | De totale prijs van deze bestelling nadat alle kortingen en belastingen zijn toegepast. |
| `commerce.order.purchaseOrderNumber` | Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend. |
| `commerce.order.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.lastUpdatedDate` | Het tijdstip waarop een bepaalde orderrecord voor het laatst is bijgewerkt in het handelssysteem. |
| `commerce.shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort. |
| `commerce.shipping.shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |
| `commerce.shipping.address` | Het fysieke verzendadres. |
| `commerce.shipping.address.street1` | Primaire straatinformatie, appartementnummer, straatnummer en straatnaam. |
| `commerce.shipping.address.street2` | Optionele straatinformatie, tweede regel. |
| `commerce.shipping.address.city` | De naam van de stad. |
| `commerce.shipping.address.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `commerce.shipping.address.postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `commerce.shipping.address.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `commerce.shipping.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.shipping.trackingNumber` | Het trackingnummer dat door de verzendende maatschappij is opgegeven voor een verzending van een bestelartikel. |
| `commerce.shipping.trackingURL` | De URL waarmee de verzendstatus van een orderitem wordt gevolgd. |
| `commerce.shipping.shipDate` | De datum waarop een of meer items van een bestelling worden verzonden. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `commerce.billing.address` | Postadres facturering. |
| `commerce.billing.address.street1` | Informatie op straat, appartementnummer, straatnummer en straatnaam |
| `commerce.billing.address.street2` | Extra veld voor straatinformatie. |
| `commerce.billing.address.city` | De naam van de stad. |
| `commerce.billing.address.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `commerce.billing.address.postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `commerce.billing.address.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |

### orderCanceled

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een bestelling annuleert. | `commerce.backofficeOrderCancelled` |

#### Gegevens verzameld van orderCanceled

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.purchaseOrderNumber` | Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend. |
| `commerce.order.cancelDate` | De datum en tijd waarop een winkelier een bestelling annuleert. |
| `commerce.order.lastUpdatedDate` | Het tijdstip waarop een bepaalde orderrecord voor het laatst is bijgewerkt in het handelssysteem. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |

### orderLineItemRefunded

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier voor een geretourneerd item wordt terugbetaald. | `commerce.backofficeCreditMemoIssued` |

#### Gegevens verzameld van orderLineItemRefunded

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.lastUpdatedDate` | Het tijdstip waarop een bepaalde orderrecord voor het laatst is bijgewerkt in het handelssysteem. |
| `commerce.order.purchaseOrderNumber` | Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend. |
| `commerce.refunds` | De lijst van terugbetalingen voor deze bestelling. |
| `commerce.refunds.transactionID` | Unieke identificatiecode voor deze restitutie. |
| `commerce.refunds.refundAmount` | De waarde van de restitutie. |
| `commerce.refunds.refundPaymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `commerce.refunds.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |

### orderItemsReturnInitiated

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een item wil retourneren. | `commerce.backofficeOrderItemsReturnInitiated` |

#### Gegevens verzameld bij orderItemsReturnInitiated

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.returns` | De RMA-informatie (Return Merchandise Authorization) voor deze bestelling. |
| `commerce.order.returns.returnID` | De unieke id voor deze RMA (Return Merchandise Authorization). |
| `commerce.order.returns.returnStatus` | De huidige status van RMA (Return Merchandise Authorization), zoals In behandeling, Gesloten enzovoort. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |
| `productListItems.returnItem` | De RMA-informatie (Return Merchandise Authorization) voor dit onderdeel. |
| `productListItems.returnItem.returnStatus` | De status van het geretourneerde item, zoals In behandeling, Goedgekeurd enzovoort. |
| `productListItems.returnItem.returnReason` | De reden waarom er voor dit object om retournering wordt gevraagd. |
| `productListItems.returnItem.returnItemCondition` | De voorwaarde van het item waarvoor de return wordt aangevraagd. |
| `productListItems.returnItem.returnResolution` | De gevraagde resolutie van het item dat wordt geretourneerd, zoals Restitutie, Exchange enzovoort. |
| `productListItems.returnItem.returnQuantityRequested` | Het aantal van dit object dat de verkoper heeft aangevraagd. |
| `productListItems.returnItem.returnQuantityAuthorized` | Het nummer van dit object dat mag worden geretourneerd. |
| `productListItems.returnItem.eturnQuantityReceived` | Het aantal geretourneerde objecten dat is ontvangen. |
| `productListItems.returnItem.returnQuantityApproved` | Het nummer van dit onderdeel met volledige retournering en goedkeuring. |

### orderItemReturnCompleted

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een object is voltooid dat een winkelier heeft aangevraagd om te retourneren. | `commerce.backofficeOrderItemsReturnCompleted` |

#### Gegevens verzameld van orderItemReturnCompleted

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.returns` | De RMA-informatie (Return Merchandise Authorization) voor deze bestelling. |
| `commerce.order.returns.returnID` | De unieke id voor deze RMA (Return Merchandise Authorization). |
| `commerce.order.returns.returnStatus` | De huidige status van RMA (Return Merchandise Authorization), zoals In behandeling, Gesloten enzovoort. |
| `commerce.commerceScope` | Hiermee geeft u aan waar een gebeurtenis heeft plaatsgevonden (weergave, winkel, website, enzovoort). |
| `commerce.commerceScope.environmentID` | De milieu-id. Een alfanumerieke id van 32 cijfers, gescheiden door afbreekstreepjes. |
| `commerce.commerceScope.storeCode` | De unieke opslagcode. U kunt veel winkels per website hebben. |
| `commerce.commerceScope.storeViewCode` | De unieke code van de archiefmening. U kunt per winkel veel weergaven van uw winkel bekijken. |
| `commerce.commerceScope.websiteCode` | De unieke websitecode. U kunt veel websites in een omgeving hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |
| `productListItems.returnItem` | De RMA-informatie (Return Merchandise Authorization) voor dit onderdeel. |
| `productListItems.returnItem.returnStatus` | De status van het geretourneerde item, zoals In behandeling, Goedgekeurd enzovoort. |
| `productListItems.returnItem.returnReason` | De reden waarom er voor dit object om retournering wordt gevraagd. |
| `productListItems.returnItem.returnItemCondition` | De voorwaarde van het item waarvoor de return wordt aangevraagd. |
| `productListItems.returnItem.returnResolution` | De gevraagde resolutie van het item dat wordt geretourneerd, zoals Restitutie, Exchange enzovoort. |
| `productListItems.returnItem.returnQuantityRequested` | Het aantal van dit object dat de verkoper heeft aangevraagd. |
| `productListItems.returnItem.returnQuantityAuthorized` | Het nummer van dit object dat mag worden geretourneerd. |
| `productListItems.returnItem.eturnQuantityReceived` | Het aantal geretourneerde objecten dat is ontvangen. |
| `productListItems.returnItem.returnQuantityApproved` | Het nummer van dit onderdeel met volledige retournering en goedkeuring. |

### orderShipmentCompleted

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een transport is voltooid. | `commerce.backofficeOrderShipmentCompleted` |

#### Gegevens verzameld bij orderShipmentCompleted

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `commerce.order` | Bevat informatie over de orde. |
| `commerce.order.purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `commerce.order.payments` | De lijst met betalingen voor deze bestelling. |
| `commerce.order.payments.paymentTransactionID` | Unieke identificatiecode voor deze betalingstransactie. |
| `commerce.order.payments.paymentAmount` | De waarde van de betaling. |
| `commerce.order.payments.paymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `commerce.order.payments.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `commerce.order.taxAmount` | Het belastingbedrag dat de koper in het kader van de eindbetaling heeft betaald. |
| `commerce.order.createdDate` | De tijd en de datum waarop een nieuwe orde in het handelssysteem wordt gecreeerd. Bijvoorbeeld, `2022-10-15T20:20:39+00:00`. |
| `commerce.shipping` | Verzendgegevens voor een of meer producten. |
| `commerce.shipping.shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort. |
| `commerce.shipping.shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |
| `commerce.shipping.shipDate` | De datum waarop een of meer items van een bestelling worden verzonden. |
| `commerce.shipping.address` | Het fysieke verzendadres. |
| `commerce.shipping.address.street1` | Primaire straatinformatie, appartementnummer, straatnummer en straatnaam. |
| `commerce.shipping.address.street2` | Optionele straatinformatie, tweede regel. |
| `commerce.shipping.address.city` | De naam van de stad. |
| `commerce.shipping.address.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `commerce.shipping.address.postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `commerce.shipping.address.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `commerce.billing.address` | Postadres facturering. |
| `commerce.billing.address.street1` | Informatie op straat, appartementnummer, straatnummer en straatnaam |
| `commerce.billing.address.street2` | Extra veld voor straatinformatie. |
| `commerce.billing.address.city` | De naam van de stad. |
| `commerce.billing.address.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `commerce.billing.address.postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `commerce.billing.address.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `productListItems` | Een array van producten in de volgorde. |
| `productListItems.SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `productListItems.name` | De weergavenaam of leesbare naam van het product. |
| `productListItems.priceTotal` | De totale prijs voor het item van de productlijn. |
| `productListItems.quantity` | Het aantal eenheden van het product in de kar. |
| `productListItems.discountAmount` | Geeft de toegepaste disconteringswaarde aan. |
| `productListItems.currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) gebruikte valutacode, zoals `USD` of `EUR`. |
| `productListItems.selectedOptions` | Veld voor een configureerbaar product. |
| `productListItems.selectedOptions.attribute` | Identificeert een attribuut van het configureerbare product, zoals `size` of `color`. |
| `productListItems.selectedOptions.value` | Hiermee wordt de waarde van het kenmerk geïdentificeerd, zoals `small` of `black`. |
| `productListItems.categories` | Bevat informatie over de categorie van een product. |
| `productListItems.categories.id` | De unieke id van de categorie. |
| `productListItems.categories.name` | De naam van de categorie. |
| `productListItems.categories.path` | Het pad naar de categorie. |
