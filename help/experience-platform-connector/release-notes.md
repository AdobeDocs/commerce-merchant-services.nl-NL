---
title: Opmerkingen bij de release
description: De nieuwste release-informatie voor Adobe Experience Platform-connector vanuit Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
source-git-commit: b48f9eadda233f4996f1e1d806ecc973cfd241c2
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Opmerkingen bij de release

Deze releaseopmerkingen bevatten updates van de aansluiting van het Experience Platform en bevatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) - Bekende problemen

Voor functieveranderingen en moeilijke situaties met betrekking tot uitbreidingen die door de schakelaar van het Experience Platform worden gebruikt, zie **Ondersteunde service-updates**.

Zie [Volgende releases](https://experienceleague.adobe.com/docs/commerce-operations/release/planning/schedule.html) om over versieschema&#39;s en steun te leren.

Zie de documentatie voor ontwikkelaars [informatie over productcompatibiliteit](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).

## Ondersteunde service-updates

Deze versienota&#39;s beschrijven eigenschapveranderingen en moeilijke situaties met betrekking tot uitbreidingen die door de schakelaar van het Experience Platform worden gebruikt.

+++Ondersteunde service-updates

_10 juni 2023_

* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij `orderId` niet in de context is doorgegaan vanwege voorvoegsels in de handels-orderidentificatiecode.
* ![Repareren](../assets/fix.svg) - Bijgewerkte configuraties voor inhoudsbeveiligingsbeleid.

_30 maart 2023_

* ![Nieuw](../assets/new.svg) - Een nieuwe extensie met de naam `data-services-b2b` die [gebeurtenissen in aanvraaglijst](events.md#b2b-events) voor B2B-handelaren
* ![Nieuw](../assets/new.svg) - Toegevoegde `uniqueIdentifier` veld naar [zoeken](events.md#search-events) gebeurtenissen. In dit nieuwe veld kunnen verkopers kruisverwijzingen gebruiken naar zoekverzoeken die overeenkomen met de zoekantwoorden.

_12 oktober 2022_

* ![Nieuw](../assets/new.svg) - Twee toegevoegd [storefront, gebeurtenissen](events.md): `openCart` en `removeFromCart` naar de Adobe Commerce Storefront Events SDK en Collector
* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor een [AEM storefront](overview.md#aem-support)

+++

## 2.2.0

_30 maart 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Nieuw](../assets/new.svg) - Gebundelde `commerce-data-export` en `saas-export` afhankelijkheden met de `experience-platform-connector` extensie. Eerder, moest u deze gebiedsdelen afzonderlijk installeren. Deze gebiedsdelen, samen met koopvaardijconfiguratie, laten server zijverwerking van toe [back office-gebeurtenissen](events.md#back-office-events).
* ![Nieuw](../assets/new.svg) - Nieuwe back office-gebeurtenis toegevoegd [`orderShipmentCompleted`](events.md#ordershipmentcompleted).

## 2.1.1

_28 februari 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor PHP 8.2 voor alle Experience Platform connectormodules

## 2.1.0

_17 januari 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Nieuw](../assets/new.svg) - De [Admin-aansluiting Experience Platform](connect-data.md) zodat kunt u uw eigen AEP Web SDK (legering) specificeren.
* ![Repareren](../assets/fix.svg) Gewijzigd in gebruik `identityMap` in plaats van `personID` wanneer u de primaire identiteit instelt voor gegevens die naar de rand worden geduwd.

## 2.0.1

_10 november 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Probleem opgelost](../assets/fix.svg) - Nu wordt de Adobe Experience Platform-context alleen ingesteld nadat de Storageront Event Collector en de Storefront Event SDK zijn geladen.

## 2.0.0

_12 oktober 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Nieuw](../assets/new.svg) - Toegevoegde mogelijkheid om uw eigen AEP Web SDK op te geven wanneer [verbinden](connect-data.md) Adobe Commerce-exemplaar naar het Experience Platform
* ![Repareren](../assets/fix.svg) - Vereisten voor het bijwerken van het bereik van de gegevensstroom, zodat de gegevensstroom-id&#39;s binnen het bereik van de website moeten worden geplaatst in plaats van dat ze moeten worden opgeslagen

## 1.0.0

_9 augustus 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

* ![Nieuw](../assets/new.svg) - Algemene beschikbaarheidsrelease
