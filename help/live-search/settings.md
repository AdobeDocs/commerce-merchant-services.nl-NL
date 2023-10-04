---
title: "[!DNL Live Search] Instellingen"
description: "Configureer instellingen voor de [!DNL Live Search] service."
exl-id: a0b63116-4b8f-490c-a54e-e21f1b02b634
source-git-commit: 06dfc8fd5dc3619732a1f534e5770b6812eddc07
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Instellingen

Gebruik de *Instellingen* om de prijsfacetwaaiers en intervallen en de standaardtaal voor de index te vormen.

Prijsfacetten geven het aantal prijsgroepen aan en de verdeling van de prijswaarden tussen deze groepen.

Taalinstellingen vertellen de [!DNL Live Search] de dienst die taal om te verwachten wanneer het schrijven van de index.

![Instellingen](assets/settings.png)

## Prijsbeperking

U kunt het aantal groepen voor het prijsbereik opgeven en aangeven hoe de prijswaarden eronder worden verdeeld. Elke prijsklasse overlapt de vorige groep met één. Vijf groepen met een interval van 20 maken bijvoorbeeld de volgende prijsbereiken: 0-20, 20-40, 40-60, 60-80 en >80. Als de catalogus niet genoeg producten bevat om alle gedefinieerde bereiken te vullen, wordt de weergave van de beschikbare groepen dienovereenkomstig aangepast. Bijvoorbeeld: 0-20, 60-80, >80.

1. Ga in Beheer naar **Marketing** > *SEO &amp; Search* > **[!DNL Live Search]**.
1. Op de **Instellingen** tab onder *Prijsbeperking* Ga als volgt te werk:
   * Voer de **Aantal selecties**, of prijsgroepen die beschikbaar moeten zijn. Er kunnen maximaal 50 prijsgroepen worden gedefinieerd.
   * Voer de **Interval, waarde**, of prijsbereik voor elke groep. De maximumwaarde is 10.000.
1. Klikken **Opslaan**.

   Het duurt ongeveer 15 minuten voordat de bijgewerkte instellingen beschikbaar zijn in de winkel.

### Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Aantal selecties | Hiermee geeft u het aantal groepen voor prijsbereik op dat als zoekfilters in de winkel kan worden gebruikt. Standaardwaarde: 8, Maximumwaarde: 50 |
| Interval, waarde | Hiermee geeft u het prijsinterval voor elke groep op. Vijf selecties met een intervalwaarde van 20 maken bijvoorbeeld vijf groepen van 0-20, 20-40, 40-60, 60-80 en >80. Standaardwaarde: 5, Maximumwaarde: 10.000 |
