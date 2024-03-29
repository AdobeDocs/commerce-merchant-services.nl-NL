---
title: '"Commerce Configurations Settings en [!DNL Live Search] '''
description: Beschrijft de de configuratiemontages van Adobe Commerce die [!DNL Live Search] kan lezen.
exl-id: a4e9e2dd-e912-4ced-a44a-091ac5334e50
features: Services, Search, Configuration
source-git-commit: 888b81683a4e139a35b771d9c573f1f5f0c3b902
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# [!DNL Live Search] en Adobe Commerce Configuration Settings

Er zijn de configuratiemontages van de Handel die [!DNL Live Search] ondersteunt. Dit onderwerp maakt een lijst van deze configuratiewaarden.

## Ondersteunde configuratiewaarden

| Configuratie-instelling voor handel | Ondersteund door Popover | Ondersteund door adapter |
|---|---|---|
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Alle producten per paginalengte toestaan | Ja. Maximaal 500 producten | Ja. Maximaal 500 producten |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Minimale lengte query | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op toegestane rasterwaarden | Ja | Ja |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Producten per pagina op standaardrasterwaarde | Ja. Maximaal 500 producten | Ja. Maximaal 500 producten |
| Winkels > Configuratie > Catalogus > Inventaris > Producten uit voorraad weergeven | Ja met v2.0.4+ | Ja met v2.0.4+ |
| Stores > Configuration > Currency > Default Display Currency | Ja met 3.1.0+ | Ja met 3.1.0+ |
| Storingen > Configuratie > Algemeen > Valuta-instelling > Valuta-opties > Basisvaluta | Ja | Ja |

Prijzen in de aanbiedingspagina van het widgetproduct en in de pop-up worden nu geconverteerd naar de standaardweergavemunt met behulp van de geconfigureerde valutakoersen.

## Zoektermen

[!DNL Live Search] supports [heroriëntering van zoektermen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/catalog/search/search-terms.html) op implementaties waar Adobe Commerce het verpletteren behandelt: Luma en andere op php-Gebaseerde thema&#39;s.

## Niet-ondersteunde configuratiewaarden

[!DNL Live Search] kan niet alle configuratiewaarden lezen. Deze tabel bevat een lijst met waarden die ontwikkelaars wellicht interessanter vinden.

| Configuratie-instelling voor handel | Notities |
|---|---|
| Storingen > Configuratie > Catalogus > Storefront > Lijstmodus | Rendering is correct, maar gebeurtenissen worden niet verzonden voor bepaalde paginainteracties |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Maximale lengte query | Niet geïmplementeerd; zoekservices accepteren maximaal 255 tekens |
| Configuration > Sales > Tax > Price Display Settings > Display Product Prices in Catalog |  |
