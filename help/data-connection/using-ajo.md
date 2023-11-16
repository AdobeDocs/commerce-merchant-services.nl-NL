---
title: Adobe Journey Optimizer gebruiken om een afgebroken winkelwagentje te verzenden
description: Leer hoe u Adobe Journey Optimizer kunt gebruiken om een verlaten winkelwagentje-e-mail te verzenden.
role: Admin, Developer
feature: Personalization, Integration
exl-id: 5e4e7c0a-c00b-4278-bd73-6b6f2fcbe770
source-git-commit: f90ef4d2732a0b0676e0899712f94b41a1c2d85a
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 0%

---

# Adobe Journey Optimizer gebruiken om een e-mailbericht voor verlaten winkelwagentje te verzenden

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) helpt u de handelservaring voor uw kopers personaliseren. U kunt Journey Optimizer bijvoorbeeld gebruiken om geplande marketingcampagnes te maken en te leveren, zoals wekelijkse promoties voor een detailhandel, of een verlaten winkelwagentje-e-mail genereren als een klant een product aan een winkelwagentje heeft toegevoegd maar het afrekenproces vervolgens niet heeft voltooid.

Als u deze stappen uitvoert, kunt u leren hoe u naar een `checkout` -gebeurtenis die door uw instantie Commerce is gegenereerd en op die gebeurtenis in Journey Optimizer reageert om een verlaten e-mailbericht met een winkelwagentje te maken.

>[!IMPORTANT]
>
>Voor demonstratiedoeleinden moet u ervoor zorgen dat u de omgeving van uw handels-sandbox gebruikt. Dit zorgt ervoor dat de opslag en de gegevens van de achterkantoorgebeurtenis u naar Experience Platform verzendt uw gegevens van de productiegebeurtenis niet verdunnen.

## Vereisten

Voordat u met deze stappen begint, moet u controleren of:

