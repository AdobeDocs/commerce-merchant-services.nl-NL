---
title: '"Problemen met het oplossen van problemen voor de [!DNL Quick Checkout]"'
description: '"Los fouten, bekende kwesties op u terwijl het gebruiken van [!DNL Quick Checkout] voor Adobe Commerce-extensie."'
exl-id: a379ff81-360d-4cb9-a123-47e8cbc0cdbd
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Problemen oplossen [!DNL Quick Checkout] voor Adobe Commerce

Gebruik de volgende het oplossen van problemenmethodes om deze specifieke kwesties op te lossen.

## Onjuist [!DNL Composer keys]

Als u de volgende fout ziet die u aangeeft, is de fout [!DNL Composer keys]:

```terminal
Could not find a matching version of package magento/quick-checkout. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (RC).
```

Controleer of uw [!DNL Composer keys] worden gekoppeld aan de Magento-id die wordt gebruikt tijdens de registratie voor snelle afhandeling.

Om te zien welke [!DNL Composer keys] zijn geconfigureerd:

1. Zoek de locatie van het dialoogvenster `auth.json` bestand:

   ```bash
   composer config --global home
   ```

1. De weergave van `auth.json` bestand:

   ```bash
   cat /path/to/auth.json
   ```

1. Zie [welke toetsen aan uw Magento-id zijn gekoppeld](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html).

## Minimale stabiliteit in de `composer.json` is ingesteld op stabiel

Als u de volgende fout ziet die u aangeeft, is de fout [!DNL Composer keys]:

```terminal
Could not find a matching version of package magento/quick-checkout. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Minimale stabiliteit instellen op `RC` in de `composer.json` bestand.

## Onvoldoende geheugen voor PHP

Als je de volgende foutmelding ziet, heb je onvoldoende geheugen voor PHP:

```terminal
Fatal error: Allowed memory size of 2146435072 bytes exhausted (tried to allocate 4096 bytes) in phar:///usr/local/bin/composer/src/Composer/DependencyResolver/RuleWatchGraph.php on line 52
```

[De geheugenlimiet verhogen](https://devdocs.magento.com/cloud/project/magento-app-php-ini.html#increase-php-memory-limit) voor PHP op uw omgeving `php.ini`.

U kunt ook de geheugenlimiet opgeven met deze opdracht: `php -d memory_limit=-1 [path to composer]/composer require magento/quick-checkout`.

Bijvoorbeeld:

```bash
php -d memory_limit=-1 vendor/bin/composer require magento/quick-checkout
```

## Ongeldig verzendadres

Er is een bekend probleem voor de [!DNL Quick Checkout].

Als het standaardverzendadres niet geldig is, wordt de klant doorgestuurd naar de stap Verzendadres. In eBay-winkel worden alleen geldige verzendadressen weergegeven.

>[!WARNING]
>
> als er geen geldig verzendadres is, ziet de klant geen beschikbaar verzendadres.

Zie de [verzendgegevens](../quick-checkout/shipping-details.md) voor meer informatie.

## Straaladreslijnen toevoegen met een nieuw verzendadres

Er is een bekend probleem voor de [!DNL Quick Checkout].

Wanneer u [aanmelden met een [!DNL Bolt] account](https://help.bolt.com/shoppers/guides/checkout/log-in/) Je kunt een nieuw verzendadres toevoegen met een maximum van 4 regels per adres.

Adobe Commerce kan doorgaans worden geconfigureerd voor ondersteuning van maximaal 20 adreslijnen op straat.

## Selectievakje `enable terms and conditions` wordt niet correct weergegeven

Er is een bekend probleem voor de [!DNL Quick Checkout].

Wanneer u de optie `Enable terms and conditions` Schakel het selectievakje in Admin en meld u aan met een [!DNL Bolt] de `Enable terms and conditions` het selectievakje wordt niet weergegeven tijdens het uitchecken. Zie de [Aanmelden](https://help.bolt.com/shoppers/account/login-dashboard/) [!DNL Bolt] voor meer informatie.

Zie [voorwaarden](https://docs.magento.com/user-guide/sales/terms-and-conditions.html) onderwerp voor meer informatie over de configuratie Admin.

## Onverwacht gedrag wanneer `Display Billing Address On` is ingesteld op `payment page`

Er is een bekend probleem voor de [!DNL Quick Checkout].

Als u de `Display Billing Address On` parameter to `payment page` en [aanmelden met een [!DNL Bolt] account](https://help.bolt.com/shoppers/guides/checkout/log-in/) wanneer u de `My billing and shipping address are the same` Selectievakje voor weergave van keuzerondjes `use existing card`.

![Hetzelfde adres](assets/checked-address.png)

Zie de [Afhandeling](https://docs.magento.com/user-guide/configuration/sales/checkout.html) onderwerp voor meer informatie over `Display Billing Address On` parameter.

## De [!DNL Quick Checkout] extension

Met Adobe Commerce kunt u uw winkel lokaliseren voor meerdere regio&#39;s en markten. U kunt zelfs foutberichten lokaliseren in uw beheerweergave.

Zie de [vertalen en lokaliseren](https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/translations/xlate.html) voor meer informatie.

## De cache leegmaken

1. Navigeren naar **[!UICONTROL System]** > **[!UICONTROL Cache Management]** en klik op **[!UICONTROL Flush Cache]** om alle ongeldige caches te vernieuwen.

## Hulp vragen

Contact [Adobe Commerce-ondersteuning](mailto:quick-checkout-support@adobe.com) voor hulp.
