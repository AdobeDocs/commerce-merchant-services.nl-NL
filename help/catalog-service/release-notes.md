---
title: '''[!DNL Catalog Service] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 40cf5c5dc6242b5efe3822b9c574fe5b219cfcd8
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# [!DNL Catalog Service] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Catalog Service] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen

## Primaire versie

### V1.5-release

_6 maart 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Toegevoegd [`categories`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/categories/) GraphQL-functionaliteit.
![Repareren](../assets/fix.svg) Verbeterde prestaties en API-schaalbaarheid.

#### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Bundel producten met vaste prijs
* Er worden geen updates ontvangen wanneer varianten uit de catalogus worden verwijderd.
* Maximale grootte voor dynamische attributen lading is 9MB.
* Productprijs per groep. Kan worden berekend met eenvoudige productprijzen.
* In een afbeeldingsarray bevat alleen de eerste afbeelding rollen.
* Kleurstalen
* De pagina met productdetails laden via de URL van het product.

De volgende beperkingen kunnen worden opgelost met de Core GraphQL API:

* Minimale geadverteerde prijs
* Tier-prijsstelling
* Downloadbare producten en cadeaukaarten

### V1.4 Release

_7 februari 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Gepubliceerde metapakket voor catalogusservices om installatiestappen te vereenvoudigen.
![Repareren](../assets/fix.svg) Schaalbaarheid van API&#39;s en prestatieverbeteringen.

### V1.3 Release

_17 januari 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Vereenvoudigde en verbeterde ervaring bij het instappen.
![Nieuw](../assets/new.svg) Er zijn nieuwe eindpunten van de sandbox van de klant beschikbaar voor preproductietests.
![Nieuw](../assets/new.svg) Ondersteuning toegevoegd voor virtuele producten.
![Repareren](../assets/fix.svg) Schaalbaarheid van API&#39;s en prestatieverbeteringen.

### V1.1-release

_18 november 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Catalogusservice biedt nu ondersteuning voor Adobe [API-net](https://developer.adobe.com/graphql-mesh-gateway/).
![Repareren](../assets/fix.svg) We hebben de API-schaalbaarheid en algemene prestaties verbeterd.

### V1.0-release

_4 oktober 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Ondersteuning voor gebundelde en gegroepeerde producten.
![Nieuw](../assets/new.svg) Extra B2B-zichtbaarheidsoverschrijvingen. De producten zijn nu doorzoekbaar en kunnen aan de kar voor specifieke klantengroepen worden toegevoegd.
![Repareren](../assets/fix.svg) De service is nu stabieler en de prestaties zijn verbeterd.

## Vorige versies

+++bèta-releases

### 0.3 Release - bèta+

_12 september 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Afbeeldingen voor varianten worden ondersteund: productafbeeldingen worden geretourneerd op basis van de geselecteerde opties
![Nieuw](../assets/new.svg) Rollen voor prijsondersteuning: alleen leden van specifieke klantengroepen de prijs van producten laten zien
![Repareren](../assets/fix.svg) Verbeterde stabiliteit en prestaties van de dienst
![Nieuw](../assets/new.svg) Updates worden ontvangen wanneer producten uit de catalogus worden verwijderd

### Bètaversie

_9 augustus 2022_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) De `products` en `refineProduct` query&#39;s retourneren de volgende gegevens:

* Vooraf gedefinieerde (systeem)productkenmerken.
* Dynamische productkenmerken en filter deze op rol (pagina met productweergave/productlijst).
* Productopties.
* Afbeeldingen van het product en filter hen door rol (PDP/PLP).
* Een specifieke prijs voor eenvoudige producten en prijsbereiken voor configureerbare producten.
* Prijzen en prijsbereiken van de klantengroep. Ze retourneren een fallback-standaardprijs voor kopers zonder een klantengroep.
* Producttypen die gebruikmaken van klantspecifieke B2B-prijzen.

+++
