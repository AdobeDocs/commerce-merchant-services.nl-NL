---
title: Opdrachtregelinterface SaaS-gegevens exporteren
description: Leer hoe te om de bevel-lijn interfacebevelen te gebruiken om voer en processen voor te beheren [!DNL data export extension] voor Adobe Commerce SaaS-diensten.
recommendations: noCatalog
exl-id: f360d920-7d02-4317-8c56-c7d4c4ed2ff2
source-git-commit: af9de40a717d2cb55a5f42483bd0e4cbcd913f64
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Opdracht-lijn Interfaceverwijzing SaaS-gegevens exporteren

Ontwikkelaars en systeembeheerders kunnen synchronisatiebewerkingen voor SaaS-gegevensexport beheren met de [Adobe Commerce-opdrachtregelprogramma](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/config-cli) (CLI). De `saas:resync` wordt opgenomen in de `magento/saas-export` pakket.

Adobe raadt u niet aan de `saas:resync` regelmatig gebruiken. De typische scenario&#39;s voor het gebruiken van het bevel zijn:

- De eerste synchronisatie
- De [SaaS Data Space ID](https://experienceleague.adobe.com/en/docs/commerce-admin/config/services/saas) is gewijzigd en u moet gegevens synchroniseren naar de nieuwe gegevensruimte.
- Problemen oplossen

## Beginsynchronisatie

>[!NOTE]
>Als u Live zoeken of Product Recommendations gebruikt, hoeft u de eerste synchronisatie niet uit te voeren. Het proces wordt automatisch gestart nadat u de service hebt verbonden met uw Commerce-instantie.

Wanneer u een `saas:resync` op de opdrachtregel, afhankelijk van de grootte van de catalogus, kan het enkele minuten tot enkele uren duren voordat de gegevens zijn bijgewerkt.

Voor de eerste synchronisatie raadt Adobe aan de opdrachten in de volgende volgorde uit te voeren:

```bash
bin/magento saas:resync --feed productattributes
bin/magento saas:resync --feed products
bin/magento saas:resync --feed scopesCustomerGroup
bin/magento saas:resync --feed scopesWebsite
bin/magento saas:resync --feed prices
bin/magento saas:resync --feed productoverrides
bin/magento saas:resync --feed variants
bin/magento saas:resync --feed categories
bin/magento saas:resync --feed categoryPermissions
```

## Voorbeelden van opdrachten

Voor gebruik `saas:resync` opdrachten, bekijk de [optieredomschrijvingen](#command-options).

- Voer een volledige resync voor een entiteitvoer uit.

  ```
  bin/magento saas:resync --feed='<FEED_NAME>' 1
  ```

  Feeds die al zijn geëxporteerd, worden niet opnieuw gesynchroniseerd.

- De opgegeven feed- en opschoongegevens volledig opnieuw synchroniseren

  ```
  bin/magento saas:resync --feed='FEED_NAME' --cleanup-feed
  ```

  Alleen gebruiken na het uitvoeren van een [!DNL Data Space ID Cleanup] -bewerking.

- Voor directe exportfeeds verzendt u alle gegevens opnieuw naar verbonden Commerce-services zonder de indexgegevens in de voedertabel af te kappen

  ```
   bin/magento saas:resync --feed='FEED_NAME' --no-reindex
  ```

- Beschikbare opdrachten en opties weergeven met beschrijvingen.

  ```
  bin/magento saas:resync --help
  ```

## Opdrachtopties

De volgende opties zijn beschikbaar voor het beheer `saas:resync` bewerkingen.

>[!NOTE]
>
>De `saas:resync` ondersteunt ook geavanceerde opties om opdrachten voor het exporteren van gegevens te verbeteren door de batch te vergroten en verwerking met meerdere threads toe te voegen. Zie [Exportverwerking aanpassen](customize-export-processing.md).

### `feed`

Met deze optie wordt opgegeven welke feed-entiteit opnieuw moet worden gesynchroniseerd, zoals `products`.

De `feed` De optiewaarde kan om het even welke beschikbare entiteitsvoer omvatten:

- `products`: feed met productgegevens
- `productAttributes`: doorvoeren van productkenmerken
- `categories`: gegevensfeed voor categorieën
- `variants`: configureerbare gegevenstoevoer voor productvariaties
- `prices`Betreft: Gegevensinvoer productprijzen
- `categoryPermissions`: gegevenstoevoer voor categorierechten
- `productOverrides`: voer met productmachtigingen
- `inventoryStockStatus`: Invoer van voorraadstatusgegevens
- `scopesWebsite`: websites met gegevensinvoer van weergaven in winkels en winkels
- `scopesCustomerGroup`: gegevensfeed voor klantengroepen
- `orders`: gegevensfeed voor verkooporders

Afhankelijk van [Commerce Services](../landing/saas.md) zijn geïnstalleerd, hebt u mogelijk een andere set feeds beschikbaar voor de `saas:resync` gebruiken.

### `no-reindex`

Deze optie verzendt de bestaande catalogusgegevens opnieuw naar [!DNL Commerce Services] zonder opnieuw te indexeren. Als deze optie niet is opgegeven, voert de opdracht een volledige redex uit voordat gegevens worden gesynchroniseerd.

Het gedrag van deze optie hangt af van het feit of de feed wordt geëxporteerd in [verouderde of directe exportmodus](data-synchronization.md#synchronization-modes)

- Voor verouderde exportfeeds worden de geïndexeerde gegevens in de feeds-tabel niet afgebroken tijdens het synchronisatieproces. In plaats daarvan worden alle gegevens opnieuw naar de Adobe Commerce-service verzonden.
- Voor directe exportfeeds wordt deze optie genegeerd als deze wordt opgegeven. Voor deze feeds wordt de index niet afgekapt door het resync-proces en worden alleen updates of items die eerder zijn mislukt, opnieuw gesynchroniseerd.

### `cleanup`

Met deze optie wordt de tabel met indexitems voor een synchronisatie gewist. Wanneer gespecificeerd, voert de gegevensuitvoer SaaS een volledige resync voor het gespecificeerde voer uit en schoont omhoog alle bestaande gegevens in de voederlijst.

Adobe raadt alleen aan deze opdracht te gebruiken nadat de opdracht [!DNL Data Space ID Cleanup] -bewerking.

>[!WARNING]
>
>**Deze optie niet regelmatig gebruiken**. Er kunnen problemen met gegevenssynchronisatie optreden in Adobe Commerce Services. Bijvoorbeeld de `delete product event` zou niet aan de dienst van Adobe Commerce kunnen verspreiden als `cleanup` wordt gebruikt.

## Problemen oplossen

Als u de verwachte gegevens niet ziet in de verbonden Commerce Services, kunt u problemen oplossen door de logbestanden met gegevensexportfouten te controleren en de `saas:resync` gebruiken in combinatie met omgevingsvariabelen om ladingen en analysegegevens te controleren. Zie [Logboeken controleren en problemen oplossen](troubleshooting-logging.md).
