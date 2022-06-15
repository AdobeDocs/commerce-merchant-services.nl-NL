---
title: Algemene configuratie
description: '"Algemene instellingen configureren om in te schakelen [!DNL Store Fulfillment] voor uw winkel. Configureer algemene extensie-instellingen, systeeminstellingen voor registratie, gegevenssynchronisatie en beveiliging. Belangrijke gegevens leveren om de integratie tussen Adobe Commerce en Store Fulfillment Services mogelijk te maken."'
role: User, Admin
level: Intermediate
source-git-commit: 42b0118b427b1e04186793b4a57c058bc1cabdd4
workflow-type: tm+mt
source-wordcount: '2413'
ht-degree: 0%

---


# Algemene configuratie

In de handel Admin van Adobe, vorm algemene configuratiemontages om toe te laten [!DNL Store Fulfillment] de diensten voor uw opslag, vormen globale uitbreidingsmontages en verstrekken zeer belangrijke gegevens voor de integratie door te vormen [!UICONTROL Account Credentials].

De integratie moet verbonden zijn met de dienst van de Afhandeling van de Opslag. Configureer ook de algemene instellingen voor winkelvervulling om de services voor winkelvervulling in te schakelen en aan te passen op basis van de mogelijkheden en operationele vereisten van uw organisatie.

De algemene configuratie voor [!DNL Store Fulfillment] bevat de volgende configuratie-instellingen:

