---
title: Adobe Experience Platform-connector installeren en configureren vanuit Adobe Commerce
description: Leer hoe u de Adobe Experience Platform-connector van Adobe Commerce installeert, configureert, bijwerkt en verwijdert.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: ce437d7a991affd2665c86c9e91bb7f39ec626c0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Experience Platform-aansluiting installeren en configureren

Voordat u de extensie installeert, [de voorwaarden opnieuw bekijken](overview.md#prereqs).

## De extensie installeren

1. Installeer de metapakket voor de aansluiting van het Experience Platform.

   ```bash
   composer require magento/experience-platform-connector
   ```

   Dit metapakket bevat de volgende modules en extensies:

   * `module-platform-connector-admin` - Werkt Admin UI bij zodat kunt u identiteitskaart DataStream vormen
   * `module-platform-connector` - Hiermee stelt u de `ImsOrgId` en `datastreamId` in de Adobe Commerce Storefront Event SDK
   * `data-services` - Biedt kenmerkcontext voor storefront-gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.
   * `commerce-services` - Verbindt uw Adobe Commerce-instantie met [Adobe Commerce SaaS](../landing/saas.md) gebruik van sandbox- en productie-API-sleutels en naar de Adobe Experience Platform met behulp van de IMS-organisatie-id.

1. (Optioneel) Opnemen [!DNL Live Search] installeer de [[!DNL Live Search]](../live-search/install.md) extensie.

## De aansluiting van het Experience Platform bijwerken {#update}

Als u de aansluiting van het Experience Platform wilt bijwerken, voert u het volgende uit vanaf de opdrachtregel:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

Als u wilt bijwerken naar een hoofdversie zoals 1.0.0 tot 2.0.0, bewerkt u de hoofdmap van het project [!DNL Composer] `.json` bestand als volgt:

1. De hoofdmap openen `composer.json` bestand en zoek naar `magento/platform-connector`.

1. In de `require` het versienummer als volgt bijwerken:

   ```json
   "require": {
      ...
      "magento/experience-platform-connector": "^2.0",
      ...
    }
   ```

1. **Opslaan** `composer.json`. Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/experience-platform-connector –-with-dependencies
   ```

## De aansluiting van het Experience Platform verwijderen {#uninstall}

Als u de aansluiting van het Experience Platform wilt verwijderen, raadpleegt u [modules verwijderen](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html).
