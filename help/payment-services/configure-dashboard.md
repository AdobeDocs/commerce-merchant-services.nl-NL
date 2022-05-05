---
title: Configureren in het dashboard
description: After installation, you can configure [!DNL Payment Services] in the dashboard.
role: Admin, User
level: Intermediate
exl-id: 015c5c8c-8184-45c1-932a-f4365ddf5a30
source-git-commit: 44e97a0299e980656aef557eb5c2bac9b6443452
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Configureren in het dashboard

U kunt [!DNL Payment Services] aan uw behoeften met nuttige configuratieopties in het dashboard.

Wanneer u op [!UICONTROL Settings] in het dashboard, kunt u snel vormen [!DNL Payment Services] voor Adobe Commerce en Magento Open Source. These configuration options apply only to the environment that is set in the [!UICONTROL Payment mode] field in the General settings.

Zie de [[!UICONTROL General] instellingensectie](#general-settings) voor meer informatie .

>[!IMPORTANT]
>
> Voor multi-store of erfenisconfiguratie, verwijs naar [Configureren in de beheerder](configure-admin.md) onderwerp.

## Configure Payment Services

U kunt [!DNL Payment Services] voor uw website en schakel het testen van sandboxen of live betalingen in het dialoogvenster [!UICONTROL General] instellingensectie.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Dashboardweergave](assets/payment-services-menu-small.png)

1. On the dashboard, click **[!UICONTROL Settings]** at the top right of the page.

   De _[!UICONTROL General]_sectie bevat de configuratieopties die worden gebruikt om [!DNL Payment Services] als betalingsmethode.

1. Voor de schakeloptie bovenaan (**[!UICONTROL Enable Payment Services as payment method]**), instellen op `Yes` om [!DNL Payment Services] voor uw website.

1. For **Payment mode**, set it to `Sandbox` if you are still testing [!DNL Payment Services] for your store or `Production` if you are ready to enable live payments.

   >[!WARNING]
   >
   >Your [!UICONTROL Sandbox Merchant ID] and [!UICONTROL Production Merchant ID] are auto-generated and present in their respectable fields when you have finished onboarding for the sandbox and/or production. Do not remove or change these IDs.

1. Als u de standaardinstellingen voor betalingsfuncties en de weergave van de winkel wilt wijzigen, stelt u de gewenste aanvullende opties in:

   - [Creditcardvelden](#credit-card-fields)
   - [Slimme PayPal-knoppen](#paypal-smart-buttons)
   - [Knopstijl](#button-style)

1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.

   If you try to navigate away from this view without saving your changes, a modal appears that prompts you to discard changes, keep editing, or save changes.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Creditcardvelden

De [!UICONTROL Credit Card Fields] betaalopties bieden een eenvoudige en veilige afhandeling van betalingsmethoden met een creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

1. Voor **[!UICONTROL Checkout title]** Voer (indien nodig) tekst in om de naam te wijzigen van de betalingsmethode die tijdens het afrekenen wordt weergegeven.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. Voor **[!UICONTROL Debug Mode]**, schakelt u de kiezer in om de foutopsporingsmodus in te schakelen.
1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.

   If you try to navigate away from this view without saving your changes, a modal appears that prompts you to discard changes, keep editing, or save changes.

1. Navigate to **[!UICONTROL System]** > **[!UICONTROL Cache Management]** and click **[!UICONTROL Flush Cache]** to refresh all invalid caches.

### Slimme PayPal-knoppen

De [!DNL PayPal Smart Buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant. See [Payments options](payments-options.md#paypal-smart-buttons) for more information.

You can enable the PayPal smart buttons payment options within the dashboard:

1. To change the name of the payment method as shown during checkout, edit the value in the **[!UICONTROL Checkout Title]** field.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), set **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. De schakelkiezers gebruiken om in of uit te schakelen [!DNL PayPal smart button] weergavefuncties:
   - **[!UICONTROL Show buttons on product detail page]**
   - **[!UICONTROL Show buttons in mini cart preview]**
   - **[!UICONTROL Show buttons on cart page]**
   - **[!UICONTROL Show Venmo button]**.
   - **[!UICONTROL PayPal Pay Later enabled]** om de optie in te schakelen om de knop tijdens het afrekenen weer te geven.

1. Als u het dialoogvenster [Later betalen](payments-options.md#pay-later-button) (indien gewenst), schakelt u de **[!UICONTROL Display Pay Later message]** optie.
1. Als u de foutopsporingsmodus wilt inschakelen, klikt u op **[!UICONTROL Debug Mode]**,
1. To save your changes, click **[!UICONTROL Save]** at the top right of the page.

   If you try to navigate away from this view without saving your changes, a modal appears that prompts you to discard changes, keep editing, or save changes.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Knopstijl

You can also configure the _[!UICONTROL Button style]_options of the PayPal smart buttons within the dashboard:

1. To change the **[!UICONTROL Layout]**, select `Vertical` or `Horizontal`.
1. Als u de coderegel in een horizontale lay-out wilt inschakelen, klikt u op **[!UICONTROL Show tagline]**.
1. Als u de **[!UICONTROL Color]** selecteert u de gewenste kleuroptie.
1. Als u het dialoogvenster **[!UICONTROL Shape]**, selecteert u `Pill` of `Rect`.
1. Klik op **[!UICONTROL Responsive button height]**.
1. Als u de **[!UICONTROL Label]** selecteert u de gewenste labeloptie.
1. Klik op **[!UICONTROL Save]** rechtsboven op de pagina.

   If you try to navigate away from this view without saving your changes, a modal appears that prompts you to discard changes, keep editing, or save changes.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

You can configure [!DNL PayPal Smart Buttons] styling in the Admin or the Dashboard. Zie [Stijlgids voor PayPal-knoppen](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) voor meer informatie .
