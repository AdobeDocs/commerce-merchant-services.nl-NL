---
title: Aan boord van de [!DNL Express Checkout] voor Adobe Commerce-extensie
description: Meer informatie over [!DNL Express Checkout] kan uw Adobe Commerce-exemplaar ten goede komen en de extensie met succes aan boord installeren en instellen.
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: d8302d2d652b4e2380cc862183e58cbd2cca831b
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---

# [!DNL Express Checkout] onboarding

>[!IMPORTANT]
>
> Deze functie is alleen bedoeld voor gebruikers van het programma Early Introducter (EAP) en is nog niet voor alle klanten toegankelijk. Momenteel beperkt tot Amerikaanse klanten. Neem contact op met Adobe Commerce Support voor hulp en vragen.

Ga als volgt te werk om aan de slag te gaan [!DNL Express Checkout] voor Adobe Commerce-extensie moet u een aantal instapkaartstappen uitvoeren om uw exemplaar te verbinden met onze uitcheckfunctionaliteit.

1. [Extensie ophalen](#get-extension).
1. [Een Merchant-account voor de productie of sandbox maken met Bolt](#create-account-with-bolt). Geef alle vereiste gegevens op om uw identiteit te verifiëren.
1. [Geef de unieke API-sleutel en Publishable Key op die zijn gegenereerd in Bolt](#obtain-api-credentials).
1. [Een betalingsprovider instellen in het Bolt-account](#configure-payment-providers).
1. [Stelt vervolgkeuzelijst Inschakelen in op Ja](#enable-extension) om de extensie te activeren.
1. [Definieer uw servicesinstellingen](#complete-admin-configuration) om het [!DNL Express Checkout] extensie.
1. [Klik op de knop Config opslaan](#enable-live-express-checkout) om extensie in te schakelen.

>[!NOTE]
>
> Als u uw Bolt-accounts niet configureert (stap 2 hierboven), kunt u uw sandbox- of productieomgeving niet instellen.

## Vereisten

Voor het gebruik van de [!DNL Express Checkout], moet u het volgende beschikbaar hebben voor Bolt:

- Ondersteunde betalingsproviders
- Merchant and Production account in Bolt
- API en Publishable-sleutel die zijn gegenereerd in Bolt

Zie de [voorwaarden](../express-checkout/prerequisites.md) voor meer informatie.

Zie [API-referenties](#obtain-api-credentials) om te leren hoe u uw API-sleutels voor uw instantie kunt maken of openen.

## Extensie ophalen

Zie de [installeren](../express-checkout/install.md) onderwerp voor gedetailleerde informatie over het verkrijgen van de uitbreiding.

## Account maken met Bolt

Voordat u de [!DNL Express Checkout] in uw Adobe Commerce Admin is het vereist om een [productie](https://merchant.bolt.com/register){target=&quot;_blank&quot;} en [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} zakelijke account in Bolt. Geef alle vereiste gegevens op om een account te maken in Bolt.

Zie de [testen en valideren](../express-checkout/testing.md) voor meer informatie.

## API-referenties verkrijgen

Als u de opdracht [!DNL Express Checkout] U hebt Bolt-unieke toetsen nodig. Verkrijg de volgende API sleutels door te navigeren aan **Ontwikkelaars** > **API** > **Toetsen** in de **Bolt Merchant Dashboard**.

- API-sleutel: Een persoonlijke sleutel die door uw achterste einde wordt gebruikt voor interactie met de Bolt API&#39;s.
- Publishable key: Een sleutel die door uw voorkant wordt gebruikt om met Bolt APIs in wisselwerking te staan.

Zie de [Bolomgevingsdetails](https://help.bolt.com/developers/references/environment-details/#about-keys){target=&quot;_blank&quot;_page voor meer informatie over de API- en Publishable-toetsen voor de [!DNL Express Checkout] extensie.

>[!CAUTION]
>
> U moet API-sleutels maken voor zowel sandbox- als productieomgevingen.

## Betalingsproviders configureren

Volg de stappen in het dialoogvenster [processorinstelling](https://help.bolt.com/integrations/adobe-express-checkout/set-up/){target=&quot;_blank&quot;} pagina Bolt voor ontwikkelaar.

## Extensie inschakelen

1. Op de _Beheer_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** voor toegang tot de configuratiepagina voor uitcheckbeheer.

![Uitdrukkelijke afhandeling](../assets/admin-view.png)

1. In de [!DNL Express Checkout] weergave, instellen **Inschakelen** tot `Yes`.
1. Selecteer de methode (Productie of Sandbox) die u wilt gebruiken.
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

## Hulp vragen

Het instapproces is ontworpen om u door de vereiste stappen te begeleiden voor het instellen en inschakelen van alle [!DNL Express Checkout] functionaliteit. Neem contact op met Adobe Commerce Support voor hulp en vragen.

Zie de [testen en valideren](../express-checkout/testing.md) voor meer informatie.
