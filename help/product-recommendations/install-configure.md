---
title: Installeren en configureren
description: Leer om te installeren, bij te werken, en te desinstalleren  [!DNL Product Recommendations].
exl-id: fa599f72-1064-41da-ac54-2b3a3c16a1fe
role: Admin, Developer
source-git-commit: 96a5791c5716f612f473540f27bd3f99b1bfe7c8
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Installeren en configureren

Het opstellen van [!DNL Product Recommendations] aan uw opslag en Admin vereist dat u de module installeert en de [ Schakelaar van de Diensten van Commerce ](../landing/saas.md) vormt. Wanneer updates worden uitgebracht, kunt u de installatie eenvoudig bijwerken met de nieuwste versie.

- [Installeren](#install)
- [Configureren](#configure)
- [Bijwerken](#update)
- [Verwijderen](#uninstall)

## Installeren [!DNL Product Recommendations] {#install}

Aangezien de module [!DNL Product Recommendations] een zelfstandig metapakket is, worden updates vaker uitgebracht dan Adobe Commerce. Om ervoor te zorgen u met de recentste insectenmoeilijke situaties en de eigenschappen bijgewerkt bent, verwijs naar de [ versienota&#39;s ](release-notes.md).

Installeer de module `magento/product-recommendations` met Composer:

```bash
composer require magento/product-recommendations
```

### Ondersteuning voor Page Builder toevoegen {#pbsupport}

[!DNL Product Recommendations] voor Page Builder is een optionele module en wordt apart geïnstalleerd. Als u [!DNL Product Recommendations] wilt gebruiken met Page Builder, installeert u de module met de volgende opdracht:

```bash
composer require magento/module-page-builder-product-recommendations
```

Door [!DNL Product Recommendations] in de Bouwer van de Pagina toe te laten, kunt u een bestaande, actieve [ aanbeveling eenheid ](https://experienceleague.adobe.com/docs/commerce-admin/page-builder/add-content/recommendations.html) aan om het even welke inhoud toevoegen die in de Bouwer van de Pagina, zoals pagina&#39;s, blokken, en dynamische blokken wordt gecreeerd.

Zie [ Gebruikend  [!DNL Product Recommendations]  met de Inhoud van de Bouwer van de Pagina ](page-builder.md) voor verdere instructies.

### Het aanbevolen type Visuele gelijkenis toevoegen {#vissimsupport}

Het _Visuele gelijkenis_ aanbevelingen type staat u toe om een aanbeveling eenheid aan uw productdetailpagina op te stellen die producten toont die [ visueel gelijkaardig ](type.md#visualsim) aan het product zijn dat wordt bekeken. Dit soort aanbevelingen is vooral handig wanneer afbeeldingen en visuele aspecten van de producten belangrijke onderdelen zijn van de boodschappenervaring. Installeer het _Visuele gelijkenis_ aanbevelingstype door het volgende bevel in werking te stellen:

```bash
composer require magento/module-visual-product-recommendations
```

## Configureren [!DNL Product Recommendations] {#configure}

Nadat u de `magento/product-recommendations` module installeert, moet u de [ Verbinding van de Diensten van Commerce ](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) vormen door API Sleutels te specificeren en een Ruimte van Gegevens te selecteren SaaS.

Om ervoor te zorgen dat de catalogusuitvoer correct loopt, bevestig dat de [ bebouwde ](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs.html) banen en [ indexeerders ](https://experienceleague.adobe.com/docs/commerce-operations/configuration-guide/cli/manage-indexers.html) lopen en `Product Feed` indexeerder wordt geplaatst aan `Update by Schedule`.

Wanneer u een koppeling naar Commerce Services tot stand brengt via API-sleutels en de SaaS-gegevensruimte opgeeft, wordt de catalogussynchronisatie gestart. U kunt [ dan verifiëren ](verify.md) dat het gedragsgegeven wordt verzonden naar uw storefront.

## De installatie van [!DNL Product Recommendations] bijwerken {#update}

Net als in alle Adobe Commerce gebruikt [!DNL Product Recommendations] Composer voor installatie en updates. Voer de volgende handelingen uit om de module `magento/product-recommendations` bij te werken:

```bash
composer update magento/product-recommendations --with-dependencies
```

Als u wilt bijwerken naar een hoofdversie, bijvoorbeeld van 3.0 tot 4.0, moet u het hoofdbestand `composer.json` voor uw project bewerken. (Zie de [ versienota&#39;s ](release-notes.md) voor informatie over de recentste versie.) Laten we bijvoorbeeld het hoofdbestand van `composer.json` openen en zoeken naar de module `magento/product-recommendations` :

```json
"require": {
    ...
    "magento/product-recommendations": "^3.0",
    ...
}
```

Laten we de hoofdversie van `3.0` naar `4.0` verplaatsen:

```json
"require": {
    ...
    "magento/product-recommendations": "^4.0",
    ...
}
```

Sla het `composer.json` -bestand op en voer de bewerking uit:

```bash
composer update magento/product-recommendations --with-dependencies
```

Of als u de modules `magento/module-visual-product-recommendations` en `magento/module-page-builder-product-recommendations` hebt geïnstalleerd:

```bash
composer update --with-dependencies magento/product-recommendations magento/module-visual-product-recommendations magento/module-page-builder-product-recommendations
```

>[!NOTE]
>
> In versies 3.x.x van Product Recommendations had u slechts één API-sleutel nodig. In versies 4.x.x en hoger moet u openbare en persoonlijke API-sleutels voor productie en openbare en persoonlijke API-sleutels voor sandbox opgeven. Als u geen van beide API-sleutels biedt, hebt u geen toegang tot de functie Product Recommendations in Admin. Het verzamelen van gegevens gaat echter door op uw winkel en de bestaande aanbevelingen blijven aan de kopers worden getoond.

## Firewalls

Voeg `commerce.adobe.io` toe aan de lijst van gewenste personen om Product Recommendations door een firewall te laten bewegen.

## Verwijderen [!DNL Product Recommendations] {#uninstall}

Indien noodzakelijk, kunt u ](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/tutorials/uninstall-modules.html) de product-aanbevelingen module [ desinstalleren.
