---
title: Aangepaste orderkenmerken toevoegen
description: Leer hoe u aangepaste orderkenmerken toevoegt aan uw gegevens op het achterkantoor en deze kenmerken naar het Experience Platform verzendt.
role: Admin, Developer
feature: Personalization, Integration
source-git-commit: 14d190726324e2f42d66c2270f2e27be5a74132f
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 2%

---

# Aangepaste orderkenmerken toevoegen

In dit artikel leert u hoe u aangepaste kenmerken kunt toevoegen aan back office-gebeurtenissen. Met aangepaste kenmerken kunt u rijke gegevensinzichten vastleggen om de analysemogelijkheden te verbeteren en persoonlijke ervaringen voor uw klanten verder te creëren.

Aangepaste kenmerken worden op twee niveaus ondersteund:

- Orderniveau
- Itemniveau bestellen

>[!NOTE]
>
>Adobe [!DNL Commerce] ondersteunt aangepaste kenmerken met een gegevenstype van een tekenreeks, Boolean of datum.

Wanneer u aangepaste kenmerken aan back office-gebeurtenissen toevoegt, moet u:

1. Maak een project in uw [!DNL Commerce] -installatie.
1. Werk uw schema bij zodat de nieuwe douanekenmerken behoorlijk in Experience Platform kunnen worden opgenomen.
1. Controleer in de beheerfunctie of de aangepaste kenmerken worden vastgelegd en verzonden naar het Experience Platform.

>[!IMPORTANT]
>
>De mapstructuur en de codevoorbeelden hieronder laten zien hoe u aangepaste kenmerken kunt implementeren. De daadwerkelijke vereiste folderstructuur en code hangt van uw archiefconfiguratie en milieu af.

## Stap 1: De mappenstructuur maken

1. Navigeer naar de map `app/code` in de [!DNL Commerce] -installatie en maak een modulemap. Bijvoorbeeld: `Magento/AepCustomAttributes` . Deze map bevat de bestanden die nodig zijn voor uw aangepaste kenmerken.
1. Maak een submap met de naam `etc` in de modulemap. De map `etc` bevat de bestanden `module.xml` , `query.xml` , `di.xml` en `et_schema.xml` .

## Stap 2: Bepaal de gebiedsdelen en de opstellingsversie

Maak een `module.xml` -bestand dat de afhankelijkheden en de instellingsversie definieert. Bijvoorbeeld:

```xml
<?xml version="1.0"?>
<!--
/**
* Copyright (c) [year], [name]. All rights reserved.
*/
-->
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Module/etc/module.xsd">
    <module name="Magento_SalesRuleStaging" setup_version="2.0.0">
        <sequence>
            <module name="Magento_Staging"/>
            <module name="Magento_SalesRule"/>
        </sequence>
    </module>
</config>
```

## Stap 3: Gegevens van de verkooporder ophalen

Maak een `query.xml` -bestand dat de gegevens van de verkooporder ophaalt. Bijvoorbeeld:

```xml
<query>
    <source name="sales_order" type="sales">
        <attribute name="increment_id" operator="eq" alias="order_increment_id"/>
        <link source="inventory_source_item" condition_type="by_sku"/>
    </source>
</query>
```

## Stap 4: De injectie voor afhankelijkheid instellen

Maak een `di.xml` -bestand waarmee de injectie van afhankelijkheid wordt ingesteld. Bijvoorbeeld:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
          package="com.example.instrumentedtest"
          android:versionCode="1"
          android:versionName="1.0">
    <uses-sdk android:minSdkVersion="8" android:targetSdkVersion="15"/>
    
    <instrumentation
        android:name=".MyInstrumentationTestRunner"
        android:targetPackage="com.example.instrumentedtest"/>
    
    <!-- More instrumentation elements might be here -->
</manifest>
```

## Stap 5: Bepaal de diensten die voor de gebiedsdeelinjectie worden gebruikt

Maak een `et_schema.xml` -bestand dat de services definieert die worden gebruikt voor het injecteren van afhankelijkheid. Bijvoorbeeld:

```xml
<services>
    <service id="App\Controller\MainController" class="App\Controller\MainController">
        <argument type="service" id="doctrine.orm.default_entity_manager"/>
        <argument type="service" id="form.factory"/>
        <argument type="service" id="security.authorization_checker"/>
    </service>

    <!-- ... -->

    <service id="App\Controller\SecurityController" class="App\Controller\SecurityController">
        <argument type="service" id="security.authentication_utils"/>
        <tag name="controller.service_arguments"/>
    </service>

    <!-- ... -->
</services>
```

## Stap 6: Een map maken voor de PHP-bestanden

Maak op hetzelfde niveau als de map `etc` een map met de naam `Module/Provider` . Deze map bevat de `OrderCustomAttributes` - en `OrderItemCustomAttributes` PHP-bestanden.

## Stap 7: Definieer de OrderCustomAttributes

Maak een `OrderCustomAttributes.php` -bestand dat de aangepaste orderkenmerken definieert. Bijvoorbeeld:

```php
namespace App\Transformers;

use League\Fractal\TransformerAbstract;
use Illuminate\Support\Collection;

class CustomAttributeTransformer extends TransformerAbstract
{
    protected $availableIncludes = [];
    protected $defaultIncludes = [];

    public function __construct($signsField, $jsonSignsField = null)
    {
        $this->signsField = $signsField;
        $this->jsonSignsField = $jsonSignsField;
    }

