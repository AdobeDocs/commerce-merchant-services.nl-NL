---
title: Configureren in het dashboard
description: Na installatie kunt u configureren [!DNL Payment Services] in het dashboard.
role: Admin, User
level: Intermediate
exl-id: 015c5c8c-8184-45c1-932a-f4365ddf5a30
source-git-commit: bae0eeac349fe3c266d868f8d94c5e033390a661
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---

# Configureren in het dashboard

U kunt [!DNL Payment Services] aan uw behoeften met nuttige configuratieopties in het dashboard.

Wanneer u op [!UICONTROL Settings] in het dashboard, kunt u snel vormen [!DNL Payment Services] voor Adobe Commerce en Magento Open Source. Deze configuratieopties zijn alleen van toepassing op de omgeving die is ingesteld in het dialoogvenster [!UICONTROL Payment mode] in de Algemene instellingen.

Zie de [[!UICONTROL General] instellingensectie](#general-settings) voor meer informatie .

>[!IMPORTANT]
>
> Voor multi-store of erfenisconfiguratie, verwijs naar [Configureren in de beheerder](configure-admin.md) onderwerp.

## Betalingsservices configureren

U kunt [!DNL Payment Services] voor uw website en schakel het testen van sandboxen of live betalingen in het dialoogvenster [!UICONTROL General] instellingensectie.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Dashboardweergave](assets/payment-services-menu-small.png)

1. Klik op het dashboard op **[!UICONTROL Settings]** rechtsboven op de pagina.

   De _[!UICONTROL General]_sectie bevat de configuratieopties die worden gebruikt om [!DNL Payment Services] als betalingsmethode.

1. Voor de schakeloptie bovenaan (**[!UICONTROL Enable Payment Services as payment method]**), instellen op `Yes` om [!DNL Payment Services] voor uw website.

1. Voor **Betalingsmodus**, stelt u deze in op `Sandbox` als u nog test [!DNL Payment Services] voor uw winkel of `Production` als u bereid bent om levende betalingen toe te laten.

   >[!WARNING]
   >
   >Uw [!UICONTROL Sandbox Merchant ID] en [!UICONTROL Production Merchant ID] automatisch worden gegenereerd en aanwezig zijn in de betreffende velden als u klaar bent met het aan boord nemen voor de sandbox en/of productie. Verwijder of wijzig deze id&#39;s niet.

1. Als u de standaardinstellingen voor betalingsfuncties en de weergave van de winkel wilt wijzigen, stelt u de gewenste aanvullende opties in:

   - [Creditcardvelden](#credit-card-fields)
   - [Slimme PayPal-knoppen](#paypal-smart-buttons)
   - [Knopstijl](#button-style)

1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Creditcardvelden

De [!UICONTROL Credit Card Fields] betaalopties bieden een eenvoudige en veilige afhandeling van betalingsmethoden met een creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

1. Voor **[!UICONTROL Checkout title]** Voer (indien nodig) tekst in om de naam te wijzigen van de betalingsmethode die tijdens het afrekenen wordt weergegeven.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. Voor **[!UICONTROL Debug Mode]**, schakelt u de kiezer in om de foutopsporingsmodus in te schakelen.
1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Slimme PayPal-knoppen

De [!DNL PayPal Smart Buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant. Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

U kunt de betalingsopties voor slimme PayPal-knoppen inschakelen in het dashboard:

1. Als u de naam van de betalingsmethode wilt wijzigen, zoals wordt weergegeven tijdens het afrekenen, bewerkt u de waarde in het dialoogvenster **[!UICONTROL Checkout Title]** veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. De schakelkiezers gebruiken om in of uit te schakelen [!DNL PayPal smart button] weergavefuncties:
   - **[!UICONTROL Show buttons on product detail page]**
   - **[!UICONTROL Show buttons in mini cart preview]**
   - **[!UICONTROL Show buttons on cart page]**
   - **[!UICONTROL Show Venmo button]**.
   - **[!UICONTROL PayPal Pay Later enabled]** om de optie in te schakelen om de knop tijdens het afrekenen weer te geven.

1. Als u het dialoogvenster [Later betalen](payments-options.md#pay-later-button) (indien gewenst), schakelt u de **[!UICONTROL Display Pay Later message]** optie.
1. Als u de foutopsporingsmodus wilt inschakelen, klikt u op **[!UICONTROL Debug Mode]**,
1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Knopstijl

U kunt ook de _[!UICONTROL Button style]_opties van de slimme PayPal-knoppen in het dashboard:

1. Als u het dialoogvenster **[!UICONTROL Layout]**, selecteert u `Vertical` of `Horizontal`.
1. Als u de coderegel in een horizontale lay-out wilt inschakelen, klikt u op **[!UICONTROL Show tagline]**.
1. Als u de **[!UICONTROL Color]** selecteert u de gewenste kleuroptie.
1. Als u het dialoogvenster **[!UICONTROL Shape]**, selecteert u `Pill` of `Rect`.
1. Klik op **[!UICONTROL Responsive button height]**.
1. Als u de **[!UICONTROL Label]** selecteert u de gewenste labeloptie.
1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

U kunt configureren [!DNL PayPal Smart Buttons] opmaken in Beheer of het dashboard. Zie [Stijlgids voor PayPal-knoppen](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) voor meer informatie .
