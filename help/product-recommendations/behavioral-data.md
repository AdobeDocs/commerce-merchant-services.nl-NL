---
title: Gedragsgegevens
description: Meer informatie over gedragsgegevens en wanneer u deze kunt gaan gebruiken.
exl-id: d68a97b9-1497-4603-a72c-4aaaf6e048cb
source-git-commit: 840b091638aedd3f6ac097a010d035eff997ffe2
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Gedragsgegevens

Sommige soorten aanbevelingen gebruiken gedragsgegevens van uw klanten om machine het leren modellen op te leiden om gepersonaliseerde aanbevelingen te bouwen. Andere soorten aanbevelingen gebruiken alleen catalogusgegevens en gebruiken geen gedragsgegevens. Als u snel wilt beginnen, kunt u de volgende, catalogus-slechts aanbevelingen types gebruiken:

- `More like this`
- `Visual similarity`

Wanneer kun je aanbevelingen gebruiken die gedragsgegevens gebruiken? Het hangt ervan af. Dit wordt bedoeld als _Koud Begin_ probleem.

Het _Koude 1} probleem van het Begin van het Begin is een maatregel van hoeveel tijd dat een model moet opleiden alvorens het als hoge kwaliteit kan worden beschouwd._ In de aanbevelingen voor producten wordt gewacht tot Adobe Sensei zijn modellen voor computerleren heeft getraind voordat het aanbevelingen op uw site implementeert. Hoe meer gegevens deze modellen hebben, des te nauwkeuriger en nuttiger de aanbevelingen zijn. Het verzamelen van deze gegevens kost tijd en varieert op basis van het verkeersvolume. Omdat deze gegevens alleen op een productiesite kunnen worden verzameld, is het in uw belang om gegevensverzameling daar zo vroeg mogelijk te implementeren. U kunt dit doen door [ te installeren en te vormen ](install-configure.md) de `magento/production-recommendations` module.

De volgende tabel bevat een aantal algemene richtlijnen voor de hoeveelheid tijd die nodig is om voldoende gegevens voor elk type aanbeveling te verzamelen:

| Type aanbeveling | Trainingstijd | Notities |
|---|---|---|
| Gebaseerd op populariteit (`Most viewed`, `Most purchased`, `Most added to cart`) | Varieert | Afhankelijk van het volume van gebeurtenissen - weergaven worden het meest gebruikt en leren dus sneller; voegt dan toe aan winkelwagentje en koopt |
| `Viewed this, viewed that` | Meer training is vereist | De productweergaven zijn aanzienlijk hoog in volume |
| `Viewed this, bought that`, `Bought this, bought that` | De meeste training is vereist | Aankoopgebeurtenissen zijn de meest voorkomende gebeurtenissen op de commercesite, met name in vergelijking met de productweergaven |
| `Trending` | Vereist drie dagen gegevens om een basislijn voor populariteit te bepalen | Trending is een maat voor de recente dynamiek in de populariteit van een product in vergelijking met zijn eigen populariteit. De trending score van een product wordt berekend met behulp van een voorgrondset (recente populariteit in 24 uur) en een achtergrondset (basislijn voor populariteit in 72 uur). Als een item in de afgelopen 24 uur veel populairder is geworden dan de basislijnpopulariteit, krijgt het een hoge trendscore. Elk product heeft deze score, en de hoogste op elk ogenblik omvatten de reeks hoogste trending producten. |

Andere variabelen die van invloed kunnen zijn op de tijd die nodig is om te trainen:

- Hoger verkeersvolume draagt bij aan sneller leren
- Sommige aanbevelingen typen sneller dan andere
- Adobe Commerce berekent de gedragsgegevens elke vier uur opnieuw. Recommendations wordt nauwkeuriger naarmate ze langer op uw site worden gebruikt.

Om u te helpen de opleidingsvooruitgang van elk aanbevelingstype visualiseren, [ creeer aanbeveling ](create.md) de indicatoren van de paginabereidheid.

Terwijl het gegeven op productie en machine het leren modellen wordt verzameld, kunt u de [ resterende taken ](implementation-workflow.md) noodzakelijk uitvoeren om aanbevelingen aan uw opslag op te stellen. Tegen de tijd dat u klaar bent met het testen en configureren van aanbevelingen, hebben de modellen voor het leren van machines genoeg gegevens verzameld en berekend om relevante aanbevelingen te bouwen, zodat u de aanbevelingen kunt implementeren in uw winkel.

Als er voor de meeste SKU&#39;s onvoldoende verkeer (weergaven, gekochte producten, trending) is, zijn er wellicht onvoldoende gegevens om het leerproces te voltooien. Dit kan ertoe leiden dat de gereedheidsindicator in de Admin er uitziet alsof deze vastzit.
De gereedheidsindicatoren zijn bedoeld om handelaren een ander gegevenspunt te bieden bij het kiezen van het aanbevolen type voor hun winkel. De getallen zijn een leidraad en mogen nooit 100% bedragen.

## Aanbevelingen voor back-up {#backuprecs}

Als er onvoldoende invoergegevens zijn om alle aangevraagde aanbevolen items in een eenheid te leveren, geeft Adobe Commerce back-upaanbevelingen om aanbevolen eenheden te vullen. Als u bijvoorbeeld het aanbevolen type `Recommended for you` op uw homepage plaatst, heeft een eerste winkelprogramma op uw site niet genoeg gedragsgegevens gegenereerd om op de juiste manier gepersonaliseerde producten te kunnen aanbevelen. In dit geval worden Adobe Commerce-items op basis van het aanbevolen type `Most viewed` aan deze gebruiker doorgegeven.

De volgende aanbevelingen typen fallback naar het `Most viewed` aanbevolen type als er onvoldoende inputgegevens zijn verzameld:

- `Recommended for you`
- `Viewed this, viewed that`
- `Viewed this, bought that`
- `Bought this, bought that`
- `Trending`
- `Conversion (view to purchase)`
- `Conversion (view to cart)`
