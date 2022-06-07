---
title: '"Aan boord van de [!DNL Quick Checkout] voor Adobe Commerce-extensie"'
description: '"Leer hoe u [!DNL Quick Checkout] kan uw Adobe Commerce-exemplaar ten goede komen en de extensie met succes aan boord installeren en instellen."'
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Quick Checkout] onboarding

Ga als volgt te werk om aan de slag te gaan [!DNL Quick Checkout] voor Adobe Commerce-extensie moet u een aantal instapkaartstappen uitvoeren om uw exemplaar te verbinden met onze uitcheckfunctionaliteit.

1. [Extensie ophalen](#get-extension).
1. [Een Merchant-account voor de productie of sandbox maken met [!DNL Bolt]](#create-account-with-bolt). Geef alle vereiste gegevens op om uw identiteit te verifiëren.
1. [Geef de unieke [!DNL API Key] en [!DNL Publishable Key] gegenereerd in [!DNL Bolt]](#obtain-api-credentials).
1. [Een betalingsprovider instellen in het dialoogvenster [!DNL Bolt] account](#configure-payment-providers).
1. [Stelt vervolgkeuzelijst Inschakelen in op Ja](#enable-extension) om de extensie te activeren.
1. [Definieer uw servicesinstellingen](#complete-admin-configuration) om het [!DNL Quick Checkout] extensie.
1. [Klik op de knop Config opslaan](#enable-live-quick-checkout) om extensie in te schakelen.

>[!NOTE]
>
> Als u uw [!DNL Bolt] accounts die u niet kunt instellen, zijn een sandbox- of productieomgeving.

## Vereisten

Voor het gebruik van de [!DNL Quick Checkout], moet het volgende beschikbaar zijn voor [!DNL Bolt]:

- Ondersteunde betalingsproviders
- Merchant and Production account in [!DNL Bolt]
- API en [!DNL Publishable key] gegenereerd in [!DNL Bolt]

Zie de [voorwaarden](../quick-checkout/prerequisites.md) voor meer informatie.

Zie [API-referenties](#obtain-api-credentials) om te leren hoe u uw [!DNL API keys] voor uw instantie.

## Extensie ophalen

Zie de [installeren](../quick-checkout/install.md) onderwerp voor gedetailleerde informatie over het verkrijgen van de uitbreiding.

## Account maken met [!DNL Bolt]

Voordat u de [!DNL Quick Checkout] in uw Adobe Commerce Admin is het vereist om een [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} en [productie](https://merchant.bolt.com/register){target=&quot;_blank&quot;} zakelijke accounts in [!DNL Bolt]. Geef alle vereiste gegevens op om een account te maken in [!DNL Bolt].

Zie de [testen en valideren](../quick-checkout/testing.md) voor meer informatie.

## API-referenties verkrijgen

Als u de opdracht [!DNL Quick Checkout] u hebt [!DNL Bolt] unieke toetsen. Verkrijg het volgende [!DNL API keys] door te navigeren naar **Ontwikkelaars** > **API** > **Toetsen** in de **Bolt Merchant Dashboard**.

- [!DNL API key]: Een persoonlijke sleutel die door uw achterste eind wordt gebruikt om met elkaar in wisselwerking te staan [!DNL Bolt] API&#39;s.
- [!DNL Publishable key]: Een toets die door uw voorzijde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s.

Zie de [[!DNL Bolt] omgevingsdetails](https://help.bolt.com/developers/references/environment-details/#about-keys)pagina {target=&quot;_blank&quot;} voor meer informatie over API en [!DNL Publishable keys] voor de [!DNL Quick Checkout] extensie.

>[!CAUTION]
>
> U moet [!DNL API keys] voor zowel sandbox- als productieomgevingen.

## Betalingsproviders configureren

Volg de stappen in het dialoogvenster [processorinstelling](https://help.bolt.com/integrations/adobe-express-checkout/set-up/){target=&quot;_blank&quot;} -ontwikkelaar [!DNL Bolt] pagina.

## Extensie inschakelen

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** voor toegang tot de configuratiepagina voor uitcheckbeheer.

   ![Snelle afhandeling](assets/admin-view.png)

1. In de [!DNL Quick Checkout] weergave, instellen **Inschakelen** tot `Yes`.
1. Selecteer de methode (Sandbox of Production) die u wilt gebruiken.

   - Sandbox voor test- en ontwikkelingsdoeleinden
   - Productie om transacties met de verwerker van de rechtstreekse betaling te verwerken

1. Valideer referenties nadat u de unieke API hebt opgegeven en [!DNL Publishable keys].

>[!CAUTION]
>
> U moet een unieke API en [!DNL Publishable keys] voordat de uitbreiding wordt toegestaan, zien klanten anders een betaalformulier en kunnen ze geen bestelling plaatsen.

## Volledige beheerdersconfiguratie

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** om toegang te krijgen tot de algemene configuratiepagina van Admin.
1. In de _Service-instellingen_ alle gegevens opgeven die nodig zijn om de extensie in te schakelen.
1. Set _Betalingsactie_ naar een van beide opties:

   - `Authorize`: Geen transactie automatisch vastleggen na toestemming.
   - `Authorize and Capture`: Transactie automatisch vastleggen na machtiging.

Raadpleeg voor meer informatie over de standaardafhandelingsopties van Adobe Commerce de [uitchecken](https://docs.magento.com/user-guide/configuration/sales/checkout.html) onderwerp.

## Live snelle afhandeling inschakelen

Om het [!DNL Quick Checkout] voor Adobe Commerce-extensie:

1. Controleer of de [!UICONTROL Enable] dropdown is ingesteld op **Ja** om de extensie te activeren.
1. Klikken **Config opslaan**.

## Hulp vragen

Het instapproces is ontworpen om u door de vereiste stappen te begeleiden voor het instellen en inschakelen van de [!DNL Express Checkout] functionaliteit. Neem via de toegewezen Slack contact op met het technische team van Adobe Commerce [Adobe Beta-programma&#39;s, kanaal](http://adobe-beta-programs.slack.com/) kanaal voor hulp.

Zie de [testen en valideren](../quick-checkout/testing.md) voor meer informatie.
