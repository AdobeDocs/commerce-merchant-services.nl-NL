---
title: Gebeurtenissen
description: Leer welke gegevens elke gebeurtenis vastlegt.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: 18edfec6dbc66ef0e94e9f54ca1061386104d90c
workflow-type: tm+mt
source-wordcount: '3141'
ht-degree: 0%

---

# Verbindingsgebeurtenissen Experience Platform

De volgende lijst maakt een lijst van de gebeurtenissen van de Handel beschikbaar wanneer u de de schakelaaruitbreiding van het Experience Platform installeert. De gegevens die door deze gebeurtenissen worden verzameld, worden naar de Adobe Experience Platform-rand verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

Naast de gegevens die door de volgende gebeurtenissen worden verzameld, wordt ook [overige gegevens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) verstrekt door de SDK van het Web van Adobe Experience Platform.

## Gebeurtenissen van Storefront

De storefront-gebeurtenissen verzamelen geanonimiseerde gedragsgegevens van uw kopers wanneer ze door uw site bladeren. De gegevens die deze gebeurtenissen verzamelen, kunnen worden gebruikt voor het maken van promoties en campagnes voor een specifieke groep kopers.

>[!NOTE]
>
>Alle storefront-gebeurtenissen omvatten de `identityMap` veld, dat een unieke identificatie van de persoon is.

### addToCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een product aan het winkelwagentje wordt toegevoegd of wanneer de hoeveelheid van een product in het winkelwagentje wordt verhoogd. | `commerce.productListAdds` |

#### Gegevens verzameld van addToCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListAdds` | Geeft aan of een product aan een winkelwagentje is toegevoegd. Een waarde van `1` geeft aan dat een product is toegevoegd. |
| `productListItems` | Een reeks producten die aan het winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal aan het winkelwagentje toegevoegde producteenheden |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

### openCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een nieuw winkelwagentje wordt gemaakt, dat wil zeggen wanneer een product aan een leeg winkelwagentje wordt toegevoegd. | `commerce.productListOpens` |

#### Gegevens verzameld van openCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListOpens` | Geeft aan of een winkelwagentje is gemaakt. Een waarde van `1` geeft aan dat er een winkelwagentje is gemaakt. |
| `productListItems` | Een reeks producten die aan het winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal aan het winkelwagentje toegevoegde producteenheden |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

### removeFromCart

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Deze activering wordt telkens uitgevoerd wanneer een product wordt verwijderd of telkens wanneer de hoeveelheid van een product in het winkelwagentje wordt verlaagd. | `commerce.productListRemovals` |

#### Gegevens verzameld uit removeFromCart

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListRemovals` | Geeft aan of een product uit het winkelwagentje is verwijderd. Een waarde van `1` geeft aan dat een product uit het winkelwagentje is verwijderd. |
| `productListItems` | Een reeks producten die uit het winkelwagentje zijn verwijderd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal uit het winkelwagentje verwijderde producteenheden |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

### shoppingCartView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelwagenpagina wordt geladen. | `commerce.productListViews` |

#### Gegevens verzameld bij shoppingCartView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListViews` | Geeft aan of een productlijst is weergegeven |
| `productListItems` | Een reeks producten in het winkelwagentje |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal eenheden van het product in het winkelwagentje |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

### pageView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een pagina wordt geladen. | `web.webpagedetails.pageViews` |

#### Gegevens verzameld van pageView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `pageViews` | Geeft aan of een pagina is geladen. A `value` van `1` Hiermee wordt aangegeven dat de pagina is geladen. |

### productPageView

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een productpagina wordt geladen. | `commerce.productViews` |

