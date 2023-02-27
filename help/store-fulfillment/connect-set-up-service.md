---
title: De oplossing voor winkelvervulling aansluiten
description: Bepaal de verbindingen tussen Adobe Commerce en de oplossing van de Afhandeling van de Opslag door een integratie van Adobe Commerce te creëren en te machtigen en de de rekeningsgeloofsbrieven van de Rekening van de Afhandeling van de Opslag toe te voegen aan de de dienstconfiguratie van Adobe Commerce.
role: User, Admin
level: Intermediate
exl-id: 74c71c43-305a-4ea7-84f8-95f3ce0a9482
source-git-commit: e7493618e00e28e2de5043ae2d7e05a81110d8f1
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# De oplossing voor winkelvervulling aansluiten

Connect Store Fulfillment Services met Adobe Commerce door de vereiste verificatiereferenties en verbindingsgegevens toe te voegen aan Adobe Commerce Admin.

- **[Configureren [!DNL Commerce integration settings]](#create-an-adobe-commerce-integration)**- Maak een Adobe Commerce-integratie voor de services van Store Fulfillment en genereer de toegangstokens om binnenkomende aanvragen van de servers van Store Fulfillment te verifiëren.

- **[Accountgegevens configureren voor services voor winkeluitvoering](#configure-store-fulfillment-account-credentials)**-Voeg je gegevens toe om Adobe Commerce te verbinden met je account voor winkelvervulling.

>[!NOTE]
>
>Voltooi de verbindingsconfiguratie en bevestig de verbinding met succes alvorens u begint te testen.

## Een Adobe Commerce-integratie maken

Om Adobe Commerce met de diensten van de Afhandeling van de Opslag te integreren, creeert u een integratie van de Handel en produceert toegangstokens die kunnen worden gebruikt om verzoeken van de servers van de Afhandeling van de Opslag voor authentiek te verklaren. U moet ook de Adobe Commerce bijwerken [!UICONTROL Consumer Settings] opties om te voorkomen `The consumer isn't authorized to access %resources.` Antwoordfouten op verzoeken van Adobe Commerce aan [!DNL Store Fulfillment] diensten.

1. Creëer in de beheerfunctie de integratie voor winkeluitvoering.

   - De extensie een naam geven
   - Voer uw e-mailadres in
   - Wachtwoord voor beheerdersaccount invoeren

1. Configureren [!UICONTROL API Resource Access permissions] voor de integratie—selecteer `[!UICONTROL All]`

1. Genereer de toegangstokens voor verificatie door de integratie op te slaan en te activeren.

1. Kopieer en sla de toegangstokens op een veilige, gecodeerde locatie op.

1. Werk samen met uw accountmanager om de configuratie aan de kant van de Store Fulfillment te voltooien en de integratie te autoriseren.

1. Adobe Commerce inschakelen [!UICONTROL Consumer Settings] optie voor [!UICONTROL Allow OAuth Access Tokens to be used as standalone Bearer tokens].

   - Ga vanuit de beheerder naar **[!UICONTROL Stores]** >  [!UICONTROL Configuration] > **[!UICONTROL Services]** >  **[!UICONTROL OAuth]** > **[!UICONTROL Consumer Settings]**

   - Stel de [!UICONTROL Allow OAuth Access Tokens to be used as standalone Bearer tokens] optie voor **[!UICONTROL Yes]**.

>[!IMPORTANT]
>
> Het integratietoken is specifiek voor de omgeving. Als u het gegevensbestand voor een milieu met de brongegevens van een verschillende milieu-voor bijvoorbeeld het herstellen van productiegegevens van een het opvoeren milieu-sluit uit `oauth_token` lijst van de gegevensbestanduitvoer zodat de details van het integratietoken niet tijdens terugzetverrichting worden beschreven.


## Geef de gegevens van de opslagaccount op

Nadat u het innameformulier hebt ingevuld, wordt voor u een account gemaakt voor het ophalen van een Walmart-winkel. U ontvangt de volgende referenties wanneer deze beschikbaar zijn:

- [!DNL Merchant ID]
- [!DNL Consumer ID]
- [!DNL Consumer Secret]
- [!DNL API Server URL]
- [!DNL Token Auth Server URL] (doorgaans hetzelfde als de bovenstaande configuratie)

Deze geloofsbrieven worden vereist om de Afhandeling van de Opslag te vormen en te gebruiken.

>[!NOTE]
>
>Het maken van een account kan enige tijd duren. Terwijl u op geloofsbrieven wacht, [Andere instellingen voor de oplossing Afhandeling opslaan bekijken en configureren](service-config-settings-overview.md).

### Referenties toevoegen om verbinding te maken met Afhandeling van winkel

1. Configureren [accountgegevens](enable-general.md) voor de productie- en sandboxomgevingen.

1. Ga vanuit de beheerder naar **[!UICONTROL Stores > Configuration > Services > Store Fulfillment by Walmart Commerce Technologies]**

1. Voer de accountgegevens in die zijn opgegeven voor de **[!UICONTROL Production environment]**. Alle velden zijn verplicht.

1. Selecteren **[!UICONTROL Save Config]**.

1. De verbinding testen door **[!UICONTROL Validate Credentials]**.

>[!NOTE]
>
>Als de geloofsbrieven ongeldig zijn, verifieer dat u de correcte waarden voor elke milieu inging en revalidate. Neem contact op met uw accountvertegenwoordiger als er nog steeds verbindingsproblemen zijn.
