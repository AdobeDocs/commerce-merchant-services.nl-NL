---
title: Instellingen
description: Leer hoe te om de bron van uw  [!DNL Product Recommendations]  gegevens te veranderen en hoe te om visuele aanbevelingen toe te laten.
exl-id: 8c074e11-e0cb-4d55-b646-30279c79bbc2
source-git-commit: 75ff893bf5867ededa49807835676ddf9b19adc9
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Instellingen

Wanneer u [ een SaaS gegevensruimte ](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) voor Recommendations vormt, verzamelt de SaaS gegevensruimte catalogusgegevens en opslag-gedrag gegevens. [ Adobe Sensei ](https://www.adobe.com/sensei.html) analyseert dat de gegevens en de productverenigingen die worden gebruikt om het Recommendations van het Product te dienen.

Niet-productieomgevingen voor het testen of opvoeren hebben doorgaans niet de hoeveelheid of kwaliteit van gedragsgegevens van de winkel om realistische productaanbevelingen te kunnen doen. Werkelijk winkelgedrag op schaal kan alleen in een productieomgeving worden vastgelegd. Om dit probleem op te lossen, staat Adobe Commerce u toe om productaanbevelingen van uw productiemilieu met andere, niet productieSaaS gegevensruimten te gebruiken. Met werkelijke storefront-gegevens in een niet-productieomgeving kunt u een voorvertoning weergeven van de aanbevelingen die uw klanten zien en experimenteren met verschillende soorten aanbevelingen en plaatsingslocaties. Recommendations vanuit een andere SaaS-gegevensruimte kan door kopers worden voorvertoond, maar er wordt niet op geklikt.

Staging-orders worden opgenomen met de testvolgorde `environmentId` . Zij heeft geen invloed op de productiegegevens. De productiegegevens worden opgehaald met de `alternateEnvironmentId` .

>[!NOTE]
>
>Wanneer het gebruiken van Product Recommendations door REST, kan de `alternateEnvironmentId` parameter worden gebruikt om andere dataspaces te specificeren. Wanneer u Product Recommendations via GraphQL gebruikt, is deze parameter niet beschikbaar.

## Kies de bron voor aanbevelingen

Als u de bron van de gegevens van uw productaanbevelingen wilt wijzigen, kiest u de SaaS-gegevensruimte met de gedragsgegevens die u wilt gebruiken. Voordat u begint, moet u ervoor zorgen dat:

- De gegevensinzameling van de opslag moet [ worden gevormd en worden toegelaten ](install-configure.md) voor uw productiemilieu en [ verifieerde ](verify.md) dat het gedragsgegevens worden verzonden naar Adobe Commerce.
- De niet-productieomgevingscatalogus moet in wezen hetzelfde zijn als de productiecatalogus. Het gebruik van vergelijkbare catalogi zorgt ervoor dat de eenheden van de productaanbeveling de eenheden in productie dicht navielen.

1. Meld u aan bij de beheerder van uw Adobe Commerce-omgeving die niet voor productie is bedoeld.

1. Op _Admin_ sidebar, ga **Marketing** > _Bevorderingen_ > **Recommendations van het Product**.

1. Klik **Montages**.

   ![ montages van de productaanbeveling ](assets/settings.png)
   _Montages_

1. In de _bron van Recommendations_ sectie, laat de **aanbevelingen van de Ophalen van een verschillende SaaS gegevensruimte** optie toe. De _bron van Recommendations_ sectie verschijnt slechts in een non-production milieu.

   Een lijst van _Beschikbare Spaties van Gegevens SaaS_ verschijnt.

   ![ montages van de productaanbeveling ](assets/settings-select-saas.png)
   _Montages_

1. Selecteer de SaaS-gegevensruimte met winkelgegevens die u wilt gebruiken.

1. Klik **sparen veranderingen**.

   Adobe Commerce haalt nu aanbevelingen op uit de geselecteerde gegevensruimte.

   >[!NOTE]
   >
   > Terwijl u aanbevelingen kunt bekijken die van een andere SaaS gegevensruimte op de niet-productiereilter worden gehaald, kunt u niet de aanbevelingen klikken.

### Een nieuwe SaaS-gegevensruimte configureren

1. In de Recommendations bronsectie, klik **uitgeven Configuratie**.

1. Volg de instructies om een nieuwe [[!DNL Commerce]  dienst ](/help/landing/saas.md) te vormen.

## Visuele aanbevelingen inschakelen

Als de [ Visuele module van Recommendations van het Product ](install-configure.md) geïnstalleerd is, moet u Visuele Recommendations toelaten om het [ Visuele ](type.md#visualsim) type van de aanbeveling van de Gelijksgelijkenis {te gebruiken.

In de _Visuele Recommendations_ sectie, plaats **laat Visuele Recommendations** aan de actieve positie toe.
