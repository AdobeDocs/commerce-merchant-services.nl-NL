---
title: productSearch query
description: "A reference guide for the ` productSearch` GraphQL query for Adobe Commerce Catalog Service."
source-git-commit: 49692cf4375ebb975b2cf132d21ac8debe609a90
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# productSearch query

De Catalogusservice voor Adobe Commerce `productSearch` De vraag kan Live Onderzoek gebruiken om details over SKUs terug te keren die als input worden gespecificeerd. Hoewel deze vraag het zelfde als is [`productSearch` query](https://devdocs.magento.com//live-search/product-search.html)Live zoeken geeft een `productView` object. Zie de [`productSearch` query](https://devdocs.magento.com//live-search/product-search.html) onderwerp voor verwijzingsinformatie.

## Syntaxis

```graphql
productSearch(
    phrase: String!
    page_size: Int = 20
    current_page: Int = 1
    filter: [SearchClauseInput!]
    sort: [ProductSearchSortInput!]
): ProductSearchResponse!
```

## Vereiste koppen

U moet de volgende HTTP-headers opgeven om deze query uit te voeren.

| Koptekst | Beschrijving |
|--- | ---|
| `Magento-Customer-Group` | Voor winkelklanten is deze waarde beschikbaar in de winkel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Deze waarde kan worden verkregen door het `bin/magento config:show services_connector/services_id/environment_id` gebruiken. Zie het veld &quot;Gegevensruimte&quot; in [Commerciële diensten](https://docs.magento.com/user-guide/configuration/services/saas.html) |
| `Magento-Store-Code` | De code die aan de opslag wordt toegewezen verbonden aan de actieve opslagmening. Bijvoorbeeld, `main_website_store`. |
| `Magento-Store-View-Code` | De code die aan de actieve archiefmening wordt toegewezen. Bijvoorbeeld, `default`. |
| `Magento-Website-Code` | De code die is toegewezen aan de website die is gekoppeld aan de actieve archiefweergave. Bijvoorbeeld, `base`. |
| `X-Api-Key` | Een unieke sleutel die wordt gegenereerd tijdens het instapproces. |

## Voorbeeld van gebruik

In het volgende voorbeeld, keert de vraag informatie over de zelfde producten zoals het vorige voorbeeld terug. Het is echter geconstrueerd om itemgegevens in de Catalogusservice te retourneren `productView` object in plaats van de kern `product` object. De prijsinformatie varieert, afhankelijk van het producttype. Ter wille van de beknoptheid wordt geen informatie over facetten weergegeven.

**Verzoek:**

```graphql
{
  productSearch(
    phrase: "bag"
    sort: [
      {
        attribute: "price"
        direction: DESC }]
    page_size: 9
  ) {
    page_info {
      current_page
      page_size
      total_pages
    }
    items {
      productView {
        name
        sku
        ... on SimpleProductView {
          price {
            final {
              amount {
                value
                currency
              }
            }
            regular {
              amount {
                value
                currency
              }
            }
          }
        }
        ... on ComplexProductView {
          options {
            id
            title
            required
            values {
              id
              title
            }
          }
          priceRange {
            maximum {
              final {
                amount {
                  value
                  currency
                }
              }
              regular {
                amount {
                  value
                  currency
                }
              }
            }
            minimum {
              final {
                amount {
                  value
                  currency
                }
              }
              regular {
                amount {
                  value
                  currency
                }
              }
            }
          }
        }
      }
    }
  }
}
```

**Reactie:**

```json
{
  "data": {
    "productSearch": {
      "page_info": {
        "current_page": 1,
        "page_size": 9,
        "total_pages": 3
      },
      "items": [
        {
          "productView": {
            "name": "Impulse Duffle",
            "sku": "24-UB02",
            "price": {
              "final": {
                "amount": {
                  "value": 74,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 74,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Fusion Backpack 567890",
            "sku": "24-MB02",
            "price": {
              "final": {
                "amount": {
                  "value": 59,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 59,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Rival Field Messenger",
            "sku": "24-MB06",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Push It Messenger Bag",
            "sku": "24-WB04",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Overnight Duffle",
            "sku": "24-WB07",
            "price": {
              "final": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 45,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Wayfarer Messenger Bag 987",
            "sku": "24-MB05",
            "price": {
              "final": {
                "amount": {
                  "value": 44,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 44,
                  "currency": "USD"
                }
              }
            }
          }
        },
        {
          "productView": {
            "name": "Driven Backpack",
            "sku": "24-WB03",
            "price": {
              "final": {
                "amount": {
                  "value": 36,
                  "currency": "USD"
                }
              },
              "regular": {
                "amount": {
                  "value": 36,
                  "currency": "USD"
                }
              }
            }
          }
        }
      ]
    }
  }
}
```
