---
title: Adobe Experience Platform-connector installeren en configureren vanuit Adobe Commerce
description: Leer hoe u de Adobe Experience Platform-connector van Adobe Commerce installeert, configureert, bijwerkt en verwijdert.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
source-git-commit: 898d49cbeb4711862a47693a0d608b74730dc845
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# De aansluiting van het Experience Platform installeren en configureren

Voordat u de extensie installeert, [de voorwaarden opnieuw bekijken](overview.md#prereqs).

## De extensie installeren

De de schakelaaruitbreiding van het Experience Platform is beschikbaar bij [Adobe Marketplace](https://marketplace.magento.com/magento-experience-platform-connector.html). Wanneer u deze extensie installeert vanaf de opdrachtregel van de server, wordt verbinding gemaakt met de Adobe Commerce-installatie als een [service](../landing/saas.md). Wanneer het proces is voltooid, **Experience Platform Connector** en **Commerce Services Connector** op de **Systeem** menu onder **Services** in de handel _Beheer_.

>[!NOTE]
>
>![B2B voor Adobe Commerce](../assets/b2b.svg) Voor B2B-handelaren is er een aparte extensie die u moet installeren. Deze extensie voegt ondersteuning toe voor B2B-specifieke gebeurtenissen. [Meer informatie](#install-the-b2b-extension).


1. Als u het dialoogvenster `experience-platform-connector` pakket, voer het volgende uit vanaf de bevellijn:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Dit metapakket bevat de volgende modules en extensies:

   * `module-experience-connector-admin` - Werkt de Admin UI bij zodat kunt u identiteitskaart DataStream voor een specifiek Adobe Commerce geval selecteren
   * `module-experience-connector` - Hiermee stelt u de `Organization ID` en `datastreamId` in de Storefront Events SDK
   * `data-services` - Biedt kenmerkcontext voor storefront-gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.
   * `services-id` - Verbindt uw Adobe Commerce-instantie met [Adobe Commerce SaaS](../landing/saas.md) het gebruiken van zandbak en productie API sleutels en aan de Adobe Experience Platform om IMS Organisatie ID terug te winnen

1. (Optioneel) Opnemen [!DNL Live Search] installeer de [[!DNL Live Search]](../live-search/install.md) extensie.

### De B2B-extensie installeren

Installeer voor B2B-handelaren de volgende extensie om deze ook te kunnen gebruiken [aanvraaglijst](events.md#b2b-events) gebeurtenisgegevens.

Download de `magento/experience-platform-connector-b2b` extensie via de opdrachtregel:

```bash
composer require magento/experience-platform-connector-b2b
```

## De aansluiting van het Experience Platform bijwerken {#update}

Als u de aansluiting van het Experience Platform wilt bijwerken, voert u het volgende uit vanaf de opdrachtregel:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

of, voor B2B-handelaren:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
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

   of, voor B2B-handelaren:

   ```bash
   composer update magento/experience-platform-connector-b2b --with-dependencies
   ```

## De aansluiting van het Experience Platform verwijderen {#uninstall}

Als u de aansluiting van het Experience Platform wilt verwijderen, raadpleegt u [modules verwijderen](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html).
