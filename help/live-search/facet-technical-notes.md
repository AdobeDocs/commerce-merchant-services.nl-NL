---
title: "Facet Technical Notes"
description: "Technische opmerkingen over het gebruik [!DNL Live Search] facetten."
exl-id: 37982610-0ff7-48b7-b088-be7d2eff8a57
source-git-commit: 995f528abc0011c6ae7c4c524982c301072ec2eb
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Technische opmerkingen facet

Facetten is een krachtige het filtreren methode die veelvoudige afmetingen van doorzoekbare statische en dynamische attributenwaarden als onderzoekscriteria gebruikt.

[!DNL Live Search] gebruikt de `productSearch` query die faceting en andere gegevens retourneert die specifiek zijn voor [!DNL Live Search]. Zie [`productSearch` query](https://developer.adobe.com/commerce/webapi/graphql/schema/live-search/queries/product-search/) voor codevoorbeelden.

## Facetaggregatie

Facetaggregatie wordt als volgt uitgevoerd: als de winkel drie facetten (categorieën, kleur en prijs) heeft en de verkoopfilters op alle drie (kleur = blauw, de prijs is van $10.00-50.00, categorieën = `promotions`).

* `categories` aggregatie - aggregaten `categories`past vervolgens de `color` en `price` , maar niet de `categories` filter.
* `color` aggregatie - aggregaten `color`past vervolgens de`price` en `categories` , maar niet de `color` filter.
* `price` aggregatie - aggregaten `price`past vervolgens de `color` en `categories` , maar niet de `price` filter.
