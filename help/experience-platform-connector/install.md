---
title: Adobe Experience Platform-connector installeren en configureren vanuit Adobe Commerce
description: Leer hoe u de Adobe Experience Platform-connector van Adobe Commerce installeert, configureert, bijwerkt en verwijdert.
source-git-commit: 9b5f2da08167e22bbba504009bccc87d0ab02c48
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Experience Platform-aansluiting installeren en configureren

Voordat u de extensie installeert, [de voorwaarden opnieuw bekijken](overview.md#prereqs).

## De extensie installeren

1. Installeer de metapakket voor de aansluiting van het Experience Platform.

   ```bash
   composer require magento/platform-connector
   ```

   Dit metapakket bevat de volgende modules:

   * `module-platform-connector-admin` - Werkt de interface van Admin bij
   * `module-platform-connector` - Hiermee stelt u de `ImsOrgId` en `datastreamId` in de Magento Storefront Events SDK

1. Installeer de uitbreiding van de Diensten van de Gegevens van de Handel om profiel en controlegebeurtenissen te omvatten.

   ```bash
   composer require magento/data-services
   ```

   De uitbreiding van de Diensten van Gegevens van de Handel verstrekt attributencontext voor storefront gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.

1. Installeer de Commerce Service Connector.

   ```bash
   composer require magento/commerce-services
   ```

   Met de Commerce Service Connector kunt u uw Adobe Commerce-instantie verbinden met [Adobe Commerce SaaS](../landing/saas.md) en de Adobe Experience Platform.

1. (Optioneel) Opnemen [!DNL Live Search] installeer de [[!DNL Live Search]](../live-search/install.md) extensie.

## De aansluiting van het Experience Platform bijwerken {#update}

Als u de aansluiting van het Experience Platform wilt bijwerken, voert u het volgende uit vanaf de opdrachtregel:

```bash
composer update magento/platform-connector --with-dependencies
```

Als u wilt bijwerken naar een hoofdversie zoals 1.0.0 tot 2.0.0, bewerkt u de hoofdmap van het project [!DNL Composer] `.json` bestand als volgt:

1. De hoofdmap openen `composer.json` bestand en zoek naar `magento/platform-connector`.

1. In de `require` het versienummer als volgt bijwerken:

   ```json
   "require": {
      ...
      "magento/platform-connector": "^2.0",
      ...
    }
   ```

1. **Opslaan** `composer.json`. Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/platform-connector –-with-dependencies
   ```

## De aansluiting van het Experience Platform verwijderen {#uninstall}

Als u de aansluiting van het Experience Platform wilt verwijderen, raadpleegt u [modules verwijderen](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html).
