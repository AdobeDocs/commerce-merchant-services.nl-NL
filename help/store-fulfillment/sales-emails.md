---
title: Verkoop-e-mails
description: Configureer instellingen voor de transactionele e-mailsjablonen om te communiceren met klanten en opslagbeheerders tijdens het bestellings- en uitvoeringsproces.
role: User, Admin
level: Intermediate
exl-id: 688732e3-06f0-4613-a589-2d465597eb28
source-git-commit: 4ea03b3be11056526adc42d875b1e26a24736d15
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 0%

---

# Verkoop-e-mails

Store Fulfillment biedt een uitgebreide reeks transactie-e-mailsjablonen aan ter ondersteuning van workflows voor bestellingen en afhandeling. Zij bieden verenigbare, geautomatiseerde mededeling en overseinen over kanalen aan— het op de hoogte brengen van klant en opslagbeheerders over de veranderingen van de ordestatus, instructies voor in-store bestelorden, en meer.

E-mailsjablonen voor afhandeling van opslagruimte worden geconfigureerd met standaardberichten en -instellingen. Merchant beheerders in Adobe Commerce kunnen configuraties beheren en wijzigen, en de e-mailmalplaatjes selecteren om met klanten in verschillende scenario&#39;s te communiceren. Beheerders kunnen sjablonen ook configureren en aanpassen.

Configureer de e-mailsjablonen voor verkoop van de beheerder: **[!UICONTROL Stores > Configuration > Sales > Sales Emails]**.

## E-mails - Algemene instellingen

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
<td><strong>Asynchroon verzenden</strong></td>
<td>Schakel deze functie uit. Asynchrone verzending van e-mail wordt niet ondersteund. Voor de snelste communicatie en reactietijd voor Winkelophaalservice stuurt u direct e-mails in plaats van ze in een batchbericht op te nemen. </td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>

## Order Ready for Pickup in Store

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
<td><strong>Ingeschakeld</strong></td>
<td>Dit e-mailbericht wordt naar de klant verzonden wanneer de partner van de winkel het ophalen van de bestelling heeft voltooid. Stel deze optie in op Nee om het e-mailbericht uit te schakelen. Als de e-mailsjabloon is uitgeschakeld, voorkomt dit niet dat een bestelling wordt gekozen door de partner in de winkel.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Order gereed voor afhalen e-mailafzender</strong></td>
<td>De identiteit van de afzender die wordt gebruikt bij het verzenden van het e-mailbericht.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Order gereed voor e-mailsjabloon voor afhalen</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om geregistreerde klanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>Order Ready for Pickup Email Template for Guest</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om gastklanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Order Ready for Pickup Email Template for Alternate Pickup Contact</strong></td>
<td>Het e-mailberichtmalplaatje wordt gebruikt om extra contacten mee te delen die in de orde worden genoemd. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Bestelling gereed voor afhalen e-mailkopie naar</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Send Order Ready for Pickup Email Copy Method</strong></td>
<td>De methode van e-mail "koolstofkopie" verzendt naar gebruik.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>


## De bestelling is opgehaald in de winkel

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
<td><strong>Ingeschakeld</strong></td>
<td>Dit e-mailbericht wordt naar de klant verzonden wanneer deze bevestigt dat deze zijn bestelling heeft opgehaald uit de winkel. Stel deze optie in op Nee om het e-mailbericht uit te schakelen. Als de e-mailsjabloon is uitgeschakeld, voorkomt dit niet dat een bestelling door de klant wordt opgehaald.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>De bestelling is opgehaald door de e-mailafzender</strong></td>
<td>De identiteit van de afzender die wordt gebruikt bij het verzenden van het e-mailbericht.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>De bestelling is opgezocht in e-mailsjabloon</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om geregistreerde klanten op de hoogte te brengen. Er wordt een standaardsjabloon bij de integratie geleverd</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>De bestelling is opgezocht in een e-mailsjabloon voor gasten</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om gastklanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Verzenden is opgezocht naar</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>De methode Verzenden is uitgezocht voor kopiëren via e-mail</strong></td>
<td>De methode voor het verzenden van e-mailberichten met de naam "carbon copy".</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>

