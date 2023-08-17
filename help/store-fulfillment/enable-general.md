---
title: Algemene configuratie
description: Algemene instellingen configureren voor inschakelen [!DNL Store Fulfillment] voor uw winkel. Configureer algemene extensie-instellingen, systeeminstellingen voor registratie, gegevenssynchronisatie en beveiliging. Belangrijke gegevens leveren om de integratie tussen Adobe Commerce en Store Fulfillment Services mogelijk te maken.
role: Admin
level: Intermediate
exl-id: 51dcfc95-3dd6-40d9-bd26-d8409a25f3c8
source-git-commit: 36b57648e156ead801764f3ee4e5e6a0f3245fe6
workflow-type: tm+mt
source-wordcount: '2419'
ht-degree: 0%

---

# Winkelservice en verkoopconfiguratie

Inschakelen [!DNL Store Fulfillment] van de [!DNL Commerce] Beheer door extensie-instellingen te configureren, de beveiligingsinstellingen voor gebruikers van de app Store Assist en de opties voor de leveringsmethode.

>[!IMPORTANT]
>
>De configuratie van de service Afhandeling opslaan is alleen van toepassing nadat u een verbinding hebt gemaakt met uw Adobe Commerce-instantie en de [!DNL Store Fulfillment] app. Zie [Afhandeling van Connect Store](connect-set-up-service.md).

## Instellingen voor services voor winkeluitvoering beheren

Instellingen beheren voor services voor winkelvervulling via de [!DNL Commerce Admin Store Configuration] -menu.

- Schakel de extensie in, configureer algemene instellingen en geef beveiligingsopties op voor gebruikersverbindingen en accounts van de app Store Assist door **[!UICONTROL Stores > Configuration > Services > Store Fulfillment by Walmart Commerce Technologies]**.

  ![Configuratie van beheerderswinkelservices voor winkeluitvoering](assets/store-services-admin-sf-config.png)

- Vorm leveringsmethodes door te selecteren **[!UICONTROL Store > Configuration > Sales > Delivery Methods > In-Store Pickup]**.

  ![Verkoopconfiguratie voor winkel beheren voor winkeluitvoering](assets/store-sales-admin-sf-deliver-config.png)

## Basisinstellingen

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Price]</strong></td>
<td>De prijs die u de klant in rekening brengt voor het ophalen in de winkel. Heeft als standaardwaarde nul.</td>
<td>Website</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Search Radius]</strong></td>
<td>De straal, in kilometers, die moet worden gebruikt wanneer een verkoopster zoekt naar een locatie voor het ophalen van een winkel in het winkeluitchecken. De zoekresultaten retourneren alleen opslagruimten die zich binnen de opgegeven zoekstraal bevinden.</td>
<td>Website</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Displayed error message]</strong></td>
<td>Bericht dat toont wanneer een klant in-store bestelwagen voor een punt selecteert dat niet beschikbaar voor in-store bestelwagen is. U kunt de standaardtekst desgewenst aanpassen.
</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody>
</table>

>[!NOTE]
>
>De [!UICONTROL Search Radius] het plaatsen wordt gebruikt slechts als u hebt gevormd [opslaglocatie en toewijzing instellen](store-location-map-provider-setup.md) voor Adobe Commerce.

## De oplossing voor winkelvervulling inschakelen

De optie [!DNL Store Fulfillment] -oplossing om de mogelijkheden voor in-store en curbside ophalen toe te voegen aan de inkoop- en uitcheckervaringen in uw Adobe Commerce-winkel.

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL Enabled]</strong></td>
<td>Schakel de oplossing in of uit. Indien ingeschakeld, configureert en gebruikt u de mogelijkheden van Store Fulfillment en maakt u de verbinding tussen uw Adobe Commerce-winkel en [!DNL Store Fulfillment] diensten. Als deze optie is uitgeschakeld, zijn alle functies van Afhandeling van winkel uitgeschakeld en is er geen communicatie tussen Adobe Commerce en de service Afhandeling van winkel. Bestelgegevens kunnen niet worden verwerkt of ontvangen.</td>
<td>Website</td>
<td>Ja</td>
</tr>
</tbody>
</table>

## Accountgegevens toevoegen

