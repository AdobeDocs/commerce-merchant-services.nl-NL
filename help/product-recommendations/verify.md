---
title: Gebeurtenisverzameling verifiëren
description: Leer hoe u kunt controleren of er gedragsgegevens naar Adobe Commerce worden verzonden.
exl-id: c8c34db4-9d87-4012-b8f0-e9b1da214305
source-git-commit: 7d9cef7a81196921b465ccf2dcd58d98b66d6598
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Gebeurtenisverzameling verifiëren

Na u [installeren en configureren](install-configure.md) de `magento/product-recommendations` kunt u controleren of de gedragsgegevens naar Adobe Commerce worden verzonden. U kunt de ontwikkelaarsgereedschappen gebruiken die beschikbaar zijn in Chrome, of de extensie Snowplow Chrome installeren. Raadpleeg voor meer informatie [Problemen oplossen [!DNL Product Recommendations] module](https://support.magento.com/hc/en-us/articles/360042224851) in de Support Knowledge Base.

## Verifiëren met ontwikkelaarsgereedschappen in Chrome

Om ervoor te zorgen dat het JS-bestand van de gebeurtenisverzamelaar op alle sitepagina&#39;s wordt geladen:

1. Kies in Chrome de optie **Google Chrome aanpassen en beheren** Selecteer vervolgens **Meer gereedschappen** > **Gereedschappen voor ontwikkelaars**.
1. Kies de optie **Netwerk** selecteert u vervolgens de **JS** type.
1. Filter voor `ds.`
1. Laad de pagina opnieuw.
1. U moet `ds.js` of `ds.min.js` in de **Naam** kolom.

![JS voor gebeurteniscollector](assets/filter-ds.png)
_JS van gebeurteniscollector_

Om ervoor te zorgen dat de gebeurtenissen op pagina&#39;s over uw plaats (huis, product, kassa, etc.) worden afgevuurd:

1. Zorg ervoor dat u eventuele advertentieblokkers in uw browser uitschakelt en cookies op de site accepteert.
1. Kies in Chrome de optie **Google Chrome aanpassen en beheren** (de drie verticale stippen in de rechterbovenhoek van de browser) en selecteer **Meer gereedschappen** > **Gereedschappen voor ontwikkelaars**.
1. Kies de optie **Netwerk** tab en filter voor `tp2`.
1. Laad de pagina opnieuw.
1. U zou vraag onder moeten zien `tp2` in de **Naam** kolom.

![Gebeurtenissen parseren](assets/filter-tp2.png)
_Controleren of gebeurtenissen worden geactiveerd_

## Verifiëren met de extensie Snowplow Chrome

Installeer de [De extensie Snowplow Analytics Debugger voor Chrome](https://chrome.google.com/webstore/detail/snowplow-analytics-debugg/jbnlcgeengmijcghameodeaenefieedm). Deze extensie geeft de gebeurtenissen weer die worden verzameld en naar Adobe Commerce worden verzonden.

1. Zorg ervoor dat u eventuele advertentieblokkers in uw browser uitschakelt en cookies op de site accepteert.

1. Kies in Chrome de optie **Google Chrome aanpassen en beheren** (de drie verticale stippen in de rechterbovenhoek van de browser) en selecteer **Meer gereedschappen** > **Gereedschappen voor ontwikkelaars**.

1. Kies de optie **Foutopsporing voor Snowplow-analyse** tab.

1. Onder de **Gebeurtenis** kolom, selecteren **Gestructureerde gebeurtenis**.

1. Omlaag schuiven totdat u ziet **Contextgegevens _n_**. Zoek de storefront-instantie in het dialoogvenster **Schema**.

1. Controleer of de [SaaS Data Space ID](https://docs.magento.com/user-guide/configuration/services/saas.html) correct is ingesteld.

![Sneeuwlaag, filter](assets/snowplow-filter.png)
_Sneeuwlaag, filter_

>[!NOTE]
>
> Een waarde van `Data validity : NOT FOUND` in debugger wijst op een intern schema. De insteekmodule Snowplow Chrome kan de gebeurtenissen niet valideren met een intern schema. Dit heeft geen invloed op de eigenlijke functionaliteit.

## Controleren of gebeurtenissen correct worden geactiveerd

Om te verifiëren dat de gebeurtenissen die voor metriek worden gebruikt correct zijn, zoek naar `impression-render`, `view`, en `rec-click` gebeurtenissen in Foutopsporing voor Snowplow-analyse. Zie de [volledige lijst van gebeurtenissen](https://devdocs.magento.com/recommendations/events.html).

>[!NOTE]
>
> Indien [Modus Cookie-beperking](https://docs.magento.com/user-guide/stores/compliance-cookie-restriction-mode.html) is ingeschakeld, verzamelt Adobe Commerce geen gedragsgegevens tot de klant hiermee instemt. Als de modus Cookie-beperking is uitgeschakeld, worden standaardgedragsgegevens verzameld.
