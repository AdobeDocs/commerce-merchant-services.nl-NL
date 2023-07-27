---
title: Feed Ingestie Service
description: Meer informatie over de Feed Ingestie Service voor Adobe Commerce
source-git-commit: b484429a529acfa95f70c5a55b6a5fcdedc887b3
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Feed Ingestie Service

>[!NOTE]
>
>De dienst van de Ingestie van het voer is momenteel in privé bèta. Het is nog niet beschikbaar voor algemeen gebruik.

De dienst van de Ingestie van de Diervoeders vermindert de tijd het om productveranderingen (prijsupdates, toevoegend nieuwe attributen) te verwerken door de instantie van Adobe Commerce te mijden en catalogusgegevens van een derde van de Planning van het Middel van de Onderneming (ERP) rechtstreeks aan de diensten van Adobe Commerce te bewegen.

Deze service is bedoeld voor klanten die hun productcatalogus opslaan en beheren in een systeem dat zich niet in de belangrijkste Adobe Commerce-toepassing bevindt.

Klanten met grote, complexe catalogi of catalogi die regelmatig worden bijgewerkt, maken zich zorgen dat de nieuwe gegevens langer kunnen duren dan u wilt weergeven in de live winkel. Aangezien de Dienst van de Catalogus weet welke gegevens het vereist om deze updates te verwerken, is er geen behoefte om de gegevens door het kernproduct van de Handel te verzenden, slechts aan de Dienst van de Catalogus door:sturen. Als u deze tussenstap verwijdert, worden efficiëntieverbeteringen gevonden.

## Invoerstromen van diervoeders

Afhankelijk van de Adobe Commerce-configuratie kunnen gegevensopslag en gegevensstromen verschillende paden volgen.

* In een standaard Adobe Commerce-instantie wordt de productcatalogus opgeslagen in de kerndatabase.
* Wanneer u Adobe Commerce Services gebruikt, worden catalogusgegevens gekopieerd van de kerndatabase naar de service en worden deze verwerkt en van daaruit geleverd.
* Wanneer het opslaan van catalogusgegevens in een derdesysteem (ERP, MDM, PIM), stromen de gegevens door de kerntoepassing van de Handel en dan aan de diensten van de Handel.
* Met de dienst van de Ingestie van de Diervoeders, gaan de productgegevens rechtstreeks van het derdesysteem naar de de diensteninfrastructuur van de Handel.

![Diervoederingestie](assets/feed-ingestion.png)

Door de kerntoepassing van de Handel over te slaan en gegevens rechtstreeks naar de diensten van de Handel te verplaatsen, worden de productupdates weerspiegeld in de winkel sneller. De catalogusgegevens van de kern, zoals SKUs, worden verzonden naar de belangrijkste toepassing van de Handel voor afzonderlijke verwerking.

## Deelnemen aan de bèta

De Feed IngestiService is ontworpen voor:

* Klanten uit de middelbare onderneming met headless implementaties
* Klanten met grote, complexe catalogi
* Klanten die de Adobe Commerce Admin niet gebruiken om catalogusgegevens te beheren, gebruiken in plaats daarvan een ERP- of een extern systeem om catalogusgegevens te beheren

Als u geïnteresseerd bent in deelname aan het bètaprogramma, neemt u contact op met het team op XXXXX@adobe.com.
