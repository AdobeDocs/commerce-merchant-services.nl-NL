---
title: Productvoorraadbeheer
description: Vorm het commerciële voorraadoverseinen en de eigenschappen beschikbaar aan klanten.
role: User, Admin
level: Intermediate
exl-id: 3ac217f7-e823-4578-8416-5ecceb76aa87
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Productvoorraadbeheer

Als verkoper kun je Adobe Commerce gebruiken [Inventory management](https://docs.magento.com/user-guide/catalog/inventory-management.html) voorraad- en bronopties. Bovendien kunt u andere opties voor voorraadbeschikbaarheid instellen met betrekking tot uw winkelactiviteiten met de Opslagoplossing.

- Optie voor thuislevering uit Merchant-winkels

- Toestaan / Beschikbaar voor ophalen van winkel

- UPC / SKU / Andere unieke product-id&#39;s

- Drempel voor voorraden

- Het verminderen van Inventaris van specifieke plaatsen op orde

Opties voor productvoorraad configureren van de beheerder: **[!UICONTROL Catalog > Products > Select Product]**

## **Opties voor productvoorraad**

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|--------------|
| **Beschikbaar voor thuislevering** | Hiermee stelt u de beschikbaarheid van Home Delivery (Ship-from-Store) voor het product in. Als deze optie is ingeschakeld, worden alle toegewezen winkellocaties met een beschikbare voorraad voor het product in aanmerking genomen voor de optie Home Delivery. Als het product is uitgeschakeld, komt het nooit in aanmerking voor thuislevering, zelfs niet als een winkel een voorraad heeft.</br></br>In de meeste gevallen is het voldoende deze optie in te stellen op winkelniveau. Er kunnen zich echter unieke gevallen voordoen voor specifieke producten, zoals producten waarvoor een federale scheepvaartbeperking geldt, die niet in aanmerking mogen komen voor thuislevering. | Website | Nee |
| **[!UICONTROL Available for Store Pickup]** | Stel de beschikbaarheid van de Ophaalservice voor het product in. Als deze optie is ingeschakeld, worden toegewezen winkellocaties met een beschikbare voorraad voor het product in aanmerking genomen voor de optie Ophalen uit winkel. Als het product is uitgeschakeld, komt het nooit in aanmerking voor Ophalen uit de winkel, zelfs niet als een winkel een voorraad heeft.</br></br>Deze optie kan handig zijn in gevallen waarin u de inventaris van winkels bijhoudt in het systeem, maar u wilt deze niet via het e-commercekanaal verkopen. | Website | Nee |
| **[!UICONTROL UPC / SKU / Custom Scannable Identifier]** | Dit kenmerk zou al als een productkenmerk moeten bestaan en heeft betrekking op **[!UICONTROL Barcode Source / Barcode Type]** instellen. Dit kenmerk wordt gebruikt om een gescande streepjescode voor uw producten bij te houden. Deze waarde kan worden verzonden wanneer een bestelling voor het selecteren naar uw winkels wordt verzonden. De associaties van de opslag kunnen de waarde met de pluklijst gebruiken om producten op de plank aan te passen gebruikend een streepjescodescanner. | Winkelweergave | Nee |

{style=&quot;table-layout:auto&quot;}

## Bronnen voor inventarisatie op productniveau

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Out of Stock Threshold]** | Stel de voorraaddrempel voor het item binnen elke bron in. Wanneer de voorraad onder de drempel daalt, wordt deze als niet-voorraad aan de bron beschouwd.</br></br>Als u de globale instelling voor Winkelconfiguratie wilt gebruiken, schakelt u het selectievakje **[!UICONTROL Use Default]** optie. | Algemeen | Nee |
| **[!UICONTROL Allow Store Pickup]** | Expliciet instellen of het item beschikbaar is voor het ophalen van de winkel, ongeacht de beschikbare voorraad of configuratie van de locatie van de winkel.</br></br> Schakel de optie [!UICONTROL Use Default] en maakt u uw selectie. Anders wordt deze instelling gekozen op basis van de configuratie voor **[!UICONTROL Allow In-Store Pickup]** die op de bron van de voorraad is vastgesteld. | Algemeen | Nee |

{style=&quot;table-layout:auto&quot;}

