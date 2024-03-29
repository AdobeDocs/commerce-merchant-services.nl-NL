---
title: Configuratie van verouderde betalingsservices
description: Na installatie kunt u configureren [!DNL Payment Services] in Admin bij de archiefconfiguratie.
role: Admin, User
level: Intermediate
exl-id: e1a3269d-bdf9-4b0f-972f-e8a0ef469503
feature: Payments, Checkout, Configuration
source-git-commit: 0dc370409ace6ac6b0a56511cd0071cf525620f1
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 0%

---

# Verouderd [!DNL Payment Services] Configuratie

U kunt [!DNL Payment Services] aan uw behoeften met nuttige configuratieopties in Admin.

Wanneer u [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] in Admin, zijn die configuraties van toepassing slechts op het milieu dat in wordt geplaatst _[!UICONTROL Method]_veld_[!UICONTROL General Configuration]_. Om het even welke veranderingen u in de configuratiegebieden aanbrengt zijn onafhankelijk van omschakeling _[!UICONTROL Method]_selectie—als u van methode wisselt, worden de selecties niet opnieuw ingesteld.

## Algemene configuratie

U kunt [!DNL Payment Services] voor uw winkel en uw  _[!UICONTROL Merchant Location]_en schakel het testen van sandboxen of het uitvoeren van rechtstreekse betalingen in de_[!UICONTROL General Configuration]_ sectie.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.

   ![Methoden, weergave](assets/methods-view.png){width="400" zoomable="yes"}

1. Stel de _[!UICONTROL Merchant Country]_in het veld_[!UICONTROL Merchant Location]_.
1. Breid uit _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_voor toegang tot de_[!UICONTROL [!DNL Payment Services]]_ sectie.
1. In de _[!UICONTROL [!DNL Payment Services]]_sectie, breid de_[!UICONTROL General Configuration]_ sectie.
1. Voor **Inschakelen**, stelt u deze in op `Yes` om [!DNL Payment Services] voor uw winkel.
1. Voor **Methode**, stelt u deze in op `Sandbox` als u nog test [!DNL Payment Services] voor uw winkel of `Production` als u bereid bent om levende betalingen toe te laten.

   >[!WARNING]
   >
   >Uw _[!UICONTROL Sandbox Merchant ID]_en_[!UICONTROL Production Merchant ID]_ automatisch worden gegenereerd en aanwezig zijn in de betreffende velden als u klaar bent met het aan boord nemen voor de sandbox en/of productie. Verwijder of wijzig deze id&#39;s niet.

1. Voor **Zachte beschrijving** (aangepaste waarden die op bankafschriften voor transacties van klanten worden weergegeven om te bepalen tussen winkels/merken/catalogi), voegt u aangepaste tekst (maximaal 22 tekens) toe in het tekstveld en vervangt u de tekst `Custom descriptor` of de bestaande waarde.
1. Klikken **[!UICONTROL Save Config]** om uw wijzigingen op te slaan.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

![Weergave Oplossing aanbevolen Adobe](assets/featured-adobe-solution-view.png){width="700" zoomable="yes"}

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Enable] | website | In- of uitschakelen [!DNL Payment Services] voor uw website. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Method] | winkelweergave | Plaats de methode, of het milieu, voor uw opslag. Opties: [!UICONTROL Sandbox] / [!UICONTROL Production] |
| [!UICONTROL Sandbox Merchant ID] | winkelweergave | De bedrijfs-id van de sandbox, die automatisch wordt gegenereerd tijdens het aan boord nemen van de sandbox. Wijzig of wijzig deze id niet. |
| [!UICONTROL Production Merchant ID] | winkelweergave | Uw bedrijfs-id voor productie, die automatisch wordt gegenereerd tijdens het aan boord nemen van sandboxen. Wijzig of wijzig deze id niet. |
| [!UICONTROL Soft Descriptor] | website- of winkelweergave | Voeg een elektronische beschrijving toe aan uw website(s) en sla de weergave(en) op om informatie toe te voegen aan klanttransacties die merken, winkels of productlijnen afbakenen. |

