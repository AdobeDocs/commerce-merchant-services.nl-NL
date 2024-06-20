---
title: Catalogus synchroniseren
description: Leer hoe u productgegevens exporteert vanuit de [!DNL Commerce] server naar [!DNL Commerce Services].
exl-id: 19d29731-097c-4f5f-b8c0-12f9c91848ac
feature: Catalog Management, Data Import/Export, Catalog Service
source-git-commit: af9de40a717d2cb55a5f42483bd0e4cbcd913f64
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---


# Catalogus synchroniseren

>[!NOTE]
>
> Het dashboard voor catalogussynchronisatie is nu het gegevensbeheerdashboard. Dit vernieuwde dashboard ondersteunt nu [[!DNL Product Recommendations]](../product-recommendations/guide-overview.md), [[!DNL Live Search]](../live-search/overview.md), en [[!DNL Catalog Service]](../catalog-service/overview.md). Klanten kunnen het gegevensbeheerdashboard ophalen door de nieuwste versie van een van deze services bij te werken. Lees meer over het onderwerp in de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/docs/commerce-admin/systems/data-transfer/data-dashboard.html) documentatie. Dit huidige onderwerp blijft voor die gebruikers die nog moeten bevorderen en nog het dashboard van de Synchronisatie van de Catalogus hebben.

Adobe Commerce gebruikt indexen om catalogusgegevens in tabellen te compileren. Het proces wordt automatisch geactiveerd door [gebeurtenissen](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/index-management.html#events-that-trigger-full-reindexing) zoals een wijziging van de productprijs of het voorraadniveau.

De dienst van de Synchronisatie van de Catalogus verplaatst productgegevens van een [!DNL Adobe Commerce] aan de [!DNL Commerce Services] de gegevens voortdurend actueel te houden. Bijvoorbeeld: [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) vereist huidige catalogusinformatie om aanbevelingen met correcte namen, prijs, en beschikbaarheid nauwkeurig terug te keren. Gebruik de _Catalogus synchroniseren_ dashboard om het synchronisatieproces of de opdrachtregelinterface te observeren en te beheren voor het activeren van een catalogussync en het opnieuw indexeren van productgegevens voor gebruik door [!DNL Commerce Services]. Zie [Referentie opdrachtregelinterface](../data-export/data-export-cli-commands.md) in de _SaaS-gegevens exporteren_ Hulplijn.

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

Zie [Logboeken en probleemoplossing](../data-export/troubleshooting-logging.md#troubleshooting) in de _Handleiding voor het exporteren van SaaS-gegevens_.
