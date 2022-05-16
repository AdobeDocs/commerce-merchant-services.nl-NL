---
title: Aan boord van de [!DNL Express Checkout] voor Adobe Commerce-extensie
description: Meer informatie over [!DNL Express Checkout] kan uw Adobe Commerce-exemplaar ten goede komen en de extensie met succes aan boord installeren en instellen.
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: bd9541c5e4810085ab85206b2ecca21e66800a2f
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# [!DNL Express Checkout] onboarding

>[!IMPORTANT]
>
> Deze functie is alleen bedoeld voor gebruikers van het programma Early Introducter (EAP) en is nog niet voor alle klanten toegankelijk. Momenteel beperkt tot Amerikaanse klanten. Neem contact op met Adobe Commerce Support voor hulp en vragen.

Ga als volgt te werk om aan de slag te gaan [!DNL Express Checkout] voor Adobe Commerce-extensie moet u een aantal instapkaartstappen uitvoeren om uw exemplaar te verbinden met onze uitcheckfunctionaliteit.

1. [Extensie ophalen](#get-extension).
1. [Een Merchant-account voor de productie of sandbox maken met [!DNL Bolt]](#create-account-with-bolt). Geef alle vereiste gegevens op om uw identiteit te verifiëren.
1. [Geef de unieke API-sleutel en Publishable-sleutel op die zijn gegenereerd in [!DNL Bolt]](#obtain-api-credentials).
1. [Een betalingsprovider instellen in het dialoogvenster [!DNL Bolt] account](#configure-payment-providers).
1. [Stelt vervolgkeuzelijst Inschakelen in op Ja](#enable-extension) om de extensie te activeren.
1. [Definieer uw servicesinstellingen](#complete-admin-configuration) om het [!DNL Express Checkout] extensie.
1. [Klik op de knop Config opslaan](#enable-live-express-checkout) om extensie in te schakelen.

>[!NOTE]
>
> Als u uw [!DNL Bolt] accounts (stap 2 hierboven) kunt u uw sandbox- of productieomgevingen niet instellen.

## Vereisten

Voor het gebruik van de [!DNL Express Checkout], moet het volgende beschikbaar zijn voor [!DNL Bolt]:

- Ondersteunde betalingsproviders
- Merchant and Production account in [!DNL Bolt]
- API en Publishable-sleutel gegenereerd in [!DNL Bolt]

Zie de [voorwaarden](../express-checkout/prerequisites.md) voor meer informatie.

Zie [API-referenties](#obtain-api-credentials) om te leren hoe u uw API-sleutels voor uw instantie kunt maken of openen.

## Extensie ophalen

Zie de [installeren](../express-checkout/install.md) onderwerp voor gedetailleerde informatie over het verkrijgen van de uitbreiding.

## Account maken met Bolt

Voordat u de [!DNL Express Checkout] in uw Adobe Commerce Admin is het vereist om een [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} en [productie](https://merchant.bolt.com/register){target=&quot;_blank&quot;} zakelijke account in [!DNL Bolt]. Geef alle vereiste gegevens op om een account te maken in [!DNL Bolt].

Zie de [testen en valideren](../express-checkout/testing.md) voor meer informatie.

## API-referenties verkrijgen

Als u de opdracht [!DNL Express Checkout] u hebt [!DNL Bolt] unieke toetsen. Verkrijg de volgende API sleutels door te navigeren aan **Ontwikkelaars** > **API** > **Toetsen** in de **Bolt Merchant Dashboard**.

- API-sleutel: Een persoonlijke sleutel die door uw achterste eind wordt gebruikt om met elkaar in wisselwerking te staan [!DNL Bolt] API&#39;s.
- Publishable key: Een toets die door uw voorzijde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s.

Zie de [[!DNL Bolt] omgevingsdetails](https://help.bolt.com/developers/references/environment-details/#about-keys){target=&quot;_blank&quot;_page voor meer informatie over de API- en Publishable-toetsen voor de [!DNL Express Checkout] extensie.

>[!CAUTION]
>
> U moet API-sleutels maken voor zowel sandbox- als productieomgevingen.

## Betalingsproviders configureren

Volg de stappen in het dialoogvenster [processorinstelling](https://help.bolt.com/integrations/adobe-express-checkout/set-up/){target=&quot;_blank&quot;} -ontwikkelaar [!DNL Bolt] pagina.

## Extensie inschakelen

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** voor toegang tot de configuratiepagina voor uitcheckbeheer.

   ![Uitdrukkelijke afhandeling](assets/admin-view.png)

1. In de [!DNL Express Checkout] weergave, instellen **Inschakelen** tot `Yes`.
1. Selecteer de methode (Sandbox of Production) die u wilt gebruiken.

   - Sandbox voor test- en ontwikkelingsdoeleinden
   - Productie om transacties met de verwerker van de rechtstreekse betaling te verwerken

1. Valideer Referenties nadat u de unieke API- en Publishable-toetsen hebt opgegeven.

>[!CAUTION]
>
> U moet unieke API- en Publishable-sleutels opgeven voordat u de extensie inschakelt, anders zien klanten een betaalformulier en kunnen ze geen bestelling plaatsen.

## Volledige beheerconfiguratie

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** om toegang te krijgen tot de algemene configuratiepagina van Admin.
1. In de _Service-instellingen_ alle gegevens opgeven die nodig zijn om de extensie in te schakelen.
1. Set _Betalingsactie_ als:

   - Autoriseren: Geen transactie automatisch vastleggen na toestemming.
   - Autoriseren en vastleggen: Transactie automatisch vastleggen na machtiging.

Raadpleeg voor meer informatie over de standaardafhandelingsopties van Adobe Commerce de [uitchecken](https://docs.magento.com/user-guide/configuration/sales/checkout.html) onderwerp.

## Live express-uitchecken inschakelen

Om het [!DNL Express Checkout] voor Adobe Commerce-extensie:

1. Klikken **Config opslaan**.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

## Hulp vragen

Het instapproces is ontworpen om u door de vereiste stappen te begeleiden voor het instellen en inschakelen van de [!DNL Express Checkout] functionaliteit. Contact [!DNL Adobe Commerce] technische team door uw toegewezen Slack [Adobe Beta-programma&#39;s, kanaal](http://adobe-beta-programs.slack.com/) voor alle bijstand.

Zie de [testen en valideren](../express-checkout/testing.md) voor meer informatie.
