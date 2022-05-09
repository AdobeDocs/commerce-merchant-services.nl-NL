---
title: Sluit uw exemplaar aan
description: Verbind uw instantie van de Handel gebruikend een API sleutel en een privé sleutel, en specificeer de gegevensruimte in de configuratie.
exl-id: 5038fd31-bac5-419e-a172-66919a9b5272
source-git-commit: 9596815e31402f23b399b223f3221074331c1773
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 0%

---

# Sluit uw exemplaar aan

[!DNL Payment Services] wordt aangedreven door de Diensten van de Handel en opgesteld als SaaS (software als dienst). U verbindt uw instantie van de Handel gebruikend een API sleutel en een privé sleutel, en specificeert de gegevensruimte in de configuratie. U stelt deze verbinding slechts eenmaal in.

Zie [Commerce Services Connector](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} in de basisgebruikershandleiding voor meer informatie over deze service.

## API-referenties verkrijgen

Om een dienst van de Handel te verbruiken SaaS, moet u de API sleutels van uw instantie gebruiken, die in uw worden gecreeerd en beheerd [Mijn accountdashboard](https://account.magento.com/customer/account/login){target=&quot;_blank&quot;}. Twee verschillende API zeer belangrijke paren kunnen voor een rekening van de Handel-voor zandbak en voor productie (levende betalingen)-hoewel slechts één paar actief kunnen tegelijkertijd worden gebruikt.

>[!NOTE]
>
>Hebt u hulp nodig bij het openen van uw [!UICONTROL My Account] dashboard? Zie [Een Commerce-account maken](https://docs.magento.com/user-guide/magento/magento-account-create.html){target=&quot;_blank&quot;} in de basisgebruikershandleiding.

Een bepaald API zeer belangrijk paar is geldig voor alle Diensten van de Handel in een milieu, zodat als u reeds de Diensten van de Handel hebt die voor uw instantie van de Handel wordt gevormd uw API zeer belangrijk paar is reeds aanwezig in Admin. Als uw persoonlijke API sleutel verloren gaat, moet een nieuw API zeer belangrijk paar op de configuratie van de Diensten van de Handel in Admin worden geproduceerd en worden toegepast.

Zie voor meer informatie over het genereren van een API-sleutel voor sandbox- of productieomgevingen [Commerce Services Connector](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} in de basisgebruikershandleiding.

>[!IMPORTANT]
>
>Als u een API zeer belangrijk paar regenereert en het Herkenningsteken SaaS verandert, verbinden alle Diensten van de Handel die door deze instantie worden gebruikt met een verschillende gegevensopslag en uw toegang (met inbegrip van eerder opgeslagen gegevens) wordt verloren. Het wordt aanbevolen geen API-sleutelpaar opnieuw te genereren en de SaaS-id te wijzigen voor een actieve productie-instantie.

### Koophandel-API en persoonlijke sleutel

Sommige [!DNL Adobe Commerce] en [!DNL Magento Open Source] de eigenschappen worden opgesteld als SaaS (software als dienst) - gekend als de Diensten van de Handel. Om deze diensten te gebruiken, moet u uw instantie van de Handel met deze diensten verbinden gebruikend een API sleutel en een privé sleutel, en de gewenste gegevensruimte specificeren in [configuratie](https://docs.magento.com/user-guide/configuration/services/saas.html){target=&quot;_blank&quot;}.

Wanneer u een rekening van de Handel creeert, die door een MageID wordt geïdentificeerd, kunt u een sleutel van de Handel API en een privé sleutel produceren. Om de Diensten van de Handel te gebruiken, zoals [!DNL Payment Services], [!DNL Product Recommendations], of [!DNL Live Search]moet de vergunninghouder deze toetsen genereren om voor validatie van machtigingen te kunnen zorgen. Deze sleutels kunnen dan worden overgegaan tot het systeem integrator of ontwikkelingsteam dat de projecten en milieu&#39;s namens de vergunninghouder beheert. Als u een oplossingsintegrator bent, kunt u deze diensten voor uw eigen behoeften ook gebruiken. In dat geval moet de ondertekenaar van het partnercontract voor handel de sleutels genereren.

### Een API-sleutel en een persoonlijke sleutel genereren

1. Meld u aan bij uw Commerce-account op [https://account.magento.com/customer/account/login](https://account.magento.com/customer/account/login).
1. Onder de **[!UICONTROL Magento]** tab, selecteert u **[!UICONTROL API Portal]** op de zijbalk.
1. Van de _[!UICONTROL Environment]_menu, selecteert u **[!UICONTROL Sandbox]**vervolgens **[!UICONTROL Production]**.

   >[!IMPORTANT]
   >
   >API-sleutels zijn vereist voor beide omgevingen.

1. Typ een naam in het dialoogvenster _[!UICONTROL API Keys]_en klik op **[!UICONTROL Add New]**.

   Met deze handeling wordt een dialoogvenster geopend waarin u de nieuwe sleutel kunt downloaden.

   >[!IMPORTANT]
   >
   >Dit dialoogvenster is de enige gelegenheid om uw sleutel te kopiëren of te downloaden.

1. Klikken **[!UICONTROL Download]** klik vervolgens op **[!UICONTROL Cancel]**.

   De _[!UICONTROL API Keys]_wordt nu uw API-sleutel weergegeven.

1. Kopieer zowel de API-sleutel als de persoonlijke sleutel wanneer u een SaaS-project selecteert of maakt.

   Zie [SaaS](https://docs.magento.com/user-guide/system/saas.html){target=&quot;_blank&quot;} in de gebruikershandleiding voor meer informatie.

Dezelfde API-sleutel kan voor alle instanties worden gebruikt, maar elke instantie moet een eigen SaaS-gegevensruimte hebben.

Wanneer u een project SaaS creeert, produceert de Handel één of meerdere gegevensruimten SaaS afhankelijk van uw vergunning van de Handel:

* [!DNL Adobe Commerce] - één productieresolutie; twee testgegevensruimten
* [!DNL Magento Open Source] - één productieresolutie; geen testgegevensruimten

### SaaS-project configureren

>[!NOTE]
>
>Als u de _[!UICONTROL Commerce Services Connector]_in de configuratie van de Handel, moet u de modules van de Handel voor uw gewenste Dienst van de Handel installeren, zoals [[!DNL Payment Services]](install.md).

Als u een SaaS-project wilt selecteren of maken, vraagt u de Commerce API-sleutel aan bij de houder van de Commerce-licentie voor uw winkel.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**.
1. Vouw in het linkerdeelvenster uit **[!UICONTROL Services]** en kiest u **[!UICONTROL Commerce Services Connector]**.
1. In de _[!UICONTROL API Keys]_plakken, plakt u uw hoofdwaarden.

   >[!IMPORTANT]
   >
   >Toetswaarden voor beide toevoegen **[!UICONTROL sandbox]** en **[!UICONTROL production]** omgevingen.

1. Klik op **[!UICONTROL Save Config]**.

   Wanneer u sparen, als er om het even welke projecten SaaS verbonden aan uw API sleutel zijn, verschijnen die projecten in _[!UICONTROL SaaS Project]_in het_[!UICONTROL SaaS Identifier]_ sectie.

1. Als er geen SaaS-projecten bestaan, klikt u op **[!UICONTROL Create Project]**. Dan ga een naam voor uw project SaaS in **[!UICONTROL Project Name]** veld.
1. Om voor de huidige configuratie van uw opslag van de Handel te gebruiken, selecteer **[!UICONTROL SaaS Data Space]**.

>[!IMPORTANT]
>
>Als u uw sleutels in de sectie van het Portaal API van Mijn Rekening regenereert, werk onmiddellijk de API sleutels in de configuratie Admin bij. Als u nieuwe sleutels produceert en niet hen in Admin bijwerkt, zullen uw uitbreidingen SaaS niet meer werken en u zult waardevolle gegevens verliezen.

U kunt de namen wijzigen door op de knop **[!UICONTROL Rename this Project]** of **[!UICONTROL Rename Data Space]** respectievelijk knoppen.

## Commerciële services configureren

De eerste stap bij instapweigering [!DNL Payment Services] moet uw Diensten van de Handel in Admin vormen.

1. Op de _Beheer_ zijbalk, ga naar **[!UICONTROL Sales]** > **[!UICONTROL [!DNL Payment Services]]**.
1. Klik op **[!UICONTROL Configure Commerce Services]**.

   Deze optie is zichtbaar als u nog geen Diensten van de Handel voor uw rekening hebt gevormd.

   U wordt geleid aan het configuratiegebied in Admin, **[!UICONTROL Stores]** > _[!UICONTROL Settings]_>**[!UICONTROL Configuration]**>**[!UICONTROL Commerce Services Connector]**, om uw Schakelaar van de Diensten van de Handel te vormen.

1. Om uw Diensten van de Handel te vormen, volg de stappen die in worden beschreven [Commerciële diensten](https://docs.magento.com/user-guide/system/saas.html#createsaasenv){target=&quot;_blank&quot;}.
