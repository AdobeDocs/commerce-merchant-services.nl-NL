---
title: Installatie
description: Beschrijving toevoegen
role: User, Admin
level: Intermediate
exl-id: 6613268a-7d22-4c54-af89-834921b7f262
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Installatie

De eerste installatie van de [!DNL Store Fulfillment] extensie in een niet-productieomgeving met een beheer van de wachtrij en caching geconfigureerd om uitzonderingsverwerking toe te staan. Uw omgeving dient andere ontwikkeltools te bevatten voor de beste werkwijzen voor het werken en onderhouden van uw Adobe Commerce-exemplaar.

## Vereisten

Controleer de [vereisten](solution-requirements.md) voor de Opslagoplossing van de Afhandeling van de Opslag en verzamel vereiste informatie alvorens u installeert [!DNL Store Fulfillment] extensie voor Adobe Commerce.

Als u een pre-release- of bètaversie van de Store Fulfillment for Adobe Commerce-extensie hebt geïnstalleerd, verwijdert u deze voordat u de huidige versie installeert.

```terminal
rm -rf composer.lock vendor/walmart &&
composer require walmart/magento-bopis-metapackage:1.0.0
```

## Installatievereisten

- **Toegang tot de Opslag die door het softwarearchief van de Technologieën van de Handel van de Marm (ZIP) wordt verstrekt**-Tijdens het instapproces en het inschakelen werkt u samen met uw accountmanager om toegang te krijgen tot het installatiebestand voor de extensie Store Fulfillment.

