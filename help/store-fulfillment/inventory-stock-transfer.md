---
title: Inventory management-bronoverdracht
description: "Configureer bestanden voor de [!DNL Store Fulfillment solution] met Adobe Commerce Inventory management. Stel een nieuwe voorraad- en overdrachtvoorraad in op basis van de standaardvoorraad, zodat u deze kunt toewijzen aan bronnen die zijn geconfigureerd om de opslagcapaciteit die door de oplossing Afhandeling van winkel wordt vereist, in te schakelen."
role: User, Admin
level: Intermediate
exl-id: 669d4dce-4cac-4bde-acc5-26c70a51f7f1
source-git-commit: e7493618e00e28e2de5043ae2d7e05a81110d8f1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---


# Inventory management-bronoverdracht

De [!DNL Store Fulfillment] -oplossing gebruikt native Adobe Commerce Inventory management. Standaard worden de [!DNL Commerce] De configuratie wijst al Webinventaris aan het standaarddossier toe, dat geen extra toegewezen bronnen kan hebben. Omdat aan een website slechts één voorraad kan worden toegewezen, moet een handelaar een nieuwe voorraad vormen en naar keuze hun standaardbroninventaris overbrengen naar een bron die aan het aangewezen werkingsgebied wordt toegewezen. Vervolgens kan de bron worden toegewezen aan het nieuwe bestand.

>[!IMPORTANT]
>
>Handelaars moeten de standaardbron voor alle producten handhaven inbegrepen in groep en bundelproducttypes. Deze producten hebben een inventarishoeveelheid nodig die voldoet aan de minimumdrempel voor hoeveelheden in voorraad en die een voorraadstatus bevat van [!UICONTROL In Stock].

Deze configuratieveranderingen helpen u drie dingen verwezenlijken:

1. [Inventarisatie naar bron overbrengen](https://docs.magento.com/user-guide/catalog/inventory-bulk-transfer-inventory.html) om de voorraad te verplaatsen van de standaardvoorraad/bron naar de nieuwe voorraad/bron.

1. [Bronnen toewijzen met een lamp](https://docs.magento.com/user-guide/catalog/inventory-bulk-assign-sources.html) om de nieuwe bronnen voor al uw producten toe te voegen.

1. [Volledige bulkupdates voor productkenmerken](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html) om de `Allow Store Pickup` en `Allow Home Delivery` kenmerken van bestaande producten. Wanneer de oplossing wordt geïnstalleerd, hebben de attributen het optimale *default* waarden. Deze kenmerken worden echter pas op bestaande producten toegepast als u het bulkupdateproces hebt voltooid.

De voorraad wordt afgetrokken van de geselecteerde bron (detailhandel of e-commerce-entrepot). De bronnen die als e-commerce pakhuizen worden gebruikt moeten aan het zelfde dossier worden toegewezen zoals de opslagbestelplaats en voorrang gegeven vóór de detailhandelsplaatsen. Zie voor meer informatie [Prioritaire bronnen voor een bestand](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html).

Raadpleeg de gebruikersdocumentatie van Adobe Commerce voor meer informatie over het beheer van voorraden, voorraden en bronnen:

- [Inventaris beheren](https://docs.magento.com/user-guide/catalog/inventory-management.html)

- [Aantal voorraden beheren](https://docs.magento.com/user-guide/catalog/inventory-manage-inventory-quantities.html)

- [Beheren van voorraden](https://docs.magento.com/user-guide/catalog/inventory-stock.html)

- [Bronnen beheren](https://docs.magento.com/user-guide/catalog/inventory-sources.html)

- [Prioritaire bronnen voor een bestand](https://docs.magento.com/user-guide/catalog/inventory-stock-priority.html)

- [Bulkupdates voor productkenmerken](https://docs.magento.com/user-guide/stores/bulk-product-attribute-update.html)


>[!IMPORTANT]
>
>Het wijzigen van de configuratie voor inventarisatie en voorraadbronnen kan ook downstreamgevolgen hebben voor geïntegreerde systemen. Zorg ervoor dat u begrijpt hoe de wijzigingen in de configuratie van de inventaris deze systemen beïnvloeden.
