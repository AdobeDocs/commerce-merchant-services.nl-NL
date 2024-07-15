---
title: Configuratie van opslaglocatie en toewijzingssysteem
description: Vorm een afstandsleverancier om de afbeelding van de opslagplaats in storefront UI te steunen. De oplossingen van de Afhandeling van de Opslag vereisen een afstandsleverancier om detailhandel onderzoek en andere afbeelding en het plannen mogelijkheden voor het volledige uitvoeringswerkschema toe te laten.
role: Admin
level: Intermediate
feature: Shipping/Delivery, Integration, Tools and External Services, Configuration
exl-id: d09c4652-e2eb-49dc-8c42-2aa9b6be5d6b
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 1%

---

# Opslaglocatie en Toewijzing instellen

Laat de opslagplaats en de afbeeldingsmogelijkheden voor de Afhandeling van de Opslag toe door a [ afstandsleverancier ](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html) te vormen om naar kleinhandelsopslagplaatsen te zoeken.

**Vereisten**

Tijdens het configuratieproces geeft u een Google API-sleutel op voor het Google Maps-platform. Als u geen hebt, [ produceert één van het platform van Kaarten van Google ](https://docs.magento.com/user-guide/catalog/inventory-configure-distance-priority.html#configure-google-maps).

Om de afstandsleverancier te vormen:

1. Voeg in de configuratie **[!UICONTROL Stores > General]** in Beheer de integratie Google Maps toe voor het inhoudstype Kaart.

   - Ga naar **[!UICONTROL Stores > Configuration  > General > Content Management]** .

   - Voeg uw Google API-sleutel toe aan het veld **[!UICONTROL Google Maps API Key]** .

1. Selecteer in de configuratie **[!UICONTROL Stores > Inventory]** in de beheerfunctie de afstandprovider voor Afhandeling opslaan.

   - Ga naar **[!UICONTROL Stores > Configuration > Catalog > Inventory]** .

   - Vouw de sectie **[!UICONTROL Distance Provider for Distance Based SSA]** uit.

   - Plaats de **Leverancier** aan **Kaart van Google**.

1. Configureer instellingen voor de **[!UICONTROL Google Distance Provider]** .

   - Voeg uw **sleutel van Google API** toe.

   - Stel **[!UICONTROL Computation Mode]** in op `Driving` en **[!UICONTROL Value]** op `Distance`
