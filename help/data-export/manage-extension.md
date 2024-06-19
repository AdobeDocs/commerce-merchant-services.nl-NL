---
title: "[!DNL Manage the Data Export extension]"
description: "Leer hoe u een upgrade van de [!DNL Data Export] en om de diensten van de gegevensuitvoer te verwijderen of onbruikbaar te maken die niet worden vereist."
role: Admin, Developer
recommendations: noCatalog
source-git-commit: 8230756c203cb2b4bdb4949f116c398fcaab84ff
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# De SaaS-extensie voor gegevensexport beheren

De [!DNL data export] De uitbreiding voor de diensten SaaS is een inzameling van modules die gegevensinzameling en synchronisatie tussen Adobe Commerce en de verbonden Diensten van Commerce toelaten.

Specifieke modules zijn opgenomen in de metapakketten voor Adobe Commerce Services-extensies, zoals [Live zoeken](/help/live-search/overview.md), [Product Recommendations](/help/product-recommendations/overview.md), en [Catalogusservice](/help/catalog-service/overview.md). Als u deze diensten gebruikt, wordt geen afzonderlijke installatie vereist om de uitbreiding van de Uitvoer van Gegevens toe te laten.

## Functies voor het exporteren van Commerce-gegevens verwijderen of uitschakelen

Als u één van de geïnstalleerde modules van de de uitvoer van handelsgegevens niet nodig hebt, gebruik `magento:module:disable` CLI bevel om het onbruikbaar te maken.

Er is bijvoorbeeld een [Categorie-API](https://developer.adobe.com/commerce/services/graphql/catalog-service/categories/) dat de categorietoestemming intern gegevens gebruikt. Als u deze API niet gebruikt, kunt u de gegevensexport uitschakelen voor de feed voor categorietoestemming.

```shell script
bin/magento module:disable Magento_CategoryPermissionDataExporter Magento_SaaSCategoryPermissions
```

### Een module bijwerken naar een specifieke versie

U kunt om het even welke geïnstalleerde modules van de de uitvoer van handelsgegevens bijwerken door Composer te gebruiken. U kunt bijvoorbeeld een module bijwerken naar een opgegeven versie en ook de vereiste afhankelijkheden bijwerken.

1. Log in bij de Commerce-toepassingsserver.

1. Werk de module bij met behulp van Composer vanaf de opdrachtregel:

   ```bash
   composer require magento/module-saas-price:103.3.1 --with-all-dependencies
   ```

Als de Commerce-instantie wordt geïmplementeerd op de Cloud-infrastructuur, werkt u de extensie bij vanuit de cloud-projectmap. Zie [Een extensie upgraden](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/configure-store/extensions#upgrade-an-extension) in de _Adobe Commerce on Cloud Infrastructure Guide_.




