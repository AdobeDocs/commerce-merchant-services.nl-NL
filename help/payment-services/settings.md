---
title: Instellingen voor betalingsservices
description: Na installatie kunt u configureren [!DNL Payment Services] in het startpunt.
role: Admin, User
level: Intermediate
exl-id: 108f2b24-39c1-4c87-8deb-d82ee1c24d55
source-git-commit: f14b4a1abe9c0f85dc9f070467f94819c1fe89e6
workflow-type: tm+mt
source-wordcount: '1909'
ht-degree: 0%

---

# Instellingen

U kunt [!DNL Payment Services] naar uw behoeften met nuttige instellingen in de [!DNL Payment Services] Home.

Om te vormen [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] klikken **[!UICONTROL Settings]**. Deze configuratieopties zijn alleen van toepassing op de omgeving die is ingesteld in het dialoogvenster _[!UICONTROL Payment mode]_van het[_ Algemeen _configuratieopties](#configure-general-settings).

Voor multi-store of erfenisconfiguratie zie [Configureren in de beheerder](configure-admin.md).

## Algemene instellingen configureren

De [!UICONTROL General] Met instellingen kunt u betalingsservices in- of uitschakelen als betalingsmethode en informatie toevoegen aan klanttransacties om een website of winkelweergave te markeren of voor te voegen met aangepaste informatie.

### Betalingsservices inschakelen

U kunt [!DNL Payment Services] voor uw website, en laat of zandbak het testen of levende betalingen toe.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Startweergave](assets/payment-services-menu-small.png)

1. Klikken **[!UICONTROL Settings]**. Zie [Inleiding tot [!DNL Payment Services] Home](payments-home.md) voor meer informatie .

   De _[!UICONTROL General]_sectie bevat instellingen die worden gebruikt om [!DNL Payment Services] als betalingsmethode.

1. Inschakelen [!DNL Payment Services] als betalingsmethode voor je winkel, in de _[!UICONTROL General]_sectie, schakelen **[!UICONTROL Enable Payment Services as payment method]**tot `Yes`.

1. Als u nog test [!DNL Payment Services] voor uw winkel, set **Betalingsmodus** tot `Sandbox`. Als u live betalingen wilt inschakelen, stelt u deze in op `Production`.

   >[!NOTE]
   >
   >Uw _[!UICONTROL Sandbox Merchant ID]_en_[!UICONTROL Production Merchant ID]_ automatisch worden gegenereerd en aanwezig zijn in de betreffende velden wanneer u klaar bent met het instappen voor de sandbox en/of productie.

1. Klikken **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

U kunt nu doorgaan met het wijzigen van de standaardinstellingen voor [betalingsopties](#configure-payment-options) functies en storefront display.

### soft descriptor toevoegen

U kunt een [!UICONTROL Soft Descriptor] naar de configuratie van uw website(s) of afzonderlijke winkelweergave(en). Zachte beschrijvingen worden weergegeven op bankafschriften van klanttransacties. Als u bijvoorbeeld meerdere winkels/merken/catalogi hebt, kunt u deze eenvoudig van elkaar scheiden door aangepaste tekst toe te voegen aan de [!UICONTROL Soft Descriptor] veld.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Startweergave](assets/payment-services-menu-small.png)

1. Klikken **[!UICONTROL Settings]**. Zie [Inleiding tot [!DNL Payment Services] Home](payments-home.md) voor meer informatie .
1. Selecteer de website- of opslagweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzelijst, waarvoor u een elektronische descriptor wilt maken. Voor de eerste setup laat u deze als **[!UICONTROL Default]** om de standaardwaarde in te stellen.
1. Voeg uw aangepaste tekst (maximaal 22 tekens) toe aan het tekstveld en vervang `Custom descriptor`.
1. Klikken **[!UICONTROL Save]**.
1. U kunt als volgt een andere softdescriptor maken dan de geconfigureerde standaardwaarde voor een website- of opslagweergave:
   1. Selecteer de website- of opslagweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzelijst, waarvoor u een elektronische descriptor wilt maken.
   1. Schakelen _uit_ **[!UICONTROL Use website]** (of **[!UICONTROL Use default]**, afhankelijk van het bereik dat u hebt geselecteerd).
   1. Voeg uw aangepaste tekst toe aan het tekstveld.
   1. Klikken **[!UICONTROL Save]**.
