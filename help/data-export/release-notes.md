---
title: "[!DNL SaaS Data Export Extension] Opmerkingen bij de release"
description: De meest recente releasegegevens voor [!DNL Data Export Extension] voor Adobe Commerce.
feature: Services, Release Notes
recommendations: noCatalog
source-git-commit: 8230756c203cb2b4bdb4949f116c398fcaab84ff
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# [!DNL SaaS Data Export] Opmerkingen bij de release Extension

In deze releaseopmerkingen worden de meest recente versies van de [!DNL SaaS data export] extensie. Er wordt ondersteuning geboden voor de belangrijkste uitgebrachte versie. Opmerkingen bij de release voor oudere versies worden ter referentie verschaft.

Updates zijn:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen


>[!NOTE]
>
>De gegevensexportuitbreiding SaaS is een inzameling van modules die automatisch met Levend Onderzoek, Product Recommendations, en de Dienst van de Catalogus geïnstalleerd is. U kunt de versie controleren die op uw systeem is geïnstalleerd met behulp van composer. In sommige gevallen kunt u de extensie voor het exporteren van gegevens op uw systeem upgraden om oplossingen of nieuwe mogelijkheden op te halen zonder de Commerce Service-versie bij te werken.

## Huidige hoofdversie

## 103.3.5 Release

![Repareren](../assets/fix.svg) Vastgestelde gebiedsdeel voor recentste compatibele versie van de gegevensuitvoer voor de gemeenschappelijke module SaaS.

![Repareren](../assets/fix.svg) Vervangen `ScopeConfig` instantie met `ServiceConfigInterface` om verschillende de dienstconfiguraties te steunen.

## 103.3.4 Release

![Repareren](../assets/fix.svg) Verbeter Commerce SaaS gegevens het uitvoerregistreren door meer details over het opnieuw indexeren proces toe te voegen.

## 103.3.3 Release

![Nieuw](../assets/new.svg) Bij het exporteren van SaaS-gegevens worden nu EAV-kenmerken (Identity-Attribute-Value) voor de metagegevensquery voor kenmerken in het cachegeheugen opgeslagen.

![Repareren](../assets/fix.svg) Het probleem waarbij de `InventoryStockStatus` feed is niet opgeslagen bij opnieuw proberen als het product is verwijderd.

## 103.3.2 Release

![Repareren](../assets/fix.svg) Het probleem waarbij de `modifiedAt` veld ontbreekt in verwijderde entiteitsfeeds.

## 103.3.1 Release

![Repareren](../assets/fix.svg) Probleem verholpen dat een `Invalid Template File` bericht dat tijdens productfeed wordt weergegeven wanneer de Page Builder wordt geïnstalleerd.

## 103.3.0 Release

![Nieuw](../assets/new.svg) Gegigreerde directe de voederlijsten van de uitvoer aan de verenigde structuur:
`id`, `source_entity_id`, `feed_id`, `modified_at`, `is_deleted`, `status`, `feed_data`, `feed_hash`, `errors`

![Nieuw](../assets/new.svg) De gemigreerde catalogus en inventarisvoer naar de directe exportoplossing.

![Nieuw](../assets/new.svg) Naam van directe exportfeed is gewijzigd in snijtaken naar `*_feed_resend_failed_items`.

![Nieuw](../assets/new.svg) Naam van directe exportfeed is gewijzigd en logtabellen worden gewijzigd.

![Repareren](../assets/fix.svg) Set `modified_at` veld in voedergegevens alleen voor diervoeders die dit vereisen.

![Repareren](../assets/fix.svg) Wijzig de `productAttributes` query om alleen productkenmerken op te halen.

## 103.2.6 Release

![Repareren](../assets/fix.svg) Probleem verholpen waarbij feeds niet opnieuw konden worden genummerd wanneer tabellen een voorvoegsel hadden.

## 103.2.5 Release

![Repareren](../assets/fix.svg) De query voor Prijs is geoptimaliseerd.

## 103.2.4 Release

![Repareren](../assets/fix.svg) Correctie van onjuiste voorraadstatus die werd weergegeven voor een product wanneer Commerce Inventory management werd ingeschakeld.

## 103.2.3 Release

![Repareren](../assets/fix.svg) Speciale prijzen op websiteniveau vastgesteld.
![Repareren](../assets/fix.svg) Mutex toegevoegd voor alle feeds die worden verwerkt.


## 103.2.2 Release

![Repareren](../assets/fix.svg) Verbeterde batchstrategie voor feeds voor grote catalogi. De batchtabel is nu gevuld met een beperkt aantal id&#39;s om het geheugengebruik te verminderen.

![Repareren](../assets/fix.svg) Elimineerde harde afhankelijkheid van CommerceInventoryDataExporter aan modules MSI.

![Repareren](../assets/fix.svg) Verbeterd `commerce-data-exporter` logboeken om meer informatie te verzamelen en te organiseren door verschillende exportstadia.

## 103.2.1 Release

- Uitgebrachte bijgewerkte versie.

## 103.2.0 Release

- Multithread-gegevenssync voor producten en prijzen toegevoegd.

