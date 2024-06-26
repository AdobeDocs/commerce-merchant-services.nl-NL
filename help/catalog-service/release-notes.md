---
title: '''[!DNL Catalog Service] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
feature: Services, Catalog Service, Release Notes
source-git-commit: 7293914fab34381deb5bc841d147371f9f3470a5
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 0%

---

# [!DNL Catalog Service] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Catalog Service].
Er wordt ondersteuning geboden voor de belangrijkste uitgebrachte versie. Opmerkingen bij de release voor oudere versies worden ter referentie verschaft.
Updates zijn:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen

## Huidige hoofdversie

### V1.19 Release

_23 mei 2024_

![Repareren](../assets/fix.svg) <!--DATA-5033-->De `InStock` markering voor optiewaarden houdt nu rekening met het bereik `enabled` status van de productvariant.

![Repareren](../assets/fix.svg) <!--DATA-5888-->Voeg ondersteuning toe voor productprijzen waarvoor grote getallen (maximaal 16 cijfers) en een grotere decimale precisie (maximaal 4 cijfers achter de komma) vereist zijn. Als u de prijsconfiguratie-updates wilt toepassen op uw bestaande catalogus, synchroniseert u de catalogusgegevens opnieuw vanuit de [Gegevensbeheerdashboard](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard)of door de [Adobe Commerce opdrachtregelinterface](../landing/catalog-sync.md#command-line-interface).

## Vorige versies

+++ Vorige versies

### V1.18 Release

_11 april 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegde ondersteuning voor PHP 8.3.

![Nieuw](../assets/new.svg) De [`products`](https://developer.adobe.com/commerce/services/graphql/catalog-service/products/) en [`refineProduct`](https://developer.adobe.com/commerce/services/graphql/catalog-service/refine-product/) query &#39; s retourneren nu aanpasbare optiegegevens voor zowel eenvoudige als complexe producten .<!--DATA-5538-->

### V1.17 Release

_22 februari 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De [[!DNL Data Management Dashboard]](https://experienceleague.adobe.com/docs/commerce-admin/systems/data-transfer/data-dashboard.html) is nu beschikbaar. Dit vernieuwde dashboard biedt inzichten in gegevensstromen voor [!DNL Product Recommendations], [!DNL Live Search], en [!DNL Catalog Service]. Ondersteuning voor deze functie is geïntroduceerd in versie 3.1.0 van het dialoogvenster `catalog-service` metapakket.

### V1.16 Release

_13 februari 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Productvideo&#39;s worden nu ondersteund door de API voor catalogusservice.
![Repareren](../assets/fix.svg) Er wordt nu steun verleend voor bundelproducten met vaste prijzen.
![Repareren](../assets/fix.svg) Opties buiten de voorraad worden nu weergegeven in de PDP-widget.

#### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Maximale grootte voor dynamische attributen lading is 9 MB.
* Productprijs per groep. Deze waarde kan worden berekend aan de hand van eenvoudige productprijzen.
* In een afbeeldingsarray bevat alleen de eerste afbeelding rollen.

De volgende beperkingen kunnen worden opgelost door gebruik te maken van API Mesh en de Core GraphQL API:

* Minimale geadverteerde prijs
* [Tier-prijsstelling](mesh.md)

### V1.13 Release

_12 oktober 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Catalogusservice ondersteunt de `inStock` markering voor productvarianten.
![Nieuw](../assets/new.svg) De `urlKey` en `externalId` er zijn velden toegevoegd aan het GraphQL-schema.
![Nieuw](../assets/new.svg) Downloadbare producten en cadeaukaarten worden nu ondersteund.

### V1.12 Release

_19 september 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Catalogusservice gebruikt nu [Prijsindexering SaaS](../price-index/price-indexing.md).
![Repareren](../assets/fix.svg) Deze versie bevat insectenmoeilijke situaties en verbeteringen aan de de dienstkant.

### V1.11 Release

_18 juli 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Catalogusservice biedt nu ondersteuning voor de [`recommendations`](https://developer.adobe.com/commerce/services/graphql/recommendations/recommendations/) GraphQL-query voor Product Recommendations.

### V1.10 Release

_27 juni 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De API voor catalogusservice ondersteunt nu `related products`.

### V1.7-release

_12 april 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De Catalogusservice schoont verwijderde productvarianten op.
![Repareren](../assets/fix.svg) Verbeterde schaalbaarheid en prestaties van de infrastructuur.

### V1.6-release

_28 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Stalen toegevoegd aan de [`products`](https://developer.adobe.com/commerce/services/graphql/catalog-service/products/) query.
![Nieuw](../assets/new.svg) De mogelijkheid om te worden toegevoegd `entityId` gebruiken [API-net](mesh.md).

### V1.5-release

_6 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegd [`categories`](https://developer.adobe.com/commerce/services/graphql/schema/catalog-service/categories/) GraphQL-functionaliteit
![Repareren](../assets/fix.svg) Verbeterde prestaties en API-schaalbaarheid.

### V1.4 Release

_7 februari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Gepubliceerde metapakket voor catalogusservices om installatiestappen te vereenvoudigen.
![Repareren](../assets/fix.svg) Schaalbaarheid van API&#39;s en prestatieverbeteringen.

### V1.3 Release

_17 januari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Vereenvoudigde en verbeterde ervaring bij het instappen.
![Nieuw](../assets/new.svg) Er zijn nieuwe eindpunten van de sandbox van de klant beschikbaar voor preproductietests.
![Nieuw](../assets/new.svg) Ondersteuning toegevoegd voor virtuele producten.
![Repareren](../assets/fix.svg) Schaalbaarheid van API&#39;s en prestatieverbeteringen.

### V1.1-release

_18 november 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Catalogusservice biedt nu ondersteuning voor de Adobe [API-net](https://developer.adobe.com/graphql-mesh-gateway/).
![Repareren](../assets/fix.svg) Verbeterde API-schaalbaarheid en algemene prestaties.

### V1.0-release

_4 oktober 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Ondersteuning voor gebundelde en gegroepeerde producten.
![Nieuw](../assets/new.svg) Extra B2B-zichtbaarheidsoverschrijvingen. De producten zijn nu doorzoekbaar en kunnen aan de kar voor specifieke klantengroepen worden toegevoegd.
![Repareren](../assets/fix.svg) De service is nu stabieler en de prestaties zijn verbeterd.

### 0.3 Release - bèta+

_12 september 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Afbeeldingen voor ondersteuning door varianten: productafbeeldingen worden geretourneerd op basis van de geselecteerde opties
![Nieuw](../assets/new.svg) Rollen voor prijsondersteuning: alleen leden van specifieke klantengroepen de prijs van producten laten zien
![Repareren](../assets/fix.svg) Verbeterde stabiliteit en prestaties van de dienst
![Nieuw](../assets/new.svg) Updates worden ontvangen wanneer producten uit de catalogus worden verwijderd

### Bètaversie

_9 augustus 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De `products` en `refineProduct` query&#39;s retourneren de volgende gegevens:

* Vooraf gedefinieerde (systeem)productkenmerken.
* Dynamische productkenmerken en filter deze op rol (pagina met productweergave/productlijst).
* Productopties.
* Productafbeeldingen en filteren op rol (PDP/PLP).
* Een specifieke prijs voor eenvoudige producten en prijsbereiken voor configureerbare producten.
* Prijzen en prijsbereiken van de klantengroep. Ze retourneren een fallback-standaardprijs voor kopers zonder een klantengroep.
* Producttypen die gebruikmaken van klantspecifieke B2B-prijzen.
