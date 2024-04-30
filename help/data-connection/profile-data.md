---
title: Profielrecordschema bijwerken voor Commerce-gegevensinsluiting
description: Leer hoe u een schema, gegevensset en gegevensstroom maakt voor het verzamelen en verzenden van Commerce-profielrecordgegevens naar het Experience Platform.
role: Admin, Developer
feature: Personalization, Integration
exl-id: 86a3ba12-7f26-4f7e-98a0-9af0d1d8d881
source-git-commit: 813be62b366b1c76a2b909079cfba31ef8000617
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Profielrecordschema bijwerken voor Commerce-gegevensinsluiting (bèta)

Wanneer uw klanten een profiel op uw Commerce-site maken, wordt een profielrecord gemaakt en worden gegevens vastgelegd. U moet een schema en een dataset tot stand brengen specifiek voor dat profielverslag alvorens u die profielgegevens aan het Experience Platform kunt stromen.

1. [Maken](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas) een schema en stel de klasse in op **Individueel profiel**.

1. [Toevoegen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas) de volgende profielspecifieke veldgroepen:

   - identityMap
   - Demografische details
   - Persoonlijke contactgegevens
   - Gebruikersaccountgegevens

1. [Inschakelen](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas) het schema voor Profiel.

   Wanneer een schema voor Profiel wordt toegelaten, nemen om het even welke datasets die van dit schema worden gecreeerd aan Real-Time CDP deel, die gegevens uit ongelijksoortige bronnen samenvoegt om een volledige mening van elke klant te construeren.

1. [Een gegevensset maken](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform) op basis van het schema dat u hebt gemaakt of bijgewerkt.

   Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan.

1. Een [aangepaste naamruimte](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces#create-namespaces) in Experience Platform met de volgende waarden:

   - **Weergavenaam**: _Commerce Customer ID_
   - **Identiteitssymbool**: _CustomerId_
   - **Type**: _Individuele apparaat-id_

   ![Aangepaste naamruimte maken](assets/custom-namespace.png){width="700" zoomable="yes"}

   Klik op **[!UICONTROL Create]**. Een aangepaste naamruimte wordt door de Unified Profile Service gebruikt om profielfragmenten aan elkaar te koppelen.

Met het schema, de dataset, en de ruimte van de douanenaam die voor de gegevens van het het profielverslag van de klant wordt gevormd, kunt u [vormen](connect-data.md#data-collection) uw Commerce-exemplaar om die gegevens te verzamelen en naar het Experience Platform te verzenden.

Om een schema, dataset, en gegevensstroom voor gedrags en achterkantoorgebeurtenisgegevens tot stand te brengen, zie [gebeurtenisschema&#39;s voor tijdreeksen bijwerken voor Commerce-gegevensinvoer](update-xdm.md).
