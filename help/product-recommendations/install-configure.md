---
title: Installeren en configureren
description: Leer installeren, bijwerken en verwijderen [!DNL Product Recommendations].
source-git-commit: 4ad607c8595b25d01b5f5020b787fc1d35d4df25
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Installeren en configureren

Implementeren [!DNL Product Recommendations] aan uw opslag en Admin vereist dat u module installeert en de Schakelaar van de Diensten van de Handel vormt. Wanneer updates worden uitgebracht, kunt u de installatie eenvoudig bijwerken met de nieuwste versie.

- [Installeren](#install)
- [Configureren](#configure)
- [Bijwerken](#update)
- [Verwijderen](#uninstall)

## Installeren [!DNL Product Recommendations] {#install}

Omdat [!DNL Product Recommendations] -module is een zelfstandig metapakket. Updates worden vaker uitgebracht dan Adobe Commerce. Raadpleeg de [releaseopmerkingen](release-notes.md).

Installeer de `magento/product-recommendations` module met Composer:

```bash
composer require magento/product-recommendations
```

### Ondersteuning voor Page Builder toevoegen {#pbsupport}

[!DNL Product Recommendations] voor Page Builder zijn optionele modules die afzonderlijk worden geïnstalleerd. Te gebruiken [!DNL Product Recommendations] met de Bouwer van de Pagina, installeer de module door het volgende bevel in werking te stellen:

```bash
composer require magento/module-page-builder-product-recommendations
```

Door [!DNL Product Recommendations] in Page Builder kunt u een bestaande, actieve [aanbeveling-eenheid](https://docs.magento.com/user-guide/cms/page-builder-add-recommendations.html) op alle inhoud die in Page Builder is gemaakt, zoals pagina&#39;s, blokken en dynamische blokken.

### Aanbevolen type voor visuele gelijkenis toevoegen {#vissimsupport}

De _Visuele gelijkenis_ het aanbevelingen type staat u toe om een aanbeveling eenheid aan uw productdetailpagina op te stellen die producten toont die [visueel vergelijkbaar](type.md#visualsim) op het product dat wordt bekeken. Dit soort aanbevelingen is vooral handig wanneer afbeeldingen en visuele aspecten van de producten belangrijke onderdelen zijn van de boodschappenervaring. Installeer de _Visuele gelijkenis_ het type van aanbeveling door het volgende bevel in werking te stellen:

```bash
composer require magento/module-visual-product-recommendations
```

## Configureren [!DNL Product Recommendations] {#configure}

Nadat u de `magento/product-recommendations` module, moet u vormen [Commerce Services Connector](https://docs.magento.com/user-guide/configuration/services/saas.html) door de API-sleutel op te geven en een SaaS-gegevensruimte te selecteren.

Om ervoor te zorgen dat de catalogusexport correct wordt uitgevoerd, moet u bevestigen dat de [kraan](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html) de [indexeerders](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html) en de `Product Feed` indexer is ingesteld op `Update by Schedule`.

Wanneer u via de API-sleutel een koppeling naar de Commerce-services hebt gemaakt en de SaaS-gegevensruimte hebt opgegeven, wordt de catalogussynchronisatie gestart en [verifieert](verify.md) dat gedragsgegevens naar uw winkel worden verzonden.

## Werk uw [!DNL Product Recommendations] installatie {#update}

Zoals alle Adobe Commerce, [!DNL Product Recommendations] gebruikt Composer voor installatie en updates. Als u het dialoogvenster `magento/product-recommendations` voert u de volgende handelingen uit:

```bash
composer update magento/product-recommendations --with-dependencies
```

Als u wilt bijwerken naar een hoofdversie, bijvoorbeeld van 2.0 tot 3.0, moet u de hoofdmap van uw project bewerken `composer.json` bestand. (Zie de [releaseopmerkingen](release-notes.md) voor informatie over de meest recente versie.) Laten we bijvoorbeeld de hoofdmap openen `composer.json` en zoek naar `magento/product-recommendations` module:

```json
"require": {
    ...
    "magento/product-recommendations": "^2.0",
    ...
}
```

Laten we de belangrijkste versie van `2.0` tot `3.0`:

```json
"require": {
    ...
    "magento/product-recommendations": "^3.0",
    ...
}
```

Sla de `composer.json` bestand en uitvoeren:

```bash
composer update magento/product-recommendations --with-dependencies
```

## Verwijderen [!DNL Product Recommendations] {#uninstall}

Indien nodig kunt u [verwijderen](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/install-cli-uninstall-mods.html) de productaanbevelingen module.
