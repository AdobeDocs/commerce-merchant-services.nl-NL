---
title: Profielrecordschema bijwerken voor gegevensinsluiting voor handel
description: Leer hoe te om een schema, dataset, en gegevensstroom tot stand te brengen om de gegevens van het het profielverslag van de Handel te verzamelen en te verzenden naar het Experience Platform.
role: Admin, Developer
feature: Personalization, Integration
source-git-commit: 99d1097b98ea18c8a317613b2366a97db131432f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Profielrecordschema bijwerken voor gegevensinsluiting voor handel

Wanneer uw kopers een profiel maken op uw Commerce-site, wordt een profielrecord gemaakt en worden gegevens vastgelegd. U moet een schema en een dataset tot stand brengen specifiek voor dat profielverslag alvorens u die profielgegevens aan het Experience Platform kunt stromen.

1. [Maken](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#create) een schema en stel de klasse in op **Individueel profiel**.

1. [Toevoegen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#add-field-groups) de volgende profielspecifieke veldgroepen:

   - identityMap
   - Demografische details
   - Persoonlijke contactgegevens
   - Gebruikersaccountgegevens

1. [Inschakelen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#profile) het schema voor Profiel.

   Wanneer een schema voor Profiel wordt toegelaten, nemen om het even welke datasets die van dit schema worden gecreeerd aan Real-Time CDP deel, die gegevens uit ongelijksoortige bronnen samenvoegt om een volledige mening van elke klant te construeren.

1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt of bijgewerkt.

   Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan.

Met het schema en de dataset die voor de gegevens van het het profielverslag van de klant wordt gevormd, kunt u [vormen](connect-data.md#data-collection) uw instantie van de Handel om die gegevens te verzamelen en te verzenden naar Experience Platform.

Om een schema, dataset, en gegevensstroom voor gedrags en achterkantoorgebeurtenisgegevens tot stand te brengen, zie [de gebeurtenisschema&#39;s van de updatetijdreeks voor de gegevensopname van de Handel](update-xdm.md).
