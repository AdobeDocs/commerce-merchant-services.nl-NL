---
title: Gebeurtenissen
description: Leer welke gegevens elke gebeurtenis vangt en de volledige schemadefinitie bekijkt.
exl-id: b0c88af3-29c1-4661-9901-3c6d134c2386
source-git-commit: 589d22f488572411b6632ac37d7bc5b752f72e2d
workflow-type: tm+mt
source-wordcount: '1818'
ht-degree: 0%

---

# Verbindingsgebeurtenissen Experience Platform

De volgende lijst maakt een lijst van de gebeurtenissen van de Handel beschikbaar wanneer u de de schakelaaruitbreiding van het Experience Platform installeert. De gegevens die door deze gebeurtenissen worden verzameld, worden naar de Adobe Experience Platform-rand verzonden. U kunt ook [aangepaste gebeurtenissen](custom-events.md) om aanvullende gegevens te verzamelen die niet uit het vak zijn verstrekt.

Naast de gegevens die door de volgende gebeurtenissen worden verzameld, wordt ook [aanvullende gegevens](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html) verstrekt door de SDK van het Web van Adobe Experience Platform.

>[!NOTE]
>
>Alle gebeurtenissen omvatten de `personID` veld, dat een unieke identificatie van de persoon is.

## addToCart

Wordt geactiveerd wanneer een product aan het winkelwagentje wordt toegevoegd of wanneer de hoeveelheid van een product in het winkelwagentje wordt verhoogd. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/addToCartAEP.ts).

### Type

Storefront

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListAdds` | Geeft aan of een product aan een winkelwagentje is toegevoegd. Een waarde van `1` geeft aan dat een product is toegevoegd. |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | Het totaal voor deze bestelling nadat alle kortingen en belastingen zijn toegepast |
| `quantity` | Het aantal eenheden dat de klant heeft aangegeven van het product te verlangen |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

## shoppingCartView

Wordt geactiveerd wanneer een winkelwagenpagina wordt geladen. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/viewAEP.ts).

### Type

Storefront

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productListViews` | Geeft aan of een productlijst is weergegeven |
| `productListItems` | Een reeks producten die aan een winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | Het totaal voor deze bestelling nadat alle kortingen en belastingen zijn toegepast |
| `quantity` | Het aantal eenheden dat de klant heeft aangegeven van het product te verlangen |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

## pageView

Wordt geactiveerd wanneer een pagina wordt geladen. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/page/viewAEP.ts).

### Type

Storefront

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `pageViews` | Geeft aan of een pagina is geladen. A `value` van `1` Hiermee wordt aangegeven dat de pagina is geladen. |

## productPageView

Wordt geactiveerd wanneer een productpagina wordt geladen. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/product/viewAEP.ts).

### Type

Storefront

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `productViews` | Geeft aan of het product is bekeken |
| `productListItems` | Een reeks producten die aan een winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | Het totaal voor deze bestelling nadat alle kortingen en belastingen zijn toegepast |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |

## startCheckout

Wordt geactiveerd wanneer de gebruiker op een uitcheckknop klikt. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/shoppingCart/initiateCheckoutAEP.ts).

### Type

Storefront

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `checkouts` | Geeft aan of een actie is uitgevoerd tijdens het uitrekenen |
| `productListItems` | Een reeks producten die aan een winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | Het totaal voor deze bestelling nadat alle kortingen en belastingen zijn toegepast |
| `quantity` | Het aantal eenheden dat de klant heeft aangegeven van het product te verlangen |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valuta voor het product |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |
| `cartID` | De unieke id die het winkelwagentje van de klant identificeert |

## completeCheckout

Wordt geactiveerd wanneer de gebruiker een bestelling plaatst. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/checkout/placeOrderAEP.ts).

### Type

Storefront

