---
title: Inschakelen [!DNL Payment Services] voor productie
description: Voltooi het instapproces door [!DNL Payment Services] voor de productie.
exl-id: 3b1269e8-127b-47f8-9738-9722a5737c63
source-git-commit: bfb2b6632fe494d6e392c214f5e3f5a11930c0b2
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 1%

---

# Inschakelen [!DNL Payment Services] voor productie

Nadat de uitbreiding Betalingsdiensten is [geïnstalleerd](install.md), uw instantie is [geconfigureerd en verbonden](connect.md)en u hebt [sandbox instellen](sandbox.md) en getest, kunt u de dienst in productie zetten en voltooien [onboarding](onboard.md).

## Set [!DNL Payment Services] als betalingsmethode

Na u [Configureer uw Commerce Services](connect.md#configure-commerce-services) en [sandbox testen](sandbox.md#enable-sandbox-testing) of [rechtstreekse betalingen](#enable-live-payments), moet u instellen [!DNL Payment Services] als betalingsmethode.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik op **[!UICONTROL Enable Payment Services]**.

   Deze optie is zichtbaar als u nog niet hebt geconfigureerd [!DNL Payment Services] als betalingsmethode voor een of meer van uw Magento-websites.

   U wordt naar het configuratiegebied in Admin geleid met de relevante opties uitgevouwen (**[!UICONTROL Sales]** > **[!UICONTROL Payment Methods]** > _[!UICONTROL Recommended Solutions]_>_[!UICONTROL Payment Services]_), waar u de [!DNL Payment Services] opties als uw [betalingsmethode](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html){target=&quot;_blank&quot;}.

1. In _[!UICONTROL General Configuration]_, set **[!UICONTROL Enable]**tot `Yes`.
1. Set **[!UICONTROL Payment Action]**, voor beide _[!UICONTROL Credit Card Fields]_en_[!UICONTROL PayPal Smart Buttons]_ op een van de volgende wijzen:

   | Instelling | Beschrijving |
   |---|---|
   | `Authorize` | Hiermee geeft u de aankoop goed en houdt u de middelen in de wacht. De hoeveelheid wordt pas opgevraagd wanneer deze door de handelaar wordt &quot;gevangen&quot;. |
   | `Authorize and Capture` | hecht zijn goedkeuring aan de aankoop en de &quot;opname&quot; van de fondsen door de handelaar. |

1. Klik op **[!UICONTROL Save Config]**.
1. Klikken **[!UICONTROL Go to Payment Services]** om terug te keren naar de [!DNL Payment Services] thuis.
1. [Cache wissen](https://docs.magento.com/user-guide/system/cache-management.html){target=&quot;_blank&quot;}.

   Het ontruimen zou na elke configuratieverandering moeten worden gedaan.

Zie [Betalingsservices configureren](configure-admin.md) voor meer informatie over het configureren van creditcardvelden en slimme PayPal-knoppen.

## Volledige merchant aan boord

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klik op **[!UICONTROL Live onboarding]**.

   Deze optie is zichtbaar als u nog niet live on boarding hebt voltooid voor [!DNL Payment Services].

   U krijgt een PayPal-venster te zien.

1. Ga verder met de PayPal-flow, gebruik de verificatiegegevens van uw PayPal-account (niet de gegevens van uw sandbox-account) of meld u aan voor een nieuwe PayPal-account.
1. Ga op de zijbalk Beheerder naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**

   De _[!UICONTROL Live onboarding]_de knop is niet meer zichtbaar en u ziet een &quot;[!UICONTROL Live payments pending]&quot; tekstvak.

   In dat tekstvak wordt je mogelijk ook gevraagd je e-mailadres bij PayPal te bevestigen om de inboeking te voltooien.

1. Als je wordt gevraagd je e-mailadres te bevestigen, controleer dan je e-mail op het bevestigingsbericht dat je van PayPal hebt ontvangen en klik je om je e-mailadres te bevestigen.
1. Ga op de zijbalk Beheerder naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Vernieuw het browservenster.

   Wanneer je PayPal-inboarding is goedgekeurd, wordt een melding weergegeven dat je betalingssysteem zich in de sandboxmodus bevindt en geen live betalingen verwerkt.

   >[!IMPORTANT]
   >
   >Als u de toestemming intrekt om [!DNL Payment Services] voor Adobe Commerce en Magento Open Source voor het verwerken van je betalingen (in de instellingen van je PayPal-rekening) kunnen bestellingen in je winkel niet worden verwerkt door [!DNL Payment Services].

## Betalingsrechten aanvragen van Adobe

Als u live aan boord wilt gaan, moet u betalingsrechten aanvragen bij Adobe:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.
1. Klikken **[!UICONTROL Get Live Payments]** in uw [!DNL Payment Services] dashboard.

   ![Aanvraagrechten](assets/request-entitlements.png)

1. Vul het formulier in.
1. Een lid van het verkoopteam zal contact met u opnemen.

U kunt ook betalingsrechten aanvragen bij Adobe op [business.adobe.com](https://business.adobe.com/resources/payment-services.html).

>[!IMPORTANT]
>
>**Live onboarding** is pas toegankelijk nadat de toeslagrechten zijn goedgekeurd.

## Prijsniveau configureren

Om uw [!DNL Payment Services] _Merchant ID_:

1. Op de _Beheer_ zijbalk, navigeren naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL Recommended Solutions]_uit.
1. In de _[!UICONTROL Payment Services]_in, vouwt u de_[!UICONTROL General Configuration]_ sectie.
1. Selecteer de vereiste _Merchant ID_ en dient deze in bij uw verkoper, die de juiste prijsopgave zal configureren.

## Live betalingen inschakelen

A _productie-handels-id_ wordt automatisch gegenereerd en wordt gevuld in het dialoogvenster [configuratie](configure-admin.md). Wijzig of wijzig deze id niet.

Levende betalingen mogelijk maken:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL Recommended Solutions]_uit.
1. In de _[!UICONTROL Payment Services]_in, vouwt u de_[!UICONTROL General Configuration]_ sectie.
1. Set **[!UICONTROL Method]** tot `Production`.
1. Klik op **[!UICONTROL Save Config]**.
1. [Cache wissen](https://docs.magento.com/user-guide/system/cache-management.html){target=&quot;_blank&quot;}.

   >[!IMPORTANT]
   >
   >Als u de cache niet wist, kunnen klanten tijdens het afrekenen geen PayPal-betalingsopties zien.

Als u teruggaat naar [!DNL Payment Services] Home wordt het bericht voor de betalingsmodus Sandbox niet meer weergegeven omdat u nu live betalingen verwerkt.

Zie [Configureren in de beheerder](configure-admin.md) voor meer configuratieopties.

>[!IMPORTANT]
>
>Als u de toestemming intrekt om [!DNL Payment Services] voor het verwerken van je betalingen (in de instellingen van je PayPal-rekening) kunnen bestellingen in je winkel niet worden verwerkt door [!DNL Payment Services]. Als je de betalingsverwerking opnieuw wilt inschakelen, moet je het instappen opnieuw voltooien.

## Test in productie

Het wordt ten zeerste aanbevolen Betalingen in productie te testen, met echte creditcards en banken, voordat u deze functionaliteit aan kopers beschikbaar maakt.

Zie [Testen en valideren](test-validate.md) voor meer informatie .
