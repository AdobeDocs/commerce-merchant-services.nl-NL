---
title: "Regels toevoegen"
description: "Leer hoe u creeert [!DNL Live Search] regels."
exl-id: c6b92ef5-3b08-47f9-8412-955a9c95a9ee
source-git-commit: 0b0e9a630162c4c98c6a3af969002def03155267
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 0%

---

# Regels toevoegen

Om een regel te bouwen, moet de eerste stap de regelredacteur gebruiken om de voorwaarden in de vraagtekst van de klant te bepalen die de bijbehorende gebeurtenissen teweegbrengen. Dan, voltooi de regeldetails, test de resultaten, en publiceer de regel.

## Een regel toevoegen

1. Ga in Beheer naar **Marketing** > SEO &amp; Search > **[!DNL Live Search]**.
1. Stel de **Toepassingsgebied** om de [winkelweergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) wanneer de regel van toepassing is.
1. Klik op de knop **Regels** tab.
1. Klikken **Regel toevoegen** om de regeleditor te starten.

## Voorwaarden

Voorwaarden zijn de vereisten om een gebeurtenis te activeren. Een regel kan tot tien voorwaarden en 25 gebeurtenissen hebben.

![Regel - Bouw uw regel](assets/rules-add-workspace.png)

>[!NOTE]
>
>Momenteel, is het niet mogelijk om regels aan een specifieke klantengroep te richten.

### Eén voorwaarde

1. Onder *Uw regel samenstellen*, selecteert u de **Voorwaarde** en volgt u de instructies om de instructie te voltooien.

   * Zoekquery bevat - Voer de tekenreeks in die in de query van de winkels moet staan. De instelling Afstemmen bepaalt de mate waarin de query van de winkels overeenkomt met de catalogus. Opties:<br /> Willekeurig - Elk deel van de querytekst van de winkels kan overeenkomen met de voorwaarde.<br />Alles - Alle query&#39;s van de klant moeten overeenkomen met de voorwaarde.
   * Zoekquery is - Voer een tekenreeks in die exact overeenkomt met de query van de verkoper. Bijvoorbeeld: &quot;yoga broek&quot;. Regels met `Search query is` en Overeenkomst `All` kan slechts één voorwaarde hebben.
   * Zoekopdracht begint met - Voer een teken of tekenreeks in die aan het begin van de zoekopdracht van de gebruiker moet staan.
   * Zoekopdracht eindigt met - Voer een teken of tekenreeks in die aan het einde van de zoekopdracht van de gebruiker moet staan.

   De resultaten worden direct weergegeven in het dialoogvenster *Uw regel testen* en worden genummerd op prioriteit. U kunt de *Resultaten per rij* schuifregelaar rechtsboven om het aantal producten in elke rij te wijzigen.

   ![Regel - eenvoudig](assets/rule-simple-test.png)

