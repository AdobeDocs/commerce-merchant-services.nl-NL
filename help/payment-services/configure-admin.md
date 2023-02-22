---
title: Configuratie van verouderde betalingsservices
description: Na installatie kunt u configureren [!DNL Payment Services] in Admin bij de archiefconfiguratie.
role: Admin, User
level: Intermediate
exl-id: e1a3269d-bdf9-4b0f-972f-e8a0ef469503
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---

# Verouderd [!DNL Payment Services] Configuratie

U kunt [!DNL Payment Services] aan uw behoeften met nuttige configuratieopties in Admin.

Wanneer u [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] in Admin, zijn die configuraties van toepassing slechts op het milieu dat in wordt geplaatst _[!UICONTROL Method]_veld_[!UICONTROL General Configuration]_. Om het even welke veranderingen u in de configuratiegebieden aanbrengt zijn onafhankelijk van het schakelen van _[!UICONTROL Method]_selectie—als u van methode verandert, worden de selecties niet opnieuw ingesteld.

## Algemene configuratie

U kunt [!DNL Payment Services] voor uw winkel en schakel het testen van sandboxen of live betalingen in in de _[!UICONTROL General Configuration]_sectie.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.

   ![Methoden, weergave](assets/methods-view.png)

1. Breid uit _[!UICONTROL Recommended Solutions]_sectie.
1. In de _[!UICONTROL [!DNL Payment Services]]_in, vouwt u de_[!UICONTROL General Configuration]_ sectie.
1. Voor **Inschakelen**, stelt u deze in op `Yes` om [!DNL Payment Services] voor uw winkel.
1. Voor **Methode**, stelt u deze in op `Sandbox` als u nog test [!DNL Payment Services] voor uw winkel of `Production` als u bereid bent om levende betalingen toe te laten.

   >[!WARNING]
   >
   >Uw _[!UICONTROL Sandbox Merchant ID]_en_[!UICONTROL Production Merchant ID]_ automatisch worden gegenereerd en aanwezig zijn in de betreffende velden als u klaar bent met het aan boord nemen voor de sandbox en/of productie. Verwijder of wijzig deze id&#39;s niet.

1. Klikken **[!UICONTROL Save Config]** om uw wijzigingen op te slaan.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Enable] | website | In- of uitschakelen [!DNL Payment Services] voor uw website. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Method] | winkelweergave | Plaats de methode, of het milieu, voor uw opslag. Opties: [!UICONTROL Sandbox] / [!UICONTROL Production] |
| [!UICONTROL Sandbox Merchant ID] | winkelweergave | De bedrijfs-id van de sandbox, die automatisch wordt gegenereerd tijdens het aan boord nemen van de sandbox. Wijzig of wijzig deze id niet. |
| [!UICONTROL Production Merchant ID] | winkelweergave | Uw bedrijfs-id voor productie, die automatisch wordt gegenereerd tijdens het aan boord nemen van sandboxen. Wijzig of wijzig deze id niet. |

## [!UICONTROL Credit Card Fields]

De [!UICONTROL Credit Card Fields] betaalopties bieden een eenvoudige en veilige afhandeling van betalingsmethoden met een creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

### Creditcardvelden configureren

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Breid uit _[!UICONTROL Recommended Solutions]_sectie.
1. In de _[!UICONTROL Payment Services]_in, vouwt u de_[!UICONTROL Credit Card Fields]_ sectie.
1. Voor **[!UICONTROL Title]**, voert u (indien nodig) tekst in om de naam van de betalingsmethode te wijzigen zoals deze tijdens het afrekenen wordt weergegeven.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), selecteert u **[!UICONTROL Authorize]** of **Autoriseren en vastleggen**.
1. Voor **[!UICONTROL Show on checkout page]** kiest u `Yes` om creditcardvelden in te schakelen op de afhandelingspagina.
1. Voor **[!UICONTROL Vault Enabled]** kiest u `Yes` om creditcardgegevens beschikbaar te maken voor afhandeling.
1. Voor **[!UICONTROL Vault Enabled in Admin]** kiest u `Yes` om de handelaar in staat te stellen orders voor klanten te maken met behulp van hun gefactureerde creditcard.
1. Voor **[!UICONTROL Debug Mode]** kiest u `Yes` om de foutopsporingsmodus in te schakelen (of `No` om deze uit te schakelen).
1. Inschakelen **[!UICONTROL 3DS Secure authentication]** (`Off` standaard) kiezen `Always` of `When required`.
1. Klikken **[!UICONTROL Save Config]** om uw wijzigingen op te slaan.
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen wordt weergegeven als titel voor deze betalingsoptie toe aan de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://experienceleague.adobe.com/docs/commerce-admin/config/sales/payment-methods/payment-methods.html) voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Show on checkout page] | website | Schakel creditcardvelden op de afhandelingspagina in of uit. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Vault enabled] | winkelweergave | In- of uitschakelen [creditcard vauleren](vaulting.md). Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Vault enabled in Admin] | winkelweergave | Mogelijkheid in- of uitschakelen voor [handelaar om orden voor klanten in Admin te voltooien](vaulting.md) met behulp van een gefactureerde betalingsmethode. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL 3DS Secure authentication] | website | In- of uitschakelen [Beveiligde 3DS-verificatie](security.md#3ds). Opties: [!UICONTROL Always] / [!UICONTROL When Required] / [!UICONTROL Off] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

