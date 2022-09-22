---
title: '[!DNL Catalog Service]'
description: '''[!DNL Catalog Service] voor Adobe Commerce biedt een manier om de inhoud van de pagina''s met productweergave en de pagina''s met productlijsten veel sneller op te halen dan de native Adobe Commerce GraphQL-query''s.'''
exl-id: 266faca4-6a65-4590-99a9-65b1705cac87
source-git-commit: dfe3d9b8738ea68257831c445f1f0b2c8c8b6859
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---

# [!DNL Catalog Service] voor Adobe Commerce

{{catalog-service-beta}}

De [!DNL Catalog Service] voor Adobe Commerce-extensie biedt uitgebreide view-model (alleen-lezen) catalogusgegevens waarmee productgerelateerde winkelervaringen snel en volledig kunnen worden weergegeven, zoals:

* Productdetailpagina&#39;s
* Productlijst en categoriepagina&#39;s
* Zoekresultatenpagina&#39;s
* Productcarrousels
* Productvergelijkingspagina&#39;s
* Alle andere pagina&#39;s die productgegevens weergeven, zoals pagina&#39;s met een cart-, volgorde- en wenslijst

De [!DNL Catalog Service] gebruik [GraphQL](https://graphql.org/) om productgegevens aan te vragen en te ontvangen. GraphQL is een vraagtaal die een frontend cliënt gebruikt om met de toepassing te communiceren programmeringsinterface (API) die op een backend zoals Adobe Commerce wordt bepaald. GraphQL is een populaire methode van mededeling omdat het lichtgewicht is en een systeemintegrator toestaat om de inhoud en de orde van elke reactie te specificeren.

Adobe Commerce heeft twee GraphQL-systemen. Het kern systeem GraphQL verstrekt een brede waaier van vragen (gelezen verrichtingen) en mutaties (schrijf verrichtingen) die een verkoopster toestaan om met vele soorten pagina&#39;s, met inbegrip van product, klantenrekening, kar, controle, en meer in wisselwerking te staan. Nochtans, worden de vragen die productinformatie terugkeren niet geoptimaliseerd voor snelheid. Het systeem van GraphQL van de diensten kan vragen op producten en verwante informatie slechts uitvoeren. Deze query&#39;s leveren meer op dan vergelijkbare core query&#39;s.

## Architectuur

Het volgende diagram toont de twee systemen GraphQL:

![Catalogusarchitectuurdiagram](assets/catalog-service-architecture.png)

In het kern systeem GraphQL, verzendt de PWA een verzoek naar de toepassing van de Handel, die elk verzoek ontvangt, het verwerkt, misschien verzendend een verzoek door veelvoudige subsystems, dan keert een antwoord op de storefront terug. Deze ronde trip kan leiden tot een trage laadtijd voor de pagina, wat kan leiden tot lagere conversiesnelheden.

[!DNL Catalog Service] verzendt vragen naar een afzonderlijke gateway GraphQL. De dienst heeft toegang tot een afzonderlijk gegevensbestand dat productdetails en verwante informatie, zoals productattributen, varianten, prijzen, en categorieën bevat. De service houdt de database via indexering synchroon met de Adobe Commerce.
Omdat de dienst directe communicatie met de toepassing overslaat, kan het de latentie van de verzoek en reactiecyclus verminderen.

>[!NOTE]
>
>De gateway is voor toekomstige integratie met Product Recommendations. In deze release hebt u toegang tot [!DNL Catalog Service] en [!DNL Live Search] de gefederaliseerde vragen van het zelfde eindpunt als u een geldige vergunningssleutel voor beide producten hebt.

De kern en de dienst systemen GraphQL communiceren niet direct met elkaar. U hebt toegang tot elk systeem via een andere URL en voor aanroepen is andere headerinformatie nodig. De twee systemen GraphQL worden ontworpen om samen worden gebruikt. De [!DNL Catalog Service] GraphQL-systeem versterkt het kernsysteem om producten sneller op de markt te brengen.

U kunt optioneel implementeren [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/) om de twee Adobe Commerce GraphQL-systemen te integreren met private en externe API&#39;s en andere softwareinterfaces die Adobe Developer gebruiken. Het netwerk kan worden gevormd om vraag te verzekeren die aan elk eindpunt wordt verpletterd bevat de correcte vergunningsinformatie in de kopballen.

## Implementatie

Voor het installatieproces moet de configuratie van de [Commerce Services Connector](../landing/saas.md). Zodra dat wordt verwezenlijkt, is de volgende stap voor een systeemintegrator om de storefront code bij te werken om op te nemen [!DNL Catalog Service] query&#39;s. Alles [!DNL Catalog Service] de vragen worden verpletterd aan de gateway GraphQL. De URL wordt tijdens het instapproces opgegeven.