#### Gegevens verzameld bij productPageView

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productViews` | Geeft aan of het product is bekeken |
| `productListItems` | Een reeks producten in het winkelwagentje |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |

### startCheckout

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer de gebruiker op een uitcheckknop klikt. | `commerce.checkouts` |

#### Gegevens verzameld van startCheckout

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `checkouts` | Geeft aan of een actie is uitgevoerd tijdens het uitrekenen |
| `productListItems` | Een reeks producten in het winkelwagentje |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal eenheden van het product in het winkelwagentje |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

### completeCheckout

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer de gebruiker een bestelling plaatst. | `commerce.order` |

#### Gegevens verzameld bij completeCheckout

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `purchases` | Geeft aan of een bestelling is geaccepteerd |
| `order` | Bevat informatie over de geplaatste order voor een of meer producten |
| `purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is. |
| `orderType` | Geeft het type bestelling aan dat is geplaatst, zoals Afhandeling of Onmiddellijke aankoop |
| `payments` | De lijst met betalingen voor deze bestelling |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) de valutacode die voor dit betalingsobject wordt gebruikt. Bijvoorbeeld: `USD` of `EUR`. |
| `paymentAmount` | De waarde van de betaling |
| `paymentType` | De betalingsmethode voor deze bestelling. De opties zijn: `cash`, `credit_card`, `debit_card`, `gift_card`, `check`, `paypal`, `wire_transfer`, `credit_card_reference`, `other` |
| `transactionID` | De unieke transactie-id voor dit betalingsobject |
| `shipping` | Verzendgegevens voor een of meer producten. |
| `shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, snelle levering, ophaling in winkel, enzovoort |
| `shippingAmount` | De totale verzendkosten voor de objecten in het winkelwagentje |
| `promotionID` | Unieke identificatiecode van de eventuele afzetbevordering |
| `personalEmail` | Hier geeft u het persoonlijke e-mailadres op |
| `address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen |
| `productListItems` | Een reeks producten in het winkelwagentje |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `quantity` | Het aantal eenheden van het product in het winkelwagentje |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valutacode die wordt gebruikt voor de totalen van de bestelling. |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |


## Profielgebeurtenissen

Profielgebeurtenissen bevatten accountgegevens, zoals `signIn`, `signOut`, `createAccount`, en `editAccount`. Deze gegevens worden gebruikt om belangrijke klantendetails te bevolken die nodig zijn om segmenten beter te bepalen of marketing campagnes uit te voeren, zoals als u klanten wilt richten die in New York wonen.

### signIn

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier zich probeert aan te melden. | `userAccount.login` |

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