## [!DNL PayPal Smart Buttons]

De [!DNL PayPal Smart Buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant.

Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

### Configureren [!DNL PayPal Smart Buttons]

U kunt de betaalopties voor slimme PayPal-knoppen inschakelen en configureren in de beheerfunctie:

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Sales]** en kiest u **[!UICONTROL Payment Methods]**.
1. Breid uit _[!UICONTROL Recommended Solutions]_sectie.
1. In de _[!UICONTROL Payment Services]_in, vouwt u de_[!UICONTROL PayPal Smart Buttons]_ sectie.
1. Als u de naam van de betalingsmethode wilt wijzigen, zoals wordt weergegeven tijdens het afrekenen, bewerkt u de _[!UICONTROL Title]_veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), selecteert u **[!UICONTROL Authorize]** of **[!UICONTROL Authorize and Capture]**.
1. Om het [Later betalen](payments-options.md#pay-later-button) (indien gewenst), selecteert u `No` for **[!UICONTROL Display Pay Later Message]**.
1. Selecteer `Yes` voor de **[!UICONTROL Debug Mode]** (`No` schakelt deze uit).
1. Klik op **[!UICONTROL Save Config]** .
1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik vervolgens op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg tijdens het afrekenen de tekst toe die als titel voor deze betalingsoptie moet worden weergegeven in de weergave Betalingsmethode. Opties: tekstveld |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Display Pay Later Message] | website | Schakel het bericht Later betalen in of uit in het winkelwagentje, de productpagina, de miniwinkelwagentje en tijdens de afrekenstroom. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Venmo Enabled] | winkelweergave | Schakel de betalingsoptie van Venmo in of uit waar betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Apple Pay Enabled] | winkelweergave | Schakel de betalingsoptie Apple Pay in of uit waar de betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL PayPal Pay Later Enabled] | winkelweergave | De weergave van betalingsopties voor latere betalingen in- of uitschakelen wanneer betalingsknoppen worden weergegeven. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de pagina met productdetails. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show buttons in mini-cart preview] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] in de voorvertoning van de minicart. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show buttons on cart page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de winkelwagentje. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

### [!DNL PayPal Smart Buttons] Stijlopties

| Veld | Toepassingsgebied | Beschrijving |
|--- |--- |--- |
| [!UICONTROL Layout] | Winkelweergave | Definieer de lay-outstijl voor PayPal Smart Buttons. Opties: [!UICONTROL Vertical] / [!UICONTROL Horizontal] |
| [!UICONTROL Color] | Winkelweergave | Definieer de kleur van de slimme PayPal-knoppen. Opties: [!UICONTROL Blue] / [!UICONTROL Gold] / [!UICONTROL Silver] / [!UICONTROL White] / [!UICONTROL Black] |
| [!UICONTROL Shape] | Winkelweergave | Vorm van de PayPal Smart-knoppen definiëren. Opties: [!UICONTROL Rectangular] / [!UICONTROL Pill] |
| [!UICONTROL Use Default Height] | Winkelweergave | Definieert of slimme PayPal-knoppen een standaardhoogte gebruiken. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Height] | Winkelweergave | Definieer de hoogte van de slimme PayPal-knoppen. Standaardwaarde: none |
| [!UICONTROL Label] | Winkelweergave | Definieer het label dat wordt weergegeven in de slimme PayPal-knoppen. Opties: [!UICONTROL PayPal] / [!UICONTROL Checkout] / [!UICONTROL Buynow] / [!UICONTROL Pay] / [!UICONTROL Installment] |
| [!UICONTROL Tagline] | Winkelweergave | Hiermee schakelt u de taglijn in. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

## De cache leegmaken

Als u de configuratie wijzigt, [de cache handmatig leegmaken](/help/payment-services/settings.md#flush-the-cache) zodat in uw winkel de meest recente configuratie-instellingen worden weergegeven.

