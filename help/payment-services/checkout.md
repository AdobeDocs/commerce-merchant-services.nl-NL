---
title: Afhandeling
description: Afhandeling aanpassen aan de behoeften van uw klant.
feature: Payments, Checkout
source-git-commit: 90bfa7099924feb308397960cff76bdf177bbe49
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Afhandeling

U kunt het afrekenen voor Adobe Commerce configureren [!DNL Payment Services] voor optimaal gebruik van de winkels. Functionaliteit zoals [automatisch ongeldig maken bestellen](#order-auto-voided-if-error) en [creditcard vauleren](#credit-card-vaulting) zorgt ervoor dat de gebruikers een vloeiende gebruikerservaring hebben.

## Volgorde automatisch ongeldig maken als er een fout optreedt

Als tijdens het uitchecken een fout optreedt, [!DNL Payment Services] Hiermee wordt de bestelling automatisch gewist of geannuleerd.

Er wordt een foutbericht weergegeven op de uitcheckpagina voor de winkelier. Het bericht kan variëren.

![Fout tijdens controleren](assets/user-checkout-error.png "Fout tijdens uitchecken")

Een opmerking over de geannuleerde volgorde wordt ook weergegeven in Beheer voor een specifieke [bestellen](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/order-management/orders/orders.html?lang=en).

![Opmerking voor geannuleerde bestelling in Admin](assets/admin-checkout-error.png "Opmerking voor geannuleerde bestelling in Admin")

Als een klant toestemming voor een bestelling krijgt, maar de bestelling niet is gemaakt en omgezet in een `Capture`, de volgorde is automatisch ongeldig. Dit proces zorgt ervoor dat er geen krediet op de creditcard van de winkels wordt gereserveerd en vermijdt de provisie voor de betalingsaanbieder die ontstaat wanneer de machtiging aan het einde van de standaardperiode van 29 dagen wordt ingetrokken.

>[!NOTE]
>
>Automatisch intrekken van bestellingen wordt alleen uitgevoerd wanneer de klant een betalingsmethode gebruikt die is ingesteld op `Authorize` modus, niet `Authorize and Capture` -modus.

## Afhandeling vanaf productpagina

Wanneer een klant rechtstreeks vanaf de productpagina uitcheckt via PayPal of [!DNL Pay Later] knoppen, alleen het item dat op de huidige productpagina wordt weergegeven, wordt aangeschaft. Objecten die al in de winkelwagentje van de klant staan, worden niet aan de afrekenstroom toegevoegd en niet aangeschaft.

Met deze functie kan de klant snel het object kopen dat hij of zij momenteel bekijkt, terwijl de eerder aan zijn of haar winkelwagentje toegevoegde items behouden blijven.
Als de klant de bestelling annuleert, wordt het item op de huidige productpagina toegevoegd aan de winkelwagentje van de klant.

Wanneer een klant de afrekenstroom op de productpagina invoert, wordt de afhandelingspagina vereenvoudigd. In de weergave worden alleen gegevens en opties weergegeven die betrekking hebben op de volgorde.

## Creditcard vaulting

Klanten kunnen hun creditcardgegevens voor toekomstige aankopen op websiteniveau (elke winkel binnen dezelfde zakelijke account) invullen (of &quot;opslaan&quot;).

Zie [Creditcard vaulting](vaulting.md) voor meer informatie
