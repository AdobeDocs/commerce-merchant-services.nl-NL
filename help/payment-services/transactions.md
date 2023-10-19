---
title: Transactierapport
description: Gebruik het rapport Transacties om de snelheid van de transactievergunning en transactietrends zichtbaar te maken.
role: User
level: Intermediate
exl-id: dd1d80f9-5983-4181-91aa-971522eb56fa
source-git-commit: 91acc6e1dfd142caca77c0dc9ba55da34f75dd60
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 0%

---

# Transactierapport

[!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] biedt uitgebreide rapportage zodat u een duidelijk overzicht kunt krijgen van de transacties, bestellingen en betalingen in uw winkel.

![Transactierapport](assets/transactions-report.png){width="700" zoomable="yes"}

Het Transactierapport biedt inzicht in transactievergunningpercentages en negatieve transactietrends zodat u de gezondheid van uw opslag effectief kunt controleren en om het even welke transactiekwesties op voorhand kunt identificeren en behandelen.

Zie afzonderlijke transacties voor in de winkel geplaatste orders en hun betalingsmethoden, resultaat, responscodes voor betalingen en meer.

De in het transactieverslag verstrekte informatie is uitsluitend bestemd voor commercieel gebruik. Deel deze informatie niet met klanten of andere potentiële fraudeurs. Transactiegegevens kunnen worden gebruikt om beveiligingscontroles te omzeilen of om orders te plaatsen die tot doorbelasting leiden.

U kunt het rapport Transacties downloaden in de .csv-bestandsindeling voor gebruik in bestaande software voor boekhouding of orderbeheer.