#### Gegevens verzameld van signIn

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `eventType` | Het primaire gebeurtenistype voor deze tijdreeksrecord, zoals: `userAccount.login` |
| `person` | Een individuele actor, contactpersoon of eigenaar |
| `accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast |
| `personalEmailID` | Hiermee geeft u de unieke id voor de persoonlijke e-mail op |
| `address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen |
| `userAccount` | Geeft alle gegevens over de loyaliteit, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan |
| `login` | Geeft aan of een bezoeker zich heeft aangemeld |

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
| `eventType` | Het primaire gebeurtenistype voor deze tijdreeksrecord, zoals: `userAccount.logout` |
| `userAccount` | Geeft alle gegevens over de loyaliteit, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan |
| `logout` | Geeft aan of een bezoeker zich heeft afgemeld |

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
| `eventType` | Het primaire gebeurtenistype voor deze tijdreeksrecord, zoals: `account.createProfile` |
| `person` | Een individuele actor, contactpersoon of eigenaar |
| `accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast |
| `accountType` | Hiermee legt u het type gebruikersaccount vast, zoals `Personal` of `Company`, indien van toepassing |
| `personalEmailID` | Hiermee geeft u de unieke id voor de persoonlijke e-mail op |
| `address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen |
| `userAccount` | Geeft alle gegevens over de loyaliteit, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan |
| `createProfile` | Hiermee wordt aangegeven of een gebruiker een accountprofiel heeft gemaakt |

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
| `eventType` | Het primaire gebeurtenistype voor deze tijdreeksrecord, zoals: `account.updateProfile` |
| `person` | Een individuele actor, contactpersoon of eigenaar |
| `accountID` | Hiermee legt u de gebruikersnaam van de gebruikersaccount vast |
| `accountType` | Hiermee legt u het type gebruikersaccount vast, zoals `Personal` of `Company`, indien van toepassing |
| `personalEmailID` | Hiermee geeft u de unieke id voor de persoonlijke e-mail op |
| `personalEmail` | Hier geeft u het persoonlijke e-mailadres op |
| `address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen |
| `userAccount` | Geeft alle gegevens over de loyaliteit, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan |
| `updateProfile` | Hiermee wordt aangegeven of een gebruiker zijn accountprofiel heeft bijgewerkt |

## Zoeken in gebeurtenissen

De zoekgebeurtenissen bevatten gegevens die relevant zijn voor de intentie van de klant. Als winkeliers inzien hoe kopers objecten zoeken, waarop ze klikken en die ze uiteindelijk kopen of opgeven, kunnen ze zien hoe kopers objecten zoeken. Een voorbeeld van hoe u deze gegevens kunt gebruiken, is als u bestaande kopers wilt richten die naar uw beste product zoeken, maar nooit het product kopen.

### searchRequestSent

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd door de volgende gebeurtenissen in het pop-upvenster &quot;Zoeken terwijl u typt&quot;:<br><br>Druk op Enter, klik op _Alles weergeven_<br><br> Wordt geactiveerd door de volgende gebeurtenissen op pagina&#39;s met zoekresultaten:<br><br>Selecteer een filter, wijzig de sorteervolgorde (_Sorteren op_), wijzigt u de sorteerrichting (oplopend of aflopend), wijzigt u het aantal resultaten per pagina (_Aantal per pagina tonen_), naar de volgende pagina gaan, naar de vorige pagina navigeren, naar een andere pagina navigeren | `searchRequest` |

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.

#### Gegevens verzameld van searchRequestSent

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `searchRequest` | Geeft aan of een zoekaanvraag is verzonden |
| `filter` | Geeft aan of er filters zijn toegepast om de zoekresultaten te beperken |
| `attribute` (filter) | De facet van een item dat wordt gebruikt om te bepalen of het moet worden opgenomen in zoekresultaten |
| `value` | Kenmerkwaarden die worden gebruikt om te bepalen welke items worden opgenomen in de zoekresultaten |
| `isRange` | Indien waar (true), wijzen waarden op eindpunten van een acceptabel waardebereik |
| `sort` | Geeft aan hoe zoekresultaten moeten worden gesorteerd |
| `attribute` (sorteren) | Een kenmerk dat wordt gebruikt voor het sorteren van items in zoekresultaten |
| `order` | De volgorde waarin de zoekresultaten moeten worden geretourneerd |
| `query` | De zoektermen |

### searchResponseReceived

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer Live zoeken resultaten oplevert voor de popover- of zoekresultatenpagina &quot;Zoeken zoals u typt&quot;. | `searchResponse` |

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.

#### Gegevens verzameld van searchResponseReceived

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `searchResponse` | Geeft aan of een zoekreactie is ontvangen |
| `suggestions` | Een array van tekenreeksen met de namen van producten en categorieën die in de catalogus staan en die vergelijkbaar zijn met de zoekquery |
| `numberOfResults` | Het aantal geretourneerde producten |
| `productListItems` | Een reeks producten in het winkelwagentje. |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |

## (bèta) Back office gebeurtenissen

>[!NOTE]
>
>Voor verkopers die reeds in ons achterkantoor bètaprogramma worden ingeschreven, hebt u toegang tot achterkantoorgebeurtenissen. Als u wilt deelnemen aan het bètaprogramma voor het back office kantoor, neemt u contact op met [drios@adobe.com](mailto:drios@adobe.com).

De gebeurtenissen van het achterkantoor bevatten informatie over de status van een orde, zoals als een orde werd geplaatst, geannuleerd, terugbetaald, of verscheept. De gegevens die deze server-zijgebeurtenissen verzamelen tonen een 360 mening van de winkelorde. Dit kan handelaren helpen de volledige orderstatus beter te richten of te analyseren wanneer het ontwikkelen van marketing campagnes. U kunt bijvoorbeeld trends waarnemen in bepaalde productcategorieën die goed presteren op verschillende momenten van het jaar. Bijvoorbeeld winterkleding die beter verkoopt tijdens koudere maanden of bepaalde productkleuren waarin consumenten in de loop der jaren geïnteresseerd zijn. Bovendien kunnen de gegevens van de ordestatus u helpen de waarde van de levenklant berekenen door de neiging van een klant te begrijpen om op vorige orden gebaseerd om te zetten.

### orderPlaced

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een bestelling plaatst. | `commerce.orderPlaced` |

#### Gegevens verzameld van orderPlaced

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `identityMap` | Bevat het e-mailadres dat de klant identificeert |
| `address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen |
| `eventType` | `commerce.orderPlaced` |
| `productListItems` | Een array van producten in de volgorde |
| `name` | De weergavenaam of leesbare naam van het product |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `quantity` | Het aantal eenheden van het product in het winkelwagentje |
| `priceTotal` | De totale prijs voor het productlijnitem |
| `discountAmount` | Geeft de toegepaste korting aan |
| `order` | Bevat informatie over de bestelling |
| `purchaseID` | De unieke id die door de verkoper is toegewezen voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is |
| `purchaseOrderNumber` | Unieke identificatiecode toegekend door de koper voor deze aankoop of dit contract |
| `payments` | De lijst met betalingen voor deze bestelling |
| `paymentType` | De betalingsmethode voor deze bestelling. Opsommende, aangepaste waarden toegestaan. |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valutacode gebruikt voor dit betalingsobject |
| `paymentAmount` | De waarde van de betaling |
| `shipping` | Verzendgegevens voor een of meer producten |
| `shippingMethod` | De door de klant gekozen verzendmethode, zoals standaardlevering, snelle levering, ophaling in winkel, enzovoort |
| `shippingAddress` | Fysiek verzendadres |
| `street1` | Informatie op straat, appartementnummer, straatnummer en straatnaam |
| `shippingAmount` | Het bedrag dat de klant voor de verzending moest betalen. |
| `billingAddress` | Postadres facturering |
| `street1` | Informatie op straat, appartementnummer, straatnummer en straatnaam |
| `street2` | Aanvullende gegevens op straatniveau |
| `city` | De naam van de stad |
| `state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `postalCode` | De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten. |
| `country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |

