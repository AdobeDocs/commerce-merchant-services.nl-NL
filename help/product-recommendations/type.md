---
title: Typen aanbevelingen
description: Leer meer over de aanbevelingen die u op verschillende pagina's op uw site kunt implementeren.
source-git-commit: 7fe89df32dc5363817f957180e5b75e7217fc14a
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---

# Typen aanbevelingen

Adobe Commerce biedt een groot aantal aanbevelingen die u op verschillende pagina&#39;s op uw site kunt implementeren. Ter referentie worden de aanbevolen typen als volgt gegroepeerd:

- [Gepersonaliseerd](#personalized)
- [Crosssells en up-sells](#crossup)
- [Populariteit](#popularity)
- [Krachtig](#highperf)

Als beste praktijk, adviseert Adobe de volgende richtlijnen wanneer het gebruiken van aanbevelingen:

- Diversifieer uw aanbevelingen types. Klanten negeren aanbevelingen als ze steeds weer dezelfde producten voorstellen.

- Implementeer niet dezelfde aanbevelingen op de pagina met winkelwagentjes en de pagina met bevestiging van bestellingen. Gebruik `Most Added to Cart` voor de kartonpagina en `Bought This, Bought That` voor de bevestigingspagina van de bestelling.

- Houd uw site rustig. Implementeer niet meer dan drie aanbevolen eenheden op dezelfde pagina.

- Als uw winkel kleding verkoopt, `More like this` aanbevelingen kunnen genderspecifieke items voorstellen die niet overeenkomen met het geslacht van het product dat wordt bekeken. U kunt dit soort aanbevelingen alleen gebruiken voor andere categorieën dan kleding.

## Gepersonaliseerd {#personalized}

| Type | Beschrijving |
|---|---|
| Aanbevolen voor u | Hiermee worden objecten aanbevolen op basis van het huidige en vorige onsite gedrag van elke verkoper. Hier worden zeer relevante aanbevelingen weergegeven op basis van de bladeren- en aankoopgeschiedenis van de klant. Dit soort aanbevelingen is effectief op de homepage waar de meeste klanten hun reis op een plaats beginnen. Voor nieuwe kopers op uw site die geen signaal hebben gegenereerd om hun ervaring aan te passen, toont Adobe Commerce objecten op basis van het meest bekeken soort aanbeveling. Wanneer de verkoopster begint te communiceren met de producten op de site, worden de aanbevolen producten echter in real-time aangepast aan hun gedrag.<br /><br />Worden gebruikt:<br /><br />- Homepage<br />- Categorie<br /><br />Voorgestelde labels:<br /><br /> - Alleen voor u<br />- Aanbevolen voor u<br />- Geïnspireerd door uw winkeltrends |
| Onlangs bekeken | De producten van vertoningen onlangs bekeken door de verkoopster, die op browser geschiedenis wordt gebaseerd. Verwijderde producten worden door de aanbevolen eenheid verwijderd. De aanbevolen eenheid wordt niet weergegeven als er geen browsergeschiedenis is of als er onvoldoende geschiedenis is wanneer filterregels worden toegepast. Als de resultaten minder producten bevatten dan worden gevormd, toont de aanbeveling eenheid slechts de teruggekeerde producten.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br />- Onlangs bekeken<br />- Kijk nog eens |

## Crosssells en up-sells {#crossup}

| Type | Beschrijving |
|---|---|
| Bekeken dit, gezien dat | Aanbevolen objecten die meestal worden weergegeven door andere kopers die hetzelfde object hebben bekeken. Vaak wordt het een sociale-bewijsaanbeveling genoemd die consumenten helpt producten te vinden die andere consumenten kunnen vinden.<br /><br />Indien gebruikt:<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br ><br />- Klanten die dit item ook hebben bekeken (PDP) |
| Bekijk dit, kocht dat | Aanbevolen objecten die het meest worden aangeschaft door kopers die het opgegeven object hebben bekeken. Helpt winkeliers te helpen producten te vinden die ze anders misschien niet hebben opgemerkt.<br /><br />Indien gebruikt:<br /><br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br />- Klanten die deze ultieme aankoop hebben bekeken<br />- Klanten die uiteindelijk zijn aangeschaft<br />- Wat kopen anderen na het bekijken van dit object? |
| Dit gekocht | Aanbevolen objecten die het meest worden aangeschaft door kopers die het opgegeven object hebben aangeschaft. Meestal gebruikt op de detailpagina van het winkelwagentje of het product om de blootstelling van het verwante product te verhogen om de gemiddelde orderwaarde te verhogen. Geeft zeer relevante producten weer die kopers aan hun winkelwagen kunnen toevoegen door samen te voegen wat andere kopers met het huidige product hebben gekocht.<br /><br />Indien gebruikt:<br /><br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br />- Haal alles in huis wat u nodig hebt<br />- Vergeet deze niet<br />- Vaak samen gekocht |
| Meer als dit | Aanbevelt items op basis van vergelijkbare inhoud en kenmerken. Door de kenmerken van de bekeken producten te evalueren, kunt u vergelijkbare producten in dezelfde categorie aanbevelen. Als een winkelier bijvoorbeeld door yoga-mats bladert, wordt u aangeraden andere producten uit de apparatencategorie te gebruiken. Omdat in dit soort aanbevelingen geen onderscheid wordt gemaakt tussen genders, wordt het niet aanbevolen voor kleding, mode of andere geslachtsspecifieke verticalen.<br /><br />Indien gebruikt:<br /><br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br /> - Meer objecten zoals deze<br />- Vergelijkbaar met dit |
| [Visuele gelijkenis](#visualsim) | Hiermee kunt u vergelijkbare producten aanbevelen als het product dat u bekijkt. Dit soort aanbevelingen is vooral handig als afbeeldingen en visuele aspecten van producten belangrijk zijn voor de boodschappenervaring. |

## Populariteit {#popularity}

| Type | Beschrijving |
|---|---|
| Meest bekeken | Aanbevolen producten die het meest werden bekeken door het aantal sessies te tellen waarop een weergaveactie in de laatste zeven dagen plaatsvond.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br />- Meest populair<br />- Trends<br />- Populair op dit moment<br />- Recent populair<br />- Populaire items geïnspireerd op dit item (PDP)<br />- Topverkopers |
| Trend | Aanbevolen items op basis van de recente dynamiek van de populariteit van een product op uw site.<br /><br />Adobe Sensei voegt gegevens over bladeren en aankopen op uw site samen om te bepalen welke producten het meest recent bij uw klanten worden gebruikt. Omdat Trending de recente productdynamiek analyseert, is het een efficiënt advisetype voor catalogi die een hoge omzet hebben. Als uw catalogus statisch is, is deze wellicht minder handig, tenzij de winkelpatronen van uw publiek sterk variëren.<br /><br />Bij gebruik op de homepage wordt met Trending aanbevolen dat objecten die onlangs op de hele site populair zijn, worden weergegeven. Trending geeft geen producten weer die altijd populair zijn, maar producten die onlangs populair zijn geworden. Als u bijvoorbeeld een campagne voor het in de handel brengen van e-mail hebt om bepaalde producten te promoten, vergroot de populariteit van de e-mail de kans dat de geprezen producten als trending worden ingedeeld.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br />- Trends<br />- Trend nu<br />- Recent trendend<br />- Hot items<br />- Trending related products (PDP) |

## Hoge prestaties {#highperf}

| Type | Beschrijving |
|---|---|
| Omzetten van aankoop bekijken | Aanbevolen producten met de hoogste weergave-naar-aankoop conversiesnelheid. Van alle winkelsessies die het product bekeken, het percentage dat het product heeft aangeschaft.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br /> -Topverkopers<br />- Populaire objecten<br />- Misschien bent u geïnteresseerd in |
| Omzetten naar winkelwagentje | Hiermee worden producten met de hoogste conversiesnelheid voor weergave naar wagen aanbevolen. Van alle winkelsessies waarin het product werd weergegeven, het percentage waarmee het product aan de winkelwagen is toegevoegd.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br /> - Topverkopers<br />- Populaire objecten<br />- Misschien bent u geïnteresseerd in |
| Meest aangeschaft | Deze aanbeveling wordt vaak &#39;&#39;Top Sellers&#39;&#39; genoemd en telt het aantal sessies waarvoor een plaatsordeactie is uitgevoerd in de laatste zeven dagen. Dit soort aanbevelingen kan op alle pagina&#39;s worden gebruikt.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br /> - Meest populair<br />- Trends<br />- Populair op dit moment<br />- Recent populair<br />- Populaire items geïnspireerd op dit item (PDP)<br />- Topverkopers |
| Meest toegevoegd aan winkelwagentje | Aanbevolen objecten die de afgelopen zeven dagen het vaakst door kopers aan winkelwagentjes zijn toegevoegd. Dit soort aanbevelingen kan op alle pagina&#39;s worden gebruikt.<br /><br />Indien gebruikt:<br /><br />- Homepage<br />- Categorie<br />- Productdetails<br />- Kar<br />- Bevestiging<br /><br />Voorgestelde labels:<br /><br /> - Meest populair<br />- Trends<br />- Populair op dit moment<br />- Recent populair<br />- Populaire items geïnspireerd op dit item (PDP)<br />- Topverkopers |

## Visuele gelijkenis {#visualsim}

De _Visuele gelijkenis_ het soort aanbevelingen beveelt aan om soortgelijke producten te gebruiken als het product dat wordt bekeken . Dit soort aanbevelingen is vooral handig wanneer afbeeldingen en visuele aspecten van de producten belangrijke onderdelen zijn van de boodschappenervaring.

### Hoe werkt het

De _Visuele gelijkenis_ het type van aanbeveling biedt aanbevelingen voor andere producten in uw catalogus die een visuele gelijkenis met de beelden die momenteel worden bekeken. Visuele gelijkenis omvat aspecten zoals:

- Kleur
- Vorm
- Grootte
- Structuur
- Materiaal
- Stijl

Adobe Sensei gebruikt AI om de beelden in uw catalogus te verwerken en te analyseren en attributen te bouwen die worden gebruikt om visuele gelijkenissen te bepalen.

>[!NOTE]
>
> Als u dit type aanbevelingen test in een niet-productieomgeving, moet u ervoor zorgen dat de URL&#39;s van de afbeelding openbaar toegankelijk zijn.

>[!NOTE]
>
> Productafbeeldingen moeten momenteel 10 MB of minder groot zijn.

Omdat dit aanbevelingen type niet op de meeste catalogi van toepassing is, wordt het niet toegelaten door gebrek. U moet dit aanbevelingstype uitdrukkelijk toelaten.

### Aanbevolen type voor visuele gelijkenis inschakelen

>[!NOTE]
>
> De _Visuele gelijkenis_ het type aanbeveling is beschikbaar wanneer u [installeren](install-configure.md) als een optionele module.

1. Op de _Beheer_ zijbalk, ga naar **Marketing** > _Aanbiedingen_ > **Product Recommendations** om de _Product Recommendations_ dashboard.

1. Klikken **Instellingen** (tandwielpictogram) om de _Instellingen_ pagina.

1. In de _Visual Recommendations_ sectie, selecteren tot **Visual Recommendations inschakelen**.

1. Klikken **Wijzigingen opslaan** als u klaar bent.

   De [Nieuwe aanbeveling maken](create.md) pagina wordt nu weergegeven **Visuele gelijkenis** als een selecteerbaar aanbevolen type wanneer het paginatype **Productgegevens**.

Nadat u visuele aanbevelingen hebt ingeschakeld, start Adobe Sensei de afbeeldingsverwerking. Hoe lang dit duurt, is afhankelijk van de grootte van de catalogus.

### Indien gebruikt

- Productdetails

### Voorgestelde winkellabels

- U kunt ook
- We hebben andere producten gevonden die je wellicht aanspreken
- Geïnspireerd door deze stijl

### Voorbeeld

In de volgende afbeelding ziet u de pagina met productdetails voor de _Clamber Watch_:

![Clamber Watch](assets/visual-sim-pdp.png)

In het volgende voorbeeld wordt het _Visuele gelijkenis_ aanbeveling-eenheid voor _Clamber Watch_:

![Visuele eenheid voor gelijkenis](assets/visual-sim-unit.png)
