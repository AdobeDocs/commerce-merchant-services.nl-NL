---
title: Veldgroepen toevoegen aan XDM-schema
description: Leer hoe u Adobe Commerce-specifieke veldgroepen toevoegt aan een XDM-schema.
exl-id: 4401bbe7-1ccc-4349-a998-9e9ee9db590f
source-git-commit: 06499893f6cad4d920a231f5b22417d3044b2319
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Veldgroepen toevoegen aan XDM-schema

Een van de [voorwaarden](overview.md#prereqs) om de verbindingslijn van het Experience Platform te gebruiken moet tot de werkruimte van de gegevensstroom toegang hebben en [een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=en) dat specifiek is voor Adobe Commerce. Wanneer u die gegevensstroom creeert, moet u ook een schema selecteren XDM dat de gegevens vertegenwoordigt u van plan bent in te voeren. Dit onderwerp voorziet u van de gebiedsgroepen uw schema XDM moet omvatten om de gegevens met succes te verzamelen die door de Adobe Commerce storefront worden verstrekt [gebeurtenissen](events.md).

1. Als u nog geen XDM-schema hebt, [maken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#create) 1. Anders, [bewerken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#edit) uw bestaande XDM-schema in de gebruikersinterface van Adobe Experience Platform.

1. [Toevoegen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=en#add-field-groups) de volgende specifieke handelsgroepen:

   - Handel
   - Zoeken op site
   - Webpagina bezoeken
   - Aanmeldingsproces gebruiker
   - Referentietoetsen
   - Persoonlijke contactgegevens
   - Handelsgegevens
   - Adobe Analytics Experience Event Commerce (als u gegevens naar Adobe Analytics wilt verzenden)
   - Persoon-id

   >[!NOTE]
   >
   > Stel geen voor handel specifieke veldgroepen in als `Primary identity`. Hierbij wordt het veld naar wens geïdentificeerd en het Experience Platform verwacht dat veld in elke gebeurtenis. Als dat veld ontbreekt, mislukt het invoeren van gegevens.

   Uw XDM-schema bevat nu Handelsspecifieke veldgroepen, zodat de gegevens die bij de Commerce-winkel worden verzameld [gebeurtenissen](events.md) wordt vertegenwoordigd in XDM.

1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) en selecteer het XDM-schema dat de handel-specifieke gebiedsgroepen bevat.
