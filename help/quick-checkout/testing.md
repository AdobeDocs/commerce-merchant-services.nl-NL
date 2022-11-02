---
title: "Testen van de [!DNL Quick Checkout] voor Adobe Commerce-extensie"
description: "Testen en valideren zorgt ervoor dat de [!DNL Quick Checkout] de extensie werkt zoals u had verwacht."
exl-id: 308f39e1-e2f6-40d8-b876-0f9013effed3
source-git-commit: bd02a8083d3f4c9cb0422b27d61bd5462187ffc3
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---


# Test de [!DNL Quick Checkout] extension

Voordat u de [!DNL Quick Checkout] voor Adobe Commerce-extensie voor uw klanten wordt aangeraden om te testen in een sandbox-omgeving en in uw productieomgeving. Testen en valideren zorgt ervoor dat de [!DNL Quick Checkout] werkt zoals verwacht en biedt een naadloze afrekenervaring voor uw winkel en klanten.

Voordat u de [!DNL Quick Checkout] in Adobe Commerce Admin is het vereist om  [productie](https://merchant.bolt.com/register){target=&quot;_blank&quot;} en [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} zakelijke accounts in [!DNL Bolt].

## Testen in sandbox

Het testen van [!DNL Quick Checkout] in een sandboxomgeving is een zeer belangrijke validatiestap, ook al is het een gesimuleerde omgeving die alleen is verbonden met de [!DNL Bolt] sandboxrekening, niet aan echte banken of handelaren.

### Sandboxaccount gebruiken

Wanneer u de sandbox test en valideert, moet u een onecht creditcardnummer en een [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} zakelijke account in [!DNL Bolt], zodat u geen echte kosten maakt voor een bestaande creditcardrekening.

## Testen in productie

>[!NOTE]
>
> U wordt ten zeerste aangeraden de [!DNL Quick Checkout] in een productieomgeving, met echte kredietkaarten en banken, voordat de uitbreiding wordt opengesteld voor kopers. Hoewel het testen in sandbox belangrijk is, is het testen in productie de meest misleidende methode om ervoor te zorgen dat het werkt zoals verwacht.

Test uw productieomgeving op een van de volgende twee aanbevolen manieren:

- Kies een tijdstip waarop je weet dat kopers geen bestellingen plaatsen.
- Gebruik een webwinkel die tijdelijk niet toegankelijk is voor kopers, maar die u wel kunt testen.

Voltooi uw productietests met echte creditcards en [!DNL Bolt] productierekeningen, het testen van de volledige levenscyclus van een controle. Wanneer u tijdens het testen de volledige afrekenstroom hebt voltooid, krijgt u een duidelijk beeld van de werking van uw functionaliteit wanneer actieve kopers deze gebruiken.

U moet ook controleren of de gegevens die op de bankafschriften staan voor de betalingsmethoden die u gebruikt bij het testen van de productie juist en verwacht zijn (inclusief de beschrijving van uw bedrijf).

## Hoe wordt de [!DNL Quick Checkout] extension

Voltooi een geslaagde afhandeling uit je winkel:

1. Ga naar je winkel en plaats de gewenste objecten in je winkelwagentje.
1. Ga door met de kassa.
1. Voer een e-mailadres in dat is gekoppeld aan een [!DNL Bolt] account wanneer hierom wordt gevraagd.
1. Voer het eenmalige wachtwoord (OTP) in dat naar het e-mailadres van het account is verzonden.
1. Selecteer het omgevingsdashboard:

   - Sandbox
   - Productie

1. Plaats de bestelling.

Zodra een bestelling is geplaatst, kunt u de details van uw bestellingen in uw _Raster voor bestellingen_ weergave:

1. Navigeren naar _Verkoop_ > _Orders_.
1. Zie een lijst met alle geplaatste bestellingen.

Zie de [Orders](https://docs.magento.com/user-guide/sales/orders.html) onderwerp voor meer informatie over uw _Raster voor bestellingen_ weergeven.