- U bent ingericht voor Adobe Journey Optimizer
- U [geconfigureerd](connect-data.md) de [!DNL Data Connection] extension
- U [bevestigd](connect-data.md#confirm-that-event-data-is-collected) dat uw de gebeurtenisgegevens van de Handel bij de rand van het Experience Platform aankomen

## Stap 1: Maak een gebruiker in de omgeving van de handels-sandbox

Maak een gebruiker in uw sandbox-omgeving en bevestig dat de gegevens van die gebruikersaccount in het Experience Platform worden weergegeven. Zorg ervoor dat de e-mail die u hebt opgegeven geldig is, zoals die later in deze sectie wordt gebruikt om de verlaten e-mail met het winkelwagentje te verzenden.

1. Meld u aan of maak een account in de omgeving van de handels-sandbox.

   ![Aanmelden bij uw testaccount](assets/sign-in-account.png){width="700" zoomable="yes"}

   Met de [!DNL Data Connection] Deze accountgegevens worden geïnstalleerd en geconfigureerd en als een profiel naar het Experience Platform verzonden.

1. Bevestig dat de gegevens van uw gebruikersaccount worden weergegeven in het dialoogvenster **[!UICONTROL Profile]** Experience Platform.

   Ga naar **[!UICONTROL Profiles]** in de Adobe Experience Platform. Klikken **[!UICONTROL Detail]** in het profiel om het profiel weer te geven dat u hebt gemaakt.

   ![Profiel bevestigen](assets/check-event-profile.png){width="700" zoomable="yes"}

## Stap 2: Gebeurtenissen weergeven in Journey Optimizer

In uw zandbakmilieu van de Handel, bekijk productpagina&#39;s, voeg punten aan een kar toe, en diverse andere activiteiten een verkoper zou uitvoeren. Deze activiteiten activeren gebeurtenissen op je winkelcentrum. U kunt nu bevestigen dat deze gebeurtenissen naar Journey Optimizer stromen.

1. Starten [Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).
1. Selecteren **[!UICONTROL Profiles]**.
1. Set **[!UICONTROL Identity namespace]** tot `Email`.
1. Stel de **[!UICONTROL Identity value]** naar uw e-mailadres.
1. Selecteer uw profiel en selecteer vervolgens het **[!UICONTROL Events]** tab.

   ![Gebeurtenisdetails controleren](assets/check-event-details.png){width="700" zoomable="yes"}

   Zoek naar `commerce.checkouts` -gebeurtenis en controleer de payload van de gebeurtenis:

   ```json
   "personID": "84281643067178465783746543501073369488", 
   "eventType": "commerce.checkouts", 
   "_id": "4b41703f-e42e-485b-8d63-7001e3580856-0", 
   "commerce": { 
       "cart": {}, 
       "checkouts": { 
           "value": 1 
       } 
   ```

   Zoals u kunt zien, bevat de volledige gebeurtenislading rijke gebeurtenisgegevens. In de volgende sectie configureert u gebeurtenissen in Journey Optimizer om te luisteren naar en te reageren op de `commerce.checkouts` -gebeurtenis die is gegenereerd door uw winkel Commerce.

## Stap 3: gebeurtenissen configureren in Journey Optimizer

Twee gebeurtenissen in Journey Optimizer configureren: één gebeurtenis luistert naar de gebeurtenis `commerce.checkouts` De gebeurtenis van de Handel, en andere is een basisonderbrekingsgebeurtenis die voor een specifieke hoeveelheid tijd wacht om over te gaan alvorens een verlaten kart e-mail teweeg te brengen.

### Een listenergebeurtenis maken

1. Starten [Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

1. Klikken **[!UICONTROL Configurations]** onder de **[!UICONTROL Administration]** in het linkerdeelvenster.

1. In de **[!UICONTROL Events]** tegel, klikken **[!UICONTROL Manage]**.

   ![Journey Optimizer-gebeurtenisconfiguratie](assets/ajo-config.png){width="700" zoomable="yes"}

1. Op de **[!UICONTROL Events]** pagina, klikt u **[!UICONTROL Create Event]**.

1. Stel de gebeurtenis als volgt in in de rechternavigatie:

   1. Stel de **[!UICONTROL Name]** tot: `firstname_lastname_checkout`.
   1. Set **[!UICONTROL Type]** tot **[!UICONTROL Unitary]**.
   1. Set **[!UICONTROL Event id typ]e** tot **[!UICONTROL Rule based]**.
   1. Set **[!UICONTROL Schema]** aan uw Commerce [schema](update-xdm.md).
   1. Selecteren **[!UICONTROL Fields]** en in de **[!UICONTROL Fields]** Selecteer de velden die nuttig zijn voor deze gebeurtenis. Selecteer bijvoorbeeld alle velden onder de **[!UICONTROL Product list items]**, **[!UICONTROL Commerce]**, **[!UICONTROL eventType]**, en **[!UICONTROL Web]**.
   1. Klikken **[!UICONTROL OK]** om de geselecteerde velden op te slaan.
   1. Klik in het dialoogvenster **[!UICONTROL Event id condition]** veld en een voorwaarde maken voor `eventType` is gelijk aan `commerce.checkouts` EN `personalEmail.address` is gelijk aan het e-mailadres dat u hebt gebruikt toen u het profiel in de vorige sectie maakte.

      ![Voorwaarde Journey Optimizer-set](assets/ajo-set-condition.png){width="700" zoomable="yes"}

   1. Klik op **[!UICONTROL OK]**.
   1. Klikken **[!UICONTROL Save]** om uw gebeurtenis op te slaan.

### Een time-outgebeurtenis maken

1. Maak een gebeurtenis in Journey Optimizer zoals u dat eerder hebt gedaan.

1. Stel de gebeurtenis als volgt in in de rechternavigatie:

   1. Stel de **[!UICONTROL Name]** tot: `firstname_lastname_timeout`.
   1. Set **[!UICONTROL Type]** tot **[!UICONTROL Unitary]**.
   1. Set **[!UICONTROL Event id typ]e** tot **[!UICONTROL Rule based]**.
   1. Set **[!UICONTROL Schema]** aan uw Commerce [schema](update-xdm.md).
   1. Stel de **[!UICONTROL Schema]**, **[!UICONTROL Fields]**, en **[!UICONTROL Event id condition]** op dezelfde manier als hierboven.
   1. Klikken **[!UICONTROL Save]** om uw gebeurtenis op te slaan.

Met deze twee gevormde gebeurtenissen, creeer een reis die een verlaten kart e-mail verzendt.

## Stap 4: Een afrekenreis maken

Maak een reis die luistert naar de `commerce.checkouts` en verzendt dan een verlaten wagente-mail nadat een gespecificeerde hoeveelheid tijd is overgegaan.

1. Selecteer in Journey Optimizer **[!UICONTROL Journeys]** krachtens **J[!UICONTROL OURNEY MANAGEMENT]**.
1. Klik op **[!UICONTROL Create Journey]**.
1. Geef de naam van uw reis op.
1. Klikken **[!UICONTROL OK]** om de reis te redden.
1. In de linkernavigatie onder de **[!UICONTROL EVENTS]** -sectie, zoek naar de uitcheckgebeurtenis die u eerder hebt gemaakt: `firstname_lastname_checkout` en sleep deze naar het canvas.

   >[!TIP]
   >
   >Als u dubbelklikt op de gebeurtenis, wordt deze automatisch toegevoegd aan het canvas.

1. Zoek naar de timeout-gebeurtenis en voeg deze toe aan het canvas.
1. Dubbelklik op de time-outgebeurtenis.

   1. In de **[!UICONTROL Timeout]** selecteert u de **[!UICONTROL Define the event time]** selectievakje.
   1. In de **[!UICONTROL Wait for]** veld enter `1` en `Minute`.
   1. Selecteer de **[!UICONTROL Set a timeout path]** selectievakje.

   Met deze time-outconfiguratie activeert een winkelier die een afhandeling uitvoert maar de bestelling niet binnen één minuut voltooit, deze time-outvertakking. In een echte productieomgeving zou je dit voor een langere periode instellen, bijvoorbeeld 24 uur.

1. In de linkernavigatie onder **[!UICONTROL ACTIONS]**, voegt u de **[!UICONTROL Email]** actie aan de onderbrekingstak. Uw reis zou als het volgende moeten kijken:

   ![Journey Optimizer Canvas](assets/ajo-canvas.png){width="700" zoomable="yes"}

### Een verlaten winkelwagentje maken

Maak een verlaten wagentje-e-mail die wordt verzonden wanneer een verlaten wagentje wordt ontdekt.

1. Dubbelklik in de hierboven gemaakte reis op de knop **[!UICONTROL Email]** op het canvas.

1. Volg de [stappen](https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/personalization-use-cases/personalization-use-case-helper-functions.html#configure-email) in de handleiding van Journey Optimizer om de verlaten wagentje-e-mail te creëren.

U hebt nu een reis in Journey Optimizer die luistert naar de `commerce.checkouts` gebeurtenis van uw winkel van de Handel en een verlaten karretje e-mail die wordt verzonden nadat een periode is overgegaan. In de volgende sectie gaat u de reis testen.

## Stap 5: De gebeurtenis voor het uitchecken in real-time activeren

In deze sectie test u de gebeurtenis in real-time.

1. Schakel in Journey Optimizer de testmodus in.

   ![Testmodus inschakelen](assets/ajo-enable-test.png){width="700" zoomable="yes"}

1. Als u deze reis in real-time wilt testen, opent u een ander browsertabblad en gaat u naar uw website Sandbox Commerce.

   1. Voeg een product toe aan uw winkelwagentje.
   1. Ga naar de uitcheckpagina.
   1. Laat vanaf de afhandelingspagina het winkelwagentje los door terug te gaan naar de hoofdpagina of uw tab te sluiten.

      De reis wordt nu in gang gezet. Om te bevestigen, open het lusje dat uw reis in Journey Optimizer heeft. Er moet een groene pijl verschijnen die het pad weergeeft dat de gebruiker heeft doorlopen.

1. Controleer uw Postvak IN op de e-mail.
