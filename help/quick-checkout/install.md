---
title: '"Installeer de [!DNL Quick Checkout] voor Adobe Commerce-extensie"'
description: '"Voer de volgende stappen uit om de [!DNL Quick Checkout] in uw Adobe Commerce-project."'
exl-id: e1dabc9a-0ab0-4f8d-98d3-7a32abbedcb8
source-git-commit: 9841db7616c8aa6d5bc5af3e6e92c0abe9a4a1e2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Installeer de [!DNL Quick Checkout]

De [!DNL Quick Checkout] voor Adobe Commerce is een naadloze afrekenervaring ontworpen om eenmalige klanten om te zetten in loyale rekeninghouders.

De [!DNL Quick Checkout] extensie voor Adobe Commerce en [!DNL Magento Open Source] kan worden geïnstalleerd met [!DNL Composer keys], die verband houden met de [Magento-id (mageid)](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions){target=&quot;_blank&quot;} opgegeven in het ondertekeningsproces. Composer gebruikt deze toetsen tijdens de eerste installatie van Adobe Commerce of in situaties waarin de [!DNL Composer keys] zijn niet eerder opgeslagen in de `auth.json` bestand.

Zie [krijg uw verificatietoetsen](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html){target=&quot;_blank&quot;} onderwerp voor meer informatie over het verkrijgen van [!DNL Composer keys].

Er zijn twee manieren om deze extensie te installeren—voor [Adobe Commerce over cloudinfrastructuur](#magento-commerce-cloud) of [ter plaatse](#on-premises) installaties. Deze methodes vereisen u om de Interface van de Lijn van het Bevel (CLI) te gebruiken.

## Minimale stabiliteit bijwerken

Voordat u de extensie installeert, kunt u de opdracht `minimum-stability` vereiste `RC` (releasekandidaat) in uw `composer.json` file als u de versie van de versiekandidaat wilt proberen. U kunt winde of uw favoriete tekstredacteur (zoals de Code van Visual Studio of de Tekst van het Sublim) gebruiken.

In uw `composer.json` bestand, wijzigen `"minimum-stability": "stable"` tot `"minimum-stability": "RC"`.

## De extensie installeren

U kunt de [!DNL Quick Checkout] uitbreiding voor zowel Adobe Commerce op cloudinfrastructuur als op locaties.

### Adobe Commerce over cloudinfrastructuur

Deze methode wordt gebruikt voor het installeren van de [!DNL Quick Checkout] extensie voor een Commerce Cloud-instantie.

1. Wijzig op uw lokale werkstation de hoofdmap van het Cloud-project.

1. Werk uw `composer.json` bestand:

   ```bash
   composer require magento/quick-checkout --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer update magento/quick-checkout`.

1. Leg de wijzigingen vast en duw op deze.

### In de bedrijfsruimten

Deze methode wordt gebruikt voor het installeren van de [!DNL Quick Checkout] uitbreiding voor een instantie ter plaatse.

1. Voeg de module Snelle afhandeling toe aan de `require` van de `composer.json` bestand:

   ```bash
   composer require magento/quick-checkout --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer update magento/quick-checkout`.

1. Upgrade uitvoeren voor Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

1. Wijzigingen vastleggen.
1. Werk uw instantie op-gebouw bij om ervoor te zorgen dat de toegewijde code wordt opgesteld.

## De extensie upgraden

Wanneer we een nieuwe versie van de [!DNL Quick Checkout]kunt u uw extensie eenvoudig upgraden.

1. De meest recente versie van het pakket ophalen:

   ```bash
   composer update
   ```

   De `composer update` alle afhankelijkheden worden bijgewerkt. Als u niet alle gebiedsdelen tezelfdertijd wilt bijwerken, gebruik in plaats daarvan dit bevel: `composer update magento/quick-checkout`.

1. Leg de wijzigingen vast en duw op deze.

## Problemen oplossen

Er kunnen fouten optreden bij het installeren van de [!DNL Quick Checkout] extensie.

Zie de [problemen oplossen](../quick-checkout/troubleshooting.md) onderwerp voor meer informatie als u om het even welke kwesties ontmoet wanneer u installeert [!DNL Quick Checkout].

## Vereisten

Zie de [voorwaarden](../quick-checkout/prerequisites.md) voor meer informatie.