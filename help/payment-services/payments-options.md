---
title: Betalingsopties
description: Stel de betalingsopties in om de beschikbare methoden voor uw winkelklanten aan te passen.
exl-id: 95e648e6-6cb8-4226-b5ea-e1857212f20a
source-git-commit: bfb2b6632fe494d6e392c214f5e3f5a11930c0b2
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# Betalingsopties

Met Adobe Commerce en Magento Open Source [!DNL Payment Services], je hebt meerdere betalingsopties beschikbaar. U kunt deze betalingsopties configureren via:

* [Dashboard](configure-dashboard.md)
* [Winkelconfiguratie](configure-admin.md) (aanbevolen voor oudere betalingsopties of een installatie in meerdere winkels)

Er zijn verschillende gedragingen voor elke betalingsmethode, afhankelijk van waar u zich bevindt in het uitbetalingsproces:

* Productpagina—De productpagina voor een item
* Mini-kar - Beschikbaar na klik van het kartpictogram wanneer een product aan de kar is toegevoegd
* Winkelwagentje - beschikbaar na klikken van _Kaart weergeven en bewerken_ van de miniwagen
* Uitchecken, weergave—Beschikbaar na klikken op _Doorgaan naar Afhandeling_ van minikarretje of winkelwagentje

>[!IMPORTANT]
>
>Betalingsdiensten aan boord moeten zijn voltooid voordat betalingen kunnen worden verwerkt.

## [!UICONTROL Credit Card Fields]

[!UICONTROL Credit Card Fields] een eenvoudige en veilige afhandeling van betalingsmethoden voor creditcard of bankpas aanbieden. Wanneer een winkelier uitcheckt met gebruik van creditcardvelden, voert hij zijn naam, factuuradres en creditcardgegevens in om zijn bestelling te plaatsen. De klantgegevens worden tijdens de aankoopsessie veilig gebruikt om ze naadloos door de afrekenstroom te begeleiden.

