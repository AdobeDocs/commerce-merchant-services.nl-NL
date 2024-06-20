---
title: Logboeken controleren en problemen oplossen
description: Leer hoe u problemen kunt oplossen [!DNL data export] fouten bij het gebruik van de logbestanden voor het exporteren van gegevens en het exporteren van bestanden.
feature: Services
recommendations: noCatalog
exl-id: 55903c19-af3a-4115-a7be-9d1efaed8140
source-git-commit: af9de40a717d2cb55a5f42483bd0e4cbcd913f64
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 0%

---

# Logbestanden controleren en problemen oplossen

De [!DNL data export] de uitbreiding verstrekt logboeken om gegevensinzameling en synchronisatieprocessen te volgen.

## Logboeken

Logbestanden zijn beschikbaar in het dialoogvenster `var/log` op de Commerce-toepassingsserver.

| lognaam | filename | beschrijving |
|-----------------| ----------| -------------|
| Logbestand SaaS-gegevensexport | `commerce-data-export.log` | Verstrekt informatie over de activiteiten van de gegevensuitvoer zoals entiteitgebeurtenissen en volledige resync trekkers.  Elk logboekverslag heeft een specifieke structuur en verstrekt informatie over het voer, de verrichting, de status, de verstreken tijd, proces identiteitskaart, en de bezoeker. |
| Logbestand met fouten bij exporteren SaaS-gegevens | `data-export-errors.log` | Verstrekt foutenmeldingen en stacksporen voor fouten die tijdens het proces van de gegevenssynchronisatie voorkomen. |
| SaaS-exportlogboek | `saas-export.log` | Verstrekt informatie over de gegevens die naar de diensten van Commerce SaaS worden verzonden. |
| Logbestand van SaaS-exportfout | `saas-export-errors.log` | Verstrekt informatie over fouten die voorkomen wanneer het verzenden van gegevens naar de diensten van Commerce SaaS. |

