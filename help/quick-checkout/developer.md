---
title: "[!DNL Quick Checkout] voor Adobe Commerce Developer Information"
description: "[!DNL Quick Checkout] ontwikkelaarsinformatie."
exl-id: 8926eda4-b4de-4938-a86c-b095616f61f6
feature: Checkout, Services
role: Developer
source-git-commit: b1984a26463e14b8dc9a789421e49e5ea81ad039
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# [!DNL Quick Checkout] Informatie over ontwikkelaar

Dit onderwerp bevat informatie voor ontwikkelaars die nauw samenwerken met Adobe Commerce en [!DNL Magento Open Source] code en wil gedetailleerde informatie over [!DNL Quick Checkout] extensie.

## Extensiepunten

De extensiepunten gebruiken om de [!DNL Quick Checkout].

Door extensiepunten te gebruiken, kunt u aanpassingen maken zonder de kerncomponenten in de toepassingscode te wijzigen.

## Verzenddetails, stap

Een extensiepunt kan worden gebruikt om de automatische stapnavigatie aan te passen nadat u zich hebt aangemeld met [!DNL Bolt].

Zodra een winkel zich aanmeldt met [!DNL Bolt]Alle geldige gegevens worden vooraf ingevuld en doorgestuurd naar de stap met de betalingsgegevens om de bestelling te plaatsen. Zie de [uitcheckstroom](https://experienceleague.adobe.com/docs/commerce-merchant-services/quick-checkout/manage-checkout/checkout-flow.html) voor meer informatie.

Met dit extensiepunt kunt u navigatie naar een betalingsstap voorkomen. Dit kan handig zijn als er extensies zijn waarvoor een winkelier aanvullende acties moet uitvoeren op de verzendstap. Zie een voorbeeld hieronder over hoe u het uitbreidingspunt met een mixin kunt gebruiken:

1. Een nieuwe mix registreren in het dialoogvenster `require-config.js` bestand in `app/code/Vendor/ModuleName/view/frontend/`.

   ```js
   var config = {
       config: {
           mixins: {
               "Magento_ExpressCheckout/js/model/can-navigate-to-payment": {
                   "Vendor/ModuleName/js/model/can-navigate-to-payment-mixin": true
               }
           }
       }
   };
   ```

1. Het model in het deelvenster `can-navigate-to-payment.js` bestand in `app/code/Vendor/ModuleName/view/frontend/web/js/model/`.

   ```js
   define([
       'Magento_Checkout/js/model/quote',
       'mage/utils/wrapper',
   ], function (quote, wrapper) {
       'use strict';
       return function (canNavigateToPayment) {
           return wrapper.wrap(canNavigateToPayment, function (originalAction) {
               /* Include custom checks or conditions to stay on the shipping step,i.e: your shopper is from Germany */
               return originalAction() && quote.shippingAddress().countryId !== 'DE');
           });
       };
   });
   ```

>[!WARNING]
>
> Dit is een voorbeeld voor een winkelier in Duitsland (DE) die op de stap Verzenddetails wil blijven.

Controleren [[!DNL Bolt] Help bij ontwikkelaars](https://help.bolt.com/developers/) voor meer informatie over [!DNL Bolt] voor ontwikkelaars.
