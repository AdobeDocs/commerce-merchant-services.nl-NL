---
title: Uitbetalingsrapport
description: Gebruik het rapport Uitbetalingen voor volledige transparantie met betrekking tot het bedrag van de betaling, het verwerkte volume en gedetailleerde rapportage over het transactieniveau voor financiële afstemming.
role: User
level: Intermediate
exl-id: f3f99474-cd28-4c8f-b0ea-dca8e014b108
source-git-commit: 4fc2b3bdf9f319337939905bca2b9525985702d4
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Uitbetalingsrapport

[!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] biedt u uitgebreide rapportage zodat u een duidelijk beeld krijgt van de bestellingen en betalingen van uw winkel.

![Financiële verslagen](assets/reports-view.png)

Het uitbetalingsrapport bevat uitgebreide informatie over de uitbetaling in één oogopslag, zodat u volledig transparant kunt zijn over het bedrag van de betaling, het verwerkte volume en gedetailleerde rapportage over het transactieniveau voor financiële afstemming.

U hoeft geen meerdere weergaven te openen voor kruisverwijzingsopdrachten en betalingen of voor het combineren van accounts. [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] kunt u al deze acties uitvoeren vanaf één locatie, het rapport Uitbetalingen, zodat u uw uitbetalingen efficiënt kunt bekijken en beheren.

Zie de gekoppelde handelsorder en transactie-id&#39;s, transactiebedragen, betalingsmethode per transactie en meer, allemaal in het betalingsrapport in de beheerder.

U kunt uitbetalingstransacties downloaden in de .csv-bestandsindeling voor gebruik in bestaande software voor boekhouding of orderbeheer.

>[!NOTE]
>
>De gegevens in deze tabel worden in aflopende volgorde gesorteerd (`DESC`) standaard gebruikt de `TRANS DATE`. De `TRANS DATE` Dit is de datum en het tijdstip waarop de transactie werd geïnitieerd.

## Beschikbaarheid

Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.

![Betalingstransacties in de beheerder](assets/payouts-report.png)

## Gegevensbron selecteren

In de mening van het rapport van Uitbetalingen kunt u de gegevensbron selecteren—_[!UICONTROL Live]_of [!UICONTROL Sandbox]_-waarvoor u rapportresultaten wilt zien.

![Selectie gegevensbronnen](assets/datasource.png)

Indien _[!UICONTROL Live]_Als de geselecteerde gegevensbron is, kunt u rapportinformatie voor uw levende opslag zien. Indien [!UICONTROL Sandbox]_ is de geselecteerde gegevensbron, kunt u rapportinformatie voor uw milieu zien Sandbox.

Gegevensbronselecties werken als volgt:

* Als u geen opslagruimten hebt die zich in de live modus bevinden, wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Sandbox]_.
* Als u opslagruimten (een of meerdere opslagruimten) in de live modus hebt, wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Live]_.
* De uitvoer van het rapport respecteert altijd de gegevensbronselectie.

U kunt als volgt de gegevensbron selecteren voor het rapport Betalingsstatus bestelling:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Klikken **[!UICONTROL Data source]** en selecteert u _[!UICONTROL Live]_of [!UICONTROL Sandbox]_.

   De rapportresultaten regenereren op basis van de geselecteerde gegevensbron.

## Transacties weergeven

Standaard worden 30 dagen transacties in het raster weergegeven.

Het aantal rijen dat wordt geretourneerd in een zoekopdracht of dat wordt weergegeven in de standaard 30 dagen aan transacties, wordt boven het weergaveraster Uitbetalingen weergegeven naast het filter voor de kalenderkiezer voor Transactiedata.

