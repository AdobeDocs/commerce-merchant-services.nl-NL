---
title: Technische opmerkingen facet
description: Technische notities over het gebruik van facetten van Live zoeken.
exl-id: 37982610-0ff7-48b7-b088-be7d2eff8a57
source-git-commit: e53fb13b98684757b8081b2e19dd33d925e8ce5d
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 0%

---

# Technische opmerkingen facet

Facetten is een krachtige het filtreren methode die veelvoudige afmetingen van doorzoekbare statische en dynamische attributenwaarden als onderzoekscriteria gebruikt.

[!DNL Live Search] gebruikt de `productSearch` query die faceting en andere gegevens retourneert die specifiek zijn voor [!DNL Live Search]. Zie [`productSearch` query](https://devdocs.magento.com/live-search/product-search.html) voor codevoorbeelden.

## Facetaggregatie

Facetsamenvoeging wordt uitgevoerd als volgt als de winkel drie facetten (categorieën, kleur en prijs) heeft en de verkoopfilters op alle drie (kleur = blauw, prijs is van $10.00-50.00, categorieën = `promotions`).

* `categories` aggregatie - aggregaten `categories`, van toepassing `color` en `price` , maar niet de `categories` filter.
* `color` aggregatie - aggregaten `color`, van toepassing `price` en `categories` , maar niet de `color` filter.
* `price` aggregatie - aggregaten `price`, van toepassing `color` en `categories` , maar niet de `price` filter.
