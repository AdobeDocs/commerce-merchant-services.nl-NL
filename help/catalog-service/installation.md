---
title: Onboarding en installatie
description: "Leer hoe u kunt installeren [!DNL Catalog Service]"
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: 8a98e069cd9ec3d2c4fec33485e5c8186d94518f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 0%

---

# Onboarding en installatie

De volgende video&#39;s laten u door de [!DNL Catalog Service] proces.

**Deel 1**: Aan boord en installatie

>[!VIDEO](https://video.tv.adobe.com/v/3415599)

**Deel 2**: De [!DNL Catalog Service]

>[!VIDEO](https://video.tv.adobe.com/v/3415600)

>[!BEGINSHADEBOX]

## Vereisten

Het instapproces voor [!DNL Catalog Service] vereist toegang tot de bevellijn van de server. Als u niet bekend bent met het werken vanaf de opdrachtregel, vraagt u een ontwikkelaar of systeemintegrator om hulp.

**Softwarevereisten**

- Adobe Commerce 2.4.4+
- PHP 8.1, 8.2
- Composer: 2.x

**Ondersteunde platforms**

- Adobe Commerce op cloudinfrastructuur: 2.4.4+
- Adobe Commerce in bedrijven: 2.4.4+

>[!ENDSHADEBOX]

## Eindpunten

[!DNL Catalog Service] beschikt over twee eindpunten voor instapweigering:

- Sandbox (`https://catalog-service-sandbox.adobe.io/graphql`)—Wordt gebruikt voor testen en valideren voordat u live gaat
- Productie (`https://catalog-service.adobe.io/graphql`) - gebruikt voor live verkeer voor Commerce-handelaren en websites

Alle testinstanties van Commerce moeten het Sandbox-eindpunt gebruiken.

Het testen van de lading zou slechts op het zandbakeindpunt moeten worden uitgevoerd. Het wordt aanbevolen om [Ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket) worden geopend wanneer het laden het testen zodat het team van de Diensten het extra serververkeer kan voorzien.

## Installatie en configuratie

Aan de slag met [!DNL Catalog Service] voor Adobe Commerce zijn de volgende stappen vereist:

- Extensies voor gegevensexport installeren
- De service- en gegevensexport configureren
- Toegang tot de service

### Extensies voor gegevensexport installeren

Het instapproces voor [!DNL Catalog Service] vereist toegang tot de bevellijn van de server.

De [!DNL Catalog Service] kan worden geïnstalleerd op de cloudinfrastructuur van Adobe Commerce en op het terrein.

De [!DNL Catalog Service] wordt geïnstalleerd met Composer-sleutels die zijn gekoppeld aan de Commerce-account [`mageid`](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-information/) verstrekt tijdens het ondertekeningsproces. Composer gebruikt deze toetsen tijdens de eerste installatie van Adobe Commerce of in situaties waarin de Composer-toetsen niet eerder zijn opgeslagen naar een externe toepassing `auth.json` bestand.

Zie [Uw verificatietoetsen ophalen](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/prerequisites/authentication-keys.html) voor meer informatie over het verkrijgen van Composer-sleutels.

#### Adobe Commerce over cloudinfrastructuur

Gebruik deze methode voor het installeren van de [!DNL Catalog Service] extensie voor een Commerce Cloud-instantie.

1. Wijzig op uw lokale werkstation de projectmap.
1. Voeg de module Catalogusservice toe.

   ```bash
   composer require "magento/catalog-service" "^3.0.1"
   ```

1. Pakketafhankelijkheden bijwerken.

   ```bash
   composer update
   ```

1. Wijzigingen in de code vastleggen en doorvoeren voor de `composer.json` en `composer.lock` bestanden.

#### In de bedrijfsruimten

Gebruik deze methode voor het installeren van de [!DNL Catalog Service] uitbreiding voor een instantie ter plaatse.

1. Composer van het gebruik om de module van de Dienst van de Catalogus aan uw project toe te voegen:

   ```bash
   composer require "magento/catalog-service" "^3.0.1"
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update
   ```

1. Upgrade Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

### De service- en gegevensexport configureren

Na de installatie [!DNL Catalog Service]moet u de [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html#apikey) door de API-sleutels op te geven en een SaaS-gegevensruimte te selecteren.

Nadat de SaaS-configuratie is voltooid, voert u een eerste gegevenssynchronisatie uit met de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard). U kunt dit dashboard gebruiken om de synchronisatiestatus te controleren voor productgegevens die van het Commerce gegevensbestand aan de diensten van Commerce SaaS worden overgebracht.

Ga als volgt te werk om te controleren of de catalogus correct wordt geëxporteerd:

- Bevestig dat cron-taken worden uitgevoerd.
- Controleer of de indexen worden uitgevoerd.
- Zorg ervoor dat de `Catalog Attributes Feed, Product Feed, Product Overrides Feed`, en `Product Variant Feed` de indexeerders worden geplaatst aan &quot;Update door Programma&quot;.

De eerste synchronisatie kan enkele minuten tot uren duren, afhankelijk van de grootte van de catalogus. Na de eerste synchronisatie worden de productgegevens van de Commerce-server doorlopend naar de Commerce-services geëxporteerd om de services up-to-date te houden. Als u de status van de synchronisatie wilt controleren, raadpleegt u de [[!DNL Data Management Dashboard]](https://experienceleague.adobe.com/docs/commerce-admin/systems/data-transfer/data-dashboard.html).

### Toegang tot de service

De [!DNL Catalog Service] API is toegankelijk via POST-opdrachten via HTTPS.

Als u de api-toets wilt verkrijgen, gaat u naar het gebied Commerce Service Connector in de beheerdersinterface en kopieert u de openbare API-sleutel.

Lees de [GraphQL-documentatie](https://developer.adobe.com/commerce/services/graphql/) om te begrijpen hoe te om de kopballen te vragen en te verzenden die voor het produceren van API verzoeken nodig zijn.

Toestaan [!DNL Catalog Service] via een firewall toevoegen `commerce.adobe.io` op de lijst van gewenste personen.

## Catalogusservice en API-net

De [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) laat ontwikkelaars toe om privé of derde APIs en andere interfaces met Adobe producten te integreren gebruikend Adobe IO.

Zie de  [[!DNL Catalog Service] en API-net](mesh.md) onderwerp voor installatie en configuratiedetails.

## Gegevensbeheerdashboard

Gebruikers kunnen naar de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/docs/commerce-admin/systems/data-transfer/data-dashboard.html) voor meer informatie over [!DNL Catalog Service] gegevenssynchronisatie.
