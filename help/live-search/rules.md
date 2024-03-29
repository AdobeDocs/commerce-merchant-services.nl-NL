---
title: "Search Merchandising"
description: "[!DNL Live Search] merchandising-regels combineren logica met acties om de winkelervaring vorm te geven."
exl-id: d06a3040-6987-4813-90ae-2f7b3ad0b232
source-git-commit: 2b0ca3f5a68e75ef4b4e71ac7705b17534e16845
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# Merchandising zoeken

Zoekhandel verwijst naar een set regels die logica combineert met handelingen om de zoekervaring van een klant in uw winkel vorm te geven. U kunt het veranderen van regels gebruiken om producten op te voeren, te begraven, te spelden, of te verbergen om onderzoeksresultaten in echt te kalibreren - tijd om uw bedrijfsdoelstellingen te steunen.

Elke regel heeft drie hoofdcomponenten:

* Voorwaarden - De voorwaarden die een handeling activeren.
* Gebeurtenissen - De acties die plaatsvinden wanneer aan de voorwaarden wordt voldaan.
* Details - De naam van de regel, en facultatief tijdkader en beschrijving.

U kunt meerdere voorwaarden en handelingen combineren en een regel voor een periode laten activeren. U kunt ook een standaardregel instellen die wordt toegepast, zelfs als er geen zoekterm is ingesteld.

## Vereisten

Een eenvoudige zoekregel kan één voorwaarde en één gebeurtenis hebben, terwijl een complexe regel tot tien voorwaarden kan hebben die tot 25 gebeurtenissen teweegbrengen.
Regels kunnen:

* Tot tien voorwaarden
* Tot 25 gebeurtenissen

Zoektekst kan het volgende bevatten:

* Alfanumerieke tekens (letters en cijfers)
* Hoofdletters of kleine letters. Kapitalisatie wordt genegeerd.

## Logische operatoren

Logische operatoren `AND` en `OR` twee voorwaarden samenvoegen en verschillende resultaten retourneren. Alle logische operatoren die in een regel met meerdere voorwaarden worden gebruikt, zijn hetzelfde. Het is niet mogelijk beide `AND` en `OR` in dezelfde regel.

### Operatoren afstemmen

De operatoren Afstemmen `All` en `Any` Bepaal de logische exploitant die wordt gebruikt om veelvoudige voorwaarden in de regel samen te voegen, en kan worden gebruikt om de bestaande exploitant te veranderen.

* `All` - Gebruikt de `AND` logische operator om meerdere voorwaarden samen te voegen. Een regel die de `All` Identieke operator kan slechts één hebben `Search query is` voorwaarde.
* `Any` - Gebruikt de `OR` logische operator om meerdere voorwaarden samen te voegen.

Wanneer het samenstellen van een complexe regel, kan het helpen om het met inspringing uit te schrijven om de voorwaarden, bijbehorende gebeurtenissen, en productnamen of SKUs te beschrijven die nodig zijn om de resultaten terug te keren u wilt bereiken. Vervolgens bouwt u de regel en test u het resultaat.

## Standaardregel

U kunt een standaardregel instellen die wordt toegepast wanneer geen zoekterm wordt opgegeven of wanneer geen andere zoekregel kan worden toegepast. Als u de standaardregel op &quot;Meest gekocht&quot;plaatst, dan zullen alle vragen aan dat rangschikkende type in gebreke blijven, tenzij super-ceded door een specifiekere onderzoekstermijn. Er kan geen zoekterm voor de standaardregel worden ingesteld.

## Volgorde van prioriteit met meerdere regels

Er wordt slechts één zoekregel tegelijk toegepast op een zoekterm.
Als meerdere regels van toepassing blijken te zijn op een zoekfrase, worden al deze regels toegepast. Als er een botsing is tussen twee regels—`rule 1` dat sku1 versterkt , maar `rule 2` verbergt zelfde SKU-toen de onlangs toegepaste regel (`rule 2`) heeft voorrang.

* Regels worden geordend met de tijdstempel &#39;Laatst gewijzigd&#39;. De regel die het laatst is gewijzigd, wordt eerst toegepast en daarna oudere regels in tijdstempelvolgorde.
* De `query is` voorwaarde heeft voorrang op andere voorwaarden. Als een nieuwere regel een `query contains` voorwaarde, maar een oudere regel heeft een `query is` voorwaarde, `query is` wordt toegepast.

### Storefront-aanvragen

Als een actieve regel een `query is` voorwaarde komt overeen met de zoekfrase. Deze wordt toegepast. Als er meerdere overeenkomende regels zijn met een `query is` voorwaarde, wordt de onlangs bijgewerkte actieve regel toegepast.
Anders wordt de laatst bijgewerkte actieve regel toegepast.

### Voorvertoningsverzoeken

Aanvraag in de beheerder werkt iets anders. Wanneer u een voorvertoning weergeeft in de beheertoepassing, worden alle regels toegepast, inclusief de regels die zijn verlopen en gepland.

* Als de regel die wordt voorvertoond een `query is` voorwaarde wordt toegepast.
* Als de regel die wordt voorvertoond geen `query is` voorwaarde, en een volgende actieve, passende regel met een `query is` voorwaarde wordt gevonden, de `query is` wordt toegepast.
* Als de regel die wordt voorvertoond geen `query is` voorwaarde, en geen andere regel met een `query is` wordt gevonden, wordt de regel toegepast die wordt voorvertoond.

## Rubriekhandel en producttoewijzingen van categorieën

[!DNL Live Search] kunt u filteren op Categorieën. Zie [Categorieverhandeling](category-merch.md) voor meer informatie .
In Adobe Commerce kunt u echter een virtuele categorie maken met [Toewijzingen van producten in categorie](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/products-in-category/categories-product-assignments.html). Dit type categorie is gemaakt bij uitvoering en komt niet voor in de categoriedatabase. Daarom [!DNL Live Search] kan dit rubriektype niet lezen of gebruiken.
