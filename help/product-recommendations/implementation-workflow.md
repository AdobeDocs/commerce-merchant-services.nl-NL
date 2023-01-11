---
title: Implementatieworkflow
description: Leer de stappen die u met succes wilt implementeren [!DNL Product Recommendations] op je winkel.
exl-id: 766e1191-0330-4515-9331-e45318539dc9
source-git-commit: 3d0de3eeb4aa96c996bc9fa38cffd7597e89e7ca
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Implementatieworkflow

[!DNL Product Recommendations] gebruikt zowel gedrags- als catalogusgegevens:

- Gedrag - Gegevens uit de betrokkenheid van een winkelier op uw site, zoals productweergaven, aan een winkelwagentje toegevoegde items en aankopen. Adobe Commerce en Adobe Sensei verzamelen geen persoonlijk identificeerbare informatie.

- Catalogus - Productmetagegevens, zoals naam, prijs en beschikbaarheid.

Wanneer u de `magento/product-recommendations module`, voegt Adobe Sensei de gedrags- en catalogusgegevens samen en maakt [!DNL Product Recommendations] voor elk type aanbeveling. De [!DNL Product Recommendations] De dienst stelt dan die aanbevelingen aan uw winkel op. Om u te helpen productaanbevelingen op uw winkel uitvoeren, gebruik het volgende werkschema:

>[!NOTE]
>
> Als uw storefront met PWA Studio wordt uitgevoerd, verwijs naar [PWA-documentatie](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/). Als u een aangepaste frontend-technologie gebruikt, zoals React of Vue JS, leert u hoe te [integreren](headless.md) [!DNL Product Recommendations] in je eindeloze winkel.

## Workflow

1. **Gegevensverzameling implementeren voor productie**

   Implementeren [!DNL Product Recommendations] vereist twee hoofdlijnen [gegevensbronnen](type.md): catalogus en gedrag. Omdat productie de enige omgeving is waarin de acties van uw klanten worden vastgelegd en geanalyseerd, is het in uw belang om zo snel mogelijk met gegevensverzameling over productie te beginnen. [Meer informatie](behavioral-data.md) hoe Adobe Sensei modellen leert die leiden tot betere kwaliteit. Als extra voordeel, wanneer u begint gedragsgegevens over productie te verzamelen, kunt u [aanbevelingen ophalen](verify.md) op basis van deze productiegegevens in een niet-productieomgeving. Vervolgens kunt u testen en experimenteren met verschillende aanbevelingen die worden berekend op basis van echte verkoopgegevens die in productie worden verzameld.

   Om gegevensinzameling aan productie op te stellen, moet u [installeren en configureren](install-configure.md) de [!DNL Product Recommendations] door een [API-sleutel](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html).

   >[!TIP]
   >
   > Het implementeren van gegevensverzameling heeft geen invloed op de weergave van de winkel of op de ervaring van kopers. Het creëren van en het opstellen van aanbevelingen veranderen slechts de klantenervaring op uw winkelfront. Zorg ervoor u op uw niet productiemilieu test alvorens aan productie op te stellen. Creëer ook geen aanbevelingen-eenheden totdat u de sjabloon aanpast. Zie de volgende stap.

1. **De sjabloon aanpassen aan uw stijl**

   Uw winkel vertegenwoordigt uw merk, dus zorg ervoor u het malplaatje van productaanbevelingen aanpast om uw plaatsthema aan te passen.

   >[!TIP]
   >
   > Door het malplaatje aan te passen, kunt u uw stijlblad specificeren, beschrijven waar een aanbevelingseenheid op een pagina, etc. verschijnt.

   Zie [Aanpassen](https://experienceleague.adobe.com/docs/commerce-merchant-services/product-recommendations/developer/customize.html) in de ontwikkelaarsdocumentatie leren hoe te om deze stap te voltooien.

1. **Testaanbevelingen voor uw niet-productieomgeving**

   Het is altijd een beste praktijk om een nieuwe technologie op uw niet productiemilieu te testen alvorens u aan productie opstelt. Als u aanbevelingen test voor uw niet-productieomgeving, kunt u met verschillende typen aanbevelingen, positionering en pagina&#39;s spelen. U kunt aanbevelingen trekken die op gedragsgegevens reeds bij productie terwijl het testen in uw niet productieklimaat worden verzameld, zodat de raadsresultaten op het het winkelen gedrag van daadwerkelijke klanten gebaseerd zijn.

   >[!TIP]
   >
   > Zorg ervoor dat de niet-productieomgevingscatalogus grotendeels dezelfde is als de catalogus die u in productie hebt. Door vergelijkbare catalogi te gebruiken, zorgt u ervoor dat de producten die in de aanbevolen eenheden worden geretourneerd, de producten op productie nauwkeurig nabootsen.

   Zie [Ophalen](staging-environment.md) gedragsgegevens uit uw productieomgeving om te leren hoe u deze stap kunt voltooien.

1. **Aanbevelingen voor uw productiewinkel maken en implementeren**

   Nu u de verzameling van gedragsgegevens in productie hebt geïmplementeerd, de sjabloon voor productaanbevelingen hebt gewijzigd en aanbevelingen hebt getest met daadwerkelijk verkoopgedrag, bent u klaar om alle code te promoten naar productie en [maken](create.md) aanbevelingen voor levende producten.
