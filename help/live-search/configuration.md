---
title: 'Commerce Configurations Settings'
description: Beschrijft de de configuratiemontages van Commerce die [!DNL Live Search] kan lezen.
exl-id: a4e9e2dd-e912-4ced-a44a-091ac5334e50
features: Services, Search, Configuration
source-git-commit: 4978bdb5549f5df911863a23fdfbfc9ab9ad05df
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Commerce-configuratie-instellingen

Er zijn Commerce-configuratie-instellingen die [!DNL Live Search] ondersteunt. In dit artikel worden deze configuratiewaarden weergegeven.

## Ondersteunde configuratiewaarden

| Commerce-configuratie-instelling | Ondersteund door Popover | Ondersteund door adapter |
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

| Commerce-configuratie-instelling | Notities |
|---|---|
| Storingen > Configuratie > Catalogus > Storefront > Lijstmodus | Rendering is correct, maar gebeurtenissen worden niet verzonden voor bepaalde paginainteracties |
| Winkels > Configuratie > Catalogus > Catalogus > Cataloguszoekopdracht > Maximale lengte query | Niet geïmplementeerd; zoekservices accepteren maximaal 255 tekens |
| Configuration > Sales > Tax > Price Display Settings > Display Product Prices in Catalog |  |
| Winkels > Configuratie > Catalogus > Storefront > Productaanbieding sorteren op | Is niet van toepassing op [!DNL Live Search] [Widget pagina met productaanbiedingen](plp-styling.md) |
