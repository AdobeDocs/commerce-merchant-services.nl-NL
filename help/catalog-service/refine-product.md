---
title: refineProduct-query
description: "A reference guide for the ` refineProduct` GraphQL query for Adobe Commerce Catalog Service."
source-git-commit: 7edfdd71c0900a6bdc7c064a29a6cce405a361ab
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 0%

---


# refineProduct-query

De `refineProduct` query maakt de resultaten van een `products` query die werd uitgevoerd tegen een complex product. Voordat u het dialoogvenster `refineProduct` query, u moet de opdracht uitvoeren `products` vraag en construeer de reactie zodat het een lijst van terugkeert `options` binnen een `ComplexProductView` inline-fragment. Wanneer een winkelier een productoptie (zoals grootte of kleur) in de winkel selecteert, voert u de opdracht `refineProduct` vraag, die SKU en geselecteerde optie specificeert - waarde IDs als input. Afhankelijk van het aantal productopties dat het complexe product heeft, moet u mogelijk het `refineProduct` vraag veelvoudige tijden, tot de verkoopster een specifieke variant heeft geselecteerd.

U zou de reactie van uw vraag moeten construeren zodat het zowel bevat `ComplexProductView` en `SimpleProductView` inline-fragmenten. Als de verkoper niet alle vereiste opties heeft geselecteerd, zal de vraag IDs van unselected opties en de minimum en maximumprijs van het product terugkeren, die op de geselecteerde opties en mogelijke resterende opties wordt gebaseerd. Als de verkoper alle vereiste opties heeft geselecteerd, keert de vraag details over een eenvoudig product terug, dat een vastgestelde prijs omvat.

## Syntaxis

```graphql
refineProduct(sku: String!, optionIds: [String!]!): ProductView
```

## Vereiste koppen

U moet de volgende HTTP-headers opgeven om deze query uit te voeren.

| Koptekst | Beschrijving |
|--- | ---|
| `Magento-Customer-Group` | Voor winkelklanten is deze waarde beschikbaar in de winkel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Deze waarde wordt weergegeven op **Systeem** > **Commerce Services Connector** > **SaaS-id** > **Data Space ID** of kan worden verkregen door het `bin/magento config:show services_connector/services_id/environment_id` gebruiken. |
| `Magento-Store-Code` | De code die aan de opslag wordt toegewezen verbonden aan de actieve opslagmening. Bijvoorbeeld, `main_website_store`. |
| `Magento-Store-View-Code` | De code die aan de actieve archiefmening wordt toegewezen. Bijvoorbeeld, `default`. |
| `Magento-Website-Code` | De code die is toegewezen aan de website die is gekoppeld aan de actieve archiefweergave. Bijvoorbeeld, `base`. |
| `X-Api-Key` | Een unieke sleutel die wordt gegenereerd tijdens het instapproces. |

## Voorbeeld van gebruik

### Details retourneren over een gedeeltelijk geselecteerd complex product

De volgende vraag keert details over de kleurenopties beschikbaar voor een middelgrote variant van product terug `MH12`. De waarde van de `optionIDs` invoerparameter wordt ontleend aan `products` query&#39;s [Details retourneren over een complex product](products.md#complex-product-example) voorbeeld.

**Verzoek:**

```graphql
query {
    refineProduct(optionIds: ["Y29uZmlndXJhYmxlLzE4Ni8xNzc="], sku: "MH12") {
        __typename
        id
        sku
        name
        url
        ... on SimpleProductView {
            price {
                final {
                    amount {
                        value
                    }
                }
                regular {
                    amount {
                        value
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
                        }
                    }
                    regular {
                        amount {
                            value
                        }
                    }
                }
                minimum {
                    final {
                        amount {
                            value
                        }
                    }
                    regular {
                        amount {
                            value
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
    "refineProduct": {
      "__typename": "ComplexProductView",
      "id": "VFVneE1nAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
      "sku": "MH12",
      "name": "Ajax Full-Zip Sweatshirt 2",
      "url": "http://example.com/ajax-full-zip-sweatshirt.html",
      "options": [
        {
          "id": "color",
          "title": "Color",
          "required": false,
          "values": [
            {
              "id": "Y29uZmlndXJhYmxlLzkzLzU5",
              "title": "Blue"
            },
            {
              "id": "Y29uZmlndXJhYmxlLzkzLzY3",
              "title": "Red"
            },
            {
              "id": "Y29uZmlndXJhYmxlLzkzLzYy",
              "title": "Green"
            }
          ]
        }
      ],
      "priceRange": {
        "maximum": {
          "final": {
            "amount": {
              "value": 69
            }
          },
          "regular": {
            "amount": {
              "value": 69
            }
          }
        },
        "minimum": {
          "final": {
            "amount": {
              "value": 69
            }
          },
          "regular": {
            "amount": {
              "value": 69
            }
          }
        }
      }
    }
  }
}
```

### Details retourneren over een volledig geselecteerd complex product