- [De oplossing inschakelen](#enable-the-store-fulfillment-solution)
- [Accountgegevens beheren om verbinding te maken met de service Afhandeling van winkel](#account-credentials)
- [Logboekregistratie configureren](#configure-logging)
- [Opties instellen voor het beheer van de volgorde en de synchronisatie van fouten](#order-synchronization)
- [Verzendopties voor winkelvervulling inschakelen](#enable-store-fullment-shipping-options)
- [Beveiligings- en verificatie-instellingen configureren voor de Store Fulfillment App](#store-fulfillment-app)
- [Beschikbaarheid en configuratie van leveringsmethode instellen](#in-store-delivery-methods)

## De oplossing voor winkelvervulling inschakelen

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enabled]** | Schakel de oplossing in of uit. Indien deze optie is ingeschakeld, configureert en gebruikt u de mogelijkheden voor het afhandelen van winkels en maakt u een verbinding tussen uw Adobe Commerce-winkel en de services voor het afhandelen van winkels. Als deze optie is uitgeschakeld, zijn alle functies voor het afhandelen van winkels uitgeschakeld en is er geen communicatie tussen Adobe Commerce en de services voor het afhandelen van winkels. Bestelgegevens kunnen niet worden verwerkt of ontvangen. | Algemeen | Ja |

Als u deze instelling wilt voltooien, raadpleegt u **Stores → Configuration → Services → Store Fulfillment by Walmart Commerce Technologies**.

## Accountreferenties toevoegen

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Environment]** | Kan selecteren *Sandbox* of *Productie*:</br> Sandbox communiceert met de uitvoeringsdiensten in een test.</br>De productie communiceert met een levende milieu. Gebruiken **alleen** in productie.</br>U krijgt een reeks geloofsbrieven voor elke milieu en kunt beide reeksen in de zelfde installatie beheren. </br></br>Sla referenties op voordat u de verbinding valideert. | Algemeen | Ja |
| **[!UICONTROL API Server URL]** | De URL naar het eindpunt van de Fulfillment API van de Winkel van de Marm. Dit moet volledig-gekwalificeerde URL zijn die aan u tijdens uw aan boord nemend proces wordt verstrekt. Klanten die aan Afhandeling van winkels werken, ontvangen zowel een sandbox- als een productie-URL. Kopieer/plak de volledige URL, inclusief de schuine streep &quot;/&quot;. | Algemeen | Ja |
| **[!UICONTROL Token Auth Server URL]** | URL aan het eindpunt van de Authentificatie van de Opslag van de Marm. De waarde moet volledig-gekwalificeerde URL zijn die aan u tijdens uw aan boord nemend proces wordt verstrekt. U ontvangt zowel een sandbox als een productie-URL. Kopieer/plak de volledige URL, inclusief slash aan het einde `/`&quot;. | Algemeen | Ja |
| **[!UICONTROL Merchant Id]** | Uw unieke bedrijfs-id (huurder) die u tijdens het instapproces hebt ontvangen. Uw id wordt gebruikt om uw bestellingen te routeren en zorgt ervoor dat uw winkels deze ontvangen. | Algemeen | Ja |
| **[!UICONTROL Consumer Id]** | Uw unieke integratie-id. Dit wordt aan u verstrekt tijdens uw aan boord gaan proces. Dat verandert niet. Het wordt gebruikt om al mededeling met de uitvoeringsdiensten voor authentiek te verklaren. | Algemeen | Ja |
| **[!UICONTROL Consumer Secret]** | Uw unieke integratiesleutel. Dit wordt aan u verstrekt tijdens uw aan boord gaan proces. Het wordt gebruikt om al mededeling met de uitvoeringsdiensten voor authentiek te verklaren. | Algemeen | Ja |

Nadat u de Account Credentials hebt geconfigureerd, selecteert u **[!UICONTROL Validate Credentials]** voor het eerst een verbinding met de uitvoeringswebservice te verifiëren en tot stand te brengen.

## Logboekregistratie configureren

Wanneer het registreren wordt toegelaten, kan uw logboekdossier snel uitbreiden. Om de kwesties van de reactietijd in productiemilieu&#39;s te verhinderen, ben zorgvuldig over het toelaten van registreren, en laat slechts voor een korte tijd toe wanneer nodig.

Vraag de systeembeheerder om uw milieu&#39;s te vormen om uitzonderingsbehandeling toe te staan zodat API-verwante uitzonderingen door de firewall of het geheime voorgeheugen kunnen worden gevangen. U kunt ook uw systeembeheerder vragen om logrotatie voor dit bestand in te stellen om de grootte te minimaliseren.

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **Foutopsporingsmodus** | Zuiver Wijze wordt gebruikt om de geregistreerde activiteit binnen de integratie te verhogen. Als deze optie is uitgeschakeld, wordt er geen foutopsporingsinformatie geregistreerd. Wanneer toegelaten, wordt al zuivert informatie geregistreerd.</br> Alle geregistreerde gegevens zijn te vinden in bestand: `var/log/walmart-bopis.log` | Algemeen | Nee |

## Ordersynchronisatie beheren

Configureer de instellingen voor het beheer van foutafhandeling voor ordersynchronisatie, cataloguskenmerken die moeten worden gebruikt voor het scannen van streepjescodes tijdens het selecteren van bestellingen, en configureer de batchformaten voor de wachtrij met opslagtegoeden.

U kunt details over de verrichtingen van de ordesynchronisatie van het dashboard van het Beheer van de Rij van de Opslag in Admin bekijken (
**[!UICONTROL System > Tools > Store Fulfillment Queue]**).

### Synchronisatie-foutbeheer

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|--------------|
| **Kritieke fout opnieuw proberen** | Hiermee worden de pogingen voor het opnieuw proberen van een recordsynchronisatiebewerking opgegeven nadat een kritieke fout is opgetreden.</br></br>De kritieke fouten komen voor wanneer de integratie er niet in slaagt een positieve reactie van de uitvoeringsdienst te krijgen. Dit kan voorkomen wanneer de dienst neer is of wanneer er een fout in de ordegegevens die wordt verzonden is.</br></br>Wanneer de drempel voor opnieuw proberen is bereikt, blijft het item in een wachtrij maar wordt het niet opnieuw verwerkt. Alle items weergeven met fouten van **[!UICONTROL System → Tools → Store Fulfillment Queue]** Beheer in de beheerder. Neem contact op met uw accountmanager om problemen op te lossen met onderdelen die op consistente wijze mislukken. | Algemeen | Nee |
| **E-mail met foutmelding inschakelen** | Schakel foutmeldingen in om een e-mailbericht te ontvangen wanneer de [!UICONTROL Retry Critical Error Threshold] wordt bereikt voor een bestelling. Het bericht bevat alle beschikbare gegevens over de fout. | Algemeen | Nee |
| **Foutmelding verzenden naar** | Een door komma&#39;s gescheiden lijst met e-mailadressen van ontvangers voor foutmeldingen. | Algemeen | Nee |
| **Exception-e-mailsjabloon bestellen** | Hier geeft u de e-mailsjabloon op die wordt gebruikt om ontvangers op de hoogte te stellen van fouten bij de synchronisatie van bestellingen. Er is een standaardsjabloon beschikbaar. Aanpassing wordt niet ondersteund. | Winkelweergave | Nee |

### Ordersynchronisatie

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Barcode Source]** | Het cataloguskenmerk dat de scannbare code voor overeenkomende items opslaat op uw bedrijfslocaties.</br></br>Als u slechts één bestaande handelsplaats hebt, is het waarschijnlijk dat u codes UPC gebruikt, terwijl uw e-commercekanaal producten door SKU identificeert. Als dit uw scenario is, selecteer het catalogusattribuut dat de code UPC bevat.</br></br>Deze instelling zorgt ervoor dat orders die naar uw leverancier worden verzonden, lijstitems met de juiste id opslaan, zodat de opslagpartners items tijdens het plukproces nauwkeurig kunnen scannen.</br></br>Als u onzeker bent, controleer met uw uitvoeringsvennoten in de Verzending en het Schoppen afdeling om te bepalen welke attributen zouden moeten worden verzonden. Mogelijk moet u het juiste kenmerk toevoegen aan de set Adobe Commerce-productkenmerken als het kenmerk momenteel niet in de database is opgenomen. | Website | Ja |
| **[!UICONTROL Barcode Type]** | Het cataloguskenmerk dat de bron van de streepjescode voor overeenkomende items opslaat op uw bedrijfslocaties.</br></br>Deze instelling zorgt ervoor dat orders die naar uw leverancier worden verzonden, lijstitems met de juiste id opslaan, zodat de opslagpartners items tijdens het plukproces op nauwkeurige wijze kunnen scannen. De opties omvatten - SKU, UPC, GTIN, UPCA, EAN13, UPCE0, DISA, UAB, CODABAR, Price Embedded UPC.</br></br>Als u niet zeker weet, selecteert u de optie die het meest lijkt op de waarden in uw [!UICONTROL Barcode Source] kenmerk. Associaten van winkels kunnen nog steeds handmatig overeenkomen met items in hun keuzelijst. | Website | Ja |
| **[!UICONTROL Max Number of Items]** | Het maximumaantal items dat in één keer uit de wachtrij voor winkelvervulling moet worden verzonden.</br></br>BOPIS-orders worden op regelmatige tijdstippen batchgewijs naar de uitvoeringsdienst verzonden. Met deze instelling kunt u de grootte van de batch bepalen.</br></br>De standaardwaarde is 100 items. Afhankelijk van het volume en de capaciteit van uw bestelling moet u deze waarde mogelijk omhoog of omlaag aanpassen. | Algemeen | Nee |


## Verzendopties voor winkelvervulling inschakelen

Configureer de verzendopties voor de afhandeling van winkels die de beschikbaarheid bepalen van opties voor het ophalen en leveren van items in de winkel voor uw Adobe Commerce-winkels.

### Verzenden naar winkel

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable Ship To Store]** | De instelling van het verzendings-naar-archief maakt gebruik van uw bestaande verzendmogelijkheden. Als u Inventory management gebruikt, of als u bestellingen kunt accepteren en uitvoeren op zakelijke locaties zonder voorraad via voorraadoverdrachten van winkel naar winkel, stelt u deze optie in op `Yes`.</br></br>Als u geen ondersteuning kunt bieden voor de optie voor het verzenden van objecten naar een winkel of deze niet wilt aanbieden, kunt u instellen op `No`. Als deze optie is uitgeschakeld, worden items in uw catalogus met een nulvoorraad voor een winkel of items die onder die locatie liggen [!DNL Out of Stock Threshold], worden niet aangeboden met opties voor in-store ophalen.</br></br>Dit is een algemene instelling die per bedrijfslocatie kan worden aangepast. | Algemeen | Nee |

### Verzenden uit winkel

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable Ship From Store]** | Schakelt de optie Home Delivery in of uit in uw winkels. Als deze optie is ingeschakeld, worden de locaties van uw winkels beschouwd als zijnde geaggregeerd met andere toegewezen bronnen in het bestand dat aan uw website is gekoppeld.</br></br>In de standaard Inventory management-services wordt [!DNL Ship from Store] Deze optie is inherent en kan niet worden uitgeschakeld. Met de Oplossing van de Afhandeling van de Opslag, hebt u de optie om het of uit te zetten.</br></br>Dit is een globale instelling. U kunt deze instelling ook per bedrijfslocatie en product aanpassen. | Algemeen | Nee |


## Gebruik accounts en machtigingen voor winkeluitvoering App beheren

Configureer de instellingen voor de gebruikersaccount en wachtwoordbeveiliging van de Store Fulfillment App en verificatie met twee factoren.

### Toepassingsbeveiliging

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL User Session Lifetime]** | Het tijdframe, in seconden, dat een gebruikerssessie met een aan een winkel gekoppelde gebruiker actief blijft voordat deze automatisch wordt afgemeld. Geldige waarden liggen tussen 60 en 31536000. | Algemeen | Nee |
| **[!UICONTROL Maximum Login Failures to Lockout Account]** | Hiermee geeft u het aantal mislukte aanmeldpogingen op dat is toegestaan voordat een aan een winkel gerelateerde persoon uit zijn of haar account is vergrendeld.</br></br>Stel de waarde in op 0 als u het afsluiten van een account wilt uitschakelen. | Algemeen | Nee |
| **[!UICONTROL Lockout Time (minutes)]** | Aantal minuten om een account te vergrendelen na mislukken van aanmelding. | Algemeen | Nee |
| **[!UICONTROL Force Password Change]** | Hiermee wordt bepaald of een wijziging van het gebruikerswachtwoord is vereist.</br></br>`Yes`: Vereisen dat de gebruiker zijn wachtwoord wijzigt na het instellen van de account.</br>`No`: raadt de gebruiker aan het wachtwoord te wijzigen na het instellen van de account. | Algemeen | Nee |
| **Wachtwoordlevensduur** | Het aantal dagen dat een wachtwoord geldig blijft voordat een vereist wachtwoord wordt gewijzigd. Laat leeg om deze optie uit te schakelen. | Algemeen | Nee |

### Twee-factor authentificatie

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **APP-gebruiker 2FA** | Schakel verificatie met twee factoren in of uit voor opslagassociaties. Wanneer toegelaten, wordt de opslagvennoot ertoe aangezet om een eenmalig wachtwoord te verstrekken dat door een authentificatieleverancier wordt geproduceerd. | Algemeen | Nee |
| **APP 2FA-beleid** | Plaatst het handhavingsbeleid voor tweefelige authentificatie.</br></br>**[!UICONTROL Optional]**: De opslagvennoot kan bifactorauthentificatie overslaan als geen leverancier wordt geplaatst.</br></br>**[!UICONTROL Mandatory]**: De opslagvennoot wordt vereist om twee-factor authentificatie te voltooien. | Algemeen | Nee |
| **2FA-providers** | Selecteer één of meerdere diensten van de authentificatieleverancier om archiefassociaties aan te bieden. Als u verificatie met twee factoren wilt instellen en verifiëren, moeten de partners van de winkel de verificatie-app installeren van een van de beschikbare providers die op hun mobiele apparaten zijn geïnstalleerd. | Algemeen | Nee |

### Leveringsmethoden

Store Fulfillment werkt door de native Adobe Commerce uit te breiden [!DNL In-Store Delivery] mogelijkheden.
Nadat u de extensie hebt geïnstalleerd, zijn er aanvullende configuratieopties voor Admin beschikbaar voor leveringsmethoden in de winkel. Configureer deze extra opties vanuit de beheerder door **[!UICONTROL Stores > Configuration > Sales > Delivery Methods > In-Store Pickup]**.

In de montages van de Afhandeling van de Opslag, kunt u de volgende leveringsmethodes voor de orden van de Bestelwagen vormen In-Store.

- **Ophalen in de winkel**—De opties van de aanbieding voor in-store levering tijdens het controleproces Dit is het gemeenschappelijkste leveringsscenario voor BOPIS orden.

- **Ophalen krullen**- De opties van de aanbieding voor klanten om bij een opslagplaats te parkeren en hun orde te hebben die aan hen door een archiefvengeassocieerde wordt geleverd.

#### Configuratie van leveringsmethoden

<!---
In-store pickup, says its global setting, but scope is Website.  How do you configure the in-store pickup options at the retail level?
--->

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Enable In-Store Pickup]** | Schakel de optie Ophalen in de winkel die tijdens het afrekenen beschikbaar is in of uit voor klanten die Ophalen uit de winkel kiezen. Wanneer het ophalen in de winkel is uitgeschakeld, wordt de optie niet weergegeven.</br></br>Deze globale instelling is van toepassing op alle winkellocaties in de detailhandel. Wanneer toegelaten, kunt u het bij de detailhandel plaats selectief onbruikbaar maken. | Website | Nee |
| **Ophalen curbside inschakelen** | Schakel de optie Ophalen curven tijdens het uitrekenen in of uit voor klanten die Ophalen van winkel kiezen.</br></br>Deze globale instelling is van toepassing op alle winkellocaties in de detailhandel. Wanneer toegelaten, kunt u het bij de detailhandel plaats selectief onbruikbaar maken. | Website | Nee |