<table>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
<tr>
<td><strong>[!UICONTROL Environment]</strong></td>
<td>Selecteer een van beide <i>[!UICONTROL Sandbox]</i> of <i>[!UICONTROL Production]</i><br></br>Selecteren [!UICONTROL Sandbox] maakt communicatie met uitvoeringsdiensten in een testomgeving mogelijk.<br></br>Selecteren [!UICONTROL Production] maakt communicatie met uitvoeringsdiensten in een live omgeving mogelijk.<br></br>U krijgt een reeks geloofsbrieven voor elke milieu en kunt beide reeksen in de zelfde installatie beheren. <br></br>Sla de gegevens op voordat u de verbinding valideert.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL API Server URL]</strong></td>
<td>De URL naar het eindpunt van de Fulfillment API van de Winkel van de Marm. De waarde moet de volledig gekwalificeerde URL zijn die tijdens het instapproces wordt verstrekt. Klanten die aan Afhandeling van winkels werken, ontvangen zowel een sandbox- als een productie-URL. Wanneer u de waarden toevoegt, moet u de volledige URL kopiëren en plakken, inclusief de schuine streep "/".</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Token Auth Server URL]</strong></td>
<td>URL aan het eindpunt van de Authentificatie van de Opslag van de Marm. De waarde moet de volledig gekwalificeerde URL zijn die tijdens het instapproces wordt verstrekt. U ontvangt zowel een sandbox als een productie-URL. Wanneer u de waarden toevoegt, moet u de volledige URL kopiëren en plakken, inclusief de schuine streep "/".</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Merchant Id]</strong></td>
<td>Uw unieke bedrijfs-id (huurder) die tijdens het instapproces is opgegeven. Deze identiteitskaart wordt gebruikt aan routeorden om ervoor te zorgen dat uw handelaarsopslag hen ontvangt.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Consumer Id]</strong></td>
<td>De unieke integratie-id die tijdens het instapproces wordt opgegeven. Deze id wordt gebruikt om alle communicatie tussen Adobe Commerce te verifiëren en uitvoeringsservices op te slaan.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Consumer Secret]</strong></td>
<td>De unieke integratietoets die tijdens het instapproces wordt geleverd. Deze sleutel wordt gebruikt om alle communicatie tussen Adobe Commerce en de dienst van de opslagvervulling voor authentiek te verklaren.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
</table>

Nadat u vormt [!UICONTROL Account Credentials], selecteert u <strong>[!UICONTROL Validate Credentials]</strong> om een verbinding aan de dienst van de archiefvervulling voor het eerst te verifiëren en te vestigen.

## Logboek configureren

Logbestanden voor services voor winkelvervulling zijn beschikbaar in het logbestand `var/log/walmart-bopis.log`.

Vraag de systeembeheerder om uw milieu&#39;s te vormen om uitzonderingsbehandeling toe te staan zodat API-verwante uitzonderingen door de firewall of het geheime voorgeheugen kunnen worden gevangen.

Omdat het dossier van het toepassingslogboek snel kan groeien, laat registreren voor de toepassing slechts voor een korte tijd toe wanneer nodig-voor voorbeeld wanneer het oplossen van problemen de kwesties van de opslagvervulling voor een [!DNL Commerce] bestelling. Deze configuratie voorkomt problemen met de responstijd in productieomgevingen die worden veroorzaakt door grote logbestanden.

>[!TIP]
>
>Voor Adobe Commerce-installaties op locatie vraagt u de systeembeheerder om logrotatie voor de installatie van `var/log/walmart-bopis.log` bestand om de grootte te minimaliseren. Voor Adobe Commerce-installaties ter plaatse gaat u naar [Logrotatie](https://experienceleague.adobe.com/docs/commerce-operations/installation-guide/next-steps/configuration.html#server-settings) in de _Adobe Commerce-installatiehandleiding_. Voor Adobe Commerce over infrastructuurprojecten in de cloud gaat u naar [Logbestanden weergeven en beheren](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/develop/test/log-locations.html).

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Debug Mode]</strong></td>
<td>Zuiver Wijze wordt gebruikt om de geregistreerde activiteit binnen de integratie te verhogen. Als deze optie is uitgeschakeld, wordt er geen foutopsporingsinformatie geregistreerd. Wanneer toegelaten, wordt al zuivert informatie geregistreerd <br></br>Alle geregistreerde gegevens zijn te vinden in het bestand: <pre>var/log/walmart-bopis.log</pre>
<td>Algemeen</td>
<td>Nee</td>
</tr>
</tbody>
</table>

