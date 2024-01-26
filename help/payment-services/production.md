---
title: Inschakelen [!DNL Payment Services] voor productie
description: Voltooi het instapproces door [!DNL Payment Services] voor de productie.
exl-id: 3b1269e8-127b-47f8-9738-9722a5737c63
feature: Payments, Checkout, Configuration, Install
source-git-commit: 5fe23b5aba9ad0a2a6c995fa6ade78f46fe7e3e1
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 0%

---

# Inschakelen [!DNL Payment Services] voor productie

U kunt de dienst in productie zetten en voltooien [onboarding](onboard.md), volgens de stappen in dit onderwerp, na u:

* [Installeren](install.md) De uitbreiding Betalingsdiensten
* [Configureren en verbinden](connect.md) uw instantie
* [Instellen](sandbox.md) en [test](test-validate.md) uw sandbox

## Set [!DNL Payment Services] als betalingsmethode

Na u [Configureer uw Commerce Services](connect.md#configure-commerce-services) en [sandbox testen](sandbox.md#enable-sandbox-testing) of [rechtstreekse betalingen](#enable-live-payments), moet u instellen [!DNL Payment Services] als betalingsmethode.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik op **[!UICONTROL Enable Payment Services]**.

   Deze optie is zichtbaar als u nog niet hebt geconfigureerd [!DNL Payment Services] als betalingsmethode voor een of meer van uw websites.

   U wordt omgeleid naar het instellingengebied in de weergave Home met de relevante opties uitgevouwen (**[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > _[!UICONTROL Settings]_), waar u de [!DNL Payment Services] opties als uw [betalingsmethode](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html){target="_blank"}.

1. In _[!UICONTROL General Configuration]_, set **[!UICONTROL Enable]**tot `Yes`.
1. Set **[!UICONTROL Payment Action]**, voor beide _[!UICONTROL Credit Card Fields]_en_[!UICONTROL PayPal payment buttons]_ op een van de volgende wijzen:

   | Instelling | Beschrijving |
   |---|---|
   | `Authorize` | Hiermee geeft u de aankoop goed en houdt u de middelen in de wacht. De hoeveelheid wordt pas opgevraagd wanneer deze door de handelaar wordt &quot;gevangen&quot;. |
   | `Authorize and Capture` | hecht zijn goedkeuring aan de aankoop en de &quot;opname&quot; van de fondsen door de handelaar. |

   >[!IMPORTANT]
   >
   >[!DNL Payment Services] ondersteunt gedeeltelijke vastleggingen. Een handelaar kan delen van een bestelling gedeeltelijk vastleggen (factureren). U kunt bijvoorbeeld elk item afzonderlijk vastleggen of één item nu en de rest later.

1. Klik op **[!UICONTROL Save]**.
1. Klikken **[!UICONTROL Go to Payment Services]** die naar de [!DNL Payment Services] Home.
1. [Cache wissen](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/cache-management.html).

   Het ontruimen zou na elke configuratieverandering moeten worden gedaan.

Zie [Betalingsservices configureren](settings.md) voor meer informatie over het configureren van creditcardvelden en PayPal-betalingsknoppen.

## Volledige merchant aan boord

De volgende stap om je winkels in staat te stellen om live te gaan met betalingsservices is het voltooien van live onboarding.

Betalingsdiensten bieden [**Geavanceerd** (volledig ondersteund) en **Standaard** (Express Checkout) betalingsopties](../payment-services/payments-options.md#standard-vs-advanced-payments-experience) en instapkaartstromen, afhankelijk van het land waar u werkt en uw voorkeursbetalingservaring.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik op **[!UICONTROL Live onboarding]**.

   Deze optie is zichtbaar als u nog niet live on boarding hebt voltooid voor [!DNL Payment Services].

1. In de _Selecteer uw land_ modal, selecteert u het land vanwaar u werkt.

   Betalingsservices bieden volledige ondersteuning voor alle betalingsopties in [vijf landen](../payment-services/overview.md#availability) momenteel. Betalingsdiensten bieden Express Checkout-mogelijkheden (een subset van betalingsopties) voor alle andere landen die in de landenlijst zijn opgenomen.

   Het land dat u in de lijst kiest, bepaalt de betalingsopties en de instapkaartstroom—[Geavanceerd](#advanced-onboarding) (volledig ondersteund) of [Standaard](#standard-onboarding) (Uitdrukkelijke Afhandeling) - beschikbaar voor u.

>[!TIP]
>
> Als u eenmaal een instapkaartoptie hebt gekozen en doorgaat (Standaard of Geavanceerd), moet u het instappen opnieuw voltooien om een upgrade uit te voeren of de oorspronkelijke selectie te verkleinen.

### Geavanceerd instapniveau

Deze instapkaartstroom is beschikbaar voor handelaren in [volledig gesteunde landen](../payment-services/overview.md#availability).

Nadat het land is geselecteerd:

1. Selecteer in het modaal dat wordt weergegeven **Geavanceerd**.

   Voor de **Standaard** , gaat u verder naar de [Standaardinstapsnelheid](#standard-onboarding).

1. Klikken **Doorgaan**.
1. Ga verder met de PayPal-flow voor de volledig ondersteunde geavanceerde instapmogelijkheden en gebruik daarbij de verificatiegegevens van uw Paypal-account (niet de gegevens van uw sandboxaccount) _of_ Meld u aan voor een nieuw PayPal-account.

>[!IMPORTANT]
>
>**Geavanceerd instapniveau** vereist dat verkopers [betalingsrechten aanvragen](#request-payments-entitlement-from-adobe) om live aan boord te gaan.

### Standaard aan boord

Deze standaard inzake instapkaartstromen is beschikbaar voor handelaren in beschikbare landen waarvoor [alleen Express Checkout-ondersteuning](../payment-services/overview.md#availability) wordt opgegeven.

Nadat het land is geselecteerd:

1. In de _Overeenkomst betalingsdiensten_ modal dat wordt weergegeven, klikt u op de knop **Overeenkomst betalingsdiensten** link naar de Adobe Commerce Payment Services-overeenkomst.
1. In de _Overeenkomst betalingsdiensten_ modal, klik **Ik accepteer**.
1. Ga verder met de PayPal-flow voor Express Checkout bij het instappen, gebruik uw PayPal-accountgegevens (niet de gegevens van uw sandboxaccount) of meld u aan voor een nieuw PayPal-account.

>[!IMPORTANT]
>
>[Apple Betalen en creditcardvelden](../payment-services/payments-options.md) zijn niet beschikbaar voor **Standaard aan boord**.

## E-mailadres bevestigen

1. Ga op de zijbalk Beheerder naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**

   De _[!UICONTROL Live onboarding]_de knop is niet meer zichtbaar en u ziet een &quot;[!UICONTROL Live payments pending]&quot; tekstvak.

   In dat tekstvak wordt je mogelijk ook gevraagd je e-mailadres bij PayPal te bevestigen om de inboeking te voltooien.

1. Als je wordt gevraagd je e-mailadres te bevestigen, controleer dan je e-mail op het bevestigingsbericht dat je van PayPal hebt ontvangen en klik je om je e-mailadres te bevestigen.
1. Ga op de zijbalk Beheerder naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Vernieuw het browservenster.

   Wanneer je PayPal-inboarding is goedgekeurd, wordt een melding weergegeven dat je betalingssysteem zich in de sandboxmodus bevindt en geen live betalingen verwerkt.

   >[!IMPORTANT]
   >
   >Als u de toestemming intrekt om [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] voor het verwerken van je betalingen (in de instellingen van je PayPal-rekening) kunnen bestellingen in je winkel niet worden verwerkt door [!DNL Payment Services]. Op de homepage van Betalingsdiensten verschijnt een waarschuwing over de ingetrokken toestemming.

## Betalingsrechten aanvragen voor Adobe

Als je winkels live wilt gaan, kun je betalingsrechten aanvragen bij Adobe (voor [Alleen geavanceerd instappen](#advanced-onboarding)):

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klikken **[!UICONTROL Get Live Payments]** in uw [!DNL Payment Services] Home.

   ![Aanvraagrechten](assets/request-entitlements.png){width="500" zoomable="yes"}

1. Vul het formulier in.
1. Een lid van het verkoopteam zal contact met u opnemen.

U kunt ook betalingsrechten aanvragen bij Adobe op [business.adobe.com](https://business.adobe.com/resources/payment-services.html).

>[!IMPORTANT]
>
>**Live onboarding** is pas toegankelijk nadat de toeslagrechten zijn goedgekeurd.

## Prijsniveau configureren

Uw [!DNL Payment Services] _Merchant ID_:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik in de weergave Home op **[!UICONTROL Settings]**. Zie [Home](payments-home.md) voor meer informatie .
1. Selecteer de vereiste _Merchant ID_ en dient deze in bij uw verkoper, die de juiste prijsopgave zal configureren.

## Live betalingen inschakelen

A _productie-handels-id_ wordt automatisch gegenereerd en wordt gevuld in het dialoogvenster [configuratie](configure-admin.md). Wijzig of wijzig deze id niet.

Live betalingen inschakelen:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik op Home op **[!UICONTROL Settings]** rechtsboven op de pagina. Zie [Home](payments-home.md) voor meer informatie .
1. In de _[!UICONTROL General Configuration]_sectieset **[!UICONTROL Payment mode]**tot `Production`.
1. Klik op **[!UICONTROL Save]**.
1. [Cache wissen](https://docs.magento.com/user-guide/system/cache-management.html){target="_blank"}.

   >[!IMPORTANT]
   >
   >Als u de cache niet wist, kunnen klanten tijdens het afrekenen geen PayPal-betalingsopties zien.

Als u teruggaat naar [!DNL Payment Services] Home wordt het bericht voor de betalingsmodus Sandbox niet meer weergegeven omdat u nu live betalingen verwerkt.

Zie [Configureren in de beheerder](configure-admin.md) voor opties voor verouderde configuratie.

>[!IMPORTANT]
>
>Als u de toestemming intrekt om [!DNL Payment Services] voor het verwerken van je betalingen (in de instellingen van je PayPal-rekening) kunnen bestellingen in je winkel niet worden verwerkt door [!DNL Payment Services]. Als je de betalingsverwerking opnieuw wilt inschakelen, moet je het instappen opnieuw voltooien. Op de homepage van Betalingsdiensten verschijnt een waarschuwing over de ingetrokken toestemming.

## Test in productie

Het wordt ten zeerste aanbevolen Betalingen in productie te testen, met echte creditcards en banken, voordat u deze functionaliteit aan kopers beschikbaar maakt.

Zie [Testen en valideren](test-validate.md) voor meer informatie .
