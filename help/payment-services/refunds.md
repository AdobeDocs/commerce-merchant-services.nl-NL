---
title: Restituties
description: Restituties maken voor [!DNL Payment Services] orders in de beheerder als onderdeel van het kredietmemo-proces.
exl-id: 2b3721a1-9c9d-4e3f-ab7d-5bd61573dcb4
source-git-commit: fd818dadbaa2a58efd7313ce888c7dda27d25f14
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Restituties

Restituties voor [!DNL Payment Services] orders worden in de beheerder gemaakt als onderdeel van het creditmemo-proces. Een creditnota is een document dat het bedrag toont dat aan de klant, voor een volledige of gedeeltelijke terugbetaling verschuldigd is, die op een aankoop kan worden toegepast of direct aan de klant kan worden teruggegeven. Creditmemo&#39;s kunnen alleen worden uitgegeven voor orders die [gefactureerd](https://docs.magento.com/user-guide/sales/invoice-create.html){target="_blank"}.

Zie [Creditnota&#39;s](https://docs.magento.com/user-guide/sales/credit-memos.html){target="_blank"} in onze basisgebruikershandleiding voor meer informatie en voor meer informatie over het uitgeven en afdrukken van creditnota&#39;s.

Voor bestellingen die met PayPal of een creditcard worden verwerkt, kunt u:

* Het volledige bedrag van de bestelling terugbetalen
* Een gedeeltelijk bedrag van een bestelling terugbetalen (of meerdere gedeeltelijke bedragen)
* Een bedrag terugbetalen dat lager is dan de waarde van een specifiek orderitem

Zie [Een creditmemo uitgeven](https://docs.magento.com/user-guide/sales/credit-memo-create.html){target="_blank"} in onze basisgebruikershandleiding voor meer informatie.

>[!NOTE]
>
>Er treedt een fout op bij bestellingen die met PayPal of een creditcard zijn verwerkt als u probeert een bestelling gedeeltelijk te retourneren voor meer dan het resterende bedrag van de bestelling (oorspronkelijk bedrag minus het totaal van de bestaande terugbetalingen), of als u een terugbetaling geeft voor een bedrag dat groter is dan het volledige bedrag van de bestelling.

De [!UICONTROL Payment Action] instellen in uw [!UICONTROL Payment Settings] configuratie—Willekeurig `Authorize` of `Authorize and Capture`—bepaalt de [basisworkflow voor restitutie](https://docs.magento.com/user-guide/sales/credit-memos.html#refund-workflow){target="_blank"} voor orders.

Zie de [Sectie voor betalingsactie](https://docs.magento.com/user-guide/sales/credit-memo-create.html#payment-action-setting){target="_blank"} van _Een creditmemo uitgeven_ voor meer informatie .
