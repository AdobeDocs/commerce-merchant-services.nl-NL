---
title: Beschikbare gegevens
description: Gebruik gegevens over financiële verslaglegging om rapportage te combineren met systemen voor niet-handel.
role: User
level: Intermediate
source-git-commit: 1186b4e52f1d613332a7862c58f482c2591e29a8
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Beschikbare gegevens

U beschikt over bepaalde bestellingen en uitbetalingsgegevens, zodat u de financiële rapportage van Adobe Commerce op externe systemen kunt coördineren.

## Wisselen met ERP-systeem

U kunt de financiële rapportage van Adobe Commerce afstemmen op uw ERP-systeem (Enterprise Resource Planning) dat niet van de Adobe is, met de verhogende id die aan een specifieke bestelling is gekoppeld.

Wanneer de betalingsservices de handelsorder naar PayPal verzendt, wordt de verhogingsid opgenomen als de `custom_id`. De `custom_id` is zichtbaar in de detailhandelsactiviteiten voor een uitbetaling en in de PayPal-website.

`custom_id` onder aan het detailhandelsbedrijf voor een uitbetaling:

![`custom_id` in detail van de handelsactiviteit](assets/merchant-activity.png)

`custom_id` in de details op de website van PayPal:

```json
   ...
   },
   "seller_protection": {
   "status": "NOT_ELIGIBLE"
   },
   "create_time": "2022-08-28T21:06:53Z",
   "custom_id": "000000829",
   "supplementary_data": {
   "related_ids":

   { "authorization_id": "6WW957787A749904A", "order_id": "3SV13726F9525791J" }
   },
   ...
```

Zie de REST APIs-documentatie van PayPal voor meer informatie:

* [`purchase_unit` waarin `custom_id` woonwijken](https://developer.paypal.com/docs/api/orders/v2/#definition-purchase_unit:~:text=Read%20only.-,purchase_unit,-Collapse)
* [Bestellingsgegevens tonen](https://developer.paypal.com/docs/api/orders/v2/#orders_get)
