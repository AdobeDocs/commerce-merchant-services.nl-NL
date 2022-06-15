---
title: Gebruikersinstelling
description: 'Uitgebreide Inventory management-bronnen instellen als winkels ter ondersteuning van de oplossing Winkelafhandeling voor Adobe Commerce. '
role: User, Admin
level: Intermediate
source-git-commit: 42b0118b427b1e04186793b4a57c058bc1cabdd4
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---


# Gebruikersinstelling

App-gebruikers voor winkelassistentie worden beheerd in Adobe Commerce. Deze gebruikers communiceren echter niet rechtstreeks met Adobe Commerce. Het gebruikersbeheer is geconfigureerd in Adobe Commerce om veilige verbindingen tussen Adobe Commerce en de app mogelijk te maken.

Het gebruikersmodel van de App van de Afhandeling van de Opslag wordt gescheiden van andere gebruikersmodellen van Adobe Commerce. De toepassing behoudt zijn eigen machtigingsmodel via gebruikersrollen en gebruikers die aan alle of specifieke locaties kunnen worden toegewezen. De volgende machtigingen worden ondersteund: De orde van het schoppen, Verzendvolgorde, en de vermindering van het Aantal van het Punt (en annulering).

>[!TIP]
>
>Voor de beste resultaten: [configureren, verbinding](connect-set-up-service.md) voordat u gebruikers en machtigingen toevoegt voor Store Associates die de app Store Assist gebruiken.

## Store Assist App - Gebruikersrollen

Tijdens de eerste gebruikersinstelling voor de app Winkelassistentie maakt u gebruikersrollen om gebruikersmachtigingen aan te passen aan de app Winkelassistentie. Bijvoorbeeld, kunt u verschillende rollen voor opslagmanagers en opslagvennoten tot stand brengen en verschillende rolmiddelen toewijzen om toestemmingen voor elk type van gebruiker te beheren.

Gebruikersrollen configureren vanuit **[!UICONTROL System > Store Fulfillment App Permissions > All Store Fulfillment App Users]**.

### Rolinformatie

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|----------------------------|-------------------------|-----------|--------------|
| **[!UICONTROL Role Name]** | Schakel de gebruiker in of uit. | Algemeen | Ja |

### Rolresources

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Resource Access]** | Maak een lijst van de beschikbare toestemmingsgroepen die aan een gebruikersrol kunnen worden toegewezen. Op dit ogenblik, heeft de Oplossing van de Afhandeling van de Opslag geen verschillende toestemmingsniveaus die voor middelrollen worden bepaald. Alle gebruikersrollen hebben de zelfde middeltoegang. | Algemeen | Ja |

## Winkelassistentie - Gebruikersgegevens

Gebruikersprofielen voor toepassingen van Store Assist beheren vanuit de beheersysteeminstellingen:  **[!UICONTROL System > Store Fulfillment App Permissions > All Store Fulfillment App Users]**.

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL is Active]** | Schakel de gebruiker in of uit. | Algemeen | Ja |
| **[!UICONTROL User Name]** | Gebruikersnaam gekoppeld aan gebruiker | Algemeen | Ja |
| **[!UICONTROL First Name]** | Voornaam gekoppeld aan gebruiker | Algemeen | Nee |
| **[!UICONTROL Last Name]** | Achternaam die aan de gebruiker is gekoppeld | Algemeen | Nee |
| **[!UICONTROL Role]** | Rol die aan de gebruiker is gekoppeld | Algemeen | Nee |
| **[!UICONTROL Access to all locations]** | Wijs gebruikers toegang tot alle winkels toe of selecteer afzonderlijke winkels. | Algemeen | Nee |
| **Landinstelling interface** | Als uw winkel meerdere talen heeft, stelt u Interfacelocatie in op de taal die u wilt gebruiken voor de beheerinterface. | Algemeen | Nee |
| **Actief van** | Als u een begindatum wilt instellen, selecteert u het kalenderpictogram. | Algemeen | Nee |
| **Actief voor** | Stel de vervaldatum in door het kalenderpictogram te selecteren. Het instellen van een vervaldatum is handig als u tijdelijke gebruikers- of rolinwijzingen wilt instellen. Na de vervaldatum wordt de status van de gebruikersaccount gewijzigd in `Inactive`, maar de account kan zo nodig nog worden bijgewerkt. | Algemeen | Nee |
