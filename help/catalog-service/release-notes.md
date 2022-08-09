---
title: '"[!DNL Catalog Service] Opmerkingen bij de release"'
description: '"De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce."'
source-git-commit: 3959cc5d07f9a0da0ba772a4f3bc56adeb3c6bf3
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---


# [!DNL Catalog Service] Opmerkingen bij de release

{{catalog-service-beta}}

In deze releaseopmerkingen worden de meest recente versies van [!DNL Catalog Service] en omvatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) - Bekende problemen

## Bètaversie

* ![Nieuw](../assets/new.svg) - de `products` en `refineProduct` query&#39;s retourneren de volgende gegevens:
   * Vooraf gedefinieerde (systeem)productkenmerken.
   * Dynamische productkenmerken en filter deze op rol (pagina met productweergave/productlijst).
   * Productopties.
   * Afbeeldingen van het product en filter hen door rol (PDP/PLP).
   * Een specifieke prijs voor eenvoudige producten en prijsbereiken voor configureerbare producten.
   * Prijzen en prijsbereiken van de klantengroep. Ze retourneren een fallback-standaardprijs voor kopers zonder een klantengroep.
   * Producttypen die gebruikmaken van klantspecifieke B2B-prijzen.

## Bekende beperkingen

* De prijzen van de reeks worden niet gesteund.
* In een array van afbeeldingen bevat alleen de eerste afbeelding rollen.
* Afbeeldingen voor varianten worden niet opgehaald.
* Er worden geen updates ontvangen wanneer producten of varianten uit de catalogus worden verwijderd.
