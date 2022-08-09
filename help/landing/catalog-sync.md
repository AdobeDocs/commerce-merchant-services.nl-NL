---
title: Catalogus synchroniseren
description: Leer hoe u productgegevens exporteert vanuit de [!DNL Commerce] server naar [!DNL Commerce Services] om de diensten voortdurend up-to-date te houden.
exl-id: 19d29731-097c-4f5f-b8c0-12f9c91848ac
source-git-commit: 68e615671f4e465d7fe89794613dbf129ae66dbf
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---

# Catalogus synchroniseren

Adobe Commerce en Magento Open Source gebruiken indexen om catalogusgegevens in tabellen te compileren. Het proces wordt automatisch geactiveerd door [gebeurtenissen](https://docs.magento.com/user-guide/system/index-management-events.html) zoals een wijziging van de productprijs of het voorraadniveau.

Het synchronisatieproces van de catalogus wordt om het uur uitgevoerd [!DNL Commerce] services voor het gebruik van catalogusgegevens. Met Catalogussynchronisatie worden productgegevens geëxporteerd uit de [!DNL Commerce] server naar [!DNL Commerce] diensten om de diensten voortdurend up-to-date te houden. Bijvoorbeeld: [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) heeft huidige catalogusinformatie nodig om aanbevelingen met correcte namen, prijs, en beschikbaarheid nauwkeurig terug te keren. U kunt de _Catalogus synchroniseren_ het dashboard om het synchronisatieproces of het [opdrachtregelinterface](#resynccmdline) catalogussynchronisatie en nieuwe productgegevens activeren op [!DNL Commerce] diensten.

>[!NOTE]
>
> Als u de opdracht _Catalogus synchroniseren_ dashboard of de bevel-lijn interface, moet u hebben [API-sleutel en een SaaS-gegevensruimte geconfigureerd](saas.md).

## Het dashboard Catalog Sync openen

Selecteer **Systeem** > _Gegevensoverdracht_ > **Catalogus synchroniseren**.

Met de **Catalogus synchroniseren** dashboard dat u kunt gebruiken:

- De synchronisatiestatus weergeven (**In uitvoering**, **Succes**, **Mislukt**)
- Het totale aantal gesynchroniseerde producten weergeven als dit gelukt is
- Gesynchroniseerde producten zoeken om hun huidige status te bekijken
- Catalogus zoeken op naam, SKU, enzovoort
- Gesynchroniseerde productgegevens weergeven in JSON om een synchronisatieverschil te diagnosticeren
- Het synchronisatieproces opnieuw starten

### Laatste synchronisatie

Meldt de synchronisatiestatus van:

- **Succes** - Geeft de datum en tijd weer waarop de synchronisatie is gelukt en het aantal producten dat is bijgewerkt
- **Mislukt** - Geeft de datum en tijd weer waarop de synchronisatie is uitgevoerd
- **In uitvoering** - Geeft de datum en tijd weer van de laatste geslaagde synchronisatie

>[!NOTE]
>
> Het synchronisatieproces van de catalogus wordt automatisch elke uur uitgevoerd. Als u echter geen producten ziet in uw winkel of als de producten geen weerspiegeling zijn van recente wijzigingen die u hebt aangebracht, kunt u deze oplossen [problemen met catalogussynchronisatie](#resolvesync).

### Gesynchroniseerde producten

Hiermee geeft u het totale aantal producten weer dat via uw [!DNL Commerce] catalogus. Na de eerste synchronisatie moet u verwachten dat alleen gewijzigde producten worden gesynchroniseerd.

## Resync {#resync}

Als u een resync van uw catalogus moet in werking stellen alvorens de per uur geplande synchronisatie voorkomt, kunt u een resync dwingen.

>[!NOTE]
>
> Dwingend een resync teweegbrengt een resync van uw volledige productcatalogus, die lading op hardwaremiddelen kan verhogen.

1. Van de _Catalogus synchroniseren_ dashboard, selecteren **Instellingen**.

   De _Instellingen voor catalogussynchronisatie_ wordt weergegeven.

1. In de _Gegevens opnieuw synchroniseren_ sectie, klikt u op [!UICONTROL Resync].

   [!DNL Commerce] synchroniseert de catalogus tijdens het volgende geplande synchronisatievenster. Afhankelijk van de grootte van de catalogus kan deze bewerking lang duren.

## Gesynchroniseerde catalogusproducten

De **Gesynchroniseerde catalogusproducten** in de tabel wordt de volgende informatie weergegeven.

| Veld | Beschrijving |
|---|---|
| ID | Unieke identificatiecode van het product |
| Naam | Storefront-naam van het product |
| Type | Identificeert het producttype, zoals eenvoudig, configureerbaar, downloadbaar, etc. |
| Laatst geëxporteerd | De datum waarop het product voor het laatst is geëxporteerd uit uw catalogus |
| Laatst gewijzigd | Datum waarop het product voor het laatst is gewijzigd in uw catalogus |
| SKU | Hiermee geeft u de voorraadeenheid voor het product weer |
| Prijs | Prijs van het product |
| Zichtbaarheid | De zichtbaarheidsinstelling van een product zoals gedefinieerd in het dialoogvenster [!DNL Commerce] catalogus |

## Synchronisatieproblemen met catalogi oplossen {#resolvesync}

Wanneer u een gegevensresync teweegbrengt, kan het tot een uur voor de gegevens duren om bij te werken en in componenten UI, zoals aanbeveling eenheden worden weerspiegeld. Als u echter na een uur nog steeds discrepanties opmerkt tussen uw catalogus en wat er op uw winkel wordt weergegeven, of als de catalogussynchronisatie is mislukt, raadpleegt u het volgende:

### Gegevensdiscrepantie

1. Geef de gedetailleerde weergave van het desbetreffende product weer in de zoekresultaten.
1. Kopieer de JSON-uitvoer en controleer of de inhoud overeenkomt met de inhoud in het dialoogvenster [!DNL Commerce] catalogus.
1. Als de inhoud niet overeenkomt, brengt u een kleine wijziging aan in het product in de catalogus, zoals het toevoegen van een spatie of een punt.
1. Wacht op resync of [handmatig opnieuw synchroniseren](#resync).

### Synchronisatie wordt niet uitgevoerd

Als de synchronisatie niet volgens een schema wordt uitgevoerd of er niets wordt gesynchroniseerd, raadpleegt u de [KnowledgeBase](https://support.magento.com/hc/en-us/articles/360042224851).

### Synchronisatie is mislukt

Als de catalogussync een status heeft van **Mislukt**, een [ondersteuningsticket](https://support.magento.com/hc/en-us/articles/360000913794#submit-ticket).

## Opdrachtregelinterface {#resynccmdline}

De `saas:resync` maakt deel uit van de `magento/saas-export` pakket. U kunt dit pakket installeren met een van de [!DNL Commerce Services] producten, zoals [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md) of [[!DNL Live Search]](/help/live-search/install.md).

>[!NOTE]
>
> Wanneer u een gegevensresync van de bevellijn teweegbrengt, kan het tot een uur voor de gegevens duren om bij te werken.

Opdrachtopties:

```bash
bin/magento saas:resync --feed <feed name> [no-reindex]
```

In de volgende tabel worden de `saas:resync` parameters en beschrijvingen.

| Parameter | Beschrijving | Vereist? |
|---| ---| ---|
| `feed` | Geeft aan welke entiteit opnieuw moet worden gesynchroniseerd, zoals `products` | Ja |
| `no-reindex` | Hiermee verzendt u de bestaande catalogusgegevens opnieuw naar [!DNL Commerce Services] zonder opnieuw te indexeren. Wanneer deze parameter niet is opgegeven, voert de opdracht een volledige redex uit voordat gegevens worden gesynchroniseerd. | Nee |

De voedernaam kan één van het volgende zijn:

- `products`— Producten in uw catalogus
- `categories`— Categorieën in uw catalogus
- `variants`— Productvariaties van een configureerbaar product, zoals kleur en grootte
- `productattributes`— Productkenmerken zoals `activity`, `gender`, `tops`, `bottoms`, enzovoort
- `productoverrides`— Klantspecifieke regels voor prijzen en zichtbaarheid van catalogi, zoals regels die zijn gebaseerd op categorietoestemmingen

### Voorbeelden

In het volgende voorbeeld worden de productgegevens van de [!DNL Commerce] catalogiseren en opnieuw synchroniseren naar de diensten van de Handel:

```bash
bin/magento saas:resync --feed products
```

Als u de producten niet volledig opnieuw wilt indexeren, kunt u in plaats daarvan de productgegevens synchroniseren die al zijn gegenereerd:

```bash
bin/magento saas:resync --feed products --no-reindex
```
