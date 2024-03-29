---
title: "Aan boord van de [!DNL Quick Checkout] voor Adobe Commerce-extensie"
description: "Leer hoe u [!DNL Quick Checkout] kan uw Adobe Commerce-exemplaar ten goede komen en de extensie met succes aan boord installeren en instellen."
exl-id: 8caf746c-e31b-4331-8b0d-ea0f1e545bdd
feature: Checkout, Services
source-git-commit: 6ba5a283d9138b4c1be11b80486826304c63247f
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# [!DNL Quick Checkout] Onboarding

Om te beginnen met het gebruik van de [!DNL Quick Checkout] voor Adobe Commerce-extensie moet u een aantal instapkaartstappen uitvoeren om uw exemplaar te verbinden met onze uitcheckfunctionaliteit.

![Snelle afhandeling](assets/overview-admin-panel.png){width="800" zoomable="yes"}

1. [Extensie ophalen](#get-extension).
1. [Een Merchant-account voor de productie of sandbox maken met [!DNL Bolt]](#create-account-with-bolt). Geef alle vereiste gegevens op om uw identiteit te verifiëren.
1. [Geef de unieke [!DNL API Key] en [!DNL Publishable Key]](#obtain-api-credentials) gegenereerd in [!DNL Bolt].
1. [Een betalingsprovider instellen in het dialoogvenster [!DNL Bolt] account](#configure-payment-providers).
1. [Stelt vervolgkeuzelijst Inschakelen in op Ja](#enable-extension) de extensie activeren.
1. [Definieer uw servicesinstellingen](#complete-admin-configuration) om het [!DNL Quick Checkout] extensie.
1. [Klik op Config opslaan](#enable-live-quick-checkout) om extensie in te schakelen.
1. Van bereik wisselen naar **Hoofdwebsite** en [klik Configure Callback URL](#check-shopper-valid-account) knop.

Als Gainsight is ingeschakeld, activeert het de **Volg de rondleiding** in uw [!DNL Quick Checkout] Beheer, deelvenster over [!DNL Quick Checkout] voor Adobe Commerce:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > **[!UICONTROL Configuration]** > Geavanceerd:

   ![Snelle afhandeling](assets/gainsight-admin.png){width="500" zoomable="yes"}

Als Gainsight niet is ingeschakeld, gaat u verder met de instapprocedure.

Zie de [[!DNL Quick Checkout] Deelvenster Beheer](../quick-checkout/admin-panel.md) voor meer informatie.

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

Voordat u de [!DNL Quick Checkout] in uw Adobe Commerce Admin is het vereist om een [sandbox](https://merchant-sandbox.bolt.com/register?platform=magento2){target="_blank"} and [production](https://merchant.bolt.com/register?platform=magento2){target="_blank"}  handelsrekeningen [!DNL Bolt]. Geef alle vereiste gegevens op om een account te maken in [!DNL Bolt].

Zie de [testen en valideren](../quick-checkout/testing.md) voor meer informatie.

## API-referenties verkrijgen

Als u de opdracht [!DNL Quick Checkout] u hebt [!DNL Bolt] unieke toetsen en [!DNL signing secret]. Verkrijg het volgende [!DNL API keys] door naar **Ontwikkelaars** > **API** > **Toetsen** in de **Bolt Merchant Dashboard**.

- [!DNL API key]: Een persoonlijke sleutel die door uw achterste einde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s.
- [!DNL Publishable key]: Een toets die door de voorzijde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s.
- [!DNL Signing secret]: Wordt gebruikt voor handtekeningverificatie op aanvragen ontvangen van [!DNL Bolt].

  ![Snelle afhandeling](assets/account-credentials.png){width="500" zoomable="yes"}

Zie de [[!DNL Bolt] omgevingsdetails](https://help.bolt.com/developers/references/environment-details/#about-keys){target="_blank"} pagina voor meer informatie over sleutels en het ondertekenen van geheim van [!DNL Bolt] voor de [!DNL Quick Checkout] extensie.

>[!CAUTION]
>
> U moet [!DNL API keys] voor zowel sandbox- als productieomgevingen.

## Betalingsproviders configureren

Volg de stappen in het dialoogvenster [processorinstelling](https://help.bolt.com/integrations/adobe-quick-checkout/set-up/){target="_blank"} ontwikkelaar [!DNL Bolt] pagina.

## Extensie inschakelen

1. Op de _Beheerder_ zijbalk, ga naar **Winkels** > _Instellingen_ > **Configuratie**.
1. Vouw in het linkerdeelvenster uit **Verkoop** en selecteert u **Afhandeling**.
1. In de [!DNL Quick Checkout] weergave, instellen **Inschakelen** tot `Yes`.

![Snelle afhandeling](assets/quick-checkout-view-no-enable.png){width="500" zoomable="yes"}

>[!CAUTION]
>
> Velden voor Snelle uitchecken zijn alleen zichtbaar wanneer **Inschakelen** is ingesteld op `Yes`.

1. Selecteer de methode (Sandbox of Production) die u wilt gebruiken.

   - Sandbox voor test- en ontwikkelingsdoeleinden
   - Productie om transacties met de verwerker van de rechtstreekse betaling te verwerken

1. Valideer referenties nadat u de unieke API hebt opgegeven en [!DNL Publishable keys].

![Snelle afhandeling](assets/quick-checkout-main-view.png){width="500" zoomable="yes"}

Zie de [Instellingen](../quick-checkout/settings-quick-checkout.md) onderwerp voor meer informatie over de configuratieopties voor [!DNL Quick Checkout] voor Adobe Commerce-extensie.

>[!CAUTION]
>
> U moet een unieke API en [!DNL Publishable] toetsen voordat de extensie wordt ingeschakeld, anders zien klanten een betaalformulier en kunnen ze geen bestelling plaatsen.

## Volledige beheerdersconfiguratie

1. Op de _Beheerder_ zijbalk, navigeren naar **Winkels** > **Configuratie** > **Afhandeling** om tot de algemene configuratiepagina van Admin van de Controle toegang te hebben.
1. In de _Service-instellingen_ alle gegevens opgeven die nodig zijn om de extensie in te schakelen.
1. Set _Betalingsactie_ naar een van beide opties:

   - `Authorize`: Leg transactie niet automatisch vast na autorisatie.
   - `Authorize and Capture`: Leg de transactie automatisch vast na machtiging.

Raadpleeg voor meer informatie over de standaardafhandelingsopties van Adobe Commerce de [uitchecken](https://docs.magento.com/user-guide/configuration/sales/checkout.html) onderwerp.

## Live snelle afhandeling inschakelen

Om het [!DNL Quick Checkout] voor Adobe Commerce-extensie:

1. Controleer of de [!UICONTROL Enable] dropdown is ingesteld op **Ja** de extensie activeren.
1. Klikken **Config opslaan**.

## Winkel controleren op geldig account

Controleren of de koper een [!DNL Bolt] account:

1. Van bereik wisselen naar **Hoofdwebsite**.
1. Klik op de knop **Callback-URL configureren** knop. Dit schakelt [!DNL Bolt] om te bepalen of de koper een account heeft. Als zij, OTP pop-up verschijnen.

   >[!CAUTION]
   >
   > Het bereik overschakelen op het **Hoofdwebsite** zorgt ervoor dat de juiste URL is ingesteld. Elke website kan meerdere domeinen hebben.

Zie de [Bereik van site, winkel en weergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings){target="_blank"} onderwerp voor meer informatie over werkingsgebied in Adobe Commerce.

## Service-instellingen configureren

![Snelle afhandeling](assets/service-settings.png){width="500" zoomable="yes"}

1. Set **Afhandeling volgen inschakelen** tot `Yes`.

   >[!CAUTION]
   >
   > Als u deze optie uitschakelt, is dit van invloed op de rapportage, omdat Adobe Commerce geen gegevens over het bijhouden van betalingen mag delen met Bolt.

1. Selecteer de **Volgende werkgebied na aanmelding** optie om de navigatiestroom te wijzigen nadat de klant zich heeft aangemeld. Standaard is deze ingesteld op **Betalingen** pagina.
1. Definiëren als [!DNL Quick Checkout] stelt de **automatische aanmelding** tijdens het afrekenen. Standaard is het ingeschakeld om zich automatisch aan te melden bij de [!DNL Bolt] netwerk.

   >[!NOTE]
   >
   > Zie [Documentatie voor automatische aanmelding inschakelen van bout](https://help.bolt.com/products/embedded/direct-api/auto-login/) voor meer informatie .

## Hulp vragen

Het instapproces is ontworpen om u door de vereiste stappen te begeleiden voor het instellen en inschakelen van de [!DNL Express Checkout] functionaliteit.

Neem via de [Adobe Commerce Help Center](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html) voor alle bijstand.

Zie de [testen en valideren](../quick-checkout/testing.md) voor meer informatie.
