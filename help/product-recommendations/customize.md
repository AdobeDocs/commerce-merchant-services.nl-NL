---
title: Aanpassen
description: Leer hoe u uw productaanbevelingen kunt aanpassen.
exl-id: b1b8e770-45ec-4403-b79b-4f0a9f7bd959
source-git-commit: acfaa1d72265e42b973677a7e014ba4b350ec56b
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Aanpassen

Wanneer u de Product Recommendations-module installeert, maakt Adobe Commerce de `ProductRecommendationsLayout` directory. Deze map bevat sjabloonbestanden die u kunt aanpassen om de weergave van de aanbevelingen in de winkel te wijzigen. Met name kunt u de volgende sjabloon wijzigen of overschrijven:

`<your theme>/Magento_ProductRecommendationsLayout/web/template/recommendations.html`

Voor meer informatie over het wijzigen van malplaatjedossiers, verwijs naar [Sjabloonaanpassing](https://developer.adobe.com/commerce/frontend-core/guide/templates/walkthrough/) in de Frontend Developer Guide.

Als u de `recommendations.html` , moet u de volgende tags in het bestand behouden om ervoor te zorgen dat Adobe Commerce gegevens over aanbevelingen kan verzamelen van uw winkel:

| Tag | Gebruiken |
|---|---|
| `<div data-bind="attr : {'data-unit-id' : unitId }"...</div>` | Verzamelt weergavegebeurtenissen. |
| `<a data-bind="attr : {'data-sku' : sku, 'data-unit-id'}"...</a>` | Verzamelt klikgebeurtenissen. <br/>**Opmerking:** Als u ankerlabels toevoegt, moet u deze kenmerken opnemen. |

Naast de `recommendations.html` bestand, de `ProductRecommendationsLayout` map bevat de volgende submappen:

| Map | Doel |
|---|---|
| `layout` | Bevat `*.xml` bestanden voor elk paginatype |
| `templates` | Bevat bestanden die scripts ophalen en renderen |
| `web/js` | Bevat de JavaScript-bestanden die aanbevelingen voor uw winkel opvragen en weergeven |
| `web/template` | Bevat de sjabloon voor de `magento/product-recommendations` module |

## Positie van de aanbevolen eenheid

Wanneer u [maken](create.md) een aanbeveling, geeft u de [locatie](placement.md) waar deze op de pagina wordt weergegeven. Een aanbevolen eenheid kan boven of onder aan de hoofdinhoudscontainer worden geplaatst. U kunt deze plaatsing echter aanpassen. Als u een type van de aanbeveling van de Bouwer van de Pagina adviserende inhoudstype creeert, gebruik de hulpmiddelen van de Bouwer van de Pagina om de aanbeveling op de pagina te plaatsen. Voor alle andere paginatypen bewerkt u de `*.xml` bestanden die worden gegenereerd wanneer de aanbeveling wordt gemaakt.

1. Wijzigen in de `layout` map:

   ```bash
   cd `<your theme>/Magento_ProductRecommendationsLayout/layout`
   ```

   In de volgende tabel worden de XML-bestanden weergegeven die zich in deze map bevinden:

   | Bestandsnaam | Pagina |
   |---|---|
   | `catalog_category_view.xml` | Categorie |
   | `catalog_product_view.xml` | Productdetails |
   | `checkout_cart_index.xml` | Kar |
   | `checkout_onepage_success.xml` | Afhandeling |
   | `cms_index_index.xml` | Home |

   >[!NOTE]
   >
   >De bestandsnamen in het dialoogvenster `layout` directory kan verschillen als in uw winkel extensies van derden worden gebruikt.

1. De `catalog_product_view.xml` zodat de aanbevolen eenheid wordt weergegeven na de productafbeelding op de pagina met productdetails. Voordat u dit XML-bestand aanpast, bekijkt u het bestand en begrijpt u welke secties u moet wijzigen:

   ```xml
   <?xml version="1.0"?>
   <page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
       <referenceBlock name="page.wrapper">
           <block class="Magento\Framework\View\Element\Template" before="-" name="product_recommendations_fetcher" template="Magento_ProductRecommendationsStorefront::fetcher.phtml" />
       </referenceBlock>
       <body>
           <referenceBlock name="main.content">
               <block class="Magento\ProductRecommendationsStorefront\Block\Renderer" after="-" name="product_recommendations_product_below_content" template="Magento_ProductRecommendationsStorefront::renderer.phtml">
                   <arguments>
                       <argument name="pagePlacement" xsi:type="string">below-main-content</argument>
                   </arguments>
               </block>
           </referenceBlock>
       </body>
   </page>
   ```

   In het bovenstaande fragment worden de `main.content` verwijzingsblok geeft aan dat de aanbevolen eenheid ergens ten opzichte van dat element wordt geplaatst. haar `block` element contains the `after="-"` kenmerk, dat aangeeft dat de aanbevolen eenheid na het hoofdinhoudsblok op de pagina wordt weergegeven.

1. We wijzigen dit bestand door een ander inhoudsblok op te geven.

   Het verwijzingsblok wijzigen `name` van `main.content` tot `product.info.media`.

   ```xml
   <?xml version="1.0"?>
   <page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
       <referenceBlock name="page.wrapper">
           <block class="Magento\Framework\View\Element\Template" before="-" name="product_recommendations_fetcher" template="Magento_ProductRecommendationsStorefront::fetcher.phtml" />
       </referenceBlock>
       <body>
           <referenceBlock name="product.info.media">
               <block class="Magento\ProductRecommendationsStorefront\Block\Renderer" after="-" name="product_recommendations_product_below_content" template="Magento_ProductRecommendationsStorefront::renderer.phtml">
                   <arguments>
                       <argument name="pagePlacement" xsi:type="string">below-main-content</argument>
                   </arguments>
               </block>
           </referenceBlock>
       </body>
   </page>
   ```

   Deze wijziging leidt ertoe dat uw aanbevolen eenheid wordt weergegeven na de productafbeelding op de pagina met productdetails. Als u de aanbevolen eenheid wilt weergeven voor de `product.info.media`wijzigt u de `after="-"` kenmerk naar `before="-"`. De `pagePlacement` argument is een intern argument dat niet mag worden gewijzigd.

Zie [overzicht van layout](https://developer.adobe.com/commerce/frontend-core/guide/layouts/) voor meer informatie over de typen blokken op de pagina.

## Aangepaste productkenmerken

Ontwikkelaars hebben vaak toegang nodig tot aangepaste productkenmerkwaarden in aanbevolen eenheden op winkelcentra, zodat ze visuele behandelingen kunnen toevoegen aan producten die op die kenmerken zijn gebaseerd.

Als uw winkel bijvoorbeeld bepaalde biologische producten verkoopt, hebt u mogelijk een aangepast kenmerk op die producten waarin ze worden aangeduid als `Organic = Yes`. Mogelijk hebt u toegang tot deze kenmerkwaarde op de winkel nodig, zodat u deze producten een speciale visuele behandeling kunt geven wanneer ze in Recommendations worden weergegeven. Op dezelfde manier staat de toegang tot deze waarden van de douaneproductattributen u toe om producten te badge of douanelogica in de presentatielaag van uw plaats te drijven.

![Badge toevoegen](assets/unit-custom.png)

Als u er zeker van wilt zijn dat een aangepast productkenmerk beschikbaar is wanneer u de aanbevolen eenheid op de pagina rendert, stelt u de optie `Used in Product Listing` eigenschap aan `Yes` in de [Productkenmerken](https://experienceleague.adobe.com/docs/commerce-admin/catalog/product-attributes/create/attribute-product-create.html) in Admin.

Wanneer deze eigenschap is ingesteld, bevat de JSON-payload een `attributes` object dat een array van kenmerkcodes en -waarden bevat. Vervolgens kunt u aangepaste opmaakcodes voor winkels toepassen op basis van deze kenmerkwaarden, zoals speciale visuele behandelingen of badges toevoegen zoals eerder vermeld.

>[!NOTE]
>
>Wijzigingen in productkenmerken kunnen maximaal een uur duren voordat ze worden weergegeven in de JSON-payload.
