---
title: Betalingsopties
description: Stel de betalingsopties in om de beschikbare methoden voor uw winkelklanten aan te passen.
exl-id: 95e648e6-6cb8-4226-b5ea-e1857212f20a
source-git-commit: 9bc392f2ae12269ded6174b830562444d6827f5f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# Betalingsopties

Met [!DNL Adobe Commerce] en [!DNL Magento Open Source] [!DNL Payment Services], je hebt meerdere betalingsopties beschikbaar. U kunt deze betalingsopties configureren via:

* [Startinstellingen](payments-home.md)
* [Winkelconfiguratie](configure-admin.md) (aanbevolen voor oudere betalingsopties of een installatie in meerdere winkels)

Er zijn verschillende gedragingen voor elke betalingsmethode, afhankelijk van waar u zich bevindt in het uitbetalingsproces:

* Productpagina—De productpagina voor een item
* Mini kart - Beschikbaar bij klikken op het pictogram van het karretje wanneer een product aan het karretje is toegevoegd
* Winkelwagentje - beschikbaar na klikken van _Kaart weergeven en bewerken_ van de miniwagen
* Uitchecken, weergave—Beschikbaar na klikken op _Doorgaan naar Afhandeling_ van minikarretje of winkelwagentje

>[!IMPORTANT]
>
>Betalingsdiensten aan boord moeten zijn voltooid voordat betalingen kunnen worden verwerkt.

## [!UICONTROL Credit Card Fields]

[!UICONTROL Credit Card Fields] een eenvoudige en veilige afhandeling van betalingsmethoden voor creditcard of bankpas aanbieden. Wanneer een winkelier uitcheckt met gebruik van creditcardvelden, voert hij zijn naam, factuuradres en creditcardgegevens in om zijn bestelling te plaatsen. De klantgegevens worden tijdens de aankoopsessie veilig gebruikt om ze naadloos door de afrekenstroom te begeleiden.