1. Om andere vragen te testen, verander de vraagtekst in *Uw regel testen* zoekvak en drukken op **Return**.
Aanvankelijk, geeft de testruit de vraag van het de onderzoeksvakje van de Voorwaarden terug. Maar nu geeft het de vraag van de doos van de testvraag terug. De testruit geeft slechts één vraag tegelijkertijd terug.
1. Als het resultaat u bevalt, werkt u de tekst in het dialoogvenster *Voorwaarden* zoekvak. Klik vervolgens ergens op de pagina om de resultaten in het testvenster bij te werken.
1. Ga naar Stap 3 om een eenvoudige regel met één voorwaarde te bouwen: [Gebeurtenissen toevoegen](#events).

### Meerdere voorwaarden

1. Als u een regel met meerdere voorwaarden wilt maken, klikt u op **Voorwaarde toevoegen**.
Een regel kan tot tien voorwaarden hebben. De logische operator die zich bij twee voorwaarden aansluit, is gebaseerd op de huidige *Overeenkomst* instellen. Standaard, *Overeenkomst* is `All` en de logische operator `AND`.

   ![Regels - Zoekquery bevat](assets/rules-search-query-contains-and.png)

1. Selecteer de tweede voorwaarde en voer de vereiste querytekst in.

1. Als u de logica van de regel wilt wijzigen, wijzigt u de **Overeenkomst** het plaatsen om te bepalen hoe dicht de het onderzoekscriteria van de klant de vraagvoorwaarde moeten aanpassen. Set **Overeenkomst** op een van de volgende wijzen:

   * Willekeurige - (Standaard) Alle logische operatoren in de regel zijn ingesteld op `OR` en de resultaten worden weergegeven in het testvenster.
   * Alles - Alle logische operatoren in de regel zijn ingesteld op `AND` en de resultaten worden weergegeven in het testvenster.

   De *Overeenkomst* value bepaalt de logische operator die wordt gebruikt om meerdere voorwaarden samen te voegen. Het wijzigen van *Overeenkomst* bij het instellen worden alle logische operatoren in de regel gewijzigd. Het is niet mogelijk om `AND` en `OR` in dezelfde regel.

   In dit voorbeeld zijn er twee aparte query&#39;s die zoeken naar &#39;yoga&#39; of &#39;broek&#39; in plaats van naar &#39;yoga-broek&#39; te zoeken. Deze regel is minder specifiek en wordt vaker geactiveerd in de winkel dan in de andere.

   ![Regels - Overeenkomst](assets/rules-match.png)

1. Als u nog een voorwaarde wilt toevoegen, klikt u op **Voorwaarde toevoegen** en herhaal het proces.

## Type rangschikking

Met de classificatie worden gebruikersgedrag en sitestatistieken gecombineerd om de productclassificatie te bepalen.
Winkeleigenaars kunnen de volgende typen classificatiestrategieën instellen:

![Regels - Overeenkomst](assets/rules-ranking-type.png)

* Meest aangeschaft: Dit rangschikt de producten op basis van de totale aankopen per SKU in de afgelopen 7 dagen.
* Meestal toegevoegd aan winkelwagentjes in volgorde van de totale &quot;Add to Cart&quot;-activiteiten in de afgelopen 7 dagen.
* Meest bekeken: Hiermee herhaalt u mijn totale weergaven per SKU in de afgelopen 7 dagen.
* Aanbevolen voor u - Gebruikt de `viewed-viewed` gegevenspunt - Kopers die deze SKU bekeken, keken ook naar deze andere SKU&#39;s
* Trending: Kijkt terug naar de gebeurtenissen van de paginaweergave in de afgelopen 72 uur voor achtergrondgebeurtenissen en 24 uur voor voorgrondgebeurtenissen
* Geen: De producten worden bevolen door Relevantie

1. Selecteer het type strategie voor de regel. In het venster Test Your Rule worden de verwachte resultaten weergegeven.

>[!NOTE]
>
>Apostroffen en aanhalingstekens in query&#39;s kunnen leiden tot enkele kleine problemen met rangschikking en relevantie in sommige talen.

## Gebeurtenissen toevoegen

Gebeurtenissen zijn acties die de zoekresultaten wijzigen als aan bepaalde voorwaarden wordt voldaan. Eén regel kan maximaal 25 gebeurtenissen bevatten.

* Verhogen - Verplaatst een product hoger in de onderzoeksresultaten.
* Branden - Verplaatst een SKU lager in de zoekresultaten.
* Een product vastzetten - Het product wordt weergegeven in de geselecteerde positie op de pagina.
* Een product verbergen - Hiermee sluit u een SKU uit van de zoekresultaten.

De eenvoudigste manier om een product vast te zetten is door te slepen en neer te zetten.

1. Klik en sleep een product in het deelvenster Testen. Sleep de aanwijzer naar de gewenste positie. De velden Product en Positie worden automatisch ingevuld in het deelvenster Gebeurtenissen.

   ![Regels - Overeenkomst](assets/rule-event-pin-product.png)

U kunt ook op het speldpictogram klikken om een product op de huidige locatie vast te zetten. Gebruik het contextmenu voor ovalen om &#39;Aan de bovenkant vastzetten&#39; of &#39;Aan de onderkant vastzetten&#39;.

>[!NOTE]
>
>U kunt alleen producten vastzetten die in de query zijn geretourneerd.

Of gebeurtenissen kunnen handmatig worden ingesteld:

1. Onder *Gebeurtenissen*, kiest u de **Gebeurtenis** plaatsvinden wanneer aan de desbetreffende voorwaarden is voldaan.

   Kies bijvoorbeeld `Hide a product`. Voer vervolgens de naam in van het product dat u wilt verbergen. Producten worden voorgesteld terwijl u typt.

1. Voor meerdere gebeurtenissen kiest u andere gebeurtenissen die u wilt activeren als aan de voorwaarden is voldaan.

## Aanvullende gegevens

De hier ingevoerde informatie wordt weergegeven in het dialoogvenster [Regeldetails](rules-workspace.md) deelvenster.

1. Onder *Details*, voert u een **Naam** voor de regel. Alle regelnamen moeten uniek zijn.
1. Voer een korte beschrijving in **Beschrijving** van de regel.
1. Voer de **Begindatum** en **Einddatum** om de regel actief te maken of de datums in de kalender te kiezen.

   Als u een datumbereik wilt selecteren, klikt u op de eerste datum en sleept u om het bereik te selecteren.

   ![Regel - volledig](assets/rule-add-details.png)

## De regel voltooien

1. Onderzoek de resultaten van de regel in de testruit.
1. Als de regel veelvoudige vragen heeft, test elk die door de regel zou kunnen worden beïnvloed.
1. Klik op **Opslaan en publiceren**.

   De regel wordt toegevoegd aan de lijst in de regelwerkruimte.

1. Hoewel de actieve regels onmiddellijk in werking treden, zou u tot 15 minuten kunnen moeten wachten op de caching vraagresultaten in de storefront om worden verfrist.

## Veldomschrijvingen

### Voorwaarden (indien)

| Voorwaarde | Beschrijving |
|--- |--- |
| Zoekquery bevat | Een teken of tekenreeks die wordt opgenomen in de query van de winkelier. De vraag van de verkoopster moet slechts één enkel karakter aanpassen om aan deze voorwaarde te voldoen. |
| Zoekquery is | Een teken of tekenreeks die exact overeenkomt met de query van de winkelier. Complexe query&#39;s met meerdere voorwaarden kunnen niet worden samengesteld wanneer deze voorwaarde wordt gebruikt. |
| Zoekquery begint met | De query van de winkelier begint met dit teken of deze tekenreeks. |
| Zoekquery eindigt met | De zoekopdracht van de klant eindigt met dit teken of deze tekenreeks. |

### Logische operatoren

| Operator | Beschrijving |
|--- |--- |
| OF | (Standaard) De logische operator `OR` vergelijkt twee voorwaarden en voldoet aan de vereisten om een gebeurtenis te activeren als minstens één voorwaarde waar is. |
| EN | De logische operator `AND` vergelijkt twee voorwaarden en voldoet aan de vereisten om een gebeurtenis te activeren als beide voorwaarden waar zijn. |

### Operatoren afstemmen

| Operator | Beschrijving |
|--- |--- |
| Alle | Hiermee wijzigt u alle logische operatoren in de regel in `OR` en retourneert de set van overeenkomende producten. |
| Alles | Hiermee wijzigt u alle logische operatoren in de regel in `AND` en retourneert de set van overeenkomende producten. |

### Gebeurtenissen

| Gebeurtenis | Beschrijving |
|--- |--- |
| Verhogen | Hiermee verplaatst u een SKU of reeks SKU&#39;s hoger in de zoekresultaten. Elk object wordt gemarkeerd met een &#39;gebooste&#39; voorvertoningsbadge in de zoekresultaten van de test. |
| Bury | Verplaatst een SKU of een waaier van SKUs lager in de onderzoeksresultaten. Elk object wordt gemarkeerd met een voorvertoningssymbool &quot;begraven&quot; in de zoekresultaten van de test. |
| Een product vastzetten | Koppelt één SKU aan een specifieke positie in de zoekresultaten. Het product wordt gemarkeerd met een &#39;vastgezette&#39; voorvertoningsbadge in de zoekresultaten van de test. |
| Een product verbergen | Sluit SKU, of waaier van SKUs, van de onderzoeksresultaten uit. |

### Details

| Veld | Beschrijving |
|--- |--- |
| Naam | De naam van de regel. Regelnamen moeten uniek zijn. |
| Begindatum | De begindatum van de regel, indien gepland. |
| Einddatum | De einddatum van de regel, indien gepland. |
| Beschrijving | Een korte beschrijving van de regel. |
