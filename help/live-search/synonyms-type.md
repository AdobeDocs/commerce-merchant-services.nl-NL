---
title: "Typen synoniemen"
description: "Eenweg en tweeweg [!DNL Live Search] synoniemen breiden de definitie van trefwoorden uit."
exl-id: 708d7b0d-7361-44f4-ae9e-b92f574ac975
source-git-commit: 9bacdb5fd232a3603bcb7abe2e93da9ead794d38
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---

# Typen synoniemen

Met synoniemen in één en twee richtingen wordt de definitie van trefwoorden uitgebreid. Sommige zijn onderling verwisselbaar met het trefwoord, terwijl andere een subset van het trefwoord vertegenwoordigen.

## 2-wegs

Synoniemen in twee richtingen hebben dezelfde betekenis en retourneren dezelfde zoekresultaten. In het volgende voorbeeld is het eerste woord dat vet wordt weergegeven, het trefwoord dat wordt gebruikt in de catalogus, gevolgd door woorden met dezelfde betekenis als het oorspronkelijke trefwoord. U kunt een eenvoudig paar synoniemen in twee richtingen, of een ketting van veelvoudige synoniemen in twee richtingen voor het zelfde sleutelwoord tot stand brengen.

**jasje** ![Selector met twee richtingen](assets/btn-two-way.png) jas
**broek** ![Selector met twee richtingen](assets/btn-two-way.png) slangen ![Selector met twee richtingen](assets/btn-two-way.png) broek

## Eenweg

Een eenrichtingssynoniem is een subset van een trefwoord, maar heeft een specifiekere betekenis. Capris en shorts zijn bijvoorbeeld broeken, maar niet alle planten zijn capris of korts. Een zoekopdracht naar broek omvat capris en korte broeken. Een zoekopdracht naar korte berichten retourneert echter geen capris.

**zweet** ![Eenvoudige kiezer](assets/btn-one-way.png) hooi
**broek** ![Eenvoudige kiezer](assets/btn-one-way.png) capris ![Meerdere eenrichtingskiezers](assets/btn-multiple-one-way.png) kalfsnuitje ![Meerdere eenrichtingskiezers](assets/btn-multiple-one-way.png) pedaalduwbakken

## Aanbevolen procedures

Houd rekening met de volgende aanbevolen procedures om optimaal te profiteren van [!DNL Live Search] synoniemen.

### &quot;Stop woorden&quot; vermijden

[!DNL Live Search] Hiermee worden algemene &#39;stopwoorden&#39; in het Engels gefilterd op synoniemen, zoals:

a, an, and, are, as, at, be, but, by, for, if, in, is, it, no, not, of, dusdanig, dat, hun, toen, daar, deze, zij, dit, aan, was,

Stopwoorden maken synoniemen niet zinvoller, maar verhogen de hoeveelheid gegevens die moet worden verwerkt.

### Enkele woorden gebruiken

Als een synoniem term meerdere woorden bevat, worden deze door de witruimte tussen de woorden als een aparte synoniemen behandeld. Als u bijvoorbeeld &quot;tijdstuk&quot; definieert als een synoniem voor &quot;watch&quot;, worden de woorden &quot;time&quot; en &quot;piece&quot; behandeld als afzonderlijke synoniemen.

### Gebruik van enkelvoudig en meervoudig

Het is niet nodig om zowel de enkelvoudige als de meervoudige vorm van een woord als een synoniem te definiëren. Als u een combinatie van enkelvoudige en meervoudige termen in uw catalogus hebt, zoekt u naar de juiste set producten. Als u bijvoorbeeld het woord &quot;pant&quot; in de productnaam gebruikt en een winkel zoekt naar &quot;broek&quot;, wordt de juiste set producten geretourneerd en wordt het woord &quot;pant&quot; voorgesteld als suggestie. In de mode-industrie en soms in de detailhandel wordt de term &quot;pant&quot; vaak gebruikt, hoewel de meervorm &quot;broek&quot; in sommige gebieden vaker wordt gebruikt. (Het woord &quot;pant&quot; verwijst technisch naar het deel van een kledingstuk dat één been bedekt. Daarom hebt u een &quot;broek&quot; nodig om beide benen te bedekken.)

### Consistentie

Zorg ervoor dat de terminologie in de catalogus wordt gebruikt. Houd er rekening mee dat er regionale verschillen in gebruik kunnen zijn, en soms verschillen binnen een bedrijfstak.

### Trefwoordtoewijzing

Deze techniek gebruikt doorzoekbare productkenmerken in plaats van synoniemen om op trefwoorden gebaseerde koppelingen tussen producten te maken. Als gevolg hiervan kan een toegewezen product in de zoekresultaten van een ander product worden weergegeven. Zie voor meer informatie [Zoekresultaten](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-results.html).
