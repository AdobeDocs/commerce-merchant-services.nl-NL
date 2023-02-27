---
title: Onboarding
description: Leer de vereisten en ondersteunde platforms op [!DNL Product Recommendations].
exl-id: ad47ac39-8f6f-4765-84ad-9e3d104385db
source-git-commit: d56fd57281a5b675e128cca75d4057756a0bf4bf
workflow-type: tm+mt
source-wordcount: '0'
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

- Adobe Commerce 2.3.x, 2.4.x
- PHP 7.3 / 7.4 / 8.1
- Composer

### Ondersteunde platforms

- Adobe Commerce on-premise (EE) : 2,4 x
- Adobe Commerce on Cloud (ECE) : 2,4 x

### Ondersteuning voor Page Builder

[!DNL Product Recommendations] kan aan een pagina worden toegevoegd als een inhoudstype van de Bouwer van de Pagina. Als u ondersteuning voor Page Builder wilt toevoegen aan Product Recommendations, raadpleegt u [Installeren en configureren](install-configure.md).

Zie [[!DNL Page Builder] Integratie](page-builder.md) voor instructies over het toevoegen van [!DNL Product Recommendations] in [!DNL Page Builder] inhoud.

### B2B-ondersteuning {#b2bsupport}

B2B-winkels vereisen vaak complexe logica die de zichtbaarheid en prijsstelling van het product voor elke winkel of klantengroep bepaalt. [!DNL Product Recommendations] now [ondersteuning](release-notes.md) deze functionaliteit door [categorietoestemmingen](https://experienceleague.adobe.com/docs/commerce-admin/catalog/categories/category-permissions.html), [gedeelde catalogi](https://experienceleague.adobe.com/docs/commerce-admin/b2b/shared-catalogs/catalog-shared.html), en [klantspecifieke prijsstelling](https://experienceleague.adobe.com/docs/commerce-admin/catalog/products/pricing/pricing-advanced.html). Bijvoorbeeld, als u bepaalde categorieën van uw retailklantensegment hebt verborgen, dan zou een verkoopster in dat segment geen aanbevelingen voor producten in die categorieën worden getoond. Ook, wanneer u een gedeelde catalogus voor specifieke klantengroepen en bedrijven bepaalt, zien die kopers aanbevelingen slechts voor producten zij kunnen toegang hebben. Alle geadviseerde producten weerspiegelen correcte klant groep-specifieke prijs die op de klantengroep van elke klant wordt gebaseerd.
