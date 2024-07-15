---
title: Overzicht van de handleiding
description: Leer hoe te om de gegevens van Adobe Commerce met Adobe Experience Platform te integreren gebruikend de  [!DNL Data Connection]  uitbreiding.
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
>De naam van de aansluiting van het Experience Platform is gewijzigd in [!DNL Data Connection] .

De extensie [!DNL Data Connection] maakt een verbinding tussen uw Adobe Commerce-webinstantie en de Adobe Experience Platform en de Edge Network. Leer hoe te [ ](./mobile-sdk-epc.md) de Mobiele SDK van Adobe Experience Platform met Commerce integreren.

Je Commerce-winkel bevat een schat aan gegevens. Informatie over hoe kopers door de producten op uw site kunnen bladeren, deze kunnen bekijken en uiteindelijk kopen, biedt mogelijkheden om een meer persoonlijke winkelervaring te creëren. Hoewel deze gegevens native Commerce-functies zoals winkelprijzenregels en dynamische blokken kunnen informeren, blijven de gegevens opgeslagen in uw Commerce-exemplaar.

De Adobe Experience Platform biedt een reeks technologieën die, wanneer ze zijn gehydrateerd met gegevens uit uw Commerce-winkel, die gegevens via de Edge Network naar andere DX-producten van de Adobe kunnen distribueren om inzicht te krijgen in het aankoopgedrag van uw klant. Met deze diepgaande inzichten, kunt u een meer gepersonaliseerde het winkelen ervaring over alle kanalen tot stand brengen.

De volgende afbeelding laat zien hoe uw Commerce-gegevens van uw winkel naar andere DX-producten van de Adobe stromen:

![ hoe de gegevens aan de rand van het Experience Platform ](assets/commerce-edge.png) stromen

In de bovenstaande afbeelding worden uw gedrags-, back office- en klantprofielgegevens naar de rand van het Experience Platform verzonden met behulp van een SDK, API en een bronaansluiting. U hoeft niet volledig te begrijpen hoe deze onderdelen werken als de extensie de complexiteit voor het delen van gegevens voor u behandelt. Wanneer de gebeurtenisgegevens zich aan de rand bevinden, kunt u die gegevens in andere Experience Platforms toepassingen opnemen. Bijvoorbeeld:

