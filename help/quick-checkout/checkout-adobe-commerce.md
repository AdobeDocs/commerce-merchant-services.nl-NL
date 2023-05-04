---
title: "Afhandelingsstroom voor een Adobe Commerce-gebruiker"
description: "Overzicht van de [!DNL Quick Checkout] voor een Adobe Commerce-gebruiker."
exl-id: 085e393b-15f6-4d5a-a04d-927b1f95b74e
source-git-commit: f790732804e110aad298689c0ddf74547ff17618
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Een bestaande Adobe Commerce-gebruiker: Hoe werkt het

Een bestaande Adobe Commerce-gebruiker kan opgeslagen verzend- en betalingsgegevens selecteren bij het plaatsen van een bestelling bij de [!DNL Quick Checkout] voor een snellere afrekenervaring.

Wanneer een winkelier zijn e-mailadres invoert bij het uitchecken, wordt de [!DNL Quick Checkout] valideert het en vindt een bestaand [!DNL Bolt] account.

## Geregistreerde gebruiker in zowel Adobe Commerce als [!DNL Bolt]

Wanneer een verkoper een geregistreerde gebruiker is in zowel Adobe Commerce als [!DNL Bolt] netwerken, worden beide netwerken opgeslagen verzendings- en betalingsgegevens verstrekt.

Indien een [!DNL Bolt] account is gevonden tijdens afrekenen, kopers kunnen doorgaan met hun [!DNL Quick Checkout] naadloze uitcheckervaring:

1. Voer het eenmalige wachtwoord (OTP) in dat naar dat wachtwoord is verzonden [!DNL Bolt] e-mailadres van account of mobiel, afhankelijk van [gebruikersvoorkeuren in het dialoogvenster [!DNL Bolt] account](https://help.bolt.com/shoppers/account/account-settings/#how-to-set-preferred-login-method){target=_blank}.

![Pop-up OTP](assets/new-logo-otp-email.png)

1. Zodra het programma geopend met uw [!DNL Bolt] -account, worden de gegevens automatisch toegevoegd:

   - Verzendgegevens
   - Betalingsmethode

1. Plaats uw bestelling.

>[!NOTE]
>
> De pop-up OTP van de Bolt verschijnt slechts wanneer de verkoopster op de checkout pagina is. De winkelier kan zich afmelden bij Bolt door dat pop-upvenster te sluiten.

Als de verkoper vóór het afrekenen is aangemeld bij Adobe Commerce, wordt de [!DNL Bolt] Het pop-up van OTP zal niet tijdens controle verschijnen, maar een bericht lijkt het voorstellen van de verkoopster om aan login om tot hun Bolt Behang toegang te hebben.

Als er problemen optreden wanneer u een bestelling als bestaande Adobe Commerce-gebruiker plaatst, raadpleegt u de [Problemen met snelle afhandeling oplossen](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/quick-checkout-issues.html) artikel in het Adobe Commerce Help Center.

## Automatische aanmelding

De component Automatische aanmelding detecteert wanneer een winkelier een actieve Bolt-sessie heeft en meldt de winkels automatisch aan. Dit slaat de rekeningsopsporing en eenmalige wachtwoordcode (OTP) stappen over omdat de verkoopster hen in een vorige zitting voltooide.

Het is mogelijk een automatische aanmelding te configureren voor [!DNL Quick Checkout] gebruikers. U kunt een configuratie inschakelen om een gebruiker tijdens het uitchecken automatisch aan te melden.

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** om tot de algemene configuratiepagina van Admin van de Controle toegang te hebben.
1. In de _Service-instellingen_ sectie voor [!DNL Quick Checkout], geeft u alle gegevens op die nodig zijn om automatische aanmelding in te stellen.

Zie [[!DNL Quick Checkout] servicemontages configureren](../quick-checkout/onboarding.md#configure-service-settings) voor meer informatie.

>[!NOTE]
>
> Eerste aanmelding bij **automatische aanmelding** is ingeschakeld, is toestemming van de gebruiker vereist om de autorisatie te starten door een pop-upvenster te accepteren.

## Nieuw [!DNL Bolt] account

Indien niet [!DNL Bolt] -account is gevonden, kunnen kopers hun standaard buiten-de-box Adobe Commerce-afhandeling voortzetten en kan de winkel in de opgeslagen gegevens alle benodigde gegevens selecteren om de bestelling te plaatsen:

- Informatie over verzending en facturering
- Verzendmethode
- Betalingsmethode controleren
- De optie om u aan te melden [!DNL Bolt] voor snellere kassa&#39;s voordat de bestelling wordt geplaatst. De winkelier kan akkoord gaan met de voorwaarden om hun [!DNL Bolt] account.

   ![Herinneren [!DNL Bolt]](assets/checkbox-remember-bolt.png)