### Gegevens verzameld

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
| `productListItems` | Een reeks producten die aan een winkelwagentje worden toegevoegd |
| `SKU` | Stock Keeping Unit. De unieke id voor het product. |
| `name` | De weergavenaam of leesbare naam van het product |
| `priceTotal` | Het totaal voor deze bestelling nadat alle kortingen en belastingen zijn toegepast |
| `quantity` | Het aantal eenheden dat de klant heeft aangegeven van het product te verlangen |
| `discountAmount` | Geeft de toegepaste korting aan |
| `currencyCode` | De [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) valutacode die wordt gebruikt voor de totalen van de bestelling. |
| `productImageUrl` | URL van hoofdafbeelding van het product |
| `selectedOptions` | Veld voor een configureerbaar product. `attribute` identificeert een attribuut van het configureerbare product, zoals `size` of `color` en `value` identificeert de waarde van het kenmerk, zoals `small` of `black`. |

## signIn

Wordt geactiveerd wanneer een winkelier zich probeert aan te melden. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signInAEP.ts).

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

### Type

Profiel

### Gegevens verzameld

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

## signOut

Wordt geactiveerd wanneer een winkelier zich afmeldt. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/signOutAEP.ts).

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

### Type

Profiel

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `eventType` | Het primaire gebeurtenistype voor deze tijdreeksrecord, zoals: `userAccount.logout` |
| `userAccount` | Geeft alle gegevens over de loyaliteit, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan |
| `logout` | Geeft aan of een bezoeker zich heeft afgemeld |

## createAccount

Wordt geactiveerd wanneer een winkelier een account probeert te maken. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/createAccountAEP.ts).

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

### Type

Profiel

### Gegevens verzameld

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

## editAccount

Wordt geactiveerd wanneer een gebruiker een account probeert te bewerken. [Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/account/editAccountAEP.ts).

>[!NOTE]
>
> Deze gebeurtenis wordt geactiveerd wanneer de specifieke actie wordt uitgevoerd. Het geeft niet aan dat de actie succesvol was.

### Type

Profiel

### Gegevens verzameld

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

## searchRequestSent

Wordt geactiveerd door de volgende gebeurtenissen in het pop-upvenster &quot;Zoeken terwijl u typt&quot;:

- Druk op Enter
- Klikken _Alles weergeven_

Wordt geactiveerd door de volgende gebeurtenissen op pagina&#39;s met zoekresultaten:

- Een filter selecteren
- De sorteervolgorde wijzigen (_Sorteren op_)
- De sorteerrichting wijzigen (oplopend of aflopend)
- Het aantal resultaten per pagina wijzigen (_Aantal per pagina tonen_)
- Naar de volgende pagina navigeren
- Naar de vorige pagina navigeren
- Naar een andere pagina navigeren

[Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchRequestSentAEP.ts).

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.

### Type

Zoeken

### Gegevens verzameld

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

## searchResponseReceived

Wordt geactiveerd wanneer Live zoeken resultaten oplevert voor de popover- of zoekresultatenpagina &quot;Zoeken zoals u typt&quot;.

[Volledig schema](https://github.com/adobe/magento-storefront-event-collector/blob/main/src/handlers/search/searchResponseReceivedAEP.ts)

>[!NOTE]
>
>Zoekgebeurtenissen worden niet ondersteund op een Adobe Commerce Enterprise Edition met de B2B-module geïnstalleerd.

### Type

Zoeken

### Gegevens verzameld

In de volgende tabel worden de gegevens beschreven die voor deze gebeurtenis zijn verzameld.

| Veld | Beschrijving |
|---|---|
| `searchResponse` | Geeft aan of een zoekreactie is ontvangen |
| `suggestions` | Een array van tekenreeksen met de namen van producten en categorieën die in de catalogus staan en die vergelijkbaar zijn met de zoekquery |
| `numberOfResults` | Het aantal geretourneerde producten |
| `productListItems` | Een reeks producten die aan een winkelwagentje worden toegevoegd. Met de `SKU`(Stock Keeping Unit) en `name` van het product (weergavenaam of leesbare naam). |
