---
title: Testen in testomgeving
description: Leren gebruiken [!DNL Product Recommendations] vanuit uw productieomgeving in uw testomgeving voor testdoeleinden.
exl-id: 178ff2aa-7821-45f7-85f1-d490d8182817
feature: Services, Recommendations, Staging
source-git-commit: 9ae4aff1851e9ce9920c4fbf11d2616d6f0f6307
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 0%

---

# Testen in testomgeving

Alvorens u aanbevelingen aan uw productiemilieu opstelt, zou u op een niet productiemilieu moeten testen om ervoor te zorgen dat alles zoals verwacht werkt.

[!DNL Product Recommendations] retourproducten op basis van [gegevens over verkoopgedrag](behavioral-data.md) verzameld bij je winkel. In een niet-productieomgeving is het echter waarschijnlijk dat u geen gedragsgegevens van kopers hebt. Het enige soort aanbevelingen dat u zonder gedragsgegevens kunt testen, is `More like this`. Voor dit soort aanbevelingen zijn geen invoergegevens vereist, omdat er een gelijksoortige directe inhoud wordt gebruikt.

De volgende aanbevelingen vereisen gedragsgegevens:

- Meest bekeken
- Bekeken dit, gezien dat
- Dit gekocht

Hoe kunt u uw aanbevelingen testen in een niet-productieomgeving met behulp van gedragsgegevens? Er zijn een paar opties.

## Aanbevelingen inzake het ophalen uit de productieomgeving (aanbevolen)

Met Adobe Commerce kunt u aanbevelingen ophalen uit uw productieomgeving en deze voorvertonen in uw niet-productieomgeving door [schakelen](settings.md) de SaaS-gegevensruimte.

Om aanbevelingen van uw productiemilieu te halen, moet u ervoor zorgen dat:

- De gegevensinzameling van de Storefront is [geconfigureerd en ingeschakeld](install-configure.md) op productie.
- Uw niet-productieomgevingscatalogus is grotendeels hetzelfde als de catalogus die u in productie hebt. Het gebruik van vergelijkbare catalogi zorgt ervoor dat de producten die in de aanbevolen eenheden worden geretourneerd, de producten op de productie nauwkeurig na houden.

## Gedragsgegevens genereren over een andere omgeving dan de productieomgeving

1. Implementeer de `magento/product-recommendations` in een niet-productieomgeving waar de catalogusgegevens overeenkomen met uw productiecatalogus.

1. Gebruik een van de niet-productie-ID&#39;s voor gegevensruimte [configuratie](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html) in de Admin.

1. Genereer de gegevens zelf door rond de winkelpagina te klikken om het gedrag van echte kopers na te bootsen (of een automatiseringsscript te maken). Door het testen genereert u gedragsgebeurtenissen in uw niet-productieomgeving. Deze gebeurtenissen worden gebruikt om de productaffiniteiten te produceren die aanbevelingen van de macht voorzien. Voor het testen [!DNL Commerce] stelt voor dat u met de volgende aanbevelingen werkt:

   - Meest bekeken - vereist minimale invoergegevens. Gebruikers moeten producten weergeven.
   - Bekeken dit, bekeken die - veelvoudige gebruikers vereist om veelvoudige producten te bekijken.
   - Koop dit, kocht dat - Vereist veelvoudige gebruikers om veelvoudige producten te kopen.

### Caveats

- De gedragsgegevens en catalogusgegevens van de niet-productie-SaaS-gegevensruimte identificeren een geïsoleerde omgeving waarin de daaruit voortvloeiende productaanbevelingen volledig gebaseerd zijn op de gedragsgegevens die op de bijbehorende opslagruimte worden gegenereerd.

- Omdat u niet over grote hoeveelheden gedragsgegevens beschikt, zijn de inputgegevens voor de gegevenssamenvoeging van de computer weinig. Deze gegevens worden echter nog steeds naar Sensei verzonden om de modellen voor machinaal leren te berekenen en aanbevelingen te doen op basis van gegevens die u binnen deze omgeving hebt gegenereerd.
