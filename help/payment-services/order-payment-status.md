---
title: Betalingsstatusrapport bestelling
description: Gebruik het rapport Betalingsstatus bestellen om de betalingsstatus van uw bestellingen beter te kunnen bekijken en om eventuele problemen op te sporen.
role: User
level: Intermediate
exl-id: 192e47b9-d52b-4dcf-a720-38459156fda4
feature: Payments, Checkout, Orders
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 0%

---

# Betalingsstatusrapport bestelling

[!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] biedt u uitgebreide rapportage zodat u een duidelijk beeld krijgt van de bestellingen en betalingen van uw winkel.

Er zijn twee beschikbare rapportageweergaven voor de betalingsstatus van bestellingen waarmee u snel de betalingsstatus van uw bestellingen kunt bekijken:

* **[Weergave betalingsstatus bestellen](#order-payment-status-data-visualization-view)**—Grafiek beschikbaar op de startpagina van de betalingsdiensten dat een visuele weergave is van de geaggregeerde betalingsstatussen per dag vanuit de weergave van het rapport over de betalingsstatus van de betalingsopdracht
* **[Overzicht van betalingsstatus van bestelling](#order-payment-status-report-view)**—Rapport beschikbaar in betalingsstatus bestelling met gedetailleerde betalingsstatus, facturering, verzending, terugbetaling en geschillenregeling voor alle transacties

De weergave van de betalingsstatus van bestellingen helpt u eenvoudig te begrijpen waar een specifieke bestelling zich binnen de bestelling bevindt om de kasstroom te verwerken. Met deze rapporten kunt u snel bestellingen bekijken (op basis van hun betalingsstatus en betalingsdatum) en mogelijke problemen identificeren.

U kunt betalingstransacties voor bestellingen downloaden in de indeling .csv en deze gebruiken in bestaande software voor boekhouding of orderbeheer.

>[!NOTE]
>
>U kunt geen financiële rapporten weergeven als u [Aan boord en geactiveerd Live-modus](production.md#enable-live-payments) for [!DNL Payment Services].

## Weergave voor visualisatie van betalingsstatusgegevens bestellen

De weergave voor de visualisatie van betalingsstatusgegevens voor bestellingen is beschikbaar in de Home Betalingsservices. Het is een visuele weergave van de geaggregeerde betalingsstatussen per dag vanaf de gedetailleerde tabel [Overzicht van betalingsstatus van bestelling](#order-payment-status-report-view).

Op de _Beheer_ zijbalk, ga naar **Verkoop** > **Betalingsdiensten** om de gegevensvisualisatie te bekijken [overzicht van de betalingsstatussen](#statuses-information).

![Visualisatie van uitbetalingsgegevens in Admin](assets/orderpayment-dataviz.png){zoomable=yes}

Klikken **Rapport weergeven** om naar de gedetailleerde tabel te navigeren [Overzicht van betalingsstatus van bestelling](#order-payment-status-report-view).

### Tijdschema statussen aanpassen

Standaard worden betalingsstatussen van 30 dagen weergegeven.

In de weergave Betalingsstatus bestellen kunt u het tijdpad voor de betalingsstatussen die u wilt bekijken aanpassen door een datumbereik te selecteren:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**. De weergave voor de visualisatie van de betalingsstatus van bestellingen is zichtbaar in de sectie Betalingsstatus bestellen.
1. Klik op de knop **[!UICONTROL Range]** selectorfilter.
1. Kies het toepasselijke datumbereik: 30 dagen, 15 dagen of 7 dagen.
1. Geef de statusinformatie voor de opgegeven datums weer.

### Statusinformatie

De betalingsstatussen voor een geselecteerd datumbereik worden links van de weergave voor betalingsstatus van bestelling weergegeven. De datums voor het geselecteerde datumbereik worden onder aan de weergave weergegeven. Als er op een bepaalde datum geen orders waren, wordt die datum niet weergegeven.

De weergave voor de visualisatie van betalingsstatusgegevens voor bestellingen bevat de volgende informatie.

| Gegevens | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Orders] | Bedragma voor orders in een opgegeven tijdsbestek; gegevens op de Y-as (links) |
| Datumbereik | Datumbereik voor het opgegeven tijdsbestek; gegevens op de X-as (onder) |
| Geautoriseerd | Orde is geautoriseerd |
| Opname aangevraagd | Vastleggen aangevraagd voor bestelling |
| Vastleggen bevestigd | Opname van bestelling voltooid |
| Gedeeltelijk vastleggen | Gedeeltelijk vastgelegde bestelling |
| Vastleggen mislukt | Vastleggen van volgorde mislukt |
| Gestemd | Volgorde ongeldig |

## Overzicht van betalingsstatus van bestelling

De weergave van het rapport Betalingsstatus bestelling is beschikbaar in de weergave Betalingsstatus bestelling van Betalingsdiensten. Het omvat gedetailleerde statussen - betaling, gefactureerd, verscheept, terugbetaling, geschil, en meer-voor alle transacties. De [Weergave voor visualisatie van betalingsstatusgegevens bestellen](#order-payment-status-data-visualization-view) in Payment Services Home is een visuele weergave van de geaggregeerde betalingsstatussen per dag vanuit de weergave van het rapport Betalingsstatus bestellen.

Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Order payment status]** om de gedetailleerde tabel met de betalingsstatusrapporten voor bestellingen weer te geven.

![Betalingstransacties bestellen in de beheerder](assets/orders-report-data.png)

U kunt deze mening, per de secties in dit onderwerp vormen, om de gegevens het best voor te stellen u wilt zien.

U kunt [uitbetalingstransacties downloaden](#download-order-payment-statuses) in een .csv-bestandsindeling voor gebruik in bestaande software voor boekhouding of orderbeheer.

>[!NOTE]
>
>De gegevens in deze tabel worden in aflopende volgorde gesorteerd (`DESC`) standaard gebruikt de `TRANS DATE`. De `TRANS DATE` Dit is de datum en het tijdstip waarop de transactie werd geïnitieerd.

### In het rapport gebruikte gegevens

De [!DNL Payment Services] -module gebruikt bestelgegevens en combineert deze met geaggregeerde betalingsgegevens uit andere bronnen (waaronder PayPal) voor zinvolle en zeer nuttige rapporten.

Bestelgegevens worden geëxporteerd en blijven in de betalingsservice staan. Wanneer u [orderstatussen wijzigen of toevoegen](https://docs.magento.com/user-guide/sales/order-status-custom.html){target="_blank"} or [edit a store view](https://docs.magento.com/user-guide/stores/stores-all-view-edit.html){target="_blank"}, [store](https://docs.magento.com/user-guide/stores/store-information.html){target="_blank"}, of de naam van de website, die gegevens worden gecombineerd met betalingsgegevens en het rapport over de betalingsstatus van de bestelling wordt gevuld met de gecombineerde informatie.

Er zijn twee stappen in dit proces:

1. De index wordt gewijzigd: `ON SAVE` (telkens wanneer orderinfo of opslaginformatie wordt gewijzigd) of `BY SCHEDULE` (op een vooraf gevormd bouwplan), afhankelijk van hoe het binnen wordt gevormd [Indexbeheer](https://docs.magento.com/user-guide/system/index-management.html){target="_blank"} in de Admin.

   Standaard wordt gegevensindexering uitgevoerd `ON SAVE`, wat betekent dat wanneer er iets verandert in de volgorde, de orderstatus, de winkelweergave, de winkel of de website, het opnieuw indexeren onmiddellijk plaatsvindt.

1. De geïndexeerde gegevens worden verzonden naar de betalingsdienst, die vervolgens het rapport over de betalingsstatus van de bestelling invult.

De enige gegevens die voor rapportagedoeleinden worden geëxporteerd en gesorteerd, zijn gegevens die worden gebruikt in het rapport betreffende de betalingsstatus van de betalingsopdracht.

>[!NOTE]
>
>De gegevens in deze tabel worden in aflopende volgorde gesorteerd (`DESC`) standaard gebruikt de `ORDER DATE`. De `ORDER DATE` Dit is de tijdstempel op de datum waarop de bestelling is gemaakt.

#### Gegevens exporteren configureren

Alhoewel, door gebrek, gebeurt het opnieuw indexeren binnen `ON SAVE` wordt aanbevolen om te indexeren in `BY SCHEDULE` in. De `BY SCHEDULE` De index wordt uitgevoerd volgens een uitsnijdschema van één minuut en alle gewijzigde gegevens worden weergegeven in het statusrapport van uw bestelling binnen twee minuten na elke gegevenswijziging. Deze geplande herindexering helpt u om het even welke druk op uw opslag te verminderen, vooral als u een groot volume van inkomende orden hebt, omdat het op een programma gebeurt (niet aangezien elke orde wordt geplaatst).

U kunt de indexmodus wijzigen—`ON SAVE` of `BY SCHEDULE`—[in de beheerder](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target="_blank"}.

Om te leren hoe te om de gegevensuitvoer te vormen, zie [Configuratie van opdrachtregel](configure-cli.md#configure-data-export).

### Gegevensbron selecteren

In de weergave van het rapport Betalingsstatus bestellen kunt u de gegevensbron selecteren—_[!UICONTROL Live]_of_[!UICONTROL Sandbox]_—waarvoor u rapportresultaten wilt zien.

![Selectie gegevensbronnen](assets/datasource.png){width=400px}

Indien _[!UICONTROL Live]_is de geselecteerde gegevensbron, kunt u rapportinformatie voor uw opslag zien die gebruikt [!DNL Payment Services] in de productiemodus. Indien_[!UICONTROL Sandbox]_ De geselecteerde gegevensbron is, kunt u rapportinformatie voor zandbakwijze zien.

Gegevensbronselecties werken als volgt:

* Als u geen winkels hebt die [!DNL Payment Services] in Live-modus wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Sandbox]_.
* Als u opslagruimten (één of meerdere) hebt die [!DNL Payment Services] in Live-modus wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Live]_.
* De uitvoer van het rapport respecteert altijd de gegevensbronselectie.

Om de gegevensbron voor uw te selecteren [!UICONTROL Order Payment Status] rapport:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Klikken **[!UICONTROL Data source]** en selecteert u _[!UICONTROL Live]_of_[!UICONTROL Sandbox]_.

   De rapportresultaten regenereren op basis van de geselecteerde gegevensbron.

### Datumtijdframe aanpassen

In de weergave van het rapport Betalingsstatus bestellen kunt u de tijdsperiode van de statussen die u wilt weergeven aanpassen door specifieke datums te selecteren. Standaard worden de betalingsstatussen van 30 dagen voor bestellingen weergegeven in het raster.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Klik op de knop **[!UICONTROL Order dates]** Kalenderkiezerfilter.
1. Kies het toepasselijke datumbereik.
1. Bekijk de betalingsstatussen voor de bestelling voor de opgegeven datums in het raster.

### Kolommen tonen en verbergen

Het rapport Betalingsstatus bestelling toont standaard alle beschikbare kolommen met informatie. U kunt, echter, aanpassen welke kolommen u in uw rapport ziet.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Klik op de knop _Kolominstellingen_ icon (![pictogram kolominstellingen](assets/column-settings.png)).
1. Als u wilt aanpassen welke kolommen u in het rapport ziet, schakelt u de kolommen in de lijst in of uit.

   In het rapport Betalingsstatus bestellen worden direct alle wijzigingen weergegeven die u hebt aangebracht in het menu Kolominstellingen. De kolomvoorkeuren worden opgeslagen en blijven van kracht als u niet in de rapportweergave navigeert.

### Statussen weergeven

De weergave van het rapport Betalingsstatus bestellen toont een uitgebreide transactiestatus en informatie over de betalingsstatus voor elke betalingsopdracht.

#### Transactiestatus

Standaard worden de betalingsstatussen van 30 dagen voor bestellingen weergegeven in het raster.

Naar links en rechts schuiven om weer te geven [betalingsstatus bestellen](#column-descriptions), inclusief opdrachtdatum, geoorloofde datum, facturering, verzending, status van betaling en meer.

Het aantal rijen dat wordt geretourneerd in een zoekopdracht of dat wordt weergegeven in de standaardbetalingsstatus van 30 dagen van een bestelling, wordt boven het weergaveraster voor betalingsstatus van bestelling weergegeven naast het filter Kalender voor orderdatums.

#### Betaalstatus

In de statuskolom Betalen wordt de huidige status van een betaling weergegeven. A `Capture failed` betaling geeft een status van een rood waarschuwingsbericht en een `Voided` bij betaling wordt een grijze waarschuwingsstatus weergegeven.

#### Terugbetalingsstatus

In de statuskolom Restitutie wordt de huidige status voor elke restitutie weergegeven. A `Capture failed` betaling geeft een status van een rood waarschuwingsbericht en een `Voided` bij betaling wordt een grijze waarschuwingsstatus weergegeven.

### Rapportgegevens bijwerken

De weergave van het rapport Betalingsstatus bestelling toont een _[!UICONTROL Last updated]_timestamp die de laatste tijd toont dat de rapportinformatie werd bijgewerkt. Standaard worden de gegevens in het rapport Betalingsstatus van bestelling elke drie uur automatisch vernieuwd.

U kunt ook handmatig afdwingen dat de gegevens in het rapport Betalingsstatus van bestelling worden vernieuwd om de meest actuele rapportgegevens te zien.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Klik op de knop _Vernieuwen_ icon (![vernieuwingspictogram](assets/refresh-button-med.png)).

   De gegevens van het rapport met de betalingsstatus van de bestelling worden vernieuwd, en *[!UICONTROL Update complete]* de bevestiging verschijnt en de recentste informatie is aanwezig in het net.

### Geschillen bekijken

Je kunt geschillen over bestellingen van je winkel bekijken en naar het PayPal Resolution Center navigeren om actie te ondernemen vanuit het statusrapport voor bestellingen.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Ga naar de **[!UICONTROL Disputes column]**.
1. Geschillen voor een bepaalde bestelling bekijken en bekijken [de status van het geschil](#order-payment-status-information).
1. Klik op de link voor het geschil-ID (beginnen met _PP-D-_) om naar de [PayPal-afwikkelingscentrum](https://www.paypal.com/us/smarthelp/article/what-is-the-resolution-center-faq3327).
1. Indien nodig passende maatregelen nemen voor het geschil.

   Klik op de kolomkop Geschillen oplossen als u geschillen wilt sorteren op status.

### Betalingsstatus van bestellingen downloaden

U kunt een CSV-bestand downloaden met alle statussen die zichtbaar zijn in het weergaveraster voor betalingsstatus van bestelling, of u nu de standaardstatus van 30 dagen bekijkt of een aangepast tijdframe.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Order payment status]**.
1. Als u statussen wilt zien gedurende een ander tijdsbestek dan de laatste 30 dagen, [de tijdlijn voor het datumbereik voor uw statussen aanpassen](#customize-dates-timeframe).
1. Klik op de knop _Downloaden_ (![downloadpictogram](assets/icon-download.png)).

De betalingsstatus van uw bestelling wordt gedownload in de indeling .csv.

<!-- ## Default order payment status timeframes

These order payment status timeframes are currently available in [!DNL Payment Services].

| Report       | Description          |
| ------------ | -------------------- |
| Yesterday | Available from the Order payment status dates selector, this shows information for the prior date. |
| | Today | Available from the Order payment status dates selector, this shows information for the current day. |
| Last 7 days | Available from the Order payment status dates selector, this shows information for the last seven days. |
| Last 30 days | Available from the Order payment status dates selector and by default in the Order payment statuses view, this shows information for the last 30 days. |
| Last 90 days | Available from the Order payment status dates selector, this shows information for the last 90 days. |
| Year to date | Available from the Order payment status dates selector, this shows information for the the entire year to date. |
| Custom range | Available from the Order payment status dates selector, this can be filtered to show a custom date range. |
-->

#### Statusinformatie

Betalingsstatusrapporten voor bestellingen bevatten de volgende informatie.

| Kolom | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Order ID] | Handelsorder-ID<br> <br>Verwante items weergeven [orderinfo](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, klikt u op de id. |
| [!UICONTROL Order Date] | Tijdstempel van besteldatum |
| [!UICONTROL Authorized Date] | Tijdstempel van betalingsvergunning |
| [!UICONTROL Order Status] | Huidige handel [orderstatus](https://docs.magento.com/user-guide/sales/order-status.html){target="_blank"} |
| [!UICONTROL Invoiced] | Factuurstatus van de bestelling—*[!UICONTROL No]*, *[!UICONTROL Partial]*, of *[!UICONTROL Yes]* |
| [!UICONTROL Shipped] | Verzendstatus van bestelling—*[!UICONTROL No]*, *[!UICONTROL Partial]*, of *[!UICONTROL Yes]* |
| [!UICONTROL Order Amt] | Totaalbedrag van de beschikking |
| [!UICONTROL Cur] | Valutatype van order |
| [!UICONTROL Pay Status] | Status van betaling voor een specifieke bestelling |
| [!UICONTROL Paid Amt] | Op bestelling betaald bedrag |
| [!UICONTROL Cur] | Valutatype van het op een bestelling betaalde bedrag |
| [!UICONTROL Refund Status] | Status van een terugbetaling op een bestelling (zoals informatie uit geretourneerde bedragen, RMA&#39;s en kredietmemo&#39;s)—   *[!UICONTROL Requires refund]*, *[!UICONTROL Refund requested]*, *[!UICONTROL Refunded]*, *[!UICONTROL Refund failed]*, of *[!UICONTROL Voided]* |
| [!UICONTROL Refund Amount] | Totaal terugbetaald bedrag voor een bestelling |
| [!UICONTROL Cur] | Valutatype van het bedrag dat voor een order wordt terugbetaald |
| [!UICONTROL Disputes] | Status van een geschil over een bestelling (informatie uit geschillen en terugbetalingen)—*[!UICONTROL Open]*, *[!UICONTROL Waiting for buyer response]*, *[!UICONTROL Waiting for seller response]*, *[!UICONTROL Under review]*, *[!UICONTROL Resolved]*, of *[!UICONTROL Other]* |
| [!UICONTROL Payment Method] | Bij de handelstransactie gebruikte betalingsmethode voor een order |
| [!UICONTROL Website] | Website van waaruit de bestelling is geplaatst |
| [!UICONTROL Store] | Winkel van waaruit de bestelling is geplaatst |
| [!UICONTROL Store View] | Winkelweergave van waaruit de bestelling is geplaatst |
