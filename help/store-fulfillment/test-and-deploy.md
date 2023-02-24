---
title: Afhandeling van winkel testen en implementeren
description: Test een plan om de functionaliteit voor winkelvervulling te verifiëren. De tests hebben betrekking op de API voor inventarissynchronisatie, de end-to-end uitvoeringsworkflow voor geannuleerde bestellingen, het gebruikersbeheer van de app voor winkelafhandeling en de ervaring die de klant heeft met het inchecken.
role: User, Admin
level: Intermediate
exl-id: 77285a66-5161-407b-94cd-b3f412d7949d
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '2660'
ht-degree: 0%

---

# Afhandeling van winkel testen en implementeren voor Adobe Commerce

Nadat u het instapproces in uw ontwikkelingsmilieu hebt voltooid, kunt u het proces beginnen om de oplossing van de Vervulling van de Opslag aan uw productiemilieu te testen en op te stellen.

**Vereisten**

Voordat u gegevens, opslaggegevens of bestellingen gaat testen of synchroniseren, controleert u of u de volgende taken hebt uitgevoerd:

- Voltooid de [Algemene configuratie](enable-general.md) voor Store Fulfillment Services.

- [De accountgegevens en verbindingsgegevens voor uw sandbox- en productieomgeving toevoegen en valideren](connect-set-up-service.md#configure-store-fulfillment-account-credentials)

- Bevestig dat de [Adobe Commerce-integratie](connect-set-up-service.md#configure-store-fulfillment-account-credentials) voor de oplossing van Afhandeling bewaren is beschikbaar en geautoriseerd.

## Voorbereiden op testen

De verbindingsconfiguratie moet worden voltooid alvorens u om het even welke testorden kunt tot stand brengen of integratie het testen uitvoeren. Voordat u gaat testen, moet u ook controleren of de opslaggegevens zijn gesynchroniseerd.

1. De bronnen van de Afhandeling van de Opslag synchroniseren.

   - Ga naar **[!UICONTROL Stores > Sources]**.

   - Selecteren **[!UICONTROL Synchronize Store Fulfillment Sources]**.

1. Van het opslagnet, verifieer dat de opslag zoals gemerkt wordt `Synced` voordat u testorders maakt.

## Monstertestplan

De detailhandelaars bevestigen de basisfunctionaliteit van de oplossing van de Afhandeling van de Opslag tijdens de configuratie en testfasen van een plaatsing. Dit voorbeeldtestplan biedt een beginpunt voor het testen. Voeg extra scenario&#39;s toe die op uw vereisten worden gebaseerd.

>[!NOTE]
>
>Nadat u het eerste instapsysteem voor de oplossing van de Behandeling van de Opslag hebt voltooid of een bestaande installatie hebt bijgewerkt, test u de toepassing altijd in een niet-productieomgeving voordat u de toepassing implementeert in de productie.

Dit steekproeftestplan bestrijkt de volgende functionele gebieden:

| Functioneel gebied | Functie | Rol |
|-------------------------------------|------------------------------------------|----------------------------------|
| Synchronisatie van inventarisatie en bestelling | API-inventarisatie | Adobe Commerce Admin |
| End-to-end | Workflows voor annulering van bestellingen | Klant, Admin, Store Associated |
| Beheer | Machtigingen voor App-uitvoering opslaan | Beheer |
| Adobe Commerce Frontend | Producttypen | Klant, beheerder |
| Afhandeling aan voorzijde</br>Formulier inchecken | Inchecken | Klant, beheerder |
| App Winkelassistentie | Volgorde</br>Selecteren</br>Werkgebied</br>en Handoff | Winkelkoppeling |

### API-inventarisatie

Deze sectie van het testplan behandelt inventaris en ordesynchronisatie om te verifiëren dat de updates aan bestelbronnen en de voorraden correct tussen Adobe Commerce en de oplossing van de Behandeling van de Opslag worden gesynchroniseerd.

**Functioneel gebied**: Synchronisatie van inventarisatie en bestelling</br>
**Rol:** Beheer</br>
**Type test:** Alles positief

<table>
<thead>
<tr>
<th>Functie</th>
<th>Scenario testen</th>
<th>Verwachte resultaten</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Ophaalvoorraadbron toevoegen</strong></td>
<td>Sla een nieuwe bron voor opgehaalde bestanden op.</td>
<td>De synchronisatie in real time verzendt de brondetails naar de dienst van het GIF van het Slim binnen 5 minuten.</td>
</tr>
<tr>
<td><strong>Bestaande bron van opgehaalde bestanden bijwerken</strong></td>
<td>Sla updates op naar een bestaande bron van ophaalvoorraad.</td>
<td>De synchrone verrichting in real time verzendt de details naar het GIF van het Smarm binnen 5 minuten</td>
</tr>
<tr>
<td><strong>Ophaalvoorraadbron</br><code>Is Synced</code> status</br><code>Is Synced</code></strong></td>
<td>Sla updates op naar een bestaande bron van ophaalvoorraad.</td>
<td>Na een geslaagde bewerking <code>Is Synced</code> kolom van de pagina Bron beheren wordt bijgewerkt vanaf <code>No</code> tot <code>Yes</code>.</td>
</tr>
<tr>
<td><strong>Gewijzigde voorraadreserveringsprocedure</strong></td>
<td>Maak en verzend een nieuwe bestelling voor een product.</td>
<td>De verkoopbare hoeveelheid voor het product neemt dienovereenkomstig af.</td>
</tr>
<tr>
<td><strong>Nieuwe order-push, API-synchronisatie—Klantenvolgorde</strong></td>
<td>De klant dient een bestelling in voor het ophalen van de winkel.</td>
<td><ul><li>In de weergave Admin-volgorde kunt u een <strong>Adobe Commerce Admin-gebruiker</strong> ziet u dat de status van Order Sync is bijgewerkt naar <code>Sent</code></li><li>Het logboek met de orderdetails bevat het bericht <code>Order was sent to BOPIS solution for sync, it's not yet acknowledged yet.</code></li></ul></td>
</tr>
<tr>
<td><strong>New Order Push, API Sync—Admin verzendt order</strong></td>
<td>An Adobe Commerce <strong>Beheer</strong> verzendt een bestelvolgorde.</td>
<td><ul><li>In de weergave Bestelling beheren wordt de status Synchronisatie van bestellingen bijgewerkt naar <code>Sent</code>.</li><li>Het logboek met de orderdetails bevat het bericht <code>Order was sent to BOPIS solution for sync, it's not yet acknowledged yet.</code></li></ul></td>
</tr>
<tr>
<td><strong>New Order Push, Exception Queue<strong></td>
<td>Identificeer verscheidene Virtuele en downloadbare producten in de Admin van Adobe Commerce die door Adobe Commerce kunnen worden vervuld zonder interactie met de dienst van de Afhandeling (FaaS) te vereisen.</td>
<td>Deze producten worden in de uitvoer op de juiste wijze verwijderd of gemarkeerd om een downstreamconflict met de FaaS te voorkomen.</td>
</tr>
</tbody>
</table>

### Workflows voor annulering van bestellingen

Deze sectie van het testplan omvat scenario&#39;s om het werkschema van begin tot eind voor orden te testen die door Adobe Commerce worden geannuleerd.

**Functioneel gebied:** Adobe Commerce Admin</br>
**Rol:** End-to-end (Admin, Store Associate, Customer)</br>
**Type testresultaat:** Positief voor alle scenario&#39;s

<table style="table-layout:fixed">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Verwachte resultaten</th>
</tr>
<tr>
<td><strong>Volledige annulering van bestelling</strong></td>
<td><ol>
<li>Plaatsingsvolgorde.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is aangemaakt (als u autoriseert en vastlegt).</li>
<li>Maak een creditmemo met alle bestelde producten uit de weergave Factuur.</li>
</ol>
</td>
<td>
<ul>
<li>Orderhistorie bijgewerkt met <code>We refunded $X online. Transaction ID: transactionID</code> en <code>Received Cancel acknowledgment from the BOPIS solution.</code></li>
<li>Status van bestelling is <code>Closed</code>. (We hebben nu een BETALINGSREVISIE ingesteld.)</li>
<li>Creditnota gemaakt in Adobe Commerce. (Wacht tot het uitsnijden werkt.)</li>
<li>Als alle items zijn opgenomen, kunt u het e-mailbericht ophalen <code>DISPLAY COMMENT HISTORY</code> shows <code>Order is ready for pickup</code> (<code>CUSTOMER NOTIFIED</code> markering is <code>true</code>.)</li>
<li>Als alle items niet zijn gekozen, wordt het e-mailbericht geannuleerd en wordt de HISTORIE VOOR OPMERKINGEN WEERGEGEVEN <code>Order has been canceled - all items were not available</code></li>
<li><code>CUSTOMER NOTIFIED</code> markering is <code>true</code>.)</li>
</ul>
</td>
</tr>
<tr><td><strong>Ongedaan maken gedeeltelijke bestelling<strong></td>
<td>
<ol>
<li>Plaats de bestelling met ten minste twee producten.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Wacht twee uur op transactieafwikkeling.</li>
<li>Maak een creditmemo met slechts een deel van de bestelde producten uit de weergave Factuur.</li>
</td>
<td>
<ul>
<li>Update voor ordergeschiedenis: <code>We refunded $X online. Transaction ID: transactionID</code></li>
<li>Update voor ordergeschiedenis: <code>Order notified as partly canceled at: Date and Hour</code></li>
<li>E-mailbericht voor terugbetaling van bestelling: <code>$x amount was refunded</code></li>
<li>Status van bestelling is <code>Processing</code>.</li>
<li>Creditnota gemaakt in Adobe Commerce (wacht tot de afbouw werkt).</li>
<li>Als sommige items niet zijn gekozen, bevestigt u dat de optie [!UICONTROL Ready for Pickup] Het e-mailbericht met de sectie Geen keuze of Terugbetaling wordt weergegeven. <code>DISPLAY COMMENT HISTORY</code> shows <code>Order is ready for pickup, but some items not available.</code>.</li>
<li><code>CUSTOMER NOTIFIED</code> markering is <code>true</code>.</li>
</ul>
</td>
</tr>
<td><strong>Gereed voor ophalen</br></br>Volledige annulering</br>(alle producten worden ingesteld op 0 qty)</br></strong></td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Ga naar de Postman en voer het "Ready for Pickup"-verzoek uit met alle producten ingesteld als <code>picked</code> with <code>0 qty</code>.</li>
</ol>
</td>
<td>
<ul>
<li>Orderhistorie bijgewerkt: <code>We refunded $X offline</code></li>
<li>De orderstatus is <code>CLOSED</code>.
<li>Het creditmemo wordt gemaakt. (Wacht tot het uitsnijden werkt.)</li>
<li>E-mailadres voor terugbetaling ontvangen: <code>$x amount was refunded</code></li>
<li>E-mailbericht voor annulering van bestelling verzonden.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Gereed voor afhalen - gedeeltelijke annulering</strong></br></br><strong>(Sommige producten worden geplukt en andere worden met <code>0 qty</code>)</strong>
</td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Ga naar de Postman en voer het "Ready for Pickup"-verzoek uit met een deel van de producten die zijn ingesteld op 0 qty en de rest van de producten is opgepikt.</li>
</ol>
</td>
<td>
<ul>
<li><code>Your order is ready for pickup</code> with [!UICONTROL Ready for Pickup Items] en [!UICONTROL Canceled Items] tabellen. </li>
<li>De status van de bestelling is READY FOR PICKUP. </li>
<li>Orderhistorie bijgewerkt: <code>We refunded $X offline.</code>
<li>Orderhistorie bijgewerkt: <code>Order notified as partly canceled at: Date and hour</code>
<li>E-mailadres voor terugbetaling ontvangen: <code>$x amount was refunded</code>
<li>De creditmemo wordt gemaakt. (Wacht tot het uitsnijden werkt.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Gereed voor afhalen - gedeeltelijke annulering</br></br>Sommige producten worden geplukt en sommige worden met <code>0 qty</code>)</strong>
</td>
<td><ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Ga naar de Postman en voer het "Ready for Pickup"-verzoek uit met een deel van de producten die zijn ingesteld op 0 qty en de rest van de producten is opgepikt.</li>
</ol>
</td>
<td><ul>
<li><code>Your order is ready for pickup</code> with [!UICONTROL Ready for Pickup Items] en [!UICONTROL Canceled Items] tabellen. </li>
<li>De status van de bestelling is READY FOR PICKUP. </li>
<li>Orderhistorie bijgewerkt: <code>We refunded $X offline.</code>
<li>Orderhistorie bijgewerkt: <code>Order notified as partly canceled at: Date and hour</code>
<li>E-mailadres voor terugbetaling ontvangen: <code>$x amount was refunded</code>
<li>De creditmemo wordt gemaakt. (Wacht tot het uitsnijden werkt.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Verzonden (tijdens dispensatie) </br></br>Volledige annulering (alle producten worden ingesteld als afgewezen)</strong>
</td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Ga naar de Postman en voer het "Ready for Pickup"-verzoek uit met alle producten ingesteld zoals u hebt gekozen.</li>
<li>Open uw brievenbus, vind Klaar voor Bestelwagen e-mail. Klik vervolgens op **[!UICONTROL Confirm Arrival]**.</li>
<li>Inchecken.</li>
<li>Ga naar Postman en voer het verzonden verzoek uit terwijl alle producten zijn ingesteld als afgewezen.</li>
</ol>
<td><ul>
<li>Orderhistorie bijgewerkt: <code>We refunded $X offline.</code></li>
<li>E-mailadres voor terugbetaling ontvangen: <code>$x amount was refunded</code></li>
<li>Status ingesteld op <code>CLOSED</code>.</li>
<li>Creditmemo gemaakt. (Wacht tot het uitsnijden werkt.)</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Verzonden (tijdens dispensatie)</br></br>Gedeeltelijke annulering</br>(Sommige producten worden afgeleverd; sommige zijn verworpen.)</strong>
</br></td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Ga naar Postman en voer het "Ready for Pickup"-verzoek uit met alle producten die zijn ingesteld als gekozen.</li>
<li>Open uw postvak. Zoek het e-mailbericht Gereed voor afhalen en selecteer <code>Confirm Arrival</code>.</li>
<li>Inchecken.</li>
<li>Ga naar de Postman en voer het verzonden verzoek uit met bepaalde producten die zijn opgegeven en waarvan sommige zijn afgewezen</li>
</ol>
</td>
<td>
<li>Orderhistorie bijgewerkt: <code>We refunded $X offline</code></li>
<li><code>Order notified as partly canceled at: Date and Hour</code>
<li>E-mailadres voor terugbetaling ontvangen: <code>$x amount was refunded</code>
<li>Orderstatus ingesteld op <code>Ready for pickup Dispensed</code>
<li>Creditmemo gemaakt. (Wacht tot het uitsnijden werkt.)</li>
</td>
</tr>
<tr>
<td> <strong>Nieuwe RMA na terugkeer (volledig)</strong>
</td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Als de optie voor autoriseren en vastleggen is geconfigureerd, controleert u of de factuur is gemaakt en of de klant de factuur per e-mail heeft ontvangen.</li>
<li>Kies alle producten met Postman.</li>
<li>Inchecken.</li>
<li>Maak een dispensatie.</li>
<li>Ga naar bestelling en selecteer<strong>[!UICONTROL Create returns]=
<li>Maak de RMA.</li>
</ol>
</td>
<td>
<ul>
<li>De RMA is gemaakt en wordt weergegeven onder de <strong>[!UICONTROL Returns]</b> in de weergave Volgorde.</li>
<li>De klant heeft een bevestigingsbericht van RMA ontvangen.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Nieuwe RMA na terugkeer — Gedeeltelijk</strong>
</td>
<td>
<ol>
<li>Plaats de bestelling.</li>
<li>Wacht tot de volgorde is gesynchroniseerd.</li>
<li>Controleer of de factuur is gemaakt (indien geautoriseerd en vastgelegd) en of de factuur per e-mail is ontvangen.</li>
<li>Kies alle producten met Postman.</li>
<li>Inchecken.</li>
<li>Maak een dispensatie.</li>
<li>Ga de orde, en selecteer  <strong>[!UICONTROL Create returns]</strong></li>
<li>Creeer RMA met een deel van de bevolen producten.</li>
</ol>
<td>
<ul>
<li>RMA gemaakt en weergegeven onder de <strong>[!UICONTROL Returns]</strong> in de weergave Volgorde.</li>
<li>De klant heeft het bevestigingsbericht van RMA ontvangen.</li>
<li>Na het creëren van RMA, krijg de vergunning RMA: Ga vanuit de beheerder naar <strong>[!UICONTROL Sales > Returns]</strong>. Selecteer de RMA die u hebt gemaakt en autoriseer deze.</li>
<li>Controleer of de klant het bevestigingsbericht voor de RMA-autorisatie heeft ontvangen.</li>
<li>Controleer of de restitutie is toegevoegd aan de transacties en de ordergeschiedenis.</li>
</ul>
</td>
</tr>
</table>


### Machtigingen voor App-uitvoering opslaan

In dit gedeelte van het testplan wordt het accountbeheer voor App Users-gebruikers voor Store Fulfillment besproken.

- Bevestig dat een Winkelgeassocieerde kan verifiëren met een nieuwe gebruikersaccount die is gemaakt met Adobe Commerce Admin.
- Bevestig dat updates van bestaande accounts correct zijn toegepast.

**Functioneel gebied:** Adobe Commerce Admin</br>
**Rol:** Admin, Store Associate</br>
**Type test:** Alle positieve

<table style="table-layout:auto">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Verwachte resultaten</th>
</tr>
<tr>
<td><strong>Gebruikersaccountbeheer - Account maken</strong></br></br>
</td>
<td>
<ol>
<li><strong>Beheer</strong> — Aanmelden bij de Adobe Commerce Admin</li>
<li>Ga naar <strong>[!UICONTROL System] &gt; Enable Fulfillment App &gt; All Store Fulfillment App Users</strong></li>
<li><strong>Nieuwe gebruiker toevoegen.</strong></li>
</ol>
<td>
<ul>
<li>Account is gemaakt.</li>
<li>Nieuwe gebruikersaccount wordt weergegeven op het tabblad [!UICONTROL Store Fulfillment Users] dashboard.</li>
<li><strong>Winkelkoppeling</strong> Meld u aan bij de app Winkelassistentie met een nieuwe gebruikersaccount.</li>
</ul>
</td>
</tr>
<tr>
<td><strong>Gebruikersaccountbeheer - Bestaande gebruikersaccount bijwerken</strong>
</td>
<td>
<ol>
<li>Meld u aan bij de Adobe Commerce Admin-gebruikersaccount.</li>
<li>Ga naar <strong>[!UICONTROL System] &gt; Enable Fulfillment App &gt; All Store Fulfillment App Users</strong>.</li>
<li>Open in de lijst Gebruikersaccount een bestaande actieve gebruikersaccount door <strong>[!UICONTROL Edit]</strong>.
<li>Schakel de account uit door <strong>[!UICONTROL Is Active]</strong> tot <strong>Nee</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Op de <strong>[!UICONTROL Store Fulfillment App Users]</strong> dashboard, de status voor de bijgewerkte account is gewijzigd in <strong>[!UICONTROL Inactive]</strong>.</li>
<li>Store Associate kan zich niet aanmelden bij de app Store Assist met de inactieve accountgegevens.</li>
</ul>
</td>
</tr>
</table>

## Adobe Commerce-producttypen

De testscenario&#39;s voor de Types van Product van Adobe Commerce verifiëren dat de klanten het correcte product, de voorraad, en de informatie van de leveringsmethode voor verschillende producttypes zien:

- [!UICONTROL Configurable]
- [!UICONTROL Grouped]
- [!UICONTROL Virtual]
- [!UICONTROL Bundle products] in de Adobe Commerce storefront.

**Functioneel gebied:** Adobe Commerce Frontend</br>
**Rol:** App-gebruiker voor hulp bij winkel (link naar winkel)</br>
**Type test:** Alle positieve

<table style="table-layout:auto">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Opmerkingen</th>
</tr>
<tr>
<td><strong>Configureerbare producten</strong>
</td>
<td>
<ul>
<li>Verifieer dat de gebruiker slechts die configureerbare opties kan zien, welke bron wordt toegelaten, de voorraad wordt toegewezen en dat er sommige punten in voorraad-controle kindproducten zijn.</li>
<li>Controleer of bij het selecteren van een andere winkel de opties die niet beschikbaar zijn, worden weergegeven als doorgestreept.</li>
<li>Controleer of configureerbare opties niet zijn geselecteerd als de gebruiker een andere winkel selecteert.</li>
<li>Controleer of een configureerbaar product al in de winkelwagentje zit en een gebruiker een andere winkel selecteert, zodat het product niet meer in voorraad is.</li>
</ul>
</td>
<td></td>
</td>
</tr>
<tr>
<td><strong>Gegroepeerde producten</strong>
</td>
<td>
<ul>
<li>Controleren of de leveringsmethoden en [!UICONTROL Add to cart] de knop is uitgeschakeld voor de klant wanneer alle onderliggende producten
<code>qty</code> instellen op <code>0</code>.</li>
<li>Controleren of de leveringsmethoden zijn ingeschakeld voor de klant wanneer ten minste een van de onderliggende producten <code>qty</code> instellen op <code>0.</code></li>
<li>Controleren of [!UICONTROL Store Pickup Delivery] Deze methode is alleen zichtbaar en actief voor producten die [!UICONTROL Available for Store Pickup] ingeschakeld. (Controleer het onderliggende product.)</li>
</ul>
</td>
<td></td>
</tr>
<tr>
<td><strong>Virtuele producten</strong>
</td>
<td>
Controleren of virtuele producten de  [!UICONTROL In-store Pickup] leveringsmethode.
<td></td>
</td>
</tr>
<tr>
<td><strong>Bundel</strong>
</td>
<td>
<ul>
<li>Controleren of ten minste één onderliggend product [!UICONTROL Available for Store Pickup] Uitgeschakeld, is de optie Ophalen van de Ophaalservice niet beschikbaar voor de klant.</li>
<li>Controleren of ten minste één onderliggend product [!UICONTROL Available for Home Delivery] uitgeschakeld, is de optie Home Delivery niet beschikbaar voor de klant.</li>
<li>Controleren of ten minste een van de onderliggende producten in een bundel uit voorraad is, wordt de bundel (het bovenliggende product) ook weergegeven als [!UICONTROL Out of stock].</li>
</ul>
</td>
<td></td>
</tr>
<tbody>
</table>

## Inchecken

Deze sectie van het testplan behandelt de Controle-In Ervaring voor de Bestellingen van de Bestelwagen van de Opslag voor de volgende mogelijkheden:

- Afwisselend oppikken contact-verifieer het werkschema voor het toevoegen van een [!UICONTROL Alternate Pickup Contact] en selecteert u een [!UICONTROL Preferred Contact] op bestellingen voor ophaalservice.

- Inchecken formulier—Controleer de workflow voor het indienen van een incheckaanvraag voor bestellingen voor winkelbestellingen.

**Functionele gebieden:** Afhandeling van winkelwagentje, inchecken van formulier voor bestellingen voor het ophalen van winkels</br>
**Rol:** Beheerder, Klant, Winkelgeassocieerd</br>
**Type test:** Alle positieve

### Contactpersoon voor afhalen alternatief


**Functioneel gebied:** Afhandeling van winkelwagentje</br>
**Rol:** Klant</br>
**Type test:** Alle positieve

<table style="table-layout:auto">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Verwachte resultaten</th>
</tr>
<tr>
<td><strong>Contactpersoon voor afhalen alternatief</br>
Inchecken</br><strong>
</td>
<td>
Een klant verzendt een bestelling met de optie Ophalen in de winkel.</td>
<td>Tijdens het uitcheckproces ziet de klant [!UICONTROL Alternate Pickup Contact] de optie in de stap Verzending.
</td>
</tr>
<tr>
<td><strong>Alternatieve voorkeurscontactpersoon voor afhalen, inchecken</strong>
<td>
Een klant verzendt een bestelling met de optie Ophalen in de winkel. Tijdens het afrekenen voegt de klant een [!UICONTROL Alternate Pickup Contact].</td>
<td>Tijdens het uitcheckproces ziet de klant [!UICONTROL Preferred Contact] in de verzendstap.</td>
</td>
</tr>
<tr>
<td><strong>Contactgegevens voor alternatief ophalen, inchecken</strong>
</td>
<td>
Een klant verzendt een bestelling met de optie Ophalen in de winkel. Tijdens het afrekenen selecteert de klant [!UICONTROL Alternate Pickup Contact] op de verzendstap.
</td>
<td>De klant ziet invoeropties om contactgegevens in te voeren: [!UICONTROL First name], [!UICONTROL Last name], [!UICONTROL Phone], en [!UICONTROL Email].</td>
</tr>
<tr>
<td><strong>Alternatieve ophaalservice, inchecken via e-mail</strong>
</td>
<td>Een klant verzendt een bestelling met de optie Ophalen in de winkel. Tijdens het afrekenen selecteert de klant [!UICONTROL Alternate Pickup Contact] voegt de contactgegevens toe aan de verzendstap en verzendt de bestelling.</td>
<td>Zowel de klant als de andere contactpersoon ontvangen een incheckbericht voor de bestelling.</td>
</tr>
<td><strong>Alternatieve ophaling, orderdetails</strong></td>
<td>Een klant verzendt een bestelling met de optie Ophalen in de winkel. Tijdens het afrekenen selecteert de klant [!UICONTROL Alternate Pickup Contact] voegt de contactgegevens toe aan de verzendstap en verzendt de bestelling.</td>
<td>De beheerder ziet de extra contactinformatie over de bewaarde orde.</td>
</tr>
<tr>
<td><strong>Alternatieve contactpersoon voor afhalen, weergave voor aan een winkel gekoppelde bestelling</strong>
</td>
<td>Een klant verzendt een bestelling met de optie Ophalen in de winkel. Tijdens het afrekenen selecteert de klant [!UICONTROL Alternate Pickup Contact] voegt de contactgegevens toe aan de verzendstap en verzendt de bestelling.</td>
<td>De Store Associate kan de extra contactinformatie over de orde in FaaS/ChaaS zien.</td>
</td>
</tr>
</tbody>
</table>

### Formulier inchecken


**Functioneel gebied:** Formulier inchecken</br>
**Rol:** Klant</br>
**Type test:** Alle positieve

<table style="table-layout:auto">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Verwachte resultaten</th>
</tr>
<tr>
<td><strong>Inchecken - Verzoek verzenden</strong>
</td>
<td>Op het incheckformulier vult een klant alle vereiste velden in en verzendt de aanvraag.</td>
<td>De klant ontvangt een succesantwoord.</td>
</tr>
<tr>
<td><strong>Inchecken van handeling—Gegevens verzoek weergeven</strong></td>
<td>Een klant verzendt een incheckaanvraag.</td>
<td>De de statusupdates van de orde in het systeem FaaS, en de Vennoot van de Opslag kunnen de controle-binnen verzoekdetails in FaaS zien.
</td>
</tr>
<tr>
<td><strong>Inchecken - Verzoek slechts eenmaal indienen</strong></td>
<td>Na het voorleggen van een controle-binnen verzoek om een orde, selecteert een klant de verbinding aan controle een tweede keer.</td>
<td>Op het inchecken-formulier ziet de klant geen optie voor het bewerken of opnieuw verzenden van het formulier.</td>
</tr>
<tr>
<td><strong>Inchecken - Arrival bevestigen</strong></td>
<td>Een ophaalvolgorde in de winkel is gemarkeerd en kan worden opgehaald in de FaaS. De klant ontvangt een e-mailbericht "Gereed voor afhalen" en selecteert [!UICONTROL Confirm Arrival].</td>
<td>De klant ziet het incheckformulier voor de bestelling.</td>
</tr>
</tbody>
</table>

## App Winkelassistentie

Deze sectie van het testplan behandelt scenario&#39;s voor het testen van orde, selecteren, en afleveringswerkschema&#39;s in de App van de Hulp van de Opslag.

**Functioneel gebied:** App Winkelassistentie</br>
**Rol:** Winkelkoppeling</br>
**Type test:** Alle positieve

<table style="table-layout:auto">
<tr>
<th>Functie</th>
<th>Scenario</th>
<th>Verwachte resultaten</th>
</tr>
<tr>
<td>
<strong>Ophalen van één bestelling—gelukkig pad, ophalen van rand</strong></td>
<td>Selecteer objecten van één en meerdere aantallen. Geen gelijke plukken, en curbside oppeling (met het opvoeren).
</td>
<td>
</td>
</tr>
<tr>
<td><strong>Ophalen van meerdere bestellingen—gelukkig pad, ophalen van rand</strong></td>
<td>Enkelvoudige en meervoudige items. Geen gelijke plukken, en curbside oppeling (met het opvoeren)</td>
<td></td>
</tr>
<tr>
<td><strong>Ophalen via één bestelling—ophalen via een gelukkig pad in de winkel</strong></td>
<td>Enkelvoudige en meervoudige items. Geen plukken van nul en ophalen in de winkel (met ophaling)</td>
<td>
</td>
</tr>
<tr>
<td><strong>Ophalen van meerdere bestellingen—gelukkig pad, ophalen in winkel</strong></td>
<td>Selecteer objecten van één en meerdere aantallen. Geen gelijke plukken, en curbside oppeling (met het opvoeren).</td>
<td></td>
</tr>
<tr>
<td><strong>Eén bestelling kiezen—geen gelukkig pad, in-store ophalen</strong></td>
<td>Afzonderlijke objecten en meerdere objecten kiezen met gedeeltelijk en niloogst en ophaalbewerkingen in de winkel (met ophaling)</td>
</td>
<td></td>
</tr>
<td><strong>Ophalen van meerdere bestellingen—niet ophalen van padcurbside</strong></td>
<td>Afzonderlijke objecten en meerdere objecten kiezen met gedeeltelijk en niloogst en ophaalbewerkingen in de winkel (met ophaling)</td>
<td></td>
</tr>
<td><strong>Eén bestelling selecteren—geen gelukkig pad, ophalen op de achtergrond</strong></td>
<td>Items van één of meerdere aantallen selecteren met gedeeltelijke en automatische selectie en curbside oppikken (met ophaling)</strong></td>
</td>
<td></td>
</tr>
<tr><td><strong>Geplaatst bestelling - geannuleerd voor kiezen</strong></td>
<td></td>
<td></td>
</tr>
<tr>
<td><strong>Geplaatste bestelling - geannuleerd voor verzending</strong></td>
<td></td>
<td></td>
</tr>
<tr>
<td><strong>Plaatsende orde - onderzoek in orde module</strong></td>
<td></td>
<td></td>
</tr>
<tr><td><strong>Plaatsende orde - onderzoek en manuele controle binnen voor overdracht</strong></td>
<td></td>
<td></td>
</tr>
<tr><td><strong>Geplaatste bestelling - alle items die niet zijn geselecteerd of niet beschikbaar zijn gemarkeerd door de kiezer</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Volgorde geplaatst met bundelitems - plukken en afleveren</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Opdracht geplaatst - Handje af met afwijzing</strong></td>
<td></td>
<td></td></tr>
<tr><td><strong>Opdracht geplaatst - Handje af met afwijzing van alle items</strong></td>
<td></td>
<td></td></tr>
</tbody>
</table>

## Implementeren

Nadat u hebt geverifieerd dat de oplossing aan uw specificaties is gevormd en getest, bent u bereid om van het opvoeren aan productie op te stellen.

De implementatie en het testen zijn afhankelijk van uw infrastructuur en mogelijkheden.

>[!TIP]
>
>Raadpleeg voor implementatierichtlijnen, checklists en best practices voor Adobe Commerce over infrastructuurprojecten in de cloud de [Je winkel implementeren](https://devdocs.magento.com/cloud/live/stage-prod-live.html) in de documentatie van Adobe Commerce Developer.
