---
title: Configuratie van opslaglocatie en toewijzingssysteem
description: Vorm een afstandsleverancier om de afbeelding van de opslagplaats in storefront UI te steunen. De oplossingen van de Afhandeling van de Opslag vereisen een afstandsleverancier om detailhandel onderzoek en andere afbeelding en het plannen mogelijkheden voor het volledige uitvoeringswerkschema toe te laten.
role: Admin
level: Intermediate
feature: Shipping/Delivery, Integration, Tools and External Services, Configuration
exl-id: d09c4652-e2eb-49dc-8c42-2aa9b6be5d6b
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Opslaglocatie en Toewijzing instellen

Schakel de locatie en toewijzingsmogelijkheden van de winkel in voor de uitvoering van de winkel door een [afstandsprovider](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html) om naar winkellocaties te zoeken.

**Vereisten**

Tijdens het configuratieproces geeft u een Google API-sleutel op voor het Google Maps-platform. Als u er geen hebt, [genereren op het Google Maps-platform](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html#configure-google-maps).

Om de afstandsleverancier te vormen:

1. Van de **[!UICONTROL Stores > General]** Voeg in de beheerfunctie de integratie Google Maps toe voor het inhoudstype Kaart.

   - Ga naar **[!UICONTROL Stores > Configuration  > General > Content Management]**.

   - Google API-sleutel toevoegen aan **[!UICONTROL Google Maps API Key]** veld.

1. Van de **[!UICONTROL Stores > Inventory]** Selecteer in de beheerdersinterface de afstandprovider voor Afhandeling opslaan.

   - Ga naar **[!UICONTROL Stores > Configuration > Catalog > Inventory]**.

   - Breid uit **[!UICONTROL Distance Provider for Distance Based SSA]** sectie.

   - Stel de **Provider** tot **Google Map**.

1. Configureer instellingen voor de **[!UICONTROL Google Distance Provider]**.

   - Voeg uw **Google API-sleutel**.

   - Set **[!UICONTROL Computation Mode]** tot `Driving` en **[!UICONTROL Value]** tot `Distance`