Naar links en rechts schuiven om weer te geven [informatie voor elke betalingstransactie](#column-descriptions) in het dagelijkse rapport, met inbegrip van de transactiedatum, referentie-id, factuurnummer en betalingsmethode-details.

### Tijdschema voor transacties aanpassen

In de weergave Uitbetalingen kunt u het tijdpad voor de uitbetalingstransacties die u wilt bekijken aanpassen door specifieke datums in te voeren of een datumbereik te selecteren in de datumkiezer:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. Klik op het selectiefilter Transactiedata agenda.
1. Kies het toepasselijke datumbereik.
1. Bekijk de uitbetalingsstatussen in het raster voor de opgegeven datums.

## Kolommen tonen en verbergen

Het rapport Uitbetalingen toont standaard de meeste beschikbare kolommen met informatie. U kunt, echter, aanpassen welke kolommen u in uw rapport ziet.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Payouts]**.
1. Klik op de knop _Kolominstellingen_ icon (![pictogram kolominstellingen](assets/column-settings.png)).
1. Als u wilt aanpassen welke kolommen u in het rapport ziet, schakelt u de kolommen in de lijst in of uit.

   In het rapport Uitbetalingen worden direct wijzigingen weergegeven die u hebt aangebracht in het menu Kolominstellingen. De kolomvoorkeuren worden opgeslagen en blijven van kracht als u niet in de rapportweergave navigeert.

## Transacties downloaden

