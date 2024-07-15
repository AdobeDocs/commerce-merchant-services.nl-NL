---
title: Configuratie van meerdere websites en bereik
description: Configureer voorraden en leveringsmethoden voor meerdere websites en sla het bereik op.
role: Admin
level: Experienced
feature: Shipping/Delivery, Inventory, Configuration
exl-id: 8939046e-1c26-4380-83be-ff8e074e591d
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# Configuratie van meerdere websites en bereik

U kunt het [ Reikwijdte ](https://docs.magento.com/user-guide/configuration/scope.html) voor een paar elementen plaatsen om veelvoudige websites, opslag, en opslagmeningen aan te passen:

- [ beheer Voorraad ](https://docs.magento.com/user-guide/catalog/inventory-stock.html) per werkingsgebied

- [!DNL Delivery Methods] beheren per bereik

U kunt voorraad toewijzen aan een website of opslagbereik. Werk vervolgens opslagbronnen bij om beschikbare leveringsmethoden in te stellen (levering thuis, ophalen bij de winkel).

Nadat de configuratie met succes is bijgewerkt, kunnen de opties voor het ophalen van de winkel op de pagina met productdetails (PDP) in de Adobe Commerce-winkel alleen worden geselecteerd voor producten die beschikbaar zijn vanuit een voorraadbron die het ophalen van de winkel toestaat.

## In-Store ophalen-instellingen beheren

Laat of maak de [!UICONTROL In-Store Pickup] opties voor elke website of opslagwerkingsgebied van de [ Configuraties van de Methode van de Levering ](enable-general.md#delivery-methods) in Admin toe onbruikbaar.

1. Navigeer naar **[!UICONTROL Stores > Configuration]** .

1. Selecteer het bereik (op te slaan website) dat u wilt configureren.

1. Blader naar **[!UICONTROL Sales > Delivery Methods]** terwijl het bereik is geselecteerd.

1. Schakel de methode **[!UICONTROL In-Store Pickup]** Delivery uit of in.

U kunt ook bepalen of curbside of in-store oppikken algemeen beschikbaar is in deze sectie.

De instellingen [!UICONTROL In-Store Pickup] en [!UICONTROL Delivery Method] per aandelenbron beheren. Er zijn vele andere configuraties die volledige flexibiliteit bieden met betrekking tot uw implementatie.