## Bestelling vertraagd

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
<td><strong>Ingeschakeld</strong></td>
<td>Dit e-mailbericht wordt naar de klant verzonden om hen op de hoogte te stellen van een vertraging bij de verwerking of het selecteren van hun bestelling in de winkel. Stel deze optie in op Nee om het e-mailbericht uit te schakelen. Als de e-mailsjabloon is uitgeschakeld, voorkomt deze functie niet dat een bestelling wordt vertraagd.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Vertraagde e-mailafzender bestellen
</strong></td>
<td>De identiteit van de afzender die wordt gebruikt bij het verzenden van het e-mailbericht.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Vertraagde e-mailsjabloon bestellen</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om geregistreerde klanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>Vertraagde e-mailsjabloon voor gasten bestellen</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om gastklanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>E-mailkopie voor bestelling met vertraging verzenden naar</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Verzendvolgorde vertraagde kopieermethode</strong></td>
<td>De methode voor het verzenden van e-mailberichten met de naam "carbon copy".</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>



## Bestelling geannuleerd

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
<td><strong>Ingeschakeld</strong></td>
<td>Dit e-mailbericht wordt naar de klant verzonden om deze te laten weten dat zijn bestelling in de winkel is geannuleerd. Instellen op <code>No</code> om de e-mailmelding uit te schakelen. Als de e-mailsjabloon is uitgeschakeld, voorkomt deze functie niet dat een bestelling wordt geannuleerd.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Bestelling geannuleerde e-mailafzender
</strong></td>
<td>De identiteit van de afzender die wordt gebruikt bij het verzenden van het e-mailbericht.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>E-mailsjabloon bestellen geannuleerd</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om geregistreerde klanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>Bestelling geannuleerd voor gast</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om gastklanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Geannuleerde e-mailkopie van bestelling verzenden naar</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Kopieermethode voor bestelling geannuleerd</strong></td>
<td>De methode voor het verzenden van e-mailberichten met de naam "carbon copy".</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>


## Bestelling gedeeltelijk geannuleerd

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
<td><strong>Ingeschakeld</strong></td>
<td>Dit e-mailbericht wordt naar de klant verzonden om deze te laten weten dat een deel van zijn bestelling in de winkel is geannuleerd. Instellen op <code>No</code> om de e-mailmelding uit te schakelen. Als de e-mailsjabloon is uitgeschakeld, voorkomt dit niet dat een bestelling gedeeltelijk wordt geannuleerd.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Gedeeltelijk geannuleerde e-mailafzender bestellen
</strong></td>
<td>De identiteit van de afzender die wordt gebruikt bij het verzenden van het e-mailbericht.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Gedeeltelijk geannuleerde e-mailsjabloon bestellen</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om geregistreerde klanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<td><strong>Gedeeltelijk geannuleerde e-mailsjabloon bestellen voor alternatief ophaalcontact</strong></td>
<td>Het e-mailberichtmalplaatje wordt gebruikt om extra contacten mee te delen die in de orde worden genoemd. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Bestelling gedeeltelijk geannuleerd voor gast</strong></td>
<td>De e-mailberichtsjabloon die wordt gebruikt om gastklanten op de hoogte te brengen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Gedeeltelijk geannuleerde e-mailkopie verzenden naar</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Gedeeltelijk geannuleerde kopieermethode voor bestelling verzenden</strong></td>
<td>De methode voor het verzenden van e-mailberichten met de naam "carbon copy".</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>

## Verzenden naar winkel

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
<td><strong>De bestelling is verzonden om e-mailafzender van producten op te slaan</strong></td>
<td>De e-mail die naar het opgegeven bedrijfspersoneel is verzonden als een geaggregeerd rapport van alle open bestellingen die pas in een handelsportefeuille kunnen worden uitgepakt als hun inventaris beschikbaar is. </br></br> Handelaars kunnen dit rapport gebruiken om voorraadoverdrachten of aanvulling te initiëren en te beheren. </br></br>Deze melding is alleen van toepassing wanneer de [!DNL Ship-to-Store] functies zijn ingeschakeld.
</br></br>Dit label heeft geen invloed op de geselecteerde verzendmaatschappij of op de labels van de verzendmethode.</br></br></td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>Verzenden om e-mailontvangers op te slaan</strong></td>
<td>Een door komma's gescheiden lijst met e-mailadressen om een kopie van elke melding te verzenden.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>E-mailsjabloon</strong></td>
<td>De sjabloon voor e-mailberichten die wordt gebruikt om ontvangers op de hoogte te stellen. De integratie bevat een standaardsjabloon.</td>
<td>Winkelweergave</td>
<td>Nee</td>
</tr>
</tbody></table>

>[!NOTE]
>
>Als u backorders toestaat, moet u een beheerder e-mailadres verstrekken om berichten over deze orden te ontvangen. Voeg het adres aan de volgende configuratiemontages toe: **[!UICONTROL Send Order Delayed Email Copy To]** in de [Opdrachtvertraging](#order-delayed) sjabloon, en [!UICONTROL Ship To Store Email Recipients] in de [Verzenden naar winkel](#ship-to-store) sjabloon.



