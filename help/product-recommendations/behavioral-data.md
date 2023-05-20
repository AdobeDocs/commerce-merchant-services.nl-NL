---
title: Gedragsgegevens
description: Meer informatie over gedragsgegevens en wanneer u deze kunt gaan gebruiken.
exl-id: d68a97b9-1497-4603-a72c-4aaaf6e048cb
source-git-commit: 840b091638aedd3f6ac097a010d035eff997ffe2
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---

# Gedragsgegevens

Sommige soorten aanbevelingen gebruiken gedragsgegevens van uw klanten om machine het leren modellen op te leiden om gepersonaliseerde aanbevelingen te bouwen. Andere soorten aanbevelingen gebruiken alleen catalogusgegevens en gebruiken geen gedragsgegevens. Als u snel wilt beginnen, kunt u de volgende, catalogus-slechts aanbevelingen types gebruiken:

- `More like this`
- `Visual similarity`

Wanneer kun je aanbevelingen gebruiken die gedragsgegevens gebruiken? Het hangt ervan af. Dit wordt de _Koude start_ probleem.

De _Koude start_ het probleem is dat wordt gemeten hoeveel tijd een model nodig heeft om te trainen voordat het als een hoge kwaliteit kan worden beschouwd . In de aanbevelingen voor producten wordt gewacht tot Adobe Sensei zijn modellen voor computerleren heeft getraind voordat het aanbevelingen op uw site implementeert. Hoe meer gegevens deze modellen hebben, des te nauwkeuriger en nuttiger de aanbevelingen zijn. Het verzamelen van deze gegevens kost tijd en varieert afhankelijk van het verkeersvolume. Omdat deze gegevens alleen op een productiesite kunnen worden verzameld, is het in uw belang om gegevensverzameling daar zo vroeg mogelijk te implementeren. U kunt dit doen door [installeren en configureren](install-configure.md) de `magento/production-recommendations` module.

De volgende tabel bevat een aantal algemene richtlijnen voor de hoeveelheid tijd die nodig is om voldoende gegevens voor elk type aanbeveling te verzamelen:

| Type aanbeveling | Trainingstijd | Notities |
|---|---|---|
| Gebaseerd op populariteit (`Most viewed`, `Most purchased`, `Most added to cart`) | Varieert | Afhankelijk van het volume van gebeurtenissen - weergaven komen het meest voor en leren dus sneller; voegt dan aan winkelwagen toe en koopt vervolgens |
| `Viewed this, viewed that` | Meer training is vereist | De productweergaven zijn aanzienlijk hoog in volume |
| `Viewed this, bought that`, `Bought this, bought that` | De meeste training is vereist | Aankoopgebeurtenissen zijn de meest voorkomende gebeurtenissen op de commercesite, met name in vergelijking met de productweergaven |
| `Trending` | Vereist drie dagen gegevens om een basislijn voor populariteit te bepalen | Trending is een maat voor de recente dynamiek in de populariteit van een product in vergelijking met zijn eigen populariteit. De trending score van een product wordt berekend met behulp van een voorgrondset (recente populariteit in 24 uur) en een achtergrondset (basislijn voor populariteit in 72 uur). Als een item in de afgelopen 24 uur veel populairder is geworden dan de basislijnpopulariteit, krijgt het een hoge trendscore. Elk product heeft deze score, en de hoogste op elk ogenblik omvatten de reeks hoogste trending producten. |

Andere variabelen die van invloed kunnen zijn op de tijd die nodig is om te trainen:

- Hoger verkeersvolume draagt bij aan sneller leren
- Sommige aanbevelingen typen trajecten sneller dan andere
- Adobe Commerce berekent de gedragsgegevens elke vier uur opnieuw. Recommendations wordt nauwkeuriger naarmate ze langer op uw site worden gebruikt.

Om u te helpen de opleidingsvooruitgang van elk aanbevelingstype visualiseren, [aanbeveling maken](create.md) op de pagina worden gereedheidsindicatoren weergegeven.

Terwijl de gegevens over productie en machine het leren modellen worden verzameld worden getraind, kunt u uitvoeren [resterende taken](implementation-workflow.md) nodig om aanbevelingen aan uw winkel op te stellen. Tegen de tijd dat u klaar bent met het testen en configureren van aanbevelingen, hebben de modellen voor het leren van machines genoeg gegevens verzameld en berekend om relevante aanbevelingen te bouwen, zodat u de aanbevelingen kunt implementeren in uw winkel.

Als er voor de meeste SKU&#39;s onvoldoende verkeer (weergaven, gekochte producten, trending) is, zijn er wellicht onvoldoende gegevens om het leerproces te voltooien. Hierdoor kan de gereedheidsindicator in de Admin er uitzien alsof deze vastzit.
De gereedheidsindicatoren zijn bedoeld om handelaren een ander gegevenspunt te bieden bij het kiezen van het aanbevolen type voor hun winkel. De getallen zijn een leidraad en mogen nooit 100% bedragen.

## Aanbevelingen voor back-up {#backuprecs}

Als er onvoldoende invoergegevens zijn om alle aangevraagde aanbevolen items in een eenheid te leveren, geeft Adobe Commerce back-upaanbevelingen om aanbevolen eenheden te vullen. Als u bijvoorbeeld de `Recommended for you` een eerste verkoopmedewerker op uw site heeft onvoldoende gedragsgegevens gegenereerd om nauwkeurig aanbevolen, gepersonaliseerde producten te kunnen gebruiken. In dit geval worden objecten op Adobe Commerce-oppervlakken gebaseerd op de `Most viewed` soort aanbeveling aan deze verkoopster.

De volgende aanbevelingen typen fallback aan `Most viewed` soort aanbeveling indien er onvoldoende inputgegevens zijn verzameld:

- `Recommended for you`
- `Viewed this, viewed that`
- `Viewed this, bought that`
- `Bought this, bought that`
- `Trending`
- `Conversion (view to purchase)`
- `Conversion (view to cart)`
