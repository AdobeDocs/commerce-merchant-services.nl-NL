---
title: Instellingen voor betalingsservices
description: Na installatie kunt u configureren [!DNL Payment Services] in het startpunt.
role: Admin, User
level: Intermediate
exl-id: 108f2b24-39c1-4c87-8deb-d82ee1c24d55
source-git-commit: 89fa175b70a2b4b37d5999dedc56a7e41ae28b7d
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 0%

---

# Instellingen

U kunt [!DNL Payment Services] naar uw behoeften met nuttige instellingen in de [!DNL Payment Services] Home.

Om te vormen [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] klikken **[!UICONTROL Settings]**. Deze configuratieopties zijn alleen van toepassing op de omgeving die is ingesteld in het dialoogvenster _[!UICONTROL Payment mode]_veld in_[!UICONTROL Settings]_ > _[!UICONTROL General]_.

>[!IMPORTANT]
>
> Voor multi-store of erfenisconfiguratie, verwijs naar [Configureren in de beheerder](configure-admin.md) onderwerp.

## Betalingsservices inschakelen

U kunt [!DNL Payment Services] voor uw website en schakel het testen van sandboxen of live betalingen in via [!UICONTROL General] sectie.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Startweergave](assets/payment-services-menu-small.png)

1. Klik op **[!UICONTROL Settings]**. Zie [Inleiding tot [!DNL Payment Services] Home](payments-home.md) voor meer informatie .

   De _[!UICONTROL General]_sectie bevat instellingen die worden gebruikt om [!DNL Payment Services] als betalingsmethode.

1. Inschakelen [!DNL Payment Services] als betalingsmethode voor je winkel, in de _[!UICONTROL General]_sectie, schakelen (**[!UICONTROL Enable Payment Services as payment method]**) naar `Yes`.

1. Als u nog test [!DNL Payment Services] voor uw winkel, set **Betalingsmodus** tot `Sandbox`. Als u live betalingen wilt inschakelen, stelt u deze in op `Production`.

   >[!NOTE]
   >
   >Uw _[!UICONTROL Sandbox Merchant ID]_en_[!UICONTROL Production Merchant ID]_ automatisch worden gegenereerd en aanwezig zijn in de betreffende velden wanneer u klaar bent met het instappen voor de sandbox en/of productie.

1. Klik op **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

U kunt nu doorgaan met het wijzigen van de standaardinstellingen voor [betalingsopties](#configure-payment-options) functies en storefront display.

### Algemene configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Enable] | website | In- of uitschakelen [!DNL Payment Services] voor uw website. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Payment mode] | winkelweergave | Plaats de methode, of het milieu, voor uw opslag. Opties: [!UICONTROL Sandbox] / [!UICONTROL Production] |
| [!UICONTROL Sandbox Merchant ID] | winkelweergave | De bedrijfs-id van de sandbox, die automatisch wordt gegenereerd tijdens het aan boord nemen van de sandbox. |
| [!UICONTROL Production Merchant ID] | winkelweergave | Uw bedrijfs-id voor productie, die automatisch wordt gegenereerd tijdens het aan boord nemen van sandboxen. |

## Betalingsopties configureren

Nu u Betalingsservices voor uw website hebt ingeschakeld, kunt u de standaardinstellingen voor betalingsfuncties en de weergave van winkels wijzigen.

### Creditcardvelden

De _[!UICONTROL Credit Card Fields]_de instellingen bieden een eenvoudige en veilige afrekenoptie voor betalingsmethoden met creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#credit-card-fields) voor meer informatie .

1. Selecteer de winkelweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzemenu waarvoor u een betalingsmethode wilt inschakelen.
1. Als u de naam wilt wijzigen van de betalingsmethode die tijdens het afrekenen wordt weergegeven, bewerkt u de waarde in het dialoogvenster **[!UICONTROL Checkout title]** veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), schakelen **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. Schakel de optie **[!UICONTROL Debug Mode]** kiezer.
1. Klik op **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen wordt weergegeven als titel voor deze betalingsoptie toe aan de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target=&quot;_blank&quot;} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

### Betalingsknoppen

