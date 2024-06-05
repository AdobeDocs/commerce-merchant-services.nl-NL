---
title: Prijsindexering SaaS
description: De SaaS Price Indexing gebruiken om prestaties te verbeteren
seo-title: Adobe SaaS Price Indexing
seo-description: Price indexing give performance improvements using SaaS infrastructure
exl-id: 5b92d6ea-cfd6-4976-a430-1a3aeaed51fd
source-git-commit: 7293914fab34381deb5bc841d147371f9f3470a5
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Prijsindexering SaaS

SaaS-prijsindexering versnelt de tijd die nodig is om prijswijzigingen door te voeren [Commerce Services](../landing/saas.md) nadat zij zijn ingediend. Op deze manier kunnen handelaren met grote, complexe catalogi of met meerdere websites of klantengroepen doorlopend prijswijzigingen verwerken.

Als u een koploze winkel hebt of de [catalogusadapter](./catalog-adapter.md) klanten kunnen SaaS Price Indexing gebruiken door de Adobe Commerce core price indexer uit te schakelen.

Computationele zware processen zoals indexering en prijsberekening zijn verplaatst van de Commerce-kern naar de Cloud-infrastructuur van Adobe. Op deze manier kunnen handelaren snel hun resources vergroten om de indexatietijden van de prijzen te verhogen en deze wijzigingen sneller te laten doorwerken.

De de indexerende gegevensstroom van de Kern aan de diensten van SaaS ziet als:

![Standaardgegevensstroom](assets/old_way.png)

Met SaaS-prijsindexering is de stroom:

![Prijsindexeringsgegevensstroom SaaS](assets/new_way.png)

Alle handelaren kunnen van deze verbeteringen profiteren, maar zij die de grootste winst zullen zien zijn klanten met:

* Constante prijswijzigingen: handelaren die herhaalde prijswijzigingen nodig hebben om strategische doelstellingen te bereiken, zoals veelvuldige promoties, seizoenskortingen of voorraadafwaarderingen.
* Meerdere websites en/of klantgroepen: verkopers met gedeelde productcatalogi op meerdere websites (domeinen/merken) en/of klantgroepen.
* Groot aantal unieke prijzen voor websites of klantgroepen: verkopers met uitgebreide gedeelde productcatalogi die unieke prijzen bevatten voor websites of klantgroepen, zoals B2B-verkopers met vooraf overeengekomen prijzen, merken met verschillende prijsstrategieën.

De prijsindexering van SaaS is gratis beschikbaar voor klanten die de diensten van Adobe Commerce gebruiken en steunt prijsberekening voor alle ingebouwde productsoorten van Adobe Commerce.

In deze handleiding wordt beschreven hoe SaaS-prijsindexering werkt en hoe deze kan worden ingeschakeld.

## Vereisten

* Adobe Commerce 2.4.4+
* Ten minste een van de volgende Commerce Services met de nieuwste versie van de Adobe Commerce-extensie:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/overview.md)
   * [Product Recommendations](../product-recommendations/guide-overview.md)

Gebruikers van Luma en Adobe Commerce Core GraphQL kunnen de [`catalog-adapter`](catalog-adapter.md) extensie die Luma en Core GraphQl-compatibiliteit biedt en de Adobe Commerce Product Price-index uitschakelt.

## Gebruik

Nadat u uw Adobe Commerce-exemplaar hebt geüpgraded met SaaS-ondersteuning voor prijsindexering, synchroniseert u de nieuwe feeds:

```bash
bin/magento saas:resync --feed=scopesCustomerGroup
bin/magento saas:resync --feed=scopesWebsite
bin/magento saas:resync --feed=prices
```

## Prijzen voor aangepaste productsoorten

Prijsberekeningen worden ondersteund voor aangepaste productsoorten zoals basisprijs, speciale prijs, groepsprijs, catalogusregelprijs enz.

Als u een aangepast producttype hebt dat een specifieke formule gebruikt om de uiteindelijke prijs te berekenen, kunt u het gedrag van de feed van de productprijs uitbreiden.

1. Een plug-in maken op het tabblad `Magento\ProductPriceDataExporter\Model\Provider\ProductPrice` klasse.

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
