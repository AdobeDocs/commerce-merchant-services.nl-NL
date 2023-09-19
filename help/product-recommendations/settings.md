---
title: Instellingen
description: Leer hoe u de bron van uw [!DNL Product Recommendations] gegevens en hoe te om visuele aanbevelingen toe te laten.
exl-id: 8c074e11-e0cb-4d55-b646-30279c79bbc2
source-git-commit: 75ff893bf5867ededa49807835676ddf9b19adc9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Instellingen

Wanneer u [een SaaS-gegevensruimte configureren](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) voor Recommendations verzamelt de SaaS-gegevensruimte catalogusgegevens en gegevens over storefront-gedrag. [Adobe Sensei](https://www.adobe.com/sensei.html) analyseert dat gegevens en vergelijkt productverenigingen die worden gebruikt om Product Recommendations te bedienen.

Niet-productieomgevingen voor het testen of opvoeren hebben doorgaans niet de hoeveelheid of kwaliteit van gedragsgegevens van de winkel om realistische productaanbevelingen te kunnen doen. Werkelijk winkelgedrag op schaal kan alleen in een productieomgeving worden vastgelegd. Om dit probleem op te lossen, staat Adobe Commerce u toe om productaanbevelingen van uw productiemilieu met andere, niet productieSaaS gegevensruimten te gebruiken. Met werkelijke storefront-gegevens in een niet-productieomgeving kunt u een voorvertoning weergeven van de aanbevelingen die uw klanten zien en experimenteren met verschillende soorten aanbevelingen en plaatsingslocaties. Recommendations vanuit een andere SaaS-gegevensruimte kan door kopers worden voorvertoond, maar er wordt niet op geklikt.

Stapelorders worden geregistreerd met behulp van de fasering `environmentId`. Zij heeft geen invloed op de productiegegevens. De productiegegevens worden opgehaald met de `alternateEnvironmentId`.

>[!NOTE]
>
>Als u Product Recommendations via REST gebruikt, wordt `alternateEnvironmentId` De parameter kan worden gebruikt om andere dataspaces te specificeren. Wanneer u Product Recommendations via GraphQL gebruikt, is deze parameter niet beschikbaar.

## Kies de bron voor aanbevelingen

Als u de bron van de gegevens van uw productaanbevelingen wilt wijzigen, kiest u de SaaS-gegevensruimte met de gedragsgegevens die u wilt gebruiken. Voordat u begint, moet u ervoor zorgen dat:

- De gegevensverzameling van de opslagront moet [geconfigureerd en ingeschakeld](install-configure.md) voor uw productieomgeving en [geverifieerd](verify.md) dat er gedragsgegevens naar Adobe Commerce worden verstuurd.
- De niet-productieomgevingscatalogus moet in wezen hetzelfde zijn als de productiecatalogus. Het gebruik van vergelijkbare catalogi zorgt ervoor dat de eenheden van de productaanbeveling de eenheden in productie dicht navielen.

1. Meld u aan bij de beheerder van uw Adobe Commerce-omgeving die niet voor productie is bedoeld.

1. Op de _Beheerder_ zijbalk, ga naar **Marketing** > _Aanbiedingen_ > **Product Recommendations**.

1. Klikken **Instellingen**.

   ![productaanbevelingen, instellingen](assets/settings.png)
   _Instellingen_

1. In de _Recommendations-bron_ in, schakelt u de **Aanbevelingen ophalen uit een andere SaaS-gegevensruimte** -optie. De _Recommendations-bron_ wordt alleen weergegeven in een niet-productieomgeving.

   Een lijst van _Beschikbare SaaS-gegevensruimten_ wordt weergegeven.

   ![productaanbevelingen, instellingen](assets/settings-select-saas.png)
   _Instellingen_

1. Selecteer de SaaS-gegevensruimte met winkelgegevens die u wilt gebruiken.

1. Klikken **Wijzigingen opslaan**.

   Adobe Commerce haalt nu aanbevelingen op uit de geselecteerde gegevensruimte.

   >[!NOTE]
   >
   > Terwijl u aanbevelingen kunt bekijken die van een andere SaaS gegevensruimte op de niet-productiereilter worden gehaald, kunt u niet de aanbevelingen klikken.

### Een nieuwe SaaS-gegevensruimte configureren

1. Klik in de Recommendations-bronsectie op **Configuratie bewerken**.

1. Volg de instructies om een nieuwe te vormen [[!DNL Commerce] service](/help/landing/saas.md).

## Visuele aanbevelingen inschakelen

Als de [Visual Product Recommendations](install-configure.md) is geïnstalleerd, moet u Visual Recommendations toelaten om het [Visuele gelijkenis](type.md#visualsim) soort aanbeveling.

In de _Visual Recommendations_ sectie, set **Visual Recommendations inschakelen** op de actieve positie.
