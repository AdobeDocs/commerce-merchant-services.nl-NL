---
title: Prijsindexering SaaS
description: De SaaS Price Indexing gebruiken om prestaties te verbeteren
seo-title: Adobe SaaS Price Indexing
seo-description: Price indexing give performance improvements using SaaS infrastructure
source-git-commit: c13e836541c8f04c9621802e482754a483ef0a21
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 0%

---

# Prijsindexering SaaS

De prijsindexering van SaaS versnelt de tijd die het voor prijsveranderingen vergt om op de website van een klant te worden weerspiegeld nadat zij zijn voorgelegd. Met deze optionele module kunnen handelaren met grote, complexe catalogi of met meerdere websites of klantgroepen prijswijzigingen sneller en doorlopend verwerken.

Het grootste knelpunt van de pijpleiding: computationele zware processen, zoals indexering en prijsberekening, zijn verplaatst van de PHP-kern naar de Cloud-Adobe-infrastructuur. Op deze manier kunnen handelaren snel hun resources vergroten om de indexatietijden te versnellen en de wijzigingen in websites op veel hogere snelheden doorvoeren.

Alle verkopers die aan de vereisten voldoen kunnen van deze verbeteringen profiteren, maar zij die de grootste winst zullen zien zijn klanten met:

* Constante prijswijzigingen: Handelaars die herhaalde veranderingen in hun prijzen vereisen om strategische doelstellingen zoals frequente bevorderingen, seizoenskortingen, of voorraaddalingen te ontmoeten.
* Meerdere websites en/of klantgroepen: Handelaars met gedeelde productcatalogi voor meerdere websites (domeinen/merken) en/of klantgroepen.
* Groot aantal unieke prijzen voor websites of klantgroepen: Handelaren met uitgebreide gedeelde productcatalogi die unieke prijzen bevatten voor websites of klantgroepen, zoals B2B-handelaren met vooraf overeengekomen prijzen, merken met verschillende prijsstrategieën.

Als u toepassingen van derden hebt die afhankelijk zijn van de PHP kern price indexer, lees de documentatie en raadpleeg de provider van de extensie voordat u wijzigingen aanbrengt.

De prijsindexering van SaaS is beschikbaar voor klanten die de diensten van Adobe Commerce gebruiken.

In deze minihandleiding wordt beschreven hoe SaaS-prijsindexering werkt en hoe deze kan worden ingeschakeld.

## Systeemvereisten

Als u de prijsindexering van SaaS wilt gebruiken, hebt u het volgende nodig:

* Adobe Commerce 2.4.4+
* Ten minste een van de volgende geïnstalleerde SaaS-services:

   * [Catalogusservice](../catalog-service/overview.md)
   * [Live zoeken](../live-search/guide-overview.md)
   * [Product Recommendations](../product-recommendations/guide-overview.md)

## Modules

De prijsindexering van SaaS gebruikt een reeks modules om functionaliteit te verstrekken. De lijst van vereiste modules zou lichtjes kunnen verschillend zijn, afhankelijk van de archiefopstelling.

Deze twee modules voegen de nieuwe feeds aan Admin toe. Met deze feeds worden gegevens over de overdracht van prijzen naar de SaaS-index doorgegeven en wordt de PHP-index voor de basisprijs genegeerd.

```
magento/module-product-override-price-remover
magento/module-bundle-product-override-data-exporter
```

Klanten die Luma en Adobe Commerce Core GraphQL gebruiken, kunnen een module installeren die Lumincompatibiliteit biedt en de PHP-indexfunctie voor de basisprijs uitschakelt:

```
adobe-commerce/catalog-adapter
```

De `catalog-adapter` alleen compatibel is met 2.4.5. De steun voor 2.4.4 en 2.4.6 zal in de nabije toekomst worden vrijgegeven.
De PHP-index voor de basisprijs kan opnieuw worden ingeschakeld als dat nodig is door een extensie van een derde of om een andere reden.

## Caveats

Afhankelijk van factoren zoals productsoorten, prijsingewikkeldheid en catalogusgrootte, kan de prijsindexering van SaaS de juiste oplossing voor uw opslag zijn. Lees de volgende beperkingen door en bepaal of dit een goede oplossing voor uw site is.

Momenteel, steunt de prijsindexering van SaaS Eenvoudige, Gegroepeerde, Virtuele, Configurable, en de Dynamische producttypes van Bundel.
Binnenkort wordt ondersteuning geboden voor de volgende producttypen: Downloadbare kaarten, Cadeaukaarten en Vaste bundel.

De prijsindexering van SaaS ondersteunt basisprijzen:

* Min./Max. normale prijs
* Min./Max. uiteindelijke prijs
* Speciale prijzen
* Prijzen van de klantengroep
* Regelprijzen voor catalogi

Als u zich hebt aangemeld bij het gebruik van de nieuwe prijsaanduiding, kunt u contact opnemen met [Ondersteuning](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html) om u te helpen het ongedaan maken.

Nieuwe feeds moeten handmatig worden gesynchroniseerd met de `resync` [CLI, opdracht](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/data-services/catalog-sync.html#resynccmdline). Anders worden de gegevens in het standaardsynchronisatieproces vernieuwd. Meer informatie over de [Catalogus synchroniseren](../landing/catalog-sync.md) proces.

## Gebruiksscenario&#39;s

### Luminantie zonder extensieafhankelijkheden

* Een Luma of Abode Commerce Core GraphQL-handelaar die een vereiste service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* Geen uitbreidingen van derden die afhankelijk zijn van de PHP-basisprijsindexeerder
* Eenvoudige, configureerbare, gegroepeerde, virtuele en bundeldynamische producten verkopen

1. Nieuwe feeds inschakelen.
1. Installeer de catalogusadapter.

### Luma en Abode Commerce Core GraphQl met PHP-afhankelijkheden voor de indexering van de basisprijs

* Een Luma of Abode Commerce Core GraphQL-handelaar die een ondersteunde service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* Met een extensie van derden die afhankelijk is van de PHP-basisprijsindexer
* Eenvoudige, configureerbare, gegroepeerde, virtuele en bundeldynamische producten verkopen

1. De nieuwe feeds inschakelen
1. Installeer de catalogusadapter.
1. Schakel de PHP-index voor de basisprijs opnieuw in.
1. Nieuwe feeds en de Luminantiecode gebruiken in het dialoogvenster `catalog-adapter` module.

### Hoofdkoopman

* Een headless-leverancier die een ondersteunde service heeft geïnstalleerd (Live Search, Product Recommendations, Catalog Service)
* Geen afhankelijkheid van PHP core price indexer
* Eenvoudige, configureerbare, gegroepeerde, virtuele en bundeldynamische producten verkopen

1. Nieuwe feeds inschakelen
1. Installeer de catalogusadapter, waardoor de PHP-indexfunctie voor de basisprijs wordt uitgeschakeld.

### Luma/Core GraphQL/Headless met niet-ondersteunde producttypen

* Luminantietakker
* Creditcards, downloadbare of gebundelde vaste producten

Wacht op volledige ondersteuning van producttypen terwijl de producttypen momenteel niet worden ondersteund.
