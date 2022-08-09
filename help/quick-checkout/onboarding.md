---
title: '"Aan boord van de [!DNL Quick Checkout] voor Adobe Commerce-extensie"'
description: '"Leer hoe u [!DNL Quick Checkout] kan uw Adobe Commerce-exemplaar ten goede komen en de extensie met succes aan boord installeren en instellen."'
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
source-git-commit: 05d967573f645db1e8473798df279712d6d2dfc9
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 0%

---

# [!DNL Quick Checkout] onboarding

Ga als volgt te werk om aan de slag te gaan [!DNL Quick Checkout] voor Adobe Commerce-extensie moet u een aantal instapkaartstappen uitvoeren om uw exemplaar te verbinden met onze uitcheckfunctionaliteit.

1. [Extensie ophalen](#get-extension).
1. [Een Merchant-account voor de productie of sandbox maken met [!DNL Bolt]](#create-account-with-bolt). Geef alle vereiste gegevens op om uw identiteit te verifiëren.
1. [Geef de unieke [!DNL API Key] en [!DNL Publishable Key]](#obtain-api-credentials) gegenereerd in [!DNL Bolt].
1. [Een betalingsprovider instellen in het dialoogvenster [!DNL Bolt] account](#configure-payment-providers).
1. [Stelt vervolgkeuzelijst Inschakelen in op Ja](#enable-extension) om de extensie te activeren.
1. [Definieer uw servicesinstellingen](#complete-admin-configuration) om het [!DNL Quick Checkout] extensie.
1. [Klik op Config opslaan](#enable-live-quick-checkout) om extensie in te schakelen.
1. Van bereik wisselen naar **Hoofdwebsite** en [klik Configure Callback URL](#check-shopper-valid-account) knop.

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

Als u de opdracht [!DNL Quick Checkout] u hebt [!DNL Bolt] unieke toetsen en [!DNL signing secret]. Verkrijg het volgende [!DNL API keys] door te navigeren naar **Ontwikkelaars** > **API** > **Toetsen** in de **Bolt Merchant Dashboard**.

- [!DNL API key]: Een persoonlijke sleutel die door uw achterste eind wordt gebruikt om met elkaar in wisselwerking te staan [!DNL Bolt] API&#39;s.
- [!DNL Publishable key]: Een toets die door uw voorzijde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s.
- [!DNL Signing secret]: Wordt gebruikt voor handtekeningverificatie op aanvragen die zijn ontvangen van [!DNL Bolt].

   ![Snelle afhandeling](assets/account-credentials.png)

Zie de [[!DNL Bolt] omgevingsdetails](https://help.bolt.com/developers/references/environment-details/#about-keys){target=&quot;_blank&quot;_page voor meer informatie over sleutels en het ondertekenen van een geheim van [!DNL Bolt] voor de [!DNL Quick Checkout] extensie.

>[!CAUTION]
>
> U moet [!DNL API keys] voor zowel sandbox- als productieomgevingen.

## Betalingsproviders configureren

Volg de stappen in het dialoogvenster [processorinstelling](https://help.bolt.com/integrations/adobe-quick-checkout/set-up/){target=&quot;_blank&quot;} -ontwikkelaar [!DNL Bolt] pagina.

## Extensie inschakelen

1. Op de _Beheer_ zijbalk, ga naar **Winkels** > _Instellingen_ > **Configuratie**.
1. Vouw in het linkerdeelvenster uit **Verkoop** en selecteert u **Afhandeling**.
1. In de [!DNL Quick Checkout] weergave, instellen **Inschakelen** tot `Yes`.

![Snelle afhandeling](assets/quick-checkout-view-no-enable.png)

>[!CAUTION]
>
> Velden voor Snelle uitchecken zijn alleen zichtbaar wanneer **Inschakelen** is ingesteld op `Yes`.

1. Selecteer de methode (Sandbox of Production) die u wilt gebruiken.

   - Sandbox voor test- en ontwikkelingsdoeleinden
   - Productie om transacties met de verwerker van de rechtstreekse betaling te verwerken

1. Valideer referenties nadat u de unieke API hebt opgegeven en [!DNL Publishable keys].

![Snelle afhandeling](assets/quick-checkout-main-view.png)

>[!CAUTION]
>
> U moet een unieke API en [!DNL Publishable] toetsen voordat de extensie wordt ingeschakeld, anders zien klanten een betaalformulier en kunnen ze geen bestelling plaatsen.

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

## Winkel controleren op geldig account

Controleren of de koper een [!DNL Bolt] account:

1. Van bereik wisselen naar **Hoofdwebsite**.
1. Klik op de knop **Callback-URL configureren** knop. Dit maakt [!DNL Bolt] om te bepalen of de koper een account heeft. Als zij, OTP pop-up verschijnen.

>[!CAUTION]
>
> Het bereik overschakelen op het **Hoofdwebsite** zorgt ervoor dat de juiste URL is ingesteld. Elke website kan meerdere domeinen hebben.

Zie de [Bereik van site, winkel en weergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings){target=&quot;_blank&quot;} voor meer informatie over het bereik in Adobe Commerce.

## Hulp vragen

Het instapproces is ontworpen om u door de vereiste stappen te begeleiden voor het instellen en inschakelen van de [!DNL Express Checkout] functionaliteit.

Neem via de [Adobe Commerce Help Center](https://support.magento.com/hc/en-us/articles/360000913794-Adobe-Commerce-Help-Center-User-Guide) voor alle bijstand.

Zie de [testen en valideren](../quick-checkout/testing.md) voor meer informatie.
