---
title: Overzicht van de handleiding
description: Leer hoe u Adobe Commerce-gegevens met Adobe Experience Platform kunt integreren met de [!DNL Data Connection] extensie.
exl-id: a8362e71-e21c-4b1d-8e3f-336e748e1018
recommendations: noCatalog
source-git-commit: 99d1097b98ea18c8a317613b2366a97db131432f
workflow-type: tm+mt
source-wordcount: '1731'
ht-degree: 0%

---

# [!DNL Data Connection] Inleiding

>[!IMPORTANT]
>
>De naam van de Experience Platform-aansluiting is gewijzigd in [!DNL Data Connection].

De [!DNL Data Connection] -extensie maakt een verbinding tussen uw Adobe Commerce-webinstantie en de Adobe Experience Platform en Edge Network. Leer hoe u [integreren](./mobile-sdk-epc.md) de Adobe Experience Platform Mobile SDK met Commerce.

Je winkel van Koophandel bevat een schat aan gegevens. Informatie over hoe kopers door de producten op uw site kunnen bladeren, deze kunnen bekijken en uiteindelijk kopen, biedt mogelijkheden om een meer persoonlijke winkelervaring te creëren. Hoewel die gegevens inheemse eigenschappen van de Handel zoals de regels van de kartprijs en dynamische blokken kunnen informeren, blijven de gegevens in uw instantie van de Handel gesilogeerd.

De Adobe Experience Platform biedt een reeks technologieën die, wanneer ze zijn gehydrateerd met gegevens van uw Commerce Store, die gegevens via het Edge Network kunnen distribueren naar andere DX-producten van de Adobe om inzicht te krijgen in het aankoopgedrag van uw klant. Met deze diepgaande inzichten, kunt u een meer gepersonaliseerde het winkelen ervaring over alle kanalen tot stand brengen.

In de volgende afbeelding ziet u hoe uw gegevens van Commerce van uw winkel naar andere DX-producten van de Adobe stromen:

![De gegevensstroom naar de rand van het Experience Platform](assets/commerce-edge.png)

In de bovenstaande afbeelding worden uw gedrags-, back office- en klantprofielgegevens naar de rand van het Experience Platform verzonden met behulp van een SDK, API en een bronaansluiting. U hoeft niet volledig te begrijpen hoe deze onderdelen werken als de extensie de complexiteit voor het delen van gegevens voor u behandelt. Wanneer de gebeurtenisgegevens zich aan de rand bevinden, kunt u die gegevens in andere Experience Platforms toepassingen opnemen. Bijvoorbeeld:

