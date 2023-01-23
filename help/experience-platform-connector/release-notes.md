---
title: Opmerkingen bij de release
description: De nieuwste release-informatie voor Adobe Experience Platform-connector vanuit Adobe Commerce.
exl-id: 7636664b-488a-46f7-8d19-a9faac126aec
source-git-commit: 975854dbdae32e5e51bb57593cf122627d01571f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 1%

---

# Opmerkingen bij de release

Deze releaseopmerkingen bevatten updates van de aansluiting van het Experience Platform en bevatten:

* ![Nieuw](../assets/new.svg) - Nieuwe functies
* ![Repareren](../assets/fix.svg) - Oplossingen en verbeteringen
* ![Bug](../assets/bug.svg) - Bekende problemen

Voor functieveranderingen en moeilijke situaties met betrekking tot uitbreidingen die door de schakelaar van het Experience Platform worden gebruikt, zie **Ondersteunde service-updates**.

Zie [Volgende releases](https://experienceleague.adobe.com/docs/commerce-operations/release/schedule.html) om over versieschema&#39;s en steun te leren.

Zie [Beschikbaarheid](https://experienceleague.adobe.com/docs/commerce-operations/release/availability.html) voor meer informatie over productcompatibiliteit.

## Ondersteunde service-updates

Deze versienota&#39;s beschrijven eigenschapveranderingen en moeilijke situaties met betrekking tot uitbreidingen die door de schakelaar van het Experience Platform worden gebruikt.

+++Ondersteunde service-updates

_12 oktober 2022_

* ![Nieuw](../assets/new.svg) - Twee toegevoegd [storefront, gebeurtenissen](events.md): `openCart` en `removeFromCart` naar de Adobe Commerce Storefront Events SDK en Collector
* ![Nieuw](../assets/new.svg) - Toegevoegde ondersteuning voor een [AEM storefront](overview.md#aem-support)

+++

## 2.1.0

_17 januari 2023_

* ![Nieuw](../assets/new.svg) - De [Admin-aansluiting Experience Platform](connect-data.md) zodat kunt u uw eigen AEP Web SDK (legering) specificeren. Voeg ook een optie toe voor handelaren die zijn ingeschreven voor ons bètaprogramma voor back office-kantoren om te verzenden [back office-gebeurtenisgegevens](connect-data.md#data-collection) aan de rand. Deze gebeurtenissen bevatten [statusgegevens van order](events.md#beta-order-status-events) over een bestelling, bijvoorbeeld of een bestelling is geplaatst, geannuleerd, terugbetaald of verzonden. Als u wilt deelnemen aan het bètaprogramma voor het back office kantoor, neemt u contact op met [drios@adobe.com](mailto:drios@adobe.com).
* ![Repareren](../assets/fix.svg) Gewijzigd in gebruik `identityMap` in plaats van `personID` wanneer u de primaire identiteit instelt voor gegevens die naar de rand worden geduwd.

## 2.0.1

_10 november 2022_

* ![Probleem opgelost](../assets/fix.svg) - Nu wordt de Adobe Experience Platform-context alleen ingesteld nadat de Storageront Event Collector en de Storefront Event SDK zijn geladen.

## 2.0.0

_12 oktober 2022_

* ![Nieuw](../assets/new.svg) - Toegevoegde mogelijkheid om uw eigen AEP Web SDK op te geven wanneer [verbinden](connect-data.md) Adobe Commerce-exemplaar naar het Experience Platform
* ![Repareren](../assets/fix.svg) - Vereisten voor het bijwerken van het bereik van de gegevensstroom, zodat de gegevensstroom-id&#39;s binnen het bereik van de website moeten worden geplaatst in plaats van dat ze moeten worden opgeslagen

## 1.0.0

_9 augustus 2022_

* ![Nieuw](../assets/new.svg) - Algemene beschikbaarheidsrelease

## Documentatie

Meer informatie:

* [Adobe Commerce Developer Documentation](https://devdocs.magento.com/)
* [Adobe Commerce-gebruikershandleiding](https://docs.magento.com/user-guide/)
