---
title: '[!DNL Product Recommendations] Workspace'
description: Leer hoe u de prestaties van productaanbevelingen kunt configureren, beheren en controleren.
exl-id: 85a06cc3-91b9-484a-96a9-fc85718e6d70
source-git-commit: 25d5321b6f29bab5d8cf329170f3644f35100438
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# [!DNL Product Recommendations] Workspace

De werkruimte van [!DNL Product Recommendations] toont een lijst van eerder gevormde aanbevelingen met metriek die u helpen het succes van elke aanbeveling volgen. De lijst kan worden gevormd om metriek voor de laatste dag, de week, of de maand te berekenen. U kunt de metriek gebruiken om actionable inzichten tot stand te brengen die op hoe vaak een aanbeveling wordt bekeken of geklikt, of te analyseren hoe goed uw aanbevelingen presteren.

![ de werkruimte van Recommendations ](assets/workspace.png)
_Recommendations Workspace_

## Bereik instellen

Aanvankelijk wordt het [ werkingsgebied ](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html) van alle aanbevelingen montages geplaatst aan `Default Store View`. Als uw installatie van Commerce veelvoudige opslagmeningen omvat, plaats **Reikwijdte** aan de [ opslagmening ](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) waar uw aanbevelingen van toepassing zijn.

## Datumbereik van metrische gegevens instellen

1. Klik de **![ controle van de selecteur van de Kalender ](assets/icon-calendar.png) van de 0} Kalender {.**

1. Kies een van de volgende opties:

   - Afgelopen 24 uur
   - Laatste 7 dagen
   - Laatste 30 dagen

   De berekende waarden in de kolommen van metriek veranderen om op de huidige datumwaaier te wijzen.

## Kolommen tonen/verbergen

1. In de upper-left hoek, klik **tonen/verbergen** ![ selecteur van de Kolom ](assets/icon-show-hide-columns.png) kolommen.

   De zichtbare kolommen hebben een blauw vinkje.

1. Voer in het menu een van de volgende handelingen uit:

   - Als u een verborgen kolom wilt weergeven, klikt u op een kolomnaam zonder vinkje.
   - Als u een zichtbare kolom wilt verbergen, klikt u op een kolomnaam met een vinkje.

   De tabel wordt vernieuwd en bevat alleen de geselecteerde kolommen.

   ![ de werkruimte van Recommendations ](assets/workspace-select-columns.png)
   _tonen/verbergen kolommen_

## Instellingen

De instellingen bepalen de SaaS-gegevensruimte die de aanbevelingen en gedraggegevens bevat.

- Om te veranderen waar aanbeveling-gedrag gegevens voortkomt, kies een verschillende gegevensruimte SaaS.

- Om een nieuwe SaaS gegevensruimte te vormen, klik **uitgeven Configuratie**. Meer leren, zie [ Montages ](settings.md).

![ de montages van Recommendations ](assets/settings.png)
_de Montages van Recommendations_

## Details weergeven

1. Klik in de tabel op de aanbeveling die u wilt onderzoeken.

   ![ de werkruimte van Recommendations ](assets/recommendation-detail.png)
   _het Detail van het Tarief van de Omzetting van de Homepage_

1. Om het statuut van de aanbeveling te veranderen, activeer **** of **** deactivate.

## Aanbeveling bewerken

Van de pagina van de aanbevelingsdetails, geeft de klik **** uit. Meer leren, ga [ Recommendations ](edit.md) uitgeven.

## Aanbeveling maken

Van de pagina van de aanbevelingsdetails, klik **creëren**. Meer leren, ga naar [ tot Recommendations ](create.md) leiden.

## Workspace-besturingselementen

| Besturing | Beschrijving |
|---|---|
| ![ de selecteur van de Kalender ](assets/icon-calendar.png) | Hiermee bepaalt u het tijdsbereik dat wordt gebruikt voor metrische berekeningen. Opties: 24 uur / 7 dagen / 30 dagen |
| ![ de selecteur van de Kolom ](assets/icon-show-hide-columns.png) | Bepaalt de kolommen die in de [!DNL Product Recommendations] lijst verschijnen. |
| Instellingen | Bepaalt de SaaS gegevensruimte waar aanbeveling-gedrag gegevens wordt gehaald, en laat ook visuele gelijkenis aanbevelingen type toe. |
| Aanbeveling maken | Opent [ creëren Nieuwe pagina van de Aanbeveling ](create.md). |

## Kolombeschrijvingen

| Kolom | Beschrijving |
|---|---|
| Naam | De naam van de aanbeveling. |
| Pagina | De pagina waar de aanbeveling wordt weergegeven. |
| Type | Het type aanbeveling. |
| Status | De adviesstatus. Opties: Inactief/actief/concept |
| Gemaakt | De datum waarop de aanbeveling is opgesteld. |
| Laatst bewerkt | De datum waarop de aanbeveling voor het laatst is bewerkt. |
| Impressies | Het aantal keren dat een aanbevolen eenheid op een pagina wordt geladen en weergegeven. Een aanbeveling-eenheid die onder de voud van de viewport van de browser ligt, wordt op de pagina weergegeven, maar niet door de gebruiker weergegeven. In dit geval wordt de weergegeven eenheid geteld als een indruk, maar een weergave wordt alleen geteld als de gebruiker de eenheid in beeld schuift. |
| vImpressions | (Zichtbare indrukkingen) Het aantal aanbevelingen-eenheden dat ten minste één weergave registreert. |
| Weergaven | Het aantal aanbevelingen dat wordt weergegeven in de viewport van de browser van de klant. Deze gebeurtenis kan meerdere keren op een pagina worden uitgevoerd. |
| Klikken | De som van het aantal tijden een verkoopster klikt een punt in de aanbeveling eenheid en het aantal tijden de verkoopster **toevoegt aan wortel** knoop in de aanbeveling eenheid |
| Ontvangsten | De inkomsten die voortvloeien uit de aanbeveling voor de huidige periode. |
| LT-inkomsten | (Levensopbrengsten) De levenslange inkomsten die worden voortgebracht door een aanbeveling. |
| Zichtbaarheid | Het percentage aanbevolen eenheden dat zich registreert voor de weergave. |
| Ctr | (Doorkliksnelheid) Het percentage eenheidsindrukkingen voor de aanbeveling die een klik registreert. |
| vCtr | (Zichtbare Doorkliksnelheid) Het percentage zichtbare indrukken voor de aanbevolen eenheid die een klik registreert. |
