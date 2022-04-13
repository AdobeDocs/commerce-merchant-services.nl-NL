---
title: Commerce Services Connector
description: Leer hoe u uw Adobe Commerce- of Magento Open Source-exemplaar integreert met behulp van een API-sleutel en een persoonlijke sleutel.
exl-id: 28027a83-449b-4b96-b926-a7bfbfd883d8
source-git-commit: 6d0c7c749fe90c7c204afe47446f3483d8668b53
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 0%

---

# [!DNL Commerce Services Connector]

Sommige Adobe Commerce- en Magento Open Source-functies worden aangedreven door [!DNL Commerce Services]  en geïmplementeerd als SaaS (software als service). Als u deze services wilt gebruiken, moet u verbinding maken met uw [!DNL Commerce] -instantie met behulp van een API-sleutel en een persoonlijke sleutel, en geef de gegevensruimte op in het dialoogvenster [configuratie](https://docs.magento.com/user-guide/configuration/services/saas.html). U hoeft dit maar één keer in te stellen.

## Beschikbare services

De volgende lijst bevat de [!DNL Commerce] functies waartoe u toegang hebt via de [!DNL Commerce Services Connector]:

| Service | Beschikbaarheid |
| ---|--- |
| [[!DNL Product Recommendations]](/help/product-recommendations/overview.md) aangedreven door Adobe Sensei | Adobe Commerce |
| [[!DNL Live Search]](/help/live-search/overview.md) aangedreven door Adobe Sensei | Adobe Commerce |
| [[!DNL Payment Services]](/help/payment-services/overview.md) | Adobe Commerce en Magento Open Source |

## Architectuur

Op hoog niveau [!DNL Commerce Services Connector] bestaat uit de volgende kernelementen:

![Connectorarchitectuur voor handelsdiensten](assets/saas-config-sync-workflow.png)

In de volgende secties wordt elk van deze elementen nader besproken.

## Credentials {#apikey}

De API-sleutel en de persoonlijke sleutel worden gegenereerd op basis van de [!DNL Commerce] rekening van de vergunninghouder, die wordt aangeduid met een unieke [!DNL Commerce] ID (MageID). Machtigingsvalidatie doorgeven voor services zoals [!DNL Product Recommendations] of [!DNL Live Search]kan de licentiehouder van de organisatie van de handelaar de set API-sleutels genereren zolang de account zich in goede staat bevindt. De sleutels kunnen op een &quot;behoefte om&quot;basis met het systeem worden gedeeld integrator of ontwikkelingsteam dat projecten en milieu&#39;s namens de vergunninghouder beheert. Daarnaast hebben integrators van oplossingen ook het recht om te gebruiken [!DNL Commerce Services]. Als u een oplossingsintegrator bent, de ondertekenaar van [!DNL Commerce] het partnercontract zou de API sleutels moeten produceren.

### Een API-sleutel en een persoonlijke sleutel genereren {#genapikey}

1. Meld u aan bij uw [!DNL Commerce] account op [https://account.magento.com](https://account.magento.com/){:target=&quot;_blank&quot;}.

1. Onder de **Magento** tab, selecteert u **API-portaal** op de zijbalk.

1. Van de _Omgeving_ menu, selecteert u **Productie** of **Sandbox**.

   >[!NOTE]
   >
   > Voor [!DNL _Product Recommendations_] en [!DNL _Live zoeken_], selecteert u **Productie**. Met productiesleutels hebt u toegang tot gegevensruimten voor productie en niet-productie. Sandboxsleutels worden niet gebruikt voor deze services.

1. Typ een naam in het dialoogvenster _API-toetsen_ en klik op **Nieuwe toevoegen**.

   Hiermee wordt een dialoogvenster geopend waarin u de nieuwe sleutel kunt downloaden.

   ![Persoonlijke sleutel downloaden](assets/download-api-private-key.png)

   >[!WARNING]
   >
   > Dit is de enige mogelijkheid om uw sleutel te kopiëren of te downloaden.

1. Klikken **Downloaden** klik vervolgens op **Annuleren**.

   De **API-toetsen** wordt nu uw API-sleutel weergegeven. U hebt zowel de API-sleutel als de persoonlijke sleutel nodig wanneer u [een SaaS-project selecteren of maken](#createsaasenv).

## SaaS-configuratie {#saasenv}

[!DNL Commerce] instanties moeten worden geconfigureerd met een SaaS-project en een SaaS-gegevensruimte, zodat [!DNL Commerce Services] kan gegevens naar de juiste locatie verzenden. In een SaaS-project worden alle SaaS-gegevensruimten gegroepeerd. De SaaS-gegevensruimten worden gebruikt voor het verzamelen en opslaan van gegevens die [!DNL Commerce Services] om te werken. Sommige van deze gegevens kunnen worden geëxporteerd uit de [!DNL Commerce] -instantie en sommige kunnen worden opgehaald uit winkelgedrag op de winkelwebsite. Die gegevens blijven vervolgens bewaard om de cloudopslag te beveiligen.

Voor [!DNL Product Recommendations], bevat de SaaS-gegevensruimte catalogus- en gedragsgegevens. U kunt een [!DNL Commerce] instantie aan een SaaS gegevensruimte door [selecteren](https://docs.magento.com/user-guide/configuration/services/saas.html) in de [!DNL Commerce] configuratie.

>[!WARNING]
>
> De SaaS-gegevensruimte van uw productie alleen gebruiken voor uw productie [!DNL Commerce] installatie om gegevensbotsingen te vermijden. Anders loopt u het risico dat u gegevens van uw productiesite verontreinigt met testgegevens, wat implementatievertragingen veroorzaakt. De gegevens van uw productieproduct kunnen bijvoorbeeld per ongeluk worden overschreven door opvoergegevens, zoals ophalings-URL&#39;s.

### Een SaaS-project selecteren of maken {#createsaasenv}

>[!NOTE]
>
> Als u de **[!UICONTROL Commerce Services Connector]** in de [!DNL Commerce] configuratie, moet u installeren [!DNL Commerce] modules naar wens [!DNL Commerce] diensten, zoals [[!DNL Product Recommendations]](/help/product-recommendations/install-configure.md).

Om een SaaS- project te selecteren of te creëren, verzoek [!DNL Commerce] API-sleutel uit de [!DNL Commerce] licentiehouder voor uw winkel.

1. Op de _Beheer_ zijbalk, ga naar **Winkels** > _Instellingen_ > **Configuratie**.

1. Vouw in het linkerdeelvenster uit **Services** en kiest u **Commerce Services Connector**.

1. In de _API-toetsen_ -sectie, plakt u de hoofdwaarden voor de **API-sleutel voor productie** en de **Persoonlijke sleutel voor productie**.

   Persoonlijke sleutels moeten `----BEGIN PRIVATE KEY---` aan het begin van de toets en `----END PRIVATE KEY----` aan het einde van de persoonlijke sleutel.

1. Klikken **Config opslaan**.

Alle SaaS-projecten die aan uw API-sleutel zijn gekoppeld, worden weergegeven in de **SaaS-project** veld.

1. Als er geen SaaS-projecten bestaan, klikt u op **Project maken**. Dan in **Projectnaam** van gebied, ga een naam voor uw project SaaS in.

   Wanneer u een project SaaS creeert, [!DNL Commerce] genereert een of meer SaaS-gegevensruimten afhankelijk van uw [!DNL Commerce] licentie:
   - Adobe Commerce - Eén productieruimte; twee testgegevensruimten
   - Magento Open Source - Eén productieruimte; geen testgegevensruimten

1. Selecteer **SaaS-gegevensruimte** voor de huidige configuratie van uw [!DNL Commerce] opslaan.

>[!WARNING]
>
> Als u nieuwe sleutels in de sectie van het Portaal API van Mijn Rekening produceert, werk onmiddellijk de API sleutels in de configuratie Admin bij. Als u nieuwe sleutels produceert en niet hen in Admin bijwerkt, werken uw uitbreidingen SaaS niet meer en u verliest waardevolle gegevens.

Als u de naam van een SaaS-project of gegevensruimte wilt wijzigen, klikt u op de knop **Naam van dit project wijzigen** of **Naam gegevensruimte wijzigen** respectievelijk.

## Catalogus synchroniseren

Wanneer uw [!DNL Commerce] instantie maakt verbinding met [!DNL Commerce Services], exporteert het catalogussynchronisatieproces productgegevens uit uw [!DNL Commerce] server naar [!DNL Commerce Services]. [Meer informatie](catalog-sync.md) over het synchronisatieproces van de catalogus.
