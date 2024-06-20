---
title: Onboarding en installatie
description: "Leer hoe u kunt installeren [!DNL Catalog Service]"
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: af9de40a717d2cb55a5f42483bd0e4cbcd913f64
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 0%

---

# Onboarding en installatie

Installeer de Catalogusservice om productgegevens van een Commerce-instantie aan te vragen en te ontvangen met de functie [GraphQL-API voor catalogusservice](https://developer.adobe.com/commerce/services/graphql/catalog-service/). De Catalog Service wordt geleverd als een composer-pakket van de repo.magento.com-opslagplaats.

>[!NOTE]
>
>Als uw Commerce-exemplaar gebruikmaakt van Live Search of Product Recommendations, wordt de Catalogusservice automatisch geïnstalleerd of bijgewerkt wanneer u aan boord bent of een upgrade uitvoert van deze services. Zie de installatie-instructies voor meer informatie [Live zoeken](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/live-search/install) en [Product Recommendations](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/product-recommendations/getting-started/install-configure).



## Systeemvereisten

**Softwarevereisten**

- Adobe Commerce 2.4.4+
- PHP 8.1, 8.2, 8.3
- Composer: 2.x

**Ondersteunde platforms**

- Adobe Commerce op cloudinfrastructuur: 2.4.4+
- Adobe Commerce in bedrijven: 2.4.4+

## Eindpunten

[!DNL Catalog Service] beschikt over twee eindpunten voor instapweigering:

- Sandbox (`https://catalog-service-sandbox.adobe.io/graphql`)—Wordt gebruikt voor testen en valideren voordat u live gaat
- Productie (`https://catalog-service.adobe.io/graphql`) - gebruikt voor live verkeer voor Commerce-handelaren en websites

Alle Commerce-testinstanties gebruiken het Sandbox-eindpunt.

Voer alle tests van de Lading op het zandbakeindpunt uit. Voordat u begint met het testen van het laden, moet u een [Ondersteuningsticket](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket) zodat het team van de Diensten het extra serververkeer kan voorzien.

## Installatie en configuratie

Aan de slag met [!DNL Catalog Service] voor Adobe Commerce zijn de volgende stappen vereist:

- De extensie Catalog Service installeren (`magento/catalog-service`)
- De service- en gegevensexport configureren
- Toegang tot de service

### De extensie Catalog Service installeren

>[!BEGINSHADEBOX]

**Vereiste**

- Toegang [repo.magento.com](https://repo.magento.com) om de extensie te installeren. Voor sleutelgeneratie en het verkrijgen van de nodige rechten, zie [Uw verificatietoetsen ophalen](https://experienceleague.adobe.com/en/docs/commerce-operations/installation-guide/prerequisites/authentication-keys). Zie voor installatie in de cloud de [Handleiding voor handel in Cloud-infrastructuur](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/authentication-keys)

- Toegang tot de opdrachtregel van de Adobe Commerce-toepassingsserver.

>[!ENDSHADEBOX]

De nieuwste versie van de extensie Catalog Services installeren (`magento/catalog-service`) op een Adobe Commerce-instantie waarop Adobe Commerce versie 2.4.4 of hoger wordt uitgevoerd. De Catalogusservice wordt geleverd als een composer-pakket van de [repo.magento.com](https://repo.magento.com) opslagplaats.

>[!BEGINTABS]

>[!TAB Cloud-infrastructuur]

Gebruik deze methode om de [!DNL Catalog Adapter] voor een Commerce Cloud-instantie.

1. Schakel op uw lokale werkstation de projectmap voor uw Adobe Commerce over het infrastructuurproject voor de cloud in.

   >[!NOTE]
   >
   >Voor informatie over het lokale beheer van Commerce-projectomgevingen raadpleegt u [Het leiden van takken met CLI](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/cli-branches) in de _Gebruikershandleiding Adobe Commerce on Cloud Infrastructure_.

1. Bekijk de omgevingsvertakking die u wilt bijwerken met de Adobe Commerce Cloud CLI.

   ```shell
   magento-cloud environment:checkout <environment-id>
   ```

1. Voeg de module Catalogusadapter toe.

   ```bash
   composer require magento/catalog-adapter --no-update
   ```

1. Pakketafhankelijkheden bijwerken.

   ```bash
   composer update "magento/catalog-adapter"
   ```

1. Wijzigingen in de code vastleggen en doorvoeren voor de `composer.json` en `composer.lock` bestanden.

1. De codewijzigingen toevoegen, toewijzen en doorvoeren voor de `composer.json` en `composer.lock` bestanden naar de cloud-omgeving.

   ```shell
   git add -A
   git commit -m "Add catalog service module"
   git push origin <branch-name>
   ```

   Als u de updates naar de cloudomgeving doorvoert, wordt het [Commerce-implementatieproces voor cloud](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/deploy/process) om de wijzigingen toe te passen. Controleer de implementatiestatus via de [logboek implementeren](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/test/log-locations#deploy-log).

>[!TAB In de bedrijfsruimten]

Gebruik deze methode om de [!DNL Catalog Adapter] voor een instantie ter plaatse.

1. Composer van het gebruik om de module van de Dienst van de Catalogus aan uw project toe te voegen:

   ```bash
   composer require magento/catalog-adapter --no-update
   ```

1. Afhankelijkheden bijwerken en de extensie installeren:

   ```bash
   composer update  "magento/catalog-adapter"
   ```

1. Upgrade Adobe Commerce:

   ```bash
   bin/magento setup:upgrade
   ```

1. Cache wissen:

   ```bash
   bin/magento cache:clean
   ```

   >[!TIP]
   >
   >In sommige gevallen, vooral wanneer het opstellen aan productie, zou u gecompileerde code kunnen willen vermijden omdat het wat tijd kan vergen. Zorg ervoor dat u een back-up van het systeem maakt voordat u wijzigingen aanbrengt.

>[!ENDTABS]

### De service- en gegevensexport configureren

Nadat u de [!DNL Catalog Service], voert u de volgende taken uit om de Catalogusservice te integreren met uw Adobe Commerce-exemplaar. Deze integratie maakt gegevenssynchronisatie en communicatie mogelijk tussen de Commerce-instantie, de Catalogusservice en andere ondersteunende services.

1. Stel de [Commerce Services Connector](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/user-guides/integration-services/saas) door de API-sleutels op te geven en een SaaS-gegevensruimte te selecteren.

   Commerce Services Connector-installatie is een eenmalig proces dat vereist is voor het gebruik van Adobe Commerce-services zoals Catalog Service, Live Search en Product Recommendations. Als u reeds de schakelaar voor een andere dienst hebt gevormd, sla deze stap over.

1. Voer een eerste gegevenssynchronisatie uit vanuit de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard).

   De eerste synchronisatie kan enkele minuten tot uren duren, afhankelijk van de grootte van de catalogus. U kunt de synchronisatiestatus controleren via het dashboard voor gegevensbeheer. Na de eerste synchronisatie worden de productgegevens van de Catalogus doorlopend geëxporteerd om de services up-to-date te houden.

   >[!NOTE]
   >
   >U kunt de eerste synchronisatie ook starten vanaf de opdrachtregel met behulp van de Commerce CLI. Zie [Eerste synchronisatie](../data-export/data-export-cli-commands.md#initial-sync) in de _Handleiding voor het exporteren van SaaS-gegevens_.

Ga als volgt te werk om te controleren of de catalogus correct wordt geëxporteerd:

- [Bevestig dat Cron-taken worden uitgevoerd](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/cron-readiness-check-issues).
- Controleer of de indexen worden uitgevoerd vanaf de [Beheerder](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/tools/index-management) of door het Commerce CLI bevel te gebruiken `bin/magento indexer:info`.
- Controleer of de `Catalog Attributes Feed, Product Feed, Product Overrides Feed`, en `Product Variant Feed` indexeerders worden ingesteld op `Update by Schedule`.

### Toegang tot de service

De [!DNL Catalog Service] GraphQL API is toegankelijk via de ` https://catalog-service.adobe.io/graphql` eindpunt dat POST bevelen over HTTPS gebruikt.

In uw GraphQL-query&#39;s moet u meerdere HTTP-headers opgeven, inclusief de openbare API-sleutel die u hebt toegevoegd aan de Adobe Commerce Services Connector-configuratie in de Admin. Zie voor meer informatie de [Storefront Services GraphQL](https://developer.adobe.com/commerce/services/graphql/) documentatie.

### Configuratie van firewall

Toestaan [!DNL Catalog Service] via een firewall toevoegen `commerce.adobe.io` op de lijst van gewenste personen.

## Catalogusservice en API-net

De [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) laat ontwikkelaars toe om privé of derde APIs en andere interfaces met Adobe producten te integreren gebruikend Adobe IO.

Zie de [[!DNL Catalog Service] en API-net](mesh.md) onderwerp voor installatie en configuratiedetails.

## Gegevensbeheerdashboard

Voor meer informatie over [!DNL Catalog Service] gegevenssynchronisatie, zie [Gegevensbeheerdashboard](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard).
