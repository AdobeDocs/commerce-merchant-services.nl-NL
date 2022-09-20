---
title: Onboarding en installatie
description: Leer hoe u kunt installeren [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: 41f42054a495fb815e6dcf0f2ef371bbd2c98701
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Onboarding en installatie

Partners en klanten zijn welkom om te beginnen met het gebruik van de [!DNL Catalog Service] voor Adobe Commerce Beta versie uitgebracht op 9 augustus 2022. Als u wilt deelnemen, moet u onze [Adobe Commerce Beta-programmavoorwaarden](https://experiencecloudpanel.adobe.com/h/s/6eGskQlHvLSHztsNmKCWMy).

Als u de overeenkomst hebt ondertekend, neemt u contact op met ons team over de [#storefront-services](https://magentocommeng.slack.com/archives/C03HVPG8RS4) public Slack channel. Wij zullen alle informatie verstrekken en de volgende stappen nodig om met het [!DNL Catalog Service] Bètaversie.

## Vereisten

Het instapproces voor [!DNL Catalog Service] vereist toegang tot de bevellijn van de server. Als u niet bekend bent met het werken vanaf de opdrachtregel, vraagt u een ontwikkelaar of systeemintegrator om hulp.

### Softwarevereisten

- Adobe Commerce 2.4.x
- PHP 8.1, 7.4, 7.3
- Composer: 2.x, 1.x

### Ondersteunde platforms

- Adobe Commerce op cloudinfrastructuur: 2,4 x
- Adobe Commerce ter plaatse: 2,4 x

## De extensie installeren

U kunt de [!DNL Catalog Service] uitbreiding voor zowel Adobe Commerce op cloudinfrastructuur als op locaties.

De [!DNL Catalog Service] wordt geïnstalleerd met Composer-sleutels die zijn gekoppeld aan de Commerce-account [mageid](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-personal/#field-descriptions) die in het ondertekeningsproces worden verstrekt. Composer gebruikt deze toetsen tijdens de eerste installatie van [!DNL Adobe Commerce]of in situaties waarin de Composer-sleutels niet eerder zijn opgeslagen op de `auth.json` bestand.

Zie [Uw verificatietoetsen ophalen](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) voor meer informatie over het verkrijgen van Composer-sleutels.

### Adobe Commerce over cloudinfrastructuur

Gebruik deze methode voor het installeren van de [!DNL Catalog Service] extensie voor een Commerce Cloud-instantie.

1. Open de `<Commerce_root>/composer.json` in een teksteditor en werk de `require` als volgt:

   ```json
   "require": {
    "magento/composer-root-update-plugin": "^2.0.2",
    "magento/magento-cloud-metapackage": ">=2.4.5 <2.4.6",
    "magento/saas-export": "^101.4.0",
    "magento/commerce-data-export": "^101.3.1",
    "magento/commerce-data-export-ee": "^101.3.1",
    "magento/services-id": "^3.0.1",
    "magento/services-connector": "1.2.1"
    }
   ```

   <!-- What if the customer already has other services installed, and some of these lines are already present? Do they need to delete the duplications? What if the version numbers are different? -->

1. Test de nieuwe configuratie plaatselijk en werk gebiedsdelen bij:

   ```bash
   composer update
   ```

   Het bevel werkt alle gebiedsdelen bij.

1. Leg uw wijzigingen vast en duw op `composer.json` en `composer.lock`.

### In de bedrijfsruimten

Gebruik deze methode voor het installeren van de [!DNL Catalog Service] uitbreiding voor een instantie ter plaatse.

1. Open de `<Commerce_root>/composer.json` in een teksteditor en werk de `require` als volgt:

   ```json
   "require": {
     "magento/magento-cloud-metapackage": ">=2.4.3 <2.4.4",
     "magento/composer-root-update-plugin": "~1.1",
     "magento/saas-export": "^101.3.1",
     "magento/commerce-data-export": "^101.2.4",    
     "magento/commerce-data-export-ee": "^101.2.4",
     "magento/services-id": "^3.0.0",
     "magento/services-connector": "1.2.1"
   }
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

   Het bevel werkt alle gebiedsdelen bij.

1. Upgrade uitvoeren voor Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

## Catalogusexport configureren

Na de installatie [!DNL Catalog Service]moet u de [Commerce Services Connector](../landing/saas.md) door API-sleutels op te geven en een SaaS-gegevensruimte te selecteren.

Ga als volgt te werk om te controleren of de catalogus correct wordt geëxporteerd:

- Bevestig dat [kroonbanen](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs.html) worden uitgevoerd.
- Controleer de [indexeerders](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/manage-indexers.html) worden uitgevoerd.
- Zorg ervoor dat de `Catalog Attributes Feed`, `Product Feed`, `Product Overrides Feed`, en `Product Variant Feed` indexeerders worden ingesteld op `Update by Schedule`.

## [!DNL Catalog Service] demo

Bekijk deze video voor meer informatie over [!DNL Catalog Service] installatie en beproeving:

>[!VIDEO](https://video.tv.adobe.com/v/3409390?quality=12&learn=on)
