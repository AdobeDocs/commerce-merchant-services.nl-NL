---
title: "Afhandelingsstroom in Adobe Commerce"
description: "Overzicht van de [!DNL Quick Checkout] flow in Adobe Commerce."
exl-id: 82761627-a0d4-4cb0-aad1-9865fcb550d4
feature: Checkout, Services, Storefront
source-git-commit: 6ba5a283d9138b4c1be11b80486826304c63247f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# [!DNL Quick Checkout] Stroom

In deze sectie vindt u een overzicht van de gebruikelijke afrekenervaring met de functie [!DNL Quick Checkout] voor Adobe Commerce-extensie.

Een geslaagde [!DNL Quick Checkout] De stroom bestaat uit de volgende stappen:

1. Open de winkelruimte en voeg objecten toe aan de winkelwagentje.
1. Ga door met de kassa.

![Afhandeling](assets/proceed-checkout.png){width="200" zoomable="yes"}

>[!NOTE]
>
> U kunt automatische login voor uw koopman toelaten. Zie [Onderwerp automatische aanmelding inschakelen van bout](https://help.bolt.com/products/embedded/direct-api/auto-login/) voor meer informatie .

1. Voer desgevraagd een e-mailadres in dat is gekoppeld aan een [!DNL Bolt] account.
1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres of telefoonnummer van account.

![Pop-up OTP](assets/new-logo-otp-email.png){width="300" zoomable="yes"}

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

- [Gastgebruiker](../quick-checkout/checkout-bolt.md) met een geregistreerde of nieuwe [!DNL Bolt] account.
- Een bestaande [Adobe Commerce-gebruiker](../quick-checkout/checkout-adobe-commerce.md) met of zonder geregistreerde [!DNL Bolt] account.

## Hulp vragen

Neem via de [Adobe Commerce Help Center](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html) voor alle bijstand.
