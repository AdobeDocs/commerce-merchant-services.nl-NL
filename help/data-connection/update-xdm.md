---
title: Tijdlijngebeurtenisschema's bijwerken voor gegevensverwerking bij handel
description: Leer hoe te om een schema, dataset, en gegevensstroom tot stand te brengen om tijdreeksgebeurtenisgegevens voor de gegevensopname van de Handel te verzamelen en te verzenden.
exl-id: 4401bbe7-1ccc-4349-a998-9e9ee9db590f
role: Admin, Developer
feature: Personalization, Integration
source-git-commit: d5824e11b4961b518e35fcf56ff2c7ee00480617
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 0%

---

# Tijdlijngebeurtenisschema&#39;s bijwerken voor gegevensverwerking bij handel

Een van de [onboarding stappen](overview.md#onboarding-steps) voor het gebruik van de [!DNL Data Connection] de extensie heeft toegang tot de werkruimte van de gegevensstroom en [een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) specifiek voor Adobe Commerce. Wanneer u die gegevensstroom creeert, moet u ook een schema selecteren dat de gegevens beschrijft u van plan bent in te voeren. Dat schema moet handels-specifieke gebiedsgroepen omvatten.

In dit artikel worden de veldgroepen weergegeven die uw schema moet opnemen om de volgende tijdreeksgegevens van de Adobe Commerce-gebeurtenissen te kunnen verzamelen:

- [Gedrag](events.md) - Omvat storefront, profiel, onderzoek, en B2B gebeurtenissen.
- [Achterkantoor](events-backoffice.md) - Bevat de status van de order en profielgebeurtenissen.

Meer informatie over [tijdreeksgegevens](data-ingestion.md).

Meer informatie over de [grondbeginselen van de schemacompositie](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html).

## Het schema van de update met het gedrag van de tijdreeks en de gegevens van de achterkantoorgebeurtenis

In deze sectie leert u hoe u uw bestaande schema bijwerkt of een schema maakt om gedrags- en back-office gebeurtenisgegevens op te nemen.

>[!NOTE]
>
>Zie [tijdreeksprofielgebeurtenisgegevens](#time-series-profile-event-data) voor meer informatie over het toevoegen van profielspecifieke velden.

1. Als u nog geen schema hebt, [maken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#create) met de klasse ingesteld op **Experience Event**.

1. [Toevoegen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#add-field-groups) de volgende handel-specifieke gebiedsgroepen (of geef uw bestaand schema uit en voeg deze gebiedsgroepen toe):

   - Zoeken op site
   - Webpagina bezoeken
   - Aanmeldingsproces gebruiker
   - Referentietoetsen
   - Persoonlijke contactgegevens
   - Kanaaldetails
   - Handelsgegevens
   - Adobe Analytics ExperienceEvent Commerce (als u gegevens naar Adobe Analytics wilt verzenden)

   >[!NOTE]
   >
   > Stel geen specifieke handelsgroepen in als `Primary identity`. Hierbij wordt het veld naar wens geïdentificeerd en het Experience Platform verwacht dat veld in elke gebeurtenis. Als dat veld ontbreekt, mislukt het invoeren van gegevens.

   Uw schema bevat nu Commerce-specific gebiedsgroepen zodat de tijdreeksgegevens die van de Handel worden verzameld [gedrag](events.md) en [achterkantoor](events-backoffice.md) gebeurtenissen worden weergegeven in het schema.

1. [Inschakelen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#profile) het schema voor Profiel.

   Wanneer een schema voor Profiel wordt toegelaten, nemen om het even welke datasets die van dit schema worden gecreeerd aan Real-Time CDP deel, die gegevens uit ongelijksoortige bronnen samenvoegt om een volledige mening van elke klant te construeren.

1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt of bijgewerkt.

   Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan.

1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) en selecteer het schema dat de handel-specifieke gebiedsgroepen en de overeenkomstige dataset bevat.

   De gegevensstroom door:sturen de verzamelde gegevens aan de dataset. De gegevens worden vertegenwoordigd in de dataset die op het geselecteerde schema wordt gebaseerd.

1. **Beta** (Optioneel) U kunt aangepaste kenmerken gebruiken als u aangepaste gegevens van Office-gebeurtenissen van uw instantie Commerce wilt doorgeven aan het Experience Platform. Deze functie is in bèta. Als u wilt deelnemen aan het bètaprogramma, verzendt u een aanvraag naar [dataconnection@adobe.com](mailto:dataconnection@adobe.com). Neem het volgende op in uw verzoek:

   - Uw [Adobe-id](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). Bijvoorbeeld `organization_id@AdobeOrg`.
   - Lijst met aangepaste kenmerken op bestelniveau.
   - Lijst met kenmerken voor het niveau Volgitem.

   Het Adobe Commerce-team zal contact met u opnemen voor meer informatie en volgende stappen.

Met de schema&#39;s, datasets, en gegevensstromen die voor gedrags en achterkantoorgegevens worden gevormd, kunt u [vormen](connect-data.md#data-collection) uw instantie van de Handel om die gegevens te verzamelen en te verzenden naar het Experience Platform.

Raadpleeg de volgende sectie voor meer informatie over het profiel van uw klant.

## Gebeurtenisgegevens tijdreeksprofiel

>[!NOTE]
>
>Deze functie is in bèta. Als u wilt deelnemen aan het bètaprogramma, verzendt u een aanvraag naar [dataconnection@adobe.com](mailto:dataconnection@adobe.com).

De gebeurtenisgegevens van het tijdreeksprofiel worden gegenereerd uit de volgende gebeurtenissen:

- [` accountCreated`](events-backoffice.md#accountcreated)
- [` accountUpdated`](events-backoffice.md#accountupdated)
- [` accountDelette`](events-backoffice.md#accountdeleted)

Als u de gegevens van de het profielgebeurtenis van uw klant in het Experience Platform wilt opnemen, kunt u uw bestaand schema van de Handel bijwerken en de zelfde reeds gevormde gegevensstroom gebruiken, of u kunt een profiel-specifieke gegevensstroom en schema tot stand brengen. Dat besluit is gebaseerd op het gegevensbeheer van uw bedrijf. De volgende twee secties lopen u door beide gevallen.

### Verzend tijdreeksprofielgebeurtenisgegevens naar Experience Platform met behulp van uw bestaande gegevensstroom

Als u een tijdreeks wilt toevoegen [server-side profielgebeurtenisgegevens](events-backoffice.md#customer-profile-events-server-side) aan uw bestaande gegevensstroom van de Handel, voeg toe `Demographic Details` veldgroep aan uw schema. Uw schema bevat nu de volgende handel-specifieke gebiedsgroepen:

- Zoeken op site
- Webpagina bezoeken
- Aanmeldingsproces gebruiker
- Referentietoetsen
- Persoonlijke contactgegevens
- Kanaaldetails
- Handelsgegevens
- Adobe Analytics ExperienceEvent Commerce (als u gegevens naar Adobe Analytics wilt verzenden)
- Nieuw: **Demografische details**

Met toevoeging van de `Demographic Details` de gebiedsgroep in uw bestaand schema van de Handel, wordt de dataset en de gegevensstroom reeds verbonden aan uw schema van de Handel gebruikt voor deze gegevens van het tijdreeksprofiel.

### Gebeurtenisgegevens van tijdreeksprofiel naar Experience Platform verzenden in een aparte gegevensstroom

Als u wilt toevoegen [server-side profielgebeurtenisgegevens](events-backoffice.md#customer-profile-events-server-side) Voer de volgende stappen uit voor een nieuwe profielspecifieke gegevensstroom en een nieuw schema.

1. [Maken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#create) een schema en stel de klasse in op **Experience Event**.

1. [Toevoegen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#add-field-groups) de volgende profielspecifieke veldgroepen:

   - Demografische details
   - Persoonlijke contactgegevens
   - Kanaaldetails
   - Handelsgegevens

1. [Inschakelen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#profile) het schema voor Profiel.

   Wanneer een schema voor Profiel wordt toegelaten, nemen om het even welke datasets die van dit schema worden gecreeerd aan Real-Time CDP deel, die gegevens uit ongelijksoortige bronnen samenvoegt om een volledige mening van elke klant te construeren.

1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt.

   Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan.

1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) en selecteer het schema XDM dat de handel-specifieke gebiedsgroepen en de overeenkomstige dataset bevat.

   De gegevensstroom door:sturen de verzamelde gegevens aan de dataset. De gegevens worden vertegenwoordigd in de dataset die op het geselecteerde schema wordt gebaseerd.

Met de schema&#39;s, datasets, en gegevensstromen die voor de gegevens van het klantenprofiel worden gevormd, kunt u [vormen](connect-data.md#data-collection) uw instantie van de Handel om die gegevens te verzamelen en te verzenden naar Experience Platform.

Als u een schema, gegevensset en gegevensstroom voor profielrecordgegevens wilt maken, raadpleegt u [profielrecordgegevens naar het Experience Platform verzenden](profile-data.md).