In de volgende vraag, heeft de verkoopster opties voor zowel grootte als kleur geselecteerd. Het antwoord bevat details over het overeenkomstige eenvoudige product.

**Verzoek:**

```graphql
query {
    refineProduct(optionIds: ["Y29uZmlndXJhYmxlLzE4Ni8xNzc=", "Y29uZmlndXJhYmxlLzkzLzU5"], sku: "MH12") {
        __typename
        id
        sku
        name
        url
        ... on SimpleProductView {
            price {
                final {
                    amount {
                        value
                    }
                }
                regular {
                    amount {
                        value
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
                        }
                    }
                    regular {
                        amount {
                            value
                        }
                    }
                }
                minimum {
                    final {
                        amount {
                            value
                        }
                    }
                    regular {
                        amount {
                            value
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
    "refineProduct": {
      "__typename": "SimpleProductView",
      "id": "VFVneE1pMU5MVUpzZFdVAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
      "sku": "MH12-M-Blue",
      "name": "Ajax Full-Zip Sweatshirt -M-Blue",
      "url": "http://example.com/catalog/product/view/id/235/s/ajax-full-zip-sweatshirt-m-blue/",
      "price": {
        "final": {
          "amount": {
            "value": 69
          }
        },
        "regular": {
          "amount": {
            "value": 69
          }
        }
      }
    }
  }
}
```

## Invoervelden

U moet een SKU-waarde en ten minste één optie-id opgeven als invoer.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `optionIds` | [Tekenreeks!]! | Een lijst met id&#39;s die zijn toegewezen aan de productopties die de winkel heeft geselecteerd, zoals specifieke kleuren en grootten. |
| `sku` | Tekenreeks! | De SKU van een complex product. |

## Uitvoervelden