## Ordersynchronisatie beheren

Configureer de instellingen voor het beheer van foutafhandeling voor ordersynchronisatie, cataloguskenmerken die moeten worden gebruikt voor het scannen van streepjescodes tijdens het selecteren van bestellingen, en configureer de batchformaten voor de wachtrij met opslagtegoeden.

U kunt details over de verrichtingen van de ordesynchronisatie van het dashboard van het Beheer van de Rij van de Opslag in Admin bekijken (
<strong>[!UICONTROL System > Tools > Store Fulfillment Queue]</strong>).

### Synchronisatie-foutbeheer

<table>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
<tr>
<td><strong>[!UICONTROL Retry Critical Error]</strong></td>
<td>Hiermee worden de pogingen voor het opnieuw proberen van een recordsynchronisatiebewerking opgegeven nadat een kritieke fout is opgetreden.<br></br>De kritieke fouten komen voor wanneer de integratie er niet in slaagt een positieve reactie van de uitvoeringsdienst te krijgen. Deze kwesties komen voor wanneer de dienst neer is, of wanneer er een fout in de ordegegevens is die worden verzonden.<br></br>Wanneer de drempel voor opnieuw proberen is bereikt, blijft het item in een wachtrij maar wordt het niet opnieuw verwerkt. Alle items weergeven met fouten van <strong>[!UICONTROL System > Tools > Store Fulfillment Queue]</strong> Beheer in de beheerder. Neem contact op met uw accountmanager om problemen op te lossen met onderdelen die op consistente wijze mislukken.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Error Notification Email]</strong></td>
<td>Schakel foutmeldingen in om een e-mailbericht te ontvangen wanneer de [!UICONTROL Retry Critical Error Threshold] wordt bereikt voor een bestelling. Het bericht bevat alle beschikbare gegevens over de fout.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Send Error Notification Email To]</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen van ontvangers voor foutmeldingen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Order Sync Exception Email Template]</strong></td>
<td>Hier geeft u de e-mailsjabloon op die wordt gebruikt om ontvangers op de hoogte te stellen van fouten bij de synchronisatie van bestellingen. Er is een standaardsjabloon beschikbaar. Aanpassing wordt niet ondersteund.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</table>

### Ordersynchronisatie

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Barcode Source]</strong></td>
<td>Het cataloguskenmerk dat de scannbare code voor overeenkomende items opslaat op uw bedrijfslocaties.<br></br>Als u slechts één bestaande handelsplaats hebt, is het waarschijnlijk dat u codes UPC gebruikt, terwijl uw e-commercekanaal producten door SKU identificeert. In dit scenario, selecteer het catalogusattribuut dat de code UPC bevat.<br></br>Deze instelling zorgt ervoor dat bestellingen die naar de items in de winkellijst worden verzonden met de juiste id, zodat de opslagpartners items tijdens het plukproces op nauwkeurige wijze kunnen scannen.<br></br>Als u onzeker bent, controleer met uw uitvoeringsvennoten in de Verzending en het Schoppen afdeling om te bepalen welke attributen zouden moeten worden verzonden. Als het kenmerk momenteel niet is opgenomen in de database, kunt u het kenmerk toevoegen aan de set Adobe Commerce-productkenmerken.</td>
<td>Website</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Barcode Type]</strong></td>
<td>Het cataloguskenmerk dat de bron van de streepjescode voor overeenkomende items opslaat op uw bedrijfslocaties.<br></br>Met deze instelling zorgt u ervoor dat bestellingen die naar de items in de winkellijst met de juiste id worden verzonden, zodat de opslagpartners items tijdens het plukproces op nauwkeurige wijze kunnen scannen. De opties omvatten - SKU, UPC, GTIN, UPCA, EAN13, UPCE0, DISA, UAB, CODABAR, Price Embedded UPC.<br></br>Als u niet zeker weet, selecteert u de optie die het meest lijkt op de waarden in uw [!UICONTROL Barcode Source] kenmerk. Associaten van winkels kunnen nog steeds handmatig overeenkomen met items in hun keuzelijst.</td>
<td>Website</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Max Number of Items]</strong></td>
<td>Het maximumaantal items dat in één keer uit de wachtrij voor winkelvervulling moet worden verzonden.<br></br>BOPIS-orders worden op regelmatige tijdstippen batchgewijs naar de uitvoeringsdienst verzonden. Met deze instelling kunt u de grootte van de batch bepalen.<br></br>De standaardwaarde is 100 items. Afhankelijk van het volume en de capaciteit van uw bestelling kunt u de maximale waarde naar boven of naar beneden aanpassen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
</tbody>
</table>

