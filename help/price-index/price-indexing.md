---
title: Prijsindexering SaaS
description: De SaaS Price Indexing gebruiken om prestaties te verbeteren
seo-title: Adobe SaaS Price Indexing
seo-description: Price indexing give performance improvements using SaaS infrastructure
exl-id: 5b92d6ea-cfd6-4976-a430-1a3aeaed51fd
source-git-commit: 8230756c203cb2b4bdb4949f116c398fcaab84ff
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Prijsindexering SaaS

SaaS-indexering verbetert de prestaties van de site doordat zware computerprocessen, zoals indexering en prijsberekening, van de Commerce-toepassing naar de cloudinfrastructuur van de Adobe worden verplaatst. Op deze manier kunnen handelaren hun resources snel vergroten om de indexatietijden van de prijzen te versnellen en zo de prijswijzigingen sneller te weerspiegelen wanneer ze gegevens naar de winkel en de verbonden Commerce-services verzenden.

Het volgende diagram toont de indexerende gegevensstroom aan de diensten SaaS wanneer Commerce het [ prijs indexerende ](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/manage-indexers) proces inbegrepen in de toepassing van Commerce gebruikt:

![ Standaardgegevensstroom ](assets/old_way.png)

Als SaaS-prijsindexering is ingeschakeld, verandert de gegevensstroom. Het indexeren van de prijs wordt uitgevoerd gebruikend [ de gegevensuitvoer van Commerce SaaS ](../data-export/data-synchronization.md).

![ SaaS prijs indexerende gegevensstroom ](assets/new_way.png)

Alle handelaren kunnen van het gebruiken van prijsindexeren SaaS profiteren, maar de handelaren die projecten met de volgende kenmerken hebben kunnen de grootste winst realiseren:

* **Constante prijsveranderingen** - Merchants die herhaalde veranderingen in hun prijzen vereisen om strategische doelstellingen zoals frequente bevorderingen, seizoensgebonden kortingen, of inventarisdalingen te ontmoeten.
* **Veelvoudige websites en/of klantengroepen** - Merchants met gedeelde productcatalogi over veelvoudige websites (domeinen/brands) en/of klantengroepen.
* **Vele unieke prijzen over websites of klantengroepen** - Merchants met uitgebreide gedeelde productcatalogi die unieke prijzen over websites of klantengroepen bevatten. Voorbeelden zijn B2B-handelaren met vooraf onderhandelde prijzen of merken met verschillende prijsstrategieën.

## Prijsindexering SaaS gebruiken

De prijsindexering van SaaS wordt automatisch toegelaten wanneer u de Diensten van Adobe Commerce installeert. Het ondersteunt prijsberekening voor alle ingebouwde Adobe Commerce-producttypen.

### Vereisten

* Adobe Commerce 2.4.4+

### Vereisten

* Een van de volgende Commerce Services moet worden geïnstalleerd met de nieuwste versie van de Commerce-extensie:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/overview.md)
   * [Product Recommendations](../product-recommendations/guide-overview.md)


>[!NOTE]
>
>Indien nodig, kan de standaardprijsindex in de toepassing van Commerce worden onbruikbaar gemaakt gebruikend de [ Adapter van de Catalogus ](catalog-adapter.md).

## Prijzen synchroniseren met prijsindexering in SaaS

Nadat het toelaten van de prijsindexering van SaaS voor Adobe Commerce, werk prijzen op Storefront en in de Diensten van Commerce door de nieuwe voer te synchroniseren bij:

```bash
bin/magento saas:resync --feed=scopesCustomerGroup
bin/magento saas:resync --feed=scopesWebsite
bin/magento saas:resync --feed=prices
```

### Prijzen voor aangepaste productsoorten

Prijsberekeningen worden ondersteund voor aangepaste producttypen zoals basisprijs, speciale prijs, groepsprijs, catalogusregelprijs enzovoort.

Als u een aangepast producttype hebt dat een specifieke formule gebruikt om de uiteindelijke prijs te berekenen, kunt u het gedrag van de feed van de productprijs uitbreiden.

1. Maak een plug-in voor de klasse `Magento\ProductPriceDataExporter\Model\Provider\ProductPrice` .

   ```xml
   <config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
           xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
       <type name="Magento\ProductPriceDataExporter\Model\Provider\ProductPrice">
           <plugin name="custom_type_price_feed" type="YourModule\CustomProductType\Plugin\UpdatePriceFromFeed" />
       </type>
   </config>
   ```

1. Maak een methode met de aangepaste formule:

   ```php
   class UpdatePriceFromFeed
   {
       /**
       * @param ProductPrice $subject
       * @param array $result
       * @param array $values
       *
       * @return array
       */
       public function afterGet(ProductPrice $subject, array $result, array $values) : array
       {
           // Override the output $result with your data for the corresponding products (see original method for details) 
           return $result;
       }
   }
   ```