## [!UICONTROL Credit Card Fields]

De [!UICONTROL Credit Card Fields] betaalopties bieden een eenvoudige en veilige afhandeling van betalingsmethoden met een creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_uit.
1. In de _[!UICONTROL Payment Services]_sectie, breid de_[!UICONTROL Credit Card Fields]_ sectie.
1. Voor **[!UICONTROL Title]**, voert u (indien nodig) tekst in om de naam van de betalingsmethode te wijzigen zoals deze tijdens het afrekenen wordt weergegeven.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), selecteert u **[!UICONTROL Authorize]** of **Autoriseren en vastleggen**.
1. Als u een betalingsmethode op de afhandelingspagina een prioriteit wilt geven, geeft u een `Numeric Only` waarde in de **[!UICONTROL Sort order]** veld.
1. Voor **[!UICONTROL Show on checkout page]**, kiest u `Yes` om creditcardvelden in te schakelen op de afhandelingspagina.
1. Voor **[!UICONTROL Vault Enabled]**, kiest u `Yes` om creditcardgegevens beschikbaar te maken voor afhandeling.
1. Voor **[!UICONTROL Vault Enabled in Admin]**, kiest u `Yes` om de handelaar in staat te stellen orders voor klanten te maken met behulp van hun gefactureerde creditcard.
1. Inschakelen **[!UICONTROL 3DS Secure authentication]** (`Off` standaard) kiezen `Always` of `When required`.
1. Voor **[!UICONTROL Debug Mode]**, kiest u `Yes` om de foutopsporingsmodus in te schakelen, of `No` om het uit te schakelen.
1. Klikken **[!UICONTROL Save Config]** om uw wijzigingen op te slaan.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen als titel voor deze betalingsoptie moet worden weergegeven, toe in de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://experienceleague.adobe.com/docs/commerce-admin/config/sales/payment-methods/payment-methods.html) voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Sort order] | winkelweergave | De sorteervolgorde voor de opgegeven betalingsmethode op de uitcheckpagina. `Numeric Only` value |
| [!UICONTROL Show on checkout page] | website | Schakel creditcardvelden op de afrekenpagina in of uit. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Vault enabled] | winkelweergave | In- of uitschakelen [creditcard vauleren](vaulting.md). Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Vault enabled in Admin] | winkelweergave | Mogelijkheid in- of uitschakelen voor [handelaar om orden voor klanten in Admin te voltooien](vaulting.md) met behulp van een gefactureerde betalingsmethode. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL 3DS Secure authentication] | website | In- of uitschakelen [Beveiligde 3DS-verificatie](security.md#3ds). Opties: [!UICONTROL Always] / [!UICONTROL When Required] / [!UICONTROL Off] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |

## [!UICONTROL Apple Pay]

De [!UICONTROL Apple Pay] Met deze betalingsoptie kan de verkoper Apple Pay aanbieden aan zijn kopers, die met Touch ID op hun apparaten aankopen kunnen doen via de Safari-browser. Merchants kunnen maximaal 99 domeinen per zakelijke account toevoegen.

Zie [Betalingsopties](payments-options.md#apple-pay-button) voor meer informatie .

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_uit.
1. In de _[!UICONTROL Payment Services]_sectie, breid de_[!UICONTROL Apple Pay]_ sectie.
1. Voor **[!UICONTROL Title]**, voert u (indien nodig) tekst in om de naam van de betalingsmethode te wijzigen zoals deze tijdens het afrekenen wordt weergegeven.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), selecteert u **[!UICONTROL Authorize]** of **[!UICONTROL Authorize and Capture]**.
1. Geef op waar de [!DNL Apple Pay] in Adobe Commerce is ingeschakeld door `Yes` in de volgende opties, indien nodig:
   * **[!UICONTROL Show Apple Pay on checkout page]**
   * **[!UICONTROL Show Apple Pay on product detail page]**
   * **[!UICONTROL Show Apple Pay in mini cart preview]**
   * **[!UICONTROL Show Apple Pay on cart page]**
1. Als u de foutopsporingsmodus wilt inschakelen, selecteert u `Yes` voor de **[!UICONTROL Debug Mode]** (`No` schakelt deze uit).
1. Als u de wijzigingen wilt opslaan, klikt u op **[!UICONTROL Save Config]** .
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen als titel voor deze betalingsoptie moet worden weergegeven, toe in de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://experienceleague.adobe.com/docs/commerce-admin/config/sales/payment-methods/payment-methods.html) voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Show on checkout page] | website | In- of uitschakelen [!DNL Apple Pay] op de uitcheckpagina. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Sort order] | winkelweergave | De sorteervolgorde voor de opgegeven betalingsmethode op de uitcheckpagina. `Numeric Only` value |
| [!UICONTROL Show buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL Apple Pay] op de pagina met productdetails. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons in mini-cart preview] | winkelweergave | In- of uitschakelen [!DNL Apple Pay] in de voorvertoning van de mini-cart. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons on cart page] | winkelweergave | In- of uitschakelen [!DNL Apple Pay] in op de winkelwagentje. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |

