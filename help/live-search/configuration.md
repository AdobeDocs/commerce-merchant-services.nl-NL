---
title: "Commerce Configurations Settings en [!DNL Live Search] "
description: "Beschrijft de de configuratiemontages van Adobe Commerce die [!DNL Live Search] kan lezen."
source-git-commit: 10edbb6127405d45c06d4c8ffc89d92a6ca061c3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# [!DNL Live Search] en Adobe Commerce-configuratie-instellingen

Er zijn de configuratiemontages van de Handel die [!DNL Live Search] ondersteunt. Dit onderwerp maakt een lijst van deze configuratiewaarden.

## Ondersteunde configuratiewaarden

| Configuratie-instelling voor handel | Ondersteund door Popover | Ondersteund door adapter |
|---|---|---|
| Opslagruimten -> Configuratie -> Catalogus -> Catalogus -> Catalogus zoeken -> Minimale vraaglengte | Ja | Ja |
| Winkels -> Configuratie -> Catalogus -> Inventaris -> Weergave van producten uit voorraad | Ja met v2.0.4+ | Ja met v2.0.4+ |
| Winkels -> Configuratie -> Algemeen -> Valuta-instelling -> Valuta-opties -> Basisvaluta | Ja | Ja |

## Niet-ondersteunde configuratiewaarden

[!DNL Live Search] kan niet alle configuratiewaarden lezen. Deze tabel bevat een lijst met waarden die ontwikkelaars wellicht interessanter vinden.

| Magento configuratie-instelling | Notities |
|---|---|
| Winkels -> Configuratie -> Catalogus -> Storefront -> Lijstmodus | Rendering is correct, maar gebeurtenissen worden niet verzonden voor bepaalde paginainteracties |
| Winkels -> Configuratie -> Catalogus -> Storefront -> Alle producten per pagina toestaan | Niet geïmplementeerd; een aanvraag indienen bij de zoekservice zonder paginagrootte en [!DNL Live Search] retourneert een standaardpaginaformaat van 20 |
| Opslagruimten -> Configuratie -> Catalogus -> Catalogus -> Cataloguszoekopdracht -> Maximale lengte van query | Niet geïmplementeerd; Zoekservices accepteert maximaal 255 tekens |
| Opslagruimten -> Configuratie -> Algemeen -> Valuta-instelling -> Valuta-opties -> Standaardvaluta | Niet geïmplementeerd; [!DNL Live Search] alleen toegang heeft tot de basisvaluta |
| Configuratie -> Verkoop -> Belastingen -> Instellingen voor prijsweergave -> Prijzen van producten weergeven in catalogus |  |