Voor details over het aanpassen van de leveringsmethodes bij geselecteerde detailhandelsopslagplaatsen, zie **Configuratie detailhandel**.

#### Configuratie van de titel van de leveringsmethode

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
<td><strong>Titel thuislevering</strong></td>
<td>Hier geeft u de titel op die u wilt weergeven voor de optie Home Delivery in de producten-, winkelwagentje- en afrekengebieden. De thuislevering heeft betrekking op de standaardverzendmogelijkheden van Adobe Commerce, van een pakhuis, door een vervoerder, rechtstreeks naar het door de klant opgegeven verzendadres.</br></br>Dit label heeft geen invloed op de geselecteerde verzendmaatschappij of op de labels van de verzendmethode.</td>
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
<td>Wanneer een klant leveringsopties wordt voorgesteld en de opname in de winkel beschikbaar is, wordt dit etiket getoond.</br></br>U kunt dit label aanpassen, dat wordt weergegeven in de producten-, winkelwagentje- en afhandelingsgebieden.</td>
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
<td>Wanneer een bestelling klaar is om in uw winkels te worden opgehaald, wordt de klant per e-mail op de hoogte gebracht. Als de klant [!DNL In-Store Pickup] tijdens het uitchecken kunt u hier de instructies voor het ophalen aanpassen.</br></br>Dit is een globale instelling die van toepassing is op alle winkellocaties. U kunt de instructies ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Instructies voor ophaalcurven</strong></td>
<td>Hiermee geeft u aangepaste instructies voor het ophalen van bestellingen op die moeten worden opgenomen in e-mailmeldingen van klanten voor bestellingen voor het ophalen van curven.</br></br>Dit is een globale instelling die van toepassing is op alle winkellocaties. U kunt de instructies ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Geschatte levertijd voor afhalen</strong></td>
<td>Het aantal minuten dat is vereist voordat een bestelling is ontvangen, uitgevoerd en klaar om te worden opgehaald. Deze informatie wordt aan de klant getoond wanneer het selecteren van een detailhandelplaats voor de leveringsoptie van de Opslag van de Opslag.</br></br>Dit is een globale instelling die van toepassing is op alle winkellocaties. U kunt de aanlooptijd ook aanpassen op het niveau van de detailhandel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Label voor geschatte ophaaltijd</strong></td>
<td>Hiermee geeft u de geschatte tijd weer tot een bestelling beschikbaar is voor het ophalen door de klant. Deze informatie wordt aan klanten getoond wanneer zij een detailhandelplaats voor de leveringsoptie van de Opslag van de Opslag selecteren.</br></br>Wanneer u dit label aanpast, kunt u de code <code>%1</code> om uw <strong>Geschatte levertijd voor afhalen</strong>.Bijvoorbeeld:</br></br><code>Ready for Pickup in %1 minutes.</code></br></br>Dit is een globale instelling die van toepassing is op alle winkellocaties. U kunt de aanlooptijd ook aanpassen op het niveau van de detailhandel.</br></br><code>Ready for Pickup in %1 minutes.</code></br></br></td>
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

#### Configuratie van de beschikbaarheidstitels van bestanden

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
<td>Wanneer een klant de lokator van de detailhandel gebruikt, wordt de beschikbaarheid van de voorraad voor het huidige item of de huidige items voor elke locatie weergegeven.</br></br>U kunt het statuslabel 'in voorraad' hier aanpassen.</td>
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
<td>Wanneer een klant de locator van de detailhandel gebruikt, wordt de voorraadbeschikbaarheid voor om het even welke huidige punten getoond voor elke plaats.</br></br>U kunt het statuslabel "gedeeltelijk in voorraad" hier aanpassen.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>
