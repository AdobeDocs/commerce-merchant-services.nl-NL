---
title: Onboarding
description: Leer de vereisten en ondersteunde platforms op [!DNL Product Recommendations].
exl-id: ad47ac39-8f6f-4765-84ad-9e3d104385db
source-git-commit: a90fcd8401b7745a65715f68efccdb3ce7c77ccb
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Onboarding

Het instapproces voor [!DNL Product Recommendations] vereist toegang tot de bevellijn van de server en bestaat uit de volgende stappen. Als u niet bekend bent met het werken vanaf de opdrachtregel, vraagt u een ontwikkelaar of systeemintegrator om hulp.

- [Implementatieworkflow](implementation-workflow.md)
- [Installeren en configureren](install-configure.md)
- [Instellingen](settings.md)
- [Verifiëren](verify.md)
- [Stationele omgeving](staging-environment.md)

## Vereisten

- Adobe Commerce 2.4.4+
- PHP 8.1, 8.2
- Composer 2

### Ondersteunde platforms

- Adobe Commerce on premise (EE) : 2.4.4+
- Adobe Commerce on Cloud (ECE) : 2.4.4+

## Endpoint

[!DNL Product Recommendations] communiceert door het eindpunt bij `https://catalog-service.adobe.io/graphql`.

### Ondersteuning voor Page Builder

[!DNL Product Recommendations] kan aan een pagina worden toegevoegd als een inhoudstype van de Bouwer van de Pagina. Als u ondersteuning voor Page Builder wilt toevoegen aan Product Recommendations, raadpleegt u [Installeren en configureren](install-configure.md).

Zie [[!DNL Page Builder] Integratie](page-builder.md) voor instructies over het toevoegen van [!DNL Product Recommendations] in [!DNL Page Builder] inhoud.

### Prijsindexering SaaS

Klanten die productaanbevelingen kunnen gebruiken [Prijsindexering SaaS](../price-index/price-indexing.md), die snellere updates van prijswijzigingen en synchronisatietijd biedt.

### B2B-ondersteuning {#b2bsupport}

B2B-winkels vereisen vaak complexe logica die de zichtbaarheid en prijsstelling van het product voor elke winkel of klantengroep bepaalt. [!DNL Product Recommendations] now [ondersteuning](release-notes.md) deze functionaliteit door [categoriemachtigingen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/category-permissions.html), [gedeelde catalogi](https://experienceleague.adobe.com/docs/commerce-admin/b2b/shared-catalogs/catalog-shared.html), en [klantspecifieke prijsstelling](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/pricing-advanced.html). Bijvoorbeeld, als u bepaalde categorieën van uw retailklantensegment hebt verborgen, dan zou een verkoopster in dat segment geen aanbevelingen voor producten in die categorieën worden getoond. Ook, wanneer u een gedeelde catalogus voor specifieke klantengroepen en bedrijven bepaalt, zien die kopers aanbevelingen slechts voor producten zij kunnen toegang hebben. Alle geadviseerde producten weerspiegelen correcte klant groep-specifieke prijs die op de klantengroep van elke klant wordt gebaseerd.

>[!NOTE]
>
>Handelaars kunnen widgets of winkelelementen aanpassen en uitbreiden met de [Catalogusservice](../catalog-service/overview.md) Storefront-API, maar elke aanpassing valt buiten het bereik van het ondersteuningsteam van de Adobe.
