---
title: Data Ingestie Service
description: Meer informatie over de Data Ingestie Service voor Adobe Commerce
exl-id: bb5aec74-faca-42ec-9fdb-3261677d451e
source-git-commit: a2f933151481cbdd39d66a0dfbd36e6c339ede62
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Data Ingestie Service

Met de Data Ingestie Service kunnen klanten met grote en/of complexe catalogi gegevens rechtstreeks naar Adobe Commerce-services verzenden.

De Data Ingestie Service verkort de tijd die nodig is om productwijzigingen (prijsupdates, het toevoegen van nieuwe kenmerken) te verwerken door de Adobe Commerce-instantie te omzeilen en catalogusgegevens van een externe Enterprise Resource Planning (ERP) rechtstreeks naar Adobe Commerce-services te verplaatsen.

Deze service is bedoeld voor klanten die hun productcatalogus opslaan en beheren in een systeem dat zich niet in de belangrijkste Adobe Commerce-toepassing bevindt. Het wordt verstrekt als API, zodat de klanten het in hun bestaande systemen kunnen integreren, die extra flexibiliteit in verstrekken hoe het wordt opgesteld.

Klanten met grote, complexe catalogi of catalogi die regelmatig worden bijgewerkt, maken zich zorgen dat de nieuwe gegevens langer kunnen duren dan u wilt weergeven in de live winkel. Aangezien de Dienst van de Catalogus weet welke gegevens het vereist om deze updates te verwerken, is er geen behoefte om de gegevens door het kernproduct van de Handel te verzenden, slechts aan de Dienst van de Catalogus door:sturen. Als u deze tussenstap verwijdert, worden efficiëntieverbeteringen gevonden.

## Gegevensinscriptiestromen

Afhankelijk van de Adobe Commerce-configuratie kunnen gegevensopslag en gegevensstromen verschillende paden volgen.

* In een standaard Adobe Commerce-instantie wordt de productcatalogus opgeslagen in de kerndatabase.
* Wanneer u Adobe Commerce Services gebruikt, worden catalogusgegevens gekopieerd van de kerndatabase naar de service en worden deze verwerkt en van daaruit geleverd.
* Wanneer het opslaan van catalogusgegevens in een derdesysteem (ERP, MDM, PIM), stromen de gegevens door de kerntoepassing van de Handel en dan aan de diensten van de Handel.
* Met de Dienst van de Ingestie van Gegevens, gaan de productgegevens rechtstreeks van het derdesysteem naar de de diensteninfrastructuur van de Handel.

![Data Ingestie-service](assets/data-ingestion.png)

Door de kerntoepassing van de Handel over te slaan en gegevens rechtstreeks naar de diensten van de Handel te verplaatsen, worden de productupdates weerspiegeld in de winkel sneller. De catalogusgegevens van de kern, zoals SKUs, worden verzonden naar de belangrijkste toepassing van de Handel voor afzonderlijke verwerking.

## API

De [API-documentatie voor Data Ingestie Service](https://developer.adobe.com/commerce/services/data-ingestion) verstrekt details over hoe te om de dienst uit te voeren.
