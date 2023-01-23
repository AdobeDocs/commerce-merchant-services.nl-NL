---
title: Shopper-profielen uploaden naar Adobe Experience Platform
description: Leer hoe u verkoopprofielen uploadt naar Adobe Experience Platform.
exl-id: fd0ee7fa-5274-4640-ba00-bcb2ec78f314
source-git-commit: 9bf28159fdac3a7237956a536f6a522b4e2918fe
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Winkelprofiel uploaden naar Adobe Experience Platform

Adobe Commerce-handelaren kunnen klantprofielgegevens uploaden naar [Klantprofiel in realtime](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html), die deel uitmaakt van Adobe Experience Platform. Het profiel staat u toe om uw klantengegevens in een verenigde mening te consolideren, die een actionable en timestamped rekening van elke klanteninteractie aanbiedt.

>[!NOTE]
>
> Profielgegevens moeten een e-mailadres bevatten, omdat op die manier de koppeling wordt gemaakt tussen een winkelier en hun gedragsgegevens voor het winkelgedrag.

Nadat u de profielen van uw winkels hebt geüpload, worden de gebeurtenisgegevens die zijn gekoppeld aan de interacties die uw klanten op uw site uitvoeren, via de aansluiting voor het Experience Platform naar Profiel verzonden en gekoppeld aan het profiel van die klant.

>[!NOTE]
>
> De `createAccount` [storefront, gebeurtenis](events.md) maakt niet automatisch een klantprofiel in Profiel. Dit is om veiligheidsredenen beperkt en is opzettelijk.

In dit onderwerp leert u hoe u uw Adobe Commerce-klantprofielen kunt uploaden naar Real-time klantprofiel in Experience Platform.

1. Bepaal waar u uw klantgegevens opslaat. Voor sommige handelaren worden deze gegevens opgeslagen in Adobe Commerce en kunnen ze [geëxporteerd](https://docs.magento.com/user-guide/system/data-export.html) als een CSV-bestand. Voor anderen kan het in een afzonderlijk systeem van het de relatiebeheer van de Klant (CRM) zijn.

1. Nadat u hebt bepaald waar u uw klantgegevens opslaat, vindt u de juiste [bronaansluiting](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html) op basis van waar de klantgegevens zijn opgeslagen. Als u geen aangewezen bronschakelaar ziet, dan gebruik [lokaal bestand uploaden](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload.html) en importeer uw winkelprofielen vanuit een CSV-bestand.

   >[!NOTE]
   >
   > Als u de lokale verbinding voor het uploaden van bestanden gebruikt, moet u de **Profielgegevensset** optie wanneer [het bepalen van de dataset](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload.html#use-an-existing-dataset). Dit identificeert de dataset als profielgegevens.

Nadat u de verkoopprofielen in Profiel hebt gemaakt, worden alle aan die winkelbezoeker gekoppelde opslaggegevens aan het profiel gekoppeld.

## Profielen vaak uploaden

Voor een verbeterde verkoopervaring moet u regelmatig profielgegevens importeren. Met sommige bronconnectors kunt u profielgegevens volgens een schema importeren.