## [!UICONTROL Google Pay]

De [!UICONTROL Google Pay] Met deze betalingsoptie kan de verkoper Google Pay aanbieden aan zijn kopers, die de Google Wallet op hun apparaten kunnen gebruiken om aankopen te doen.

Zie [Betalingsopties](payments-options.md#google-pay-button) voor meer informatie .

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_uit.
1. In de _[!UICONTROL Payment Services]_sectie, breid de_[!UICONTROL Google Pay]_ sectie.
1. (Optioneel) Wijzig de naam van de betalingsmethode die tijdens het afrekenen wordt weergegeven door de nieuwe naam in te voeren in het dialoogvenster **[!UICONTROL Title]** veld.
1. [De betalingsactie instellen](production.md#set-payment-services-as-payment-method) door **[!UICONTROL Authorize]** of **[!UICONTROL Authorize and Capture]**.
1. Geef op waar de [!DNL Google Pay] in Adobe Commerce is ingeschakeld door `Yes` in de volgende opties, indien nodig:
   * **[!UICONTROL Show Google Pay on checkout page]**
   * **[!UICONTROL Show Google Pay on product detail page]**
   * **[!UICONTROL Show Google Pay in mini cart preview]**
   * **[!UICONTROL Show Google Pay on cart page]**
1. Als u de foutopsporingsmodus wilt inschakelen, selecteert u `Yes` voor de **[!UICONTROL Debug Mode]** (`No` schakelt deze uit).
1. Vorm de verschijning van _[!UICONTROL Google Pay]_door de knop **[!UICONTROL Button Color]**,**[!UICONTROL Button Type]**, en **[!UICONTROL Button Style]**indien nodig.
1. Als u de hoogte wilt instellen, gebruikt u de standaardwaarde voor de hoogte die is gedefinieerd in **[!UICONTROL Button Style]**.
1. Als u de wijzigingen wilt opslaan, klikt u op **[!UICONTROL Save Config]** .
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Hiermee geeft u het tekstlabel op dat voor deze betalingsoptie wordt weergegeven in de weergave Betalingsmethode tijdens het uitchecken. Opties: `[!UICONTROL text field]` |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://experienceleague.adobe.com/docs/commerce-admin/config/sales/payment-methods/payment-methods.html) voor de opgegeven betalingsmethode. Opties: `[!UICONTROL Authorize]` / `[!UICONTROL Authorize and Capture]` |
| [!UICONTROL Show on checkout page] | website | In- of uitschakelen [!DNL Google Pay] op de uitcheckpagina. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Sort order] | winkelweergave | De sorteervolgorde voor de opgegeven betalingsmethode op de uitcheckpagina. `Numeric Only` value |
| [!UICONTROL Show buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL Google Pay] op de pagina met productdetails. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons in mini-cart preview] | winkelweergave | In- of uitschakelen [!DNL Google Pay] in de voorvertoning van de mini-cart. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons on cart page] | winkelweergave | In- of uitschakelen [!DNL Google Pay] op de winkelwagentje. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Button Color] | Winkelweergave | De kleur van de [!DNL Google Pay] knop. Opties: `[!UICONTROL Default]` / `[!UICONTROL Black]` / `[!UICONTROL White]` |
| [!UICONTROL Button Type] | Winkelweergave | Het type van het dialoogvenster definiëren [!DNL Google Pay] knop. Opties: `[!UICONTROL buy]` / `[!UICONTROL checkout]` / `[!UICONTROL order]` / `[!UICONTROL pay]` / `[!UICONTROL plain]` |

