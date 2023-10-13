---
title: Connect Commerce-gegevens naar Adobe Experience Platform
description: Leer hoe u de gegevens van de Handel met de Adobe Experience Platform verbindt.
exl-id: 87898283-545c-4324-b1ab-eec5e26a303a
feature: Personalization, Integration, Configuration
source-git-commit: 24494546d6d21cf46e3cb9f0fdd503ec8007daf8
workflow-type: tm+mt
source-wordcount: '2263'
ht-degree: 0%

---

# Connect Commerce-gegevens naar Adobe Experience Platform

Wanneer u de aansluiting voor het Experience Platform installeert, worden twee nieuwe configuratiepagina&#39;s weergegeven in de **Systeem** menu onder **Services** in de handel _Beheerder_.

- Commerce Services Connector
- Experience Platform Connector

Om uw Adobe Commerce instantie aan Adobe Experience Platform aan te sluiten, moet u beide schakelaars vormen, die met de schakelaar van de Diensten van de Handel dan met de schakelaar van het Experience Platform beëindigen beginnen.

## De schakelaar van de Diensten van de Handel bijwerken

Als u eerder een dienst van Adobe Commerce hebt geïnstalleerd, hebt u waarschijnlijk reeds de schakelaar van de Diensten van de Handel gevormd. Indien niet, dan moet u de volgende taken op [Commerce Services-connector](../landing/saas.md) pagina:

