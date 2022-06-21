---
title: Werkruimte
description: Leer hoe u de prestaties van productaanbevelingen kunt configureren, beheren en controleren.
exl-id: 85a06cc3-91b9-484a-96a9-fc85718e6d70
source-git-commit: 9f1f05475b2d8401ec33272e3f12e3cc7285478d
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---

# Werkruimte

De [!DNL Product Recommendations] de werkruimte toont een lijst van eerder gevormde aanbevelingen met metriek die u helpen het succes van elke aanbeveling volgen. De lijst kan worden gevormd om metriek voor de laatste dag, de week, of de maand te berekenen. U kunt de metriek gebruiken om actionable inzichten tot stand te brengen die op hoe vaak een aanbeveling wordt bekeken of geklikt, of te analyseren hoe goed uw aanbevelingen presteren.

![Recommendations-werkruimte](assets/workspace.png)
_Recommendations Workspace_

## Bereik instellen

In eerste instantie [bereik](https://docs.magento.com/user-guide/stores/websites-stores-views.html) van alle aanbevolen instellingen is ingesteld op `Default Store View`. Als uw installatie van de Handel veelvoudige opslagmeningen omvat, plaats **Toepassingsgebied** aan de [winkelweergave](https://docs.magento.com/user-guide/configuration/scope.html) waar uw aanbevelingen van toepassing zijn.

## Datumbereik van metrische gegevens instellen

1. Klik op de knop **Kalender** ![Kalenderkiezer](assets/icon-calendar.png) controle.

1. Kies een van de volgende opties:

   - Afgelopen 24 uur
   - Laatste 7 dagen
   - Laatste 30 dagen

   De berekende waarden in de kolommen van metriek veranderen om op de huidige datumwaaier te wijzen.

## Kolommen tonen/verbergen

1. Klik in de linkerbovenhoek op **Tonen/verbergen** ![Kolomkiezer](assets/icon-show-hide-columns.png) kolommen.

   De zichtbare kolommen hebben een blauw vinkje.

1. Voer in het menu een van de volgende handelingen uit:

   - Als u een verborgen kolom wilt weergeven, klikt u op een kolomnaam zonder vinkje.
   - Als u een zichtbare kolom wilt verbergen, klikt u op een kolomnaam met een vinkje.

   De tabel wordt vernieuwd en bevat alleen de geselecteerde kolommen.

   ![Recommendations-werkruimte](assets/workspace-select-columns.png)
   _Kolommen tonen/verbergen_

## Instellingen

De instellingen bepalen de SaaS-gegevensruimte die de aanbevelingen en gedraggegevens bevat.

- Om te veranderen waar aanbeveling-gedrag gegevens voortkomt, kies een verschillende gegevensruimte SaaS.

- Als u een nieuwe SaaS-gegevensruimte wilt configureren, klikt u op **Configuratie bewerken**. Zie voor meer informatie [Instellingen](settings.md).

![Recommendations-instellingen](assets/settings.png)
_Recommendations-instellingen_

## Details weergeven

1. Klik in de tabel op de aanbeveling die u wilt onderzoeken.

   ![Recommendations-werkruimte](assets/recommendation-detail.png)
   _Detail conversiesnelheid startpagina_

1. Als u de status van de aanbeveling wilt wijzigen, klikt u op **Activeren** of **Deactiveren**.

## Aanbeveling bewerken

Klik op de pagina met informatie over de aanbeveling op **Bewerken**. Ga voor meer informatie naar [Recommendations bewerken](edit.md).

## Aanbeveling maken

Klik op de pagina met informatie over de aanbeveling op **Maken**. Ga voor meer informatie naar [Recommendations maken](create.md).

## Besturingselementen werkruimte

| Control | Beschrijving |
|---|---|
| ![Kalenderkiezer](assets/icon-calendar.png) | Hiermee bepaalt u het tijdsbereik dat wordt gebruikt voor metrische berekeningen. Opties: 24 uur / 7 dagen / 30 dagen |
| ![Kolomkiezer](assets/icon-show-hide-columns.png) | Hiermee bepaalt u de kolommen die worden weergegeven in het dialoogvenster [!DNL Product Recommendations] tabel. |
| Instellingen | Bepaalt de SaaS gegevensruimte waar aanbeveling-gedrag gegevens wordt gehaald, en laat ook visuele gelijkenis aanbevelingen type toe. |
| Aanbeveling maken | Hiermee opent u de [Nieuwe aanbeveling maken](create.md) pagina. |

## Kolombeschrijvingen

| Kolom | Beschrijving |
|---|---|
| Naam | De naam van de aanbeveling. |
| Pagina | De pagina waar de aanbeveling wordt weergegeven. |
| Type | Het type aanbeveling. |
| Status | De status van de aanbeveling. Opties: Inactief/actief/concept |
| Gemaakt | De datum waarop de aanbeveling is opgesteld. |
| Laatst bewerkt | De datum waarop de aanbeveling voor het laatst is bewerkt. |
| Impressies | Het aantal keren dat een aanbevolen eenheid op een pagina wordt geladen en weergegeven. Een aanbeveling-eenheid die onder de voud van de viewport van de browser ligt, wordt op de pagina weergegeven, maar niet door de gebruiker weergegeven. In dit geval wordt de weergegeven eenheid geteld als een indruk, maar een weergave wordt alleen geteld als de gebruiker de eenheid in beeld schuift. |
| vImpressions | (Zichtbare indrukkingen) Het aantal aanbevelingen dat ten minste één weergave registreert. |
| Weergaven | Het aantal aanbevelingen dat wordt weergegeven in de viewport van de browser van de klant. Deze gebeurtenis kan meerdere keren op een pagina worden uitgevoerd. |
| Klikken | De som van het aantal keren dat een winkelbediende op een item in de aanbevolen eenheid klikt en het aantal keren dat de winkelbediende op de knop klikt **Toevoegen aan winkelwagentje** knop in de aanbevolen eenheid |
| Ontvangsten | De inkomsten die voortvloeien uit de aanbeveling voor de huidige tijdspanne. |
| LT-inkomsten | (Levensopbrengsten) De levenslange inkomsten die worden voortgebracht door een aanbeveling. |
| Zichtbaarheid | Het percentage aanbevolen eenheden dat zich registreert voor de weergave. |
| Ctr | (Doorkliksnelheid) Het percentage eenheidsindrukkingen voor de aanbeveling die een klik registreert. |
| vCtr | (Zichtbare Doorkliksnelheid) Het percentage zichtbare indrukken voor de aanbevolen eenheid die een klik registreert. |
