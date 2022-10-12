---
title: Opmerkingen bij de release
description: De meest recente releasegegevens voor [!DNL Product Recommendations] uit Adobe Commerce.
exl-id: 1758e688-d26f-45e7-818c-d4726338a6c3
source-git-commit: ab7bb72826ff3aee1ce93d30dde0a752ef8069de
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 0%

---

# Opmerkingen bij de release

De releaseopmerkingen bevatten updates voor het volgende [!DNL Product Recommendations] modules:

* Vanaf maart 2021 [!DNL Product Recommendations] worden nu ondersteund in [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/product-recommendations/) opslagronten.
* [!DNL Product Recommendations] pakket: `magento/product-recommendations`
* Ondersteuning voor Page Builder in [!DNL Product Recommendations] (optioneel) module: `magento/module-page-builder-product-recommendations`
* Visuele steun van het type van gelijkheidsaanbeveling voor [!DNL Product Recommendations] (optioneel) module: `magento/module-visual-product-recommendations`

De opmerkingen bij de release omvatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen

Zie de documentatie voor ontwikkelaars [informatie over productcompatibiliteit](https://devdocs.magento.com/release/availability.html).

## Adobe Commerce 2.3.x en 2.4.x

## 4.0.0 van magento/product-recommendations

* ![Nieuw](../assets/new.svg) - Toegevoegd [gereedheidsindicatoren](create.md) om u te helpen de opleidingsvooruitgang van elk aanbevelingstype visualiseren.
* ![Nieuw](../assets/new.svg) - Dit is een belangrijke versie. U moet [bewerken](install-configure.md#update) de basis `composer.json` bestand voor uw project. Voor deze release moet u ook twee API-sleutels opgeven bij de installatie en configuratie van Product Recommendations: [een productiesleutel en een sandboxsleutel](../landing/saas.md).

### Bekende beperkingen

* De `websiteCode` value is incorrect teruggekeerd als het een onderstrepingsteken (_) bevat.

## 3.3.7 van de aanbevelingen van magento/product

* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor PHP 8.1
* ![Nieuw](../assets/new.svg) - Verbeterde afbeeldingsgrootte, zodat afbeeldingen van verschillende grootte consistenter worden verwerkt in de referentiesjabloon

## 3.3.6 van de aanbevelingen inzake magento/product

* ![Nieuw](../assets/new.svg) - Geoptimaliseerd [!DNL Product Recommendations] metapakket door de gebiedsdelen uitdrukkelijk te vermelden

### 3.3.5 van de aanbevelingen van magento/product

* ![Nieuw](../assets/new.svg) - Toegevoegd [B2B-ondersteuning](onboarding.md#b2bsupport) in Product Recommendations
* ![Nieuw](../assets/new.svg) - Nieuwe feeds toegevoegd aan [catalogusgegevens synchroniseren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-catalog-sync.html) aan Commerce Services via de opdrachtregel

### 3.3.3 van de aanbevelingen inzake magento/product

* ![Nieuw](../assets/new.svg) - Nieuw toegevoegd [typen aanbevelingen](type.md): Conversie (weergave naar winkelwagentje), Conversie (weergave voor aankoop) en Recent bekeken. Deze nieuwe aanbevelingen zijn beschikbaar in het dialoogvenster `magento/product-recommendations` module 3.2.2 en hoger.
* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij Fastly&#39;s Web Application Firewall (WAF) een cookie onjuist blokkeerde
* ![Repareren](../assets/fix.svg) - Producten die waren toegewezen aan de niet-standaardwinkelweergave werden niet weergegeven in de _Recommendations-productvoorvertoning_ wanneer u een aanbeveling voor die specifieke winkelweergave maakt
* ![Repareren](../assets/fix.svg) - Bepaalde namen van aanbevolen eenheden in de Page Builder stonden de aanbeveling-eenheid niet in de winkel. Dit probleem is nu opgelost.

### 3.3.2. van magento/productaanbevelingen

* ![Repareren](../assets/fix.svg) - Oplossing voor ontbrekende afhankelijkheid voor B2B-ondersteuning

### 3.3.1. van magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor B2B-klantgroepprijzen. Wanneer u een [prijsfilter](filters.md) op een aanbeveling-eenheid zien B2B-klanten die zijn aangemeld de prijsstelling voor de klantengroep die voor de weergegeven producten is ingesteld.

### 3.3.0 van magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor Adobe Client Data Layer om de verzameling van gedragsgegevens over Adobe Commerce-functies en -services te standaardiseren. Zie de [readme](https://github.com/adobe/magento-storefront-event-collector/blob/main/README.md) voor meer informatie.

### 3.2.6 van de aanbevelingen inzake magento/product

* ![Repareren](../assets/fix.svg) - Modaal JavaScript-fout opgelost
* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij Fastly&#39;s Web Application Firewall (WAF) een cookie onjuist blokkeerde

### 3.2.5 van de aanbevelingen inzake magento/product

* ![Nieuw](../assets/new.svg) - De naam Magento Services wijzigen in [Commerciële diensten](https://docs.magento.com/user-guide/system/saas.html) en verbeterde bruikbaarheid in de beheerder

### 3.2.4 van de aanbevelingen inzake magento/product

* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij de fout &quot;Kan gegevens met configureerbare productopties niet ophalen&quot; werd verholpen bij het indexeren van productkenmerken

### 3.2.3 van de aanbevelingen inzake magento/product

* ![Repareren](../assets/fix.svg) - Oplossing voor de fout &quot;Kan configureerbare gegevens voor productopties niet ophalen&quot; tijdens het synchroniseren van catalogi.
* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij de opslagcode niet correct werd ingesteld toen u de configuratie &quot;Winkelcode toevoegen aan URL&quot; inschakelde.
* ![Repareren](../assets/fix.svg) - Verbeterde detectie van wijzigingen in de configuratie van het deelvenster Admin om ervoor te zorgen dat deze wijzigingen worden doorgevoerd in de gegevens van Catalog Sync

### 3.2.2. van magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - De mogelijkheid om [voorvertoning van aanbevelingen](create.md) tijdens het maken. Hiervoor moet u mogelijk de module bijwerken naar de meest recente versie.
* ![Nieuw](../assets/new.svg) - De mogelijkheid om [bewaken en beheren](https://docs.magento.com/user-guide/system/catalog-sync.html) het synchronisatieproces van de catalogus door de beheerder.
* ![Nieuw](../assets/new.svg) - Toegevoegd [filters](filters.md) om te controleren welke producten in aanbevelingen worden getoond.
* ![Nieuw](../assets/new.svg) - Toegevoegde [Visuele gelijkenis](type.md#visualsim) soort aanbeveling.

### 1.2.1 van magento/module-page-builder-product-recommendations for Page Builder

* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor de 3.2.0+-versie van de `magento/product-recommendations` module

### 3.1.0 van magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - De mogelijkheid om [resync](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-catalog-sync.html) uw catalogus naar SaaS-services via de opdrachtregel.
* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor voorvoegsels van databasetabellen
* ![Repareren](../assets/fix.svg) - Verwijderde ondersteuning voor PHP 7.1

### 3.0.8 van magento/productaanbevelingen

* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij gebeurtenissen werden verzonden voor gegevensverzameling voordat de module werd geconfigureerd, wat ongeldig verkeer veroorzaakte

### 3.0.6 van de aanbevelingen inzake magento/product

* ![Nieuw](../assets/new.svg) - **(bèta)** Inclusief ondersteuning voor nieuwe [Visuele gelijkenis](type.md#visualsim) soort aanbeveling.

### 1.0.0 van magento/module-visual-product-recommendations

* ![Nieuw](../assets/new.svg) - **(bèta)** [Visuele gelijkenis](type.md#visualsim). Met de _Visuele gelijkenis_ met aanbevelingen kunt u een aanbevolen eenheid op de pagina met productdetails plaatsen waarop producten worden weergegeven die visueel lijken op het product dat wordt weergegeven.

### 3.0.5 van magento/productaanbevelingen

* ![Repareren](../assets/fix.svg) - Oplossing voor de fout &#39;&#39;Kan de gegevens van de productopties niet ophalen&#39;&#39; die tijdens het exporteren van de catalogus kon optreden.
* ![Repareren](../assets/fix.svg) - Het valutasymbool in de _Ontvangsten_ kolom op de _Product Recommendations_ het dashboard geeft nu correct de geconfigureerde basisvaluta weer .

### 3.0.4 van magento/productaanbevelingen

* ![Repareren](../assets/fix.svg) - Toegevoegde ondersteuning voor Adobe Commerce 2.4.0

### 3.0.3 van de aanbevelingen van magento/product

* ![Repareren](../assets/fix.svg) - Verbeterde symboolimplementatie in storefront-sjabloon

### 1.0.4 van magento/module-page-builder-product-recommendations for Page Builder

* ![Nieuw](../assets/new.svg) - Naam van toegevoegde productaanbeveling bij het bewerken van het inhoudstype van Page Builder

### 3.0.2 magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - Een statuskolom toegevoegd aan het raster wanneer u Aanbeveling-eenheden selecteert in de Page Builder
* ![Repareren](../assets/fix.svg) - Probleem verholpen met onjuiste http/https-protocollen in product- en afbeeldings-URL&#39;s

### 3.0.1 van magento/productaanbevelingen

Dit is een belangrijke versie. U moet [bewerken](install-configure.md#update) het hoofdbestand composer.json van uw project.

* ![Nieuw](../assets/new.svg) - Ophalen [!DNL Product Recommendations] van alternatieve SaaS-gegevensruimten. Hierdoor kunt u productaanbevelingen gebruiken die in uw productomgeving zijn berekend op andere, niet-productieomgevingen. [Schakelen tussen SaaS-gegevensruimten](settings.md) Deze functie wordt verder beschreven.

* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij het afrekenen werd geblokkeerd voor kopers die de Blokoorsprong gebruikten
* ![Repareren](../assets/fix.svg) - Probleem verholpen waarbij externe add-to-cart-gebeurtenissen werden verzonden

### 1.0.3 van magento/module-page-builder-product-recommendations for Page Builder

* ![Nieuw](../assets/new.svg) - Ondersteuning voor Page Builder. Met de integratie van de Bouwer van de Pagina, kunt u de eenheden van de Aanbeveling van de Aanbeveling in om het even welke willekeurige plaats op de Bouwer van de Pagina-geschreven inhoud nauwkeurig en korrelig plaatsen. U kunt ook zelf de koppen en aanbevelingen opmaken. Ga naar [Page Builder](https://docs.magento.com/user-guide/cms/page-builder-add-recommendations.html) voor meer informatie .

### 2.0.0 van magento/productaanbevelingen

* ![Nieuw](../assets/new.svg) - Algemene beschikbaarheidsrelease!

## Documentatie

Meer informatie over [!DNL Product Recommendations] en [!DNL Product Recommendations] ontwikkeling:

* [Handboek](overview.md)
* [Documentatie voor ontwikkelaars](https://devdocs.magento.com/recommendations/product-recs.html)
