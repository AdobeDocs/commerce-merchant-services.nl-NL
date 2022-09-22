---
title: productquery
description: "A reference guide for the ` products` GraphQL query for Adobe Commerce Catalog Service."
source-git-commit: d9b8c89f6d04aa9d569b450af2893b92938119ad
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# productquery

De Catalogusservice voor Adobe Commerce `products` de vraag keert details over SKUs terug die als input wordt gespecificeerd. Hoewel deze query dezelfde naam heeft als de [`products` query](https://devdocs.magento.com/guides/v2.4/graphql/queries/products.html) die met Adobe Commerce en Magento Open Source wordt geleverd, zijn er enkele verschillen.

De vraag van de Dienst van de Catalogus vereist één of meerdere waarden SKU als input. De vraag wordt hoofdzakelijk ontworpen om informatie terug te winnen om de volgende types van inhoud terug te geven:

* Pagina&#39;s met productdetails - U kunt volledige details over het product verstrekken dat door gespecificeerde SKU wordt geïdentificeerd.

* Productvergelijkingspagina&#39;s - U kunt geselecteerde informatie ophalen over meerdere producten, zoals de naam, prijs en afbeelding.

De `ProductView` uitvoerobject is aanzienlijk anders dan de kern `products` query `Products` uitvoerobject. Tot de belangrijkste verschillen behoren:

* Producten zijn eenvoudig of complex. Eenvoudige, virtuele, downloadbare en cadeaukaartproducten worden toegewezen aan `SimpleProductView`. Alle andere producttypen worden toegewezen aan `ComplexProductView`. Eenvoudige producten hebben prijzen gedefinieerd. Complexe producten hebben prijsbereiken. Omdat complexe producten uit meerdere eenvoudige producten bestaan, hebben zij toegang tot eenvoudige productprijzen.

* Merchant-bepaalde attributen worden blootgesteld in een top-level container en wijzen op hun storefront rollen. Rollen omvatten Tonen op PDP, Tonen op PLP en Tonen op zoekresultaten.

* Afbeeldingen zijn ook toegankelijk als container op hoofdniveau en kunnen door hun rol worden gefilterd. Een afbeelding kan een basis-, kleine of miniatuurrol hebben.

## Syntaxis

```graphql
products (skus [String]) [ProductView]
```

## Vereiste koppen

U moet de volgende HTTP-headers opgeven om deze query uit te voeren.

| Koptekst | Beschrijving |
| --- | --- |
| `Magento-Customer-Group` | Voor winkelklanten is deze waarde beschikbaar in de winkel `dataservices_customer_group` cookie. |
| `Magento-Environment-Id` | Deze waarde wordt weergegeven op **Systeem** > **Commerce Services Connector** > **SaaS-id** > **Data Space ID** of kan worden verkregen door het `bin/magento config:show services_connector/services_id/environment_id` gebruiken. |
| `Magento-Store-Code` | De code die aan de opslag wordt toegewezen verbonden aan de actieve opslagmening. Bijvoorbeeld, `main_website_store`. |
| `Magento-Store-View-Code` | De code die aan de actieve archiefmening wordt toegewezen. Bijvoorbeeld, `default`. |
| `Magento-Website-Code` | De code die is toegewezen aan de website die is gekoppeld aan de actieve archiefweergave. Bijvoorbeeld, `base`. |
| `X-Api-Key` | Een unieke sleutel die wordt gegenereerd tijdens het instapproces. |

## Voorbeeld van gebruik

### Details retourneren over een eenvoudig product

De volgende vraag keert details over een eenvoudig product terug.

**Verzoek:**

```graphql
query {
  products(skus: ["24-MB02"]) {
    id
    sku
    name
    url
    description
    shortDescription
    attributes(roles: ["visible in Search"]) {
      name
      label
      value
      roles
    }
    ... on SimpleProductView {
      price {
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
```

**Reactie:**

```json
{
  "data": {
    "products": [
      {
        "id": "TWpRdFRVSXdNZwBaR1ZtWVhWc2RBAE16UmxNamMwTUdFdE56UTNNeTAwWXpnNUxUZzNNekF0TlRjME1ETm1ZMlV5TjJGbABiV0ZwYmw5M1pXSnphWFJsWDNOMGIzSmwAWW1GelpRAFRVRkhVMVJITURBMU5UYzVNRE00",
        "sku": "24-MB02",
        "name": "Fusion Backpack 567890",
        "url": "http://example.com/fusion-backpack.html",
        "description": "<p>With the Fusion Backpack strapped on, every trek is an adventure - even a bus ride to work. That's partly because two large zippered compartments store everything you need, while a front zippered pocket and side mesh pouches are perfect for stashing those little extras, in case you change your mind and take the day off.</p>\r\n<ul>\r\n<li>Durable nylon construction.</li>\r\n<li>2 main zippered compartments.</li>\r\n<li>1 exterior zippered pocket.</li>\r\n<li>Mesh side pouches.</li>\r\n<li>Padded, adjustable straps.</li>\r\n<li>Top carry handle.</li>\r\n<li>Dimensions: 18\" x 10\" x 6\".</li>\r\n</ul>",
        "shortDescription": "",
        "attributes": [
          {
            "name": "activity",
            "label": "Activity",
            "value": [
              "Hiking",
              "School",
              "Yoga"
            ],
            "roles": [
              "visible in PDP",
              "visible in compare list",
              "visible in Search"
            ]
          },
          {
            "name": "features_bags",
            "label": "Features",
            "value": [
              "Hydration Pocket",
              "Audio Pocket",
              "Waterproof",
              "Lightweight"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "material",
            "label": "Material",
            "value": [
              "Burlap",
              "Nylon",
              "Polyester"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "strap_bags",
            "label": "Strap/Handle",
            "value": [
              "Adjustable",
              "Double",
              "Padded"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "style_bags",
            "label": "Style Bags",
            "value": [
              "Backpack",
              "Laptop"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          }
        ],
        "price": {
          "regular": {
            "amount": {
              "value": 59,
              "currency": "USD"
            }
          }
        }
      }
    ]
  }
}
```

### Details retourneren over een complex product {#complex-product-example}

De volgende vraag keert details over een configureerbaar product terug.

**Verzoek:**

```graphql
query {
  products(skus: ["MH12"]) {
    __typename
    id
    sku
    name
    url
    description
    shortDescription
    attributes(roles: ["visible in Search"]) {
      name
      label
      value
      roles
    }
    ... on ComplexProductView {
      priceRange {
        maximum {
          regular {
            amount {
              value
              currency
            }
          }
        }
        minimum {
          regular {
            amount {
              value
              currency
            }
          }
        }
      }
      options {
        id
        required
        title
        values {
          id
          title
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
    "products": [
      {
        "__typename": "ComplexProductView",
        "id": "VFVneE1nAFpHVm1ZWFZzZEEATXpSbE1qYzBNR0V0TnpRM015MDBZemc1TFRnM016QXROVGMwTURObVkyVXlOMkZsAGJXRnBibDkzWldKemFYUmxYM04wYjNKbABZbUZ6WlEAVFVGSFUxUkhNREExTlRjNU1ETTQ",
        "sku": "MH12",
        "name": "Ajax Full-Zip Sweatshirt 2",
        "url": "http://example.com/ajax-full-zip-sweatshirt.html",
        "description": "<p>The Ajax Full-Zip Sweatshirt makes the optimal layering or outer piece for archers, golfers, hikers and virtually any other sportsmen. Not only does it have top-notch moisture-wicking abilities, but the tight-weave fabric also prevents pilling from repeated wash-and-wear cycles.</p>\r\n<p>&bull; Mint striped full zip hoodie.<br />&bull; 100% bonded polyester fleece.<br />&bull; Pouch pocket.<br />&bull; Rib cuffs and hem. <br />&bull; Machine washable.</p>",
        "shortDescription": "",
        "attributes": [
          {
            "name": "climate",
            "label": "Climate",
            "value": [
              "All-Weather",
              "Cool",
              "Indoor",
              "Spring",
              "Windy"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "customattribute",
            "label": "customAttribute",
            "value": "asd",
            "roles": [
              "visible in PDP",
              "visible in PLP",
              "visible in Search"
            ]
          },
          {
            "name": "material",
            "label": "Material",
            "value": [
              "Fleece",
              "Polyester"
            ],
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "pattern",
            "label": "Pattern",
            "value": "Striped",
            "roles": [
              "visible in PDP",
              "visible in Search"
            ]
          },
          {
            "name": "testtttattribute",
            "label": "testtttAttribute",
            "value": "asd",
            "roles": [
              "visible in PDP",
              "visible in PLP",
              "visible in Search"
            ]
          }
        ],
        "priceRange": {
          "maximum": {
            "regular": {
              "amount": {
                "value": 69,
                "currency": "USD"
              }
            }
          },
          "minimum": {
            "regular": {
              "amount": {
                "value": 69,
                "currency": "USD"
              }
            }
          }
        },
        "options": [
          {
            "id": "color",
            "required": false,
            "title": "Color",
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
          },
          {
            "id": "size",
            "required": false,
            "title": "Size",
            "values": [
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzU=",
                "title": "XS"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzY=",
                "title": "S"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzc=",
                "title": "M"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzg=",
                "title": "L"
              },
              {
                "id": "Y29uZmlndXJhYmxlLzE4Ni8xNzk=",
                "title": "XL"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

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
