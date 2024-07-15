---
title: Configuratie achtergrondproces
description: "Vorm de programma's voor  [!DNL Store Fulfillment]  achtergrondprocessen die in het synchroniseren van gegevens met de uitvoeringsdiensten worden gebruikt."
role: Admin, Developer
level: Intermediate
exl-id: 742ae59e-77a0-4db6-b156-2992d4403be7
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 0%

---


# Configuratie achtergrondproces

De integratie van de Afhandeling van de Opslag gebruikt achtergrondprocessen en berichtrijen voor optimale prestaties en schaal. Bouw milieu&#39;s voor uw opslag van Adobe Commerce gebruikend [ plaatsingsvariabelen ](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner) die [ de looppas van de berichtrij ](https://devdocs.magento.com/guides/v2.4/config-guide/mq/rabbitmq-overview.html) automatisch beginnen.

De processen van de achtergrond worden beheerd gebruikend de standaardAdobe Commerce [ Geplande functionaliteit van Taken ](https://docs.magento.com/user-guide/system/cron.html). Deze processen zijn de oorzaak van het synchroniseren van orde en de handelaarconfiguratiegegevens met de Webdiensten van de opslagvervulling.

## Geplande taken beheren voor het uitvoeren van een winkel

Ga vanuit Beheer naar **[!UICONTROL Stores > Configuration > Advanced > System > Cron (Scheduled Tasks) > Cron configuration options for group:store_fulfillment]** .

Controleer de standaardconfiguratie voor de diensten van de Afhandeling van de Opslag. U kunt deze instellingen aanpassen op basis van het verwerkingsvolume van uw bestelling en de beschikbaarheid van bronnen.
