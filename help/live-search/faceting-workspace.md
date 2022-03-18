---
title: Werkruimte naast elkaar
description: Leer hoe u de werkruimte Live zoeken gebruikt.
exl-id: b47b5c19-59bb-41e4-9599-3b90cbc44b70
source-git-commit: 19f0c987ab6b43b6fac1cad266b5fd47a7168e73
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Werkruimte naast elkaar

De [!DNL Live Search] De werkruimte bevat een lijst met alle facetten die momenteel beschikbaar zijn en biedt toegang tot de gereedschappen die u nodig hebt voor het instellen en beheren van facetten. Vastgezette facetten worden als eerste weergegeven in de lijst met bestaande facetten, gevolgd door dynamische facetten. De lijst kan worden gefilterd om alle facetten, of slechts die te tonen die worden vastgezet of dynamisch.

![Werkruimte naast elkaar](assets/faceting-workspace.png)

## Bereik instellen

Als uw Adobe Commerce-installatie meerdere winkelweergaven bevat, stelt u **Toepassingsgebied** aan de [winkelweergave](https://docs.magento.com/user-guide/configuration/scope.html) waar uw facetinstellingen van toepassing zijn.

## De lijst filteren

1. Klik op de knop **Filteren op** controle.
1. Kies een van de volgende opties:

   * Alle filters
   * Vastgezet
   * Dynamisch

   ![Werkruimte naast elkaar](assets/facets-filter-by.png)

## Een facet toevoegen

1. Klikken **Elementen toevoegen**.
1. Zie [Facetten toevoegen](facets-add.md) voor gedetailleerde instructies.

## Kolombeschrijvingen

| Kolom | Beschrijving |
|--- |--- |
| (eerste kolom) | Lijsten vastgezet en dynamische facetten door [label](facets-type.md) die zichtbaar is voor de verkoopster. |
| Tekst selecteren | De [selectiemethode](facets-type.md) die wordt toegewezen aan het overeenkomstige productkenmerk. De `single select` type wordt gebruikt voor alles [!DNL Commerce] opslagronten. Voor headless implementaties, `multi-select` type kan worden toegewezen met een logische operator (`or` of `and`) om de reeks geretourneerde producten te bepalen. |
| Tekst sorteren | De [sorteervolgorde](facets-type.md) van facetwaarden. Facetten worden alfabetisch gesorteerd voor alle [!DNL Commerce] opslagronten. Voor [koploos] implementaties, kunnen de facetten of alfabetisch of door telling worden gesorteerd. Opties: Alfabetisch, Aantal (alleen zonder kop) |
| Max. waarde | Het aantal facetwaarden dat in de opslagruimte als filters beschikbaar is, met een maximum van 10. |

## Besturingselementen

| Control | Beschrijving |
|--- |--- |
| Elementen toevoegen | Hiermee opent u de [facetredacteur](facets-add.md). |
| Filteren op | Hiermee bepaalt u de [type facetten](facets-type.md) die in de lijst worden weergegeven. Opties: Alles, vastgezet, dynamisch |