| Toepassing | Doel | Gevallen gebruiken |
|---|---|---|
| [ Adobe  [!DNL Real-Time CDP] ](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/rtcdp-intro/overview.html) | Profielbeheer en segmenteringsservice | **de geschiedenissegmentatie van de Aankoop**: De handelaren kunnen klanten identificeren die een punt kopen dat op een specifieke tijdspanne (maandelijks, driemaandelijks, jaarlijks, etc.) wordt gebaseerd. De handelaren kunnen segmenten voor deze klanten dan tot stand brengen en hen richten voor bevorderingen, campagnes, en als _bovenkant van de trechter_ gegevens voor lood voor abonnementendiensten.<br> **op categorie-gebaseerde segmentatie**: De handelaren kunnen zien welke categorie van producten werd gekocht.<br> **het Aanbieden-Gebaseerde segmentatie**: De handelaren kunnen klanten identificeren die constant producten terugkeren. De aanbiedingen en kortingen kunnen nu intelligenter zijn. Bijvoorbeeld, kan de vrije verzending voor een klant worden verwijderd die producten de hele tijd terugkeert.<br> **Lookalike richtend**: A _Lookalike Publiek_ is een methodologie die door een handelaar voor hun bevorderingen wordt genomen om nieuwe mensen te bereiken die waarschijnlijk in hun zaken geinteresseerd zullen zijn omdat zij gelijkaardige kenmerken aan uw bestaande klanten delen. De segmenten van de ookalike kunnen worden tot stand gebracht gebaseerd op gedrags en transactionele gegevens.<br> **Eigenschap van de Klant**: De veranderingen in klantengedrag kunnen als resultaat van de diepere klantenprofielen worden geïdentificeerd die van de transactiegegevens kunnen worden gecreeerd. Er zal een hoger vertrouwen in de aandrijvingsscore zijn aangezien er meer gegevens zijn die in de berekeningen zoals productwinst en productconfiguraties stromen.<br> **dwars-verkoopt**: Een handelaar kan sterke dwars-verkoop en omhoog-verkoopkansen van de korrelige informatie identificeren die in Commerce wordt gevangen. |
| [ Klant  [!DNL Journey Analytics] ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) | Diepe analyse van de volledige Commerce-reis | **seizoensgebonden tendensen**: Een handelaar kan seizoensgebonden tendensen identificeren, die hen helpen zich op de periodieke verandering in vraag voor bepaalde producten voorbereiden. Ook, kunnen de handelaren veranderingen in algemene populariteit van om het even welk product over jaren identificeren.<br> **analyse van de Omzetting**: Door te weten wanneer een product werd gekocht, gekoppeld aan toegang tot de gebeurtenissen van de storefrontindruk, kunnen de handelaren een rijk profiel van de klant produceren om omzetanalyse uit te voeren. |
| [ Adobe  [!DNL Analytics] ](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/analytics-overview.html) | Diepe analyse van het gedrag van de klant en de prestaties van de campagne | **Winst van de Orde**: De handelaren kunnen klanten en de grotere klantensegmenten identificeren die een patroon van het terugkeren van producten hebben. Dit helpt de handelaren hun handelsstrategie verbeteren aangezien zij begrijpen hoe hun gedrag van de klantenbasis als kijkt.<br> **Adres van de Orde**: Gebaseerd op het verschepende adres, kan een handelaar begrijpen als de orden door de klanten zelf worden geplaatst of als het voor een ander individu of een entiteit is.<br> **seizoensgebonden tendensen**: Een handelaar kan seizoensgebonden tendensen identificeren, die hen helpen zich op de periodieke verandering in vraag voor bepaalde producten voorbereiden. Ook, kunnen de handelaren veranderingen in algemene populariteit van om het even welk product over jaren identificeren.<br> **analyse van de Omzetting**: Door te weten wanneer een product werd gekocht, gekoppeld aan toegang tot de gebeurtenissen van de storefrontindruk, kunnen de handelaren een rijk profiel van de klant produceren om omzetanalyse uit te voeren. **Nota** Adobe Analytics steunt slechts gedrags (storefront) gebeurtenisgegevens. Adobe Analytics biedt geen ondersteuning voor transactiegegevens (back-koffice). |
| [ Adobe  [!DNL Journey Optimizer] ](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) | Campagneorchestratie langs kanalen | **Op gedrag-gebaseerde reizen**: De handelaren kunnen een klant richten die een mobiele telefoon twee jaar geleden kocht door hen voor te stellen het nieuwe model te kopen. Handelaars kunnen persoonlijke campagnes en promoties voor deze klanten maken en de functionaliteit van e-mail en SMS gebruiken om te bereiken. Handelaren kunnen ook historische volgorde- en gedragsgegevens gebruiken om trends te identificeren. Bijvoorbeeld, kan een klant die een punt met een bepaalde configuratie in het verleden kocht en nu het zelfde product opnieuw probeert te kopen, hun koopreis hebben verbeterd door hen zicht en toegang tot de zelfde productconfiguraties te geven.<br> **Personalization**: Met toegang tot de informatie van het klantenprofiel, [!DNL Journey Optimizer] kan hoogst gepersonaliseerde reizen ontgrendelen die handelaars toestaan om aan de klanten op veelvoudige verschillende kanalen te bereiken.<br> **Nieuw profiel creeerde**: Welkome e-mail en promotionele activiteiten kunnen nieuwe klanten in hun het winkelen reizen aanmoedigen en beïnvloeden.<br> **Geschrapte Profiel**: De handelaren kunnen verkiezen ophouden verzendend bevorderende e-mail naar cliënten die hun rekening hebben gesloten. De handelaren kunnen ook campagnes bouwen om verloren klanten terug te winnen. |

## Gegevens van Experience Platform terugbrengen naar Commerce