Zie [Opties voor Google Pay API-aanvraagobjecten](https://developers.google.com/pay/api/web/reference/request-objects) documentatie voor meer informatie.

## [!DNL PayPal Payment Buttons]

De [!DNL PayPal payment buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

Configureren [!DNL PayPal payment buttons]

U kunt de betalingsopties van de PayPal-betalingsknoppen inschakelen en configureren in de beheerfunctie:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_uit.
1. In de _[!UICONTROL Payment Services]_sectie, breid de_[!UICONTROL PayPal payment buttons]_ sectie.
1. Als u de naam van de betalingsmethode wilt wijzigen, zoals wordt weergegeven tijdens het afrekenen, bewerkt u de _[!UICONTROL Title]_veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), selecteert u **[!UICONTROL Authorize]** of **[!UICONTROL Authorize and Capture]**.
1. Als u een betalingsmethode op de afhandelingspagina een prioriteit wilt geven, geeft u een `Numeric Only` waarde in de **[!UICONTROL Sort order]** veld.
1. Om het [Later betalen](payments-options.md#pay-later-button), selecteert u `Yes`/`No` for **[!UICONTROL Display Pay Later Message]**.
1. Geef op waar de PayPal-betalingsknoppen in Adobe Commerce zijn ingeschakeld door `Yes` in de volgende opties, indien nodig:
   * **[!UICONTROL Show buttons on checkout page]**
   * **[!UICONTROL Show buttons on product detail page]**
   * **[!UICONTROL Show buttons in mini cart preview]**
   * **[!UICONTROL Show buttons on cart page]**
1. Als u Venmo wilt inschakelen als betalingsoptie, selecteert u `Yes` for **[!UICONTROL Venmo Enabled]**.
1. Als je creditcards als betalingsoptie wilt inschakelen (PayPal Smart-knop), selecteer je `Yes` for **[!UICONTROL Credit and Debit Card Enabled]**.
1. Om het [PayPal PayPal Later](payments-options.md#pay-later-button) betalingsoptie, selecteer `Yes`/`No` for **[!UICONTROL PayPal Pay Later Enabled]**.
1. Als u de foutopsporingsmodus wilt inschakelen, selecteert u `Yes` voor de **[!UICONTROL Debug Mode]** (`No` schakelt deze uit).
1. Als u de wijzigingen wilt opslaan, klikt u op **[!UICONTROL Save Config]** .
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg tijdens het afrekenen de tekst toe die als titel voor deze betalingsoptie moet worden weergegeven in de weergave Betalingsmethode. Opties: tekstveld |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Display Pay Later Message] | website | Schakel het bericht Later betalen in of uit in het winkelwagentje, de productpagina, de miniwinkelwagentje en tijdens de afrekenstroom. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons on checkout page] | winkelweergave | In- of uitschakelen [!DNL PayPal payment buttons] op de uitcheckpagina. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL PayPal payment buttons] op de pagina met productdetails. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons in mini-cart preview] | winkelweergave | In- of uitschakelen [!DNL PayPal payment buttons] in de voorvertoning van de mini-cart. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Show buttons on cart page] | winkelweergave | In- of uitschakelen [!DNL PayPal payment buttons] in op de winkelwagentje. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Venmo Enabled] | winkelweergave | Schakel de betalingsoptie van Venmo in of uit waar betalingsknoppen worden weergegeven. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Credit and Debit Card Enabled] | winkelweergave | Schakel de opties voor creditering en incasso in of uit waar de betalingsknoppen worden weergegeven. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL PayPal Pay Later Enabled] | winkelweergave | De weergave van PayPal-betalingsopties voor latere betalingen in- of uitschakelen wanneer betalingsknoppen worden weergegeven. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |

