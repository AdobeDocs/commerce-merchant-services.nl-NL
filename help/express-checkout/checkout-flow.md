---
title: Afhandelingsstroom
description: Overzicht van de [!DNL Express Checkout] stroom in Adobe Commerce.
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
source-git-commit: 163dd5260908b4ea3a8bfbcfdb834531d1603734
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Express Checkout] stroom

>[!IMPORTANT]
>
> Deze functie is alleen bedoeld voor gebruikers van het programma Early Introducter (EAP) en is nog niet voor alle klanten toegankelijk. Momenteel beperkt tot Amerikaanse klanten. Neem contact op met Adobe Commerce Support voor hulp en vragen.

In deze sectie vindt u een overzicht van de gebruikelijke afrekenervaring met de functie [!DNL Express Checkout] voor Adobe Commerce-extensie.

Een geslaagde [!DNL Express Checkout] De stroom bestaat uit de volgende stappen:

1. Open de winkelruimte en voeg objecten toe aan de winkelwagentje.
1. Ga door met de kassa.

![Afhandeling](../assets/proceed-checkout.png)

1. Voer desgevraagd een e-mailadres in dat is gekoppeld aan een Bolt-account.
1. Voer het Eenmalige wachtwoord (OTP) in dat naar het e-mailadres of telefoonnummer van dat Bolt-account is verzonden.
1. Zodra u bent aangemeld met uw Bolt-account, worden de afbetalingsgegevens automatisch ingevuld:

   - Verzendgegevens
   - Betalingsmethode

   >[!NOTE]
   >
   > Je kunt je bestaande portefeuillegegevens (adres- of creditcardgegevens) ook gebruiken als je afbetalingsgegevens automatisch worden ingevuld.

1. Place Order.

De [!DNL Express Checkout] is compatibel met standaard aanvullende Adobe Commerce-afhandelingsopties, zoals [cadeaukaarten](https://docs.magento.com/user-guide/catalog/product-gift-card.html) of [kortingscodes](https://docs.magento.com/user-guide/marketing/price-rules-cart-coupon.html).

## [!DNL Express Checkout] use cases

De [!DNL Express Checkout] staat voor veelvoudige gebruiksgevallen tijdens een controlestroom toe:

- Gastgebruiker met een geregistreerde Bolt-account.
- Gastgebruiker met een nieuwe Bolt-account.
- Een bestaande Adobe Commerce-gebruiker met of zonder geregistreerde Bolt-account.

## Afhandeling door gastgebruiker: Hoe werkt het

De ervaring bij het afrekenen van gasten verschilt van de ervaring bij het aanmelden. Wanneer een winkelier een e-mailadres invoert bij het afrekenen, [!DNL Express Checkout] valideert het om een bestaand Bolt-account te zoeken.

### Geregistreerde Bolt-account

Als een Bolt-account wordt gevonden, gaan kopers door met hun [!DNL Express Checkout] naadloze uitcheckervaring:

1. Voer het eenmalige wachtwoord (OTP) dat naar het e-mailadres of mobiele adres van dat Bolt-account is verzonden in, afhankelijk van de gebruikersvoorkeuren in het Bolt-account.
1. Zodra u bent aangemeld met uw Bolt-account, worden automatisch de uitcheckgegevens ingevuld:

   - Verzendgegevens
   - Betalingsmethode

1. Place Order.

>[!TIP]
>
> Gastgebruiker plaatst de bestelling en kan zich registreren in Adobe Commerce.

### Nieuwe Bolt-account

Als er geen Bolt-account wordt gevonden, gaan kopers verder met het standaard uitchecken van Adobe Commerce en biedt de winkel alle benodigde gegevens om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- Er verschijnt een selectievakje om u in Bolt aan te melden voor snellere kassa&#39;s voordat u de bestelling plaatst. Ze kunnen akkoord gaan met de voorwaarden om hun Bolt-account te maken.

   ![Bolt onthouden](../assets/checked-bolt.png)

- De gastgebruiker plaatst de bestelling en kan zich in Adobe Commerce registreren.

## Een bestaande Adobe Commerce-gebruiker: Hoe werkt het

Een bestaande gebruiker kan bestaande details selecteren wanneer de gebruiker een orde met [!DNL Express Checkout] voor een snellere afrekenervaring.

Wanneer een winkelier een e-mailadres invoert bij het afrekenen, [!DNL Express Checkout] valideert het om een bestaand Bolt-account te zoeken.

### Geregistreerde Bolt-account bij een Adobe Commerce-gebruiker

Als er een Bolt-account wordt gevonden, gaan kopers door met het standaard uitchecken van Adobe Commerce en biedt de winkel alle benodigde gegevens en plaatst deze vervolgens de bestelling:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren

Zie de [problemen oplossen](../express-checkout/troubleshooting.md) onderwerp voor meer informatie als u problemen ontmoet wanneer u een orde als bestaande gebruiker van Adobe Commerce plaatst.

>[!NOTE]
>
> Als de gebruiker een Bolt-account heeft en e-mailberichten niet worden weergegeven als geregistreerd in Adobe Commerce, wordt de aanmelding Eenmalig wachtwoord (OTP) geactiveerd. Zie de [ingeschreven Bolt-account](#registered-bolt-account) stroom.

### Nieuwe Bolt-account

Als er geen Bolt-account wordt gevonden, gaan kopers door met het standaard afrekenen van Adobe Commerce en kiest de winkel alle benodigde gegevens in de opgeslagen gegevens om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- Er verschijnt een selectievakje om u in Bolt aan te melden voor snellere kassa&#39;s voordat u de bestelling plaatst. Ze kunnen akkoord gaan met de voorwaarden om hun Bolt-account te maken.

   ![Bolt onthouden](../assets/checked-bolt.png)

## Hulp vragen

Neem contact op met Adobe Commerce Support voor hulp en vragen.
