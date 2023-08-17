---
title: Installeren [!DNL Payment Services]
description: Installeer de uitbreiding van de Diensten van Betalingen.
exl-id: babaa91a-9376-4acb-b934-a89f9df52016
role: Admin
feature: Payments, Checkout, Install, Upgrade
source-git-commit: 0c8d9498ea7a30a99f834694ef8a865ad24466ab
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# Installeren [!DNL Payment Services]

Het downloaden en installeren van [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] is een eerste vereiste voor het gebruik [!DNL Payment Services].

![[!DNL Payment Services] extensiebeheerweergave](assets/admin-view.png)

## De extensie downloaden

U moet de extensie eerst downloaden van [Commerce Marketplace](https://experienceleague.adobe.com/docs/commerce-admin/start/resources/commerce-marketplace.html) voordat u de toepassing installeert.

1. Ga naar de [Uitbreiding betalingsdiensten in de Commerce Marketplace](https://commercemarketplace.adobe.com/magento-payment-services.html).
1. U kiest de editie en versie door te schakelen **[!UICONTROL Edition]** en **[!UICONTROL Your store version]** naar uw voorkeurskeuzes.
1. Klik op **[!UICONTROL Add to Cart]**.
1. Uitchecken voltooien en klikken **[!UICONTROL Place Order]**.
1. Controleer het e-mailadres dat is gekoppeld aan het downloaden van uw Marketplace voor bevestiging van de bestelling en voor meer informatie.

## De extensie installeren

U kunt de [!DNL Payment Services] extensie voor beide [!DNL Adobe Commerce] op cloudinfrastructuur en op bedrijfslocaties, die zijn gekoppeld aan uw Commerce-account [mageid](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions) die in het ondertekeningsproces worden verstrekt. [!DNL Magento Open Source] de klanten gebruiken de instructies ter plaatse.

Composer gebruikt deze toetsen tijdens de eerste installatie van [!DNL Adobe Commerce]of in situaties waarin de Composer-sleutels niet eerder zijn opgeslagen op de `auth.json` bestand.

Zie [Uw verificatietoetsen ophalen](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) voor meer informatie over het verkrijgen van Composer-sleutels.

Zie [Een extensie installeren](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/extensions.html) voor meer informatie over wat om te overwegen alvorens een uitbreiding te downloaden en te installeren.

### [!DNL Adobe Commerce] over cloudinfrastructuur

Deze methode wordt gebruikt voor het installeren van de [!DNL Payment Services] extensie voor een Commerce Cloud-instantie.

1. Werk uw `composer.json` bestand:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update magento/payment-services --with-dependencies
   ```

   Gebruik de `composer update` gebruiken om alle basisafhankelijkheden bij te werken.

1. Leg de wijzigingen vast en duw op deze.

### Op het terrein en in andere configuraties

Deze methode wordt gebruikt voor het installeren van de [!DNL Payment Services] verlenging voor een instantie ter plaatse en [!DNL Magento Open Source] klanten.

1. Voer de volgende opdrachten uit om de extensie te verkrijgen:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update magento/payment-services --with-dependencies
   ```

   Gebruik de `composer update` gebruiken om alle basisafhankelijkheden bij te werken.

1. Upgrade uw exemplaar:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

1. Wijzigingen vastleggen.
1. Om ervoor te zorgen dat de toegewijde code wordt opgesteld, werk uw instantie bij.

## De extensie upgraden

Wanneer een nieuwe versie van [!DNL Payment Services] wordt vrijgegeven, kunt u uw uitbreiding gemakkelijk bevorderen.

1. De meest recente versie van het pakket ophalen:

   ```bash
   composer update magento/payment-services --with-dependencies
   ```

   Gebruik de `composer update` gebruiken om alle basisafhankelijkheden bij te werken.

1. Leg de wijzigingen vast en duw op deze.

## Problemen oplossen

Er kunnen fouten optreden bij het installeren van de [!DNL Payment Services] extensie. Gebruik de volgende methoden voor het oplossen van problemen om de fouten op te lossen.

### Onjuiste Composer-sleutels

Als de volgende fout aangeeft dat u onjuiste Composer-toetsen hebt:

```terminal
Could not find a matching version of package magento/payment-services. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Controleer of uw Composer-sleutels geldig zijn en of u toegang hebt tot andere Magento&#39;s.

Om te zien welke Composer sleutels worden gevormd:

1. Zoek de locatie van het dialoogvenster `auth.json` bestand:

   ```bash
   composer config --global home
   ```

1. De weergave `auth.json` bestand:

   ```bash
   cat /path/to/auth.json
   ```

1. Zie [welke sleutels aan uw rekening van de Handel worden geassocieerd `MageID`](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html).

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
