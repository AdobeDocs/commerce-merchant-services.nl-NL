---
title: '''[!DNL Catalog Service] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: d84996bc76a44b39aeaee7f8b0ed4973fbe5de37
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# [!DNL Catalog Service] Opmerkingen bij de release

In deze releaseopmerkingen worden de meest recente versies van [!DNL Catalog Service] en omvatten:

* ![Nieuw](../assets/new.svg) Nieuwe functies
* ![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) Bekende problemen

## V1.1-release

Releasedatum: 2022-11-18 Compatibel met Adobe Commerce (EE): 2.4.x Compatibel met Adobe Commerce for Cloud (ECE): 2.4.x Stabiliteit: Algemene beschikbaarheid

![Nieuw](../assets/new.svg) Catalogusservice biedt nu ondersteuning voor Adobe [API-net](https://developer.adobe.com/graphql-mesh-gateway/).
![Repareren](../assets/fix.svg) We hebben de API-schaalbaarheid en algemene prestaties verbeterd.

### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Tier-prijsstelling
* Er worden geen updates ontvangen wanneer varianten uit de catalogus worden verwijderd
* Maximale grootte voor dynamische kenmerklading is 9 MB

## V1.0-release

Releasedatum: 2022-10-04 Compatibel met Adobe Commerce (EE): 2.4.x Compatibel met Adobe Commerce for Cloud (ECE): 2.4.x Stabiliteit: Algemene beschikbaarheid

![Nieuw](../assets/new.svg) Ondersteuning voor gebundelde en gegroepeerde producten.
![Nieuw](../assets/new.svg) Extra B2B-zichtbaarheidsoverschrijvingen. De producten zijn nu doorzoekbaar en kunnen aan de kar voor specifieke klantengroepen worden toegevoegd.
![Repareren](../assets/fix.svg) De service is nu stabieler en de prestaties zijn verbeterd.

### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Tier-prijsstelling
* Updates worden niet ontvangen wanneer varianten uit de catalogus worden verwijderd
* Maximale grootte voor de lading van dynamische attributen is &lt;9MB
* Vaste prijs voor bundelproducten
* Totale prijs voor gegroepeerde producten
* Ondersteuning voor producttypen van virtuele, downloadbare en cadeaukaarten
* Minimale geadverteerde prijs (MAP)

## 0.3 Release - bèta+

Releasedatum: 2022-09-12 Compatibel met Adobe Commerce (EE): 2.4.x Compatibel met Adobe Commerce for Cloud (ECE): 2.4.x Stabiliteit: Beta

![Nieuw](../assets/new.svg) Afbeeldingen voor varianten worden ondersteund: productafbeeldingen worden geretourneerd op basis van de geselecteerde opties
![Nieuw](../assets/new.svg) Rollen voor prijsondersteuning: alleen leden van specifieke klantengroepen de prijs van producten laten zien
![Repareren](../assets/fix.svg) Verbeterde stabiliteit en prestaties van de dienst
![Nieuw](../assets/new.svg) Updates worden ontvangen wanneer producten uit de catalogus worden verwijderd

### Bekende beperkingen

Deze functies worden nog niet ondersteund:

* Tier-prijsstelling
* Bundel en gegroepeerde producten
* Er worden geen updates ontvangen wanneer varianten uit de catalogus worden verwijderd
* B2B-zichtbaarheidsoverschrijvingen: producten kunnen doorzoekbaar zijn of aan winkelwagentje worden toegevoegd voor specifieke klantengroepen

## Bètaversie

Releasedatum: 2022-08-09 Compatibel met Adobe Commerce (EE): 2.4.x Compatibel met Adobe Commerce for Cloud (ECE): 2.4.x Stabiliteit: Beta

![Nieuw](../assets/new.svg) De `products` en `refineProduct` query&#39;s retourneren de volgende gegevens:

* Vooraf gedefinieerde (systeem)productkenmerken.
* Dynamische productkenmerken en filter deze op rol (pagina met productweergave/productlijst).
* Productopties.
* Afbeeldingen van het product en filter hen door rol (PDP/PLP).
* Een specifieke prijs voor eenvoudige producten en prijsbereiken voor configureerbare producten.
* Prijzen en prijsbereiken van de klantengroep. Ze retourneren een fallback-standaardprijs voor kopers zonder een klantengroep.
* Producttypen die gebruikmaken van klantspecifieke B2B-prijzen.

### Bekende beperkingen

* Bundel en gegroepeerde producten worden niet ondersteund.
* De prijzen van de reeks worden niet gesteund.
* In een array van afbeeldingen bevat alleen de eerste afbeelding rollen.
* Afbeeldingen voor varianten worden niet opgehaald.
* Er worden geen updates ontvangen wanneer producten of varianten uit de catalogus worden verwijderd.