## Knopstijl

U kunt ook de _[!UICONTROL Button style]_opties voor de betalingsknoppen:

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Vouw de sectie _[!UICONTROL FEATURED ADOBE PAYMENT SOLUTION]_uit.
1. In de _[!UICONTROL [!DNL Payment Services]]_sectie, breid de_[!UICONTROL PayPal Smart Button Styling]_ sectie.
1. Selecteer `Vertical` of `Horizontal` for **[!UICONTROL Layout]**
1. Als u de kleur wilt instellen, selecteert u een van de beschikbare kleuren in **[!UICONTROL Color]**.
1. Selecteer `Rectangular` of `Pill` for **[!UICONTROL Shape]**.
1. Selecteer `Yes` of `No` for **[!UICONTROL Use Default Height]**.
1. Voeg de gewenste pixelhoogte toe voor het instellen van de aangepaste hoogte **[!UICONTROL Height]**.
1. Selecteer `Yes` of `No` for **[!UICONTROL Tagline]**.
1. Als u de wijzigingen wilt opslaan, klikt u op **[!UICONTROL Save Config]** .
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

U kunt ook de opmaak van de betalingsknoppen configureren [in Instellingen](settings.md#button-style) vanuit Home Betalingsservices.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|--- |--- |--- |
| [!UICONTROL Layout] | Winkelweergave | Definieer de lay-outstijl voor PayPal-betalingsknoppen. Opties: `[!UICONTROL Vertical]` / `[!UICONTROL Horizontal]` |
| [!UICONTROL Color] | Winkelweergave | Geef de kleur van de PayPal-betalingsknoppen op. Opties: [!UICONTROL Blue] / `[!UICONTROL Gold]` / `[!UICONTROL Silver]` / `[!UICONTROL White]` / `[!UICONTROL Black]` |
| [!UICONTROL Shape] | Winkelweergave | Vorm van de PayPal-betalingsknoppen definiëren. Opties: `[!UICONTROL Rectangular]` / `[!UICONTROL Pill]` |
| [!UICONTROL Use Default Height] | Winkelweergave | Hiermee wordt gedefinieerd of voor PayPal-betalingsknoppen een standaardhoogte wordt gebruikt. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |
| [!UICONTROL Height] | Winkelweergave | Bepaal de hoogte van de PayPal-betalingsknoppen. Standaardwaarde: geen |
| [!UICONTROL Label] | Winkelweergave | Definieer het label dat wordt weergegeven in de PayPal-betalingsknoppen. Opties: `[!UICONTROL PayPal]` / `[!UICONTROL Checkout]` / `[!UICONTROL Buynow]` / `[!UICONTROL Pay]` / `[!UICONTROL Installment]` |
| [!UICONTROL Tagline] | Winkelweergave | Hiermee schakelt u de taglijn in. Opties: `[!UICONTROL Yes]` / `[!UICONTROL No]` |

## De cache leegmaken

Als u de configuratie wijzigt, [de cache handmatig leegmaken](/help/payment-services/settings.md#flush-the-cache) zodat in uw winkel de meest recente configuratie-instellingen worden weergegeven.
