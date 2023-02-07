---
title: Onboarding en installatie
description: Leer hoe u kunt installeren [!DNL Catalog Service]
exl-id: 4e9fbdc9-67a1-4703-b8c0-8b159e0cc2a7
source-git-commit: ce5e37c470bb93dc7bc2301ead0789adcf9ab995
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%

---

# Onboarding en installatie

## Vereisten

Het instapproces voor [!DNL Catalog Service] vereist toegang tot de bevellijn van de server. Als u niet bekend bent met het werken vanaf de opdrachtregel, vraagt u een ontwikkelaar of systeemintegrator om hulp.

### Softwarevereisten

- Adobe Commerce 2.4.x
- PHP 8.1
- Composer: 2,x

### Ondersteunde platforms

- Adobe Commerce op cloudinfrastructuur: 2,4 x
- Adobe Commerce ter plaatse: 2,4 x

## Omgevingen

Catalog Service heeft twee omgevingen die beschikbaar zijn voor instapweigering:

- Sandbox (https://catalog-service-sandbox.adobe.io/graphql) - wordt gebruikt voor tests en validatie voordat u live gaat
- Productie (https://catalog-service.adobe.io/graphql)-) gebruikt voor het live verkeer voor handelaars en websites

## Installatie en configuratie

Als u aan de slag wilt met Catalog Service for Adobe Commerce, moet u de volgende stappen uitvoeren:

- Extensies voor gegevensexport installeren
- De service- en gegevensexport configureren
- Toegang tot de service

### Extensies voor gegevensexport installeren

Het instapproces voor de Dienst van de Catalogus vereist toegang tot de bevellijn van de server.

De extensie Catalog Service kan zowel op Adobe Commerce-cloudinfrastructuur als op locatie worden geïnstalleerd.

De Catalogusservice wordt geïnstalleerd met Composer-sleutels die zijn gekoppeld aan de Commerce-account [mageid](https://developer.adobe.com/commerce/marketplace/guides/sellers/profile-personal/#field-descriptions) verstrekt tijdens het ondertekeningsproces. Composer gebruikt deze toetsen tijdens de eerste installatie van Adobe Commerce of in situaties waarin de Composer-toetsen niet eerder zijn opgeslagen naar een externe toepassing `auth.json` bestand.

Zie [Uw verificatietoetsen ophalen](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/prerequisites/authentication-keys.html) voor meer informatie over het verkrijgen van Composer-sleutels.

#### Adobe Commerce over cloudinfrastructuur

Gebruik deze methode voor het installeren van de uitbreiding van de Dienst van de Catalogus voor een instantie van Commerce Cloud.

1. Open de `<Commerce_root>/composer.json` bestand in een teksteditor en werk de vereiste sectie als volgt bij:

```json
"require": {
  "magento/catalog-service": "^1.0.2"
}
```

1. Test de nieuwe configuratie plaatselijk en werk gebiedsdelen bij:

```bash
composer update
```

Het bevel werkt alle gebiedsdelen bij.

1. Leg uw wijzigingen vast en duw op `composer.json` en `composer.lock`.

#### In de bedrijfsruimten

Gebruik deze methode voor het installeren van de uitbreiding van de Dienst van de Catalogus voor een instantie op-gebouw.

1. Open de `<Commerce_root>/composer.json` bestand in een teksteditor en werk de vereiste sectie als volgt bij:

```json
"require": {
    "magento/catalog-service": "^1.0.2"
}
```

1. Afhankelijkheden bijwerken en de extensie installeren:

```bash
composer update
```

Het bevel werkt alle gebiedsdelen bij.

1. Upgrade uitvoeren voor Adobe Commerce:

```bash
bin/magento setup:upgrade
```

1. Cache wissen:

```bash
bin/magento cache:clean
```

### De service- en gegevensexport configureren

Nadat u de Catalogusdienst installeert, moet u vormen [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html#apikey) door de API-sleutels op te geven en een SaaS-gegevensruimte te selecteren.

Nadat de SaaS-configuratie is voltooid, voert u een eerste gegevenssynchronisatie uit door de [Catalogus synchroniseren](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html) hulplijn.

Ga als volgt te werk om te controleren of de catalogus correct wordt geëxporteerd:

- Bevestig dat cron-taken worden uitgevoerd.
- Controleer of de indexen actief zijn.
- Zorg ervoor dat de `Catalog Attributes Feed, Product Feed, Product Overrides Feed`, en `Product Variant Feed` de indexeerders worden geplaatst aan &quot;Update door Programma&quot;.

De eerste synchronisatie kan enkele minuten tot uren duren, afhankelijk van de grootte van de catalogus. Na de eerste synchronisatie exporteert de Catalogus de productgegevens van de Commerce-server voortdurend naar de Commerce-diensten om de diensten up-to-date te houden.

### Toegang tot de service

De API van de Catalogusservice is toegankelijk gebruikend POST bevelen over HTTPS.

Om api-sleutel te verkrijgen, ga naar het gebied van de Schakelaar van de Dienst van de Handel in admin en kopieer de openbare API sleutel.

Lees de [GraphQL-documentatie](https://developer.adobe.com/commerce/webapi/graphql/) om te begrijpen hoe te om de kopballen te vragen en te verzenden die voor het produceren van API verzoeken nodig zijn.

## Catalogusservice en API-net

De [API-net voor Adobe Developer App Builder](https://developer.adobe.com/graphql-mesh-gateway/gateway/overview/) laat ontwikkelaars toe om privé of derde APIs en andere interfaces met de producten van Adobe te integreren gebruikend Adobe IO.

Zie de  [Catalogusservice en API-net](mesh.md) onderwerp voor installatie en configuratiedetails.
