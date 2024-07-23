---
title: SaaS-gegevens voor het exporteren van gegevens uitbreiden en aanpassen
description: Leer hoe te om de  [!DNL SaaS Data Export]  voedergegevens uit te breiden en aan te passen.
role: Admin, Developer
recommendations: noCatalog
source-git-commit: 51238f86f36a756b86d07bdf6bb0a5cf0c61cbeb
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# SaaS-gegevens voor het exporteren van gegevens uitbreiden en aanpassen

De extensie [!DNL Commerce Data Export] biedt een manier om gegevens uit de [!DNL Commerce] -toepassing te exporteren naar Commerce Services, zoals Live zoeken, Catalog Service en Product Recommendations. Indien nodig kunt u de voedergegevens uitbreiden en aanpassen om extra gegevens op te nemen of de verzamelde gegevens wijzigen door de module `Magento\CatalogDataExporter` bij te werken.

>[!NOTE]
>
>Het toevoegen van nieuwe gegevens aan de feed of het wijzigen van bestaande gegevens kan van invloed zijn op de prestaties van de voederverzameling en problemen veroorzaken in de verwerkingslogica aan de Adobe Commerce-zijde. Zorg ervoor dat u de aangepaste code test voordat u gaat samenvoegen met een productieomgeving.

## Kenmerkgegevens in de productfeed uitbreiden

Het diervoeder bevat standaardkenmerken die vereist zijn voor productverwerking of die algemeen door consumenten worden gebruikt. U kunt extra systeemkenmerken in de productfeed opnemen door deze aan de feed toe te voegen.

Om deze taak te voltooien, werk de `magento/catalog-data-exporter` module bij om de extra systeemattributen aan het [ dossier van de de configuratieconfiguratie van de gebiedsdeelinjectie ](https://developer.adobe.com/commerce/php/development/build/dependency-injection-file/) toe te voegen (`di.xml`). Voeg de attributen aan de vraag van het Attribuut van het Product toe (`Magento\CatalogDataExporter\Model\Query\ProductAttributeQuery`).

**Voorbeeld**

```xml
    <type name="Magento\CatalogDataExporter\Model\Query\ProductAttributeQuery">
        <arguments>
            <argument name="systemAttributes" xsi:type="array">
                <item name="news_from_date" xsi:type="string">news_from_date</item>
                ...
                <item name="some_system_attribute_code">some_system_attribute_code</item>
            </argument>
        </arguments>
    </type>
```
