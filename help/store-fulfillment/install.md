---
title: Installatie
description: "Installeer de [!DNL Store Fulfillment solution] voor een Adobe Commerce storefront met Composer for PHP."
role: Admin, Developer
level: Intermediate
feature: Shipping/Delivery, Install
exl-id: 6613268a-7d22-4c54-af89-834921b7f262
source-git-commit: 78b09113e72382053b01d6016276bae3aa545fa3
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---


# Installatie

Voltooi de eerste installatie van de [!DNL Store Fulfillment for Adobe Commerce by Walmart Commerce Technologies] extensie in een niet-productieomgeving met een beheer van de wachtrij en caching geconfigureerd om uitzonderingsverwerking toe te staan. Zorg ervoor dat uw ontwikkelomgeving ontwikkeltools bevat voor de beste werkwijzen voor het werken en onderhouden van uw Adobe Commerce-instantie.

>[!TIP]
>
>Voer een upgrade uit van de extensie Store Fulfillment voor Adobe Commerce op de locatie door het volgende te doen: [upgradeinstructies](https://experienceleague.adobe.com/docs/commerce-operations/upgrade-guide/modules/upgrade.html) in de _Adobe Commerce Upgrade Guide_. Voor Adobe Commerce over cloud-infrastructuur raadpleegt u [Een extensie upgraden](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/configure-store/extensions.html#upgrade-an-extension) in de *Handleiding voor handel in Cloud-infrastructuur*.

## Vereisten

Controleer de [vereisten](solution-requirements.md) voor de Opslagoplossing van de Afhandeling van de Opslag en verzamel vereiste informatie alvorens u installeert of bevordert [!DNL Store Fulfillment] voor Adobe Commerce.

Als u een pre-versie of bètaversie van de Store Fulfillment for Adobe Commerce-extensie hebt geïnstalleerd, gebruikt u de volgende opdracht om deze te verwijderen voordat u de huidige versie installeert.

```terminal
rm -rf composer.lock vendor/walmart &&
composer require walmart/magento-bopis-metapackage:1.0.0
```

## Installatievereisten

- **Toegang tot de Opslag die door het softwarearchief van de Technologieën van de Handel van de Marm (ZIP) wordt verstrekt**—Tijdens het instapproces en het inschakelen van uw account werkt u samen met uw accountmanager om toegang te krijgen tot het installatiebestand voor de extensie Store Fulfillment.

- **Adobe Commerce-accountgegevens**-De installatie van de [!DNL Store Fulfillment] oplossing vereist een [[!DNL Commerce] account](https://docs.magento.com/user-guide/magento/magento-account.html){target="_blank"}. U hebt een account-id en gebruikersgegevens nodig met de toegang tot de [!DNL Adobe Commerce] project.

- Voor [!DNL Adobe Commerce] bij cloudinfrastructuurprojecten moeten softwareinstallatieprogramma&#39;s beheerderstoegang tot het Cloud-project hebben. Zie [Gebruikerstoegang beheren](https://devdocs.magento.com/cloud/project/user-admin.html).

- **Ervaring met Composer en de[!DNL Commerce CLI]**—Zie [Algemene installatie van CLI](https://devdocs.magento.com/extensions/install/){target="_blank"} voor informatie over het gebruik van deze gereedschappen om extensies te installeren en te beheren op de [!DNL Adobe Commerce] platform.

- **Ervaring met het installeren van extensies van derden op Adobe Commerce**—Raadpleeg de documentatie bij Adobe Commerce voor meer informatie.

   - [Een extensie installeren voor een Adobe Commerce-instantie in de cloud-infrastructuur](https://devdocs.magento.com/cloud/howtos/install-components.html#install-an-extension).

   - [Een extensie installeren voor een Adobe Commerce-exemplaar op locatie](https://devdocs.magento.com/extensions/install/).

### Stap 1: De extensiesbundel downloaden

Volg de instructies van uw accountvertegenwoordigers om het archiefbestand te downloaden dat de Composer-pakketten bevat voor het installeren van de extensie Store Fulfillment Services.

### Stap 2: Extensieartefacten extraheren naar uw toepassing

Extraheer het archiefdossier dat de integratiebundel bevat om de uitbreiding van de Diensten van de Afhandeling van de Opslag te installeren.

1. Maak een doelmap voor de geëxtraheerde bestanden.

   - Ga vanaf de opdrachtregel naar de hoofdmap van het webserverdocument.

   - Een `artifacts` directory.

1. Extraheer het archiefbestand naar de nieuwe map.

1. Controleer of de bestanden zijn uitgepakt door de bestandenlijst te bekijken.

   ```
   ../var/www/html/artifacts]$ ls -a
   .
   ..
   bopis-sdk.zip
   module-magento-bopis-alternate-pickup-contact-admin-ui.zip
   module-magento-bopis-alternate-pickup-contact-api.zip
   ```

### Stap 3: Uw app configureren met Composer

Gebruik Composer om de bronmap voor de installatie te configureren en de extensie Services voor winkelvervulling te installeren.

1. Configureer de bronopslagplaats voor de Composer-installatie.

   ```bash
   composer config repositories.artifacts artifact artifacts/
   ```

1. Voeg de uitbreiding van de Diensten van de Afhandeling van de Opslag toe aan `composer.json`.

   ```bash
   composer require walmart/magento-bopis-metapackage:1.0.0
   ```

>[!NOTE]
>
>Voor betere prestaties op Adobe Commerce-exemplaren op locatie kunt u [de configuratie voor automatisch laden bijwerken](https://experienceleague.adobe.com/docs/commerce-operations/performance-best-practices/deployment-flow.html#update-the-autoloader): `composer dump-autoload --optimize`

### Stap 4: Upgrade het databaseschema en de gegevens

Voltooi de installatie met de `bin/magento setup:upgrade` om het gegevensbestandschema en de gegevens met de veranderingen bij te werken om de oplossing van de Afhandeling van de Opslag te steunen.

>[!NOTE]
>
>Voor Adobe Commerce-infrastructuurprojecten in de cloud hoeft u de extensie niet te registreren. Wijs in plaats daarvan de codewijzigingen toe vanaf de vorige stap en duw deze naar uw omgevingsvertakking. De opdrachten voor het bijwerken van het databaseschema en de gegevens worden automatisch uitgevoerd tijdens het proces voor het bouwen en implementeren van de cloud.

### Stap 5: De installatie voltooien

1. Registreer de extensie met Adobe Commerce via de `setup:upgrade` Magento CLI, opdracht.

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

1. Log in bij de server.

   Voor installaties op Adobe Commerce op cloudinfrastructuur, [gebruik SSH om zich aan te melden bij de verre omgeving](https://devdocs.magento.com/cloud/env/environments-ssh.html#ssh).

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

Gebruik indien nodig de [instellen:static-content:inzetten](https://experienceleague.adobe.com/docs/commerce-operations/reference/commerce-on-premises.html){target="_blank"} CLI bevel om statische meningsdossiers aan uw productiemilieu op te stellen.

```terminal
php bin/magento setup:static-content:deploy -f
```

De `-f` is vereist als u een leeg thema gebruikt.

>[!NOTE]
>
>Zie de klasse [Statische inhoud implementeert best practices in Adobe Commerce](https://experienceleague.adobe.com/docs/commerce-operations/implementation-playbook/best-practices/development/static-content-deployment.html) artikel in het Adobe Commerce Help Center.