## Verzendopties voor winkelvervulling inschakelen

Configureer de verzendopties voor de afhandeling van winkels die de beschikbaarheid bepalen van opties voor het ophalen en leveren van items in de winkel voor uw Adobe Commerce-winkels.

### Verzenden naar winkel

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Enable Ship To Store]</strong></td>
<td>De instelling voor het naar de winkel verzenden van verzendingen is gebaseerd op uw bestaande verzendmogelijkheden. Als u Inventory management gebruikt, of als u bestellingen kunt accepteren en uitvoeren op zakelijke locaties zonder voorraad via voorraadoverdrachten van winkel naar winkel, stelt u deze optie in op Ja.<br></br>Als u geen ondersteuning kunt bieden voor de optie voor het aan boord brengen van een schip of deze niet wilt aanbieden, stelt u deze in op "Nee". Als deze optie is uitgeschakeld, worden items in uw catalogus met een nulvoorraad voor een winkel of items die onder de [!DNL Out of Stock Threshold] voor die locatie, worden niet aangeboden met opties voor in-store ophalen.<br></br>U kunt de waarde van deze instelling per bedrijfslocatie aanpassen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
</tbody>
</table>

### Verzenden uit winkel

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
</thead>
<tbody>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong></td>
<td>Schakelt de optie Home Delivery in of uit in uw winkels. Als deze optie is ingeschakeld, worden de locaties van uw winkels beschouwd als zijnde geaggregeerd met andere toegewezen bronnen in het bestand dat aan uw website is gekoppeld.<br></br>In de standaard Inventory management-services wordt [!DNL Ship from Store] Deze optie is inherent en kan niet worden uitgeschakeld. Met de oplossing Afhandeling bewaren kunt u deze in- of uitschakelen.<br></br>U kunt deze instelling per bedrijfslocatie en product aanpassen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
</tbody>
</table>


## Gebruik accounts en machtigingen voor winkeluitvoering App beheren

Configureer de instellingen voor de gebruikersaccount en wachtwoordbeveiliging van de Store Fulfillment App en verificatie met twee factoren.

### Toepassingsbeveiliging

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL User Session Lifetime]</strong></td>
<td>Het tijdframe, in seconden, dat een gebruikerssessie met een aan een winkel gekoppelde gebruiker actief blijft voordat deze automatisch wordt afgemeld. Geldige waarden liggen tussen 60 en 31536000.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Maximum Login Failures to Lockout Account]</strong></td>
<td>Hiermee geeft u het aantal mislukte aanmeldpogingen op dat is toegestaan voordat een aan een winkel gerelateerde persoon uit zijn of haar account is vergrendeld.<br></br>Stel de waarde in op 0 als u het afsluiten van een account wilt uitschakelen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Lockout Time (minutes)]</strong></td>
<td>Aantal minuten om een account te vergrendelen na mislukken van aanmelding.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Force Password Change]</strong></td>
<td><em>[!UICONTROL Yes]</em>: Vereisen dat de gebruiker zijn wachtwoord wijzigt na het instellen van de account.<br></br><em>[!UICONTROL No]</em>: raadt aan dat de gebruiker het wachtwoord wijzigt na het instellen van de account.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Password Lifetime]</strong></td>
<td>Het aantal dagen dat een wachtwoord geldig blijft voordat een vereist wachtwoord wordt gewijzigd. Laat leeg om deze optie uit te schakelen.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
</tbody>
</table>

