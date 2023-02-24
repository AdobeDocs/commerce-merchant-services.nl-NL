---
title: App-instelling
description: Stel de [!DNL Store Assist] app voor het beheer van end-to-end workflows voor de afhandeling van winkels en processen voor het online kopen van orders.
role: User, Admin
level: Intermediate
exl-id: bcb5b02b-0141-407a-ad55-6e10e8e1aa90
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Setup van app

Store Assist is een afhandeling-als-dienst (FaaS) platform app aangedreven door de Technologieën van de Handel van de Marm. De app biedt in-store uitvoeringsmogelijkheden voor verwerking [!DNL buy online, pick up in store] (BOPIS) orders. Met de Hulp van de Opslag, kunnen de opslagvennoten zien welke punten klanten bestelde, de correcte punten sneller plukken, en opstelling vervulde orden voor de ophaallevering in-store of curbside aan klanten.

De app Store Assist ontvangt alle bestelling- en klantgegevens, van bestellingsgegevens tot ophaaltijden en stelt de gegevens beschikbaar voor het online opslaan van partners via mobiele apparaten. De app bevat [!UICONTROL Pick], [!UICONTROL Stage], [!UICONTROL Handoff], en [!UICONTROL Orders] modules om Winkelgeassocieerde leden te helpen bij het uitvoeren van bijvoorbeeld de volgende activiteiten:

- Wijs leveringsdatums en -tijden voor bestellingen toe.
- Ontvang meldingen van klanten wanneer ze aankomen voor het ophalen van bestellingen.
- Werkgebiedbestellingen voor overdracht aan klanten.
- De orderstatus van het spoor voor alle orden in hun toegewezen opslagplaatsen.

>[!NOTE]
>
>Zie [Workflows voor afhandeling van winkelassistentie](store-assist-modules.md) voor meer informatie over de app Winkelassistentie.

## De app Store Assist configureren

Voor de app Store Assist zijn twee soorten configuraties vereist:

- Adobe Commerce Admin-systeeminstellingen naar [gebruikersaccounts beheren, gebruikersrollen, bronmachtigingen](user-setup.md), en [het maken en modelleren van selecties van auto&#39;s die tijdens het inchecken beschikbaar zijn voor klanten](check-in-experience-setup.md).

- De configuratie-instellingen aan de voorzijde om de interface van de app Store Assist en andere instellingen aan te passen, zoals:

   - **De app Winkelassistentie plaatsen**—Pas de gebruikersinterface van de app aan met het bedrijfslogo en de kleuren.

   - **De standaardinstructies bijwerken**—Pas de instructies in de modules Winkel bijstaan bij keuze, Werkgebied, Afhandeling en Volgorde aan om Winkelgeassocieerde leden door elke stap van de uitvoeringsworkflow voor uw bedrijf te begeleiden.

   - **Lokalisatie**—Selecteer de beschikbare taal voor de app. Kies de datum- en tijdnotatie en selecteer de standaardmaateenheden en de standaardvaluta.

   - **Inactiviteitstijd**—Geef op hoeveel tijd de toepassing inactief moet zijn voordat deze zich afmeldt.

   - **Annulering uit de winkel**—Specificeer of de orden van de opslag kunnen worden geannuleerd en welke rollen annuleringstoestemmingen hebben

   - **Opschonen van bestellingen, venster**—Opgeven hoe lang het verleden is [Geschatte levertijd voor afhalen](enable-general.md#delivery-method-title-configuration) dat een geplakte order in ophaling alvorens wordt herbevolkt-bijvoorbeeld, drie dagen blijft. De standaardwaarde is zeven dagen. Als deze configuratie is ingeschakeld, wordt de volgorde automatisch geannuleerd wanneer deze tijd verloopt. De items worden opnieuw opgeslagen en de verkoper ontvangt een annuleringsbericht.

   - Alles aanpassen in app-instructies (kiezen, opvoeren, afleveren).

   - **Pictogrammen**—Specificeer of om een duw bericht te verzenden om het plukken proces te beginnen nadat een klant een orde plaatst.

   - **Meldingen inchecken**—Geef op of u een pushmelding wilt verzenden tijdens het inchecken van bestellingen- na inchecken, nadat de wachttijd van de klant een bepaalde periode overschrijdt. Of schakel de melding uit.

   - **Handje uit-proces**—Schakel optionele processen in wanneer Store Associate bestelling aan de klant levert, bijvoorbeeld een handtekening van de klant vereisen of de koppeling vragen om de klant-id te controleren.

   - **Afkeuring van item inschakelen bij afbreken**—Toestaan dat klanten bestellingen retourneren of annuleren tijdens het afhandelen van bestellingen.
   Het werk met het team van de Diensten van de Cliënt van de Technologieën van de Handel van de Handel van de Mara om frontend configuratie voor de Hulp App van de Winkel te voltooien.

## Downloaden en installeren van apps

Nadat de app Store Assist is ingesteld en geconfigureerd, kunnen Store Associates vanaf hun mobiele apparaten de app Store Assist downloaden, installeren en aanmelden bij de app Store Assist.

- Controleren of het mobiele apparaat voldoet aan de [hardware- en softwarevereisten](solution-requirements.md#store-assist-app-requirements) voor de Oplossing van de Behandeling van de Opslag.

- Download de app Store Assist vanuit de [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id1609281539){target="_blank"} or the [Google Play store](https://play.google.com/store/apps/details?id=com.walmart.faas.storeassist){target="_blank"}.

- Voor het aanmelden bij Store Associates is de volgende informatie vereist:

   - **[!UICONTROL Company name]** gekoppeld aan de account Winkelassistentie

   - **Accountgegevens voor Winkelassistentie**—gebruikersnaam en wachtwoord voor hun account.
   Een Adobe Commerce-beheerder kan [!DNL Store Assist app] gebruikersaccounts voor alle opslaglocaties die [Ophalen in winkel](merchant-store-configuration.md#pickup-location-configuration) ingeschakeld in de beheerinstellingen voor winkels.