De [!DNL PayPal Smart Buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant. Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

U kunt de betalingsopties voor slimme PayPal-knoppen inschakelen en configureren:

1. Selecteer de winkelweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzemenu waarvoor u een betalingsmethode wilt inschakelen.
1. Als u de naam van de betalingsmethode wilt wijzigen, zoals wordt weergegeven tijdens het afrekenen, bewerkt u de waarde in het dialoogvenster **[!UICONTROL Checkout Title]** veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), schakelen **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. De schakelkiezers gebruiken om in of uit te schakelen [!DNL PayPal smart button] weergavefuncties:
   - **[!UICONTROL Show PayPal buttons on product detail page]**
   - **[!UICONTROL Show PayPal buttons in mini cart preview]**
   - **[!UICONTROL Show PayPal buttons on cart page]**
   - **[!UICONTROL Show PayPal Pay Later button]**
   - **[!UICONTROL Show PayPal Pay Later message]**
   - **[!UICONTROL Show Venmo button]**
   - **[!UICONTROL Show Apple Pay button]**

      >[!NOTE]
      >
      > Apple Pay is standaard ingeschakeld voor de sandboxmodus, maar u kunt ook [moet een Apple Developer Account hebben](test-validate.md#test-in-sandbox-environment) (invullen met valse creditcard en factureringsgegevens) om deze te testen. Als je Apple Pay klaar bent voor gebruik in de productiemodus, nadat je een [testen en valideren](test-validate.md)Neem contact op met de verkoper om deze in te schakelen voor je live winkel(s).

1. Schakel de optie **[!UICONTROL Debug Mode]** kiezer.
1. Klik op **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg tijdens het afrekenen de tekst toe die als titel voor deze betalingsoptie moet worden weergegeven in de weergave Betalingsmethode. Opties: tekstveld |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target=&quot;_blank&quot;} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Show PayPal buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de pagina met productdetails. Opties: [!UICONTROL  Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons in mini cart preview] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] in de voorvertoning van de minikaart. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons on cart page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de winkelwagentje. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal Pay Later button] | winkelweergave | De weergave van betalingsopties voor latere betalingen in- of uitschakelen wanneer betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal Pay Later Message] | website | Schakel het bericht Later betalen in of uit in het winkelwagentje, de productpagina, de miniwinkelwagentje en tijdens de afrekenstroom. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show Venmo button] | winkelweergave | Schakel de betalingsoptie van Venmo in of uit waar betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show Apple Pay button] | winkelweergave | Schakel de betalingsoptie Apple Pay in of uit waar de betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

### Knopstijl

U kunt ook de _[!UICONTROL Button style]_opties van de slimme PayPal-knoppen:

1. Als u het dialoogvenster **[!UICONTROL Layout]**, selecteert u `Vertical` of `Horizontal`.

   >[!NOTE]
   >
   > Als de knopstijl is geconfigureerd als `Horizontal` en uw winkel is geconfigureerd om meerdere slimme PayPal-knoppen weer te geven, worden mogelijk slechts twee knoppen weergegeven op de productpagina, de afhandelingspagina en de minikaart, en één knop in het winkelwagentje.

1. Als u de taglijn in een horizontale lay-out wilt inschakelen, schakelt u het **[!UICONTROL Show tagline]** kiezer.
1. Als u de **[!UICONTROL Color]** selecteert u de gewenste kleuroptie.
1. Als u de **[!UICONTROL Shape]**, selecteert u `Pill` of `Rect`.
1. Schakel de optie **[!UICONTROL Responsive button height]** kiezer.
1. Als u de **[!UICONTROL Label]** selecteert u de gewenste labeloptie.
1. Klik op **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

U kunt configureren [!DNL PayPal Smart Buttons] stijl [in de oudere configuratie in de beheerder](configure-admin.md#configure-paypal-smart-buttons) of hier [!DNL Payment Services Home]. Zie [Stijlgids voor PayPal-knoppen](https://developer.paypal.com/docs/checkout/standard/customize/buttons-style-guide/) voor meer informatie over de opties.

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|--- |--- |--- |
| [!UICONTROL Layout] | Winkelweergave | Definieer de lay-outstijl voor de betaalknoppen. Opties: [!UICONTROL Vertical] / [!UICONTROL Horizontal] |
| [!UICONTROL Tagline] | Winkelweergave | Taglijn in-/uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Color] | Winkelweergave | Geef de kleur van de betaalknoppen op. Opties: [!UICONTROL Blue] / [!UICONTROL Gold] / [!UICONTROL Silver] / [!UICONTROL White] / [!UICONTROL Black] |
| [!UICONTROL Shape] | Winkelweergave | Vorm van de betaalknoppen definiëren. Opties: [!UICONTROL Rectangular] / [!UICONTROL Pill] |
| [!UICONTROL Responsive Button Height] | Winkelweergave | Definieert of voor de betalingsknoppen een standaardhoogte wordt gebruikt. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Height] | Winkelweergave | Bepaal hoogte van de betalingsknopen. Standaardwaarde: none |
| [!UICONTROL Label] | Winkelweergave | Definieer het label dat in de betaalknoppen wordt weergegeven. Opties: [!UICONTROL PayPal] / [!UICONTROL Checkout] / [!UICONTROL Buynow] / [!UICONTROL Pay] / [!UICONTROL Installment] |