>[!NOTE]
>
>U kunt geen financiële rapporten weergeven als u [Aan boord en geactiveerde Live-modus](production.md#enable-live-payments) for [!DNL Payment Services].

## Transactierapportweergave

De weergave van het Transactierapport is beschikbaar in de weergave Transacties van Betalingsdiensten. Het bevat alle beschikbare informatie over transacties voor je winkel(s).

Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**om de gedetailleerde het rapportmening van Transacties in tabelvorm te zien.

![Transactierapportweergave](assets/transactions-report-detail.png){width="600" zoomable="yes"}

U kunt deze mening, per de secties in dit onderwerp vormen, om de gegevens het best voor te stellen u wenst te zien.

Zie gekoppelde orders van de Handel en de identiteitskaart van de leverancierstransactie, transactiebedragen, betalingsmethode per transactie, en meer, allen binnen dit rapport.

Niet alle betalingsmethoden bieden dezelfde mate van informatie. Met creditcardtransacties worden bijvoorbeeld de respons-, AVS- en CCV-codes en de laatste vier cijfers van de kaart in het Transactierapport weergegeven. Met de slimme PayPal-knoppen gebeurt dit niet.

U kunt [downloadtransacties](#download-transactions) in een .csv-bestandsindeling voor gebruik in bestaande software voor boekhouding of orderbeheer.

### Gegevensbron selecteren

In de het rapportmening van Transacties, kunt u de gegevensbron selecteren—**[!UICONTROL Live]** of **[!UICONTROL Sandbox]**—waarvoor u rapportresultaten wilt zien.

![Selectie gegevensbronnen](assets/datasource.png){width="300" zoomable="yes"}

Indien _[!UICONTROL Live]_is de geselecteerde gegevensbron, kunt u rapportinformatie voor uw opslag zien die gebruikt [!DNL Payment Services] in de productiemodus. Indien_[!UICONTROL Sandbox]_ De geselecteerde gegevensbron is, kunt u rapportinformatie voor uw zandbakwijze zien.

Gegevensbronselecties werken als volgt:

* Als u geen winkels hebt die [!DNL Payment Services] in de productiemodus wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Sandbox]_.
* Als u opslagruimten (één of meerdere) hebt die [!DNL Payment Services] in de productiemodus wordt de gegevensbronselectie standaard ingesteld op _[!UICONTROL Live]_.
* De uitvoer van het rapport respecteert altijd de gegevensbronselectie.

Om de gegevensbron voor uw te selecteren [!UICONTROL Transactions] rapport:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**.
1. Klikken **[!UICONTROL Data source]** en selecteert u **[!UICONTROL Live]** of **[!UICONTROL Sandbox]**.

   De rapportresultaten regenereren op basis van de geselecteerde gegevensbron.

### Tijdskader voor datums aanpassen

In de weergave van het Transactierapport kunt u de tijdlijn aanpassen van de transacties die u wilt weergeven door specifieke datums te selecteren. Standaard worden 30 dagen transacties in het raster weergegeven.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**.
1. Klik op de knop **[!UICONTROL Transaction dates]** Kalenderkiezerfilter.
1. Kies het toepasselijke datumbereik.
1. Geef de transacties voor de opgegeven datums weer in het raster.

### Rapportgegevens filteren

In de weergave van het Transactierapport kunt u de resultaten filteren die u wilt bekijken door filtercriteria te selecteren.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**.
1. Klik op de knop **[!UICONTROL Filter]** kiezer.
1. Schakelen tussen _[!UICONTROL Transaction Result]_opties om rapportresultaten voor slechts geselecteerde ordetransacties te zien.
1. Selecteer de _[!UICONTROL Card Type]_om de rapportresultaten voor het geselecteerde kaarttype te zien. Er wordt knopinfo met meer informatie weergegeven wanneer de betalingsverwerker het type kaart niet kan identificeren.
1. Selecteer de _[!UICONTROL Card Brand]_om de rapportresultaten voor het geselecteerde kaartmerk te bekijken. Er wordt knopinfo met meer informatie weergegeven wanneer de betalingsverwerker het kaartmerk niet kan identificeren.
1. Schakelen tussen _[!UICONTROL Payment Method]_opties om de rapportresultaten voor slechts geselecteerde betalingsmethodes te zien.
1. Voer een _Min. orderbedrag_ of _Max. aantal bestellingen_ om rapportresultaten binnen die waaier van het ordebedrag te zien.
1. Voer een _[!UICONTROL Order ID]_om naar een specifieke transactie te zoeken.
1. Voer de _[!UICONTROL Card Last Four Digits]_om te zoeken naar een specifieke creditcard of bankpas.
1. Klikken **[!UICONTROL Hide filters]** om het filter te verbergen.

### Kolommen tonen en verbergen

Het rapport van Transacties toont alle beschikbare kolommen van informatie door gebrek. U kunt, echter, aanpassen welke kolommen u in uw rapport ziet.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**.
1. Klik op de knop **[!UICONTROL Column settings]** pictogram ![pictogram kolominstellingen](assets/column-settings.png){width="20" zoomable="yes"}.
1. Om aan te passen welke kolommen die u in het rapport ziet, controleer of uncheck kolommen in de lijst.

   In het rapport Transacties worden direct alle wijzigingen weergegeven die u hebt aangebracht in het menu Kolominstellingen. De kolomvoorkeuren worden opgeslagen en blijven van kracht als u niet in de rapportweergave navigeert.

### Rapportgegevens bijwerken

De het rapportmening van Transacties toont een _[!UICONTROL Last updated]_timestamp die de laatste tijd toont dat de rapportinformatie werd bijgewerkt. Door gebrek, worden het rapportgegevens van Transacties auto-verfrist om de drie uur.

U kunt ook manueel dwingen verfrist zich van de rapportgegevens om de meest bijgewerkte rapportinformatie te zien.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > _[!UICONTROL Transactions]_>**[!UICONTROL View Report]**.
1. Klik op de knop _Vernieuwen_ icon (![vernieuwingspictogram](assets/refresh-button-med.png){width="20" zoomable="yes"}).

   De gegevens van het Transactierapport worden vernieuwd, en *[!UICONTROL Update complete]* de bevestiging verschijnt en de recentste informatie is aanwezig in het net.

### Transacties downloaden

U kunt een CSV-bestand downloaden met alle transacties die zichtbaar zijn in het raster van de transactieweergave, of u nu de standaardtransacties van 30 dagen bekijkt of een aangepast tijdframe.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]** > **[!UICONTROL Transactions]**.
1. Als u transacties wilt zien voor een ander tijdsbestek dan de laatste 30 dagen, [de tijdlijn voor het datumbereik voor uw statussen aanpassen](#customize-dates-timeframe).
1. Klik op de knop _Downloaden_ ![downloadpictogram](assets/icon-download.png){width="20" zoomable="yes"} pictogram.

Uw transacties worden gedownload in de indeling .csv.

### Kolombeschrijvingen

Transactierapporten bevatten de volgende informatie.

| Kolom | Beschrijving |
| ------------ | -------------------- |
| [!UICONTROL Order ID] | Handelsorder-id (bevat alleen waarden voor geslaagde transacties en is leeg voor geweigerde transacties)<br> <br>Verwante items weergeven [orderinfo](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, klikt u op de id. |
| [!UICONTROL Provider Transaction ID] | Transactie-id verstrekt door de betalingsaanbieder; bevat alleen waarden voor geslaagde transacties en bevat een streepje voor geweigerde transacties. |
| [!UICONTROL Transaction Date] | Tijdstempel van transactiedatum |
| [!UICONTROL Payment Method] | Betalingsmethode van transactie met gedetailleerde informatie over merk en type kaart. Zie [kaarttypen](https://developer.paypal.com/docs/api/orders/v2/#definition-card_type) voor meer informatie; beschikbaar voor Payment Services versie 1.6.0 en hoger |
| [!UICONTROL Card Last Four Digits] | Laatste vier cijfers van de voor de transactie gebruikte krediet- of debetkaarten |
| [!UICONTROL Result] | Het resultaat van de transactie—*[!UICONTROL OK]* (geslaagde transactie), *[!UICONTROL Rejected by Payment Provider]* (geweigerd door PayPal), *[!UICONTROL Rejected by Bank]* (geweigerd door bank die kaart heeft uitgegeven) |
| [!UICONTROL Response Code] | Foutcode die een reden voor afwijzing van een betalingsaanbieder of bank geeft; zie de lijst met mogelijke antwoordcodes en beschrijvingen voor [`Rejected by Bank` status](https://developer.paypal.com/docs/api/orders/v2/#definition-processor_response) en [`Rejected by Payment Provider` status](https://developer.paypal.com/api/rest/reference/orders/v2/errors/). |
| [!UICONTROL AVS Code] | Adres Verification Service-code; de responsgegevens van de processor voor betalingsverzoeken. Zie [lijst van mogelijke codes en beschrijvingen](https://developer.paypal.com/docs/api/orders/v2/#definition-processor_response) voor meer informatie . |
| [!UICONTROL CVV Code] | Waardencode voor verificatie van kaarten voor krediet- en debetkaarten; zie [lijst van mogelijke codes en beschrijvingen](https://developer.paypal.com/docs/api/orders/v2/#definition-processor_response) voor meer informatie . |
| [!UICONTROL Amount] | Volgorde van transactie |
| [!UICONTROL Currency] | Valuta gebruikt voor order in transactie |
| [!UICONTROL Type] | [Betalingsactie](../payment-services/production.md#set-payment-services-as-payment-method) voor transactie—`Authorize` of `Authorize and Capture` |

### Foutresponscodes

De _Antwoordcode_ de kolom toont een specifieke fout of succescode met betrekking tot de transactie. Enkele veelvoorkomende foutcodes die u kunt zien, zijn:

* `PAYMENT_DENIED`—De transactie is door PayPal geweigerd omdat het vermoeden bestond dat er sprake was van fraude.
* `INTERNAL_SERVER_ERROR`—Transactie is geweigerd door PayPal en er is een PayPal-serverfout opgetreden. De transactie kan opnieuw worden geprobeerd.
* `INSTRUMENT_DECLINED`—De klant is door PayPal geweigerd op basis van een geselecteerde betalingsmethode. Transactie kan opnieuw worden uitgevoerd met een andere betalingsmethode.
* `9500`—De transactie werd door de geassocieerde bank geweigerd omdat het vermoeden bestond dat er sprake was van fraude.
* `5120`—De transactie werd door de geassocieerde bank geweigerd omdat de klant over onvoldoende middelen beschikte voor de betaling.
* `5650`—Transactie is door de geassocieerde bank geweigerd omdat de bank een sterke cliëntautheffing nodig heeft ([3DS](security.md#3ds)).

Gedetailleerde foutresponscodes voor mislukte transacties zijn beschikbaar voor transacties die jonger zijn dan 1 juni 2023. Gedeeltelijke rapportgegevens worden weergegeven voor transacties die vóór 1 juni 2023 hebben plaatsgevonden.