De `ProductView` retourobject is een interface die de volgende velden kan bevatten. Het wordt uitgevoerd door de [`SimpleProductView`](#SimpleProductView-type) en [`ComplexProductView`](#ComplexProductView-type) typen.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Een lijst met door de handelaar gedefinieerde kenmerken die is toegewezen aan de winkel. |
| `description` | String | De gedetailleerde beschrijving van het product. |
| `id` | ID! | De product-id, gegenereerd als een samengestelde sleutel, uniek per landinstelling. |
| `images(roles: [String])` | [ProductViewImage] | Een lijst met afbeeldingen die voor het product zijn gedefinieerd. |
| `metaDescription` | String | Een kort overzicht van het product voor aanbiedingen met zoekresultaten. |
| `metaKeyword` | String | Een door komma&#39;s gescheiden lijst met trefwoorden die alleen zichtbaar zijn voor zoekmachines. |
| `metaTitle` | String | Een tekenreeks die wordt weergegeven op de titelbalk en het tabblad van de browser en in de lijsten met zoekresultaten. |
| `name` | String | Productnaam. |
| `shortDescription` | String | Een samenvatting van het product. |
| `sku` | String | Product SKU. |
| `url` | String | Canonieke URL van het product. |

### Het type ComplexProductView {#ComplexProductView-type}

De `ComplexProductView` type vertegenwoordigt bundel, configureerbaar, en groepsproducten. Complexe productprijzen worden geretourneerd als een prijsklasse, omdat de prijswaarden kunnen variëren op basis van geselecteerde opties. Het type implements `ProductView`.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Een lijst met door de handelaar gedefinieerde kenmerken die is toegewezen aan de winkel. |
| `description` | String | De gedetailleerde beschrijving van het product. |
| `id` | ID! | De product-id, gegenereerd als een samengestelde sleutel, uniek per landinstelling. |
| `images(roles: [String])` | [ProductViewImage] | Een lijst met afbeeldingen die voor het product zijn gedefinieerd. |
| `metaDescription` | String | Een kort overzicht van het product voor aanbiedingen met zoekresultaten. |
| `metaKeyword` | String | Een door komma&#39;s gescheiden lijst met trefwoorden die alleen zichtbaar zijn voor zoekmachines. |
| `metaTitle` | String | Een tekenreeks die wordt weergegeven op de titelbalk en het tabblad van de browser en in de lijsten met zoekresultaten. |
| `name` | String | Productnaam. |
| `options` | [ProductViewOption] | Een lijst met selecteerbare opties. |
| `priceRange` | ProductViewPriceRange | Een reeks mogelijke prijzen voor een complex product. |
| `shortDescription` | String | Een samenvatting van het product. |

### Prijssoort

De `Price type` bepaalt de prijs van een eenvoudig product of een deel van een prijsklasse voor een complex product. Het kan een lijst van prijsaanpassingen bevatten.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `amount` | ProductViewMoney | Bevat de monetaire waarde en valutacode van een product. |

### Het type PriceAdjustment

De `PriceAdjustment` type geeft het bedrag en het type van een prijsaanpassing aan. Een codewaarde van het voorbeeld is `weee`.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `amount` | Float | Het bedrag van de prijsaanpassing. |
| `code` | String | Geeft het type prijsaanpassing aan. |

### Het type ProductViewAttribute

De `ProductViewAttribute` type is een container voor door de klant gedefinieerde kenmerken die in de winkel worden weergegeven.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `label` | String | Label van het kenmerk. |
| `name` | Tekenreeks! | Naam van een kenmerkcode. |
| `roles` | [String] | Rollen die zijn toegewezen voor een kenmerk in de winkel, zoals &#39;Tonen op PLP&#39;, &#39;Tonen in PDP&#39; of &#39;Tonen in Zoeken&#39;. |
| `value` | JSON | Kenmerkwaarde, willekeurig van type. |

### Het type ProductViewImage

De `ProductViewImage` type bevat details over een productafbeelding.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `label` | String | Het weergavelabel van de productafbeelding. |
| `roles` | [String] | Een lijst die beschrijft hoe de afbeelding wordt gebruikt. Kan `image`, `small_image`, of `thumbnail`. |
| `url` | Tekenreeks! | De URL naar de afbeelding van het product. |

### Het type ProductViewMoney

De `ProductViewMoney` type definieert een monetaire waarde, inclusief een numerieke waarde en een valutacode.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `currency` | ProductViewCurrency | Een drieletterige valutacode, zoals USD of EUR. |
| `value` | Float | Een getal dat een monetaire waarde uitdrukt. |

### Het type ProductViewOption

De opties van het product verstrekken een manier om producten te vormen door selecties van bepaalde optiewaarden te maken. Als u een of meerdere opties selecteert, wordt een specifiek eenvoudig product aangeduid.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `id` | ID | De id van de optie. |
| `multi` | Boolean | Geeft aan of de optie meerdere keuzen toestaat. |
| `required` | Boolean | Geeft aan of de optie moet worden geselecteerd. |
| `title` | String | De weergavenaam van de optie. |
| `values` | [ProductViewOptionValue!] | Lijst met beschikbare optiewaarden. |

### De interface ProductViewOptionValue

De `ProductViewOptionValue` interface definieert de productvelden die beschikbaar zijn voor de `ProductViewOptionValueProduct` en `ProductViewOptionValueConfiguration` typen.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `id` | ID | De id van een optiewaarde. |
| `title` | String | De weergavenaam van de waarde van de optie. |

### Het type ProductViewOptionValueConfiguration

De `ProductViewOptionValueConfiguration` type is een implementatie van `ProductViewOptionValue` voor configuratiewaarden.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `id` | ID | De id van een optiewaarde. |
| `title` | String | De weergavenaam van de waarde van de optie. |

### Het type ProductViewOptionValueProduct

De `ProductViewOptionValueProduct` type is een implementatie van `ProductViewOptionValue` dat details over een eenvoudig product toevoegt.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `id` | ID | De id van een optiewaarde. |
| `title` | String | De weergavenaam van de waarde van de optie. |
| `product` | SimpleProductView | Details over een eenvoudig product. |

### Het type ProductViewPrice

De `ProductViewPrice` type geeft de basisweergave van de productprijs weer, die inherent is aan eenvoudige producten.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `final` | Prijs | Prijswaarde na kortingen, exclusief gepersonaliseerde promoties. |
| `regular` | Prijs | Door de handelaar opgegeven basisproductprijs. |
| `roles` | [String] | Hiermee bepaalt u of de prijs zichtbaar of verborgen moet zijn. |

### Het type ProductViewPriceRange

De `ProductViewPriceRange` type geeft de minimum - en maximumprijs van een complex product weer .

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `maximum` | ProductViewPrice | Maximumprijs. |
| `minimum` | ProductViewPrice | Minimumprijs. |

### Het type SimpleProductView {#SimpleProductView-type}

De `SimpleProductView` type vertegenwoordigt alle producttypes, behalve bundel, configureerbaar, en groep. Eenvoudige productprijzen bevatten geen prijsmarges. `SimpleProductView` implements `ProductView`.

| Veld | Gegevenstype | Beschrijving |
|--- | --- | ---|
| `attributes(roles: [String])` | [ProductViewAttribute] | Een lijst met door de handelaar gedefinieerde kenmerken die is toegewezen aan de winkel. |
| `description` | String | De gedetailleerde beschrijving van het product. |
| `id` | ID! | De product-id, gegenereerd als een samengestelde sleutel, uniek per landinstelling. |
| `images(roles: [String])` | [ProductViewImage] | Een lijst met afbeeldingen die voor het product zijn gedefinieerd. |
| `metaDescription` | String | Een kort overzicht van het product voor aanbiedingen met zoekresultaten. |
| `metaKeyword` | String | Een door komma&#39;s gescheiden lijst met trefwoorden die alleen zichtbaar zijn voor zoekmachines. |
| `metaTitle` | String | Een tekenreeks die wordt weergegeven op de titelbalk en het tabblad van de browser en in de lijsten met zoekresultaten. |
| `name` | String | Productnaam. |
| `price` | ProductViewPrice | Weergave basisproductprijs. |
| `shortDescription` | String | Een samenvatting van het product. |
| `sku` | String | Product SKU. |
| `url` | String | Canonieke URL van het product. |
