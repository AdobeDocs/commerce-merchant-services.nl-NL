---
title: Soorten handelsgegevens
description: Leer de typen gegevens die u kunt verzamelen en naar het Experience Platform verzenden.
role: Admin, Developer
feature: Personalization, Integration
source-git-commit: d5824e11b4961b518e35fcf56ff2c7ee00480617
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# Soorten handelsgegevens

De [Gegevensverbinding, extensie](overview.md) Verbindt uw gegevens van de Handel met het Experience Platform. Gegevens die bestemd zijn voor gebruik in het Experience Platform, worden gegroepeerd in twee gedragstypen: gegevens uit de tijdreeks, die tot de **Experience Event** klasse, en recordgegevens, die tot **Individueel profiel** klasse.

Meer informatie over [gegevensgedrag](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#data-behaviors) en [klassen](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#class) in Experience Platform.

## Gegevens uit tijdreeksen

De gegevens van de tijdreeksen verstrekken een momentopname van het systeem op het tijdstip dat een actie of direct of indirect door een verslagonderwerp werd genomen. Als een winkelier bijvoorbeeld door een product op uw site bladert, voegt u een product toe aan de winkelwagentje, plaatst u een bestelling enzovoort. Gegevens uit tijdreeksen worden in het Experience Platform opgenomen met een schema waarvoor de klasse is ingesteld op **Experience Event**.

### Vastgelegde tijdreeksgegevens

Zie [gedragsgebeurtenissen](events.md) en [back office-gebeurtenissen](events-backoffice.md) om te leren welke gegevens worden vastgelegd wanneer een tijdreeksgebeurtenis wordt gegenereerd.

### Schema nodig om gebeurtenisgegevens voor tijdreeksen in te voeren

Leer hoe u [een schema maken](update-xdm.md) die gedrags- en back-office tijdreeksgebeurtenisgegevens kunnen invoeren.

## Gegevens opnemen

>[!NOTE]
>
>Deze functie is in bèta. Als u wilt deelnemen aan het bètaprogramma, verzendt u een aanvraag naar [dataconnection@adobe.com](mailto:dataconnection@adobe.com).

De gegevens van het verslag verstrekken informatie over de attributen van een onderwerp. Een onderwerp kan een organisatie of een individu zijn. Een winkelier op uw site maakt bijvoorbeeld een account en genereert recordgegevens. Dit gegeven wordt opgenomen in het Experience Platform gebruikend een schema dat de klasse heeft die aan wordt geplaatst **Individueel profiel**. U kunt die recordgegevens naar de profielbeheer en segmentatieservice van de Adobe verzenden: [Real-Time CDP](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/rtcdp-intro/overview.html).

### Vastgelegde profielrecordgegevens

Zie [klantprofielrecordgegevens](events-profilerecord.md) om te zien welke gegevens worden vastgelegd wanneer een profielrecord wordt gegenereerd.

### Schema nodig voor het invoeren van profielrecordgegevens

Leer hoe u [een schema maken](profile-data.md) die recordgegevens voor profielen kunnen invoeren.
