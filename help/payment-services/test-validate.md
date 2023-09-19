---
title: Testen en valideren
description: Testen en valideren helpen u ervoor te zorgen dat [!DNL Payment Services] functies werken naar behoren en bieden de beste betalingsopties voor uw klanten
exl-id: 95b4615e-73b0-41e8-83e2-e65a0b22f10f
feature: Payments, Checkout
source-git-commit: 75ff893bf5867ededa49807835676ddf9b19adc9
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Testen en valideren

Voordat u [!DNL Payment Services] for [!DNL Adobe Commerce] en [!DNL Magento Open Source] voor uw kopers is het een goed idee om in uw sandboxomgeving te testen _en_ in productie. Testen en valideren helpen u ervoor te zorgen dat [!DNL Payment Services] -functies werken naar behoren en bieden de beste betalingsopties voor uw winkel en klanten.

## Testen in sandboxomgeving

Testen [!DNL Payment Services] in een sandbox-omgeving is een belangrijke validatiestap, ook al is het een gesimuleerde omgeving die alleen is verbonden met de PayPal-sandbox, niet met echte banken en handelaren.

1. Voltooi een geslaagde afhandeling in je winkel, ofwel met [Creditcardvelden](payments-options.md#credit-card-fields) of een van de [Slimme PayPal-knoppen](payments-options.md#paypal-smart-buttons). Zie [Referenties testen](#testing-credentials) voor meer informatie over het gebruik van valse creditcards voor het testen.
1. Vastleggen (wanneer uw betalingsactie is [instellen op `Authorize and Capture`](onboard.md#set-payment-services-as-payment-method)), [teruggave](refunds.md), of [void](voids.md) de zojuist voltooide bestelling. U kunt ook eenvoudig [een factuur maken](https://docs.magento.com/user-guide/sales/invoice-create.html){target="_blank"} voor een bestelling als uw betalingsactie is ingesteld op `Authorize` in plaats van `Authorize and Capture`.
1. Bekijk de transactie en andere informatie in de [Uitbetalingsrapport](payouts.md).
1. Zie de details van de bestelling in de [Betalingsstatusrapport bestellen](order-payment-status.md).

### Referenties testen

Bij het testen en valideren van uw sandbox moet u valse creditcardnummers gebruiken, zodat u geen echte kosten maakt voor een bestaande creditcardaccount.

De PayPal-creditcardgenerator gebruiken voor [willekeurige creditcardgegevens genereren](https://www.paypal.com/us/smarthelp/article/where-can-i-find-test-credit-card-numbers-ts2157) voor het testen.

Apple Pay in sandboxmodus testen:

* Een [Apple sandbox-testeraccount](https://developer.apple.com/apple-pay/sandbox-testing/#create-a-sandbox-tester-account), invullen met valse creditcard- en factureringsgegevens.
* [Sandboxdomeinen registreren](https://developer.paypal.com/docs/checkout/apm/apple-pay/#link-registeryoursandboxdomains).

>[!NOTE]
>
>De betalingsverwerking van de sandbox van PayPal is soms traag en de service kan af en toe omlaag gaan. Deze situatie geeft geen indicatie van de snelheid en de efficiëntie van de verwerking van de rechtstreekse betalingen.

## Test in productie

U wordt ten zeerste aangeraden om te testen [!DNL Payment Services] in productie, met echte kredietkaarten en banken, voordat deze functionaliteit aan kopers wordt aangeboden. Zelfs als het testen [!DNL Payment Services] in de sandbox is belangrijk, het testen in productie is de meest misleidende methode om ervoor te zorgen dat [!DNL Payment Services] werkt zoals verwacht.

U kunt testen [!DNL Payment Services] bij de productie op twee manieren:

* Kies een tijdstip waarop je weet dat kopers geen bestellingen plaatsen.
* Gebruik een webwinkel die tijdelijk niet toegankelijk is voor kopers, maar die u wel kunt testen.

Voltooi uw productietests met echte creditcards en PayPal-rekeningen en test de volledige levenscyclus van een betaling, inclusief het vastleggen en terugbetalen. Als u het hele afrekenen en de betalingsstroom tijdens de tests uitvoert, krijgt u een duidelijk beeld van hoe uw [!DNL Payment Services] Deze functionaliteit werkt wanneer actieve kopers deze gebruiken.

U moet ook controleren of de gegevens die op de bankafschriften staan voor de betalingsmethoden die u gebruikt bij het testen van de productie juist en verwacht zijn (inclusief de beschrijving van uw bedrijf).

Als je Apple Pay wilt testen in de productiemodus, moet je [registreer uw productiedomeinen](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain).
