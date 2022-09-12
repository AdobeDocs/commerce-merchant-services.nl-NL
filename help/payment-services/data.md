---
title: Beschikbare gegevens
description: Gebruik gegevens over financiële verslaglegging om rapportage te combineren met systemen voor niet-handel.
role: User
level: Intermediate
source-git-commit: ed471f363546f1d337e85568dc5079cae4507840
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Beschikbare gegevens

U beschikt over bepaalde bestellingen en uitbetalingsgegevens, zodat u de financiële rapportage van Adobe Commerce op externe systemen kunt coördineren.

## Wisselen met ERP-systeem

U kunt de financiële rapportage van Adobe Commerce afstemmen op uw ERP-systeem (Enterprise Resource Planning) dat niet van de Adobe is, met de verhogende id die aan een specifieke bestelling is gekoppeld.

Wanneer de betalingsservices de handelsorder naar PayPal verzendt, wordt de verhogingsid opgenomen als de `custom_id` _en_ in de `invoice_id` (die ook een willekeurige tekenreeks na de `increment_id`).

De id&#39;s zijn gemakkelijk toegankelijk in zowel de zakelijke activiteitengegevens voor een betaling als in de PayPal-website.

De `invoice_id` en `custom_id` worden onder aan de detailhandel weergegeven voor een uitbetaling:

![`custom_id` in detail van de handelsactiviteit](assets/merchant-activity-ids.png)

`custom_id` en `invoice_id` in de details op de website van PayPal:

```json
   ...
   {
    "id": "4E855005GK253170H",
    "intent": "AUTHORIZE",
    "status": "COMPLETED",
    "payment_source": {
        ...
    },
    "purchase_units": [
        {
            ...
            "custom_id": "000001322",
            "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
            ...
            "payments": {
                "authorizations": [
                    {
                       ...
                        "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
                        "custom_id": "000001322",
                        ...
                    }
                ],
                "captures": [
                    {
                        ...
                        "invoice_id": "000001322-c01bd7c3-920f-4542-a900-738082177e92",
                        "custom_id": "000001322",
                        ...
                    }
                ]
            }
        }
    ],
    "payer": {
        ...
    },
    "create_time": "2022-09-12T14:59:01Z",
    "update_time": "2022-09-12T14:59:45Z",
    "links": [
        ...
    ]
}
   ...
```

Zie de REST APIs-documentatie van PayPal voor meer informatie:

* [`purchase_unit`, waarin `custom_id` en `invoice_id` woonachtig](https://developer.paypal.com/docs/api/orders/v2/#definition-purchase_unit:~:text=Read%20only.-,purchase_unit,-Collapse)
* [Bestellingsgegevens tonen](https://developer.paypal.com/docs/api/orders/v2/#orders_get)
