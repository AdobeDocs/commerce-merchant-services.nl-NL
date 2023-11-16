---
title: Installeren [!DNL Data Connection]
description: Leer hoe u de [!DNL Data Connection] uit Adobe Commerce.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
role: Admin, Developer
feature: Install
source-git-commit: 2392cb4257f6efdcb8fc3e38c007148e03e338fd
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Installeren [!DNL Data Connection]

Voordat u de extensie installeert, [de voorwaarden opnieuw bekijken](overview.md#prereqs).

## De extensie installeren

De [!DNL Data Connection] de extensie is beschikbaar via de [Adobe Marketplace](https://commercemarketplace.adobe.com/magento-experience-platform-connector.html). Wanneer u deze extensie installeert vanaf de opdrachtregel van de server, wordt verbinding gemaakt met de Adobe Commerce-installatie als een [service](../landing/saas.md). Wanneer het proces is voltooid, **[!DNL Data Connection]** en **Commerce Services Connector** worden weergegeven op **Systeem** menu onder **Services** in de handel _Beheerder_.

>[!IMPORTANT]
>
>Terwijl de naam van de extensie is gewijzigd van Experience Platform-aansluiting in [!DNL Data Connection]blijft de pakketnaam `experience-platform-connector` om achterwaartse verenigbaarheid te steunen.

1. Als u het dialoogvenster `experience-platform-connector` pakket, voer het volgende uit vanaf de bevellijn:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Dit metapakket bevat de volgende modules en extensies:

   * `module-experience-connector-admin` - Werkt de interface van Admin bij zodat kunt u identiteitskaart DataStream voor een specifieke instantie van Adobe Commerce selecteren.
   * `module-experience-connector` - Hiermee stelt u de `Organization ID` en `datastreamId` in de Storefront Events SDK.
   * `data-services` - Biedt kenmerkcontext voor storefront-gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.
   * `services-id` - Verbindt uw Adobe Commerce-instantie met [Adobe Commerce SaaS](../landing/saas.md) het gebruiken van zandbak en productie API sleutels en aan de Adobe Experience Platform om IMS Organisatie ID terug te winnen.
   * `orders-connector` - Verbindt de bestelstatusservice met uw Adobe Commerce-exemplaar.

1. (Optioneel) Opnemen [!DNL Live Search] gegevens, die [zoekgebeurtenissen](events.md#search-events), installeert u de [[!DNL Live Search]](../live-search/install.md) extensie.

1. (Optioneel) B2B-gegevens op te nemen, die [aanvraaggebeurtenissen](events.md#b2b-events), installeert u de [B2B-extensie](#install-the-b2b-extension).

### De connector voor bestellingen configureren

Nadat u de `experience-platform-connector` extensie, moet u de installatie van de `orders-connector` op basis van het implementatietype: op locatie of Adobe Commerce op Cloud-infrastructuur.

#### In de bedrijfsruimten

In omgevingen op locatie moet u handmatig het genereren van code en Adobe Commerce Events inschakelen:

```bash
bin/magento events:generate:module
bin/magento module:enable Magento_AdobeCommerceEvents
bin/magento setup:upgrade
bin/magento setup:di:compile
bin/magento config:set adobe_io_events/eventing/enabled 1
```

#### Cloud-infrastructuur

Schakel in Adobe Commerce op Cloud-infrastructuur de optie `ENABLE_EVENTING` algemene variabele in `.magento.env.yaml`. [Meer informatie](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/configure/env/stage/variables-global.html#enable_eventing).

```bash
stage:
   global:
      ENABLE_EVENTING: true
```

Pas bijgewerkte bestanden toe op de cloud-omgeving en druk ze op deze bestanden. Wanneer de plaatsing wordt gebeëindigd, laat het verzenden van gebeurtenissen met het volgende bevel toe:

```bash
bin/magento config:set adobe_io_events/eventing/enabled 1
```

### De B2B-extensie installeren

Installeer voor B2B-handelaren de volgende extensie om deze ook te kunnen gebruiken [aanvraaglijst](events.md#b2b-events) gebeurtenisgegevens.

Download de `magento/experience-platform-connector-b2b` extensie door het volgende uit te voeren vanaf de opdrachtregel:

```bash
composer require magento/experience-platform-connector-b2b
```

## Werk de [!DNL Data Connection] extension {#update}

Als u het dialoogvenster [!DNL Data Connection] extensie, voert u de volgende handelingen uit vanaf de opdrachtregel:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

Of, voor B2B-handelaren:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
```

Als u een update wilt uitvoeren naar een belangrijke versie, bijvoorbeeld van 2.0.0 tot 3.0.0, bewerkt u de hoofdmap van het project [!DNL Composer] `.json` bestand als volgt:

1. De hoofdmap openen `composer.json` bestand en zoek naar `magento/experience-platform-connector`.

1. In de `require` het versienummer als volgt bijwerken:

   ```json
   "require": {
      ...
      "magento/experience-platform-connector": "^3.0",
      ...
    }
   ```

1. **Opslaan** `composer.json`. Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/experience-platform-connector –-with-dependencies
   ```

   Of, voor B2B-handelaren:

   ```bash
   composer update magento/experience-platform-connector-b2b --with-dependencies
   ```

## De installatie van de [!DNL Data Connection] extension {#uninstall}

Als u het dialoogvenster [!DNL Data Connection] extensie, verwijzen naar [modules verwijderen](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html).
