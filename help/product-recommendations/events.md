---
title: Gegevens verzamelen
description: Leer hoe gebeurtenissen gegevens verzamelen voor productaanbevelingen.
exl-id: b827d88c-327f-4986-8239-8f1921d8383c
feature: Services, Recommendations, Eventing
source-git-commit: 7ed9321a2f4e58a7476aa91e74611fe896e1a7b1
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Gegevens verzamelen

Als u Adobe Commerce-functies op basis van SaaS installeert en configureert, zoals [Product Recommendations](install-configure.md) of [Live zoeken](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/onboard/install.html), zetten de modules gedragsgegevensinzameling aan uw winkelcentrum op. Dit mechanisme verzamelt geanonimiseerde gedragsgegevens van uw kopers en geeft de aanzet tot productaanbevelingen. Bijvoorbeeld de `view` wordt gebruikt om de gebeurtenis te berekenen `Viewed this, viewed that` het soort aanbeveling en de `place-order` wordt gebruikt om de gebeurtenis te berekenen `Bought this, bought that` soort aanbeveling.

>[!NOTE]
>
>Gegevensverzameling ten behoeve van productaanbevelingen omvat geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. Meer informatie [meer](https://www.adobe.com/privacy/experience-cloud.html).

De volgende gebeurtenissen zijn niet specifiek voor Product Recommendations, maar zijn vereist om resultaten te retourneren:

- `view`
- `add-to-cart`
- `place-order`

De [Adobe Commerce Storefront Event Collector](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/#quick-start) geeft een lijst weer van alle gebeurtenissen die aan uw storefront worden opgesteld. Uit die lijst komt echter een subset van gebeurtenissen naar voren die specifiek zijn voor Product Recommendations. Deze gebeurtenissen verzamelen gegevens wanneer de klanten met aanbevelingen op de storefront in wisselwerking staan en macht de metriek die wordt gebruikt om u te helpen analyseren hoe goed uw aanbevelingen presteren.

| Gebeurtenis | Beschrijving | Gebruikt voor metriek? |
| --- | --- | --- |
| `impression-render` | De aanbevolen eenheid wordt weergegeven op de pagina. | Ja |
| `rec-add-to-cart-click` | De klant klikt op de knop **Toevoegen aan winkelwagentje** voor een item in de aanbevolen eenheid. | Ja, wanneer een **Toevoegen aan winkelwagentje** is aanwezig in de sjabloon met aanbevelingen. |
| `rec-click` | De klant klikt op een product in de aanbevolen eenheid. | Ja |
| `view` | De aanbevolen eenheid kan op de pagina worden weergegeven, bijvoorbeeld door naar de pagina te schuiven. | Ja |

De volgende gebeurtenissen zijn vereist om het dashboard correct te vullen.
| Dashboardkolom | Gebeurtenissen | Veld samenvoegen | | — | — | — | | Impressies |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render` | unitId | | Weergaven |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-unit-view` | unitId | | Klikken |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click`    | unitId | | Ontvangsten |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click`, `place-order` | unitId, sku | | LT-ontvangsten |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click`, `place-order` | unitId, sku | | CTR |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-item-click`, `recs-add-to-cart-click`  | unitId, sku | | vCTR |`page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-unit-view`, `recs-item-click`, `recs-add-to-cart-click` | unitId, sku |

Als uw winkel is geïmplementeerd met PWA Studio, raadpleegt u de [PWA-documentatie](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Als u een aangepaste frontend-technologie gebruikt, zoals React of Vue JS, raadpleegt u de gebruikershandleiding voor meer informatie over de integratie [Product Recommendations zonder kop](headless.md) milieu.

## Caveats

Als u een advertentie blokkeert en privacy-instellingen hebt, kunt u `magento/product-recommendations` van het vastleggen van gebeurtenissen en kan de betrokkenheid en opbrengst veroorzaken [cijfers](workspace.md) te laag worden gerapporteerd.

Eventing legt niet elke transactie vast die op de locatie van de handelaar plaatsvindt. Uiteindelijk is het bedoeld om de handelaar een algemeen idee te geven van gebeurtenissen die op de plaats gebeuren.

Bij een headless-implementatie moet de gebeurtenis worden geïmplementeerd om het Recommendations-dashboard voor producten van stroom te voorzien.

>[!NOTE]
>
>Indien [Modus Cookie-beperking](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) is ingeschakeld, verzamelt Adobe Commerce geen gedragsgegevens totdat de winkel toestemming geeft om cookies te gebruiken. Als de modus Cookie-beperking is uitgeschakeld, verzamelt Adobe Commerce standaard gedragsgegevens.