Het verzenden van Commerce-gegevens naar het Experience Platform met de extensie [!DNL Data Connection] is een van de mogelijkheden voor het delen van Commerce-gegevens. De andere kant, die een facultatieve uitbreiding is, wordt genoemd [ Audience Activation ](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html). Met deze extensie kunt u een publiek in Real-Time CDP opbouwen en dat publiek naar uw Commerce-winkel distribueren om de regels voor de winkels van winkelwagentjes, verwante producten en dynamische blokken te informeren.

Op een hoog niveau ziet de gegevensstroom van uw Commerce-winkel naar het Experience Platform en terug door de extensie Audience Activation er als volgt uit:

![[!DNL Data Connection] flow ](assets/data-connection.png)

Nadat u de verbinding tussen Commerce en Experience Platform en Experience Platform aan Commerce hebt ingesteld, blijven de gegevens doorlopen. U hoeft niet opnieuw verbinding te maken, tenzij u dit moet doen door een upgrade.

## Concepten

Het delen van gegevens tussen deze twee systemen vereist dat u verschillende concepten begrijpt.

* **Gegevens** - de gegevens die met het Experience Platform worden gedeeld zijn gegevens die van browser gebeurtenissen op uw opslag, achterbureaugebeurtenissen op de server, en profielverslaggegevens worden verzameld. Storefront-gebeurtenissen worden vastgelegd op basis van de interacties van kopers op de site en omvatten gebeurtenissen zoals [`addToCart`](events.md#addtocart) , [`pageView`](events.md#pageview) , [`createAccount`](events.md#createaccount) , [`editAccount`](events.md#editaccount) , [`startCheckout`](events.md#startcheckout) , [`completeCheckout`](events.md#completecheckout) , [`signIn`](events.md#signin) , [`signOut`](events.md#signout) , enzovoort. Zie [ storefront gebeurtenissen ](events.md#storefront-events) voor de volledige lijst van storefront gebeurtenissen. Server-kant, of achterkantoorgebeurtenissen, omvatten [ de status van de orde ](events-backoffice.md#order-status) informatie, zoals [`orderPlaced`](events-backoffice.md#orderplaced), [`orderReturned`](events-backoffice.md#orderitemreturncompleted), [`orderShipped`](events-backoffice.md#ordershipmentcompleted), [`orderCancelled`](events-backoffice.md#ordercancelled), etc. Zie [ achterbureaugebeurtenissen ](events-backoffice.md) voor de volledige lijst van achterbureaugebeurtenissen. Profielrecordgegevens bevatten informatie wanneer een nieuw profiel wordt gemaakt, bijgewerkt of verwijderd. Zie [ gegevens van het profielverslag ](events-profilerecord.md) om meer te leren.

* **Experience Platform en Edge Network** - het gegevenspakhuis voor de meeste producten van Adobe DX. De gegevens die naar het Experience Platform worden verzonden worden dan verspreid aan de Adobe DX producten door de Edge Network van het Experience Platform. U kunt bijvoorbeeld Journey Optimizer starten, uw specifieke Commerce-gebeurtenisgegevens ophalen van de rand en een verlaten wagente-mail maken in Journey Optimizer. Journey Optimizer kan deze e-mail vervolgens verzenden als er in je Commerce-winkel winkels winkels verlaten winkelwagentjes zijn. Leer meer over het [ Experience Platform en de Edge Network ](https://experienceleague.adobe.com/docs/platform-learn/data-collection/web-sdk/overview.html).

* **Schema** - het schema is wat de structuur van het gegeven beschrijft dat wordt verzonden. Voordat een Experience Platform uw Commerce-gegevens kan invoeren, moet u een schema samenstellen om de gegevensstructuur te beschrijven en beperkingen op te geven aan het type gegevens dat binnen elk veld kan worden opgenomen. De schema&#39;s bestaan uit een basisklasse en nul of meer groepen van het schemagebied. Het schema gebruikt de XDM-structuur, die alle Adobe DX-producten kunnen lezen. Dus wanneer u uw gegevens naar het Experience Platform verzendt, kunt u er zeker van zijn dat uw gegevens worden begrepen in alle DX-producten. Leer meer over [ schema&#39;s ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

* **Dataset** - een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst die een schema (kolommen) en gebieden (rijen) bevat. Datasets bevatten ook metagegevens die verschillende aspecten van de gegevens beschrijven die ze opslaan. Alle gegevens die met succes in Adobe Experience Platform worden opgenomen, bevinden zich in gegevenssets. Leer meer over [ datasets ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html).

* **Datastream** - identiteitskaart die gegevens om van Adobe Experience Platform aan andere producten van Adobe DX toestaat te stromen. Deze id moet zijn gekoppeld aan een specifieke website in uw specifieke Adobe Commerce-exemplaar. Wanneer u deze gegevensstroom creeert, specificeer het XDM schema u hierboven creeerde. Leer meer over [ gegevensstromen ](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html).

## Ondersteunde architectuur

De extensie [!DNL Data Connection] is beschikbaar op de volgende architecturen:

* PHP/Luma
* [ PWA Studio ](https://developer.adobe.com/commerce/pwa-studio/integrations/adobe-commerce/aep/)
* [ AEM ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/content-and-commerce/integrations/aep.html)

## Vereisten

Als u de extensie [!DNL Data Connection] wilt gebruiken, moet u over het volgende beschikken:

* Adobe Commerce 2.4.4 of hoger
* Adobe ID- en organisatie-id
* [ de Gegevens van de Cliënt van de Adobe Laag (ACDL) ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/client-data-layer/overview.html), die wordt vereist om storefront gebeurtenisgegevens te verzamelen
* Rechten op andere Adobe DX-producten.

## Stappen aan boord

Op een hoog niveau worden de volgende stappen uitgevoerd om de extensie [!DNL Data Connection] in te schakelen:

1. [ installeer ](install.md) de [!DNL Data Connection] uitbreiding.
1. [ Teken binnen ](https://helpx.adobe.com/manage-account/using/access-adobe-id-account.html) aan uw rekening van de Adobe en [ mening om ](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) uw organisatieidentiteitskaart te bevestigen. De organisatie-id is de id die is gekoppeld aan uw bedrijf voor het geleverde Experience Cloud. Deze id is een alfanumerieke tekenreeks van 24 tekens, gevolgd door (en moet omvatten) `@AdobeOrg` .
1. Verzeker u [ toestemming voor gegevensinzameling in Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html) hebt.
1. Herzie de [ types van gegevens ](data-ingestion.md) u kunt verzamelen en verzenden.
1. Creeer of werk uw [ schema van de de tijdreeksgebeurtenis van de tijdreeks ](update-xdm.md) of [ schema van het profielverslag ](profile-data.md) met Commerce-Specifieke gebiedsgroepen bij.
1. [ creeer een dataset ](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/experience-cloud/platform.html#create-a-dataset) die van het schema wordt gebaseerd u creeerde of bijgewerkt. Deze dataset bevat de gegevens van Commerce die naar het Experience Platform Edge worden verzonden.
1. [ creeer een gegevensstroom ](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) en selecteer het schema XDM dat de Commerce-Specifieke gebiedsgroepen bevat.
1. [ verbind met de Diensten van Commerce ](../landing/saas.md).
1. [ verbind met Adobe Experience Platform ](connect-data.md).

De rest van deze gids begeleidt u door elk van deze stappen meer in detail zodat kunt u aan snelheid krijgen en beginnen gebruikend de macht van de producten van Adobe DX in uw opslag van Commerce.

>[!NOTE]
>
>Voor mobiele ontwikkelaars, leer hoe te [ ](./mobile-sdk-epc.md) de Mobiele SDK van Adobe Experience Platform met Commerce integreren.

## Publiek

Deze gids is ontworpen voor de Adobe Commerce-handelaar die zijn Commerce-winkel wil verrijken en aanpassen om de winkelervaring voor zijn klanten te verbeteren.

## Ondersteuning

Gebruik de volgende bronnen als u informatie nodig hebt of vragen hebt die niet in deze handleiding worden behandeld:

* [ centrum van de Hulp ](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/overview.html) {target="_blank"}
* [ kaartjes van de Steun ](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#submit-ticket) {target="_blank"} - leg een kaartje voor om extra hulp te ontvangen.
