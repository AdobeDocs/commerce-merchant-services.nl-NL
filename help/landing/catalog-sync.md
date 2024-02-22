---
title: Catalogus synchroniseren
description: Leer hoe u productgegevens exporteert vanuit de [!DNL Commerce] server naar [!DNL Commerce Services].
exl-id: 19d29731-097c-4f5f-b8c0-12f9c91848ac
feature: Catalog Management, Data Import/Export, Catalog Service
source-git-commit: 289ac6ac464955f18f3a2448099ad459e6264941
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 0%

---


# Catalogus synchroniseren

>[!NOTE]
>
> Het dashboard voor catalogussynchronisatie is nu het gegevensbeheerdashboard. Dit vernieuwde dashboard ondersteunt nu [!DNL Product Recommendations], [!DNL Live Search], en [!DNL Catalog Service]. Klanten kunnen het gegevensbeheerdashboard ophalen door de nieuwste versie van een van deze services bij te werken. Lees meer over het onderwerp in de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/docs/commerce-admin/systems/data-transfer/data-dashboard.html) documentatie. Dit huidige onderwerp blijft voor die gebruikers die nog moeten bevorderen en nog het dashboard van de Synchronisatie van de Catalogus hebben.

Adobe Commerce gebruikt indexen om catalogusgegevens in tabellen te compileren. Het proces wordt automatisch geactiveerd door [gebeurtenissen](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html#events-that-trigger-full-reindexing) zoals een wijziging van de productprijs of het voorraadniveau.

De dienst van de Synchronisatie van de Catalogus verplaatst productgegevens van een [!DNL Adobe Commerce] aan de [!DNL Commerce Services] de gegevens voortdurend actueel te houden. Bijvoorbeeld: [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) vereist huidige catalogusinformatie om aanbevelingen met correcte namen, prijs, en beschikbaarheid nauwkeurig terug te keren. Gebruik de _Catalogus synchroniseren_ het dashboard om het synchronisatieproces of het [opdrachtregelinterface](#resynccmdline) catalogussynchronisatie activeren en productgegevens opnieuw indexeren voor gebruik door [!DNL Commerce Services].

## Het dashboard Catalog Sync openen

Selecteer **Systeem** > _Gegevensoverdracht_ > **Catalogus synchroniseren**.

Met de **Catalogus synchroniseren** dashboard dat u kunt:

- De synchronisatiestatus weergeven (**In uitvoering**, **Succes**, **Mislukt**)
- Het totale aantal gesynchroniseerde producten weergeven
- Gesynchroniseerde producten zoeken om hun huidige status weer te geven
- Catalogus zoeken op naam, SKU, enz.
- Gesynchroniseerde productgegevens weergeven in JSON om een synchronisatieverschil te diagnosticeren
- Het synchronisatieproces opnieuw starten

### Laatste synchronisatie

Meldt de synchronisatiestatus van:

- **Succes** - Geeft de datum en tijd weer waarop de synchronisatie is gelukt en het aantal bijgewerkte producten
- **Mislukt** - Geeft de datum en tijd weer waarop de synchronisatie is uitgevoerd
- **In uitvoering** - Geeft de datum en tijd weer van de laatste geslaagde synchronisatie

Het synchronisatieproces van de catalogus wordt automatisch om het uur uitgevoerd. Als u de verwachte producten niet ziet in de winkel of als de producten geen weerspiegeling zijn van recente wijzigingen die u hebt aangebracht, kunt u deze oplossen [problemen met catalogussynchronisatie](#resolvesync).

### Gesynchroniseerde producten

Hiermee geeft u het totale aantal producten weer dat is gesynchroniseerd met uw [!DNL Commerce] catalogus. Na de eerste synchronisatie moeten alleen gewijzigde producten worden gesynchroniseerd.

## Resync {#resync}

Als u een resync van uw catalogus moet in werking stellen alvorens de per uur geplande synchronisatie voorkomt, kunt u een resync dwingen.

>[!NOTE]
>
> Dwingend een resync teweegbrengt een resync van uw volledige productcatalogus, die lading op hardwaremiddelen kan verhogen.

1. Van de _Catalogus synchroniseren_ dashboard, selecteren **Instellingen**.

   De _Instellingen voor catalogussynchronisatie_ wordt weergegeven.

1. In de _Gegevens opnieuw synchroniseren_ sectie, klikken [!UICONTROL Resync].

   [!DNL Commerce] synchroniseert de catalogus tijdens het volgende geplande synchronisatievenster. Afhankelijk van de grootte van de catalogus kan deze bewerking lang duren.

## Gesynchroniseerde catalogusproducten

De **Gesynchroniseerde catalogusproducten** in de tabel wordt de volgende informatie weergegeven.

| Veld | Beschrijving |
|---|---|
| ID | Unieke identificatiecode van het product |
| Naam | Storefront-naam van het product |
| Type | Identificeert het producttype, zoals eenvoudig, configureerbaar, of downloadbaar |
| Laatst geëxporteerd | De datum waarop het product voor het laatst is geëxporteerd uit uw catalogus |
| Laatst gewijzigd | Datum waarop het product voor het laatst is gewijzigd in uw catalogus |
| SKU | Geeft de voorraadeenheid voor het product weer |
| Prijs | Prijs van het product |
| Zichtbaarheid | De zichtbaarheidsinstelling van een product zoals gedefinieerd in het dialoogvenster [!DNL Commerce] catalogus |

## Synchronisatieproblemen met catalogi oplossen {#resolvesync}

Wanneer u een gegevensresync teweegbrengt, kan het tot een uur voor de gegevens duren om bij te werken en in UI componenten zoals aanbeveling eenheden worden weerspiegeld. Raadpleeg het volgende als u nog steeds discrepanties ziet tussen uw catalogus en de gegevens in de winkel, of als de catalogussynchronisatie is mislukt:

### Gegevensafwijking

1. Geef de gedetailleerde weergave van het desbetreffende product weer in de zoekresultaten.
1. Kopieer de JSON-uitvoer en controleer of de inhoud overeenkomt met de inhoud in het dialoogvenster [!DNL Commerce] catalogus.
1. Als de inhoud niet overeenkomt, brengt u een kleine wijziging aan in het product in de catalogus, zoals het toevoegen van een spatie of een punt.
1. Wacht op resync of [een handmatige resync activeren](#resync).

### Synchronisatie wordt niet uitgevoerd

Als de synchronisatie niet volgens een schema wordt uitgevoerd of er niets wordt gesynchroniseerd, raadpleegt u deze [KnowledgeBase](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-product-recommendations-module-in-magento-commerce.html) artikel.

### Synchronisatie is mislukt

Als de catalogussync de status **Mislukt**, een [ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket).

## Opdrachtregelinterface {#resynccmdline}

De `saas:resync` maakt deel uit van de `magento/saas-export` en is beschikbaar in de doos met een van de [!DNL Commerce Services] producten, zoals [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md) of [[!DNL Live Search]](/help/live-search/install.md).

>[!NOTE]
>
> Wanneer u een gegevenssync voor de eerste keer uitvoert, voert u de opdracht `productattributes` voer eerst, gevolgd door `productoverrides`, voordat u de `products` voer.

Opdrachtopties:

```bash
bin/magento saas:resync --feed <feed name> [no-reindex|cleanup-feed]
```

In de volgende tabel worden de `saas:resync` parameters en beschrijvingen.

| Parameter | Beschrijving | Vereist? |
|---| ---| ---|
| `feed` | Geeft aan welke entiteit opnieuw moet worden gesynchroniseerd, zoals `products` | Ja |
| `no-reindex` | Hiermee verzendt u de bestaande catalogusgegevens opnieuw naar [!DNL Commerce Services] zonder opnieuw te indexeren. Wanneer deze parameter niet is opgegeven, voert de opdracht een volledige redex uit voordat gegevens worden gesynchroniseerd. | Nee |
| `cleanup-feed` | Schoont de indexeertabel van de feed vóór een synchronisatie. | Nee |

De voedernaam kan één van het volgende zijn:

- `products`— Producten in uw catalogus
- `productattributes`— Productkenmerken zoals `activity`, `gender`, `tops`, `bottoms`, enzovoort
- `variants`— Productvariaties van een configureerbaar product, zoals kleur en grootte
- `prices` — Productprijzen
- `scopesCustomerGroup` — Klantengroepen
- `scopesWebsite` — Websites met winkelweergaven
- `categories`— Categorieën in uw catalogus
- `categoryPermissions` - Machtigingen voor elk van de categorieën
- `productoverrides`— Klantspecifieke regels voor prijzen en zichtbaarheid van catalogi, zoals regels die zijn gebaseerd op categorietoestemmingen

Afhankelijk van [Commerciële diensten](../landing/saas.md) zijn geïnstalleerd, hebt u mogelijk verschillende feeds beschikbaar voor `saas:resync` gebruiken.

Het wordt afgeraden de opdracht `saas:resync` regelmatig te gebruiken. Mogelijk moet u de opdracht handmatig uitvoeren in twee scenario&#39;s:

- De eerste synchronisatie
- De [SaaS Data Space ID](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) is gewijzigd

### Beginsynchronisatie

Wanneer u een `saas:resync` Afhankelijk van de grootte van de catalogus kan het enkele minuten tot enkele uren duren voordat de gegevens zijn bijgewerkt.

Voor de eerste synchronisatie wordt aangeraden opdrachten in de volgende volgorde uit te voeren:

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

### Problemen oplossen

Als u de verwachte gegevens niet ziet in [!DNL Commerce Service], controleert u of er een probleem is opgetreden tijdens de synchronisatie vanuit de [!DNL Adobe Commerce] aan de [!DNL Commerce Service] platform.

Er zijn twee logbestanden in het dialoogvenster `var/log/` map:

- `commerce-data-export-errors.log` - als er een fout is opgetreden tijdens _verzamelen_ fase
- `saas-export-errors.log` - als er een fout is opgetreden tijdens _verzenden_ fase

#### De lading van de voer controleren

Het kan handig zijn om de feed-lading te zien die naar de [!DNL Commerce Service]. Dit kan door de omgevingsvariabele door te geven `EXPORTER_EXTENDED_LOG=1`. De `no-reindex` markering betekent dat alleen momenteel verzamelde gegevens worden verzonden.

```bash
EXPORTER_EXTENDED_LOG=1 bin/magento saas:resync --feed=products --no-reindex
```

De lading is beschikbaar in `var/log/saas-export.log`.

#### Payload behouden in voederindextabel

Startpagina van `magento/module-data-exporter:103.0.0` bepaalde feeds : productfeed , prijsfeeds , alleen de minimaal vereiste gegevens in de indextabel bewaren .

Het behouden van ladingsgegevens in de indexlijst wordt niet geadviseerd op productie, maar het kan op een ontwikkelaarinstantie nuttig zijn. Dit doet u door het `PERSIST_EXPORTED_FEED=1` omgevingsvariabele:

```bash
PERSIST_EXPORTED_FEED=1 bin/magento saas:resync --feed=products
```

#### Profielen

Als het opnieuw indexproces van specifieke voer een onredelijke hoeveelheid tijd vergt, stel profiler in werking om extra gegevens te verzamelen die voor het Team van de Steun nuttig zouden kunnen zijn. Om dit te doen, geef `EXPORTER_PROFILER=1`omgevingsvariabele:

```bash
EXPORTER_PROFILER=1 bin/magento indexer:reindex catalog_data_exporter_products
```

Profilergegevens worden opgeslagen in `var/log/commerce-data-export.log` met het formaat:

`<Provider class name>, <# of processed entities>, <execution time im ms>, <memory consumption in Mb>`

#### Een ondersteuningsverzoek indienen

Als u fouten ziet die niet te maken hebben met configuratie of extensies van derden, dient u een [ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket) met zoveel mogelijk informatie.
