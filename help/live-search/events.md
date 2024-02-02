---
title: '[!DNL Live Search] Gebeurtenissen'
description: Meer informatie over hoe gebeurtenissen gegevens verzamelen voor [!DNL Live Search].
feature: Services, Eventing
exl-id: b0c72212-9be0-432d-bb8d-e4c639225df3
source-git-commit: 8d669cf6042340659574c86a43836a02954f24ce
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# [!DNL Live Search] Gebeurtenissen

[!DNL Live Search] gebruikt gebeurtenissen om zoekalgoritmen zoals &quot;Meest bekeken&quot; en &quot;Dit bekeken, heeft dat bekeken&quot; van stroom te voorzien. Terwijl de gebruikers van LUMA uit de doos verhinderen, moeten de headless en andere douaneimplementaties het voorkomen voor hun eigen behoeften uitvoeren.

Sinds [!DNL Live Search] en [!DNL Product Recommendations] Gebruik het zelfde backend algoritme, sommige gebeurtenissen worden gedeeld door beide diensten. Sommige Product Recommendations-gebeurtenissen zijn vereist om het Recommendations-dashboard te vullen.

## Gebeurtenissen

In deze tabel worden de gebeurtenissen beschreven die door [!DNL Live Search] strategieën.

| Strategie | Producten | Gebeurtenissen | Pagina |
| --- | --- | --- | ---|
| Meest bekeken | Live zoeken<br>Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Meest aangekocht | Live zoeken<br>Recs product | paginaweergave<br>afhandeling voltooien | Winkelwagentje/Afhandeling |
| Meest toegevoegd aan winkelwagentje | Live zoeken<br>Recs product | paginaweergave<br>toevoegen aan winkelwagentje | Productdetailpagina<br>Pagina met productaanbiedingen<br>Kar<br>Gewenste lijst |
| Bekeken dit, gezien dat | Live zoeken<br>Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Trend | Live zoeken<br>Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Bekijk dit, kocht dat | Recs product | paginaweergave<br>productweergave | Productdetailpagina<br>Winkelwagentje/Afhandeling |
| Dit gekocht | Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Conversie: Weergeven voor aankoop | Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Conversie: Weergeven voor aankoop | Recs product | paginaweergave<br>afhandeling voltooien | Winkelwagentje/Afhandeling |
| Omzetten: Weergeven naar winkelwagentje | Recs product | paginaweergave<br>productweergave | Productdetailpagina |
| Omzetten: Weergeven naar winkelwagentje | Recs product | paginaweergave<br>toevoegen aan winkelwagentje | Productdetailpagina<br>Pagina met productaanbiedingen<br>Kar<br>Wishlist |

>[!NOTE]
>
>Gegevensverzameling ten behoeve van [!DNL Live Search] omvat geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [Meer informatie](https://www.adobe.com/privacy/experience-cloud.html).

## Vereiste dashboardgebeurtenissen

Sommige gebeurtenissen zijn vereist om de [Het dashboard voor live zoeken](performance.md)

| Dashboardgebied | Gebeurtenissen | Veld samenvoegen |
| ------------------- | ------------- | ---------- |
| Unieke zoekopdrachten | `page-view`, `search-request-sent`, | searchRequestId |
| Zoekopdrachten met nulresultaten | `page-view`, `search-request-sent`, | searchRequestId |
| Resultaatsnelheid nul | `page-view`, `search-request-sent`, | searchRequestId |
| Populaire zoekopdrachten | `page-view`, `search-request-sent`, | searchRequestId |
| Gem. klikpositie | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click` | searchRequestId |
| Doorklikfrequentie | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click` | searchRequestId, sku |
| Omrekeningskoers | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click`, `product-view`, `add-to-cart`, `place-order` | searchRequestId, sku |

### Vereiste contexten

Alle gebeurtenissen vereisen de `Page` en `Storefront` context. Dit moet gebeuren op paginaniveau/storefront toepassingslaag eerder dan wanneer het produceren van individuele gebeurtenissen (bijvoorbeeld, in een PHP opslag, is de PHP toepassingscontainer verantwoordelijk voor het plaatsen van hen bij runtime).

## Gebruik

Hier volgt een voorbeeldimplementatie van de `search-request-sent` gebeurtenis:

```javascript
const mse = window.magentoStorefrontEvents;

/* set in application container */
// mse.context.page(pageCtx);
// mse.context.setStorefrontInstance(storefrontCtx);

/* set before firing event */
mse.context.setSearchInput(searchInputCtx);
mse.publish.searchRequestSent("search-bar");
```

## Caveats

Ad blockers en privacy-instellingen kunnen voorkomen dat gebeurtenissen worden vastgelegd en kunnen de betrokkenheid en de inkomsten van de service en [cijfers](workspace.md) te laag gerapporteerd.

Eventing legt niet elke transactie vast die op de locatie van de handelaar plaatsvindt. Uiteindelijk is het bedoeld om de handelaar een algemeen idee te geven van gebeurtenissen die op de plaats gebeuren.

Bij implementatie zonder hoofd moet de gebeurtenis worden geïmplementeerd om de [Recommendations-dashboard voor product](../product-recommendations/events.md).

>[!NOTE]
>
>Indien [Modus Cookie-beperking](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) is ingeschakeld, verzamelt Adobe Commerce geen gedragsgegevens totdat de winkel toestemming geeft om cookies te gebruiken. Als de modus Cookie-beperking is uitgeschakeld, verzamelt Adobe Commerce standaard gedragsgegevens.
