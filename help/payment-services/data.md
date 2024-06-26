---
title: Beschikbare gegevens
description: Gebruik gegevens over financiële verslaggeving om rapportage te combineren met niet-Commerce-systemen.
role: User
level: Intermediate
exl-id: dbf41ce9-01f9-45d0-b651-e4c499e83822
feature: Payments, Checkout, Data Import/Export
source-git-commit: 9a933d41bffc2af453eed00caeb941eb18b23852
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---

# Beschikbare gegevens

U beschikt over bepaalde bestellingen en uitbetalingsgegevens, zodat u de financiële rapportage van Adobe Commerce op externe systemen kunt coördineren.

## Wisselen met ERP-systeem

U kunt de financiële rapportage van Adobe Commerce afstemmen op uw ERP-systeem (Enterprise Resource Planning) dat niet van de Adobe is, met de verhogende id die aan een specifieke bestelling is gekoppeld.

Wanneer betalingsservices de Commerce-bestelling naar PayPal sturen, wordt de verhogingsid opgenomen als de `custom_id` _en_ in de `invoice_id` (die ook een willekeurige tekenreeks na de `increment_id`).

De id&#39;s zijn gemakkelijk toegankelijk in zowel de zakelijke activiteitengegevens voor een betaling als in de PayPal-website.

De `invoice_id` en `custom_id` worden onder aan de detailhandel weergegeven voor een uitbetaling:

![`custom_id` in detail van de handelsactiviteit](assets/merchant-activity-ids.png){width="600" zoomable="yes"}

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

* [`purchase_unit`, waarin `custom_id` en `invoice_id` woonachtig](https://developer.paypal.com/docs/api/orders/v2/#definition-purchase_unit)
* [Bestellingsgegevens tonen](https://developer.paypal.com/docs/api/orders/v2/#orders_get)
