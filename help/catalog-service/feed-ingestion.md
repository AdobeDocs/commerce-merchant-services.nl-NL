---
title: Feed Ingestie Service
description: Meer informatie over de Feed Ingestie Service voor Adobe Commerce
exl-id: bb5aec74-faca-42ec-9fdb-3261677d451e
source-git-commit: d3798efa038c35f71bb0bb6874d954a8e66c7467
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Feed Ingestie Service

Met de Feed Ingestieservice kunnen klanten met grote en/of complexe catalogi gegevens rechtstreeks naar Adobe Commerce-services verzenden.

De dienst van de Ingestie van de Diervoeders vermindert de tijd die het neemt om productveranderingen (prijsupdates, toevoegend nieuwe attributen) te verwerken door de instantie van Adobe Commerce te mijden en catalogusgegevens van een derde van de Planning van het Middel van de Onderneming (ERP) rechtstreeks aan de diensten van Adobe Commerce te bewegen.

Deze service is bedoeld voor klanten die hun productcatalogus opslaan en beheren in een systeem dat zich niet in de belangrijkste Adobe Commerce-toepassing bevindt. Het wordt verstrekt als API, zodat de klanten het in hun bestaande systemen kunnen integreren, die extra flexibiliteit in verstrekken hoe het wordt opgesteld.

Klanten met grote, complexe catalogi of catalogi die regelmatig worden bijgewerkt, maken zich zorgen dat de nieuwe gegevens langer kunnen duren dan u wilt weergeven in de live winkel. Aangezien de Dienst van de Catalogus weet welke gegevens het vereist om deze updates te verwerken, is er geen behoefte om de gegevens door het kernproduct van de Handel te verzenden, slechts aan de Dienst van de Catalogus door:sturen. Als u deze tussenstap verwijdert, worden efficiëntieverbeteringen gevonden.

## Invoerstromen van diervoeders

Afhankelijk van de Adobe Commerce-configuratie kunnen gegevensopslag en gegevensstromen verschillende paden volgen.

* In een standaard Adobe Commerce-instantie wordt de productcatalogus opgeslagen in de kerndatabase.
* Wanneer u Adobe Commerce Services gebruikt, worden catalogusgegevens gekopieerd van de kerndatabase naar de service en worden deze verwerkt en van daaruit geleverd.
* Wanneer het opslaan van catalogusgegevens in een derdesysteem (ERP, MDM, PIM), stromen de gegevens door de kerntoepassing van de Handel en dan aan de diensten van de Handel.
* Met de dienst van de Ingestie van de Diervoeders, gaan de productgegevens rechtstreeks van het derdesysteem naar de de diensteninfrastructuur van de Handel.

![Diervoederingestie](assets/feed-ingestion.png)

Door de kerntoepassing van de Handel over te slaan en gegevens rechtstreeks naar de diensten van de Handel te verplaatsen, worden de productupdates weerspiegeld in de winkel sneller. De catalogusgegevens van de kern, zoals SKUs, worden verzonden naar de belangrijkste toepassing van de Handel voor afzonderlijke verwerking.

## API

De [API-documentatie voor Feed IngestiService](https://developer.adobe.com/commerce/services/feed-ingestion) verstrekt details over hoe te om de dienst uit te voeren.
