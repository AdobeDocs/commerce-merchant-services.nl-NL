---
title: Gegevens verzamelen
description: Leer hoe gebeurtenissen gegevens verzamelen voor productaanbevelingen.
exl-id: b827d88c-327f-4986-8239-8f1921d8383c
feature: Services, Recommendations, Eventing
source-git-commit: 67296ea42bfddb10b0c86cb1ca47324f5fec7825
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Gegevens verzamelen

Wanneer u installeert en op SaaS-Gebaseerde eigenschappen van Adobe Commerce zoals [ Recommendations van het Product ](install-configure.md) of [ Levend Onderzoek ](https://experienceleague.adobe.com/docs/commerce-merchant-services/live-search/onboard/install.html) vormt, voeren de modules gedragsgegevensinzameling aan uw storefront op. Dit mechanisme verzamelt geanonimiseerde gedragsgegevens van uw kopers en geeft de aanzet tot productaanbevelingen. De gebeurtenis `view` wordt bijvoorbeeld gebruikt om het `Viewed this, viewed that` aanbeveling-type te berekenen en de gebeurtenis `place-order` wordt gebruikt om het `Bought this, bought that` aanbeveling-type te berekenen.

>[!NOTE]
>
>Gegevensverzameling ten behoeve van productaanbevelingen omvat geen persoonlijk identificeerbare informatie (PII). Alle gebruikers-id&#39;s, zoals cookie-id&#39;s en IP-adressen, worden strikt geanonimiseerd. Leer [ meer ](https://www.adobe.com/privacy/experience-cloud.html).

De volgende gebeurtenissen zijn niet specifiek voor Product Recommendations, maar zijn vereist om resultaten te retourneren:

- `view`
- `add-to-cart`
- `place-order`

De [ Verzameling van de Gebeurtenis van Adobe Commerce Storefront ](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/#quick-start) maakt een lijst van alle gebeurtenissen die aan uw storefront worden opgesteld. Uit die lijst komt echter een subset van gebeurtenissen naar voren die specifiek zijn voor Product Recommendations. Deze gebeurtenissen verzamelen gegevens wanneer de klanten met aanbevelingen op de storefront in wisselwerking staan en macht de metriek die wordt gebruikt om u te helpen analyseren hoe goed uw aanbevelingen presteren.

| Gebeurtenis | Beschrijving | Gebruikt voor metriek? |
| --- | --- | --- |
| `impression-render` | De aanbevolen eenheid wordt weergegeven op de pagina. | Ja |
| `rec-add-to-cart-click` | De klant klikt **toevoegt aan wortel** knoop voor een punt in de aanbeveling eenheid. | Ja, wanneer **toevoegt aan wortel** knoop in het aanbevelingen malplaatje aanwezig is. |
| `rec-click` | De klant klikt op een product in de aanbevolen eenheid. | Ja |
| `view` | De aanbevolen eenheid kan op de pagina worden weergegeven, bijvoorbeeld door naar de pagina te schuiven. | Ja |

De volgende gebeurtenissen zijn vereist om het dashboard correct te vullen.

| Dashboardkolom | Gebeurtenissen | Veld samenvoegen |
| ---------------- | --------- | ----------- |
| Impressies | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render` | unitId |
| Weergaven | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-unit-view` | unitId |
| Klikken | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click` | unitId |
| Ontvangsten | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click`, `place-order` | unitId, sku |
| LT-ontvangsten | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-item-click`, `recs-add-to-cart-click`, `place-order` | unitId, sku |
| CTR | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-item-click`, `recs-add-to-cart-click` | unitId, sku |
| vCTR | `page-view`, `recs-request-sent`, `recs-response-received`, `recs-unit-render`, `recs-unit-view`, `recs-item-click`, `recs-add-to-cart-click` | unitId, sku |

Als uw storefront met PWA Studio wordt uitgevoerd, verwijs naar de [ documentatie van de PWA ](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Als u een douane frontend technologie zoals React of Vue JS gebruikt, verwijs naar de gebruikersgids om te leren hoe te om [ Product Recommendations in een headless ](headless.md) milieu te integreren.

## Caveats

Ad blokkers en privacymontages kunnen de `magento/product-recommendations` module verhinderen gebeurtenissen te vangen en zouden de overeenkomst en opbrengst [ metriek ](workspace.md) kunnen veroorzaken om worden onderdrukt.

Eventing legt niet elke transactie vast die op de locatie van de handelaar plaatsvindt. Uiteindelijk is het bedoeld om de handelaar een algemeen idee te geven van gebeurtenissen die op de plaats gebeuren.

Bij een headless-implementatie moet de gebeurtenis worden geïmplementeerd om het Recommendations-dashboard voor producten van stroom te voorzien.

>[!NOTE]
>
>Als [ de Wijze van de Beperking van het Koekje ](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html) wordt toegelaten, verzamelt Adobe Commerce geen gedragsgegevens tot de verkoopster toestemming geeft om koekjes te gebruiken. Als de modus Cookie-beperking is uitgeschakeld, verzamelt Adobe Commerce standaard gedragsgegevens.
