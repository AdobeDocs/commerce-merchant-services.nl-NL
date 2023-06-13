---
title: '"Commerce Configurations Settings en [!DNL Live Search] '''
description: Beschrijft de de configuratiemontages van Adobe Commerce die [!DNL Live Search] kan lezen.
exl-id: a4e9e2dd-e912-4ced-a44a-091ac5334e50
source-git-commit: c8303b11c7a274a3956a7336203aa34bd9d6a67f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# [!DNL Live Search] en Adobe Commerce-configuratie-instellingen

Er zijn de configuratiemontages van de Handel die [!DNL Live Search] ondersteunt. Dit onderwerp maakt een lijst van deze configuratiewaarden.

## Ondersteunde configuratiewaarden

| Configuratie-instelling voor handel | Ondersteund door Popover | Ondersteund door adapter |
|---|---|---|
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Alle producten per paginalengte toestaan | Ja. Maximaal 500 producten | Ja. Maximaal 500 producten |
| Opslag > Configuratie > Catalogus > Catalogus > Catalogus Onderzoek > Minimale Lengte van de Vraag | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op toegestane rasterwaarden | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op standaardrasterwaarde | Ja | Ja |
| Winkels > Configuratie > Catalogus > Inventaris > Producten uit voorraad weergeven | Ja met v2.0.4+ | Ja met v2.0.4+ |
| Stores > Configuration > Currency > Default Display Currency | Ja met 3.1.0+ | Ja met 3/1/0+ |
| Storingen > Configuratie > Algemeen > Valuta-instelling > Valuta-opties > Basisvaluta | Ja | Ja |

Prijzen in de aanbiedingspagina van het widgetproduct en in de pop-up worden nu geconverteerd naar de standaardweergavemunt met de geconfigureerde valutakoersen

## Niet-ondersteunde configuratiewaarden

[!DNL Live Search] kan niet alle configuratiewaarden lezen. Deze tabel bevat een lijst met waarden die ontwikkelaars wellicht interessanter vinden.

| Configuratie-instelling voor handel | Notities |
|---|---|
| Storingen > Configuratie > Catalogus > Storefront > Lijstmodus | Rendering is correct, maar gebeurtenissen worden niet verzonden voor bepaalde paginainteracties |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Maximale lengte query | Niet geïmplementeerd; Zoekservices accepteert maximaal 255 tekens |
| Configuration > Sales > Tax > Price Display Settings > Display Product Prices in Catalog |  |
