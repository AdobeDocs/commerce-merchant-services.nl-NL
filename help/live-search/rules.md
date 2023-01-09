---
title: "Regels"
description: "[!DNL Live Search] de regels combineren logica met acties om de het winkelen ervaring te vormen."
exl-id: d06a3040-6987-4813-90ae-2f7b3ad0b232
source-git-commit: 941fdc25f93679593cb3c5db0d29d7a561fcce58
workflow-type: tm+mt
source-wordcount: '296'
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
