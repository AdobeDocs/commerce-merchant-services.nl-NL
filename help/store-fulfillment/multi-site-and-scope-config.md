---
title: Meerdere website- en bereikconfiguratie
description: Configureer voorraden en leveringsmethoden voor meerdere websites en sla het bereik op.
role: User, Admin
level: Intermediate
source-git-commit: 42b0118b427b1e04186793b4a57c058bc1cabdd4
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 1%

---


# Meerdere website- en bereikconfiguratie

U kunt de [Toepassingsgebied](https://docs.magento.com/user-guide/configuration/scope.html) voor een paar elementen om veelvoudige websites, opslag, en opslagmeningen aan te passen:

- [Stock beheren](https://docs.magento.com/user-guide/catalog/inventory-stock.html) per bereik

- Beheren [!DNL Delivery Methods] per bereik

U kunt voorraad toewijzen aan een website of opslagbereik. Werk vervolgens opslagbronnen bij om beschikbare leveringsmethoden in te stellen (levering thuis, ophalen bij de winkel).

Nadat de configuratie met succes is bijgewerkt, kunnen de opties voor het ophalen van de winkel op de pagina met productdetails (PDP) in de Adobe Commerce-winkel alleen worden geselecteerd voor producten die beschikbaar zijn vanuit een voorraadbron die het ophalen van de winkel toestaat.

## In-Store ophalen-instellingen beheren

Schakel de [!UICONTROL In-Store Pickup] opties voor elke website of opslagbereik uit de [Configuraties van leveringsmethoden](enable-general.md#delivery-methods) in de Admin.

1. Ga naar **[!UICONTROL Stores > Configuration]**.

1. Selecteer het bereik (op te slaan website) dat u wilt configureren.

1. Met geselecteerd bereik navigeert u naar **[!UICONTROL Sales > Delivery Methods]**.

1. Schakel het dialoogvenster **[!UICONTROL In-Store Pickup]** Leveringsmethode.

U kunt ook bepalen of curbside of in-store oppikken algemeen beschikbaar is in deze sectie.

De [!UICONTROL In-Store Pickup] en [!UICONTROL Delivery Method] instellingen per voorraadbron. Er zijn vele andere configuraties die volledige flexibiliteit bieden met betrekking tot uw implementatie.
