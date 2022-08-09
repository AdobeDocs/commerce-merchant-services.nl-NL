---
title: Connect Commerce-gegevens naar Adobe Experience Platform
description: Leer hoe u de gegevens van de Handel met de Adobe Experience Platform verbindt.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
source-git-commit: 2b735c292920bb0e9052d86bf152748e7ce96079
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Connect Commerce-gegevens naar Adobe Experience Platform {#connectaep}

Voordat u uw Adobe Commerce-gegevens verbindt met de Adobe Experience Platform, moet u zich aanmelden bij uw Adobe-account in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid). Nadat u zich hebt aangemeld en uw organisatie-id hebt geselecteerd, kunt u vervolgens het bereik en de gegevensstroom-id opgeven in het dialoogvenster **Experience Platform Connector** in Admin.

1. Ga in Beheer naar **Systeem** > Services > **Experience Platform Connector**.

1. In de **Toepassingsgebied** vervolgkeuzelijst, selecteert u de context of het &quot;bereik&quot; van de winkelweergave.

   De organisatie-id is algemeen. Per Adobe Commerce-exemplaar kan slechts één organisatie-id worden gekoppeld.

1. In de **IMS-organisatie** in het veld wordt de id weergegeven die is gekoppeld aan uw Adobe Experience Platform-account, zoals deze is geconfigureerd in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid).

1. In de **DataStream-id** veld, plak de id van de gegevensstroom die u [gemaakt](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html) in Adobe Experience Platform.

## Relatie tussen DataStream-id en uw Commerce Instance StorageView

Met de DataStream-id wordt het doorsturen van gebeurtenissen van Adobe Experience Platform naar andere Adobe DX-producten mogelijk en kan deze worden gekoppeld aan een specifieke opslagweergave binnen uw specifieke Adobe Commerce-instantie. U kunt veelvoudige storeviews aan zelfde identiteitskaart DataStream ook associëren. Het hangt van af wat het meest voor uw zaken zinvol is.

## Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Toepassingsgebied | Specifieke opslag waar u de configuratiemontages wilt toepassen. |
| IMS Org (Global) | Id die behoort tot de organisatie die het Adobe DX-product heeft aangeschaft. Deze id koppelt uw Adobe Commerce-exemplaar aan Adobe Experience Platform. |
| DataStream-id (Storeview) | ID die gegevens om van Adobe Experience Platform aan andere Adobe DX producten toestaat te stromen. Deze id kan worden gekoppeld aan een specifieke storeView binnen uw specifieke Adobe Commerce-exemplaar. |

Als de extensie voor de aansluiting van het Experience Platform is geïnstalleerd, wordt de koppeling tussen Adobe Commerce en Adobe Experience Platform gemaakt en wordt de DataStream-id opgegeven. De gegevens van de handel gaan dan naar de Adobe Experience Platform-rand en naar andere Adobe DX-producten.

## Commerciële gegevens aan de rand

Wanneer de gegevens van de Handel naar de rand van Adobe Experience Platform worden verzonden, kunt u rapporten als het volgende bouwen:

![Commerciële gegevens in Adobe Experience Manager](assets/aem-data-1.png)
_Commerciële gegevens in Adobe Experience Manager_
