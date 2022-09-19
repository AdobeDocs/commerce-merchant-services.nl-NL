---
title: "Regelcomponenten"
description: "Meer informatie over [!DNL Live Search] regelcomponenten en operatoren."
exl-id: 4065aec3-a8d4-4d55-b939-16ad7b0f33ee
source-git-commit: 0a1d70465247422db44daee302c67fe1a5a29d32
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Regelcomponenten

Een regel beschrijft de voorwaarden die worden vereist om gebeurtenissen teweeg te brengen die de onderzoeksresultaten veranderen die in antwoord op de vraag van een verkoopster zijn teruggekeerd.

## Vereisten

Een eenvoudige regel kan één enkele voorwaarde en één enkele gebeurtenis hebben, terwijl een complexe regel tot tien voorwaarden kan hebben die tot 25 gebeurtenissen teweegbrengen.
Regels kunnen:

* Tot tien voorwaarden
* Tot 25 gebeurtenissen

Zoektekst kan het volgende bevatten:

* Alfanumerieke tekens (letters en cijfers)
* Hoofdletters of kleine letters

## Logische operatoren

Logische operatoren `AND` en `OR` twee voorwaarden samenvoegen en verschillende resultaten retourneren. Alle logische operatoren die in een regel met meerdere voorwaarden worden gebruikt, zijn hetzelfde. Het is niet mogelijk beide `AND` en `OR` in dezelfde regel.

### Operatoren afstemmen

De operatoren Afstemmen `All` en `Any` Bepaal de logische exploitant die wordt gebruikt om veelvoudige voorwaarden in de regel samen te voegen, en kan worden gebruikt om de bestaande exploitant te veranderen.

* `All` - Gebruikt de `AND` logische operator om meerdere voorwaarden samen te voegen. Een regel die de `All` Identieke operator kan slechts één hebben `Search query is` voorwaarde.
* `Any` - Gebruikt de `OR` logische operator om meerdere voorwaarden samen te voegen.

Wanneer het samenstellen van een complexe regel, kan het helpen om het met inspringing uit te schrijven om de voorwaarden, bijbehorende gebeurtenissen, en productnamen of SKUs te beschrijven die nodig zijn om de resultaten terug te keren u wilt bereiken. Vervolgens bouwt u de regel en test u het resultaat.
