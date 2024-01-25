---
title: Betalingsopties
description: Stel de betalingsopties in om de beschikbare methoden voor uw winkelklanten aan te passen.
exl-id: 95e648e6-6cb8-4226-b5ea-e1857212f20a
feature: Payments, Checkout, Configuration
source-git-commit: ff83c83a054e5b14814cc3076744c5517081a80f
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 0%

---

# Betalingsopties

Met [!DNL Adobe Commerce] en [!DNL Magento Open Source] [!DNL Payment Services], je hebt meerdere betalingsopties beschikbaar.

U kunt deze betalingsopties configureren in [Startinstellingen](payments-home.md) of [Winkelconfiguratie](configure-admin.md) (aanbevolen voor oudere betalingsopties of een installatie in meerdere opslagruimten).

Er zijn verschillende gedragingen voor elke betalingsmethode, afhankelijk van waar u zich bevindt in het uitbetalingsproces:

* Productpagina—De productpagina voor een item
* Mini kart - Beschikbaar bij klikken op het pictogram van het karretje wanneer een product aan de winkelwagentjes is toegevoegd
* Winkelwagentje - beschikbaar na klikken van _Kaart weergeven en bewerken_ van de miniwagen
* Uitchecken, weergave—Beschikbaar na klikken op _Doorgaan naar Afhandeling_ van minikarretje of winkelwagentje

>[!IMPORTANT]
>
>[!DNL Payment Services] de boeking moet zijn voltooid voordat de betalingen kunnen worden verwerkt.

## Standaard versus geavanceerde betalingservaring

[!DNL Payment Services] verstrekt **Geavanceerd** (volledig ondersteund) en **Standaard** (Express Checkout) betalingsopties en instapstromen, afhankelijk van het land waarin u werkt.

