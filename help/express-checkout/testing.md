---
title: Het testen van [!DNL Express Checkout] voor Adobe Commerce-extensie
description: Testen en valideren zorgt ervoor dat de [!DNL Express Checkout] de extensie werkt zoals u had verwacht.
exl-id: 308f39e1-e2f6-40d8-b876-0f9013effed3
source-git-commit: d8302d2d652b4e2380cc862183e58cbd2cca831b
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Het testen van [!DNL Express Checkout] voor Adobe Commerce-extensie

>[!IMPORTANT]
>
> Deze functie is alleen bedoeld voor gebruikers van het programma Early Introducter (EAP) en is nog niet voor alle klanten toegankelijk. Momenteel beperkt tot Amerikaanse klanten. Neem contact op met Adobe Commerce Support voor hulp en vragen.

Voordat u de [!DNL Express Checkout] voor Adobe Commerce-extensie voor uw klanten wordt aangeraden om te testen in een sandbox-omgeving en in uw productieomgeving. Testen en valideren zorgt ervoor dat de [!DNL Express Checkout] werkt zoals verwacht en biedt een naadloze afrekenervaring voor uw winkel en klanten.

Voordat u de [!DNL Express Checkout] in uw Adobe Commerce Admin is het vereist om een [productie](https://merchant.bolt.com/register){target=&quot;_blank&quot;} en [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} zakelijke account in Bolt.

## Testen in sandbox

Het testen van [!DNL Express Checkout] in een sandbox-omgeving is een zeer belangrijke validatiestap, ook al is het een gesimuleerde omgeving die alleen is verbonden met de Bolt-sandbox-account, niet met echte banken of handelaren.

### Sandboxaccount gebruiken

Wanneer u de sandbox test en valideert, moet u een onecht creditcardnummer en een [sandbox](https://merchant-sandbox.bolt.com/register){target=&quot;_blank&quot;} zakelijke account in Bolt, zodat u geen echte kosten maakt voor een bestaande creditcardaccount.

## Testen in productie

>[!NOTE]
>
> U wordt ten zeerste aangeraden de [!DNL Express Checkout] in een productieomgeving, met echte kredietkaarten en banken, voordat de uitbreiding wordt opengesteld voor kopers. Hoewel het testen in sandbox belangrijk is, is het testen in productie de meest misleidende methode om ervoor te zorgen dat het werkt zoals verwacht.

Aanbevolen om op twee manieren in productie te testen:

- Kies een tijdstip waarop je weet dat kopers geen bestellingen plaatsen.
- Gebruik een webwinkel die tijdelijk niet toegankelijk is voor kopers, maar die u wel kunt testen.

Voltooi uw productietests met echte creditcards en Bolt-productierekeningen en test de volledige levenscyclus van een afhandeling. Wanneer u de volledige afrekenstroom voltooit tijdens het testen, krijgt u een duidelijk beeld van de werking van uw functionaliteit wanneer live kopers deze gebruiken.

U moet ook controleren of de gegevens die op de bankafschriften staan voor de betalingsmethoden die u gebruikt bij het testen van de productie juist en verwacht zijn (inclusief de beschrijving van uw bedrijf).

## Hoe wordt de [!DNL Express Checkout] extension

Voer de volgende stappen uit om een afhandeling uit uw winkel te voltooien:

1. Ga naar je winkel en plaats de gewenste objecten in je winkelwagentje.
1. Ga door met de kassa.
1. Voer een e-mailadres in dat aan een Bolt-account is gekoppeld wanneer hierom wordt gevraagd.
1. Voer het eenmalige wachtwoord (OTP) in dat naar het e-mailadres van het account is verzonden.
1. Selecteer het omgevingsdashboard:

   - Sandbox
   - Productie

1. Place Order.

Zodra een bestelling is geplaatst, kunt u de details van uw bestellingen in uw _Raster voor bestellingen_ weergave:

1. Navigeren naar _Verkoop_ > _Orders_.
1. Zie een lijst met alle geplaatste bestellingen.

Zie de [orders](https://docs.magento.com/user-guide/sales/orders.html) onderwerp voor meer informatie over uw _Raster voor bestellingen_ weergeven.
