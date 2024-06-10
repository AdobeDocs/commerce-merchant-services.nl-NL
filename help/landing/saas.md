---
title: Commerce Services Connector
description: Leer hoe u uw Adobe Commerce- of Magento Open Source-instantie integreert met de API-sleutels voor productie en sandbox.
exl-id: 28027a83-449b-4b96-b926-a7bfbfd883d8
feature: Services, Saas
role: Admin, User
source-git-commit: 448cfcc1297aba21383cdba3284aeb95095360b2
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 0%

---

# [!DNL Commerce Services Connector]

Sommige Adobe Commerce- en Magento Open Source-functies worden aangedreven door [!DNL Commerce Services] en geïmplementeerd als SaaS (software als service). Als u deze services wilt gebruiken, moet u verbinding maken met uw [!DNL Commerce] -instantie die de API-sleutels voor productie en sandbox gebruikt, en geeft u de gegevensruimte op in het dialoogvenster [configuratie](https://experienceleague.adobe.com/docs/commerce-admin/config/services/saas.html). U hoeft dit maar één keer in te stellen.

## Beschikbare services {#availableservices}

De volgende lijst bevat de [!DNL Commerce] functies die u kunt openen via de [!DNL Commerce Services Connector]:

| Service | Beschikbaarheid |
| ---|--- |
| [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) aangedreven door Adobe Sensei | Adobe Commerce |
| [[!DNL Live Search]](/help/live-search/overview.md) aangedreven door Adobe Sensei | Adobe Commerce |
| [[!DNL Payment Services]](/help/payment-services/overview.md) | Adobe Commerce en Magento Open Source |
| [[!DNL Channel Manager]](https://experienceleague.adobe.com/docs/commerce-channels/channel-manager/intro-to-channel-manager/overview.html) | Adobe Commerce en Magento Open Source |
| [[!DNL Site-Wide Analysis Tool]](https://experienceleague.adobe.com/docs/commerce-operations/tools/site-wide-analysis-tool/intro.html) | Adobe Commerce |
| [[!DNL Catalog Service]](/help/catalog-service/overview.md) | Adobe Commerce |
| [[!DNL Data Connection]](/help/data-connection/overview.md) | Adobe Commerce |

## Architectuur

Op hoog niveau [!DNL Commerce Services Connector] bestaat uit de volgende kernelementen:

![Commerce Services Connector Architectuur](assets/saas-config-sync-workflow.png)

In de volgende secties wordt elk van deze elementen nader besproken.

## Credentials {#apikey}

De API-sleutels voor productie en sandbox worden gegenereerd op basis van de [!DNL Commerce] de [licentiehouder](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/start/onboarding) die door een uniek [!DNL Commerce] ID (MageID). Machtigingsvalidatie doorgeven voor services zoals [!DNL Product Recommendations] of [!DNL Live Search]kan de eigenaar van de licentie voor de organisatie van de handelaar de set met API-sleutels genereren, zolang de account zich in goede staat bevindt.

De sleutels kunnen op een &quot;behoefte-aan-weet&quot;basis met het systeemintegrator of ontwikkelingsteam worden gedeeld dat projecten en milieu&#39;s namens de vergunninghouder beheert. Ontwikkelaars die zijn toegekend [!DNL Shared Access] door de eigenaar van de licentie de sleutels niet namens hem kunnen genereren, zelfs niet als de organisatie van de handelaar aanwezig is in de [!DNL Switch Accounts] vervolgkeuzelijst op hun account.

Daarnaast hebben integrators van oplossingen ook het recht om te gebruiken [!DNL Commerce Services]. Als u een oplossingsintegrator bent, de ondertekenaar van [!DNL Commerce] het partnercontract zou de API sleutels moeten produceren.

>[!NOTE]
>
>De eigenaar van de licentie is doorgaans de primaire contactpersoon op de Adobe Commerce-account en is niet altijd dezelfde als de projecteigenaar van de Adobe Commerce voor het infrastructuurproject in de cloud.

### De API-sleutels voor productie en sandbox genereren {#genapikey}

1. Aanmelden bij uw [!DNL Commerce] account op [https://account.magento.com](https://account.magento.com/){:target=&quot;_blank&quot;}.

1. Onder de **Magento** tab, selecteert u **API-portaal** op de zijbalk.

1. Van de _Omgeving_ menu, selecteert u **Productie** of **Sandbox**.

1. Typ een naam in het dialoogvenster _API-toetsen_ sectie en klik op **Nieuwe toevoegen**.

   Hiermee wordt een dialoogvenster geopend waarin u de nieuwe sleutel kunt downloaden.

   ![Persoonlijke sleutel downloaden](assets/download-api-private-key.png)

   >[!WARNING]
   >
   > Dit is de enige mogelijkheid om uw toetsen te kopiëren of te downloaden.

1. Klikken **Downloaden** klik vervolgens op **Annuleren**.

1. Herhaal bovenstaande stappen voor elke omgeving (productie en sandbox).

   De **API-toetsen** geeft nu uw API-toetsen (Public) weer. Wanneer u werkt, hebt u zowel de productietoetsen als de sandboxsleutels nodig (Public+Private) [een SaaS-project selecteren of maken](#createsaasenv).

## SaaS-configuratie {#saasenv}

[!DNL Commerce] instanties moeten worden geconfigureerd met een SaaS-project en een SaaS-gegevensruimte, zodat [!DNL Commerce Services] kan gegevens naar de juiste locatie verzenden. Een SaaS-project groepeert alle SaaS-gegevensruimten. De SaaS-gegevensruimten worden gebruikt voor het verzamelen en opslaan van gegevens die [!DNL Commerce Services] om te werken. Sommige van deze gegevens kunnen worden geëxporteerd uit de [!DNL Commerce] -instantie en sommige kunnen worden opgehaald uit winkelgedrag op de winkelwebsite. Die gegevens blijven vervolgens bewaard om de cloudopslag te beveiligen.

Voor [!DNL Product Recommendations], bevat de SaaS-gegevensruimte catalogus- en gedragsgegevens. U kunt een [!DNL Commerce] instantie aan een SaaS gegevensruimte door [selecteren](https://docs.magento.com/user-guide/configuration/services/saas.html) in de [!DNL Commerce] configuratie.

>[!WARNING]
>
> De SaaS-gegevensruimte van uw productie alleen gebruiken voor uw productie [!DNL Commerce] installatie om gegevensbotsingen te vermijden. Anders loopt u het risico dat u gegevens van uw productiesite verontreinigt met testgegevens, wat implementatievertragingen veroorzaakt. De gegevens van uw productieproduct kunnen bijvoorbeeld per ongeluk worden overschreven door opvoergegevens, zoals ophalings-URL&#39;s.

### Een SaaS-project selecteren of maken {#createsaasenv}

Om een SaaS- project te selecteren of te creëren, verzoek [!DNL Commerce] API-sleutel uit de [!DNL Commerce] licentiehouder voor uw winkel.

1. Op de _Beheerder_ zijbalk, ga naar **Systeem** > Services > **Commerce Services Connector**.

   Als u het geneesmiddel niet ziet **[!UICONTROL Commerce Services Connector]** in de [!DNL Commerce] configuratie, installeer de [!DNL Commerce] modules naar wens [[!DNL Commerce] service](#availableservices). Zorg er ook voor dat `magento/module-services-id` pakket is geïnstalleerd.

1. In de _Sandbox API-sleutels_ en _API-sleutels voor productie_ secties, plakt u de hoofdwaarden.

   Persoonlijke sleutels moeten `----BEGIN PRIVATE KEY---` aan het begin van de toets en `----END PRIVATE KEY----` aan het einde van de persoonlijke sleutel.

1. Klikken **Opslaan**.

Alle SaaS-projecten die aan uw sleutels zijn gekoppeld, worden weergegeven in de **Project** in het veld **SaaS-id** sectie.

1. Als er geen SaaS-projecten bestaan, klikt u op **Project maken**. Dan in **Project** van gebied, ga een naam voor uw project SaaS in.

   Wanneer u een project SaaS creeert, [!DNL Commerce] genereert een of meer SaaS-gegevensruimten afhankelijk van uw [!DNL Commerce] licentie:
   - Adobe Commerce - Eén productiedeswitruimte; twee testgegevensruimten
   - Magento Open Source - Eén gegevensruimte voor productie; geen gegevensruimten voor tests

1. Selecteer de **Gegevensruimte** voor de huidige configuratie van uw [!DNL Commerce] opslaan.

>[!WARNING]
>
> Als u nieuwe sleutels in de sectie van het Portaal API van Mijn Rekening produceert, werk onmiddellijk de API sleutels in de configuratie Admin bij. Als u nieuwe sleutels produceert en niet hen in Admin bijwerkt, werken uw uitbreidingen SaaS niet meer en u verliest waardevolle gegevens.

Als u de namen van uw SaaS-project of gegevensruimte wilt wijzigen, klikt u op **Naam wijzigen** naast een van beide. Het veranderen van de naam beïnvloedt niet uw dienst omdat de naam slechts een etiket is om u te helpen tussen projecten en gegevensruimten identificeren en onderscheiden.

## IMS-organisatie (optioneel) {#organizationid}

Als u uw Adobe Commerce-exemplaar wilt verbinden met de Adobe Experience Platform, meldt u zich aan bij uw Adobe-account met uw Adobe ID. Nadat u zich hebt aangemeld, wordt de IMS-organisatie die is gekoppeld aan uw Adobe-account in deze sectie weergegeven.

## Catalogus synchroniseren

Wanneer uw [!DNL Commerce] instantie maakt verbinding met [!DNL Commerce Services], exporteert het catalogussynchronisatieproces productgegevens uit uw [!DNL Commerce] server naar [!DNL Commerce Services]. Momenteel gebruikt alleen Product Recommendations de catalogussynchronisatieservice. [Meer informatie](catalog-sync.md) over het synchronisatieproces van de catalogus.
