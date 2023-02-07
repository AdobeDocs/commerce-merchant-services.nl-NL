---
title: '[!DNL Catalog Service]'
description: '''[!DNL Catalog Service] voor Adobe Commerce biedt een manier om de inhoud van de pagina''s met productweergaven en de pagina''s met productlijsten veel sneller op te halen dan de GraphQL-zoekopdrachten van de native Adobe Commerce.'''
exl-id: 266faca4-6a65-4590-99a9-65b1705cac87
source-git-commit: dd9ba7171cf6a199701b1abb8083a65326e89f5d
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---

# [!DNL Catalog Service] voor Adobe Commerce

De [!DNL Catalog Service] voor Adobe Commerce-extensie biedt uitgebreide view-model (alleen-lezen) catalogusgegevens waarmee productgerelateerde winkelervaringen snel en volledig kunnen worden weergegeven, zoals:

* Productdetailpagina&#39;s
* Productlijst en categoriepagina&#39;s
* Zoekresultatenpagina&#39;s
* Productcarrousels
* Productvergelijkingspagina&#39;s
* Alle andere pagina&#39;s die productgegevens weergeven, zoals pagina&#39;s met een cart-, volgorde- en wenslijst

De [!DNL Catalog Service] gebruik [GraphQL](https://graphql.org/) om productgegevens aan te vragen en te ontvangen. GraphQL is een querytaal die een front-end client gebruikt om te communiceren met de API (Application Programming Interface) die op een back-end zoals Adobe Commerce is gedefinieerd. GraphQL is een veelgebruikte communicatiemethode omdat deze lichtgewichtgericht is en een systeemintegrator de inhoud en volgorde van elke reactie kan opgeven.

Adobe Commerce heeft twee GraphQL-systemen. Het kernGraphQL systeem verstrekt een brede waaier van vragen (lees verrichtingen) en mutaties (schrijf verrichtingen) die een verkoopster toestaan om met vele soorten pagina&#39;s, met inbegrip van product, klantenrekening, kar, controle, en meer in wisselwerking te staan. Nochtans, worden de vragen die productinformatie terugkeren niet geoptimaliseerd voor snelheid. Het GraphQL-systeem voor services kan alleen query&#39;s uitvoeren op producten en gerelateerde informatie. Deze query&#39;s leveren meer op dan vergelijkbare core query&#39;s.

## Architectuur

In het volgende diagram worden de twee GraphQL-systemen weergegeven:

![Catalogusarchitectuurdiagram](assets/catalog-service-architecture.png)

In het kernGraphQL systeem, verzendt de PWA een verzoek naar de toepassing van de Handel, die elk verzoek ontvangt, verwerkt het, misschien verzendend een verzoek door veelvoudige subsystems, dan keert een antwoord op de opslag terug. Deze ronde trip kan leiden tot een trage laadtijd voor de pagina, wat kan leiden tot lagere conversiesnelheden.

[!DNL Catalog Service] is een Gateway van de Diensten Storefront. De dienst heeft toegang tot een afzonderlijk gegevensbestand dat productdetails en verwante informatie, zoals productattributen, varianten, prijzen, en categorieën bevat. De service houdt de database via indexering synchroon met de Adobe Commerce.
Omdat de dienst directe communicatie met de toepassing overslaat, kan het de latentie van de verzoek en reactiecyclus verminderen.

>[!NOTE]
>
>De gateway is voor toekomstige integratie met Product Recommendations. In deze release hebt u toegang tot de [!DNL Catalog Service GraphQL] en de [!DNL Live Search] vragen van het zelfde eindpunt als u een geldige vergunningssleutel voor beide producten hebt.

De kern en de dienstGraphQL systemen communiceren niet direct met elkaar. U hebt toegang tot elk systeem via een andere URL en voor aanroepen is andere headerinformatie nodig. De twee GraphQL-systemen zijn ontworpen voor gezamenlijk gebruik. De [!DNL Catalog Service] Het GraphQL-systeem is een aanvulling op het kernsysteem, zodat producten sneller kunnen worden opgeslagen.

U kunt optioneel implementeren [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/) de twee Adobe Commerce GraphQL-systemen te integreren met particuliere en externe API&#39;s en andere software-interfaces met Adobe Developer. Het netwerk kan worden gevormd om vraag te verzekeren die aan elk eindpunt wordt verpletterd bevat de correcte vergunningsinformatie in de kopballen.

## Architectuurgegevens

In de volgende secties worden enkele verschillen tussen de twee GraphQL-systemen beschreven.

### Schema-beheer

Aangezien de Catalogusdienst als dienst werkt, hoeven integrators zich niet bezorgd te maken over de onderliggende versie van Handel. De syntaxis van de query&#39;s is voor alle versies hetzelfde. Bovendien is het schema verenigbaar voor alle handelaren. Deze consistentie maakt het gemakkelijker om beste praktijken te vestigen, en verhoogt opnieuw gebruik van storefront widgets beduidend.

### Vereenvoudiging van productsoorten

Het schema vermindert de diversiteit van producttypen tot twee gebruiksgevallen:

* Eenvoudige producten zijn producten die worden gedefinieerd met één prijs en hoeveelheid. De Catalogusservice wijst de eenvoudige, virtuele, downloadbare en cadeau-kaartproducttypen toe aan `simpleProductViews`.

* Complexe producten bestaan uit meerdere eenvoudige producten. De componenten eenvoudige producten kunnen verschillende prijzen hebben. Een complex product kan ook worden bepaald zodat de verkoopster de hoeveelheid componenten eenvoudige producten kan specificeren. De Dienst van de Catalogus brengt de configureerbare, bundel, en gegroepeerde producttypes aan in kaart `complexProductViews`.

Complexe productopties worden verenigd en onderscheiden door hun gedrag, niet door type. Elke optiewaarde vertegenwoordigt een eenvoudig product. Deze optie heeft toegang tot de eenvoudige productkenmerken, inclusief prijs. Wanneer de verkoper alle opties voor een complex product selecteert, wijst de combinatie geselecteerde opties naar een specifiek eenvoudig product. Het eenvoudige product blijft dubbelzinnig totdat de gebruiker een waarde voor alle beschikbare opties selecteert.

### Prijzen

Eenvoudige producten vertegenwoordigen de basisverkoopeenheid die een prijs heeft. De Catalogusservice berekent de normale prijs vóór kortingen en de uiteindelijke prijs na kortingen. Prijsberekeningen kunnen vaste productbelastingen bevatten. Ze sluiten gepersonaliseerde promoties uit.

Een complex product heeft geen vaste prijs. In plaats daarvan retourneert de Catalogusservice de prijzen van gekoppelde voorbeelden. Een handelaar kan bijvoorbeeld in eerste instantie dezelfde prijzen toewijzen aan alle varianten van een configureerbaar product. Als bepaalde grootten of kleuren niet populair zijn, kan de handelaar de prijzen van die varianten verlagen. De prijs van het complexe (configureerbare) product vertoont dus eerst een prijsbereik, dat de prijs van zowel standaard- als niet-populaire varianten weerspiegelt. Nadat de winkelier een waarde voor alle beschikbare opties heeft geselecteerd, toont de winkel één enkele prijs.

## Implementatie

Voor het installatieproces moet de configuratie van de [Commerce Services Connector](../landing/saas.md). Zodra dat wordt verwezenlijkt, is de volgende stap voor een systeemintegrator om de storefront code bij te werken om op te nemen [!DNL Catalog Service] query&#39;s. Alles [!DNL Catalog Service] query&#39;s worden gerouteerd naar de GraphQL-gateway. De URL wordt tijdens het instapproces opgegeven.
