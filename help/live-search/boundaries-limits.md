---
title: "Grens en grenzen"
description: Meer informatie over de grenzen en grenzen van [!DNL Live Search] om ervoor te zorgen dat het voldoet aan de behoeften van uw bedrijf.
role: Admin, Developer
exl-id: ad6737f9-6ecd-4d82-89e7-d95425e4ba53
source-git-commit: 63c90d4ef0e14c0baaf8c79569a01e5dffa5b450
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Grenzen en grenzen

Adobe Commerce biedt opties voor het zoeken naar sites. Controleer de volgende grenzen en grenzen om ervoor te zorgen dat [!DNL Live Search] en [!DNL Catalog Service] voldoen aan de behoeften van uw bedrijf. Als u geavanceerde onderzoeksmogelijkheden zoals inhoudsonderzoek nodig hebt, breng-uw-eigen-algoritme (BYOA), of op attribuut-gebaseerde handel, overweeg een derdezoekoplossing.

## Algemeen

- De [Geavanceerd zoeken](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/catalog/search/search) module is uitgeschakeld wanneer [!DNL Live Search] wordt geïnstalleerd en wordt de koppeling Geavanceerd zoeken in de voettekst van de winkel verwijderd.
- [Prijsniveau](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/products/pricing/product-price-tier) en [Speciale prijzen](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/products/pricing/product-price-special) worden niet ondersteund in de [!DNL Live Search] veld- en pagina met productaanbiedingen.
- De productprijzen omvatten geen btw.
- Zoeken naar inhoud wordt niet ondersteund.
- Er is een limiet van 10.000 producten die gepagineerd kunnen worden.
- De zoekadapter ondersteunt geen productkenmerken die zijn gemaakt met een aangepast bronmodel en die als facetten worden gebruikt. Om deze functionaliteit te ondersteunen, moet u de [Widget pagina met productaanbiedingen](plp-styling.md).

## Indexeren

- [!DNL Live Search] [indexen](indexing.md) maximaal 450 productkenmerken per winkelweergave. Deze worden als volgt verdeeld:
   - 50 sorteerbare kenmerken
   - 200 filterbare kenmerken
   - 200 doorzoekbare kenmerken
- [!DNL Live Search] indexeert alleen producten uit de Adobe Commerce-database.
- CMS-pagina&#39;s worden niet geïndexeerd.
- SKU-, naam- en categoriekenmerken kunnen standaard worden doorzocht en kunnen niet worden uitgesloten van de zoekopdracht. Zorg ervoor dat u de toewijzing van de producten uit de categorieën ongedaan maakt als ze niet in die categorieën mogen voorkomen.

## Facetten

- Een maximum van 100 attributen kan als facetten van de 200 filterbare attributen worden gevormd die kunnen worden geïndexeerd.
- Binnen een facet kunnen maximaal 30 emmers worden geretourneerd. Indien meer dan 30 emmers moeten worden teruggegeven, [een ondersteuningsticket maken](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide) De Adobe kan dus het effect op de prestaties analyseren en bepalen of het haalbaar is om deze limiet voor uw omgeving te verhogen.
- Dynamische facetten kunnen prestatieproblemen veroorzaken in grote indexen en indexen met hoge rangorde. Als u dynamische facetten hebt gemaakt en u merkt dat de prestaties achteruitgaan of dat de pagina niet wordt geladen met time-outfouten, kunt u proberen uw facetten te wijzigen in vastgezet om te bepalen of dat het prestatieprobleem verhelpt.
- Status van voorraad (`quantity_and_stock_status`) wordt niet ondersteund als facet. U kunt `inStock: 'true'` om producten uit de voorraad te filteren. Dit wordt vanuit het vak in het dialoogvenster ondersteund `LiveSearchAdapter` wanneer &quot;Weergave van producten uit de voorraad&quot; is ingesteld op &quot;Waar&quot; in het dialoogvenster [!DNL Commerce] Admin.
- Datumtypekenmerken worden niet als facet ondersteund.

## Query

- [!DNL Live Search] heeft geen toegang tot de volledige taxonomie van de categorieboom, waardoor sommige gelaagde navigatie onderzoeksscenario&#39;s voorbij zijn bereik maken.
- [!DNL Live Search] gebruikt een unieke [GraphQL-eindpunt](https://developer.adobe.com/commerce/services/graphql/live-search/) voor vragen om eigenschappen zoals dynamische facetting en onderzoek-als-u-type te steunen. Hoewel vergelijkbaar met de [GRAPHQL API](https://developer.adobe.com/commerce/webapi/graphql/)Er zijn echter enkele verschillen en sommige gebieden zijn mogelijk niet volledig compatibel.
- Het maximumaantal resultaten dat in een onderzoeksvraag kan worden teruggekeerd is 10.000.
- Het is niet mogelijk om resultaten te filteren met behulp van een datumtype-kenmerk.

## Regels

- Het maximale aantal zoekopdrachten dat wordt verhandeld [regels](rules.md) per winkelweergave is 50.
- Voor het verhandelen van categorieën kan één regel per categorie gelden.
- Het maximumaantal voorwaarden per regel is 10.
- Het maximumaantal gebeurtenissen per regel is 25.

## Synoniemen

- [!DNL Live Search] kan maximaal 200 [synoniemen](synonyms.md) per winkelweergave.
- Synoniemen van meerdere woorden zijn beperkt tot 20 per winkelweergave.

## Categorie verhandelen

- Voor elke winkelweergave kan één regel per categorie worden gemaakt. Elke regel kan het volgende hebben:
   - Tot tien voorwaarden
   - Tot 25 gebeurtenissen

## B2B- en categoriemachtigingen

- Producten worden niet weergegeven als deze niet worden toegevoegd aan een standaard gedeelde catalogus.
- Om klantengroepen te beperken die de toestemmingen van de Catalogus gebruiken:
   - De producten moeten aan de categorie van de Wortel worden toegewezen.
   - Aan de klantengroep &quot;Niet aangemeld&quot; moeten de machtigingen &quot;Toestaan&quot; worden toegekend.
   - Om producten tot de &quot;niet Gelogde&quot;klantengroep te beperken, ga naar elke categorie en plaats toestemming voor elke klantengroep.
- Ondersteuning voor B2B met Live Search for PWA Studio wordt momenteel niet ondersteund.
