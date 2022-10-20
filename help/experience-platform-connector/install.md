---
title: Adobe Experience Platform-connector installeren en configureren vanuit Adobe Commerce
description: Leer hoe u de Adobe Experience Platform-connector van Adobe Commerce installeert, configureert, bijwerkt en verwijdert.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: bd1cf8a3b4740594cf6b8678d899d771a886cb2e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# De aansluiting van het Experience Platform installeren en configureren

Voordat u de extensie installeert, [de voorwaarden opnieuw bekijken](overview.md#prereqs).

## De extensie installeren

De verbindingsuitbreiding van het Experience Platform wordt geïnstalleerd vanaf de bevellijn van de server en verbindt met uw installatie van Adobe Commerce als a [service](../landing/saas.md). Wanneer het proces is voltooid, **Experience Platform Connector** verschijnt op de **Systeem** menu onder **Services** in de handel _Beheer_.

De aansluiting van het Experience Platform is geïnstalleerd als een uitbreiding van [Adobe Marketplace](https://marketplace.magento.com/magento-experience-platform-connector.html).

1. Als u het dialoogvenster `experience-platform-connector` pakket, voer het volgende uit vanaf de bevellijn:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Dit metapakket bevat de volgende modules en extensies:

   * `module-platform-connector-admin` - Werkt de Admin UI bij zodat kunt u identiteitskaart DataStream voor een specifiek Adobe Commerce geval selecteren
   * `module-platform-connector` - Hiermee stelt u de `Organization ID` en `datastreamId` in de Storefront Events SDK
   * `data-services` - Biedt kenmerkcontext voor storefront-gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.
   * `services-id` - Verbindt uw Adobe Commerce-instantie met [Adobe Commerce SaaS](../landing/saas.md) het gebruiken van zandbak en productie API sleutels en aan de Adobe Experience Platform om IMS Organisatie ID terug te winnen

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