- **Adobe Commerce-accountgegevens**-Installeren [!DNL Channel Manager] vereist een [Handelsrekening](https://docs.magento.com/user-guide/magento/magento-account.html){target=&quot;_blank&quot;}. U hebt een account-id en gebruikersgegevens nodig met de toegang tot de [!DNL Adobe Commerce] project.

- Voor [!DNL Adobe Commerce] bij cloudinfrastructuurprojecten moeten softwareinstallatieprogramma&#39;s beheerderstoegang tot het Cloud-project hebben. Zie [Gebruikerstoegang beheren](https://devdocs.magento.com/cloud/project/user-admin.html).

- **Ervaring met Composer en de[!DNL Commerce CLI]**—Zie [Algemene installatie van CLI](https://devdocs.magento.com/extensions/install/){target=&quot;_blank&quot;} voor informatie over het gebruik van deze gereedschappen voor het installeren en beheren van extensies op het tabblad [!DNL Adobe Commerce] platform.

- **Ervaring met het installeren van extensies van derden op Adobe Commerce**- Raadpleeg de documentatie bij Adobe Commerce ter referentie.

   - [Een extensie installeren voor een Adobe Commerce-instantie in de cloud-infrastructuur](https://devdocs.magento.com/cloud/howtos/install-components.html#install-an-extension)

   - [Een extensie installeren voor een Adobe Commerce-exemplaar op locatie](https://devdocs.magento.com/extensions/install/)

### Stap 1: De extensiebundel downloaden

Volg de instructies van uw accountvertegenwoordigers om het archiefbestand te downloaden dat de Composer-pakketten bevat voor het installeren van de extensie Store Fulfillment Services.

### Stap 2: Extensieartefacten extraheren naar uw toepassing

Extraheer het archiefdossier dat de integratiebundel bevat om de uitbreiding van de Diensten van de Afhandeling van de Opslag te installeren.

1. Maak een doelmap voor de geëxtraheerde bestanden.

   - Ga vanaf de opdrachtregel naar de hoofdmap van het document van de webserver.

   - Een `artifacts` directory.

1. Extraheer het archiefbestand naar de nieuwe map.

1. Controleer of de geëxtraheerde bestanden door de bestandenlijst te bekijken.

   ```
   ../var/www/html/artifacts]$ ls -a
   .
   ..
   bopis-sdk.zip
   module-magento-bopis-alternate-pickup-contact-admin-ui.zip
   module-magento-bopis-alternate-pickup-contact-api.zip
   ```

### Stap 3: Uw app configureren met Composer

Gebruik Composer om de bronmap voor de installatie te configureren en de extensie Store Fulfillment Services te installeren.

1. Configureer de bronopslagplaats voor de Composer-installatie.

   ```bash
   composer config repositories.artifacts artifact artifacts/
   ```

1. Voeg de uitbreiding van de Diensten van de Afhandeling van de Opslag toe aan `composer.json`

   ```bash
   composer require walmart/magento-bopis-metapackage:1.0.0
   ```

>[!NOTE]
>
>Voor betere prestaties op Adobe Commerce-exemplaren op locatie kunt u [de configuratie voor automatisch laden bijwerken](https://experienceleague.adobe.com/docs/commerce-operations/performance-best-practices/deployment-flow.html#update-the-autoloader): `composer dump-autoload --optimize`

### Stap 4: Het databaseschema en de gegevens bijwerken

Voltooi de installatie met de `bin/magento setup:upgrade` om het gegevensbestandschema en de gegevens met de veranderingen bij te werken om de oplossing van de Afhandeling van de Opslag te steunen.

>Opmerking:
>Voor Adobe Commerce-infrastructuurprojecten in de cloud hoeft u de extensie niet te registreren. Wijs in plaats daarvan de codewijzigingen toe vanaf de vorige stap en duw deze naar uw omgevingsvertakking. De opdrachten voor het bijwerken van het databaseschema en de gegevens worden automatisch uitgevoerd tijdens het proces voor het bouwen en implementeren van de cloud.

### Stap 5: De installatie voltooien

1. Registreer de extensie met Adobe Commerce via de `setup:upgrade` Magento CLI-opdracht.

   ```terminal
   bin/magento setup:upgrade
   ```

1. Indien gevraagd, compileert u uw [!DNL Commerce] project.

   ```bash
   bin/magento setup:di:compile
   ```

1. Maak de cache leeg.

   ```bash
   bin/magento cache:clean
   ```

1. Onderhoudsmodus uitschakelen.

   ```bash
   bin/magento maintenance:disable
   ```

### Stap 6: De installatie controleren

Verifieer bij de Adobe Commerce-server of de modules voor de extensie Store Fulfillment Services zijn geïnstalleerd en ingeschakeld.

1. Meld u aan bij de server.

   Voor installaties op Adobe Commerce op cloudinfrastructuur gebruikt u SSH om u aan te melden bij de externe omgeving.

1. Verifieer dat de modules van de Diensten van de Afhandeling van de Opslag worden toegelaten.

   ```bash
   bin/magento module:status  --enabled | grep Walmart
   ```

   De uitvoer moet de volgende modules bevatten:

   ```
   Walmart_BopisBase
   Walmart_BopisAlternatePickupContact
   Walmart_BopisAlternatePickupContactFrontend
   Walmart_BopisApiConnector
   Walmart_BopisAlternatePickupContactAdminUi
   Walmart_BopisCheckoutPickInStoreApi
   Walmart_BopisInventorySourceAdminUi
   Walmart_BopisCheckoutPickInStore
   Walmart_BopisInventoryCatalogApi
   Walmart_BopisPreferredLocationApi
   Walmart_BopisHomeDeliveryApi
   Walmart_BopisHomeDelivery
   Walmart_BopisPreferredLocation
   Walmart_BopisInventoryCatalog
   Walmart_BopisPreferredLocationFrontend
   Walmart_BopisCheckoutPickInStoreAdminUi
   Walmart_BopisInventorySourceApi
   Walmart_BopisInventorySourceFaasSync
   Walmart_BopisInventorySourceReservation
   Walmart_BopisLocationCheckInApi
   Walmart_BopisLogging
   Walmart_BopisStoreAssociateApi
   Walmart_BopisLocationCheckInFrontend
   Walmart_BopisStoreAssociate
   Walmart_BopisOperationQueue
   Walmart_BopisOperationQueueAdminUi
   Walmart_BopisOperationQueueApi
   Walmart_BopisOrderFaasSync
   Walmart_BopisOrderUpdateApi
   Walmart_BopisLocationCheckIn
   Walmart_BopisInventoryCatalogAdminUi
   Walmart_BopisPreferredLocationAdminUi
   Walmart_BopisDeliverySelection
   Walmart_BopisCheckoutPickInStoreFrontend
   Walmart_BopisLocationCheckInAdminUi
   Walmart_BopisStoreAssociateAdminUi
   Walmart_BopisOrderUpdate
   Walmart_BopisStoreAssociateTfa
   Walmart_BopisStoreAssociateTfaApi
   ```

### Aanvullende stappen

Gebruik indien nodig de [instellen:static-content: inzetten](https://devdocs.magento.com/guides/v2.4/reference/cli/magento-commerce.html#setupstatic-contentdeploy) CLI bevel om statische meningsdossiers aan uw productiemilieu op te stellen.

```terminal
php bin/magento setup:static-content:deploy -f
```

De `-f` is vereist als u een leeg thema gebruikt.

>[!NOTE]
>
>Zie voor meer informatie [Statische inhoud implementeert best practices in Adobe Commerce](https://support.magento.com/hc/en-us/articles/360031624091) in het Adobe Commerce Help Center.

