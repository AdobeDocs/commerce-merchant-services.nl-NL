---
title: "Grens en grenzen"
description: Leer over de grenzen en de grenzen voor  [!DNL Live Search]  om ervoor te zorgen het aan de behoeften van uw zaken voldoet.
role: Admin, Developer
exl-id: ad6737f9-6ecd-4d82-89e7-d95425e4ba53
source-git-commit: 61ebda0015c6d5a7c0bb08f7aae9a4593bca84a4
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 0%

---

# Grenzen en grenzen

Adobe Commerce biedt opties voor het zoeken naar sites. Controleer de volgende grenzen en grenzen om ervoor te zorgen dat [!DNL Live Search] en [!DNL Catalog Service] aan de behoeften van uw zaken voldoen. Als u geavanceerde onderzoeksmogelijkheden zoals inhoudsonderzoek nodig hebt, breng-uw-eigen-algoritme (BYOA), of op attribuut-gebaseerde handel, overweeg een derdezoekoplossing.

## Algemeen

- De [ Geavanceerde module van het Onderzoek ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/catalog/search/search) wordt onbruikbaar gemaakt wanneer [!DNL Live Search] wordt geïnstalleerd, en de Geavanceerde verbinding van het Onderzoek in storefront wordt verwijderd.
- [ Rij die ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/products/pricing/product-price-tier) en [ Speciale Prijsverhoging ](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/products/pricing/product-price-special) wordt [!DNL Live Search] niet gesteund op het gebied en van de Lijst van het Product van de Pagina Widget.
- De productprijzen omvatten geen btw.
- Zoeken naar inhoud wordt niet ondersteund.
- Er is een limiet van 10.000 producten die gepagineerd kunnen worden.
- Er geldt een harde limiet van 1 MB per kenmerk, inclusief beschrijving en aangepaste kenmerken.
- De zoekadapter ondersteunt geen productkenmerken die zijn gemaakt met een aangepast bronmodel en die als facetten worden gebruikt. Om deze functionaliteit te steunen, moet u het [ product gebruiken dat van de Pagina Widget ](plp-styling.md) van de Pagina een lijst maakt.

## Indexeren

- [!DNL Live Search] [ indexen ](indexing.md) tot een totaal van 450 productattributen per archiefmening. Deze worden als volgt verdeeld:
   - 50 sorteerbare kenmerken
   - 200 filterbare kenmerken
   - 200 doorzoekbare kenmerken
- [!DNL Live Search] indexeert alleen producten uit de Adobe Commerce-database.
- CMS-pagina&#39;s worden niet geïndexeerd.
- SKU-, naam- en categoriekenmerken kunnen standaard worden doorzocht en kunnen niet worden uitgesloten van de zoekopdracht. Zorg ervoor dat u de toewijzing van de producten uit de categorieën ongedaan maakt als ze niet in die categorieën mogen voorkomen.

## Facetten

- Een maximum van 100 attributen kan als facetten van de 200 filterbare attributen worden gevormd die kunnen worden geïndexeerd.
- Binnen een facet kunnen maximaal 30 emmers worden geretourneerd. Als meer dan 30 emmers moeten zijn teruggekeerd, [ creeer een steunkaartje ](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide) zodat kan de Adobe het prestatieseffect analyseren en bepalen als het haalbaar is om deze grens voor uw milieu te verhogen.
- Dynamische facetten kunnen prestatieproblemen veroorzaken in grote indexen en indexen met hoge rangorde. Als u dynamische facetten hebt gemaakt en u merkt dat de prestaties achteruitgaan of dat de pagina niet wordt geladen met time-outfouten, kunt u proberen uw facetten te wijzigen in vastgezet om te bepalen of dat het prestatieprobleem verhelpt.
- De voorraadstatus (`quantity_and_stock_status`) wordt niet ondersteund als facet. U kunt `inStock: 'true'` gebruiken om te filteren uit aandelenproducten. Dit wordt vanuit het vak in de module `LiveSearchAdapter` ondersteund wanneer &quot;Display out of stock products&quot; is ingesteld op &quot;True&quot; in [!DNL Commerce] Admin.
- Datumtypekenmerken worden niet als facet ondersteund.

## Query

- [!DNL Live Search] gebruikt een uniek [ eindpunt van GraphQL ](https://developer.adobe.com/commerce/services/graphql/live-search/) voor vragen om eigenschappen zoals dynamisch facetten en onderzoek-als-u-type te steunen. Hoewel gelijkaardig aan [ GraphQL API ](https://developer.adobe.com/commerce/webapi/graphql/), zijn er een paar verschillen en sommige gebieden kunnen niet volledig compatibel zijn.
- Het maximumaantal resultaten dat in een onderzoeksvraag kan worden teruggekeerd is 10.000.
- Het is niet mogelijk om resultaten te filteren met behulp van een datumtype-kenmerk.

## Regels

- Het maximumaantal onderzoek handelend [ regels ](rules.md) per archiefmening is 50.
- Voor het verhandelen van categorieën kan één regel per categorie gelden.
- Het maximumaantal voorwaarden per regel is 10.
- Het maximumaantal gebeurtenissen per regel is 25.

## Synoniemen

- [!DNL Live Search] kan tot 200 [ synoniemen ](synonyms.md) per archiefmening beheren.
- Synoniemen van meerdere woorden werken mogelijk niet altijd naar behoren. Zorg ervoor dat u deze synoniemen in de testomgeving test voordat u ze in de productie gebruikt, omdat ze mogelijk een negatief effect hebben op de relevantie.

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
- Ondersteuning voor de functie Out-of-box voor B2B met de PLP-widget op PWA Studio wordt momenteel niet ondersteund. Nochtans, kunt u [ gebruiken API ](install.md#pwa-support) om deze functionaliteit uit te voeren.
- Categoriefacetten in [!DNL Live Search] kunnen categorieën weergeven die niet aan een bepaalde klantengroep kunnen worden weergegeven.

## [!DNL Storefront popover]

- [[!DNL popover]](storefront-popover.md) is beschikbaar slechts voor opslag die het ** thema Luma, of een aangepast thema gebruiken dat op *Luma* gebaseerd is. De bakkrummen op de pagina van onderzoeksresultaten zullen niet *Luma* stileren.
- [!DNL popover] steunt niet het *Lege* thema.
- [!DNL popover] wordt niet ondersteund op het formulier Snelle volgorde.
- Schijflijsten en productvergelijkingen worden niet ondersteund.
