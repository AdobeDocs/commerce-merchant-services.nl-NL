---
title: "[!DNL SaaS Data Export Guide]"
description: "Meer informatie over het gebruik van de [!DNL data export] extensie voor Adobe Commerce SaaS-services waarmee gegevens worden gesynchroniseerd tussen Adobe Commerce en verbonden Commerce-services."
role: Admin, Developer
recommendations: noCatalog
source-git-commit: 8230756c203cb2b4bdb4949f116c398fcaab84ff
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# [!DNL SaaS Data Export] Handleiding

[!DNL SaaS data export] verbetert de prestaties vooraf door de gegevenssynchronisatie tussen een Adobe Commerce-instantie en aangesloten Commerce Services te optimaliseren. Wanneer u Live Search, Product Recommendations of de Catalogusservice toevoegt aan een Adobe Commerce-installatie, kunt u de [!DNL Data export] wordt automatisch geïnstalleerd.

Met de SaaS-gegevens worden diverse soorten gegevens verzameld en geëxporteerd, ook wel _feeds_, die specifieke soorten informatie bijeenvoegen. Afhankelijk van welke Commerce-services worden geïnstalleerd, bevat de SaaS-gegevensexportfeed het volgende:

- **feeds van catalogusentiteiten** samengestelde productgegevens. Gegevens omvatten producten, productkenmerken, productprijzen, productvariaties, categorieën, categorietoestemmingen en productmachtigingen.
- De **Scopes feed** aggregeert gegevens voor klantengroepen, websites, opslag, en opslagmeningen.
- De **Verkooporderfeed** aggregeert ordergegevens met inbegrip van hun verbonden entiteiten zoals facturen, overbrengingen, creditnota&#39;s, etc.
- De **Multi-Source Inventory feed** aggregaten gegevens over voorraadstatusposten.

De extensie voor het exporteren van gegevens ondersteunt verschillende methoden voor het initiëren en beheren van het proces voor gegevenssynchronisatie.

- **Handmatige synchronisatie van de beheerder of de opdrachtregel**

   - De [Gegevensbeheerdashboard](https://experienceleague.adobe.com/en/docs/commerce-admin/systems/data-transfer/data-dashboard) in Commerce Admin geeft u een grafische weergave van de synchronisatiestatus. U kunt het dashboard gebruiken om volledige resynchronisatie uit te voeren (_volledige synchronisatie_) van alle feeds. Adobe raadt echter aan om alleen volledige synchronisatie uit te voeren wanneer u Adobe Commerce voor de eerste keer verbindt met een Commerce-service. Zie [Synchronisatieproces](data-synchronization.md).

   - De [Adobe Commerce-opdrachtregelprogramma](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/config-cli) (CLI) bevat opdrachten waarmee u specifieke feeds kunt synchroniseren en aanvullende opties waarmee u de verwerking van feed kunt aanpassen.

- **Geautomatiseerde synchronisatie met uitsnijdtaken**

   - [Gedeeltelijke gegevenssynchronisatie](data-synchronization.md#partial-synchronization-with-cron-jobs)—Cron-taken activeren een gedeeltelijke gegevenssynchronisatie wanneer een Commerce-gebruiker een entiteit bijwerkt. Tijdens het exporteren van gegevens worden alleen deze updates naar verbonden Commerce-services verzonden. Het partiële synchronisatieproces is gebaseerd op het MView-mechanisme en vereist geen acties van de Admin-gebruiker of systeemintegrator.

   - [Automatisch opnieuw proberen voor synchronisatiefouten](data-synchronization.md#failed-items-sync-for-error-recovery)—Cron-taken activeren het automatisch opnieuw proberen van het synchronisatieproces wanneer fouten optreden tijdens het synchronisatieproces van gegevens.

- **Planning en prestaties exporteren**

   - Ontwikkelaars en systeemintegrators kunnen een schatting maken van de tijd die nodig is voor het exporteren van SaaS-gegevens om gegevens tussen Adobe Commerce en verbonden services te synchroniseren. Deze schatting kan helpen bij het plannen van gegevensexportverwerking om verstoring van de site te voorkomen. Zie [Gegevensvolume en verzendingstijd schatten](estimate-data-volume-sync-time.md).

   - In gevallen waarin de synchronisatie sneller moet verlopen, biedt SaaS-gegevensexport aanpassingsopties om de prestaties van de exportverwerking te verbeteren. Zie [Prestaties bij het exporteren van gegevens verbeteren](customize-export-processing.md).

- **De activiteiten van de gegevensuitvoer volgen en problemen oplossen**—Gebruik logboeken voor het exporteren van gegevens en voor het exporteren van bestanden om de synchronisatiestatus te controleren en de nuttige lading van de feed tijdens het synchronisatieproces en het indexatieproces te controleren. Zie [Logboekregistratie en probleemoplossing](troubleshooting-logging.md).



