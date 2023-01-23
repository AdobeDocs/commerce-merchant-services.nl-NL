---
title: Veldgroepen toevoegen aan XDM-schema
description: Leer hoe u Adobe Commerce-specifieke veldgroepen toevoegt aan een XDM-schema.
exl-id: 4401bbe7-1ccc-4349-a998-9e9ee9db590f
source-git-commit: c9b1d7e34632f7a54544bc6944144b1833ecc5a5
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Veldgroepen toevoegen aan XDM-schema

Een van de [onboarding stappen](overview.md#onboarding-steps) om de verbindingslijn van het Experience Platform te gebruiken moet tot de werkruimte van de gegevensstroom toegang hebben en [een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) dat specifiek is voor Adobe Commerce. Wanneer u die gegevensstroom creeert, moet u ook een schema selecteren XDM dat de gegevens vertegenwoordigt u van plan bent in te voeren. Dit onderwerp voorziet u van de gebiedsgroepen uw schema XDM moet omvatten om de gegevens met succes te verzamelen die door de Adobe Commerce storefront worden verstrekt [gebeurtenissen](events.md).

1. Als u nog geen XDM-schema hebt, [maken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#create) 1. Anders, [bewerken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#edit) uw bestaande XDM-schema in de gebruikersinterface van Adobe Experience Platform.

1. [Toevoegen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#add-field-groups) de volgende specifieke handelsgroepen:

   - Zoeken op site
   - Webpagina bezoeken
   - Aanmeldingsproces gebruiker
   - Referentietoetsen
   - Persoonlijke contactgegevens
   - Handelsgegevens
   - Adobe Analytics Experience Event Commerce (als u gegevens naar Adobe Analytics wilt verzenden)
   - Identiteitskaart

   >[!NOTE]
   >
   > Stel geen voor handel specifieke veldgroepen in als `Primary identity`. Hierbij wordt het veld naar wens geïdentificeerd en het Experience Platform verwacht dat veld in elke gebeurtenis. Als dat veld ontbreekt, mislukt het invoeren van gegevens.

   Uw XDM-schema bevat nu Handelsspecifieke veldgroepen, zodat de gegevens die bij de Commerce-winkel worden verzameld [gebeurtenissen](events.md) wordt vertegenwoordigd in XDM.

1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt of bijgewerkt.

   Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst, die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan.

1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) en selecteer het schema XDM dat de handel-specifieke gebiedsgroepen en de overeenkomstige dataset bevat.

   De gegevensstroom door:sturen de verzamelde gegevens aan de dataset. De gegevens worden vertegenwoordigd in de dataset die op het geselecteerde schema wordt gebaseerd.
