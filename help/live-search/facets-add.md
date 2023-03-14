---
title: "Facetten toevoegen"
description: "Leer hoe u filterbare productkenmerken kunt toevoegen als [!DNL Live Search] facetten."
exl-id: 0df6c21b-55b3-41ce-94f4-f70b70ffb84e
source-git-commit: 10edbb6127405d45c06d4c8ffc89d92a6ca061c3
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 0%

---

# Facetten toevoegen

Elk filtreerbaar productkenmerk kan als facet worden gebruikt. De *Elementen toevoegen* in dit deelvenster worden de huidige facetten weergegeven en kunt u gemakkelijk aanvullende productkenmerken als facetten toewijzen. Tijdens dit proces in drie stappen wordt een kenmerk gekozen om als facet te worden gebruikt, worden eigenschappen indien nodig bewerkt en worden de wijzigingen in het winkelcentrum gepubliceerd.

![Werkruimte naast elkaar](assets/facets-add.png)

## Stap 1: Een facet toevoegen

1. Ga in Beheer naar **Marketing** > SEO &amp; Search > **[!DNL Live Search]**.
1. Op de *Faceting* tabblad, klikt u op **Elementen toevoegen**.
1. In de *Elementen toevoegen* lijst, heeft elk beschikbaar attribuut een afzonderlijke ![Knop Toevoegen](assets/btn-add.png). Voer een van de volgende handelingen uit:

   * In de *Kenmerken naast elkaar* lijst, kies het productkenmerk dat u als facet wilt gebruiken en klik **Toevoegen**.
   * Als u een specifiek productkenmerk wilt zoeken, voert u de eerste paar tekens van de kenmerknaam in het dialoogvenster *Zoeken* doos. Klik vervolgens op **Toevoegen**.

      Als u prijsafhankelijke intervallen en groepen wilt configureren, raadpleegt u [Instellingen](settings.md). Ga voor meer informatie naar [Typen gezichten](facets-type.md).
Het facet wordt onder aan het dialoogvenster *Dynamische factoren* en de *Wijzigingen publiceren* wordt beschikbaar.

1. Als het facet dat u wilt toevoegen, niet is gevonden, gaat u naar **Winkels** > Kenmerken > **Product** en verifieer dat het attribuut heeft [vereiste eigenschappen](facets.md) te gebruiken als facet. Werk indien nodig de volgende archiefront-eigenschappen van het kenmerk bij:

   * Gebruiken in Zoeken - `Yes`
   * Gebruiken in gelaagde navigatie met zoekresultaten - `Yes`
   * Gebruiken in gelaagde navigatie - `Filterable (with results)`

1. Vernieuw de cache wanneer daarom wordt gevraagd.

   Het facet wordt beschikbaar in de winkel wanneer de catalogus opnieuw wordt gesynchroniseerd met [!DNL Live Search]. Als het facet na twee uur niet beschikbaar is, zie [Catalogusgegevens synchroniseren](install.md#synchronize-catalog-data).

## Stap 2: Eigenschappen van facetten bewerken (optioneel)

1. Klik op **Meer** (![Meer kiezer](assets/btn-more.png)) in de rechterkolom.
1. Klik in het menu op **Bewerken**. Pas vervolgens de volgende eigenschappen naar wens aan.

   * Label - ([Koploos](facets-type.md) (alleen) Voer het facetlabel in dat u wilt gebruiken.
   * Type sorteren - Facets worden alfabetisch gesorteerd voor alle [!DNL Commerce] opslagronten. Voor implementaties zonder kop kunnen facetten alfabetisch of op aantal worden gesorteerd. Opties: Alfabetisch, Aantal (alleen zonder kop)
   * Max. waarde - Voer het maximale aantal facetwaarden in dat in de winkelruimte wordt weergegeven. Geldige vermeldingen: 0 - 30; Standaard: 8

1. Klik op **Opslaan**.

   ![Werkruimte naast elkaar](assets/facet-edit.png)

1. Het facet vastzetten op de bovenkant van het *Filters* lijst, klikt u op het grijze drukknop (![Vastzetten, kiezer](assets/btn-pin-gray.png)).
1. Als u de volgorde van het vastgezette facet wilt wijzigen, klikt u op de knop **Verplaatsen** (![Selector verplaatsen](assets/btn-move.png)) en sleep de rij naar een nieuwe positie in het deelvenster *Vastgezette gezichten* sectie.

## Stap 3: Wijzigingen publiceren

1. Wanneer het facet is voltooid, klikt u op **Wijzigingen publiceren**.
1. Wacht tot het facet in de winkel wordt weergegeven.
Als het facet na twee uur niet beschikbaar is, zie [Exporteren verifiëren](install.md#synchronize-catalog-data) in de installatie-instructies.

## Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Label | ([Koploos](facets-type.md) alleen) De [facetlabel](facets-type.md) die zichtbaar is in de winkel, kan worden bewerkt voor consistentie met uw merk. |
| Sorteertype | De methode die wordt gebruikt om [sorteren](facets-type.md) facetten. Alles [!DNL Commerce] storefronts sorteren alleen alfabetische facetten. Implementaties zonder kop kunnen ook worden gesorteerd op `Count`. Opties:<br />Alfabetisch - Hiermee worden facetten alfabetisch gesorteerd.<br />Tellen - (alleen Koploos) sorteert facetten op basis van het aantal gevonden overeenkomsten. |
| Max. waarde | Het maximumaantal waarden dat in de opslagruimte voor elk facet kan worden getoond. Facetten die een reeks waarden vertegenwoordigen, worden gelijkmatig verdeeld. Geldige vermeldingen: 0 - 30; Standaard: 8 |

### Besturingselementen

| Control | Beschrijving |
|--- |--- |
| ![Vastzetten, kiezer](assets/btn-pin-blue.png) | Hiermee wordt een facet aan de bovenkant van de knop vastgezet of losgekoppeld *Filters* lijst. |
| ![Meer kiezer](assets/btn-more.png) | Hiermee geeft u een menu weer met meer acties die op het geselecteerde facet kunnen worden toegepast. Opties: Bewerken, Verwijderen |
| ![Selector verplaatsen](assets/btn-move.png) | Gebruik de *Verplaatsen* pictogram om een vastgezet facet naar een andere plaats in het deelvenster *Vastgezette facetten* sectie. |
