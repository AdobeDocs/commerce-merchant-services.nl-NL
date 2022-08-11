---
title: '''[!DNL Catalog Service] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Catalog Service] voor Adobe Commerce.
exl-id: 9bf8e3f7-5b74-4755-867e-ac1c5000ff33
source-git-commit: 72913e0c0b7364e38d37fe1a8279c40a4e849c02
workflow-type: tm+mt
source-wordcount: '0'
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

* Bundel en gegroepeerde producten worden niet ondersteund.
* De prijzen van de reeks worden niet gesteund.
* In een array van afbeeldingen bevat alleen de eerste afbeelding rollen.
* Afbeeldingen voor varianten worden niet opgehaald.
* Er worden geen updates ontvangen wanneer producten of varianten uit de catalogus worden verwijderd.
