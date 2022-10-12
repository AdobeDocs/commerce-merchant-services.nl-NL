---
title: Connect Commerce-gegevens naar Adobe Experience Platform
description: Leer hoe u de gegevens van de Handel met de Adobe Experience Platform verbindt.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
source-git-commit: 1af2dee51391c94e19b68481d390cc2629fe1d6e
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Connect Commerce-gegevens naar Adobe Experience Platform {#connectaep}

Als u uw Adobe Commerce-instantie wilt verbinden met de Adobe Experience Platform, moet u een organisatie-id en een gegevensstroom-id opgeven.

![Configuratie van Experience Platform-aansluiting](assets/epc-config.png)

1. Meld u aan bij uw Adobe-account in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid) en selecteer uw organisatie-id.

1. Ga in Beheer naar **Systeem** > Services > **Experience Platform Connector**.

1. In de **Toepassingsgebied** vervolgkeuzelijst, de context instellen op **Website**.

1. In de **Organisatie-id** in het veld wordt de id weergegeven die is gekoppeld aan uw Adobe Experience Platform-account, zoals deze is geconfigureerd in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid). De organisatie-id is algemeen. Per Adobe Commerce-exemplaar kan slechts één organisatie-id worden gekoppeld.

1. In de **DataStream-id** veld, plak de id van de gegevensstroom die u [gemaakt](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html#create) in de Adobe Experience Platform.

   >[!NOTE]
   >
   >Het bereik van de gegevensstroom-id moet op websiteniveau of hoger worden ingesteld. Op dat niveau wordt dezelfde gegevensstroom-id gebruikt voor elke website in de hiërarchie. U kunt het bereik van de gegevensstroom-id niet instellen op opslagniveau.

1. (Optioneel) Als u geen AEP Web SDK aan uw site hebt toegewezen, laat u dit veld leeg en implementeert de aansluiting van het Experience Platform er een voor u. Anders, voeg de naam van uw AEP Web SDK toe.

## Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Toepassingsgebied | Specifieke website waarop u de configuratie-instellingen wilt toepassen. |
| Organisatie-id (wereldwijd) | Id die behoort tot de organisatie die het Adobe DX-product heeft aangeschaft. Deze id koppelt uw Adobe Commerce-exemplaar aan Adobe Experience Platform. |
| DataStream-id (website) | ID die gegevens om van Adobe Experience Platform aan andere Adobe DX producten toestaat te stromen. Deze id moet zijn gekoppeld aan een specifieke website in uw specifieke Adobe Commerce-exemplaar. |
| AEP Web SDK Name (Global) | Als u geen AEP Web SDK hebt die aan uw plaats wordt opgesteld, verlaat dit gebied leeg en de schakelaar van het Experience Platform stelt voor u op. Als u al een AEP Web SDK hebt die aan uw plaats wordt opgesteld, specificeer de naam van die SDK op dit gebied. Dit staat de Collector van de Gebeurtenis Storefront en de Gebeurtenis SDK toe om uw AEP Web SDK eerder dan de versie te gebruiken die door de schakelaar van het Experience Platform wordt opgesteld. |

Als de extensie voor de aansluiting van het Experience Platform is geïnstalleerd, wordt de koppeling tussen Adobe Commerce en Adobe Experience Platform gemaakt en wordt de DataStream-id opgegeven. De gegevens van de handel gaan dan naar de Adobe Experience Platform-rand en naar andere Adobe DX-producten.

>[!NOTE]
>
> De hoeveelheid tijd die nodig is om gegevens van de rand naar andere Adobe DX-producten te laten stromen, kan variëren.

## Commerciële gegevens aan de rand

Wanneer de gegevens van de Handel naar de rand van Adobe Experience Platform worden verzonden, kunt u rapporten als het volgende bouwen:

![Commerciële gegevens in Adobe Experience Manager](assets/aem-data-1.png)
_Commerciële gegevens in Adobe Experience Manager_