* **Geavanceerd** - Alle beschikbare [betalingsopties](../payment-services/payments-options.md) zijn beschikbaar voor [volledig gesteunde landen](../payment-services/overview.md#availability). Selecteer tijdens het instappen de optie [Geavanceerde instapoptie](../payment-services/production.md#advanced-onboarding).
* **Standaard** - Een subset betalingsopties (Express Checkout) - PayPal-krediet- en debetkaarten - is beschikbaar voor andere ondersteunde landen. [Creditcardvelden](#credit-card-fields) en [Apple Pay](#apple-pay-button) niet beschikbaar zijn voor deze instapoptie. Selecteer tijdens het instappen de optie [Standaardinstapoptie](../payment-services/production.md#standard-onboarding).

Zie [Inschakelen [!DNL Payment Services] voor productie](../payment-services/production.md#complete-merchant-onboarding) voor meer informatie over het invullen van Advanced en Standard onboarding.

## [!UICONTROL Credit Card Fields]

[!UICONTROL Credit Card Fields] een eenvoudige en veilige afhandeling van betalingsmethoden voor creditcard of bankpas aanbieden. Wanneer een winkelier uitcheckt met gebruik van creditcardvelden, voert hij zijn naam, factuuradres en creditcardgegevens in om zijn bestelling te plaatsen. De klantgegevens worden tijdens de aankoopsessie veilig gebruikt om ze naadloos door de afrekenstroom te begeleiden.

![Creditcardvelden in afhandeling](assets/credit-card-fields.png){width="500" zoomable="yes"}

Inschakelen [creditcard vauleren](#vaulting) zodat kopers hun creditcardgegevens kunnen bewaren voor een snelle afhandeling later.

U kunt [!UICONTROL Credit Card Fields] in de opslagconfiguratie of de [!DNL Payment Services] Home. Zie [Instellingen](settings.md#credit-card-fields) voor meer informatie .

U kunt ook de lay-out, breedte, hoogte en buitenstijl van de creditcardvelden wijzigen. Zie [PayPal-documentatie](https://developer.paypal.com/docs/checkout/advanced/customize/card-field-style/) voor meer informatie .

## [!DNL Apple Pay] knop

Klanten kunnen [[!DNL Apple Pay]](https://www.apple.com/apple-pay/), die gebruik maakt van betalingsgegevens van creditcard en bankpas die op een iOS- of macOS-apparaat zijn opgeslagen, voor aankopen.

[!DNL Apple Pay] is alleen beschikbaar in de Safari-browser.

![Apple Pay button in minicart](assets/apple-pay-button.png){width="500" zoomable="yes"}

De [!DNL Apple Pay] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

>[!NOTE]
>
> Te gebruiken [!DNL Apple Pay] voor uw winkels, voltooi [zelfregistratie met [!DNL Apple Pay]](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain) (_Uw live domein registreren_ alleen deel) en [configureren voor uw winkels in [!DNL Payment Services]](settings.md#payment-buttons).

U kunt [!UICONTROL Apple Pay] in de winkelconfiguratie of de startpagina van de betalingsservices. Zie [Instellingen](settings.md#apple-pay) voor meer informatie .

## [!DNL PayPal Smart Buttons]

[!DNL PayPal Smart Buttons], die PayPal gebruiken om een aankoop te voltooien, slaat het verzendadres, het factuuradres en de betalingsgegevens van je winkel op voor later gebruik. Kopers kunnen elke betalingsmethode gebruiken die eerder door PayPal is opgeslagen of aangeboden.

![PayPal-knop](assets/paypal-button.png){width="350" zoomable="yes"}

U kunt [!UICONTROL PayPal Smart Buttons] in de opslagconfiguratie of de [!DNL Payment Services] Home.  Zie [Instellingen](settings.md#payment-buttons) voor meer informatie .

Zie PayPal&#39;s [Documentatie over betalingsmethoden](https://developer.paypal.com/docs/checkout/payment-methods/) om te leren in welke landen elke betalingsmethode momenteel beschikbaar is.

### [!DNL PayPal] knop

Klanten kunnen met gemak en vertrouwen uitchecken met de PayPal-knop.

De [!DNL PayPal] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### [!DNL Venmo] knop

Klanten kunnen uitchecken met de [Venmo](https://venmo.com/) knop.

De [!DNL Venmo] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### PayPal-incasso of creditcard

Klanten kunnen uitchecken via de button PayPal-incasso of creditcard.

De button PayPal Debit of Creditcard is zichtbaar vanaf de betalingspagina.

Met deze optie kun je een betalingsoptie voor een debet of creditcard aan kopers aanbieden met een PayPal-gehoste knop als alternatief voor de integratie met een creditcard.

### [!DNL Pay Later] knop

Bied uw klanten kortetermijnbetalingen, rentevrije betalingen en andere financieringsopties aan, zodat ze nu kunnen kopen en later kunnen betalen met de [!DNL Pay Later] knop.

De [!DNL Pay Later] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

Meer informatie over de aanbiedingen voor Later betalen vindt u in [Later PayPal biedt documentatie](https://developer.paypal.com/docs/checkout/pay-later/us/). Gebruik de **Land of regio** vervolgkeuzelijst om een interessegebied te selecteren.

Zie [Instellingen](settings.md#payment-buttons) leren hoe u de [!DNL Pay Later] berichten.

## Alleen PayPal-betalingsknoppen gebruiken

Om uw opslag snel in productiemodus te krijgen kunt u _alleen_ PayPal-betalingsknoppen (Venmo, PayPal, enz.)—in plaats van ook de optie PayPal-creditcardbetaling te gebruiken.

Zo kunt u:

* Geef uw klanten diverse betalingsopties, waaronder de betaalknoppen Venmo en PayPal, met de optie om door PayPal gehoste kaartvelden uit te schakelen en een bestaande creditcardprovider te gebruiken.
* Gebruik de bestaande creditcardprovider voor creditcardbetalingen en gebruik daarbij ook de andere betalingsopties van PayPal.
* Gebruik de betalingsknoppen van PayPal in een regio waarin PayPal geen creditcards als betalingsoptie ondersteunt.

Naar **betalingen vastleggen met _alleen_ PayPal-betalingsknoppen (_niet_ (de optie PayPal-creditcardbetaling)**:

1. Zorg ervoor dat uw winkel [in productiemodus](settings.md#enable-payment-services).
1. [De gewenste PayPal-betalingsknoppen configureren](settings.md#payment-buttons) in Instellingen.
1. Draaien _Uit_ de **[[!UICONTROL Show PayPal Credit and Debit card button]](settings.md#payment-buttons)** in de _[!UICONTROL Payment buttons]_sectie.

Naar **betalingen vastleggen met uw bestaande creditcardprovider _en_ PayPal-betalingsknoppen**:

1. Zorg ervoor dat uw winkel [in productiemodus](settings.md#enable-payment-services).
1. [De gewenste PayPal-betalingsknoppen configureren](settings.md#payment-buttons).
1. Draaien _Uit_ de **[[!UICONTROL PayPal Show Credit and Debit card button]](settings.md#payment-buttons)** in de _[!UICONTROL Payment buttons]_sectie.
1. Draaien _Uit_ de **[[!UICONTROL Show on checkout page]](settings.md#credit-card-fields)** in de _[!UICONTROL Credit card fields]_en gebruik uw [bestaande creditcardprovider](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/payments/payments.html#payments).

## Orderrecalculatie

Wanneer een klant de afhandelingsstroom invoert van de mini-cart, winkelwagentje of productpagina, wordt deze doorgestuurd naar een pagina voor het controleren van bestellingen waar hij het geselecteerde verzendadres kan zien in een pop-upvenster van PayPal. Nadat de klant de verzendmethode heeft geselecteerd, wordt het orderbedrag op de juiste wijze herberekend en kan de klant de verzendkosten en -belastingen zien.

Wanneer een klant de afrekenstroom vanaf de afhandelingspagina invoert, is het systeem zich al bewust van het verzendadres en het uiteindelijke berekende bedrag en worden de totalen op de juiste wijze weergegeven.

Belastingvrije dagen, verzendkosten en BTW kunnen per locatie sterk verschillen. Na [!DNL Payment Services] ontvangt het verzendadres en de verzendkosten, worden alle toepasselijke kosten snel opnieuw berekend en op de juiste wijze weergegeven tijdens de laatste afrekenfasen.

## Creditcard vaulting

Klanten kunnen hun creditcardgegevens voor toekomstige aankopen op websiteniveau (elke winkel binnen dezelfde zakelijke account) invullen (of &quot;opslaan&quot;).

Zie [Creditcard vaulting](vaulting.md) voor meer informatie .

## Beveiliging

Zie [PCI-compatibiliteit](security.md#pci-compliance) voor meer informatie .
