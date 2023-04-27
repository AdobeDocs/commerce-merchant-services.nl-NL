---
title: Connect Commerce-gegevens naar Adobe Experience Platform
description: Leer hoe u de gegevens van de Handel met de Adobe Experience Platform verbindt.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
source-git-commit: dead0b8dae69476c196652abd43c4966a38c4141
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 0%

---

# Connect Commerce-gegevens naar Adobe Experience Platform

Wanneer u de aansluiting voor het Experience Platform installeert, worden twee nieuwe configuratiepagina&#39;s weergegeven in de **Systeem** menu onder **Services** in de handel _Beheer_.

- Commerce Services Connector
- Experience Platform Connector

Als u uw Adobe Commerce-instantie wilt verbinden met het Adobe Experience-platform, moet u beide connectors configureren, te beginnen met de Commerce Services-connector en vervolgens voltooien met de Experience Platform-connector.

## De schakelaar van de Diensten van de Handel bijwerken

Als u eerder een dienst van Adobe Commerce hebt geïnstalleerd, hebt u waarschijnlijk reeds de schakelaar van de Diensten van de Handel gevormd. Indien niet, dan moet u de volgende taken op [Commerce Services-connector](../landing/saas.md) pagina:

1. Meld u aan bij uw account voor Handel om [productie- en sandbox-API-sleutels ophalen](../landing/saas.md#credentials).
1. Selecteer een [SaaS-gegevensruimte](../landing/saas.md#saas-configuration).
1. Meld u aan bij uw Adobe-account naar [uw organisatie-id ophalen](../landing/saas.md#ims-organization-optional).

Nadat u de schakelaar van de Diensten van de Handel vormt, vormt u dan de schakelaar van het Experience Platform.

## De aansluiting van het Experience Platform bijwerken

In deze sectie verbindt u uw Adobe Commerce-exemplaar met de Adobe Experience Platform met behulp van uw organisatie-id. Vervolgens kunt u het type gegevens opgeven (winkel of achterkantoor) dat u naar de rand van het Experience Platform wilt verzenden.

![Configuratie van Experience Platform-aansluiting](assets/epc-config-dc.png)

## Algemeen

1. Meld u aan bij uw Adobe-account in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid) en selecteer uw organisatie-id.

   >[!NOTE]
   >
   >Als u eerder de schakelaar van de Diensten van de Handel vormde, kunt u deze stap overslaan aangezien uw organisatieidentiteitskaart reeds is geselecteerd.

1. Ga in Beheer naar **Systeem** > Services > **Experience Platform Connector**.

1. In de **Toepassingsgebied** vervolgkeuzelijst, de context instellen op **Website**.

1. In de **Organisatie-id** , controleert u de id die aan uw Adobe Experience Platform-account is gekoppeld, zoals deze in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid). De organisatie-id is algemeen. Per Adobe Commerce-exemplaar kan slechts één organisatie-id worden gekoppeld.

1. (Optioneel) Als u al een [AEP Web SDK (legering)](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) opgesteld aan uw plaats, laat checkbox toe en voeg de naam van uw Web SDK van AEP toe. Anders, verlaat deze gebieden leeg en de schakelaar van het Experience Platform stelt voor u op.

   >[!NOTE]
   >
   >Als u uw eigen SDK van het Web van AEP specificeert, gebruikt de schakelaargebruik van het Experience Platform identiteitskaart verbonden aan die SDK en niet gegevensstroom ID die op deze pagina (als om het even welk) wordt gespecificeerd.

## Gegevensverzameling

In de **Gegevensverzameling** selecteert u de gegevens van het archief en/of het achterkantoor die u naar de rand van het Experience Platform wilt verzenden. Om ervoor te zorgen dat uw Adobe Commerce-instantie kan beginnen met het verzamelen van gegevens, raadpleegt u de [voorwaarden](overview.md#prerequisites).

Zie het gebeurtenisonderwerp om meer over te leren [storefront](events.md#storefront-events) en [achterkantoor](events.md#back-office-events) gebeurtenissen.

>[!NOTE]
>
>Alle velden in het dialoogvenster **Gegevensverzameling** van toepassing op **Website** bereik of hoger.

1. Selecteren **Gebeurtenissen van Storefront** als u gedragsgegevens van de storefront wilt verzenden.

   >[!NOTE]
   >
   >De **Gebeurtenissen van Storefront** Schakel het selectievakje automatisch in als de AEP Web SDK en de Organisatie-id geldig zijn.

1. Selecteren **Back office evenementen** als u de statusinformatie van een bestelling wilt verzenden, bijvoorbeeld of een bestelling is geplaatst, geannuleerd, terugbetaald of verzonden.

   >[!NOTE]
   >
   >Als u **Back office evenementen**, worden alle gegevens van het achterkantoor naar de rand van het Experience Platform verzonden. Als een winkelier ervoor kiest zich af te melden voor gegevensverzameling, moet u de privacyvoorkeur van de winkels expliciet instellen in het Experience Platform. Dit is anders dan storefront-gebeurtenissen waarbij de verzamelaar al toestemming afhandelt op basis van de voorkeuren van de winkels. [Meer informatie](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/consent/adobe/dataset.html) over het instellen van de privacyvoorkeur van een winkelier in het Experience Platform.

1. Om de updates van de backoffice gebeurtenisgegevens te verzekeren die op een programma volgens een [kraan](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/cron.html) taak, moet u de `Sales Orders Feed` indexeren naar `Update by Schedule`.

   1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL System]** > _[!UICONTROL Tools]_>**[!UICONTROL Index Management]**.

   1. Schakel het selectievakje in voor de `Sales Orders Feed` indexeerprogramma.

   1. Set **[!UICONTROL Actions]** tot `Update by Schedule`.

   1. Als u de gegevens van het achterkantoor voor het eerst toelaat, stel de volgende bevelen in werking om opnieuw te indexeren en een resync teweeg te brengen. Volgende resyncs komen automatisch voor zolang als [kraan](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/cron.html) taak correct is ingesteld.

      ```bash
      bin/magento index:reindex sales_order_data_exporter_v2
      ```

      ```bash
      bin/magento saas:resync --feed orders
      ```

1. (Sla deze stap over als u uw eigen AEP Web SDK gebruikt.) [Maken](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#create) een gegevensstroom in de Adobe Experience Platform of selecteer een bestaande gegevensstroom u voor inzameling wilt gebruiken.

1. (Sla deze stap over als u uw eigen AEP Web SDK gebruikt.) In de **DataStream-id** veld, plakt u de id van die nieuwe of bestaande gegevensstroom.

## Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Toepassingsgebied | Specifieke website waarop u de configuratie-instellingen wilt toepassen. |
| Organisatie-id (wereldwijd) | Id die behoort tot de organisatie die het Adobe DX-product heeft aangeschaft. Deze id koppelt uw Adobe Commerce-exemplaar aan Adobe Experience Platform. |
| Is de AEP Web SDK reeds opgesteld aan uw plaats | Schakel dit selectievakje in als u uw eigen AEP Web SDK aan uw site hebt toegewezen |
| AEP Web SDK Name (Global) | Als u reeds een Experience Platform Web SDK hebt die aan uw plaats wordt opgesteld, specificeer de naam van die SDK op dit gebied. Dit staat de Collector van de Gebeurtenis Storefront en de Gebeurtenis SDK toe om uw Experience PlatformWeb SDK eerder dan de versie te gebruiken die door de schakelaar van het Experience Platform wordt opgesteld. Als u geen Experience Platform Web SDK hebt die aan uw plaats wordt opgesteld, verlaat dit gebied leeg en de schakelaar van het Experience Platform stelt voor u op. |
| Gebeurtenissen van Storefront | Wordt standaard ingeschakeld zolang de organisatie-id en de gegevensstroom-id geldig zijn. Met Storefront-gebeurtenissen worden geanonimiseerde gedragsgegevens verzameld bij kopers die door uw site bladeren. |
| Back Office-gebeurtenissen | Als deze optie is ingeschakeld, bevat de gebeurtenislading geanonimiseerde gegevens over de status van de bestelling, zoals of een bestelling is geplaatst, geannuleerd, terugbetaald of verzonden. |
| DataStream-id (website) | ID die gegevens om van Adobe Experience Platform aan andere Adobe DX producten toestaat te stromen. Deze id moet zijn gekoppeld aan een specifieke website in uw specifieke Adobe Commerce-exemplaar. Als u uw eigen SDK van het Web van het Experience Platform specificeert, specificeer geen gegevensstroom identiteitskaart op dit gebied. De verbindingslijn van het Experience Platform gebruikt gegevensstroom identiteitskaart verbonden aan die SDK en negeert om het even welke gegevensstroom ID die op dit gebied (als om het even welk) wordt gespecificeerd. |

## Controleren of gegevens naar Experience Platform worden verzonden

Na het instappen, beginnen de storefrontgegevens aan de rand van het Experience Platform te stromen. De gegevens van het achterkantoor nemen ongeveer 5 minuten na het instappen voor aan de rand te verschijnen. Volgende updates zijn zichtbaar aan de rand op basis van het uitsnijdschema.

Wanneer de gegevens van de Handel naar de rand van het Experience Platform worden verzonden, kunt u rapporten als het volgende bouwen:

![Commerciële gegevens in Adobe Experience Platform](assets/aem-data-1.png)
_Commerciële gegevens in Adobe Experience Platform_
