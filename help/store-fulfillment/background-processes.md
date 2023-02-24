---
title: Configuratie achtergrondproces
description: "Vorm de programma's voor [!DNL Store Fulfillment] achtergrondprocessen die worden gebruikt voor het synchroniseren van gegevens met de uitvoeringsservices."
role: User, Admin
level: Intermediate
exl-id: 742ae59e-77a0-4db6-b156-2992d4403be7
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Configuratie achtergrondproces

De integratie van de Afhandeling van de Opslag gebruikt achtergrondprocessen en berichtrijen voor optimale prestaties en schaal. Bouw milieu&#39;s voor uw opslag van Adobe Commerce gebruikend [implementatievariabelen](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner) automatisch starten [wachtrij met berichten](https://devdocs.magento.com/guides/v2.4/config-guide/mq/rabbitmq-overview.html).

Achtergrondprocessen worden beheerd met de standaard Adobe Commerce [Geplande taken](https://docs.magento.com/user-guide/system/cron.html) functionaliteit. Deze processen zijn de oorzaak van het synchroniseren van orde en de handelaarconfiguratiegegevens met de Webdiensten van de opslagvervulling.

## Geplande taken beheren voor winkeluitvoering

Ga vanuit de beheerder naar **[!UICONTROL Stores > Configuration > Advanced > System > Cron (Scheduled Tasks) > Cron configuration options for group:store_fulfillment]**.

Controleer de standaardconfiguratie voor de diensten van de Afhandeling van de Opslag. Afhankelijk van het volume van uw ordeverwerking en de beschikbaarheid van bronnen, zou u deze montages kunnen moeten aanpassen.