## Leveringsmethoden

Store Fulfillment werkt door de native Adobe Commerce uit te breiden [!DNL In-Store Delivery] mogelijkheden. Nadat u de extensie hebt geïnstalleerd, kunt u in-store leveringsmethoden configureren met behulp van de volgende uitgebreide instellingen die aan Admin worden toegevoegd.

- **Ophalen in de winkel**—De opties van de aanbieding voor in-store levering tijdens het controleproces Deze montages vormen de gemeenschappelijkste leveringsscenario&#39;s voor bevelen BOPIS.

- **[!UICONTROL Curbside pick up]**- De opties van de aanbieding voor klanten om bij een opslagplaats te parkeren en hun orde te hebben die aan hen door een archiefvengeassocieerde wordt geleverd.

Configureer deze instellingen vanuit de beheerder door <strong>[!UICONTROL Stores > Configuration > Sales > Delivery Methods > In-Store Pickup]</strong>.

>[!NOTE]
>
>Voor meer informatie over het vormen van in-store leveringsopties, zie [In-Store levering](https://docs.magento.com/user-guide/shipping/shipping-in-store-delivery.html) in de _Adobe Commerce-gebruikershandleiding_.


### Configuratie van leveringsmethoden

Met de in-store leveringsmethode, kan de klant een bron selecteren die als oppiklocatie tijdens het uitrekenen moet worden gebruikt.

<table>
<thead>
<tr>
<td><strong>Veld</strong></td>
<td><strong>Beschrijving</strong></td>
<td><strong>Toepassingsgebied</strong></td>
<td><strong>Vereist</strong></td>
</tr>
 </thead>
 <tbody>
<tr>
<td><strong>[!UICONTROL Enable In-Store Pickup]</strong></td>
<td>Schakel de optie Ophalen in de winkel die tijdens het uitchecken beschikbaar is in of uit voor klanten die Ophalen uit de winkel kiezen. Wanneer het ophalen in de winkel is uitgeschakeld, wordt de optie niet weergegeven.<br></br>Deze globale instelling is van toepassing op alle winkellocaties in de detailhandel. Wanneer toegelaten, kunt u het bij de detailhandel plaats selectief onbruikbaar maken.</td>
<td>Website</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Curbside Pickup]</strong></td>
<td>Schakel de optie Ophalen curven tijdens het uitrekenen in of uit voor klanten die Ophalen van winkel kiezen.<br></br>Deze globale instelling is van toepassing op alle winkellocaties in de detailhandel. Wanneer toegelaten, kunt u het bij de detailhandel plaats selectief onbruikbaar maken.</td>
<td>Website</td>
<td>Nee</td>
</tr>
</tbody>
</table>

### Configuratie van titel leveringsmethode

