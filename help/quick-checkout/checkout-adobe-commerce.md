---
title: "Afhandelingsstroom voor een Adobe Commerce-gebruiker"
description: "Overzicht van de [!DNL Quick Checkout] voor een Adobe Commerce-gebruiker."
exl-id: 085e393b-15f6-4d5a-a04d-927b1f95b74e
source-git-commit: d4b58b0ee3da866d460cf18d96ec9dd27b195f7a
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Een bestaande Adobe Commerce-gebruiker: Hoe werkt het

Een bestaande Adobe Commerce-gebruiker kan opgeslagen verzend- en betalingsgegevens selecteren bij het plaatsen van een bestelling bij de [!DNL Quick Checkout] voor een snellere afrekenervaring.

Wanneer een winkelier zijn e-mailadres invoert bij het uitchecken, wordt de [!DNL Quick Checkout] valideert het en vindt een bestaand [!DNL Bolt] account.

## Geregistreerde gebruiker in zowel Adobe Commerce als [!DNL Bolt]

Wanneer een verkoper een geregistreerde gebruiker is in zowel Adobe Commerce als [!DNL Bolt] netwerken, worden beide netwerken opgeslagen verzendings- en betalingsgegevens verstrekt.

Indien een [!DNL Bolt] account is gevonden tijdens afrekenen, kopers kunnen doorgaan met hun [!DNL Quick Checkout] naadloze uitcheckervaring:

1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres van account of mobiel, afhankelijk van [gebruikersvoorkeuren in het dialoogvenster [!DNL Bolt] account](https://help.bolt.com/shoppers/account/account-settings/#how-to-set-preferred-login-method){target=_blank}.

![Pop-up OTP](assets/pop-up.png)

1. Zodra het programma geopend met uw [!DNL Bolt] -account, worden de gegevens automatisch toegevoegd:

   - Verzendgegevens
   - Betalingsmethode

1. Plaats uw bestelling.

>[!NOTE]
>
> De pop-up OTP van de Bolt verschijnt slechts wanneer de verkoopster op de checkout pagina is. De winkelier kan zich afmelden bij Bolt door dat pop-upvenster te sluiten.

Als de verkoper vóór het afrekenen is aangemeld bij Adobe Commerce, wordt de [!DNL Bolt] Pop-up OTP zal niet tijdens controle verschijnen.

Als er problemen optreden wanneer u een bestelling als bestaande Adobe Commerce-gebruiker plaatst, raadpleegt u de [Problemen met snelle afhandeling oplossen](https://support.magento.com/hc/en-us/articles/6909450342541) artikel in het Adobe Commerce Help Center.

## Nieuw [!DNL Bolt] account

Indien niet [!DNL Bolt] -account is gevonden, kunnen kopers hun standaard buiten-de-box Adobe Commerce-afhandeling voortzetten en kan de winkel in de opgeslagen gegevens alle benodigde gegevens selecteren om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- De optie om u aan te melden [!DNL Bolt] voor snellere kassa&#39;s voordat de bestelling wordt geplaatst. De winkelier kan akkoord gaan met de voorwaarden om hun [!DNL Bolt] account.

   ![Herinneren [!DNL Bolt]](assets/checkbox-remember-bolt.png)
