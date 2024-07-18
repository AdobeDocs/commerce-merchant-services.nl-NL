---
title: '[!DNL SaaS Data Export Extension] Opmerkingen bij de release'
description: De recentste versieinformatie voor  [!DNL Data Export Extension]  voor Adobe Commerce.
feature: Services, Release Notes
recommendations: noCatalog
exl-id: 0c7aeeda-e8a6-4740-b466-0661a6d2df07
source-git-commit: 7757cc382e306a6c074a815d5148a4dcd8fff284
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# [!DNL SaaS Data Export] Opmerkingen bij de release Extension

In deze releaseopmerkingen worden de nieuwste versies van de extensie [!DNL SaaS data export] beschreven. Er wordt ondersteuning geboden voor de belangrijkste uitgebrachte versie. Opmerkingen bij de release voor oudere versies worden ter referentie verschaft.

Updates zijn:

![ Nieuwe ](../assets/new.svg) Nieuwe eigenschappen
![ bevestig ](../assets/fix.svg) Bevestigingen en verbeteringen
![ Bug ](../assets/bug.svg) Bekende kwesties


>[!NOTE]
>
>De gegevensexportuitbreiding SaaS is een inzameling van modules die automatisch met Levend Onderzoek, Product Recommendations, en de Dienst van de Catalogus geïnstalleerd is. U kunt de versie controleren die op uw systeem is geïnstalleerd met behulp van composer. In sommige gevallen kunt u de extensie voor het exporteren van gegevens op uw systeem upgraden om oplossingen of nieuwe mogelijkheden op te halen zonder de Commerce Service-versie bij te werken.

## Huidige hoofdversie

## 103.3.8 Release

](../assets/fix.svg) Uitgeschakelde configuratieopties van 0} herstellen {worden niet meer uitgevoerd als actieve opties.![<!--MDEE-812-->
![ herstellen ](../assets/fix.svg) de Opties en de waarden worden nu bijgewerkt op een configureerbaar product wanneer de veranderingen in een kindproduct worden aangebracht. <!--MDEE-835-->
![ Nieuw ](../assets/new.svg) voegde de capaciteit toe om de extra gegevens van het systeemattribuut in de voer van productattributen te omvatten.

## 103.3.7 Release

![ bevestig ](../assets/fix.svg) Verwijderde onnodige gebiedsdelen uit de module InventoryDataExporter.
](../assets/fix.svg) Gewijzigde vereiste versies voor inventarismodules inbegrepen in de module CatalogInventoryDataExporter van de Reparatie ![ {om Adobe Commerce versie 2.4.4 te steunen.

## 103.3.6 Release

![ bevestig ](../assets/fix.svg) Vaste implocks die tijdens voer opnieuw indexerend op multi-draadwijze voorkwamen. De vragen zijn nu gescheiden in de verrichtingen van het Tussenvoegsel en van de Update.
![ bevestig ](../assets/fix.svg) optimaliseerde de vraag van Prijzen voor grote catalogi met vele websites.
![ Nieuwe ](../assets/new.svg) toegevoegde retry logica om ontbroken transacties opnieuw in werking te stellen wanneer de imlocklocks voorkomt.

## 103.3.5 Release

![ bevestig ](../assets/fix.svg) Vastgestelde gebiedsdeel voor recentste compatibele versie van de gegevensuitvoer voor de gemeenschappelijke module SaaS.

![ verbeter ](../assets/fix.svg) Vervangen `ScopeConfig` instantie met `ServiceConfigInterface` om verschillende de dienstconfiguraties te steunen.

## 103.3.4 Release

](../assets/fix.svg) verbeter Commerce SaaS gegevens het uitvoerregistreren door meer details over het opnieuw indexeren proces toe te voegen.![

## 103.3.3 Release

![ Nieuwe ](../assets/new.svg) de gegevensuitvoer SaaS nu caches Entiteit-Attributen-Waarde (EAV) attributen voor de vraag van attributenmeta-gegevens.

![ bevestig ](../assets/fix.svg) een kwestie waar het `InventoryStockStatus` voer niet werd bewaard bij opnieuw proberen als het product werd geschrapt.

## 103.3.2 Release

![ bevestig ](../assets/fix.svg) een kwestie waar het `modifiedAt` gebied van verwijderde entiteitsvoer mist.

## 103.3.1 Release

![ bevestig ](../assets/fix.svg) een kwestie die een `Invalid Template File` bericht veroorzaakte om tijdens productvoer te verschijnen die opnieuw indexeert wanneer de Bouwer van de Pagina wordt geïnstalleerd.

## 103.3.0 Release

![ Nieuwe ](../assets/new.svg) Gemigreerde directe de voederlijsten van de uitvoer aan de verenigde structuur:
`id` , `source_entity_id` , `feed_id` , `modified_at` , `is_deleted` , `status` , `feed_data` , `feed_hash` , `errors`

![ Nieuwe ](../assets/new.svg) Gemigreerde catalogus en inventarisvoer aan de directe uitvoeroplossing.

![ Nieuw ](../assets/new.svg) anders genoemd directe voer voer voer schaafbanen aan `*_feed_resend_failed_items`.

![ Nieuw ](../assets/new.svg) hernoemde directe de uitvoervoer en veranderingslogboeklijsten.

](../assets/fix.svg) Repareer `modified_at` gebied van de Reeks ![ {in voedergegevens slechts voor voer dat het vereist.

![ verbeter ](../assets/fix.svg) wijzig de `productAttributes` vraag om slechts productattributen terug te winnen.

## 103.2.6 Release

![ bevestig ](../assets/fix.svg) een kwestie die voer verhinderde opnieuw te worden gefixeerd wanneer de lijsten een prefix hebben.

## 103.2.5 Release

![ bevestig ](../assets/fix.svg) optimaliseerde de vraag van de Prijs.

## 103.2.4 Release

![ bevestig ](../assets/fix.svg) onjuiste status van de Voorraad die voor een product werd getoond wanneer Commerce Inventory management wordt toegelaten.

## 103.2.3 Release

![ bevestig ](../assets/fix.svg) Vaste prijs van websiteniveau.
](../assets/fix.svg) Toegevoegde mutex van 0} herstellen {voor alle voer dat wordt verwerkt.![


## 103.2.2 Release

![ verbeter ](../assets/fix.svg) Verbeterde feeds batchstrategie voor grote catalogi. De batchtabel is nu gevuld met een beperkt aantal id&#39;s om het geheugengebruik te verminderen.

](../assets/fix.svg) Elimineerde harde gebiedsdeel van CommerceInventoryDataExporter aan modules MSI.![

](../assets/fix.svg) Verbeterde `commerce-data-exporter` logboeken van 0} herstellen {om meer informatie te verzamelen en door verschillende het uitvoeren stadia te organiseren.![

## 103.2.1 Release

- Uitgebrachte bijgewerkte versie.

## 103.2.0 Release

- Multithread-gegevenssync voor producten en prijzen toegevoegd.