| Toepassing | Doel | Gevallen gebruiken |
|---|---|---|
| [Adobe [!DNL Real-Time CDP]](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/rtcdp-intro/overview.html) | Profielbeheer en segmenteringsservice | **Segmentering koopgeschiedenis**: Merchants kunnen klanten identificeren die een item aanschaffen op basis van een specifieke tijdsperiode (maandelijks, driemaandelijks, jaarlijks, enzovoort). De handelaren kunnen segmenten voor deze klanten dan tot stand brengen en hen richten voor bevorderingen, campagnes, en zoals _bovenzijde van de trechter_ gegevens voor leads voor abonnementservices.<br> **Op categorieën gebaseerde segmentatie**: Merchants kunnen zien welke categorie producten is aangeschaft.<br> **Op aanbiedingen gebaseerde segmentatie**: Merchants kunnen klanten identificeren die consequent producten retourneren. De aanbiedingen en kortingen kunnen nu intelligenter zijn. De gratis verzending kan bijvoorbeeld worden verwijderd voor een klant die de producten de hele tijd retourneert.<br> **Lookaliasing**: A _Lookalike-publiek_ is een methodologie die door een handelaar wordt genomen voor hun bevorderingen om nieuwe mensen te bereiken die in hun zaken waarschijnlijk geïnteresseerd zullen zijn omdat zij gelijkaardige eigenschappen met uw bestaande klanten delen. De segmenten van de ookalike kunnen worden tot stand gebracht gebaseerd op gedrags en transactionele gegevens.<br> **Klantenbetrouwbaarheid**: Wijzigingen in klantengedrag kunnen worden geïdentificeerd als resultaat van de diepere klantenprofielen die op basis van de transactiegegevens kunnen worden gemaakt. Er zal meer vertrouwen zijn in de pensiteitsscore aangezien er meer gegevens in de berekeningen vloeien, zoals productteruggaven en productconfiguraties.<br> **Cross-sell**: Een handelaar kan sterke mogelijkheden voor cross-sell en up-sell identificeren aan de hand van de in het kader van de handel vastgelegde informatie in korrelvorm. |
| [Klant [!DNL Journey Analytics]](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) | Diepgaande analyse van de volledige reis van de Handel | **Seizoensgebonden trends**: Een handelaar kan seizoentrends vaststellen, waardoor hij zich kan voorbereiden op de periodieke verandering van de vraag naar bepaalde producten. Handelaren kunnen ook veranderingen in de algemene populariteit van elk product over jaren vaststellen.<br> **Conversieanalyse**: Door te weten wanneer een product werd gekocht, samen met toegang tot de gebeurtenissen van de storefront indruk, kunnen de handelaren een rijk profiel van de klant produceren om omzetanalyse uit te voeren. |
| [Adobe [!DNL Analytics]](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/analytics-overview.html) | Diepe analyse van het gedrag van de klant en de prestaties van de campagne | **Opdrachten**: Merchants kunnen klanten en de grotere klantensegmenten identificeren die een patroon van het terugkeren van producten hebben. Dit helpt de handelaren hun handelsstrategie verbeteren aangezien zij begrijpen hoe hun gedrag van de klantenbasis kijkt als.<br> **Opdrachtadres**: Op basis van het verzendadres kan een handelaar begrijpen of de orders door de klanten zelf worden geplaatst of dat het voor een andere persoon of entiteit is.<br> **Seizoensgebonden trends**: Een handelaar kan seizoentrends vaststellen, waardoor hij zich kan voorbereiden op de periodieke verandering van de vraag naar bepaalde producten. Handelaren kunnen ook veranderingen in de algemene populariteit van elk product over jaren vaststellen.<br> **Conversieanalyse**: Door te weten wanneer een product werd gekocht, samen met toegang tot de gebeurtenissen van de storefront indruk, kunnen de handelaren een rijk profiel van de klant produceren om omzetanalyse uit te voeren. **Opmerking** Adobe Analytics ondersteunt alleen gedragsgebeurtenisgegevens (storefront). Adobe Analytics biedt geen ondersteuning voor transactiegegevens (back-koffice). |
| [Adobe [!DNL Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) | Campagneorchestratie langs kanalen | **Op gedrag gebaseerde reizen**: Merchants kunnen zich richten op een klant die twee jaar geleden een mobiele telefoon heeft gekocht door te suggereren dat ze het nieuwe model aanschaffen. Handelaars kunnen persoonlijke campagnes en promoties voor deze klanten maken en de functionaliteit van e-mail en SMS gebruiken om te bereiken. Handelaren kunnen ook historische volgorde- en gedragsgegevens gebruiken om trends te identificeren. Een klant die bijvoorbeeld een product met een bepaalde configuratie in het verleden heeft gekocht en nu hetzelfde product opnieuw wil kopen, kan zijn aankoopreis verbeteren door de klant meer zichtbaarheid te geven en toegang te geven tot dezelfde productconfiguraties.<br> **Personalisatie**: Met toegang tot klantprofielinformatie, [!DNL Journey Optimizer] kunnen zeer gepersonaliseerde reizen ontgrendelen, zodat handelaren de klanten op verschillende kanalen kunnen bereiken.<br> **Nieuw profiel gemaakt**: Welkomste-mails en promotieactiviteiten kunnen nieuwe klanten stimuleren en beïnvloeden bij hun winkelreizen.<br> **Profiel verwijderd**: Merchants kunnen ervoor kiezen geen speciale e-mails meer te verzenden naar klanten die hun account hebben gesloten. De handelaren kunnen ook campagnes bouwen om verloren klanten terug te winnen. |

## Gegevens van Experience Platform terugbrengen in de handel

Verstuur uw gegevens van de Handel naar het Experience Platform gebruikend [!DNL Data Connection] de uitbreiding is één kant van de mogelijkheden van de Handel om gegevens te delen. De andere zijde, die een facultatieve uitbreiding is, wordt genoemd [Audience Activation](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html). Met deze extensie kunt u een publiek opbouwen in Real-Time CDP en dat publiek distribueren naar uw winkel voor Handel om de regels voor de winkelprijzen, verwante producten en dynamische blokken te informeren.

Op een hoog niveau, ziet de stroom van gegevens van uw opslag van de Handel aan het Experience Platform en terug door de uitbreiding van het Audience Activation als het volgende:

![[!DNL Data Connection] stroom](assets/data-connection.png)

Nadat u opstelling de verbinding tussen Handel aan Experience Platform en Experience Platform aan Handel, blijft de gegevens stromen. U hoeft niet opnieuw verbinding te maken, tenzij u dit moet doen door een upgrade.

## Concepten

Het delen van gegevens tussen deze twee systemen vereist dat u verschillende concepten begrijpt.

* **Gegevens** - De gegevens die met het Experience Platform worden gedeeld, zijn gegevens die worden verzameld van browsergebeurtenissen in uw winkelcentrum, back office-gebeurtenissen op de server en profielrecordgegevens. Storefront-gebeurtenissen worden vastgelegd op basis van de interactie van klanten op de site en bevatten gebeurtenissen zoals [`addToCart`](events.md#addtocart), [`pageView`](events.md#pageview), [`createAccount`](events.md#createaccount), [`editAccount`](events.md#editaccount), [`startCheckout`](events.md#startcheckout), [`completeCheckout`](events.md#completecheckout), [`signIn`](events.md#signin), [`signOut`](events.md#signout), enzovoort. Zie [storefront, gebeurtenissen](events.md#storefront-events) voor de volledige lijst van storefront-gebeurtenissen. Server-kant, of achterkantoorgebeurtenissen, omvatten [orderstatus](events-backoffice.md#order-status) informatie, zoals [`orderPlaced`](events-backoffice.md#orderplaced), [`orderReturned`](events-backoffice.md#orderitemreturncompleted), [`orderShipped`](events-backoffice.md#ordershipmentcompleted), [`orderCancelled`](events-backoffice.md#ordercancelled), enzovoort. Zie [back office-gebeurtenissen](events-backoffice.md) voor de volledige lijst van achterkantoorgebeurtenissen. Profielrecordgegevens bevatten informatie wanneer een nieuw profiel wordt gemaakt, bijgewerkt of verwijderd. Zie [profielrecordgegevens](events-profilerecord.md) voor meer informatie.

* **Experience Platform en Edge Network** - Het gegevenspakhuis voor de meeste Adobe DX producten. De gegevens die naar het Experience Platform worden verzonden worden dan verspreid aan de Adobe DX producten door het Netwerk van de Rand van het Experience Platform. U kunt bijvoorbeeld Journey Optimizer starten, de gegevens van uw specifieke Commerce-gebeurtenis van de rand ophalen en een verlaten e-mailbericht over winkelwagentjes maken in Journey Optimizer. Journey Optimizer kan die e-mail vervolgens verzenden als er in je winkel voor Handel winkels geen winkelwagentjes zijn opgegeven. Meer informatie over de [Experience Platform en Edge Network](https://experienceleague.adobe.com/docs/platform-learn/data-collection/web-sdk/overview.html).

* **Schema** - Het schema is wat de structuur beschrijft van de gegevens die worden verzonden. Alvorens het Experience Platform uw gegevens van de Handel kan opnemen, moet u een schema samenstellen om de gegevensstructuur te beschrijven en beperkingen te verstrekken aan het type van gegevens dat binnen elk gebied kan worden bevat. De schema&#39;s bestaan uit een basisklasse en nul of meer groepen van het schemagebied. Het schema gebruikt de XDM-structuur, die alle Adobe DX-producten kunnen lezen. Dus wanneer u uw gegevens naar het Experience Platform verzendt, kunt u er zeker van zijn dat uw gegevens worden begrepen in alle DX-producten. Meer informatie over [schema&#39;s](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

* **Gegevensset** - Een opslag- en beheerconstructie voor een verzameling gegevens, doorgaans een tabel die een schema (kolommen) en velden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan. Alle gegevens die met succes in Adobe Experience Platform worden opgenomen, bevinden zich in gegevenssets. Meer informatie over [gegevenssets](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html).

* **DataStream** - ID waarmee gegevens van Adobe Experience Platform naar andere Adobe DX-producten kunnen stromen. Deze id moet zijn gekoppeld aan een specifieke website in uw specifieke Adobe Commerce-exemplaar. Wanneer u deze gegevensstroom creeert, specificeer het XDM schema u hierboven creeerde. Meer informatie over [datastreams](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html).

## Ondersteunde architectuur

De [!DNL Data Connection] de extensie is beschikbaar op de volgende architecturen :

* PHP/Luma
* [PWA Studio](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/)
* [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html)

## Vereisten

Als u de opdracht [!DNL Data Connection] extensie hebt, moet u het volgende hebben:

* Adobe Commerce 2.4.4 of hoger
* Adobe ID- en organisatie-id
* [Adobe Client Data Layer (ACDL)](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/client-data-layer/overview.html), die vereist is voor het verzamelen van storefront-gebeurtenisgegevens
* Rechten op andere Adobe DX-producten.

## Stappen aan boord

Op een hoog niveau [!DNL Data Connection] de extensie omvat de volgende stappen:

1. [Installeren](install.md) de [!DNL Data Connection] extensie.
1. [Aanmelden](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) op uw Adobe account en [bevestiging bekijken](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) uw organisatie-id. De organisatie-id is de id die is gekoppeld aan uw bedrijf voor het geleverde Experience Cloud. Deze id bestaat uit een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet worden opgenomen) `@AdobeOrg`.
1. Zorg ervoor dat u [toestemming voor gegevensverzameling in Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html).
1. Controleer de [gegevenstypen](data-ingestion.md) u kunt verzamelen en verzenden.
1. Maak uw [gebeurtenisschema tijdreeks](update-xdm.md) of [schema voor profielrecordgegevens](profile-data.md) met specifieke handelsgroepen.
1. [Een gegevensset maken](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) gebaseerd op het schema dat u hebt gemaakt of bijgewerkt. Deze dataset bevat de gegevens van de Handel die naar de Rand van het Experience Platform worden verzonden.
1. [Een gegevensstroom maken](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) en selecteer het XDM-schema dat de handel-specifieke gebiedsgroepen bevat.
1. [Verbinden met de Diensten van de Handel](../landing/saas.md).
1. [Verbinding maken met Adobe Experience Platform](connect-data.md).

De rest van deze gids begeleidt u meer in detail door al deze stappen zodat kunt u aan snelheid krijgen en beginnen gebruikend de macht van de producten van Adobe DX in uw opslag van de Handel beginnen.

>[!NOTE]
>
>Leer hoe u voor mobiele ontwikkelaars [integreren](./mobile-sdk-epc.md) de Adobe Experience Platform Mobile SDK met Commerce.

## Publiek

Deze gids is ontworpen voor de Adobe Commerce-handelaar die zijn winkel wil verrijken en aanpassen om de winkelervaring voor zijn klanten te verbeteren.

## Ondersteuning

Gebruik de volgende bronnen als u informatie nodig hebt of vragen hebt die niet in deze handleiding worden behandeld:

* [Help Center](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html){target="_blank"}
* [Ondersteuningstickets](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket){target="_blank"}—Verstuur een ticket om extra hulp te ontvangen.
