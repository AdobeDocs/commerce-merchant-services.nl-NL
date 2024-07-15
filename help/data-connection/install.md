---
title: Installeren  [!DNL Data Connection]
description: Leer hoe te om, de  [!DNL Data Connection]  uitbreiding van Adobe Commerce te installeren bij te werken en te desinstalleren.
exl-id: e78e8ab0-8757-4ab6-8ee1-d2e137fe6ced
role: Admin, Developer
feature: Install
source-git-commit: 9001cd24db0941b7c7edcfd5b10464dc90084fd7
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Installeren [!DNL Data Connection]

Alvorens u de uitbreiding installeert, [ herzie de eerste vereisten ](overview.md#prereqs).

## De extensie installeren

De [!DNL Data Connection] uitbreiding is beschikbaar bij de [ Marketplace van de Adobe ](https://commercemarketplace.adobe.com/magento-experience-platform-connector.html). Wanneer u deze uitbreiding van de bevellijn van de server installeert, verbindt het met uw installatie van Adobe Commerce als a [ dienst ](../landing/saas.md). Wanneer het proces volledig is, **[!DNL Data Connection]** en **de Schakelaar van de Diensten van Commerce** verschijnen op het **4} menu van het Systeem onder** Diensten **in Commerce _Admin_.**

![[!DNL Data Connection] de mening van Admin van de uitbreiding ](assets/epc-adminui.png)

>[!IMPORTANT]
>
>Hoewel de naam van de extensie is gewijzigd van Experience Platform-aansluiting in [!DNL Data Connection] , blijft de pakketnaam `experience-platform-connector` om achterwaartse compatibiliteit te ondersteunen.

1. Voer de volgende handelingen uit vanaf de opdrachtregel om het pakket `experience-platform-connector` te downloaden:

   ```bash
   composer require magento/experience-platform-connector
   ```

   Dit metapakket bevat de volgende modules en extensies:

   * `module-experience-connector-admin` - Werkt de interface van Admin bij zodat kunt u identiteitskaart DataStream voor een specifieke instantie van Adobe Commerce selecteren.
   * `module-experience-connector` - Stelt de `Organization ID` en `datastreamId` in de Storefront Events SDK in.
   * `data-services` - Biedt kenmerkcontext voor storefront-gebeurtenissen. Wanneer bijvoorbeeld een uitcheckgebeurtenis plaatsvindt, wordt informatie over het aantal items in het winkelwagentje en de productkenmerkgegevens voor die items opgenomen.
   * `services-id` - verbindt uw instantie van Adobe Commerce met [ Adobe Commerce SaaS ](../landing/saas.md) gebruikend zandbak en productie API sleutels en met Adobe Experience Platform om IMS Organisatie identiteitskaart terug te winnen
   * `orders-connector` - Verbindt de bestelstatusservice met uw Adobe Commerce-instantie.

1. (Facultatief) om [!DNL Live Search] gegevens te omvatten, die [ onderzoeksgebeurtenissen ](events.md#search-events) omvatten, installeer de [[!DNL Live Search]](../live-search/install.md) uitbreiding.

1. (Facultatief) om B2B- gegevens te omvatten, die [ aanvraaggebeurtenissen ](events.md#b2b-events) omvatten, installeer de [ B2B uitbreiding ](#install-the-b2b-extension).

### De Adobe I/O-gebeurtenissen installeren

Nadat u de extensie `experience-platform-connector` hebt geïnstalleerd, moet u de Adobe I/O Events for Adobe Commerce installeren.

De volgende stappen zijn van toepassing op zowel Adobe Commerce op cloudinfrastructuur als op installaties ter plaatse.

1. Als u Commerce 2.4.4 of 2.4.5 in werking stelt, gebruik het volgende bevel om de gebeurtenismodules te laden:

   ```bash
   composer require magento/commerce-eventing=^1.0 --no-update
   ```

   In Commerce 2.4.6 en hoger worden deze modules automatisch geladen.

1. Werk de projectgebiedsdelen bij.

   ```bash
   composer update
   ```

1. Schakel de nieuwe modules in:

   ```bash
   bin/magento module:enable Magento_AdobeCommerceEventsClient Magento_AdobeCommerceEventsGenerator Magento_AdobeIoEventsClient Magento_AdobeCommerceOutOfProcessExtensibility
   ```

De installatie voltooien op basis van het implementatietype: op locatie of Adobe Commerce op Cloud-infrastructuur.

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

Schakel in Adobe Commerce op de Cloud-infrastructuur de globale variabele `ENABLE_EVENTING` in `.magento.env.yaml` in. [ leer meer ](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/configure/env/stage/variables-global.html#enable_eventing).

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

Voor kooplieden B2B, installeer de volgende uitbreiding om ](events.md#b2b-events) gebeurtenisgegevens van de 0} verzoeklijst {te omvatten.[

Download de extensie `magento/experience-platform-connector-b2b` door het volgende uit te voeren vanaf de opdrachtregel:

```bash
composer require magento/experience-platform-connector-b2b
```

## De extensie [!DNL Data Connection] bijwerken {#update}

Voer de volgende handelingen uit vanaf de opdrachtregel om de extensie [!DNL Data Connection] bij te werken:

```bash
composer update magento/experience-platform-connector --with-dependencies
```

Of, voor B2B-handelaren:

```bash
composer update magento/experience-platform-connector-b2b --with-dependencies
```

Als u een update wilt uitvoeren naar een belangrijke versie, bijvoorbeeld van 2.0.0 tot 3.0.0, bewerkt u het hoofdbestand [!DNL Composer] `.json` van het project als volgt:

1. Open het hoofdbestand `composer.json` en zoek naar `magento/experience-platform-connector` .

1. Werk in de sectie `require` het versienummer als volgt bij:

   ```json
   "require": {
      ...
      "magento/experience-platform-connector": "^3.0",
      ...
    }
   ```

1. **sparen** `composer.json`. Voer vervolgens de volgende handelingen uit vanaf de opdrachtregel:

   ```bash
   composer update magento/experience-platform-connector –-with-dependencies
   ```

   Of, voor B2B-handelaren:

   ```bash
   composer update magento/experience-platform-connector-b2b --with-dependencies
   ```

## De extensie [!DNL Data Connection] verwijderen {#uninstall}

Om de [!DNL Data Connection] uitbreiding te desinstalleren, verwijs naar [ uninstall modules ](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html).