1. De standaardschermdescriptor inschakelen voor een website of winkel _of_ de softwaredescriptor die voor de bovenliggende website wordt gebruikt:
   1. Selecteer de website- of opslagweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzelijst, waarvoor u een bestaande elektronische descriptor wilt inschakelen.
   1. Schakelen _op_ **[!UICONTROL Use website]** (of **[!UICONTROL Use default]**, afhankelijk van het bereik dat u hebt geselecteerd).
   1. Klikken **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Enable] | website | In- of uitschakelen [!DNL Payment Services] voor uw website. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Payment mode] | winkelweergave | Plaats de methode, of het milieu, voor uw opslag. Opties: [!UICONTROL Sandbox] / [!UICONTROL Production] |
| [!UICONTROL Sandbox Merchant ID] | winkelweergave | De bedrijfs-id van de sandbox, die automatisch wordt gegenereerd tijdens het aan boord nemen van de sandbox. |
| [!UICONTROL Production Merchant ID] | winkelweergave | Uw bedrijfs-id voor productie, die automatisch wordt gegenereerd tijdens het aan boord nemen van sandboxen. |
| [!UICONTROL Soft Descriptor] | website- of winkelweergave | Voeg een elektronische beschrijving toe aan uw website(s) en sla de weergave(en) op om informatie toe te voegen aan klanttransacties die merken, winkels of productlijnen afbakenen. De [!UICONTROL Use website] met toggle wordt elke schermdescriptor toegepast die op websiteniveau is toegevoegd. De [!UICONTROL Use default] met toggle wordt elke schermdescriptor toegepast die als standaard is toegevoegd. |

## Betalingsopties configureren

Nu hebt u deze functie ingeschakeld [!UICONTROL Payment Services] voor uw website kunt u de standaardinstellingen voor betalingsfuncties en de storefront-weergave wijzigen.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Startweergave](assets/payment-services-menu-small.png)