<table>
<thead>
<tr>
<th><strong>Veld</strong></th>
<th><strong>Beschrijving</strong></th>
<th><strong>Toepassingsgebied</strong></th>
<th><strong>Vereist</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>Titel van thuislevering</strong></td>
<td>Hier geeft u de titel op die u wilt weergeven voor de optie Home Delivery in de producten-, winkelwagentje- en afrekengebieden. De levering van het huis verwijst naar de standaardverzendmogelijkheden van Adobe Commerce-van een pakhuis, door een drager, of direct aan het klant-verstrekte verzendadres. </br></br>Dit label heeft geen invloed op de labels van de verzendmethode voor de geselecteerde verzendende vervoerder.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Beschrijving van thuislevering</strong></td>
<td>Een optionele beschrijving die wordt weergegeven wanneer de Titel van thuislevering aan klanten wordt getoond. Meestal, is de beschrijving een statisch bericht om uw leveringsbeloftes mee te delen. Enkele voorbeelden:</br><code>Same-day shipping on orders by 4</code></br></br><code>Ships within 2 business days</code></td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Titel voor ophalen van winkel</strong></td>
<td>Wanneer een klant leveringsopties wordt voorgesteld en de opname in de winkel beschikbaar is, wordt dit etiket getoond. </br></br>U kunt dit label aanpassen, dat wordt weergegeven in de producten-, winkelwagentje- en afhandelingsgebieden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>Ophaalbeschrijving van winkel</strong></td>
<td>Waar de titel Ophalen winkel wordt weergegeven, kun je eventueel een beschrijving opnemen. Dit statische bericht helpt klantenmededelingen met betrekking tot de ervaring van de archiefbestelwagen verbeteren. Enkele voorbeelden:</br></br><code>Get it today for free!</code></br></br><code>Ready for pickup in an hour!</code></td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Titel voor ophaalservice in de winkel</strong></td>
<td>Wanneer Ophalen in de winkel is ingeschakeld, wordt deze titel aan klanten weergegeven als de optie Ophalen uit de winkel. U kunt het label ervan aanpassen.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<tr>
<td><strong>Titel voor ophalen krullen</strong></td>
<td>Wanneer de Bestelwagen van de Band wordt toegelaten, wordt de optie getoond aan klanten als een type van de optie van de Bestelwagen van de Opslag. U kunt het label hier aanpassen.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Instructies voor het in-store ophalen</strong></td>
<td>Wanneer een bestelling klaar is om in uw winkels te worden opgehaald, wordt de klant per e-mail op de hoogte gebracht. Als de klant [!DNL In-Store Pickup] tijdens het uitchecken kunt u hier de instructies voor het ophalen aanpassen. </br></br>Deze instructies worden globaal ingesteld en zijn van toepassing op alle winkellocaties. U kunt de instructies ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Instructies voor ophaalcurven</strong></td>
<td>Geeft aangepaste instructies voor het ophalen van bestellingen op die moeten worden opgenomen in e-mailmeldingen van klanten voor bestellingen voor het ophalen van bestellingen op de achtergrond. </br></br>Deze instructies worden globaal ingesteld en zijn van toepassing op alle winkellocaties. U kunt de instructies ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Geschatte levertijd voor afhalen</strong></td>
<td>Het aantal minuten dat is vereist voordat een bestelling is ontvangen, uitgevoerd en klaar om te worden opgehaald. Deze informatie wordt aan de klant getoond wanneer het selecteren van een detailhandelplaats voor de leveringsoptie van de Opslag van de Opslag. Deze instelling geldt voor alle winkellocaties. U kunt de aanlooptijd ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Label voor geschatte ophaaltijd</strong></td>
<td>Hiermee geeft u de geschatte tijd weer tot een bestelling beschikbaar is voor het ophalen door de klant. Deze informatie wordt aan klanten getoond wanneer zij een detailhandelplaats voor [!DNL In-Store Pickup] leveringsoptie. </br></br>Wanneer u dit label aanpast, kunt u de code <code>%1</code> om uw <strong>Geschatte levertijd voor afhalen</strong>. Bijvoorbeeld:</br></br><code>Ready for Pickup in %1 minutes.</code></br></br>Deze instelling geldt voor alle winkellocaties. U kunt de aanlooptijd ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
<tr>
<td><strong>Disclaimer ophaaltijd</strong></td>
<td>De inhoud die wordt weergegeven op de productpagina in de knopinfo met winkeluren, feestdagen, onverwachte sluitingen enzovoort</td>
<td>Winkelweergave
</td>
<td>Nee
</td>
</tr>
</tbody></table>

### Configuratie Beschikbaarheid voorraad

<table>
<thead>
<tr>
<th><strong>Veld</strong></th>
<th><strong>Beschrijving</strong></th>
<th><strong>Toepassingsgebied</strong></th>
<th><strong>Vereist</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>In voorraad</strong></td>
<td>Wanneer een klant de detailhandel locator gebruikt, wordt de voorraadbeschikbaarheid voor de huidige punten getoond voor elke plaats. </br></br>U kunt de <em>[!UICONTROL in-stock]</em> status label hier.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Buiten de voorraad</strong></td>
<td>Wanneer een klant de detailhandel locator gebruikt, wordt de voorraadbeschikbaarheid voor om het even welke huidige punten getoond voor elke plaats.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Gedeeltelijk in voorraad</strong></td>
<td>Wanneer een klant de locator van de detailhandel gebruikt, wordt de voorraadbeschikbaarheid voor om het even welke huidige punten getoond voor elke plaats. </br></br>U kunt de <em>[!UICONTROL partially in-stock]</em> status label hier.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>

