---
title: '"Afhandelingsstroom"'
description: '"Overzicht van de [!DNL Quick Checkout] flow in Adobe Commerce."'
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Quick Checkout] stroom

In deze sectie vindt u een overzicht van de gebruikelijke afrekenervaring met de functie [!DNL Quick Checkout] voor Adobe Commerce-extensie.

Een geslaagde [!DNL Quick Checkout] De stroom bestaat uit de volgende stappen:

1. Open de winkelruimte en voeg objecten toe aan de winkelwagentje.
1. Ga door met de kassa.

![Afhandeling](assets/proceed-checkout.png)

1. Voer desgevraagd een e-mailadres in dat is gekoppeld aan een [!DNL Bolt] account.
1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres of telefoonnummer van account.
1. Zodra het programma geopend met uw [!DNL Bolt] account, betalingsgegevens worden automatisch ingevuld in:

   - Verzendgegevens
   - Betalingsmethode

   >[!NOTE]
   >
   > Je kunt je bestaande portefeuillegegevens (adres- of creditcardgegevens) ook gebruiken als je afbetalingsgegevens automatisch worden ingevuld.

1. Place Order.

De [!DNL Quick Checkout] is compatibel met standaard aanvullende Adobe Commerce-afhandelingsopties, zoals [cadeaukaarten](https://docs.magento.com/user-guide/catalog/product-gift-card.html) of [kortingscodes](https://docs.magento.com/user-guide/marketing/price-rules-cart-coupon.html).

## [!DNL Quick Checkout] use cases

De [!DNL Quick Checkout] staat voor veelvoudige gebruiksgevallen tijdens een controlestroom toe:

- Gastgebruiker met geregistreerde [!DNL Bolt] account.
- Gastgebruiker met een nieuwe [!DNL Bolt] account.
- Een bestaande Adobe Commerce-gebruiker met of zonder geregistreerde [!DNL Bolt] account.

## Afhandeling door gastgebruiker: Hoe werkt het

De ervaring bij het afrekenen van gasten verschilt van de ervaring bij het aanmelden. Wanneer een winkelier een e-mailadres invoert bij het afrekenen, [!DNL Quick Checkout] valideert het om een bestaand [!DNL Bolt] account.

### Geregistreerd [!DNL Bolt] account

Indien een [!DNL Bolt] account is gevonden, kopers gaan verder met hun [!DNL Quick Checkout] naadloze uitcheckervaring:

1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres van account of mobiel, afhankelijk van de voorkeuren van de gebruiker in het dialoogvenster [!DNL Bolt] account.
1. Zodra het programma geopend met uw [!DNL Bolt] -account, worden de uitcheckgegevens automatisch ingevuld:

   - Verzendgegevens
   - Betalingsmethode

1. Place Order.

>[!TIP]
>
> Gastgebruiker plaatst de bestelling en kan zich registreren in Adobe Commerce.

### Nieuw [!DNL Bolt] account

Indien niet [!DNL Bolt] -account is gevonden, kunnen kopers hun standaard buiten-de-box Adobe Commerce-afhandeling voortzetten en kan winkels alle benodigde gegevens verstrekken om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- Er verschijnt een selectievakje om u aan te melden [!DNL Bolt] voor snellere kassa&#39;s voordat u de bestelling plaatst. Ze kunnen akkoord gaan met de voorwaarden om hun [!DNL Bolt] account.

   ![Herinneren [!DNL Bolt]](assets/checked-bolt.png)

- De gastgebruiker plaatst de bestelling en kan zich in Adobe Commerce registreren.

## Een bestaande Adobe Commerce-gebruiker: Hoe werkt het

Een bestaande gebruiker kan bestaande details selecteren wanneer de gebruiker een orde met [!DNL Quick Checkout] voor een snellere afrekenervaring.

Wanneer een winkelier een e-mailadres invoert bij het afrekenen, [!DNL Quick Checkout] valideert het om een bestaand [!DNL Bolt] account.

### Geregistreerd [!DNL Bolt] account bij een Adobe Commerce-gebruiker

Indien een [!DNL Bolt] -account wordt gevonden, kunnen kopers hun standaard uitchecken via Adobe Commerce en kan winkelen alle benodigde gegevens verstrekken en vervolgens de bestelling plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren

Zie de [problemen oplossen](../quick-checkout/troubleshooting.md) onderwerp voor meer informatie als u problemen ontmoet wanneer u een orde als bestaande gebruiker van Adobe Commerce plaatst.

>[!NOTE]
>
> Als de gebruiker een [!DNL Bolt] account en e-mail worden niet weergegeven als geregistreerd in Adobe Commerce, maar de aanmelding voor eenmalige wachtwoorden (One-Time Password, OTP) wordt geactiveerd. Zie de [geregistreerd [!DNL Bolt] account](#registered-bolt-account) stroom.

### Nieuw [!DNL Bolt] account

Indien niet [!DNL Bolt] -account is gevonden, kunnen kopers hun standaard afhandeling door Adobe Commerce voortzetten en kan winkeliers alle benodigde gegevens uit hun opgeslagen gegevens selecteren om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- Er verschijnt een selectievakje om u aan te melden [!DNL Bolt] voor snellere kassa&#39;s voordat u de bestelling plaatst. Ze kunnen akkoord gaan met de voorwaarden om hun [!DNL Bolt] account.

   ![Herinneren [!DNL Bolt]](assets/checked-bolt.png)

## Hulp vragen

Contact [Adobe Commerce-ondersteuning](mailto:quick-checkout-support@adobe.com) voor alle bijstand.
