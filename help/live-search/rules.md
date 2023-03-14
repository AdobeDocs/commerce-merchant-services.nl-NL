---
title: "Regels"
description: "[!DNL Live Search] de regels combineren logica met acties om de het winkelen ervaring te vormen."
exl-id: d06a3040-6987-4813-90ae-2f7b3ad0b232
source-git-commit: c4bca0c7238be653dd13b051634c662e5891767d
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---

# Regels

[!DNL Live Search] de regels combineren logica met acties om de onderzoekservaring van een verkoopster in uw opslag te vormen. U kunt regels gebruiken om producten op te voeren, te begraven, te spelden, of te verbergen om onderzoeksresultaten in echt te kalibreren - tijd om uw bedrijfsdoelstellingen te steunen.

Elke regel heeft drie hoofdcomponenten:

* Voorwaarden - De voorwaarden die een handeling activeren.
* Gebeurtenissen - De acties die plaatsvinden wanneer aan de voorwaarden wordt voldaan.
* Details - De naam van de regel, en facultatief tijdkader en beschrijving.

U kunt veelvoudige voorwaarden en acties combineren, en een regel plannen om voor een periode actief te zijn.

## Vereisten

Een eenvoudige regel kan één enkele voorwaarde en één enkele gebeurtenis hebben, terwijl een complexe regel tot tien voorwaarden kan hebben die tot 25 gebeurtenissen teweegbrengen.
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

## Volgorde van prioriteit met meerdere regels

Er wordt slechts één regel tegelijk toegepast op een zoekterm.
Als meerdere regels van toepassing blijken te zijn op een zoekfrase, worden al deze regels toegepast. Als er een botsing is tussen twee regels—`rule 1` dat sku1 versterkt , maar `rule 2` verbergt zelfde SKU-toen de onlangs toegepaste regel (`rule 2`) heeft voorrang.

* Regels worden geordend met de tijdstempel &#39;Laatst gewijzigd&#39;. De regel die het laatst is gewijzigd, wordt eerst toegepast en daarna oudere regels in tijdstempelvolgorde.
* De `query is` voorwaarde heeft voorrang op andere voorwaarden. Als een nieuwere regel een `query contains` voorwaarde, maar een oudere regel heeft een `query is` voorwaarde, de `query is` wordt toegepast.

### Storefront-aanvragen

Als een actieve regel een `query is` voorwaarde komt overeen met de zoekfrase en wordt toegepast. Als er meerdere overeenkomende regels zijn met een `query is` voorwaarde, wordt de onlangs bijgewerkte actieve regel toegepast.
Anders wordt de laatst bijgewerkte actieve regel toegepast.

### Voorvertoningsverzoeken

Aanvraag in de beheerder werkt iets anders. Wanneer u een voorvertoning weergeeft in Admin, worden alle regels toegepast, inclusief de regels die zijn verlopen en gepland.

* Als de regel die wordt voorvertoond een `query is` voorwaarde, wordt deze toegepast.
* Als de regel die wordt voorvertoond geen `query is` voorwaarde, en een volgende actieve, passende regel met een `query is` voorwaarde wordt gevonden, de `query is` wordt toegepast.
* Als de regel die wordt voorvertoond geen `query is` voorwaarde, en geen andere regel met een `query is` wordt gevonden, wordt de regel toegepast die wordt voorvertoond.

## Categorievoorschriften en producttoewijzingen voor categorieën

[!DNL Live Search] kunt u filteren op Categorieën.
In Adobe Commerce kunt u echter een virtuele categorie maken met [Toewijzingen van producten in categorie](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/products-in-category/categories-product-assignments.html). Dit type categorie is gemaakt bij uitvoering en komt niet voor in de categoriedatabase. L[!DNL Live Search] kan dit rubriektype niet lezen of gebruiken.
