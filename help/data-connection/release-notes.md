---
title: Aanvullende informatie
description: De meest recente releasegegevens voor de [!DNL Data Connection] uit Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
feature: Personalization, Integration, Release Notes
source-git-commit: 6378b89e5a077e35213f35e84be9a629c1bdc3ac
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Aanvullende informatie

>[!IMPORTANT]
>
>De naam van de Experience Platform-aansluiting is gewijzigd in [!DNL Data Connection].

Deze releaseopmerkingen bevatten updates voor de [!DNL Data Connection] en omvat:

![Nieuw](../assets/new.svg) - Nieuwe functies
![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
![Bug](../assets/bug.svg) - Bekende problemen

Voor functiewijzigingen en correcties die betrekking hebben op extensies die worden gebruikt door de [!DNL Data Connection] extensie, zie **Ondersteunde service-updates**.

Zie [Volgende releases](https://experienceleague.adobe.com/docs/commerce-operations/release/planning/schedule.html) om over versieschema&#39;s en steun te leren.

Zie de documentatie voor ontwikkelaars op [leren welke versies van de Handel deze module steunen](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Ondersteunde service-updates

In deze releaseopmerkingen worden wijzigingen in functies en correcties beschreven die betrekking hebben op extensies die door de [!DNL Data Connection] extensie.

+++Ondersteunde service-updates

_24 januari 2024_

![Nieuw](../assets/new.svg) - De `data-services-b2b` extensie om een nieuwe aanvraaggebeurtenis op te nemen, genaamd [deleteRequisitionList](events.md#deleterequisitionlist) voor B2B-handelaren.

_16 november 2023_

![Repareren](../assets/fix.svg) - Probleem verholpen waarbij een foutbericht ten onrechte werd weergegeven wanneer u een bestelling met meerdere verzendadressen plaatste.
![Repareren](../assets/fix.svg) - Probleem verholpen in het dialoogvenster [productPageView](events.md#productpageview) gebeurtenis waarbij `productListItems.priceTotal` in het gebeurtenisveld werd de prijs niet geconverteerd nadat de valuta in de winkelweergave was gewijzigd.
![Repareren](../assets/fix.svg) - Probleem verholpen in het dialoogvenster `productListItems` gebeurtenisveld waarin de valutacode niet werd bijgewerkt toen de handelaar van mening veranderde over de winkel.

_10 oktober 2023_

![Nieuw](../assets/new.svg) - Toegevoegde statusgebeurtenissen voor nieuwe bestellingen: [Facturering van bestelling](events.md#orderinvoiced), [Terugsturen van bestelling-item gestart](events.md#orderitemsreturninitiated), en [Terugsturen van bestelling van object voltooid](events.md#orderitemreturncompleted).
![Repareren](../assets/fix.svg) - Probleem verholpen waarbij wijzigingen in de valutaconfiguratie niet werden doorgevoerd in de gebeurtenissen na het vernieuwen van de cache.
![Repareren](../assets/fix.svg) - Correctie van fout wanneer het bevestigingsbericht van de orde niet verschijnt als de asynchrone plaatsing van de orde wordt toegelaten.
![Nieuw](../assets/new.svg) - Gegevens toegevoegd aan [addToRequisitionList](events.md#addtorequisitionlist) gebeurtenis voor eenvoudige producten op de pagina van de categorieweergave.
![Repareren](../assets/fix.svg) - Probleem verholpen in het dialoogvenster `selectedOptions` gegevens in de [addToRequisitionList](events.md#addtorequisitionlist) gebeurtenis wanneer de producten van de de bevestigingspagina van de Orde worden toegevoegd.
![Nieuw](../assets/new.svg) - Toegevoegde productgegevens aan [addToRequisitionList](events.md#addtorequisitionlist) gebeurtenis wanneer de producten aan de vraaglijst van de de meningspagina van de Categorie worden toegevoegd.
![Nieuw](../assets/new.svg) - Toegevoegd [addToRequisitionList](events.md#addtorequisitionlist) gebeurtenis wanneer configureerbare producten aan de verzoeklijst van de de meningspagina van het Product worden toegevoegd.
![Nieuw](../assets/new.svg) - Toegevoegd [addToRequisitionList](events.md#addtorequisitionlist) en [removeFromRequisitionList](events.md#removefromrequisitionlist) voorvallen waarbij de hoeveelheid product wordt verhoogd en/of afgenomen van een aanvraaglijst.

_10 juni 2023_

![Repareren](../assets/fix.svg) - Probleem verholpen waarbij `orderId` niet in de context is geslaagd wegens voorvoegsels in de handels-ordeaanduiding.
![Repareren](../assets/fix.svg) - Bijgewerkte configuraties voor inhoudsbeveiligingsbeleid.

_30 maart 2023_

![Nieuw](../assets/new.svg) - Een extensie met de naam `data-services-b2b` die [gebeurtenissen in aanvraaglijst](events.md#b2b-events) voor B2B-handelaren.
![Nieuw](../assets/new.svg) - Toegevoegde `uniqueIdentifier` veld naar [zoeken](events.md#search-events) gebeurtenissen. Met dit nieuwe veld kunnen verkopers zoekopdrachten en zoekreacties doorzoeken.

_12 oktober 2022_

![Nieuw](../assets/new.svg) - Twee toegevoegd [storefront, gebeurtenissen](events.md), `openCart` en `removeFromCart`, naar de Adobe Commerce Storefront Events SDK en Collector.
![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor een [AEM storefront](overview.md#aem-support).

+++

## 3.1.0.

_16 november 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) - De naam van de aansluiting op het Experience Platform is gewijzigd in [!DNL Data Connection].
![Repareren](../assets/new.svg) - Mogelijkheid toegevoegd om de foutreactie te registreren als Adobe IMS het toegangstoken niet kan genereren.
![Repareren](../assets/new.svg) - Er is een meldingsbericht toegevoegd als u probeert Historische bestellingen te synchroniseren, maar geen accountgegevens hebt opgegeven.

## 3.0.0.

_10 oktober 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Dit is een belangrijke versie. [Bewerken](install.md#update-the-data-connection) het hoofdbestand composer.json van uw project.

![Nieuw](../assets/new.svg) - Algemene beschikbaarheid voor [historische order verzenden](connect-data.md#send-historical-order-data) gegevens en status aan het Experience Platform.
![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor OAuth 2.0 wanneer u [vormen](connect-data.md#connect-commerce-data-to-adobe-experience-platform) de [!DNL Data Connection] extensie.
![Nieuw](../assets/new.svg) - Afgelopen ondersteuning voor Adobe Commerce 2.4.3.

## 2.3.0.

_27 juni 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - Toegevoegde mogelijkheden tot [verzenden van storefront-gebeurtenissen uitschakelen](connect-data.md#data-collection) aan het Experience Platform.
![Repareren](../assets/fix.svg) - Bijgewerkte configuraties voor inhoudsbeveiligingsbeleid.
![Repareren](../assets/fix.svg) - Vaste ondersteuning voor back office evenementen op de versie Commerce 2.4.7.
![Nieuw](../assets/new.svg) - Een meldingsbericht toegevoegd over cachevalidatie wanneer u wijzigingen opslaat in het dialoogvenster [!DNL Data Connection] extensievorm.


## 3.0.0-bèta1 (alleen intern)

_13 juni 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - (Beta) Toegevoegde mogelijkheid tot [historische order verzenden](connect-data.md#beta-send-historical-order-data) gegevens en status aan het Experience Platform. Deze functie is alleen beschikbaar voor bètagebruikers. U kunt deelnemen aan de bètaversie door een e-mail naar het volgende adres te verzenden: `dataconnection@adobe.com`.

## 2.2.0.

_30 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - Gebundelde `commerce-data-export` en `saas-export` afhankelijkheid van de `experience-platform-connector` extensie. Eerder, moest u deze gebiedsdelen afzonderlijk installeren. Deze gebiedsdelen, samen met bedrijfsmatige configuratie, laten server-zijverwerking van toe [back office-gebeurtenissen](events.md#back-office-events).
![Nieuw](../assets/new.svg) - Nieuwe back office-gebeurtenis toegevoegd [`orderShipmentCompleted`](events.md#ordershipmentcompleted).

## 2.1.1.

_28 februari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor PHP 8.2 voor iedereen [!DNL Data Connection] extensies.

## 2.1.0.

_17 januari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - De [[!DNL Data Connection] extensiebeheer](connect-data.md) zodat kunt u uw eigen AEP Web SDK (legering) specificeren.
![Repareren](../assets/fix.svg) Gewijzigd in gebruik `identityMap` in plaats van `personID` wanneer u de primaire identiteit instelt voor gegevens die naar de rand worden verplaatst.

## 2.0.1.

_10 november 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) - Nu wordt de Adobe Experience Platform-context alleen ingesteld nadat de Storageront Event Collector en de Storefront Event SDK zijn geladen.

## 2.0.0.

_12 oktober 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - Toegevoegde mogelijkheid om uw eigen AEP Web SDK op te geven wanneer [verbinden](connect-data.md) uw Adobe Commerce-exemplaar naar het Experience Platform.
![Repareren](../assets/fix.svg) - Vereisten voor een bijgewerkt gegevensstroombereik, zodat de gegevensstroom-id&#39;s binnen het bereik van de website moeten worden geplaatst in plaats van dat ze moeten worden opgeslagen.

## 1.0.0.

_9 augustus 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) - Algemene beschikbaarheidsrelease.
