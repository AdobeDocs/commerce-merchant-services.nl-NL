---
title: '''[!DNL Catalog Service] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
feature: Services, Catalog Service, Release Notes
source-git-commit: 9ae4aff1851e9ce9920c4fbf11d2616d6f0f6307
workflow-type: tm+mt
source-wordcount: '471'
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

### V1.10 Release

_27 juni 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Catalogusservice kan nu verwante producten weergeven in de widget pagina met productdetails.

#### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Bundel producten met vaste prijs
* Maximale grootte voor dynamische attributen lading is 9 MB.
* Productprijs per groep. Kan worden berekend met eenvoudige productprijzen.
* In een afbeeldingsarray bevat alleen de eerste afbeelding rollen.

De volgende beperkingen kunnen worden opgelost met behulp van het API-net en de Core GraphQL API:

* Minimale geadverteerde prijs
* [Tier-prijsstelling](mesh.md)
* Downloadbare producten en cadeaukaarten

### V1.7-release

_12 april 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) De Catalogusservice schoont verwijderde productvarianten op.
![Repareren](../assets/fix.svg) Verbeterde schaalbaarheid en prestaties van de infrastructuur.

### V1.6-release

_28 maart 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Stalen toegevoegd aan de [`products`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/products/) query.
![Nieuw](../assets/new.svg) De mogelijkheid om te worden toegevoegd `entityId` gebruiken [API-net](mesh.md).

### V1.5-release

_6 maart 2023_

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/new.svg) Toegevoegd [`categories`](https://developer.adobe.com/commerce/webapi/graphql/schema/catalog-service/queries/categories/) GraphQL-functionaliteit.
![Repareren](../assets/fix.svg) Verbeterde prestaties en API-schaalbaarheid.

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
![Repareren](../assets/fix.svg) Verbeterde API-schaalbaarheid en algemene prestaties.

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
