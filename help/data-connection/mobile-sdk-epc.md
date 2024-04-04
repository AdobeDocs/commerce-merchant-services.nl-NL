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

De [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) met de mobiele app Commerce kunnen handelaren Commerce verzenden  [gebeurtenisgegevens](events.md) naar de rand van het Experience Platform.

Wanneer de de gebeurtenisgegevens van de Handel bij de rand beschikbaar zijn, kan het door andere toepassingen van Adobe Experience Cloud worden betreden. U kunt de gegevens bijvoorbeeld gebruiken om een publiek op te bouwen in Real-Time CDP en vervolgens [die doelgroepen gebruiken](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html) om uw mobiele app van de Handel te personaliseren.

## Configuratie

Installeer en configureer de SDK in het Experience Platform om de Adobe Experience Platform Mobile SDK met Commerce te gaan gebruiken. Dan, voltooi uw configuratie in Handel.

### Experience Platform

1. Meer informatie over de mogelijkheden van mobiele apps vindt u in de [Zelfstudie over Adobe Experience Cloud in mobiele apps](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html).

1. [Installeren en configureren](https://developer.adobe.com/client-sdks/documentation/getting-started/) de SDK in Experience Platform.

   >[!NOTE]
   >
   >Het schema dat u in het Experience Platform maakt en configureert, is hetzelfde schema als dat u in de toepassingscode in de mobiele app Commerce gebruikt.

### Handel

Nadat u de configuratie van SDK voor het platform van de Ervaring voltooit, voeg de configuratie van SDK aan Handel toe.

1. Om de gebeurtenisgegevens van de Handel naar het Experience Platform via SDK te verzenden, moet u een schema XDM in de toepassingscode verstrekken. Dit schema moet overeenkomen met het schema [geconfigureerd](https://developer.adobe.com/client-sdks/home/getting-started/set-up-schemas-and-datasets/) voor de SDK in het Experience Platform.

   In het volgende voorbeeld wordt getoond hoe u de `web.webpagedetails.pageViews` en stelt de `identityMap` het e-mailveld gebruiken.

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

   In de bouwstijlmontages van uw project, voeg URL aan het eindpunt van GraphQL van de Handel toe. Bijvoorbeeld:

   - Foutopsporing: http://_foutopsporing_.commercesite.cloud/graphql/
   - Release: http://_vrijgeven_.commercesite.cloud/graphql/

1. Om gegevens van de Eindpunten van GraphQL van de Handel terug te winnen, produceer eerst de noodzakelijke dossiers en de folders in uw project gebruikend [Apollo Code Generator](https://www.apollographql.com/docs/ios/).

   1. Van uw projectfolder, [installeren](https://www.apollographql.com/docs/ios/get-started#1-install-the-apollo-frameworks) Apollo iOS.

   1. [Initialiseren](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#initialize) de Apollo Codegen CLI.

      Hiermee maakt u een `apollo-codegen-configuration.json` bestand.

   1. Genereer de benodigde GraphQL-bestanden en -mappen in uw project door de inhoud van de `apollo-codegen-configuration.json` bestand met het volgende:

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

   1. [Ophalen](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#fetch-schema) het schema Commerce GraphQL.

      Zorg ervoor dat het pad naar de `./apollo-codegen-config.json` bestand, dat de verwijzing naar het schema Commerce GraphQL bevat.

   1. [Genereren](https://www.apollographql.com/docs/ios/code-generation/codegen-cli/#generate) de broncode.

      Zorg ervoor dat het pad naar de `./apollo-codegen-config.json` bestand, dat de configuratiegegevens bevat om de benodigde bestanden en mappen te genereren.

   1. Binnen het nieuwe ontwerp **GraphQLGenerated** GraphQL-typen toevoegen of bewerken. U kunt bijvoorbeeld een `DynamicBlocks.graphql` typen met de volgende inhoud:

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

   U hebt nu de Adobe Experience Platform Mobile SDK geïntegreerd met uw mobiele app Commerce. Gebeurtenisgegevens lopen van uw app naar de rand van het Experience Platform.

## Hoe te om de gebeurtenissen van de Handel te onderscheiden die van mobiele toepassingen worden geproduceerd

Alles [gebeurtenissen](events.md) bevat een veld met de naam `channel`. De `channel` field contains `channel._id` en `channel._type` die voor een Luma-archief naamruimtewaarden bevat van `"https://ns.adobe.com/xdm/channels/web"` en `"https://ns.adobe.com/xdm/channel-types/web"` respectievelijk. Voor een mobiele winkel zijn de naamruimtewaarden echter `"https://ns.adobe.com/xdm/channels/mobile-app"` en `"https://ns.adobe.com/xdm/channel-types/mobile"` respectievelijk.

## Volgende stappen

Als u wilt leren hoe u het Real-Time CDP-publiek kunt ophalen uit uw app voor mobiele handel om de regels voor de prijs van winkelwagentjes, dynamische blokken en gerelateerde productregels te informeren, raadpleegt u [Audience Activation](https://experienceleague.adobe.com/docs/commerce-admin/customers/audience-activation.html#retrieve-audiences-using-the-adobe-experience-platform-mobile-sdk).