1. Meld u aan bij uw account voor Handel om [productie- en sandbox-API-sleutels ophalen](../landing/saas.md#credentials).
1. Selecteer een [SaaS-gegevensruimte](../landing/saas.md#saas-configuration).
1. Meld u aan bij uw Adobe-account om [uw organisatie-id ophalen](../landing/saas.md#ims-organization-optional).

Nadat u de schakelaar van de Diensten van de Handel vormt, vormt u dan de schakelaar van het Experience Platform.

## De aansluiting van het Experience Platform bijwerken

In deze sectie verbindt u uw Adobe Commerce-exemplaar met de Adobe Experience Platform met behulp van uw organisatie-id. Vervolgens kunt u het type gegevens opgeven (winkel en achterkantoor) dat u naar de rand van het Experience Platform wilt verzenden.

![Configuratie van Experience Platform-aansluiting](assets/epc-config-dc.png)

## Algemeen

1. Ga in Beheer naar **Systeem** > Services > **Experience Platform Connector**.

1. Op de **Instellingen** tab onder **Algemeen**, controleert u de id die aan uw Adobe Experience Platform-account is gekoppeld, zoals deze is geconfigureerd in het dialoogvenster [Commerce Services Connector](../landing/saas.md#organizationid). De organisatie-id is algemeen. Per Adobe Commerce-exemplaar kan slechts één organisatie-id worden gekoppeld.

1. In de **Toepassingsgebied** vervolgkeuzelijst, de context instellen op **Website**.

1. (Optioneel) Als u al een [AEP Web SDK (legering)](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) opgesteld aan uw plaats, laat checkbox toe en voeg de naam van uw Web SDK van AEP toe. Anders, verlaat deze gebieden leeg en de schakelaar van het Experience Platform stelt voor u op.

   >[!NOTE]
   >
   >Als u uw eigen SDK van het Web van AEP specificeert, gebruikt de schakelaargebruik van het Experience Platform identiteitskaart verbonden aan die SDK en niet gegevensstroom ID die op deze pagina (als om het even welk) wordt gespecificeerd.

## Gegevensverzameling

In deze sectie geeft u het type gegevens op dat u naar de rand van het Experience Platform wilt verzenden. Er zijn twee soorten gegevens: client-side en server-side.

Gegevens aan de clientzijde zijn gegevens die worden vastgelegd op de opslagront. Dit omvat winkelinteracties, zoals `View Page`, `View Product`, `Add to Cart`, en [aanvraaglijst](events.md#b2b-events) informatie (voor B2B-handelaren). Gegevens aan de serverzijde of gegevens aan de achterzijde van het kantoor zijn gegevens die zijn vastgelegd in de Commerce-servers. Dit omvat informatie over de status van een bestelling, zoals of een bestelling is geplaatst, geannuleerd, terugbetaald, verzonden of voltooid.

Als u er zeker van wilt zijn dat uw Adobe Commerce-instantie kan beginnen met het verzamelen van gegevens, raadpleegt u de [voorwaarden](overview.md#prerequisites).

Zie het gebeurtenisonderwerp om meer over te leren [storefront](events.md#storefront-events) en [achterkantoor](events.md#back-office-events) gebeurtenissen.

>[!NOTE]
>
>Alle velden in het dialoogvenster **Gegevensverzameling** van toepassing **Website** bereik of hoger.

1. Selecteren **Gebeurtenissen van Storefront** als u gedragsgegevens van de storefront wilt verzenden.

1. Selecteren **Back office evenementen** als u de statusinformatie van een bestelling wilt verzenden, bijvoorbeeld of een bestelling is geplaatst, geannuleerd, terugbetaald of verzonden.

   >[!NOTE]
   >
   >Als u **Back office evenementen**, worden alle gegevens van het achterkantoor naar de rand van het Experience Platform verzonden. Als een winkelier ervoor kiest zich af te melden voor gegevensverzameling, moet u de privacyvoorkeur van de winkels expliciet instellen in het Experience Platform. Dit is anders dan storefront-gebeurtenissen waarbij de verzamelaar al toestemming afhandelt op basis van de voorkeuren van de winkels. [Meer informatie](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/consent/adobe/dataset.html) over het instellen van de privacyvoorkeur van een winkelier in het Experience Platform.

1. (Sla deze stap over als u uw eigen AEP Web SDK gebruikt.) [Maken](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#create) een gegevensstroom in de Adobe Experience Platform of selecteer een bestaande gegevensstroom u voor inzameling wilt gebruiken. Voer die gegevensstroom-id in het dialoogvenster **DataStream-id** veld.

1. Voer de **Dataset-id** dat u uw gegevens van de Handel wilt bevatten. De id van de gegevensset zoeken:

   1. Open de interface van het Experience Platform en selecteer **Gegevenssets** in de linkernavigatie om het dialoogvenster **Gegevenssets** dashboard. Het dashboard maakt een lijst van alle beschikbare datasets voor uw organisatie. De details worden getoond voor elke vermelde dataset, met inbegrip van zijn naam, het schema de dataset zich aan, en status van de meest recente versiereeks houdt.
   1. Open de dataset verbonden aan uw gegevensstroom.
   1. In de rechterruit, bekijk de details over de dataset. Kopieer de id van de gegevensset.

   ![Gegevensset-id kopiëren](./assets/retrieve-dataset-id.png){width="700" zoomable="yes"}

1. Om de updates van de backoffice gebeurtenisgegevens te verzekeren die op een programma volgens een [kraan](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/cron.html) taak, moet u de `Sales Orders Feed` indexeren naar `Update by Schedule`.

   1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL System]** > _[!UICONTROL Tools]_>**[!UICONTROL Index Management]**.

   1. Schakel het selectievakje in voor de `Sales Orders Feed` indexeerprogramma.

   1. Set **[!UICONTROL Actions]** tot `Update by Schedule`.

   1. Als u de gegevens van het achterkantoor voor het eerst toelaat, stel de volgende bevelen in werking om opnieuw te indexeren en een resync teweeg te brengen. Volgende resyncs komen automatisch voor zolang als [kraan](https://experienceleague.adobe.com/docs/commerce-admin/systems/tools/cron.html) taak correct is ingesteld.

      ```bash
      bin/magento index:reindex sales_order_data_exporter_v2
      ```

      ```bash
      bin/magento saas:resync --feed orders
      ```

## Veldomschrijvingen

| Veld | Beschrijving |
|--- |--- |
| Toepassingsgebied | Specifieke website waarop u de configuratie-instellingen wilt toepassen. |
| Organisatie-id (wereldwijd) | Id die behoort tot de organisatie die het Adobe DX-product heeft aangeschaft. Deze id koppelt uw Adobe Commerce-exemplaar aan Adobe Experience Platform. |
| Is de AEP Web SDK reeds opgesteld aan uw plaats | Schakel dit selectievakje in als u uw eigen AEP Web SDK aan uw site hebt toegewezen |
| AEP Web SDK Name (global) | Als u reeds een Experience Platform Web SDK hebt die aan uw plaats wordt opgesteld, specificeer de naam van die SDK op dit gebied. Dit staat de Collector van de Gebeurtenis Storefront en de Gebeurtenis SDK toe om uw Experience PlatformWeb SDK eerder dan de versie te gebruiken die door de schakelaar van het Experience Platform wordt opgesteld. Als u geen Experience Platform Web SDK hebt die aan uw plaats wordt opgesteld, verlaat dit gebied leeg, en de schakelaar van het Experience Platform stelt één voor u op. |
| Gebeurtenissen van Storefront | Wordt standaard ingeschakeld zolang de organisatie-id en de gegevensstroom-id geldig zijn. Met Storefront-gebeurtenissen worden geanonimiseerde gedragsgegevens verzameld bij kopers die door uw site bladeren. |
| Back office evenementen | Als deze optie is ingeschakeld, bevat de gebeurtenislading geanonimiseerde gegevens over de status van de bestelling, zoals of een bestelling is geplaatst, geannuleerd, terugbetaald of verzonden. |
| DataStream-id (website) | ID die gegevens om van Adobe Experience Platform aan andere Adobe DX producten toestaat te stromen. Deze id moet zijn gekoppeld aan een specifieke website in uw specifieke Adobe Commerce-exemplaar. Als u uw eigen SDK van het Web van het Experience Platform specificeert, specificeer geen gegevensstroom identiteitskaart op dit gebied. De verbindingslijn van het Experience Platform gebruikt gegevensstroom identiteitskaart verbonden aan die SDK en negeert om het even welke gegevensstroom ID die op dit gebied (als om het even welk) wordt gespecificeerd. |
| Gegevensset-id (website) | Identiteitskaart van de dataset die uw gegevens van de Handel bevat. Dit veld is vereist tenzij u de optie **Gebeurtenissen van Storefront** of **Back office evenementen** selectievakjes. Ook, als u uw eigen SDK van het Web van het Experience Platform gebruikt en daarom geen gegevensstroom identiteitskaart specificeerde, moet u dataset ID nog toevoegen verbonden aan uw gegevensstroom. Anders kunt u dit formulier niet opslaan. |

>[!NOTE]
>
>Na het instappen, beginnen de storefrontgegevens aan de rand van het Experience Platform te stromen. Het duurt ongeveer vijf minuten voordat de gegevens op het achterkantoor aan de rand worden weergegeven. Volgende updates zijn zichtbaar aan de rand op basis van het uitsnijdschema.

## Gegevens in historische volgorde verzenden

Adobe Commerce verzamelt maximaal vijf jaar [historische ordegegevens en status](events.md#back-office-events). U kunt de schakelaar van het Experience Platform gebruiken om die historische gegevens naar het Experience Platform te verzenden om uw klantenprofielen te verrijken en de klantenervaringen te personaliseren die op die vroegere orden worden gebaseerd. De gegevens worden opgeslagen in een dataset binnen Experience Platform.

Terwijl de Handel reeds de historische ordegegevens verzamelt, zijn er verscheidene stappen u moet voltooien om die gegevens naar Experience Platform te verzenden.

Bekijk deze video om meer over historische orden te leren dan voltooi de volgende stappen om historische ordeverzameling uit te voeren.

>[!VIDEO](https://video.tv.adobe.com/v/3424672)

### Stap 1: Een project maken in Adobe Developer Console

>[!NOTE]
>
>Als u reeds geïnstalleerd en toegelaten hebt [Audience Activation](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html) hebt voltooid, hebt u stap 1 en 2 al uitgevoerd en kunt u stap 3 overslaan.

Creeer een project in de Console van Adobe Developer die Handel voor authentiek verklaart zodat kan het Experience Platform API vraag maken.

Volg de stappen in het dialoogvenster [API&#39;s van Experience Platforms verifiëren en openen](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html) zelfstudie.

Terwijl u de zelfstudie doorloopt, moet u ervoor zorgen dat uw project het volgende heeft:

- Toegang tot het volgende [productprofielen](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-product-profiles): **Standaardproductie, alle toegang** en **Alle toegang standaard AEP**.
- De juiste [rollen en toestemmingen worden gevormd](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#assign-api-to-a-role).
- Als u hebt besloten JSON Web Tokens (JWT) als uw server-aan-server authentificatiemethode te gebruiken, moet u ook een privé sleutel uploaden.

Het resultaat van deze stap leidt tot een configuratiedossier dat u in de volgende stap gebruikt.

### Stap 2: configuratiebestand downloaden

Download de [workspace-configuratiebestand](https://developer.adobe.com/commerce/extensibility/events/project-setup/#download-the-workspace-configuration-file). De inhoud van dit bestand kopiëren en in het **Servicerekening/Referentiedetails** pagina van de Commerce Admin.

1. Navigeer in Commerce Admin naar **Winkels** > Instellingen > **Configuratie** > **Services** > **Experience Platform Connector**.

1. Selecteer de server-aan-server vergunningsmethode die u van uitvoerde **Type Adobe I/O-autorisatie** -menu. Adobe beveelt het gebruik van OAuth aan. JWT is vervangen. [Meer informatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/).

1. (Alleen JWT) Kopieer en plak de inhoud `private.key` in het bestand **Clientgeheim** veld. Gebruik de volgende opdracht om de inhoud te kopiëren.

   ```bash
   cat config/private.key | pbcopy
   ```

   Zie [Service Account (JWT)-verificatie](https://developer.adobe.com/developer-console/docs/guides/authentication/JWT/) voor meer informatie over de `private.key` bestand.

1. Kopieer de inhoud van het dialoogvenster `<workspace-name>.json` in het bestand **Servicerekening/Referentiedetails** veld.

   ![Admin-configuratie Experience Platform Connector](./assets/epc-admin-config.png){width="700" zoomable="yes"}

1. Klikken **Config opslaan**.

### Stap 3: De bestelsynchronisatieservice instellen

Nadat u de referenties voor ontwikkelaars hebt ingevoerd, stelt u de bestelsynchronisatieservice in. De bestelsynchronisatieservice gebruikt de [Message Queue Framework](https://developer.adobe.com/commerce/php/development/components/message-queues/) en RabbitMQ. Nadat u deze stappen hebt uitgevoerd, kunnen de statusgegevens van de bestelling worden gesynchroniseerd met SaaS, wat vereist is voordat deze naar het Experience Platform worden verzonden.

1. [Inschakelen](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/configure/service/rabbitmq.html) RabbitMQ.

   >[!NOTE]
   >
   >RabbitMQ is al ingesteld voor Commerce versie 2.4.7 en hoger, maar u moet de consument inschakelen.

1. Gebruikers in een wachtrij met berichten inschakelen op snijtaak in `.magento.env.yaml` gebruiken `CRON_CONSUMERS_RUNNER` omgevingsvariabele.

   ```yaml
      stage:
        deploy:
          CRON_CONSUMERS_RUNNER:
            cron_run: true
   ```

   >[!NOTE]
   >
   >Zie de [documentatie over implementatievariabelen](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/configure/env/stage/variables-deploy.html#cron_consumers_runner) voor meer informatie over alle beschikbare configuratieopties.

Als de bestelsynchronisatieservice ingeschakeld is, kunt u het historische bereik van de ordedatum opgeven op de pagina voor de aansluiting van het Experience Platform.

### Stap 4: geef een datumbereik voor de ordergeschiedenis op

Geef het datumbereik op voor de historische orders die u naar het Experience Platform wilt verzenden.

![Geschiedenis van volgorde synchroniseren](./assets/order-history.png){width="700" zoomable="yes"}

1. Ga in Beheer naar **Systeem** > Services > **Experience Platform Connector**.

1. Selecteer de **Orderhistorie** tab.

1. Onder **Synchronisatie van orderhistorie** de **Gegevensset-id kopiëren uit instellingen** selectievakje is al ingeschakeld. Dit verzekert u het zelfde dataset gebruikt die in wordt gespecificeerd **Instellingen** tab.

1. In de **Van** en **Naar** geeft u het datumbereik op voor de historische volgordegegevens die u wilt verzenden. U kunt geen datumbereik selecteren dat langer is dan vijf jaar.

1. Selecteren **[!UICONTROL Start Sync]** om de synchronisatie te activeren. Historische ordegegevens zijn batchgegevens in tegenstelling tot opslag en achterkantoorgegevens die gegevens stromen. Het duurt ongeveer 45 minuten voordat de gegevens in de batch in Experience Platform zijn ontvangen.

| Veld | Beschrijving |
|--- |--- |
| Gegevensset-id kopiëren uit instellingen | Kopieert dataset ID u op ingegaan **Instellingen** tab. |
| Gegevensset-id (website) | Identiteitskaart van de dataset die uw gegevens van de Handel bevat. Dit veld is vereist tenzij u de optie **Gebeurtenissen van Storefront** of **Back office evenementen** selectievakjes. Ook, als u uw eigen SDK van het Web van het Experience Platform gebruikt en daarom geen gegevensstroom identiteitskaart specificeerde, moet u dataset ID nog toevoegen verbonden aan uw gegevensstroom. Anders kunt u dit formulier niet opslaan. |
| Van | Datum vanaf wanneer u wilt beginnen met het verzamelen van gegevens over de ordergeschiedenis. |
| Naar | Datum vanaf welke u het verzamelen van de gegevens van de ordegeschiedenis wilt beëindigen. |
| Synchronisatie starten | Begint het proces om de gegevens van de ordegeschiedenis aan de rand van het Experience Platform te synchroniseren. Deze knop is uitgeschakeld als de **[!UICONTROL Dataset ID]** veld is leeg of de id van de gegevensset is ongeldig. |

## Bevestig dat gebeurtenisgegevens worden verzameld

Als u wilt bevestigen dat gegevens worden verzameld bij uw winkel voor Handel, gebruikt u de [Adobe Experience Platform debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html) om je plaats van de Handel te bekijken. Nadat u hebt bevestigd dat de gegevens worden verzameld, kunt u verifiëren dat uw opslag en de gegevens van de achterkantoorgebeurtenis bij de rand verschijnen door een vraag in werking te stellen die gegevens van terugkeert [gegevensset die u hebt gemaakt](overview.md#prerequisites).

1. Selecteren **Zoekopdrachten** in de linkernavigatie van het Experience Platform en klik [!UICONTROL Create Query].

   ![Query-editor](assets/query-editor.png)

1. Wanneer de Redacteur van de Vraag opent, ga een vraag in die gegevens van de dataset selecteert.

   ![Query maken](assets/create-query.png)

   Uw query ziet er bijvoorbeeld als volgt uit:

   ```sql
   SELECT * from `your_dataset_name` ORDER by TIMESTAMP DESC
   ```

1. Nadat de vraag loopt, worden de resultaten getoond in **Resultaten** tab, naast de **Console** tab. In deze weergave ziet u de tabeluitvoer van uw query.

   ![Query-editor](assets/query-results.png)

In dit voorbeeld ziet u gebeurtenisgegevens uit de [`commerce.productListAdds`](events.md#addtocart), [`commerce.productViews`](events.md#productpageview), [`web.webpagedetails.pageViews`](events.md#pageview), enzovoort. In deze weergave kunt u controleren of de gegevens van de Handel aan de rand zijn binnengekomen.

Als de resultaten niet zijn wat u verwacht, open uw dataset en zoek om het even welke ontbroken partijinvoer. Meer informatie over [problemen oplossen bij importeren van batch](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/troubleshooting.html).

## Volgende stappen

Wanneer de gegevens van de Handel naar de rand van de Experience Platform worden verzonden, kunnen andere producten van Adobe Experience Cloud, zoals Adobe Journey Optimizer, die gegevens gebruiken. U kunt Journey Optimizer bijvoorbeeld configureren om te luisteren naar bepaalde gebeurtenissen en op basis van die gebeurtenisgegevens een e-mailbericht activeren voor een eerste gebruiker of als er een verlaten winkelwagentje is. Meer weten over het uitbreiden van je handelsplatform via [maken van reizen van klanten](using-ajo.md) in Journey Optimizer.