### orderShipped

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een bestelling wordt verzonden. | `commerce.orderLineItemShipped` |

#### Gegevens verzameld van orderShipped

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.
|Veld|Omschrijving| |—|—| |`identityMap`|Bevat het e-mailadres dat de klant identificeert| |`address`|Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen| |`eventType`|`commerce.orderLineItemShipped`| |`productListItems`|Een reeks producten in de volgorde| |`name`|De weergavenaam of leesbare naam van het product| |`SKU`|Eenheid voorraadbewaring. De unieke id voor het product.| |`quantity`|Aantal eenheden van het product in de kar| |`priceTotal`|De totale prijs voor het product-line artikel| |`discountAmount`|Geeft het toegepaste kortingsbedrag aan| |`order`|Bevat informatie over de bestelling| |`purchaseID`|Unieke identificatiecode toegekend door de verkoper voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is| |`purchaseOrderNumber`|Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend| |`payments`|Lijst van betalingen voor deze bestelling| |`paymentType`|De wijze van betaling van deze bestelling. Opsommende, aangepaste waarden toegestaan.| |`currencyCode`|De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) voor dit betalingsobject gebruikte valutacode| |`paymentAmount`|De waarde van de betaling| |`shipping`|Verzendgegevens voor een of meer producten| |`shippingMethod`|De door de klant gekozen verzendmethode, zoals standaardlevering, versnelde levering, ophaalservice, enzovoort| |`shippingAddress`|Fysiek verzendadres| |`street1`|Informatie op straat, appartementnummer, straatnummer en straatnaam| |`shippingAmount`|Het bedrag dat de klant voor de verzending moest betalen.| |`billingAddress`|Factureringsadres per post | |`street1`|Informatie op straat, appartementnummer, straatnummer en straatnaam| |`street2`|Aanvullend veld voor straatinformatie| |`city`|De naam van de stad| |`state`|De naam van de staat. Dit is een veld met vrije vorm.| |`postalCode`|De postcode van de locatie. Postcodes zijn niet voor alle landen beschikbaar. In sommige landen zal dit slechts een deel van de postcode bevatten.| |`country`|De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben.|

### orderCanceled

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een winkelier een bestelling annuleert. | `commerce.orderCancelled` |

#### Gegevens verzameld van orderCanceled

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.
|Veld|Omschrijving| |—|—| |`identityMap`|Bevat het e-mailadres dat de klant identificeert| |`address`|Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen| |`eventType`|`commerce.orderCancelled`| |`productListItems`|Een reeks producten in de volgorde| |`name`|De weergavenaam of leesbare naam van het product| |`SKU`|Eenheid voorraadbewaring. De unieke id voor het product.| |`quantity`|Aantal eenheden van het product in de kar| |`priceTotal`|De totale prijs voor het product-line artikel| |`discountAmount`|Geeft het toegepaste kortingsbedrag aan| |`order`|Bevat informatie over de bestelling| |`purchaseID`|Unieke identificatiecode toegekend door de verkoper voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is| |`purchaseOrderNumber`|Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend|

### orderRefunded

| Beschrijving | XDM-gebeurtenisnaam |
|---|---|
| Wordt geactiveerd wanneer een gebruiker een item in een bestelling retourneert. | `commerce.creditMemoIssued` |

#### Gegevens verzameld van orderRefunded

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.
|Veld|Omschrijving| |—|—| |`identityMap`|Bevat het e-mailadres dat de klant identificeert| |`address`|Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen| |`eventType`|`commerce.creditMemoIssued`| |`productListItems`|Een reeks producten in de volgorde| |`order`|Bevat informatie over de bestelling| |`purchaseID`|Unieke identificatiecode toegekend door de verkoper voor deze aankoop of dit contract. Er is geen garantie dat de id uniek is| |`purchaseOrderNumber`|Unieke identificatiecode die door de koper voor deze aankoop of dit contract is toegekend|