    public function transform(Collection $collection)
    {
        // Initialize array for additional information.
        $additionalInformation = [];

        // Source - this comes from values sent to this transformer.
        foreach ($collection->{$this->signsField} ?: [] as $value) {
            if (is_array($value)) {
                // If value is an array, serialize it.
                foreach ($value as &$item) {
                    if (isset($item['custom_attr'])) {
                        // Serialize custom attribute data.
                        ...
                    }
                }
            } else {
                // Add non-array values directly.
                ...
            }
        }

        ...

        return [
            'current' => ...,
            'additional_information' => ...,
            'source' => ...,
        ];
    }

    private function flatten(array $values)
    {
      return Arr::flatten($values);
  }
}
```

## Stap 8: Definieer de OrderItemCustomAttributes

Maak een `OrderItemCustomAttributes.php` -bestand dat de aangepaste kenmerken voor de items van de volgorde definieert. Bijvoorbeeld:

```php
namespace Magento\AepCustomAttributes\Model\Provider;

use Magento\Framework\Serialize\Serializer\Json;

class OrderItemCustomAttribute
{
    private Json $jsonSerializer;
    private string $usingField;

    public function __construct(Json $jsonSerializer, string $usingField)
    {
        $this->jsonSerializer = $jsonSerializer;
        $this->usingField = $usingField;
    }

    public function get(array $values): array
    {
        $output = [];
        $values = $this->flatten($values);

        foreach ($values as $row) {
            $info = \is_string($row['additionalInformation']) ? $row['additionalInformation'] : '{}';
            $unserializedData = $this->jsonSerializer->unserialize($info) ?? [];

            $attrLabel = implode(',', ['label1', 'label2']);
            $unserializedData['custom_attr1'] = $attrLabel;

            $additionalInformation = [];
            foreach ($unserializedData as $name => $value) {
                $additionalInformation[] = [
                    'name' => $name,
                    'value' => \is_string($value) ? $value : $this->jsonSerializer->serialize($value),
                ];
            }

            foreach ($additionalInformation as $information) {
                $output[] = [
                    'additionalInformation' => $information,
                    $this->usingField => $row[$this->usingField],
                ];
            }
        }

        return $output;
    }

    private function flatten(array $values): array
    {
        return array_merge([], ...array_values($values));
    }
}
```

## Stap 9: Maak een map voor het productContext-bestand

Maak op hetzelfde niveau als de map `etc` een map met de naam `Plugin/Module` . Deze map bevat het `ProductContext.php` -bestand.

## Stap 10: Bepaal de klasse ProductContext

Maak een bestand met de naam `ProductContext.php` dat de klasse `ProductContext` definieert. Bijvoorbeeld:

```php
namespace Magento\Catalog\Model\Product;

use Magento\Framework\App\ResourceConnection;
use Magento\Quote\Api\Data\CartInterface;

class ProductContext
{
    private $brandCache = [];
    private $resourceConnection;

    public function __construct(
        ResourceConnection $resourceConnection
    ) {
        $this->resourceConnection = $resourceConnection;
    }

    public function afterGetProductData($subject, array $result)
    {
        if (isset($result['brand_id'])) {
            if (!isset($this->brandCache[$result['brand_id']])) {
                // @todo load brand label by brand id.
                $this->brandCache[$result['brand_id']] = 'Brand Label ' . $result['brand_id'];
            }
            $result['brands'] = ['label' => $this->brandCache[$result['brand_id']]];
        }

        return $result;
    }
}
```

## Stap 11: Registreer de module

Maak op hetzelfde niveau als de map `etc` een `registration.php` -bestand dat de module registreert. Bijvoorbeeld:

```php
use \Magento\Framework\Component\ComponentRegistrar;

ComponentRegistrar::register(
    ComponentRegistrar::MODULE,
    'Dfe_Stripe',
    __DIR__
);
```

## Stap 12: Het bestaande XDM-schema uitbreiden

Als u er zeker van wilt zijn dat de nieuwe aangepaste orderkenmerken door uw [!DNL Commerce] -schema in het Experience Platform kunnen worden opgenomen, moet u het schema uitbreiden en deze aangepaste velden opnemen.

Leren hoe te om een bestaand schema uit te breiden XDM om deze douanegebieden te omvatten, zie [ schema&#39;s in het UI ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas#custom-fields-for-standard-groups) artikel in de documentatie van het Experience Platform creëren en uitgeven. Het veld Tenant-id wordt dynamisch gegenereerd, maar de veldstructuur moet overeenkomen met het voorbeeld in de documentatie bij het Experience Platform.

>[!IMPORTANT]
>
>Aangepaste XDM-kenmerken moeten overeenkomen met de kenmerken die vanuit [!DNL Commerce] worden verzonden.

Voeg aan `commerce.order` een veld toe voor Order-niveau:

![ Niveau van de Orde ](assets/order-level.png)

Voeg velden toe voor het itemniveau Volgorde aan `productListItems` :

![ het Niveau van het Punt van de Orde ](assets/order-item-level.png)

## Stap 12: Bevestig dat de gegevens worden vastgelegd

Bekijk het [ lusje van de Aanpassing van Gegevens ](connect-data.md#data-customization) in Admin om te bevestigen dat de gegevens van de douanekenmerken worden gevangen en naar het Experience Platform verzonden.

### Problemen oplossen

Bevestig het volgende als het bericht `No custom order attributes found.` wordt weergegeven op het tabblad **[!UICONTROL Data Customization]** :

1. U hebt de eerste vereisten voltooid om de [ uitbreiding van de Verbinding van Gegevens ](overview.md#prerequisites) toe te laten.
1. U hebt [ attributen van de douaneorde ](#add-custom-order-attributes) gevormd.
1. Er is ten minste één bestelgebeurtenis gegenereerd.
