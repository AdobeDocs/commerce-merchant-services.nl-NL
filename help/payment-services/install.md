---
title: Installeren [!DNL Payment Services]
description: Installeer de uitbreiding van de Diensten van Betalingen.
exl-id: babaa91a-9376-4acb-b934-a89f9df52016
source-git-commit: bcb817775fe9cd9ac7096931dd40d5ec0c4a5cfc
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Installeren [!DNL Payment Services]

De installatie van de [!DNL Payment Services] uitbreiding voor Adobe Commerce en Magento Open Source is een eerste vereiste voor het gebruik van [!DNL Payment Services].

![[!DNL Payment Services] extensiebeheerweergave](assets/admin-view.png)

De [!DNL Payment Services] -extensie voor Adobe Commerce en Magento Open Source kunnen worden geïnstalleerd met Composer-sleutels die zijn gekoppeld aan de Magento-id ([mageid](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions) die in het ondertekeningsproces worden verstrekt. Composer gebruikt deze toetsen tijdens de eerste installatie van Adobe Commerce of in situaties waarin de Composer-toetsen niet eerder zijn opgeslagen op de `auth.json` bestand.

Zie [Uw verificatietoetsen ophalen](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) voor meer informatie over het verkrijgen van Composer-sleutels.

Er zijn twee manieren om deze extensie te installeren—voor [Adobe Commerce over cloudinfrastructuur](https://devdocs.magento.com/payment-services/install-payments.html#magento-commerce-cloud) of [In de bedrijfsruimten](https://devdocs.magento.com/payment-services/install-payments.html#on-premises) installaties. Deze methodes vereisen u om de Interface van de Lijn van het Bevel (CLI) te gebruiken.

## Minimale stabiliteit bijwerken

Voordat u de extensie installeert, moet u de `minimum-stability` vereiste `RC` (releasekandidaat) in uw `composer.json` bestand. U kunt winde of uw favoriete tekstredacteur (zoals de Code van Visual Studio of de Tekst van het Sublim) gebruiken.

In uw `composer.json` bestand, wijzigen `"minimum-stability": "stable"` tot `"minimum-stability": "RC"`.

## De extensie installeren

U kunt de [!DNL Payment Services] uitbreiding voor zowel Adobe Commerce op cloudinfrastructuur als op locaties.

### Adobe Commerce over cloudinfrastructuur

Deze methode wordt gebruikt voor het installeren van de [!DNL Payment Services] extensie voor een Commerce Cloud-instantie.

1. Werk uw `composer.json` bestand:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer require magento/payment-services`.

1. Leg de wijzigingen vast en duw op deze.

### In de bedrijfsruimten

Deze methode wordt gebruikt voor het installeren van de [!DNL Payment Services] uitbreiding voor een instantie ter plaatse.

1. Voer de volgende opdrachten uit om de extensie te verkrijgen:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer require magento/payment-services`.

1. Upgrade uitvoeren voor Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

1. Wijzigingen vastleggen.
1. Om ervoor te zorgen dat de toegewijde code wordt opgesteld, werk uw op-gebouw instantie bij.

## De extensie upgraden

Wanneer een nieuwe versie van [!DNL Payment Services] wordt vrijgegeven, kunt u uw uitbreiding gemakkelijk bevorderen.

1. De meest recente versie van het pakket ophalen:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer update magento/payment-services`.

1. Leg de wijzigingen vast en duw op deze.

## Problemen oplossen

Er kunnen fouten optreden bij het installeren van de [!DNL Payment Services] extensie. Gebruik de volgende methoden voor het oplossen van problemen om de fouten op te lossen.

### Onjuiste Composer-sleutels

Als de volgende fout aangeeft dat u onjuiste Composer-toetsen hebt:

```terminal
Could not find a matching version of package magento/payment-services. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Controleer of uw Composer-sleutels zijn gekoppeld aan de Magento-id die tijdens het [!DNL Payment Services] registratie.

Om te zien welke Composer sleutels worden gevormd:

1. Zoek de locatie van het dialoogvenster `auth.json` bestand:

   ```bash
   composer config --global home
   ```

1. De weergave van `auth.json` bestand:

   ```bash
   cat /path/to/auth.json
   ```

1. Zie [welke toetsen aan uw Magento-id zijn gekoppeld](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html).

### Onvoldoende geheugen voor PHP

Als je de volgende foutmelding ziet, heb je onvoldoende geheugen voor PHP:

```terminal
Fatal error: Allowed memory size of 2146435072 bytes exhausted (tried to allocate 4096 bytes) in phar:///usr/local/bin/composer/src/Composer/DependencyResolver/RuleWatchGraph.php on line 52
```

[De geheugenlimiet verhogen](https://devdocs.magento.com/cloud/project/magento-app-php-ini.html#increase-php-memory-limit) voor PHP op uw omgeving `php.ini`.

U kunt ook de geheugenlimiet opgeven met deze opdracht: `php -d memory_limit=-1 [path to composer]/composer require magento/payment-services`.

Bijvoorbeeld:

```bash
php -d memory_limit=-1 vendor/bin/composer require magento/payment-services
```
