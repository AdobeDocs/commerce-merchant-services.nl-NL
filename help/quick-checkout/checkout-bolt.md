---
title: "Uitchecken van een gebruiker van een bout in Adobe Commerce"
description: Overzicht van de [!DNL Quick Checkout] stroom voor een gebruiker van de Bolt in Adobe Commerce.
exl-id: 12f58b7e-1f86-4891-b225-9f4be82c2d5d
feature: Checkout, Services, Storefront
source-git-commit: b1984a26463e14b8dc9a789421e49e5ea81ad039
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Gastgebruikers

De ervaring bij uitchecken door gasten verschilt van de gebruikerservaring van de Adobe. Wanneer een winkelier een e-mailadres invoert bij het afrekenen, [!DNL Quick Checkout] valideert het en vindt een bestaand [!DNL Bolt] account.

>[!WARNING]
>
> De [!DNL In-Store Pickup] (ISPU)-functionaliteit wordt niet ondersteund wanneer de [!DNL Quick Checkout] is ingeschakeld.

## Geregistreerd [!DNL Bolt] account

Indien een [!DNL Bolt] account is gevonden, kopers gaan verder met hun [!DNL Quick Checkout] naadloze uitcheckervaring:

1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres van account of mobiel, afhankelijk van [gebruikersvoorkeuren in het dialoogvenster [!DNL Bolt] account](https://help.bolt.com/shoppers/account/account-settings/#how-to-set-preferred-login-method){target=_blank}.

![Pop-up OTP](assets/new-logo-otp-email.png)

1. Zodra het programma geopend met uw [!DNL Bolt] -account, worden de gegevens automatisch toegevoegd:

   - Verzendgegevens
   - Betalingsmethode

1. Plaats uw bestelling.

>[!TIP]
>
> De gastgebruiker plaatst de bestelling en kan zich optioneel registreren in Adobe Commerce.

## Nieuw [!DNL Bolt] account

Indien niet [!DNL Bolt] -account is gevonden, gaan kopers door met het standaard uitchecken van Adobe Commerce en geeft de winkel alle benodigde gegevens om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- Er verschijnt een selectievakje om u aan te melden [!DNL Bolt] voor snellere kassa&#39;s voordat u de bestelling plaatst. De winkelier kan akkoord gaan met de voorwaarden om hun [!DNL Bolt] account.
- De gastgebruiker plaatst de bestelling en kan zich optioneel registreren in Adobe Commerce.
