---
title: De Adobe Experience Platform Mobile SDK integreren met Commerce
description: Leer hoe u de Adobe Experience Platform Mobile SDK kunt gebruiken met uw headless of aangepaste Commerce-winkel.
role: Admin, Developer
feature: Personalization, Integration, Eventing
exl-id: d1340b15-e7de-42b5-ad64-d4c31f0db029
source-git-commit: 593e92ebf890bd7d9bfef1cd13be727ca6be172b
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# De Adobe Experience Platform Mobile SDK integreren met Commerce

>[!IMPORTANT]
>
>De Adobe Experience Platform Mobile SDK voor iOS ondersteunt iOS 11 of hoger.

Het integreren van [ Adobe Experience Platform Mobiele SDK ](https://developer.adobe.com/client-sdks/home/) met de mobiele app van Commerce staat verkopers toe om de gebeurtenisgegevens van Commerce [ ](events.md) naar de rand van het Experience Platform te verzenden.

Wanneer Commerce-gebeurtenisgegevens aan de rand beschikbaar zijn, kunnen deze door andere Adobe Experience Cloud-toepassingen worden geopend. Bijvoorbeeld, kunt u de gegevens gebruiken om publiek in Real-Time CDP toen [ te bouwen die publiek ](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html) gebruiken om uw mobiele app van Commerce te personaliseren.

## Configuratie

Installeer en configureer de SDK in het Experience Platform om de Adobe Experience Platform Mobile SDK met Commerce te gaan gebruiken. Voltooi vervolgens de configuratie in Commerce.

### Experience Platform

1. Leer over mobiele toepassingsmogelijkheden door [ Adobe Experience Cloud in mobiele apps te herzien leerprogramma ](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html).

1. [ installeer en vorm ](https://developer.adobe.com/client-sdks/documentation/getting-started/) SDK in Experience Platform.

   >[!NOTE]
   >
   >Het schema dat u maakt en configureert in het Experience Platform is hetzelfde schema als dat u gebruikt in de toepassingscode in uw mobiele Commerce-app.

### Commerce

Nadat u de SDK-configuratie voor het Experience-platform hebt voltooid, voegt u de SDK-configuratie toe aan Commerce.

1. Als u Commerce-gebeurtenisgegevens naar het Experience Platform wilt verzenden via de SDK, moet u een XDM-schema opgeven in de toepassingscode. Dit schema moet het schema [ aanpassen dat ](https://developer.adobe.com/client-sdks/home/getting-started/set-up-schemas-and-datasets/) voor SDK in het Experience Platform wordt gevormd.

   In het volgende voorbeeld ziet u hoe u de gebeurtenis `web.webpagedetails.pageViews` bijhoudt en de gebeurtenis `identityMap` instelt met behulp van het e-mailveld.

   ```swift
   let stateName = "luma: content: ios: us: en: home"
   var xdmData: [String: Any] = [
       "eventType": "web.webpagedetails.pageViews",
       "web": [
           "webPageDetails": [
               "pageViews": [
                   "value": 1
               ],
               "name": "Home page"
           ]
       ]
   ]
   
   let experienceEvent = ExperienceEvent(xdm: xdmData)
   Edge.sendEvent(experienceEvent: experienceEvent)
   
   // Adobe Experience Platform - Update Identity
   
   let emailLabel = "mobileuser@example.com"
   
   let identityMap: IdentityMap = IdentityMap()
   identityMap.add(item: IdentityItem(id: emailLabel), withNamespace: "Email")
   Identity.updateIdentities(with: identityMap)
   ```

1. Maak verbinding met de omgeving van de Commerce Cloud.

   In de bouwstijlmontages van uw project, voeg URL aan het eindpunt van Commerce GraphQL toe. Bijvoorbeeld:

   - Zuiver: http://_zuivert_.commercesite.cloud/graphql/
   - Versie: http://_versie_.commercesite.cloud/graphql/

1. Om gegevens van de eindpunten van Commerce GraphQL terug te winnen, produceer eerst de noodzakelijke dossiers en de folders in uw project gebruikend de [ Generator van de Code van Apollo ](https://www.apollographql.com/docs/ios/).

   1. Van uw projectfolder, [ installeert ](https://www.apollographql.com/docs/ios/get-started#1-install-the-apollo-frameworks) Apollo iOS.

   1. [ initialiseert ](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#initialize) de Codegen CLI van Apollo.

      Hiermee maakt u een `apollo-codegen-configuration.json` -bestand.

   1. Genereer de benodigde GraphQL-bestanden en -mappen in uw project door de inhoud van het `apollo-codegen-configuration.json` -bestand te vervangen door:

      ```json
      {
      "schemaName" : "MagentoAPI",
      "input" : {
          "operationSearchPaths" : [
          "**/*.graphql"
          ],
          "schemaSearchPaths" : [
          "**/*.graphqls"
          ]
      },
      "output" : {
          "testMocks" : {
          "none" : {
          }
          },
          "schemaTypes" : {
          "path" : "../MagentoAPI",
          "moduleType" : {
              "swiftPackageManager" : {
              }
          }
          },
          "operations" : {
          "inSchemaModule" : {
          }
          }
      },
      "schemaDownloadConfiguration": {
          "downloadMethod": {
              "introspection": {
                  "endpointURL": "http://magento24.com/graphql/",
                  "httpMethod": {
                      "POST": {}
                  },
                  "includeDeprecatedInputValues": false,
                  "outputFormat": "SDL"
              }
          },
          "downloadTimeout": 60,
          "headers": [],
          "outputPath": "magento.graphqls"
      }
      }
      ```

   1. [ Vetch ](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#fetch-schema) het schema van GraphQL van Commerce.

      Zorg ervoor dat het pad naar het `./apollo-codegen-config.json` -bestand is, dat de verwijzing naar het Commerce GraphQL-schema bevat.

   1. [ produceer ](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#generate) de broncode.

      Zorg ervoor dat het pad naar het `./apollo-codegen-config.json` -bestand is, dat de configuratiegegevens bevat om de benodigde bestanden en mappen te genereren.

   1. Binnen de pas gecreëerde **GraphQLGenerated** omslag, voeg of geef de types van GraphQL toe uit. U kunt bijvoorbeeld een `DynamicBlocks.graphql` -type met de volgende inhoud toevoegen:

      ```graphql
      query dynamicBlocks($input: DynamicBlocksFilterInput){
          dynamicBlocks(input: $input)
          {
              items {
                  content {
                      html
                  }
              }
          }
      }
      ```

   U hebt de Adobe Experience Platform Mobile SDK nu geïntegreerd met uw mobiele Commerce-app. Gebeurtenisgegevens lopen van uw app naar de rand van het Experience Platform.

## Commerce-gebeurtenissen die zijn gegenereerd vanuit mobiele toepassingen onderscheiden

Alle [ gebeurtenissen ](events.md) bevatten een geroepen gebied `channel`. Het veld `channel` bevat `channel._id` en `channel._type` , die voor een Luma-storefront naamruimtewaarden `"https://ns.adobe.com/xdm/channels/web"` en `"https://ns.adobe.com/xdm/channel-types/web"` hebben. Voor een mobiele winkel zijn de naamruimtewaarden echter respectievelijk `"https://ns.adobe.com/xdm/channels/mobile-app"` en `"https://ns.adobe.com/xdm/channel-types/mobile"` .

## Volgende stappen

Om te leren hoe te om het publiek van Real-Time CDP van uw mobiele app van Commerce terug te winnen om de regels van de kartprijs, dynamische blokken, en verwante productregels te informeren, zie [ Audience Activation ](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html#retrieve-audiences-using-the-adobe-experience-platform-mobile-sdk).