Als u de verwachte gegevens voor een dienst van Adobe Commerce niet ziet, gebruik de foutenlogboeken voor de uitbreiding van de gegevensuitvoer om te bepalen waar het probleem voorkwam. Ook, kunt u logboeken met extra gegevens voor het volgen en het oplossen van problemen uitbreiden. Zie [Uitgebreide logboekregistratie](#extended-logging).

### Logbestandsindeling

Elke logrecord heeft de volgende structuur.

```
[<log record datetime>] report.<log level>:
{
   "feed": "<feed name>",
   "operation": "<executed operation>",
   "status": "<status of operation>",
   "elapsed": "<time elaspsed from script run>",
   "pid": "<proccess id who executed `operation`>",
   "caller": "<who called this `operation`>"
} [] []
```

>[!NOTE]
>
>De op JSON gebaseerde tekenreeks is verfraaid voor betere leesbaarheid.

De volgende lijst beschrijft de verrichtingstypes die in de logboeken kunnen worden geregistreerd.

| Bewerking | Beschrijving | Voorbeeld van de bezoeker |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| volledige synchronisatie | Met Volledige synchronisatie worden alle gegevens voor een bepaalde feed verzameld en naar SaaS verzonden. | `bin/magento saas:resync --feed=products` |
| gedeeltelijke reïndex | Gedeeltelijke synchronisatie verzamelt gegevens en verzendt deze naar SaaS voor alleen bijgewerkte entiteiten in een bepaalde feed. Dit logboek is alleen aanwezig als er bijgewerkte entiteiten zijn. | `bin/magento cron:run --group=index` |
| mislukte items opnieuw proberen | Hiermee worden items voor een bepaalde feed opnieuw verzonden naar SaaS als de vorige synchronisatiebewerking is mislukt als gevolg van een Commerce-toepassing of serverfout. Dit logbestand is alleen aanwezig als mislukte items bestaan. | `bin/magento cron:run --group=saas_data_exporter`  (om het even welke &quot;*_data_exporter&quot;kron groep) |
| volledige synchronisatie (verouderd) | Volledige synchronisatie voor een bepaalde feed in de oudere exportmodus. | `bin/magento saas:resync --feed=categories` |
| gedeeltelijke redex (verouderd) | Verzendt bijgewerkte entiteiten naar SaaS voor een bepaalde feed in de oudere exportmodus. Dit logboek is alleen aanwezig als er bijgewerkte entiteiten zijn. | `bin/magento cron:run --group=index` |
| gedeeltelijke synchronisatie (verouderd) | Verzendt bijgewerkte entiteiten naar SaaS voor een bepaalde feed in de oudere exportmodus. Dit logboek is alleen aanwezig als er bijgewerkte entiteiten zijn. | `bin/magento cron:run --group=saas_data_exporter` (om het even welke &quot;*_data_exporter&quot;kron groep) |


### Voorbeelden van logboekregistratie

Tijdens een volledige resync, wordt de vooruitgang gevolgd en geregistreerd elke 30 seconden door gebrek. Hier volgt een voorbeeld van een logbestandvermelding.

```json
{
   "feed": "prices",
   "operation": "full sync",
   "status": "Progress: 2/5, processed: 200, synced: 100",
   "elapsed": "00:00:00 190 ms",
   "pid": "12824",
   "caller": "bin/magento saas:resync --feed=products"
}
```

In dit voorbeeld wordt `status` waarden geven informatie over de synchronisatiebewerking:

- **`"Progress 2/5"`** geeft aan dat 2 van 5 herhalingen zijn voltooid. Het aantal herhalingen is afhankelijk van het aantal geëxporteerde entiteiten.
- **`"processed: 200"`** geeft aan dat 200 objecten zijn verwerkt.
- **`"synced: 100"`** geeft aan dat 100 items naar SaaS zijn verzonden. Het is te verwachten dat `"synced"` is niet gelijk aan `"processed"`. Hier volgt een voorbeeld:
   - **`"synced" < "processed"`** betekent dat de voederlijst geen veranderingen in het punt, in vergelijking met de eerder gesynchroniseerde versie ontdekte. Dergelijke items worden genegeerd tijdens de synchronisatiebewerking.
   - **`"synced" > "processed"`** dezelfde entiteitskaart (bijvoorbeeld `Product ID`) kan meerdere waarden in verschillende bereiken hebben. Eén product kan bijvoorbeeld worden toegewezen aan vijf websites. In dit geval kun je 1 verwerkt object en 5 gesynchroniseerde objecten hebben.

+++ **Voorbeeld: log met volledige resync voor de prijsfeed**

```
Price feed full resync:

[2024-03-05T21:00:51.754687+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Initialize","elapsed":"383 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:51.803178+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Creating batch table `catalog_data_exporter_product_prices_index_batches`. Start position: 30515","elapsed":"434 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:51.851878+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Batch table `catalog_data_exporter_product_prices_index_batches` created. Total Items: 500, batches: ~1","elapsed":"482 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:51.852548+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"start processing `500` items in `1` threads with `500` batch size","elapsed":"483 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:52.288369+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Progress 1\/1, processed 500, synced 0","elapsed":"919 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:53.994249+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Progress 1\/1, processed 500, synced 100","elapsed":"00:00:02 625 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
[2024-03-05T21:00:53.995168+00:00] report.INFO: {"feed":"prices","operation":"full sync","status":"Complete","elapsed":"00:00:02 626 ms","pid":"14469","caller":"bin\/magento saas:resync --feed=prices"} [] []
```

+++

## Logbestanden met New Relic weergeven en problemen oplossen

Als u Adobe Commerce-logbestanden opslaat in de New Relic, kunt u parseringsregels toevoegen om de leesbaarheid en zoekervaring te verbeteren.

1. Meld u aan bij New Relic.

1. Ga naar `Logs => Parsing`.

1. Klik op `Create parsing rule`.

1. Vorm de het ontleden regel door de volgende waarden toe te voegen.

   - **Filterlogboeken op basis van NRQL**

     `filePath LIKE '%commerce-data-export%.log'`

   - **Parseerregel**

     `\[%{DATA:timestamp}\] report.%{DATA:logLevel} %{GREEDYDATA:feed:json}`

In dit voorbeeld wordt een regel toegevoegd waarmee u New Relic-logbestanden kunt opvragen op basis van een bepaald type feed, bewerking, enzovoort.

**Voorbeeldquerytekenreeks**—`feed.feed:"products" and feed.status:"Complete"`

## Problemen oplossen

Als er gegevens ontbreken of onjuist zijn in Commerence Services, controleert u de logboeken om te zien of er een probleem is opgetreden tijdens de synchronisatie van de Adobe Commerce-instantie naar het Commerce Service-platform. Indien nodig, gebruik uitgebreide registreren om extra informatie aan logboeken voor het oplossen van problemen toe te voegen.

- commerce-data-export-errors.log - als er een fout is opgetreden tijdens de verzamelfase
- saas-export-errors.log - als een fout tijdens het overbrengen van fase gebeurde

Als u fouten ziet die niet te maken hebben met configuratie of extensies van derden, dient u een [ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html?lang=en#submit-ticket) met zoveel mogelijk informatie.

### Synchronisatieproblemen met catalogi oplossen {#resolvesync}

Wanneer u een gegevensresync teweegbrengt, kan het tot een uur voor de gegevens duren om bij te werken en in UI componenten zoals levende onderzoek en aanbeveling eenheden worden weerspiegeld. Raadpleeg het volgende als u nog steeds discrepanties ziet tussen uw catalogus en de gegevens in de Commerce-winkel of als de catalogussynchronisatie is mislukt:

#### Gegevensafwijking

1. Geef de gedetailleerde weergave van het desbetreffende product weer in de zoekresultaten.
1. Kopieer de JSON-uitvoer en controleer of de inhoud overeenkomt met de inhoud in het dialoogvenster [!DNL Commerce] catalogus.
1. Als de inhoud niet overeenkomt, brengt u een kleine wijziging aan in het product in de catalogus, zoals het toevoegen van een spatie of een punt.
1. Wacht op resync of [een handmatige resync activeren](#resync).

#### Synchronisatie wordt niet uitgevoerd

Als de synchronisatie niet volgens een schema wordt uitgevoerd of er niets wordt gesynchroniseerd, raadpleegt u deze [KnowledgeBase](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-product-recommendations-module-in-magento-commerce.html) artikel.

#### Synchronisatie is mislukt

Als de catalogussync de status **Mislukt**, een [ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket).

## Uitgebreide logboekregistratie

Voor extra logboekinformatie, kunt u milieuvariabelen gebruiken om logboeken met extra gegevens voor het volgen en het oplossen van problemen uit te breiden.

Er zijn twee logbestanden in het dialoogvenster `var/log/` map:

- commerce-data-export-errors.log - als er een fout is opgetreden tijdens de verzamelfase
- saas-export-errors.log - als een fout tijdens het overbrengen van fase gebeurde

U kunt omgevingsvariabelen gebruiken om logbestanden uit te breiden met extra gegevens voor het bijhouden en oplossen van problemen.

### Controleer de lading van de voer

Neem de payload van de feed op in het SaaS-exportlogboek door het volgende toe te voegen `EXPORTER_EXTENDED_LOG=1` omgevingsvariabele wanneer u de feed opnieuw synchroniseert.

```shell script
EXPORTER_EXTENDED_LOG=1 bin/magento saas:resync --feed=products
```

Nadat de bewerking is voltooid, is de lading van de feed beschikbaar voor revisie in het SaaS-exportlogboek (`var/.log/saas-export.log`).

### Payload behouden in voederindextabel

Voor de Commerce SaaS-extensie voor gegevensexport (`magento/module-data-exporter`) 103.3.0 en hoger, houden de directe uitvoervoer slechts de minimaal vereiste gegevens in de indexlijst. De feeds bevatten alle statusfeeds voor catalogi en voorraden.

Het behouden van ladingsgegevens in de indexlijst wordt niet geadviseerd in productiemilieu&#39;s, maar het kan in een ontwikkelaarmilieu nuttig zijn. Neem de payload van de feed op in de index door de `PERSIST_EXPORTED_FEED=1` omgevingsvariabele wanneer u de feed opnieuw synchroniseert.

```shell script
PERSIST_EXPORTED_FEED=1 bin/magento saas:resync --feed=products
```

### Profiel uitvoeren om trage prestaties op te lossen

Als het opnieuw indexproces van een specifieke voer een onredelijke hoeveelheid tijd vergt, stel profiler in werking om extra gegevens te verzamelen die voor het Team van de Steun nuttig zouden kunnen zijn.

Voer de analyse uit door de `EXPORTER_PROFILER=1` omgevingsvariabele wanneer u de opdracht voor opnieuw indexeren uitvoert.

```
EXPORTER_PROFILER=1 bin/magento indexer:reindex catalog_data_exporter_products
```

Profilergegevens worden opgeslagen in het logboek voor gegevensexport (`var/log/commerce-data-export.log`) in de volgende notatie:

```
<Provider class name>, <# of processed entities>, <execution time im ms>, <memory consumption in Mb>
```
