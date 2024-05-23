---
title: Uw instantie verbinden
description: Sluit uw Commerce-instantie aan met behulp van een API-sleutel en een persoonlijke sleutel en geef de gegevensruimte op in de configuratie.
exl-id: 5038fd31-bac5-419e-a172-66919a9b5272
feature: Payments, Checkout, Configuration, Saas
source-git-commit: 5d3a89b2ef06b2c67ec715ce4f31f22249b336e0
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Uw instantie verbinden

[!DNL Payment Services] wordt aangedreven door Commerce Services en als SaaS (software als dienst) opgesteld. U maakt verbinding met uw Commerce-instantie door een API-sleutel en een persoonlijke sleutel te gebruiken en de gegevensruimte in de configuratie op te geven met de [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html). **U stelt deze verbinding slechts eenmaal in.**

>[!INFO]
>
> Zie onze [[!DNL Adobe Commerce] Services Connector](https://experienceleague.adobe.com/docs/commerce-learn/tutorials/admin/adobe-commerce-services/configure-adobe-commerce-services-connector.html?lang=en) video voor aanvullende informatie.

* Als u *heeft uw instantie al aangesloten* door uw API-referenties te verkrijgen en te gebruiken en Commerce Services te configureren, kunt u doorgaan naar [testsandbox instellen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/sandbox.html).
* Als u nog *moet uw instantie verbinden*, zie de informatie in dit onderwerp over [verkrijgen van API-referenties](#obtain-api-credentials) en [configureren, Commerce Services](#configure-commerce-services).
* Als u *onzeker of uw instantie wordt aangesloten*, navigeer naar **Systeem** > Services > **Commerce Services Connector** en bekijk de waarden voor de openbare en persoonlijke API-sleutel in het dialoogvenster [!UICONTROL Sandbox Keys] en [!UICONTROL Production Keys] en de *Project* en *Gegevensruimte* in de [!UICONTROL SaaS Identifier] sectie. Als deze waarden aanwezig zijn, wordt de instantie verbonden.

>[!NOTE]
>
>Alle handelaren die recht hebben op Betalingsdiensten, kunnen gebruik maken van één ruimte voor productiegegevens en twee ruimten voor testgegevens.

## API-referenties verkrijgen

Als u een Commerce SaaS-service wilt gebruiken, moet u de API-sleutels van uw instantie (Commerce, openbare API-sleutel en een persoonlijke sleutel) gebruiken voor zowel de sandbox als de productie, die in uw [Mijn accountdashboard](https://account.magento.com/customer/account/login). [Het sleutelpaar](https://docs.magento.com/user-guide/configuration/services/saas.html) kan worden gemaakt voor een Commerce-account—een voor een sandbox en een voor productie—maar er kan slechts één paar tegelijk actief worden gebruikt.

>[!NOTE]
>
>Hebt u hulp nodig bij het openen van uw [!UICONTROL My Account] dashboard? Zie [Een Commerce-account maken](https://docs.magento.com/user-guide/magento/magento-account-create.html).

Een openbare API-sleutel is altijd beschikbaar op het dashboard voor Mijn account nadat deze is gemaakt. Het kan worden gekopieerd of worden geschrapt zoals nodig. De persoonlijke API-sleutel wordt zichtbaar wanneer u een openbare API-sleutel maakt voor de sandbox of productie. Deze sleutel kan alleen worden gekopieerd of opgeslagen vanuit het dialoogvenster dat verschijnt en kan later niet worden geopend.

Een gegeven API zeer belangrijk paar is geldig voor alle Diensten van Commerce in een milieu, zodat als u reeds de Diensten van Commerce voor uw geval hebt gevormd, is uw API zeer belangrijk paar reeds aanwezig in de Schakelaar van de Diensten van Commerce.

Als uw API-sleutel verloren gaat, moet er een nieuw API-sleutelpaar zijn [gegenereerd](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#generate-an-api-key-and-private-key) en [toegepast](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#configure-saas-project) naar de Commerce Services Connector-configuratie in de Admin. Als de verkeerde sleutels worden gevormd of niets in config bestaat, verschijnt een de foutendialoog van de rekeningscontrole in de Diensten die van de Betaling u op de hoogte brengen dat de rekening niet werd geverifieerd.

Zie een [lijst met beschikbare Commerce Services die de API gebruiken](https://docs.magento.com/user-guide/system/saas.html#available-services).

Zie voor meer informatie over het genereren van een API-sleutel voor sandbox- of productieomgevingen [Credentials](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#apikey).

>[!IMPORTANT]
>
>Het wordt aanbevolen geen API-sleutelpaar opnieuw te genereren *en* de SaaS-id en/of gegevensruimte wijzigen op een actieve productie-instantie. U verliest gegevens voor uw instantie als deze worden gewijzigd.

## Commerce Services configureren

Dezelfde API-sleutel kan in alle instanties worden gebruikt, maar elke instantie moet een eigen sleutel hebben [SaaS-gegevensruimte](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#saasenv).

>[!NOTE]
>
>De handelaren moeten de zelfde sleutels gebruiken die voor MageID voor hun toeslagrechten worden geproduceerd.

Nu u uw geloofsbrieven hebt verkregen, kunt u uw project SaaS en de Ruimte van Gegevens van het Saas vormen.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]**.
1. Klik op **[!UICONTROL Configure Commerce Services]**.

   Deze optie is zichtbaar als u nog geen Commerce Services voor uw account hebt geconfigureerd.

   U wordt geleid aan het configuratiegebied in Admin, **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**>**[!UICONTROL Commerce Services Connector]**, om uw Commerce Services-connector te configureren.

1. Volg de stappen in [SaaS-configuratie](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html#saasenv).

   >[!INFO]
   >
   > Zie onze [[!DNL Adobe Commerce] Services Connector](https://experienceleague.adobe.com/docs/commerce-learn/tutorials/admin/adobe-commerce-services/configure-adobe-commerce-services-connector.html?lang=en#configuration-faqs) video voor aanvullende informatie.

## Endpoint

[!DNL Payment Services] gebruikt de [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html) om verbinding te maken met Commerce Services en te implementeren als SaaS. Dit [!DNL Commerce Services Connector] communiceert door het eindpunt bij:

* `commerce-beta.adobe.io` voor sandboxomgevingen.
* `commerce.adobe.io for` voor live omgevingen.