Inschakelen [creditcard vauleren](#vaulting) zodat kopers hun creditcardgegevens kunnen bewaren voor een snelle afhandeling later.

U kunt configureren [!UICONTROL Credit Card Fields] in de winkelconfiguratie of de startpagina van de betalingsservices. Zie [Instellingen](settings.md#credit-card-fields) voor meer informatie .

U kunt ook de lay-out, breedte, hoogte en buitenstijl van de creditcardvelden wijzigen. Zie [PayPal-documentatie](https://developer.paypal.com/docs/checkout/advanced/customize/card-field-style/) voor meer informatie .

## [!DNL PayPal Smart Buttons]

[!DNL PayPal Smart Buttons], die PayPal gebruiken om een aankoop te voltooien, slaat het verzendadres, het factuuradres en de betalingsgegevens van je winkel op voor later gebruik. Kopers kunnen elke betalingsmethode gebruiken die eerder door PayPal is opgeslagen of aangeboden.

![[!DNL PayPal Smart Buttons] opties](assets/buttons-md.png)

U kunt configureren [!UICONTROL PayPal Smart Buttons] in de winkelconfiguratie of de startpagina van de betalingsservices.  Zie [Instellingen](settings.md#payment-buttons) voor meer informatie .

### [!DNL PayPal] knop

Klanten kunnen met gemak en vertrouwen uitchecken met de PayPal-knop.

De [!DNL PayPal] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### [!DNL Venmo] knop

Klanten kunnen uitchecken met de [Venmo](https://venmo.com/) knop.

De [!DNL Venmo] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### [!DNL Apple Pay] knop

Klanten kunnen Touch ID op hun apparaten gebruiken [[!DNL Apple Pay]](https://www.apple.com/apple-pay/), die gebruik maakt van betalingsgegevens voor creditcard en bankpas die op hun iOS- of macOS-apparaat zijn opgeslagen.

De [!DNL Apple Pay] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

>[!NOTE]
>
> Te gebruiken [!DNL Apple Pay] voor uw winkels, volledig [zelfregistratie met [!DNL Apple Pay]](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain) (_Uw live domein registreren_ alleen deel) en [configureren voor uw winkels in [!DNL Payment Services]](settings.md#payment-buttons).

### [!DNL Pay Later] knop

Bied uw klanten kortetermijnbetalingen, rentevrije betalingen en andere financieringsopties aan, zodat ze nu kunnen kopen en later kunnen betalen met de [!DNL Pay Later] knop.

De [!DNL Pay Later] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave:

* **Wanneer een klant een product tussen $30 en $600 selecteert**, berichten via PayPal en [!DNL Pay Later] knoppen geven de klant meer informatie over de [!DNL Pay in 4] betalingsoptie. Klanten kunnen op **Meer informatie** voor meer informatie over &quot;[!DNL Pay in 4]&quot;, optie _of_ Klik op de tekst &quot;Of zie 6 maanden speciale financiering&quot; in het pop-upmenu voor meer informatie over en het aanvragen van de optie PayPal-krediet.
* **Wanneer een klant een product of producten selecteert die meer bedragen dan $ 98,99**, berichten via PayPal en [!DNL Pay Later] Deze knoppen bieden klanten meer informatie over de optie PayPal Credit. Klanten kunnen op **Meer informatie** voor meer informatie over de optie PayPal Credit en het aanvragen van deze optie, _of_ Klik op de tekst &quot;Of zie Betalen in 4&quot; in de pop-up voor meer informatie over de [!DNL Pay in 4] optie.

   >[!NOTE]
   >
   >De hierboven vermelde bedragen kunnen worden gewijzigd.

Zie [Instellingen](settings.md#payment-buttons) leren hoe u de [!DNL Pay Later] berichten.

Er zijn twee betalingsopties voor de [!DNL Pay Later] knop:

* **Betalen in 4**—Klanten kunnen hun ordersaldo betalen in vier rentevrije betalingen (elke twee weken) na een eerste aanbetaling. Zie de [Betalen in 4 documentatie](https://www.paypal.com/us/digital-wallet/ways-to-pay/buy-now-pay-later) voor meer informatie .
* **PayPal-krediet**—Klanten kunnen hun ordersaldo volledig betalen over een periode van zes maanden, zonder rente. Zie de [PayPal-kredietdocumentatie](https://www.paypal.com/us/webapps/mpp/paypal-credit) voor meer informatie .

### [!DNL Pay Now] knop

De [!DNL Pay Now] Deze knop is zichtbaar in het pop-upvenster van PayPal wanneer een klant op een betalingsknop op het betalingsscherm klikt.

Als het definitieve orderbedrag nog niet bekend is (bijvoorbeeld wanneer u nog geen adresgegevens voor de verzending hebt) en de klant bezig is zich af te melden bij de productpagina, de miniwinkelwagentje of het winkelwagentje, zoals _Doorgaan_ is in plaats daarvan beschikbaar. Wanneer een klant klikt _Doorgaan_ Nadat ze hun betalingsmethode hebben bevestigd, worden ze doorgestuurd naar een pagina voor het controleren van orders om de benodigde gegevens te verzamelen voordat ze de afhandeling voltooien.

## Orderrecalculatie

Wanneer een klant de afhandelingsstroom invoert van de mini-cart, winkelwagentje of productpagina, wordt deze doorgestuurd naar een pagina voor het controleren van bestellingen waar hij het geselecteerde verzendadres kan zien in een pop-upvenster van PayPal. Nadat de klant de verzendmethode heeft geselecteerd, wordt het orderbedrag op de juiste wijze herberekend en kan de klant de verzendkosten en -belastingen zien.

Wanneer een klant de afrekenstroom vanaf de afhandelingspagina invoert, is het systeem zich al bewust van het verzendadres en het uiteindelijke berekende bedrag en worden de totalen op de juiste wijze weergegeven.

Belastingvrije dagen, verzendkosten en BTW kunnen per locatie sterk verschillen. Na [!DNL Payment Services] ontvangt het verzendadres en de verzendkosten, worden alle toepasselijke kosten snel opnieuw berekend en op de juiste wijze weergegeven tijdens de laatste afrekenfasen.

## Afhandeling vanaf productpagina

Wanneer een klant rechtstreeks vanaf de productpagina uitcheckt via PayPal of [!DNL Pay Later] knoppen, alleen het item dat op de huidige productpagina wordt weergegeven, wordt aangeschaft. Objecten die al in de winkelwagentje van de klant staan, worden niet aan de afhandelingsstroom toegevoegd en niet aangeschaft.

Als de klant de bestelling annuleert, wordt het item op de huidige productpagina toegevoegd aan het winkelwagentje van de klant en worden andere items in het winkelwagentje samengevoegd. Met deze functie kan de klant snel het object kopen dat hij of zij momenteel bekijkt, terwijl hij of zij ook andere objecten behoudt die hij of zij eerder aan zijn winkelwagentje heeft toegevoegd tijdens het bladeren door producten.

Wanneer een klant de afrekenstroom op de productpagina invoert, wordt de afhandelingspagina vereenvoudigd. In de weergave worden alleen gegevens en opties weergegeven die betrekking hebben op de volgorde.

## Creditcard vaulting

Klanten kunnen hun creditcardgegevens voor toekomstige aankopen op websiteniveau (elke winkel binnen dezelfde zakelijke account) invullen (of &quot;opslaan&quot;).

Zie [Creditcard vaulting](vaulting.md) voor meer informatie .

## Beveiliging

Zie [PCI-compatibiliteit](security.md#pci-compliance) voor meer informatie .
