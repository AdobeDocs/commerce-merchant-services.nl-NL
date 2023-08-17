---
title: Void
description: Met biedingen kunt u de middelen vrijmaken op een creditcard- of bankcreditcardrekening die door een machtiging voor het bedrag van een aankoop zijn geblokkeerd of opzij worden gehouden.
exl-id: 029a7038-2812-46ce-b188-929a7a758d89
feature: Payments, Checkout
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Void

Met [!DNL Payment Services], kunt u bestaande Commerce-functionaliteit gebruiken voor het blokkeren van transacties. Met biedingen kunt u de middelen vrijmaken op een creditcard- of bankcreditcardrekening die door een machtiging voor het bedrag van een aankoop zijn geblokkeerd of opzij worden gehouden.

>[!NOTE]
>
>U kunt een transactie alleen annuleren als de betaling nog niet is vastgelegd.

Als uw winkel [geconfigureerd](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} als u alleen fondsen (zonder opname) wilt toestaan op het verkooppunt, resulteert een aankoop in een bestelling met een `Processing` status in de Commerce Admin.

U kunt [een bestelling annuleren](https://docs.magento.com/user-guide/sales/order-update.html#cancel-a-pending-order){target="_blank"} dat niet wordt gefactureerd. Eventuele niet-vastgelegde machtigingen worden ook ingetrokken als onderdeel van dat annuleringsproces.

>[!NOTE]
>
>Als u een bestelling annuleert, resulteert dit ook in een &#39;void&#39;, maar het annuleren van een bestelling leidt niet tot annulering.

Als u meer wilt weten over de basisstappen die een bestelling doorloopt, raadpleegt u de [Workflow voor bestellen](https://docs.magento.com/user-guide/sales/order-workflow.html){target="_blank"} onderwerp in de kernGebruikershandleiding.

Ga voor meer informatie over de functie void en hoe u een ordertransactie kunt voorkomen naar [Een bestelling verwerken](https://docs.magento.com/user-guide/sales/order-processing.html){target="_blank"} in de basisgebruikershandleiding.
