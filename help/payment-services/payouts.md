---
title: Uitbetalingsrapport
description: Gebruik het rapport Uitbetalingen voor volledige transparantie met betrekking tot het bedrag van de betaling, het verwerkte volume en gedetailleerde rapportage over het transactieniveau voor financiële afstemming.
role: User
level: Intermediate
exl-id: f3f99474-cd28-4c8f-b0ea-dca8e014b108
feature: Payments, Checkout
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 0%

---

# Uitbetalingsrapport

[!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] biedt u uitgebreide rapportage zodat u een duidelijk beeld krijgt van de bestellingen en betalingen van uw winkel.

Er zijn twee beschikbare meningen van de het melden van Uitbetalingen om u toe te laten om diepgaande informatie over al uw uitbetalingen te zien:

* **[Weergave gegevensvisualisatie uitbetaling](#payouts-data-visualization-view)**—Grafiek beschikbaar op het Huis van Betalingsdiensten dat een visuele vertegenwoordiging van samengevoegde bedragen per dag van de mening van het Verslag van Uitbetalingen is
* **[Weergave uitbetalingsrapport](#payouts-report-view)**—Rapport beschikbaar in Betalingen waarin gedetailleerde uitbetalingsinformatie voor alle transacties wordt weergegeven

In de weergave Uitbetalingen worden uitgebreide uitbetalingsgegevens in één oogopslag weergegeven, zodat u volledige transparantie kunt krijgen over het bedrag van de betaling, het verwerkte volume en gedetailleerde rapportage over het transactieniveau voor financiële afstemming.

>[!NOTE]
>
>Uitbetalingsrapporten tonen alleen orders die zijn vastgelegd (betalingsactie is ingesteld op [`Authorize and Capture`](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/production.html#set-payment-services-as-payment-method))—of [gemarkeerd als `Invoiced`](https://docs.magento.com/user-guide/sales/invoice-create.html).

## Weergave gegevensvisualisatie uitbetaling

De weergave voor de visualisatie van betalingsgegevens is beschikbaar in de startpagina van Betalingsservices. Het is een visuele weergave van de geaggregeerde bedragen per dag vanaf de gedetailleerde tabel [Weergave uitbetalingsrapport](#payouts-report-view).

Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** om het gegevensvisualisatieschema van crediteringen tegenover debiteringen en de bewegende gemiddelden in de loop der tijd te zien.

![Visualisatie van uitbetalingsgegevens in Admin](assets/payouts-report.png){zoomable=yes}

Klikken **[!UICONTROL View Report]** om naar de gedetailleerde tabel te navigeren [Weergave uitbetalingsrapport](#payouts-report-view).

### Tijdschema voor transacties aanpassen

Standaard worden 30 dagen transacties weergegeven.

In de visualisatieweergave voor betalingsgegevens kunt u het tijdkader voor de uitbetalingstransacties die u wilt bekijken aanpassen door een datumbereik te selecteren:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**. De weergave van de gegevensvisualisatie van Uitbetalingen is zichtbaar in de sectie Uitbetalingen.
1. Klik op de knop **[!UICONTROL Range]** selectorfilter.
1. Kies het toepasselijke datumbereik: 30 dagen, 15 dagen of 7 dagen.
1. Bekijk de transactiegegevens voor de opgegeven datums.

### Transactiegegevens

De transactiebedragen voor een geselecteerd datumbereik worden links van de weergave Betalingsgegevens weergegeven. De datums voor het geselecteerde datumbereik worden onder aan de weergave weergegeven. Als er op een bepaalde datum geen uitbetalingen zijn gedaan, wordt die datum niet weergegeven.

De weergave voor de visualisatie van betalingsgegevens bevat de volgende informatie.

| Gegevens | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Transaction amount] | Bedragma voor transacties binnen een bepaald tijdsbestek; gegevens op de Y-as (links) |
| Datumbereik | Datumbereik voor het opgegeven tijdsbestek; gegevens op de X-as (onder) |
| Krediet | Betalingen voor het opgegeven tijdsbestek |
| Debet | Debiteringen (terugbetalingen) voor het opgegeven tijdsbestek |
| Gemiddeld verplaatsen | Weergave van de gemiddelde uitbetaling voor elke datum in het opgegeven tijdsbestek |
| Netto voor bereik | Netto uitbetalingsbedrag voor het opgegeven tijdkader (bereik) |

## Weergave uitbetalingsrapport

De weergave van het betalingsrapport is beschikbaar in de weergave Uitbetalingen van betalingsservices. Deze bevat alle beschikbare informatie over de betalingen voor je winkel(s). De [Weergave gegevensvisualisatie uitbetaling](#payouts-data-visualization-view) in Payment Services Home is een visuele weergave van de geaggregeerde bedragen per dag in deze meer gedetailleerde rapportweergave.

Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]** om de gedetailleerde tabelweergave van het uitbetalingsrapport te bekijken.

![Betalingstransacties in de beheerder](assets/payouts-report-new.png){zoomable=yes}

U kunt deze mening, per de secties in dit onderwerp vormen, om de gegevens het best voor te stellen u wilt zien.

Zie de gekoppelde handelsorder en transactie-id&#39;s, transactiebedragen, betalingsmethode per transactie en meer, allemaal in het betalingsrapport in de beheerder.

U kunt [uitbetalingstransacties downloaden](#download-transactions) in een .csv-bestandsindeling voor gebruik in bestaande software voor boekhouding of orderbeheer.

>[!NOTE]
>
>De gegevens in deze tabel worden in aflopende volgorde gesorteerd (`DESC`) standaard gebruikt de `TRANS DATE`. De `TRANS DATE` Dit is de datum en het tijdstip waarop de transactie werd geïnitieerd.

### Gegevensbron selecteren

In de mening van het rapport van Uitbetalingen kunt u de gegevensbron selecteren—_[!UICONTROL Live]_of_[!UICONTROL Sandbox]_—waarvoor u rapportresultaten wilt zien.

![Selectie gegevensbronnen](assets/datasource.png){width=400px}

Indien _[!UICONTROL Live]_is de geselecteerde gegevensbron, kunt u rapportinformatie voor opslag op productiemodus zien. Indien_[!UICONTROL Sandbox]_ Als de geselecteerde gegevensbron is, kunt u rapportinformatieopslag op zandbakwijze zien.

Gegevensbronselecties werken als volgt:

* Als u geen opslagruimten hebt die zich in de live modus bevinden, wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Sandbox]_.
* Als u opslagruimten (een of meerdere opslagruimten) in de live modus hebt, wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Live]_.
* De uitvoer van het rapport respecteert altijd de gegevensbronselectie.

U kunt als volgt de gegevensbron selecteren voor het rapport Betalingsstatus bestelling:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Klikken **[!UICONTROL Data source]** en selecteert u _[!UICONTROL Live]_of_[!UICONTROL Sandbox]_.

   De rapportresultaten regenereren op basis van de geselecteerde gegevensbron.

### Transacties weergeven

Standaard worden 30 dagen transacties weergegeven.

Het aantal rijen dat wordt geretourneerd in een zoekopdracht of dat wordt weergegeven in de standaard 30 dagen aan transacties, wordt boven het weergaveraster Uitbetalingen weergegeven naast het filter voor de kalenderkiezer voor Transactiedata.

Naar links en rechts schuiven om weer te geven [informatie voor elke betalingstransactie](#column-descriptions) in het dagelijkse rapport, met inbegrip van de transactiedatum, referentie-id, factuurnummer en betalingsmethode-details.

#### Tijdschema voor transacties aanpassen

In de weergave van het rapport Uitbetalingen kunt u het tijdpad voor de uitbetalingstransacties die u wilt bekijken aanpassen door specifieke datums in te voeren of een datumbereik te selecteren in de datumkiezer:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Klik op het selectiefilter Transactiedata agenda.
1. Kies het toepasselijke datumbereik.
1. Bekijk de uitbetalingsstatussen in het raster voor de opgegeven datums.

### Kolommen tonen en verbergen

In de weergave van het rapport Uitbetalingen worden standaard de meeste beschikbare kolommen met informatie weergegeven. U kunt echter aanpassen welke kolommen u in het rapport ziet.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Payouts]**.
1. Klik op de knop _Kolominstellingen_ icon (![pictogram kolominstellingen](assets/column-settings.png)).
1. Als u wilt aanpassen welke kolommen u in het rapport ziet, schakelt u de kolommen in de lijst in of uit.

   In de weergave van het rapport Uitbetalingen worden direct alle wijzigingen weergegeven die u hebt aangebracht in het menu Kolominstellingen. De kolomvoorkeuren worden opgeslagen en blijven van kracht als u niet in de rapportweergave navigeert.

### Transacties downloaden

U kunt een CSV-bestand downloaden dat alle transacties bevat die zichtbaar zijn in het raster van de weergave Uitbetalingen.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. [Tijdschema datumbereik voor uw transacties aanpassen](#customize-transactions-timeframe).
1. Klik op de knop _Downloaden_ (![](assets/icon-download.png)).

Uw uitbetalingstransacties worden gedownload in de CSV-indeling.

### Kolombeschrijvingen

Uitbetalingsrapporten bevatten de volgende informatie.

| Kolom | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Provider] | Betalingsaanbieder |
| [!UICONTROL Provider trans] | Transactie-id |
| [!UICONTROL Trans date] | Datum en tijdstip waarop de transactie is gestart |
| [!UICONTROL Type] | Transactietype—*[!UICONTROL PAYMENT]*, *[!UICONTROL BONUS]*, *[!UICONTROL CHARGEBACK]*, *[!UICONTROL CORRECTION]*, *[!UICONTROL CURRENCY_CONVERSATION]*, *[!UICONTROL DEPOSIT]*, *[!UICONTROL DISBURSEMENT]*, *[!UICONTROL DISPUTE]*, *[!UICONTROL FEES]*, *[!UICONTROL HOLD]*, *[!UICONTROL HOLD_RELEASE]*, *[!UICONTROL INCENTIVES]*, *[!UICONTROL OTHERS]*, *[!UICONTROL RECOUP]*, *[!UICONTROL REFUND]*, *[!UICONTROL REVERSAL]*, *[!UICONTROL WITHDRAWAL]* <br> <br>Zie [Transactietypen](#transaction-types) voor meer informatie . |
| [!UICONTROL Status] | Huidige status van de transactie—*[!UICONTROL SUCCESS]*, *[!UICONTROL DENIED]*, *[!UICONTROL PENDING]* |
| [!UICONTROL Code] | Transactiecode die een creditering aangeeft (*CR*) of Debet (*DR*) |
| [!UICONTROL Reference ID] | Oorspronkelijke transactie-id waarvoor deze gebeurtenis verband houdt |
| [!UICONTROL Invoice] | Factuur-id (één per bestelling) van de transactie |
| [!UICONTROL Commerce order] | Handelsorder-ID <br> <br>Verwante items weergeven [orderinfo](https://docs.magento.com/user-guide/sales/orders.html), klikt u op de id. |
| [!UICONTROL Commerce trans] | Transactie-id voor handel |
| [!UICONTROL Pay method] | Type creditcard—*[!UICONTROL BANK]*, *[!UICONTROL PAYPAL]*, *[!UICONTROL CREDIT_CARD]*—en bijbehorende kaartprovider (zoals *Visa* of *MasterCard*) |
| [!UICONTROL TRANS AMT] | Bedrag van de transactie |
| [!UICONTROL CUR] | Valuta-eenheid voor transactiebedrag |
| [!UICONTROL PENDING] | Nog uit te betalen bedrag |
| [!UICONTROL CUR] | Valuta-eenheid voor het uitstaande bedrag |
| [!UICONTROL SELLER AMT] | Bedrag van aan of van een klant overgedragen middelen <br> <br>Bij fondsen die van de verkopersaccount worden afgevoerd, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL CUR] | Valuta-eenheid voor het bedrag van de verkoper |
| [!UICONTROL PARTNER FEE] | Partner-kosten verbonden aan de transactie <br> <br>Bij fondsen die uit de rekening van de partnervergoeding worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL CUR] | Valuta-eenheid voor partnergeld |
| [!UICONTROL PROV FEES] | Aan de transactie gekoppelde kosten <br> <br>Bij geldmiddelen die uit de betaalrekening van de aanbieder worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL CUR] | Valuta-eenheid voor leveranciersvergoeding |
| [!UICONTROL FEE %] | Percentage van het transactiebedrag dat als vergoeding in rekening wordt gebracht |
| [!UICONTROL FIXED FEE] | Vaste kosten provider |
| [!UICONTROL CHBK FEE] | Restitutievergoeding voor de transactie <br> <br>Een voorvoegsel van het streepje (-) geeft aan dat de terugboekingskosten zijn teruggedraaid. |
| [!UICONTROL CUR] | Valuta-eenheid voor terugboekingsvergoeding |
| [!UICONTROL HOLD AMT] | In de wachtstand gezet of vrijgegeven bedrag <br> <br>Een streepje (-) voorvoegsel geeft aan dat gelden die in het bezit zijn, worden vrijgegeven. |
| [!UICONTROL CUR] | Valuta-eenheid voor het bedrag van de reserve |
| [!UICONTROL RECOUP AMT] | Bedrag teruggeboekt van de terugvorderingsrekening <br> <br>Bij fondsen die uit de terugvorderingsrekening worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL CUR] | Valuta-eenheid voor het terugvorderingsbedrag |

### Transactietypen

Deze transactietypen kunnen in de uitbetalingstransacties worden vermeld.

| Rapport | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL PAYMENT] | Geld dat tussen een koper en een verkoper is verplaatst voor een bestelling |
| [!UICONTROL AUTH] | Vergunningverlening en annulering van transacties |
| [!UICONTROL BONUS] | -- |
| [!UICONTROL CHARGEBACK] | Terugboekingskosten en terugboekingskosten |
| [!UICONTROL CORRECTION] | -- |
| [!UICONTROL CURRENCY_CONVERSION] | -- |
| [!UICONTROL DEPOSIT] | -- |
| [!UICONTROL DISBURSEMENT] | -- |
| [!UICONTROL DISPUTE] | -- |
| [!UICONTROL FEES] | Partner-kosten, betalings- en terugboekingstransacties |
| [!UICONTROL HOLD] | -- |
| [!UICONTROL HOLD_RELEASE] | -- |
| [!UICONTROL INCENTIVES] | -- |
| [!UICONTROL OTHERS] | -- |
| [!UICONTROL RECOUP] | Winsten van bank- of verliesrekeningen |
| [!UICONTROL REFUND] | -- |
| [!UICONTROL REVERSAL] | -- |
| [!UICONTROL WITHDRAWAL] | -- |
