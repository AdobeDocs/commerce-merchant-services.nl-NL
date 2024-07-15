---
title: '[!DNL Live Search] Gebeurtenissen'
description: Leer hoe de gebeurtenissen gegevens voor  [!DNL Live Search] verzamelen.
feature: Services, Eventing
exl-id: b0c72212-9be0-432d-bb8d-e4c639225df3
source-git-commit: 0d966c8dbd788563fa453912961fdc62a5a6c23e
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# [!DNL Live Search] Gebeurtenissen

In [!DNL Live Search] worden gebeurtenissen gebruikt om zoekalgoritmen zoals &quot;Meest bekeken&quot; en &quot;Dit bekeken, heeft dat bekeken&quot;, van stroom te voorzien. Terwijl de gebruikers van LUMA uit de doos verhinderen, moeten de headless en andere douaneimplementaties het voorkomen voor hun eigen behoeften uitvoeren.

Aangezien [!DNL Live Search] en [!DNL Product Recommendations] hetzelfde backend-algoritme gebruiken, worden sommige gebeurtenissen door beide services gedeeld. Sommige Product Recommendations-gebeurtenissen zijn vereist om het Recommendations-dashboard te vullen.

In deze tabel worden de gebeurtenissen beschreven die door [!DNL Live Search] -strategieën worden gebruikt.

| Strategie | Producten | Gebeurtenissen | Pagina |
| --- | --- | --- | ---|
| Meest bekeken | Levende Onderzoek <br> Recs van het Product | paginamening <br> productmening | Productdetailpagina |
| Meest aangekocht | Levende Onderzoek <br> Recs van het Product | de mening van de pagina <br> volledige controle | Winkelwagentje/Afhandeling |
| Meest toegevoegd aan winkelwagentje | Levende Onderzoek <br> Recs van het Product | paginaweergave <br> toevoegen aan winkelwagentje | De detailpagina van het product <br> product die pagina <br> van de Lijst van de Kar <br> van de Wenslijst van het Product |
| Bekeken dit, gezien dat | Levende Onderzoek <br> Recs van het Product | paginamening <br> productmening | Productdetailpagina |
| Trend | Levende Onderzoek <br> Recs van het Product | paginamening <br> productmening | Productdetailpagina |
| Bekijk dit, kocht dat | Recs product | paginamening <br> productmening | De detailpagina van het product <br> Kar/Controle |
| Dit gekocht | Recs product | paginamening <br> productmening | Productdetailpagina |
| Conversie: Weergeven voor aankoop | Recs product | paginamening <br> productmening | Productdetailpagina |
| Conversie: Weergeven voor aankoop | Recs product | de mening van de pagina <br> volledige controle | Winkelwagentje/Afhandeling |
| Omzetten: Weergeven naar winkelwagentje | Recs product | paginamening <br> productmening | Productdetailpagina |
| Omzetten: Weergeven naar winkelwagentje | Recs product | paginaweergave <br> toevoegen aan winkelwagentje | De detailpagina van het product <br> van de lijst van het Product pagina <br> Kaart <br> Wislijst |

>[!NOTE]
>
>Gegevensverzameling ten behoeve van [!DNL Live Search] omvat geen PII (Persoonlijk identificeerbare informatie). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. [ leer meer ](https://www.adobe.com/privacy/experience-cloud.html).

## Vereiste dashboardgebeurtenissen

Sommige gebeurtenissen worden vereist om het [ Levende dashboard van het Onderzoek ](performance.md) te bevolken

| Dashboardgebied | Gebeurtenissen | Veld samenvoegen |
| ------------------- | ------------- | ---------- |
| Unieke zoekopdrachten | `page-view` , `search-request-sent` , | searchRequestId |
| Zoekopdrachten met nulresultaten | `page-view` , `search-request-sent` , | searchRequestId |
| Resultaatsnelheid nul | `page-view` , `search-request-sent` , | searchRequestId |
| Populaire zoekopdrachten | `page-view` , `search-request-sent` , | searchRequestId |
| Gem. klikpositie | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click` | searchRequestId |
| Doorklikfrequentie | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click` | searchRequestId, sku |
| Omrekeningskoers | `page-view`, `search-request-sent`, `search-response-received`, `search-results-view`, `search-product-click`, `product-view`, `add-to-cart`, `place-order` | searchRequestId, sku |

### Vereiste contexten

Voor alle gebeurtenissen is de context `Page` en `Storefront` vereist. Dit moet gebeuren op paginaniveau/storefront toepassingslaag eerder dan wanneer het produceren van individuele gebeurtenissen (bijvoorbeeld, in een PHP opslag, is de PHP toepassingscontainer verantwoordelijk voor het plaatsen van hen bij runtime).

## Gebruik

Hier volgt een voorbeeldimplementatie van de gebeurtenis `search-request-sent` :

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

Ad blokkers en privacymontages kunnen gebeurtenissen verhinderen worden gevangen en zouden de overeenkomst en opbrengst [ metriek ](workspace.md) kunnen veroorzaken om worden onderdrukt.

Eventing legt niet elke transactie vast die op de locatie van de handelaar plaatsvindt. Uiteindelijk is het bedoeld om de handelaar een algemeen idee te geven van gebeurtenissen die op de plaats gebeuren.

De draadloze implementaties moeten het verhinderen uitvoeren om het [ dashboard van het Product Recommendations ](../product-recommendations/events.md) te macht.

>[!NOTE]
>
>Als [ de Wijze van de Beperking van het Koekje ](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) wordt toegelaten, verzamelt Adobe Commerce geen gedragsgegevens tot de verkoopster toestemming geeft om koekjes te gebruiken. Als de modus Cookie-beperking is uitgeschakeld, verzamelt Adobe Commerce standaard gedragsgegevens.
