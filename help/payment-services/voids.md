---
title: Void
description: Met biedingen kunt u de middelen vrijmaken op een creditcard- of bankcreditcardrekening die door een machtiging voor het bedrag van een aankoop zijn geblokkeerd of opzij worden gehouden.
exl-id: 029a7038-2812-46ce-b188-929a7a758d89
feature: Payments, Checkout
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Void

Met [!DNL Payment Services] kunt u bestaande Commerce-functionaliteit gebruiken om transacties te blokkeren. Met biedingen kunt u de middelen vrijmaken op een creditcard- of bankcreditcardrekening die door een machtiging voor het bedrag van een aankoop zijn geblokkeerd of opzij worden gehouden.

>[!NOTE]
>
>U kunt een transactie alleen annuleren als de betaling nog niet is vastgelegd.

Als uw opslag [ ](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions) {target="_blank"} wordt gevormd om slechts (niet vangst) middelen op het punt van verkoop toe te staan, resulteert een aankoop van uw opslag in een orde met een `Processing` status in Commerce Admin.

U kunt [ ook annuleren een orde ](https://docs.magento.com/user-guide/sales/order-update.html#cancel-a-pending-order) {target="_blank"} die niet wordt gefactureerd. Eventuele niet-vastgelegde machtigingen worden ook ingetrokken als onderdeel van dat annuleringsproces.

>[!NOTE]
>
>Als u een bestelling annuleert, resulteert dit ook in een &#39;void&#39;, maar het annuleren van een bestelling leidt niet tot annulering.

Meer over de basisstappen leren en de orde gaat door, zie het [ Werkschema van de Orde ](https://docs.magento.com/user-guide/sales/order-workflow.html) {target="_blank"} onderwerp in de gids van de kerngebruiker.

Om over de leegte functionaliteit te leren en hoe te om een ordetransactie te ontdoen, zie [ Verwerking een Orde ](https://docs.magento.com/user-guide/sales/order-processing.html) {target="_blank"} in de gids van de kerngebruiker.
