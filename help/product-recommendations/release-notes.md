---
title: '''[!DNL Product Recommendations] Opmerkingen bij de release'
description: De meest recente releasegegevens voor [!DNL Product Recommendations] uit Adobe Commerce.
exl-id: 1758e688-d26f-45e7-818c-d4726338a6c3
feature: Services, Recommendations, Release Notes
source-git-commit: 6f31361e95b17ee3fa19ff3c2f4a7e2d6d9bc091
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 0%

---

# [!DNL Product Recommendations] Opmerkingen bij de release

De releaseopmerkingen bevatten updates voor het volgende [!DNL Product Recommendations] modules:

* [!DNL Product Recommendations] pakket: `magento/product-recommendations`
* Ondersteuning voor Page Builder in [!DNL Product Recommendations] (optioneel) module: `magento/module-page-builder-product-recommendations`
* Visuele steun van het type van gelijkheidsaanbeveling voor [!DNL Product Recommendations] (optioneel) module: `magento/module-visual-product-recommendations`

Er wordt ondersteuning geboden voor de belangrijkste uitgebrachte versie. Opmerkingen bij de release voor oudere versies worden ter referentie verschaft.
De opmerkingen bij de release omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Repareren](../assets/fix.svg) Oplossingen en verbeteringen
![Bug](../assets/bug.svg) Bekende problemen

Zie de documentatie voor ontwikkelaars op [informatie over productondersteuning](https://experienceleague.adobe.com/en/docs/commerce-operations/release/product-availability).

## Gehoste service-updates

Deze nota&#39;s beschrijven updates of bekende kwesties die buiten een versioned versie of verbeteringen aan de ontvangen dienst werden gepubliceerd of ontdekt.

_28 juni 2024_

![Bug](../assets/bug.svg) Aan de kar toegevoegde producten van een [!DNL Product Recommendations] -eenheid op de winkelwagentje niet worden verwijderd uit de lijst met aanbevolen producten wanneer de winkelwagentje opnieuw wordt geladen.
![Bug](../assets/bug.svg) Producten die uit het winkelwagentje worden verwijderd, blijven in het `cartSkus` -array tot de winkelwagentje opnieuw wordt geladen.

_18 juli 2023_

![Nieuw](../assets/new.svg) [!DNL Product Recommendations] heeft nu een GraphQL [`recommendations`](https://developer.adobe.com/commerce/services/graphql/recommendations/recommendations/) query.

_25 april 2023_

![Nieuw](../assets/new.svg) [!DNL Product Recommendations] klanten kunnen nu profiteren van [Prijsindexering SaaS](../price-index/price-indexing.md).

## Huidige hoofdversie

### 6.0.2 van magento/productaanbevelingen

_9 mei 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Probleem verholpen waarbij werd geklikt op de knop **[!DNL Add to Cart]** op een eenvoudig product in een Product Recommendations-eenheid werd de winkelner omgeleid naar de homepage in plaats van op de huidige pagina te blijven.
![Bug](../assets/bug.svg) Er is een validatiefout veroorzaakt door de `referenceBlock` in het `ProductRecommendations Layout` XML-bestand

### Vorige versies

### 6.0.1 van magento/productaanbevelingen

_19 maart 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Ondersteuning voor PHP 8.3 toegevoegd.

### 6.0.0 van magento/product-recommendations

_22 februari 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De [!DNL Catalog Sync Dashboard] is nu [[!DNL Data Management Dashboard]](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard). Dit vernieuwde dashboard biedt inzichten in gegevensstromen voor [!DNL Product Recommendations], [!DNL Live Search], en [!DNL Catalog Service].
![Repareren](../assets/fix.svg) Probleem verholpen waarbij afrekenfouten werden veroorzaakt voor [!DNL Product Recommendations].

+++5.0.0 en eerder

### 5.0.1 van magento/productaanbevelingen

_15 september 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Nieuwe modules toegevoegd ter ondersteuning van de [Saas Price Index](../price-index/price-indexing.md).
![Nieuw](../assets/new.svg) Er zijn nieuwe gegevensexportmodules toegevoegd ter ondersteuning van het exporteren van meer producttypen, waaronder gebundelde producten en cadeaukaarten.
![Repareren](../assets/fix.svg) De tabelgrootte van de producten en de prijsvoeding is sterk afgenomen. Tabellen `catalog_data_exporter_products` en `catalog_data_exporter_product_prices` moet een aanzienlijke vermindering van de omvang zien.

#### Bekende beperkingen

* De `websiteCode` value is incorrect teruggekeerd als het een onderstrepingsteken (_) bevat.

### 5.0.0 van magento/productaanbevelingen

_20 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Bijgewerkt [!DNL Product Recommendations] ter ondersteuning van Adobe Commerce 2.4.6.
![Nieuw](../assets/new.svg) Dit is een belangrijke versie. [Bewerken](install-configure.md#update) de basis `composer.json` bestand voor uw project.
![Nieuw](../assets/new.svg) [!DNL Product Recommendations] ondersteunt nu volledig [Inventory management](https://experienceleague.adobe.com/en/docs/commerce-admin/inventory/introduction) Mogelijkheden in Commerce (voorheen bekend als Multi-Source Inventory, of MSI). Om volledige steun toe te laten, moet u [update](install-configure.md#update) de afhankelijkheidsmodule `commerce-data-export` naar versie 102.2.0+.

### 4.0.1 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Eerder [!DNL Product Recommendations] zou een fout tonen wanneer de weergavetunt werd overgeschakeld naar een niet-standaardvaluta. Wisselen naar andere valuta werkt nu goed.

### 4.0.0 van magento/product-recommendations

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegd [gereedheidsindicatoren](create.md) om u te helpen de opleidingsvooruitgang van elk aanbevelingstype visualiseren.
![Nieuw](../assets/new.svg) Dit is een belangrijke versie. [Bewerken](install-configure.md#update) de basis `composer.json` bestand voor uw project. Voor deze release moet u ook twee API-sleutels opgeven bij de installatie en configuratie [!DNL Product Recommendations]: [een productiesleutel en een sandboxsleutel](../landing/saas.md).

#### Bekende beperkingen

* De `websiteCode` value is incorrect teruggekeerd als het een onderstrepingsteken (_) bevat.

### 3.3.7 van de aanbevelingen van magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Ondersteuning voor PHP 8.1 toegevoegd
![Nieuw](../assets/new.svg) Verbeterde afbeeldingsgrootte wordt aangepast, zodat de afbeeldingsgrootte in de referentiesjabloon consistenter wordt verwerkt

### 3.3.6 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Geoptimaliseerd [!DNL Product Recommendations] metapakket door de gebiedsdelen uitdrukkelijk te vermelden

### 3.3.5 van de aanbevelingen van magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegd [B2B-ondersteuning](onboarding.md#b2bsupport) in [!DNL Product Recommendations]
![Nieuw](../assets/new.svg) Nieuwe feeds toegevoegd aan [catalogusgegevens synchroniseren](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/user-guides/data-services/catalog-sync) naar Commerce Services via de opdrachtregel

### 3.3.3 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Nieuw toegevoegd [typen aanbevelingen](type.md): Conversie (weergave naar winkelwagentje), Conversie (weergave voor aankoop) en Recent weergegeven. Deze nieuwe aanbevelingen zijn beschikbaar in het dialoogvenster `magento/product-recommendations` module 3.2.2 en hoger.
![Repareren](../assets/fix.svg) Probleem verholpen waarbij Fastly&#39;s Web Application Firewall (WAF) een cookie onjuist blokkeerde
![Repareren](../assets/fix.svg) Producten die waren toegewezen aan de niet-standaardwinkelweergave werden niet weergegeven in het dialoogvenster _Recommendations-productvoorvertoning_ wanneer u een aanbeveling voor die specifieke winkelweergave maakt
![Repareren](../assets/fix.svg) Bepaalde namen van aanbevelingen in de Page Builder stonden de aanbeveling-eenheid niet in de winkel. Dit probleem is nu opgelost.

### 3.3.2. van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Oplossing voor ontbrekende afhankelijkheid voor B2B-ondersteuning

### 3.3.1. van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Extra ondersteuning voor B2B-klantgroepprijzen. Wanneer u een [prijsfilter](filters.md) op een aanbeveling-eenheid zien B2B-klanten die zijn aangemeld de prijsstelling voor de klantengroep die voor de weergegeven producten is ingesteld.

### 3.3.0 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegde steun voor de Laag van Gegevens van de Cliënt van de Adobe om gedragsgegevensinzameling over eigenschappen en de diensten van Adobe Commerce te standaardiseren. Zie de [readme](https://github.com/adobe/commerce-events/blob/main/packages/storefront-events-collector/README.md) voor meer informatie.

### 3.2.6 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Modaal JavaScript-fout opgelost
![Repareren](../assets/fix.svg) Probleem verholpen waarbij Fastly&#39;s Web Application Firewall (WAF) een cookie onjuist blokkeerde

### 3.2.5 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De naam van services voor Magento&#39;s wijzigen in [Commerce Services](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/user-guides/integration-services/saas) en verbeterde bruikbaarheid in de beheerder

### 3.2.4 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Oplossing voor de fout &#39;&#39;Kan configureerbare gegevens voor productopties niet ophalen&#39;&#39; bij het indexeren van productkenmerken

### 3.2.3 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Correctie van de fout &#39;&#39;Kan configureerbare gegevens voor productopties niet ophalen&#39;&#39; tijdens synchroniseren van catalogus.
![Repareren](../assets/fix.svg) Probleem verholpen waarbij de opslagcode niet correct werd ingesteld toen u de configuratie &quot;Winkelcode toevoegen aan URL&quot; inschakelde. Dit probleem is nu opgelost.
![Repareren](../assets/fix.svg) Verbeterde detectie van wijzigingen in de configuratie van het deelvenster Admin om ervoor te zorgen dat deze wijzigingen worden weerspiegeld in de gegevens van Catalog Sync

### 3.2.2. van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De mogelijkheid toegevoegd om [voorvertoning van aanbevelingen](create.md) tijdens het maken. Hiervoor moet u mogelijk de module bijwerken naar de meest recente versie.
![Nieuw](../assets/new.svg) De mogelijkheid toegevoegd om [bewaken en beheren](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/user-guides/data-services/catalog-sync) het synchronisatieproces van de catalogus door de beheerder.
![Nieuw](../assets/new.svg) Toegevoegd [filters](filters.md) om te controleren welke producten in aanbevelingen worden getoond.
![Nieuw](../assets/new.svg) De [Visuele gelijkenis](type.md#visualsim) soort aanbeveling.

### 1.2.1 van magento/module-page-builder-product-recommendations for Page Builder

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Toegevoegde ondersteuning voor de 3.2.0+-versie van de `magento/product-recommendations` module

### 3.1.0 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) De mogelijkheid toegevoegd om [resync](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/user-guides/data-services/catalog-sync) uw catalogus naar SaaS-services via de opdrachtregel.
![Nieuw](../assets/new.svg) Extra ondersteuning voor voorvoegsels van databasetabellen
![Repareren](../assets/fix.svg) Ondersteuning voor PHP 7.1 is verwijderd

### 3.0.8 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Probleem verholpen waarbij gebeurtenissen werden verzonden voor gegevensverzameling voordat de module werd geconfigureerd, wat ongeldig verkeer veroorzaakte. Dit probleem is nu opgelost.

### 3.0.6 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) **(Beta)** Inclusief ondersteuning voor nieuwe [Visuele gelijkenis](type.md#visualsim) soort aanbeveling.

### 1.0.0 van magento/module-visual-product-recommendations

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) **(Beta)** [Visuele gelijkenis](type.md#visualsim). Met de _Visuele gelijkenis_ met aanbevelingen kunt u een aanbevolen eenheid op de pagina met productdetails plaatsen waarop producten worden weergegeven die visueel lijken op het product dat wordt weergegeven.

### 3.0.5 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Correctie van de fout &#39;&#39;Kan gegevens over productopties niet ophalen&#39;&#39; die tijdens het exporteren van de catalogus kon optreden.
![Repareren](../assets/fix.svg) Het valutasymbool in het dialoogvenster _Ontvangsten_ kolom op de _[!DNL Product Recommendations]_het dashboard geeft nu correct de geconfigureerde basisvaluta weer .

### 3.0.4 van de aanbevelingen inzake magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Extra ondersteuning voor Adobe Commerce 2.4.0

### 3.0.3 van de aanbevelingen van magento/product

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg) Verbeterde symboolimplementatie in storefront sjabloon

### 1.0.4 van magento/module-page-builder-product-recommendations for Page Builder

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Naam van toegevoegde productaanbeveling bij het bewerken van het inhoudstype van de Page Builder

### 3.0.2 magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Een statuskolom toegevoegd aan het raster wanneer u Aanbeveling-eenheden selecteert in Page Builder
![Repareren](../assets/fix.svg) Probleem verholpen met onjuiste http/https-protocollen in product- en afbeeldings-URL&#39;s

### 3.0.1 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

Dit is een belangrijke versie. [Bewerken](install-configure.md#update) het hoofdbestand composer.json van uw project.

![Nieuw](../assets/new.svg) Ophalen [!DNL Product Recommendations] van alternatieve SaaS-gegevensruimten. Hierdoor kunt u [!DNL Product Recommendations] berekend in uw productomgeving op andere, niet-productieomgevingen. [Schakelen tussen SaaS-gegevensruimten](settings.md) Deze functie wordt verder beschreven.

![Repareren](../assets/fix.svg) Probleem verholpen waarbij afhandeling werd geblokkeerd voor kopers die de Blokoorsprong gebruikten
![Repareren](../assets/fix.svg) Probleem opgelost waarbij externe add-to-cart-gebeurtenissen werden verzonden

### 1.0.3 van magento/module-page-builder-product-recommendations for Page Builder

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Ondersteuning voor Page Builder. Met de integratie van de Bouwer van de Pagina, kunt u de eenheden van de Aanbeveling nauwkeurig en korrelig in om het even welke willekeurige plaats op de Bouwer van de Pagina-geschreven inhoud plaatsen. U kunt ook zelf de koppen en aanbevelingen opmaken. Ga naar [Page Builder](https://experienceleague.adobe.com/en/docs/commerce-admin/page-builder/add-content/recommendations) voor meer informatie .

### 2.0.0 van magento/productaanbevelingen

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg) Algemene beschikbaarheidsrelease!

+++

## Documentatie

Meer informatie over [!DNL Product Recommendations] en [!DNL Product Recommendations] ontwikkeling:

* [Gebruikershandleiding](overview.md)
* [Documentatie voor ontwikkelaars](https://experienceleague.adobe.com/en/docs/commerce-merchant-services/product-recommendations/developer/development-overview)