1. Klikken **[!UICONTROL Settings]**. Zie [Inleiding tot [!DNL Payment Services] Home](payments-home.md) voor meer informatie .
1. Betalingsopties configureren voor [creditcards](#credit-card-fields), [betaalknoppen](#payment-buttons), en [knopstijl](#button-style), op de volgende secties.

### Creditcardvelden

De _[!UICONTROL Credit Card Fields]_de instellingen bieden een eenvoudige en veilige afrekenoptie voor betalingsmethoden met creditcard of bankpas.

Zie [Betalingsopties](payments-options.md#credit-card-fields) voor meer informatie .

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL Payment Services]**.

   ![Startweergave](assets/payment-services-menu-small.png)

1. Selecteer de winkelweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzemenu waarvoor u een betalingsmethode wilt inschakelen.
1. Als u de naam wilt wijzigen van de betalingsmethode die tijdens het afrekenen wordt weergegeven, bewerkt u de waarde in het dialoogvenster **[!UICONTROL Checkout title]** veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), schakelen **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. Inschakelen [Beveiligde 3DS-verificatie](security.md#3ds) (`Off` standaard) schakelt u de **[!UICONTROL 3DS Secure authentication]** kiezer naar `Always` of `When required`.
1. Schakel de optie **[!UICONTROL Show on checkout page]** kiezer.
1. In- of uitschakelen [kaartvaulatie](#card-vaulting), schakelt u de **[!UICONTROL Vault enabled]** kiezer.
1. In- of uitschakelen [Betaalmethoden in het beheerprogramma](#card-vaulting) (voor handelaren die orders voor klanten in de Admin voltooien met behulp van hun gefactureerde betalingsmethode) schakelt u de **[!UICONTROL Show vaulted methods in Admin]** kiezer.
1. Als u de foutopsporingsmodus wilt in- of uitschakelen, schakelt u de optie **[!UICONTROL Debug Mode]** kiezer.
1. Klikken **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. [De cache leegmaken](#flush-the-cache).

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen wordt weergegeven als titel voor deze betalingsoptie toe aan de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL 3DS Secure authentication] | website | In- of uitschakelen [Beveiligde 3DS-verificatie](security.md#3ds). Opties: [!UICONTROL Always] / [!UICONTROL When Required] / [!UICONTROL Off] |
| [!UICONTROL Show on checkout page] | website | In- of uitschakelen van creditcardvelden om weer te geven op de afhandelingspagina. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Vault enabled] | winkelweergave | In- of uitschakelen [creditcard vauleren](vaulting.md). Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Show vaulted payment methods in Admin] | winkelweergave | Laat of maak capaciteit voor koopman voor klanten in Admin toe onbruikbaar [met een in kluizen geplaatste betalingsmethode](vaulting.md). Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |

### Betalingsknoppen

De [!DNL PayPal Smart Buttons] betaalopties bieden een eenvoudig, snel en veilig afhandelingsproces voor uw klant. Zie [Betalingsopties](payments-options.md#paypal-smart-buttons) voor meer informatie .

U kunt de betalingsopties voor slimme PayPal-knoppen inschakelen en configureren:

1. Selecteer de winkelweergave in het dialoogvenster **[!UICONTROL Scope]** vervolgkeuzemenu waarvoor u een betalingsmethode wilt inschakelen.
1. Als u de naam van de betalingsmethode wilt wijzigen, zoals wordt weergegeven tijdens het afrekenen, bewerkt u de waarde in het dialoogvenster **[!UICONTROL Checkout Title]** veld.
1. Naar [betalingsactie instellen](production.md#set-payment-services-as-payment-method), schakelen **[!UICONTROL Payment action]** tot `Authorize` of `Authorize and Capture`.
1. De schakelkiezers gebruiken om in of uit te schakelen [!DNL PayPal smart button] weergavefuncties:
   - **[!UICONTROL Show PayPal buttons on product checkout page]**
   - **[!UICONTROL Show PayPal buttons on product detail page]**
   - **[!UICONTROL Show PayPal buttons in mini-cart preview]**
   - **[!UICONTROL Show PayPal buttons on cart page]**
   - **[!UICONTROL Show PayPal Pay Later button]**
   - **[!UICONTROL Show PayPal Pay Later message]**
   - **[!UICONTROL Show Venmo button]**
   - **[!UICONTROL Show Apple Pay button]**

      >[!NOTE]
      >
      > Apple Betaal je [moet een Apple-sandbox-testaccount hebben](https://developer.apple.com/apple-pay/sandbox-testing/#create-a-sandbox-tester-account) (invullen met valse creditcard en factureringsgegevens) om deze te testen. Als je Apple Pay klaar hebt in de sandbox _of_ productiemodus, na het voltooien van [testen en valideren](test-validate.md#test-in-sandbox-environment), voltooid [zelfregistratie met [!DNL Apple Pay]](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain) (_Uw live domein registreren_ alleen deel) en [configureren voor uw winkels in [!DNL Payment Services]](settings.md#payment-buttons).

      Terwijl u de zichtbaarheid van betalingsknoppen of het Later bericht PayPal Pay (PayPal Pay) in- of uitschakelt, wordt onder aan de pagina Settings een visuele voorvertoning van die configuratie weergegeven.

1. Schakel de optie **[!UICONTROL Debug Mode]** kiezer.
1. Klikken **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. [De cache leegmaken](#flush-the-cache).

#### Configuratieopties

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg tijdens het afrekenen de tekst toe die als titel voor deze betalingsoptie moet worden weergegeven in de weergave Betalingsmethode. Opties: tekstveld |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Show PayPal buttons on checkout page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de uitcheckpagina. Opties: [!UICONTROL  Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons on product detail page] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] op de pagina met productdetails. Opties: [!UICONTROL  Yes] / [!UICONTROL No] |
| [!UICONTROL Show PayPal buttons in mini-cart preview] | winkelweergave | In- of uitschakelen [!DNL PayPal Smart Buttons] in de voorvertoning van de minicart. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
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
   > Als de knopstijl is geconfigureerd als `Horizontal` en uw winkel is geconfigureerd om meerdere slimme PayPal-knoppen weer te geven, worden mogelijk slechts twee knoppen weergegeven op de productpagina, de afhandelingspagina en de miniwinkelwagentje, en één knop in het winkelwagentje.

1. Als u de taglijn in een horizontale lay-out wilt inschakelen, schakelt u het **[!UICONTROL Show tagline]** kiezer.
1. Als u de **[!UICONTROL Color]** selecteert u de gewenste kleuroptie.
1. Als u de **[!UICONTROL Shape]**, selecteert u `Pill` of `Rectangle`.
1. Schakel de optie **[!UICONTROL Responsive button height]** kiezer.
1. Als u de **[!UICONTROL Label]** selecteert u de gewenste labeloptie.

   Terwijl u de configuratieopties voor lay-out, kleur, vorm, hoogte en label wijzigt, wordt onder aan de pagina Instellingen een visuele voorvertoning van die configuratie weergegeven.

1. Klikken **[!UICONTROL Save]**.

   Als u probeert weg van deze mening te navigeren zonder uw veranderingen op te slaan, verschijnt een modaal die u ertoe aanzet om veranderingen te verwerpen, het uitgeven te houden, of veranderingen te bewaren.

1. [De cache leegmaken](#flush-the-cache).

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

## De cache leegmaken

Als u de configuratie wijzigt in _Instellingen_ Als u bijvoorbeeld de PayPal-, Venmo- of PayPal PayPal PayPal PayLater-knoppen in- of uitschakelt, wordt de cache handmatig leeggemaakt, zodat in de winkel de meest recente configuraties worden weergegeven.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]**.
1. Klikken **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

Als om het even welk Type van Geheime voorgeheugen in de lijst van het Beheer van het Geheime voorgeheugen een heeft `INVALIDATED` status, wordt de meest recente configuratie voor dat item mogelijk niet weergegeven in uw winkel. Duw het geheime voorgeheugen om uw opslag bij te werken om de recentste configuratie te tonen.

Om ervoor te zorgen dat uw opslag de correcte configuratie toont, periodiek [cachegeheugen leegmaken](https://docs.magento.com/user-guide/system/cache-management.html).

## Kaart vauleren

U kunt functionaliteit inschakelen waarmee uw klanten hun creditcardgegevens in hun Mijn account kunnen opslaan en gebruiken voor toekomstige aankopen.

U kunt ook kaartvaulting in Admin gebruiken om verdere orden voor bestaande klanten te voltooien.

Kaarten in- of uitschakelen in het dialoogvenster [Instellingen voor creditcardvelden](#credit-card-fields).

Zie [Creditcard vaulting](vaulting.md) voor meer informatie .

## 3DS

3DS beschermt klanten en handelaren tegen frauduleuze activiteiten in hun winkels en maakt naleving van de EU-normen mogelijk.

3DS in- of uitschakelen in het dialoogvenster [Instellingen voor creditcardvelden](#credit-card-fields).

Zie [3DS in beveiliging](security.md#3ds) voor meer informatie .

## Meerdere PayPal-accounts gebruiken

In [!UICONTROL Payment Services], je kunt meerdere PayPal-rekeningen gebruiken binnen **één** handelsrekening op het niveau van de website. Als u bijvoorbeeld uw winkel(s) in meerdere landen gebruikt (die verschillende [valuta](https://docs.magento.com/user-guide/stores/currency.html)) of wil Adobe Commerce gebruiken voor bepaalde onderdelen van uw bedrijf, maar niet _alles_, je kunt je zakelijke account zo instellen dat je meerdere PayPal-accounts kunt gebruiken.

Zie [Bereik van site, winkel en weergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html) voor meer informatie over de hiërarchie van websites, winkels en opslagweergaven.

Je verkoper kan een nieuwe [bereik](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) voor uw zakelijke account en aan boord van de aanvullende site met PayPal zodat alle PayPal-knoppen die u configureert, op uw site worden weergegeven. Neem contact op met uw verkoper voor hulp bij het gebruik van meerdere PayPal-accounts voor uw websites.
