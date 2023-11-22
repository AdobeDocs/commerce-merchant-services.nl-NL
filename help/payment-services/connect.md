---
title: Uw instantie verbinden
description: Verbind uw instantie van de Handel gebruikend een API sleutel en een privé sleutel, en specificeer de gegevensruimte in de configuratie.
exl-id: 5038fd31-bac5-419e-a172-66919a9b5272
feature: Payments, Checkout, Configuration, Saas
source-git-commit: 6769e29a4ae07b8cf15aa2da3cac2fe8583497e0
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---

# Uw instantie verbinden

[!DNL Payment Services] wordt aangedreven door de Diensten van de Handel en opgesteld als SaaS (software als dienst). U verbindt uw instantie van de Handel gebruikend een API sleutel en een privé sleutel, en specificeert de gegevensruimte in de configuratie gebruikend [Commerce Services Connector](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html). **U stelt deze verbinding slechts eenmaal in.**

* Als u *heeft uw instantie al aangesloten*, door uw API geloofsbrieven te verkrijgen en te gebruiken en de Diensten van de Handel te vormen, kunt u te werk gaan [testsandbox instellen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/sandbox.html).
* Als u nog *moet uw instantie verbinden*, zie de informatie in dit onderwerp over [verkrijgen van API-referenties](#obtain-api-credentials) en [configureren van Commerce Services](#configure-commerce-services).
* Als u *onzeker of uw instantie wordt aangesloten*, navigeer naar **Systeem** > Services > **Commerce Services Connector** en bekijk de waarden voor de openbare en persoonlijke API-sleutel in het dialoogvenster [!UICONTROL Sandbox Keys] en [!UICONTROL Production Keys] en de *Project* en *Gegevensruimte* in de [!UICONTROL SaaS Identifier] sectie. Als deze waarden aanwezig zijn, wordt de instantie verbonden.

## API-referenties verkrijgen

Om een dienst van SaaS van de Handel te verbruiken, moet u de API sleutels van uw instantie (de openbare sleutel van de Handel API en een privé sleutel) voor zowel zandbak als productie gebruiken, die in uw worden gecreeerd en geleid [Mijn accountdashboard](https://account.magento.com/customer/account/login). [Het sleutelpaar](https://docs.magento.com/user-guide/configuration/services/saas.html) kan voor een rekening van de Handel-voor zandbak en voor productie-hoewel slechts één paar actief kunnen worden gebruikt tegelijkertijd.

>[!NOTE]
>
>Hebt u hulp nodig bij het openen van uw [!UICONTROL My Account] dashboard? Zie [Een Commerce-account maken](https://docs.magento.com/user-guide/magento/magento-account-create.html).

Een openbare API-sleutel is altijd beschikbaar op het dashboard voor Mijn account nadat deze is gemaakt. Het kan worden gekopieerd of worden geschrapt zoals nodig. De persoonlijke API-sleutel wordt zichtbaar wanneer u een openbare API-sleutel maakt voor de sandbox of productie. Deze sleutel kan alleen worden gekopieerd of opgeslagen vanuit het dialoogvenster dat verschijnt en kan later niet worden geopend.

Een bepaald API zeer belangrijk paar is geldig voor alle Diensten van de Handel in een milieu, zodat als u reeds de Diensten van de Handel hebt die voor uw geval worden gevormd, is uw API zeer belangrijk paar reeds aanwezig in de Schakelaar van de Diensten van de Handel.

Als uw API-sleutel verloren gaat, moet er een nieuw API-sleutelpaar zijn [gegenereerd](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#generate-an-api-key-and-private-key) en [toegepast](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/connect.html#configure-saas-project) aan de Configuratie van de Verbinding van de Diensten van de Handel in Admin. Als de verkeerde sleutels worden gevormd of niets in config bestaat, verschijnt een de foutendialoog van de rekeningscontrole in de Diensten die van de Betaling u op de hoogte brengen dat de rekening niet werd geverifieerd.

Zie een [lijst met beschikbare commerciële services die de API gebruiken](https://docs.magento.com/user-guide/system/saas.html#available-services).

Zie voor meer informatie over het genereren van een API-sleutel voor sandbox- of productieomgevingen [Credentials](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#apikey).

>[!IMPORTANT]
>
>Het wordt aanbevolen geen API-sleutelpaar opnieuw te genereren *en* de SaaS-id en/of gegevensruimte wijzigen op een actieve productie-instantie. U verliest gegevens voor uw instantie als deze worden gewijzigd.

## Commerciële services configureren

Dezelfde API-sleutel kan in alle instanties worden gebruikt, maar elke instantie moet een eigen sleutel hebben [SaaS-gegevensruimte](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/saas.html#saasenv).

>[!NOTE]
>
>De handelaren moeten de zelfde sleutels gebruiken die voor MageID voor hun toeslagrechten worden geproduceerd.

Nu u uw geloofsbrieven hebt verkregen, kunt u uw project SaaS en de Ruimte van Gegevens van het Saas vormen.

1. Op de _Beheerder_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]**.
1. Klik op **[!UICONTROL Configure Commerce Services]**.

   Deze optie is zichtbaar als u de Diensten van de Handel voor uw rekening nog niet hebt gevormd.

   U wordt geleid aan het configuratiegebied in Admin, **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**>**[!UICONTROL Commerce Services Connector]**, om uw Schakelaar van de Diensten van de Handel te vormen.

1. Om uw Diensten van de Handel te vormen, volg de stappen in [SaaS-configuratie](https://experienceleague.adobe.com/docs/commerce-merchant-services/user-guides/integration-services/saas.html#saasenv).
