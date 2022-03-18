---
title: Aan boord [!DNL Payment Services]
description: Sluit uw exemplaar aan met [!DNL Payment Services] door een paar instapstappen te voltooien.
role: User
level: Intermediate
exl-id: 1ee8c660-0941-4378-a1d7-ae45de3de211
source-git-commit: bcb817775fe9cd9ac7096931dd40d5ec0c4a5cfc
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Aan boord [!DNL Payment Services]

Aan de slag met [!DNL Payment Services] voor Adobe Commerce en Magento Open Source moet u enkele instapkaartstappen uitvoeren om uw exemplaar te verbinden met de betalingsfunctionaliteit.

## Stroom aan boord

![Stroom aan boord](assets/onboarding-diagram.svg)

In dit stroomdiagram wordt het algemene proces voor instapweigering getoond [!DNL Payment Services].

Nadat u het instappen voor zandbak of levende betalingen voltooit, is de financiële rapportering toegankelijk van [!DNL Payment Services] in de Admin.

Als zowel sandbox- als live-betalingen zijn ingeschakeld, kunt u gemakkelijk schakelen tussen deze modi vanuit de [!DNL Payment Services] thuis.

## Vereisten

Voor gebruik [!DNL Payment Services], moet het volgende beschikbaar zijn voor uw instantie:

* Module Services Connector
* Services ID-module
* API-sleutels

De modules van de Schakelaar van de Diensten en van identiteitskaart van de Diensten worden automatisch geïnstalleerd tijdens [installatie van [!DNL Payment Services]](install.md). Wanneer de installatie volledig is, kunt u een nieuwe sectie in de configuratiemontages zien (**[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**) wanneer u uitvouwt **[!UICONTROL Services]**—**[!UICONTROL Commerce Services Connector]**.

Ga voor meer informatie over het maken van of toegang krijgen tot uw API-sleutels naar [API-referenties](#obtain-api-credentials).

## Stappen aan boord

1. [Installeer de [!DNL Payment Services] extension](install.md#get-payment-services).
1. [API-referenties verkrijgen](connect.md#obtain-api-credentials).
1. [Sluit uw exemplaar aan](connect.md#configure-commerce-services) aan Commerce Services. Deze verbinding moet slechts eenmaal per instantie van de Handel worden voltooid.
1. [De sandboxservice instellen](sandbox.md#enable-sandbox-testing) (dan wel [rechtstreekse betalingen mogelijk maken](sandbox.md#enable-live-payments) als u functionaliteit in een andere omgeving hebt getest) met een PayPal-rekening voor betalingsverwerking.
1. [Set [!DNL Payment Services] als betalingsmethode](production.md#set-payment-services-as-payment-method)in de sandboxmodus, om testbetalingen te verwerken.
1. [Betalingsrechten aanvragen](production.md#request-payments-entitlement-from-adobe) om live aan boord te gaan.
1. [Volledige merchant aan boord](production.md#complete-merchant-onboarding) om rechtstreekse betalingen voor je commerciële websites mogelijk te maken.
1. [Uw [!DNL Payment Services] Merchant ID](production.md#configure-pricing-tier) en geef het aan Verkoop om de correcte tarifering te vormen.
1. [Inschakelen [!DNL Payment Services] in actieve modus](production.md#enable-live-payments) beginnen met de verwerking van rechtstreekse betalingen.
1. Betalingen testen, in beide gevallen [sandbox](sandbox.md#test-in-sandbox-environment) en [productie](production.md#test-in-production) omgevingen.

>[!NOTE]
>
>Als u uw Diensten van de Handel in Admin (stap 3) niet vormt, kunt u opstelling zandbak of levende betalingen niet.

## Problemen oplossen

* [Problemen oplossen [!DNL Payment Services] installatie](https://support.magento.com/hc/en-us/articles/4406603542541)
* [PayPal-sandboxaccount niet geverifieerd](https://support.magento.com/hc/en-us/articles/4406954952461)
* [Vertraagd [!DNL Payment Services] rapportgegevens](https://support.magento.com/hc/en-us/articles/4406114741517)
