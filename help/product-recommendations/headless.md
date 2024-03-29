---
title: Koploos
description: Leer hoe u kunt integreren [!DNL Product Recommendations] in een koploze winkel.
exl-id: 316d0b0c-5938-4e2f-9d0d-747746cf6056
source-git-commit: 521ea4fc2cce809fc12d3958e37089f3e34e1068
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---

# Koploos

U kunt [!DNL Product Recommendations] in een koploze winkel met [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/) of een aangepaste frontend-technologie, zoals React of Vue JS.

Aangepaste integratoren en ontwikkelaars zonder kop dienen deze Luma- en PWA-instructies te gebruiken als een aanbevolen implementatie. Er zijn vele manieren om Product Recommendations in hoofdloze oplossingen uit te voeren en deze documentatie behandelt niet alle scenario&#39;s. Integratoren moeten gebeurtenissen, ontwerpen en testen voor hun implementaties bestrijken.

[!DNL Product Recommendations] vereisen [gedrags- en catalogusgegevens](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/development-overview.html) om te werken. Het synchronisatieproces van catalogusgegevens blijft ongewijzigd in een headless-implementatie, maar er zijn wijzigingen nodig voor het verzamelen van gedragsgegevens.

>[!NOTE]
>
>De instanties zonder kop moeten gebeurtenis uitvoeren om het Recommendations-dashboard van het Product van stroom te voorzien.

Om te integreren [!DNL Product Recommendations] in een koploze winkel, moet u:

1. Verstuur gedragsgegevens naar Adobe Sensei om de resultaten van de productaanbeveling te analyseren en te berekenen. U kunt ook aanvullende gegevens verzenden om productaanbevelingen in te schakelen [metrische rapportage](workspace.md).

1. Resultaten van productaanbevelingen ophalen en deze resultaten op de pagina weergeven.

U kunt beide handelingen uitvoeren met de beschikbare SDK&#39;s, zoals beschreven in de volgende workflow.

1. [Installeren](install-configure.md) de [!DNL Product Recommendations] -module.

1. De [Adobe Commerce Storefront Event SDK](https://developer.adobe.com/commerce/services/shared-services/storefront-events/sdk/) om de [gedragsgebeurtenissen](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/events.html).

   De minimaal vereiste gebeurtenissen om te retourneren [!DNL Product Recommendations] resultaten:

   | Gebeurtenis | Categorie |
   |--- | ---|
   | `view` | product |
   | `add-to-cart` | product |
   | `place-order` | uitchecken |

   Inschakelen [metrische rapportage](workspace.md)zijn de volgende aanvullende gebeurtenissen vereist:

   | Gebeurtenis | Categorie |
   |--- | ---|
   | `impression-render` | aanbeveling-eenheid |
   | `view` | aanbeveling-eenheid |
   | `rec-click` | aanbeveling-eenheid |
   | `rec-add-to-cart-click` | aanbeveling-eenheid (als een knop &quot;Toevoegen aan winkelwagentje&quot; aanwezig is in de sjabloon met aanbevelingen) |

1. Wanneer de gebeurtenissen worden geactiveerd, gebruikt u de opdracht [Adobe Commerce Storefront Event Collector](https://developer.adobe.com/commerce/services/shared-services/storefront-events/collector/) om de gebeurtenissen af te handelen en deze naar Adobe Sensei te verzenden.

1. Nadat de gedragsgegevens zijn verzameld, kunt u [maken](create.md) [!DNL Product Recommendations] in de Admin.

1. Gebruik de [RECOMMENDATIONS SDK](https://developer.adobe.com/commerce/services/product-recommendations/) om de aanbevolen eenheden op de winkel te krijgen. De SDK retourneert de benodigde productgegevens voor het weergeven van aanbevolen eenheden op een pagina.