U kunt configureren [!UICONTROL Credit Card Fields] in de winkelconfiguratie of het dashboard Betalingsservices. Zie [Configureren [!DNL Payment Services]](configure-dashboard.md#configure-credit-card-fields) voor meer informatie .

## [!DNL PayPal Smart Buttons]

[!DNL PayPal Smart Buttons], die PayPal gebruiken om een aankoop te voltooien, slaat het verzendadres, het factuuradres en de betalingsgegevens van je winkel op voor later gebruik. Kopers kunnen elke betalingsmethode gebruiken die eerder door PayPal is opgeslagen of aangeboden.

U kunt configureren [!DNL PayPal Smart Buttons] in de winkelconfiguratie of het dashboard Betalingsservices.  Zie [Configureren [!DNL Payment Services]](configure-dashboard.md#configure-paypal-smart-buttons) voor meer informatie .

### PayPal-knop

Klanten kunnen met gemak en vertrouwen uitchecken met de PayPal-knop.

De PayPal-knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### Knop Venmo

Klanten kunnen uitchecken met de [Venmo](https://venmo.com/) knop.

De knop Venmo is zichtbaar vanaf de productpagina, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

### [!DNL Pay Later] knop

Bied uw klanten kortetermijnbetalingen, rentevrije betalingen en andere financieringsopties aan, zodat ze nu kunnen kopen en later kunnen betalen met de [!DNL Pay Later] knop.

De [!DNL Pay Later] Deze knop is zichtbaar vanaf de pagina met producten, de miniwinkelwagentje, de winkelwagentje en de afrekenweergave.

Er zijn twee betalingsopties voor de [!DNL Pay Later] knop:

* **Betalen in 4**—Klanten kunnen hun ordersaldo betalen in vier rentevrije betalingen (elke twee weken) na een eerste aanbetaling. Zie de [Betalen in 4 documentatie](https://www.paypal.com/us/digital-wallet/ways-to-pay/buy-now-pay-later) voor meer informatie .
* **PayPal-krediet**—Klanten kunnen hun ordersaldo volledig betalen over een periode van zes maanden, zonder rente. Zie de [PayPal-kredietdocumentatie](https://www.paypal.com/us/webapps/mpp/paypal-credit) voor meer informatie .

### [!DNL Pay Now] knop

De [!DNL Pay Now] Deze knop is zichtbaar in het pop-upvenster van PayPal wanneer een klant op een betalingsknop op het betalingsscherm klikt.

Als het definitieve orderbedrag nog niet bekend is (bijvoorbeeld wanneer u nog geen adresgegevens voor de verzending hebt) en de klant bezig is zich af te melden bij de productpagina, de miniwinkelwagentje of het winkelwagentje, zoals _Doorgaan_ is in plaats daarvan beschikbaar. Wanneer een klant klikt _Doorgaan_ Nadat ze hun betalingsmethode hebben bevestigd, worden ze doorgestuurd naar een pagina voor het controleren van orders om de benodigde gegevens te verzamelen voordat ze de afhandeling voltooien.

## [!DNL Pay Later] berichten

Om uw klant te helpen deze als mogelijke betalingsopties identificeren, [!DNL Pay Later] Het overseinen is zichtbaar op de productpagina, in de mini-kar en het winkelwagentje, en tijdens controle.

* **Wanneer een klant een product tussen $30 en $600 selecteert**, berichten via PayPal en [!DNL Pay Later] knoppen geven de klant meer informatie over de betalingsoptie Betalen in 4. Klanten kunnen op **Meer informatie** voor meer informatie over de optie Betalen in 4 _of_ Klik op de tekst &quot;Of zie 6 maanden speciale financiering&quot; in het pop-upmenu voor meer informatie over en het aanvragen van de optie PayPal-krediet.
* **Wanneer een klant een product of producten selecteert die meer bedragen dan $ 98,99**, berichten via PayPal en [!DNL Pay Later] Deze knoppen bieden klanten meer informatie over de optie PayPal Credit. Klanten kunnen op **Meer informatie** voor meer informatie over de optie PayPal Credit en het aanvragen van deze optie _of_ Klik op de tekst &#39;&#39;Of zie Betalen in 4&#39;&#39; in de pop-up voor meer informatie over de optie Betalen in 4.

   >[!NOTE]
   >
   >De hierboven vermelde bedragen kunnen worden gewijzigd.

Zie [Configureren [!DNL Payment Services]](configure-admin.md#configure-paypal-smart-buttons) leren hoe u de [!DNL Pay Later] berichten.

## Orderrecalculatie

Wanneer een klant de afhandelingsstroom invoert van de mini-cart, winkelwagentje of productpagina, wordt deze doorgestuurd naar een pagina voor het controleren van bestellingen waar hij het geselecteerde verzendadres kan zien in een pop-upvenster van PayPal. Nadat de klant de verzendmethode heeft geselecteerd, wordt het orderbedrag op de juiste wijze herberekend en kan de klant de verzendkosten en -belastingen zien.

Wanneer een klant de afrekenstroom vanaf de afhandelingspagina invoert, is het systeem zich al bewust van het verzendadres en het uiteindelijke berekende bedrag en worden de totalen op de juiste wijze weergegeven.

Belastingvrije dagen, verzendkosten en BTW kunnen per locatie sterk verschillen. Na [!DNL Payment Services] ontvangt het verzendadres en de verzendkosten, worden alle toepasselijke kosten snel opnieuw berekend en op de juiste wijze weergegeven tijdens de laatste afrekenfasen.

## Afhandeling vanaf productpagina

Wanneer een klant rechtstreeks vanaf de productpagina uitcheckt via PayPal of [!DNL Pay Later] knoppen, alleen het item dat op de huidige productpagina wordt weergegeven, wordt aangeschaft. Objecten die al in de winkelwagentje van de klant staan, worden niet aan de afhandelingsstroom toegevoegd en niet aangeschaft.

Als de klant de bestelling annuleert, wordt het item op de huidige productpagina toegevoegd aan het winkelwagentje van de klant en worden andere items in het winkelwagentje samengevoegd. Met deze functie kan de klant snel het object kopen dat hij of zij momenteel bekijkt, terwijl hij of zij ook andere objecten behoudt die hij of zij eerder aan zijn winkelwagentje heeft toegevoegd tijdens het bladeren door producten.

Wanneer een klant de afrekenstroom op de productpagina invoert, wordt de afhandelingspagina vereenvoudigd. In de weergave worden alleen gegevens en opties weergegeven die betrekking hebben op de volgorde.

## Beveiliging

Zie [PCI-compatibiliteit](security.md#pci-compliance) voor meer informatie .
