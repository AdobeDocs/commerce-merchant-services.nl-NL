---
title: Onboarding-overzicht
description: '"Maak verbinding met uw [!DNL Commerce] aan de [!DNL Store Fulfillment Manager] door een paar instapstappen te voltooien."'
role: User, Admin
level: Intermediate
exl-id: f8e403ac-9bbd-4ea2-b209-9b1a8d1e32a2
source-git-commit: 26d0ddbcbe648b336d527788668caef1f8e688ed
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 1%

---

# Onboarding-overzicht

Aan boord van Store Fulfillment door de uitbreiding op uw instantie van de Handel te installeren en de API verbindingen te vormen. Deze verbindingen maken communicatie en gegevenssynchronisatie tussen uw instantie van de Handel, derdesystemen voor voorraadbeheer, en de App van de Hulp van de Opslag mogelijk.

Nadat u aan boord gaat, vorm en beheer de oplossing van Admin van de Handel

![[!DNL Store Fulfillment Service] configuratie in de beheerweergave](assets/store-fulfillment-admin-home.png)

## Onboarding-overzicht

1. Installeer de Store Fulfillment door de uitbreiding van de Technologieën van het Spoor voor Adobe Commerce.

1. Schakel de oplossing en de volledige algemene configuratie voor de integratie, de actieve functies en het inlaatformulier aan boord in vanuit de beheerfunctie om verbinding te maken met uitvoeringsservices.

1. Configureer de leveringsmethoden.

1. De bronnen van de opstelling als uw fysieke opslag en vormt producten in uw catalogus.

1. Selecteer en configureer de e-mailsjablonen voor het beheer van de communicatie van de klant voor het online aanschaffen van BOPIS-transacties.

1. Maak gebruikers en rollen voor de app Winkelassistentie.

1. Vorm de programma&#39;s voor achtergrondprocessen om gegevens aan de uitvoeringsdienst te synchroniseren.

## Vereisten

U moet aan de volgende vereisten voldoen om de oplossing te installeren, op te stellen en te gebruiken.

* **Informatie over handelsrekeningen**-Installeren [!DNL Channel Manager] vereist een [Handelsrekening](https://docs.magento.com/user-guide/magento/magento-account.html){target=&quot;_blank&quot;}. U hebt een account-id en gebruikersgegevens nodig met de toegang tot de [!DNL Adobe Commerce] -instantie.

* Voor [!DNL Adobe Commerce] bij cloudinfrastructuurprojecten moeten softwareinstallatieprogramma&#39;s beheerderstoegang tot het Cloud-project hebben. Zie [Gebruikerstoegang beheren](https://devdocs.magento.com/cloud/project/user-admin.html).

* **Toegang tot het archief Opslag van de Opslag door het softwarearchief van de Technologieën van Walmart (.zip- dossier) om de Oplossing van de Afhandeling van de Opslag te installeren**-Tijdens het instapproces en het inschakelen biedt uw vertegenwoordiger van uw klantenaccount downloadtoegang tot het installatiebestand.

* **Ervaring met Composer en de[!DNL Commerce CLI]**—Zie [Algemene installatie van CLI](https://devdocs.magento.com/extensions/install/){target=&quot;_blank&quot;} voor informatie over het gebruik van deze gereedschappen voor het installeren en beheren van extensies op [!DNL Adobe Commerce] en [!DNL Magento Open Source] platforms.

* [!DNL Inventory Management] extensie voor Adobe Commerce en Magento Open Source

   De Inventory management-extensie moet zijn geïnstalleerd en ingeschakeld op uw Adobe Commerce- en Magento Open Source-exemplaar. Deze extensie wordt standaard geïnstalleerd en ingeschakeld in Adobe Commerce 2.3.x en hoger. Zie voor meer informatie [Inventory management installeren](https://devdocs.magento.com/extensions/inventory-management/) in de documentatie van Adobe Commerce Developer.

## Platform- en versievereisten

De [!DNL Store Fulfillment] Adobe Commerce-klanten kunnen op de volgende platforms een oplossing kiezen.

* Adobe Commerce over wolkeninfrastructuur (ECE)
* Adobe Commerce in bedrijven (EE)

De oplossing van de Afhandeling van de Opslag is compatibel met de volgende softwareversies.

**Softwarecompatibiliteit**

| **Software** | **Minimumversie** | **Maximale versie** |
|----------------|---------------------|---------------------|
| Adobe Commerce | 2.4.0. | 2.4.4. |
| Composer | 1.x | 2.x |
| MariaDB | 10,2 | 10,4 |
| MySQL | 5,7 | 8,0 |
| PHP | 7,4 | 8,1 |

Raadpleeg de Adobe Commerce voor gedetailleerde vereisten [Systeemvereisten](https://devdocs.magento.com/guides/v2.4/install-gde/system-requirements.html) in de documentatie van de Ontwikkelaar.

### Bedrijfsvereisten

Uw bedrijf moet aan de volgende minimumcriteria voldoen om de oplossing van de Afhandeling van de Opslag uit te voeren.

* Alleen in de VS gevestigde ondernemingen

* B2C-detailhandelaren, CPG-fabrikanten die D2C verkopen of distributeurs die D2C verkopen of aan kleine bedrijven

* Ten minste één fysieke opslag of opslagplaats

* Je productvoorraad beheren met Inventory management for Adobe Commerce (was MSI)

* Vermogen om handelsvoorraden te synchroniseren

* Wi-Fi-beschikbaarheid opslaan op alle locaties die ondersteuning bieden voor de oplossing Afhandeling opslaan

* Associateurs van winkels en pakhuizen hebben toegang tot mobiele apparaten van iOS of Android tijdens hun verhuizing, persoonlijk of verstrekt door de handelaar

* Producten die door de oplossing van de Afhandeling van de Opslag worden beheerd moeten productattributen hebben die of SKU of UPC productcode omvatten
