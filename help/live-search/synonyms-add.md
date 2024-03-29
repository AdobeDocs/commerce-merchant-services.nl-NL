---
title: "Synoniemen toevoegen"
description: "Toevoegen [!DNL Live Search] synoniemen om de reactie op zoekverzoeken te verbeteren."
exl-id: 6c277d88-cb22-4174-abda-6d6bb65fe3be
source-git-commit: 63318e2eb75bc5fb0a243b6430751b076e541b72
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Synoniemen toevoegen

Verhoog de betrokkenheid van klanten door uw eigen gekrulde lijst met [!DNL Live Search] synoniemen. [!DNL Live Search] kan maximaal 200 synoniemen per `Data Space ID`.

![[!DNL Live Search] synoniemen](assets/synonym-workspace.png)

## Stap 1: Een synoniem toevoegen

1. Ga in Beheer naar **Marketing** > SEO &amp; Search > **[!DNL Live Search]**.
1. Voor meerdere winkels stelt u **Toepassingsgebied** aan de [winkelweergave](https://experienceleague.adobe.com/docs/commerce-admin/start/setup/websites-stores-views.html#scope-settings) waar de synoniem-instellingen van toepassing zijn.
1. Klik op de knop **Synoniemen** tab.
1. Klik op de knop **Synoniemen toevoegen** knop.

## Stap 2: De synoniem door type bepalen

Volg de instructies voor de [type synoniem](synonyms-type.md) die u wilt maken.

### Synoniem in twee richtingen

1. De standaardinstelling accepteren **2-wegs** -optie.

   ![Synoniem in twee richtingen toevoegen](assets/synonym-add-two-way.png)


1. Voer de **Trefwoord** term of uitdrukking die moet worden aangepast.
1. Voer de **Uitbreiding** term(en) die u als synoniemen voor het trefwoord wilt toevoegen. Scheid meerdere termen met een komma.
In dit voorbeeld is het trefwoord dat moet overeenkomen &#39;broek&#39; en zijn de uitbreidingstermijnen &#39;brousers, slacks&#39;.

   ![Voorbeeld van synoniem in twee richtingen](assets/synonym-add-two-way-example.png)

1. Klik op **Opslaan**.
De reeks synoniemen verschijnt in de lijst met een tweerichtingspijl tussen elke termijn die betekent de termijnen onderling verwisselbaar zijn.

   ![Synoniem in twee richtingen](assets/synonym-two-way.png)

### Eenvoudige synoniem

1. Klik op de knop **Eenweg** synoniem type.

   ![Eenvoudige synoniem toevoegen](assets/synonym-add-one-way.png)

1. Voer de **Trefwoord** en **Uitbreiding** voorwaarden. Scheid meerdere termen met een komma.

   ![Voorbeeld van eenrichtingssynoniem](assets/synonym-add-one-way-example.png)

   In dit voorbeeld is het trefwoord &#39;broek&#39; en zijn de eenmalige uitbreidingstermen &#39;capris, peddle-push&#39; elk een subset van &#39;broek&#39;, maar met een specifieke betekenis.

1. Klik op **Opslaan**.
De reeks synoniemen verschijnt in de lijst met een eenrichtingspijl die van de uitbreidingstermijnen aan het sleutelwoord richt om erop te wijzen de termijnen subsets van het sleutelwoord zijn. Een plusteken scheidt elke uitbreidingstermijn.

   ![Eenvoudige synoniem](assets/synonym-one-way.png)

## Stap 3: Wijzigingen publiceren

1. Wanneer uw synoniemen volledig zijn, klik **Wijzigingen publiceren**.
1. Wacht maximaal twee uur totdat uw updates beschikbaar zijn in de winkel.

## Veldbeschrijvingen

| Veld | Beschrijving |
|--- |--- |
| [Type](synonyms.md) | Hiermee wordt bepaald of synoniemen dezelfde betekenis hebben als het trefwoord of een subset van het trefwoord zijn. Opties:<br />Tweerichtings (gebrek) - Termen die de zelfde betekenis zoals het sleutelwoord hebben en de zelfde onderzoeksresultaten terugkeren<br />Eenzijdig - Termen die een subset van het trefwoord zijn. Eenwegssynoniemen retourneren een uitgebreidere lijst met specifieke producten. |
| Trefwoord | Een woord dat vaak wordt gekoppeld aan een selectie producten in uw catalogus. |
| Uitbreiding | Aanvullende termen met dezelfde of een vergelijkbare betekenis als het trefwoord. |