U kunt een CSV-bestand downloaden dat alle transacties bevat die zichtbaar zijn in het raster van de weergave Uitbetalingen.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > **[!UICONTROL Payouts]**.
1. [Tijdschema datumbereik voor uw transacties aanpassen](#customize-transactions-timeframe).
1. Klik op de knop _Downloaden_ (![](assets/icon-download.png)).

Uw uitbetalingstransacties worden gedownload in de CSV-indeling.

## Transactiegegevens

De weergave Uitbetalingen bevat uitgebreide informatie over elke transactie die in het raster wordt weergegeven.

### Kolombeschrijvingen

Uitbetalingsrapporten bevatten de volgende informatie.

| Kolom | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Provider] | Betalingsaanbieder |
| [!UICONTROL Provider trans] | Transactie-id |
| [!UICONTROL Trans date] | Datum en tijdstip waarop de transactie is gestart |
| [!UICONTROL Type] | Transactietype—*[!UICONTROL PAYMENT]*, *[!UICONTROL AUTH]*, *[!UICONTROL BONUS]*, *[!UICONTROL CHARGEBACK]*, *[!UICONTROL CORRECTION]*, *[!UICONTROL CURRENCY_CONVERSATION]*, *[!UICONTROL DEPOSIT]*, *[!UICONTROL DISBURSEMENT]*, *[!UICONTROL DISPUTE]*, *[!UICONTROL FEES]*, *[!UICONTROL HOLD]*, *[!UICONTROL HOLD_RELEASE]*, *[!UICONTROL INCENTIVES]*, *[!UICONTROL OTHERS]*, *[!UICONTROL RECOUP]*, *[!UICONTROL REFUND]*, *[!UICONTROL REVERSAL]*, *[!UICONTROL WITHDRAWAL]* <br> <br>Zie [Transactietypen](#transaction-types) voor meer informatie . |
| [!UICONTROL Status] | Huidige status van de transactie—*[!UICONTROL SUCCESS]*, *[!UICONTROL DENIED]*, *[!UICONTROL PENDING]* |
| [!UICONTROL Code] | Transactiecode die een creditering aangeeft (*CR*) of Debet (*DR*) |
| [!UICONTROL Reference ID] | Oorspronkelijke transactie-id waarvoor deze gebeurtenis verband houdt |
| [!UICONTROL Invoice] | Factuur-id (één per bestelling) van de transactie |
| [!UICONTROL Commerce order] | Handelsorder-ID <br> <br>Verwante items weergeven [orderinfo](https://docs.magento.com/user-guide/sales/orders.html){target=&quot;_blank&quot;}, klikt u op de id. |
| [!UICONTROL Commerce trans] | Transactie-id voor handel <br> <br>Verwante items weergeven [transactiegegevens](https://docs.magento.com/user-guide/sales/transactions.html){target=&quot;_blank&quot;}, klikt u op de id. |
| [!UICONTROL Pay method] | Type creditcard—*[!UICONTROL BANK]*, *[!UICONTROL PAYPAL]*, *[!UICONTROL CREDIT_CARD]*—en bijbehorende kaartprovider (zoals *Visa* of *MasterCard*) |
| [!UICONTROL Trans amt] | Bedrag van de transactie |
| [!UICONTROL Cur] | Valuta-eenheid voor transactiebedrag |
| [!UICONTROL Pending] | Nog uit te betalen bedrag |
| [!UICONTROL Cur] | Valuta-eenheid voor het uitstaande bedrag |
| [!UICONTROL Seller amt] | Bedrag van aan of van een klant overgedragen middelen <br> <br>Bij fondsen die van de verkopersaccount worden afgevoerd, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL Cur] | Valuta-eenheid voor het bedrag van de verkoper |
| [!UICONTROL Partner fee] | Partner-kosten verbonden aan de transactie <br> <br>Bij fondsen die uit de rekening van de partnervergoeding worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL Cur] | Valuta-eenheid voor partnergeld |
| [!UICONTROL Prov fees] | Aan de transactie gekoppelde kosten <br> <br>Bij geldmiddelen die uit de betaalrekening van de aanbieder worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL Cur] | Valuta-eenheid voor leveranciersvergoeding |
| [!UICONTROL Fee %] | Percentage van het transactiebedrag dat als vergoeding in rekening wordt gebracht |
| [!UICONTROL Fixed fee] | Vaste kosten provider |
| [!UICONTROL Chbk fee] | Restitutievergoeding voor de transactie <br> <br>Een voorvoegsel van het streepje (-) geeft aan dat de terugboekingskosten zijn teruggedraaid. |
| [!UICONTROL Cur] | Valuta-eenheid voor terugboekingsvergoeding |
| [!UICONTROL Hold amt] | In de wachtstand gezet of vrijgegeven bedrag <br> <br>Een streepje (-) voorvoegsel geeft aan dat gelden die in het bezit zijn, worden vrijgegeven. |
| [!UICONTROL Cur] | Valuta-eenheid voor het bedrag van de reserve |
| [!UICONTROL Recoup amt] | Bedrag teruggeboekt van de terugvorderingsrekening <br> <br>Bij fondsen die uit de terugvorderingsrekening worden verplaatst, wordt een voorvoegsel voor een streepje (-) weergegeven. |
| [!UICONTROL Cur] | Valuta-eenheid voor het terugvorderingsbedrag |

### Transactietypen

Deze transactietypen kunnen in de uitbetalingstransacties worden vermeld.

| Rapport | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL PAYMENT] | Geld dat tussen een koper en een verkoper is verplaatst voor een bestelling |
| [!UICONTROL AUTH] | Vergunningverlening en annulering van transacties |
| [!UICONTROL BONUS] | — |
| [!UICONTROL CHARGEBACK] | Terugboekingskosten en terugboekingskosten |
| [!UICONTROL CORRECTION] | — |
| [!UICONTROL CURRENCY_CONVERSION] | — |
| [!UICONTROL DEPOSIT] | — |
| [!UICONTROL DISBURSEMENT] | — |
| [!UICONTROL DISPUTE] | — |
| [!UICONTROL FEES] | Partner-kosten, betalings- en terugboekingstransacties |
| [!UICONTROL HOLD] | — |
| [!UICONTROL HOLD_RELEASE] | — |
| [!UICONTROL INCENTIVES] | — |
| [!UICONTROL OTHERS] | — |
| [!UICONTROL RECOUP] | Winsten van bank- of verliesrekeningen |
| [!UICONTROL REFUND] | — |
| [!UICONTROL REVERSAL] | — |
| [!UICONTROL WITHDRAWAL] | — |
