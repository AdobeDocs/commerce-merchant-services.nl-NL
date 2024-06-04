---
title: "[!DNL Payment Services] Opmerkingen bij de release"
description: Lees de opmerkingen bij de release voor meer informatie over alle [!DNL Payment Services] lozingen.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
feature: Payments, Release Notes
source-git-commit: 9b4ce379728b126390177d64c10d57b2c587619c
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 0%

---

# Aanvullende informatie

In deze releaseopmerkingen wordt de eerste release van [!DNL Payment Services] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

Voor functieveranderingen en moeilijke situaties die buiten de regelmatige versie van de eigenschapversie worden vrijgegeven, herzie _Gehoste service-updates_ secties.

Meer informatie over komende releases, productondersteuning en welke Adobe Commerce-versies ondersteuning bieden voor de [!DNL Payment Services] -extensie, zie de Adobe Commerce [Releaseplanning](https://experienceleague.adobe.com/en/docs/commerce-operations/release/planning/schedule) en [Beschikbaarheid van producten](https://experienceleague.adobe.com/en/docs/commerce-operations/release/product-availability) onderwerpen.

## Gehoste service-updates

Deze versienota&#39;s beschrijven eigenschapveranderingen en moeilijke situaties die voorkwamen en buiten de regelmatige eigenschapversies voor de ontvangen dienst werden vrijgegeven.

+++Hosted service-updates

_5 maart 2024_

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-5252 --> Handelaars kunnen nu gegevens uit de dashboardrasters kopiëren door de inhoud van één cel te selecteren.

_10 oktober 2023_

![Nieuwe uitgave](../assets/fix.svg)<!-- Issue PAY-4888 --> Handelaren kunnen nu creditcardtransacties filteren met de laatste vier cijfers van het kaartnummer in de [Transactierapport](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/transactions.html).

_12 juli 2023_

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4587 --> Een onderwerp dat in het [!DNL Payment Services] 2.1.0-release die verhinderde dat autorisatiewachtwoorden werden geplaatst door eerdere extensieversies, is nu opgelost. Handelaren die elke versie van [!DNL Payment Services] kan autorisaties voorkomen.

_9 juni 2023_

![Nieuw](../assets/new.svg)<!-- Issue PAY-4288 --> Handelaren kunnen [vormen _alleen_ PayPal-betalingsknoppen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/payments-options.html#use-only-paypal-payment-buttons)—en _niet_ gebruik de betalingsoptie PayPal-creditcard. Op deze manier kunnen verkopers verschillende betalingsopties aanbieden, zoals de betalingsknoppen Venmo en PayPal, en een bestaande creditcardprovider gebruiken in plaats van de optie PayPal-creditcardbetaling.

![Nieuw](../assets/new.svg)<!-- Issue PAY-4050 --> Toegevoegde [gegevensvisualisatieweergave](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html#order-payment-status-data-visualization-view), die wordt weergegeven op de startpagina van de betalingsservice, voor het rapport over de betalingsstatus van de bestelling.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4486--> Eerder werd de button PayPal PayPal Later niet weergegeven bij de afhandeling voor Britse handelaren. Dat probleem is opgelost.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4485--> Weergaven voor de visualisatie van rapportgegevens worden nu weergegeven op [!DNL Payment Services] Home wanneer[!DNL Payment Services] is uitgeschakeld.

_25 januari 2023_

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-4102 --> Nieuwe installaties van [!DNL Payment Services] kunnen Commerce Services niet configureren, renderen [!DNL Payment Services] onwerkbaar. Werk uw [!DNL Payment Services] uitbreiding tot versie 1.5.3.

_12 september 2022_

![Nieuw](../assets/new.svg)<!-- Issue PAY-3705 --> De `increment_id` is nu beschikbaar voor gebruik bij het in overeenstemming brengen van uitbetalingen in externe ERP-systemen. Het wordt doorgegeven aan de [`custom_id` _en_ `invoice_id`](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/data.html#reconcile-with-erp-system), zichtbaar in zowel de PayPal-website als de zakelijke activiteitengegevens voor een uitbetaling.

_31 augustus 2022_

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3629 --> Wanneer een nieuwe handelaar tot [!DNL Payment Services] Voor het eerst wordt de pagina nu meteen geladen om de inhoud weer te geven in plaats van dat een pagina moet worden vernieuwd.

_9 augustus 2021_

![Nieuw](../assets/new.svg)<!-- Issue PAY-3420 --> Apple Pay is nu beschikbaar als een slimme PayPal-knop. Dit [betalingsoptie](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-options.html#apple-pay-button) kunnen klanten de functie Touch ID op hun iOS- of macOS-apparaat gebruiken om Apple Pay te selecteren. Apple Pay verwerkt de betaling met de betalingsgegevens van de creditcard en de bankpas die op het apparaat zijn opgeslagen.

_28 juni 2021_

![Nieuw](../assets/new.svg)<!-- Issue PAY-1720 --> Geschillen met betrekking tot winkelbestellingen zijn nu beschikbaar in [het rapport betreffende de betalingsstatus van de opdracht](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html#view-disputes). Je kunt geschillen oplossen door rechtstreeks naar het PayPal Resolution Center te navigeren vanuit [!DNL Payment Services].

![Nieuw](../assets/new.svg)<!-- Issue PAY-2854 --> Verbeteringen in gebruikerservaring van [!DNL Payment Services] Het huis omvat de capaciteit om een configuratie op het huidige overervingsniveau en verbeteringen aan de vertoning van de kopbal en de navigatie te wijzigen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2854 --> U kunt nu waarschuwingen zien wanneer u overschakelt van de sandboxmodus naar de productiemodus en wanneer u probeert weg te navigeren van een weergave met updates die niet zijn opgeslagen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2761 --> U kunt de gegevens die worden weergegeven in het dialoogvenster [Betalingsstatusrapport bestellen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html#show-and-hide-columns) en de [Uitbetalingsrapport](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/payouts.html#show-and-hide-columns) door kolommen te tonen of te verbergen gebruikend de de montagecontrole van de Kolom.

+++

## v2.6.0

_4 juni 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-4877 --> Nu, [!DNL Payment Services] supports [Prijsmogelijkheden L2/L3](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/levels-card-payment-transactions.html). Deze functie is alleen beschikbaar voor [!DNL Payment Services] klanten met IC++ toegelaten tarifering. Als u L2/L3 verwerkingsgegevens wilt gebruiken voor [!DNL Payment Services], neemt u contact op met uw [!DNL Payment Services] accountmanager.

![Repareren](../assets/fix.svg)<!-- PAY-5455 -->[!DNL Payment Services] staat u toe om Apple Pay direct van de uitbreiding toe te laten zonder het downloaden en het ontvangen van [domeinkoppelingsbestand](https://developer.paypal.com/docs/checkout/apm/apple-pay/#register-your-live-domain).

## v2.5.0

_23 april 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- Issue PAY-5396 -->[!DNL Payment Services] now supports [Adobe Commerce-richtsnoeren voor de `--db-prefix` parameter](https://experienceleague.adobe.com/en/docs/commerce-operations/installation-guide/advanced#install-from-the-command-line) voor Adobe Commerce versie 2.4.7 en hoger.

## v2.4.3

_16 april 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- Issue PAY-5106 --> Probleem verholpen waarbij het totaal van de bestellingen onjuist werd ingevuld tijdens het afrekenen tussen PayPal en Adobe Commerce. Handelaars kunnen er nu voor zorgen dat de totalen van het orderbedrag correct zijn wanneer ze een bestelling plaatsen.

## v2.4.2

_11 april 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue xxx --> Extra ondersteuning voor Adobe Commerce 2.4.7.

## v2.4.1

_4 april 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- PAY-5322 --> Oplossing voor een PCI-compatibiliteitsprobleem met nieuwere Adobe Commerce-releases. Nu, [!DNL Payment Services] is aangepast aan de betalingsvereisten in Adobe Commerce als betalingsoptie.

![Repareren](../assets/fix.svg)<!-- PAY-5323 --> PayPal en Venmo worden correct weergegeven in Adobe Commerce. Probleem verholpen waarbij de optie voor het in- en uitschakelen van PayLater en Venmo niet werd toegestaan voor de beheerder.

## v2.4.0

_20 maart 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-4868 --> Handelaars kunnen [Google Pay gedurende de hele aankoop configureren](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/payments-options.html), vergelijkbaar met andere betalingsknoppen in[!DNL Payment Services] via de beheerder.

![Nieuw](../assets/new.svg)<!-- PAY-4381 --> [Betalingsservices ondersteunen Google Pay via GraphQL](https://developer.adobe.com/commerce/webapi/graphql/payment-services/) verkopers toestaan een headless Commerce-ervaring te hebben met de betalingsmethode Google Pay.

![Nieuw](../assets/new.svg)<!-- PAY-4878 --> Nu, [!DNL Payment Services] de basisfunctie voor afrekenen is gebundeld voor Adobe Commerce en Magento Open Source handelaren.[!DNL Payment Services] kan nu handelaren met bedrijven in om het even welke 200 geographies wereldwijd steunen.[!DNL Payment Services] standaardafhandeling biedt opties voor debiteren/crediteren, PayPal, Venmo (indien beschikbaar) en PayLater (indien beschikbaar) in een systeem voor automatische inboeking.

![Repareren](../assets/fix.svg)<!-- PAY-5291 --> Het ontvangen van een betalingsbevestiging voor bepaalde transacties kan worden uitgesteld. In dat geval kunnen verkopers nu een bijgewerkte betalingsstatus voor een bestelling krijgen. [Betalingsdiensten detecteren de hangende status van een betalingstransactie](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html) in een order door in behandeling zijnde transacties op te sporen en deze transacties proactief te controleren en bij te werken wanneer de status in behandeling is vastgelegd.

## v2.3.4

_1 maart 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-5244 --> Compatibiliteit met asynchrone uitchecken is hersteld.

![Repareren](../assets/fix.svg)<!-- PAY-5253 --> Correctie van een fout waarbij een vault-token niet tot [!DNL Payment Services] kan niet worden verwijderd.

## v2.3.3

_14 februari 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-5048 --> Extra ondersteuning voor PHP 8.3

![Repareren](../assets/fix.svg)<!-- PAY-5048 --> Oplossing voor een fout met de `is_deleted` markering. Bestellingen mislukken nu niet vanwege de `Rejected` status die vanuit de extensie is verzonden.

## v2.3.2

_26 januari 2024_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- PAY-5183 --> Problemen met REST/GraphQL-prestaties opgelost. De creditcardknop wordt nu weergegeven wanneer deze via de API wordt opgehaald.

## v2.3.1

_7 december 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-5047 --> Het type creditcard/bankpas of betalingsmethode is nu beschikbaar op de volgende locaties:
- de pagina van de klantenorde op de winkel
- het bevestigingsbericht voor bestelling dat naar de klant is verzonden
- van de [weergave orderdetails](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/order-management/orders/order-processing.html#view-an-order) in de Commerce Admin.

## v2.3.0

_1 december 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-4381 --> [Betalingsservices bieden nu ondersteuning voor GraphQL-integratie](https://developer.adobe.com/commerce/webapi/graphql/payment-services/). Met GraphQL-ondersteuning voor PayPal-betalingsknoppen, gehoste velden en Apple Pay,[!DNL Payment Services] ondersteunt nu een Commerce-installatie zonder kop.

## v2.2.1

_27 september 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4870 --> Probleem verholpen waarbij het nieuwe headerkenmerk onjuist werd ingevuld in Storefront bij het verzenden van de extensie-versie met de laatste release. Voorheen, met de `1.3.0` release van de Commerce Services-connector, kon u de `User-Agent header` van de [!DNL Payment Services] extensie.

## v2.2.0

_30 augustus 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- PAY-4638 --> Toegevoegde [integratie met handtekening](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/security-compliance/fraud-protection.html), die geautomatiseerde diensten ter bescherming van fraude verleent.

![Nieuw](../assets/new.svg)<!-- PAY-3981 --> [Betalen met Apple voor speciale betaling](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/payments-options.html?lang=en#apple-pay-button)buiten de PayPal-betalingsknoppen om de zichtbaarheid van de betalingsoptie voor winkeliers te vergroten en verkopers in staat te stellen de plaatsing en opmaak van Apple Pay te bepalen.

![Nieuw](../assets/new.svg)<!-- PAY-4002 --> Verbeterde gebruikerservaring bij het uitchecken van creditcardvelden, inclusief stijlverbeteringen zoals het toevoegen van betaalpictogrammen, om de cognitieve belasting van winkels te verlagen en conversies te verhogen.

![Nieuw](../assets/new.svg)<!-- PAY-4002 --> Toegevoegde functionaliteit om handelaren toe te staan [de volgorde van hun betalingsopties sorteren](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/configure/settings.html#payment-buttons) bepaalde betalingsopties voorrang te geven. Deze functionaliteit moedigt een hoger tarief van het controlegesprek aan.

![Nieuw](../assets/new.svg)<!-- PAY-4035 --> De handelaren kunnen nu efficiënt de gezondheid van hun opslag controleren en om het even welke transactiekwesties identificeren gebruikend de nieuwe [Transactierapport](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/transactions.html) beschikbaar via[!DNL Payment Services] Admin-startpagina. In het verslag worden ook gegevens gepresenteerd over de percentages van de transactievergunning en de negatieve tendensen in de transacties.

## v2.1.0

_9 juni 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue xxx --> Extra ondersteuning voor Adobe Commerce 2.4.7-bèta1.

![Nieuw](../assets/new.svg)<!-- Issue xxx --> Toegevoegd [beschikbaarheid in de volgende landen en geassocieerde valuta&#39;s](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.html#availability): Australië, Frankrijk, Verenigd Koninkrijk.

![Nieuw](../assets/new.svg)<!-- Issue PAY-4296 --> Toegevoegd [uitgebreide bronnen voor beheerdersrollen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/configure/settings.html#configure-roles) om ervoor te zorgen dat Admin-gebruikers orders voor klanten kunnen maken en beheren en dat ze[!DNL Payment Services] in het menu Verkoop.

![Nieuw](../assets/new.svg)<!-- Issue PAY-4236 --> Toegevoegd [automatisch ongeldig maken voor orders die fouten veroorzaken tijdens het uitchecken](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/checkout.html#order-auto-voided-if-error).

![Nieuw](../assets/new.svg)<!-- Issue PAY-4183 --> Functionaliteit gemaakt op [de knop voor de optie voor betaling via creditcard/bankpas weergeven](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/payments-options.html#debit-or-credit-card-button) op de uitcheckpagina.

## v2.0.0

_10 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-4152 --> Extra ondersteuning voor PHP 8.2 en Adobe Commerce 2.4.6. Niet compatibel met PHP 7.x.

## v1.6.1

_10 maart 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- Issue PAY-4226 --> Probleem verholpen waardoor nieuwe problemen werden voorkomen [!DNL Payment Services] verkopers kunnen het afrekenen in Admin gebruiken.[!DNL Payment Services] gebruikte voorheen de Commerce-klant-id, die niet bestaat voor nieuwe klanten.

![Repareren](../assets/fix.svg)<!-- Issue PAY-4205 --> Probleem opgelost waarbij de opgegeven staat van het verzendadres tijdens het afrekenen werd vervangen door de status in de standaard belastinginstellingen via de optie [PayPal-optie](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/payments-options.html#paypal-smart-buttons). Nu kunnen klanten hun bestellingen naar een andere staat laten verzenden dan die welke in de belastinginstellingen van de handelaar als standaard is geconfigureerd.

![Repareren](../assets/fix.svg)<!-- Issue PAY-4202 --> Probleem verholpen waarbij werd voorkomen dat klanten met een creditcard een aankoop konden voltooien of een geldige betalingsmethode voor een winkel konden verwijderen. Dit probleem is nu opgelost. [met de `Authorize and Capture` betalingsactie](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/get-started/production.html#set-payment-services-as-payment-method). Eerder werd een fout met betrekking tot de &quot;Provider Vault ID not found&quot; weergegeven toen de klant probeerde de gefactureerde creditcards te gebruiken of te wijzigen.

## v1.6.0

_17 februari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-3540 --> Toegevoegd [PGB 3DS-compatibiliteitskenmerk voor handelaren die handelen in de Europese Unie (EU) en Groot-Brittannië](security.md#3ds). Deze extra beveiligingslaag, die vereist dat kopers zich verifiëren bij hun creditcardmaatschappij, helpt internetfraude te voorkomen en is vereist in het kader van de EU-regelgeving inzake naleving.

![Nieuw](../assets/new.svg)<!-- Issue PAY-3609 --> De mogelijkheid toegevoegd om [kaartvaulatie inschakelen in de beheerder](vaulting.md#use-vaulting-in-the-admin). Op deze manier kunnen handelaren via hun gefactureerde betalingsmethoden een bestelling voor klanten in de beheerder maken.

## v1.5.4

_29 januari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4110 --> Probleem verholpen waarbij kopers een bestelling niet konden plaatsen met behulp van betalingsknoppen op de productpagina, miniwinkelwagentje en winkelwagentje. Kopers kunnen nu bestellingen voltooien.

## v1.5.3

_25 januari 2023_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-4102 --> Een oplossing vrijgegeven voor een incompatibel probleem. Met deze release wordt de extensie van de service-id vergrendeld op de nieuwste stabiele versie, waardoor nieuwe [!DNL Payment Services] installaties voor het configureren van Commerce Services.

## v1.5.2

_22 december 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3992 --> Betere facturering in [!DNL Payment Services] wanneer een betalingsmethode wordt afgewezen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3999 -->[!DNL Payment Services] geeft nu correct PayPal-betalingsknoppen voor verkopers weer met [Brandcontrole](https://commercemarketplace.adobe.com/swissup-firecheckout.html){target=_blank} aangepaste sjabloon voor de uitcheckpagina. Eerder werden de knoppen periodiek weergegeven door de minicart.

## v1.5.1

_23 november 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-3923 -->[!DNL Payment Services] omvat nu het versieaantal in de kopbal van de gebruikersagent zodat de verzoeken, ongebruikte eindpunten kunnen volgen, filtreren of verwerpen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3968 -->[!DNL Payment Services] geeft nu correct de ordergegevens weer wanneer een bestelling van de productpagina wordt geplaatst met behulp van betalingsknoppen.

## v1.5.0

_18 november 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-3880 --> Een winkelier kan nu [hun creditcardgegevens opslaan tijdens het afrekenen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/vaulting.html) gebruiken in een latere aankoop voor dezelfde of een andere winkel binnen dezelfde zakelijke account.

![Nieuw](../assets/new.svg)<!-- Issue PAY-3950 --> Handelaren kunnen nu de [Direct kopen, Commerce-functie](https://experienceleague.adobe.com/docs/commerce-admin/stores-sales/point-of-purchase/checkout-instant-purchase.html) voor hun winkels, zodat de koper het kan (gebruiken [gefactureerde creditcardgegevens](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-checkout/vaulting.html)) om het afrekenen te versnellen.

## v1.4.1

_14 oktober 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Repareren](../assets/fix.svg)<!-- Issue PAY-3766 --> Wanneer de betalingsmethode van een klant wordt afgewezen, is het zichtbare foutbericht beschrijverender. Het adviseert de klant om betalingsinformatie opnieuw in te voeren en opnieuw te proberen, een andere betalingsmethode te proberen, of hun bank over de geweigerde transactie te contacteren.

## v1.4.0

_30 september 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-784 -->[!DNL Payment Services] omvat nu de mogelijkheid om een zakelijke account in te stellen op [meerdere PayPal-zakelijke accounts gebruiken](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/configure/settings.html#use-multiple-paypal-accounts). Hierdoor kan de handelaar in meerdere landen uw winkels bedienen met verschillende valuta&#39;s, of Adobe Commerce gebruiken voor een deel van uw bedrijf.

![Nieuw](../assets/new.svg)<!-- Issue PAY-3231 --> Handelaren kunnen [toevoegen [!UICONTROL Soft Descriptor]](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/configure/settings.html#add-soft-descriptor) op websites of in afzonderlijke winkelweergaven wordt de configuratie weergegeven die op de bankafschriften van klanttransacties wordt getoond om merken, winkels of productlijnen te omlijnen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-3707 --> [De creditcardvelden en PayPal-betalingsknoppen in- of uitschakelen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/configure/settings.html#configure-payment-options) voor afhandeling binnen[!DNL Payment Services] instellingen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3546 --> Wanneer een klant klikt **[!UICONTROL Edit cart]**, wordt de pagina omgeleid naar de winkelwagentje en worden de bijgewerkte items weergegeven in plaats van dat er een leeg winkelwagentje wordt weergegeven.

## v1.3.1

_6 september 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3663 --> Wanneer de winkel van een handelaar een bestelling vastlegt die is geautoriseerd met een niet-globale valuta, wordt het vastlegproces voltooid en wordt geen fout weergegeven.

## v1.3.0

_9 augustus 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-XX --> Algemene beschikbaarheidsrelease—[!DNL Payment Services] is nu [ondersteund door [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.5](https://devdocs.magento.com/release/availability.html#compatibility).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-x --> Apple Pay is nu compatibel met Safari browser v15.5 op mobiele apparaten en desktops.

## v1.2.0

_29 juni 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-x --> Apple Pay is niet compatibel met Safari browser v15.5 op mobiele apparaten en desktops. Als je Safari versie 15.5 gebruikt, kun je het afrekenen met Apple Pay niet voltooien.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3264 --> Als een aangemelde gebruiker eerder een ander facturerings-/verzendadres dan het standaardadres voor zijn account had geselecteerd, is het afrekenen mislukt. Het geselecteerde facturerings-/verzendadres wordt nu verzonden (in plaats van het standaard opgeslagen adres) en de afhandeling is voltooid.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3314 --> Als u PayPal-betalingsknoppen uitschakelt voor afhandeling, worden geen fouten weergegeven.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3330 --> Betalingen mislukken niet meer tijdens het afrekenen wanneer een gastgebruiker een telefoonnummer invoert dat streepjes bevat.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3338 PAY-2502 --> Als de gebruikersgegevens van Commerce Services ongeldig zijn,[!DNL Payment Services] meldt u nu door een aanmeldingsfout van het dialoogvenster [!DNL Payment Services] Start in de Admin.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-0 --> [!DNL Payment Services] is onverenigbaar met `commerce-data-export` v101.20 en hoger, waardoor deze niet verenigbaar is met de [[!DNL Channel manager] extension](https://experienceleague.adobe.com/docs/commerce-channels/channel-manager/guide-overview.html).

## v1.1.0

_31 maart 2022_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease—[!DNL Payment Services] is nu [ondersteund door [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.4](https://devdocs.magento.com/release/availability.html#compatibility).

![Nieuw](../assets/new.svg)<!-- Issue PAY-2682 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] is nu beschikbaar voor Canadese handelaren. Handelaren kunnen de configuratie van betalingen in of bekijken [Frans](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.html?lang=fr#carte-de-cr%C3%A9dit-et-devises-accept%C3%A9es) of [Engels](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.html#accepted-credit-cards-and-currencies).

![Nieuw](../assets/new.svg)<!-- Issue PAY-2681 --> [!DNL Payment Services] supports [Canadese dollars (CAD)](overview.md#accepted-credit-cards-and-currencies) voor creditcards en PayPal-transacties.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2680 --> Handelaren kunnen [aan boord [!DNL Payment Services]](onboard.md) uitbreiding in de Engelse of Franse taal.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2678 --> Handelaren kunnen nu financiële rapporten bekijken, beide [Betalingsstatus bestellen](order-payment-status.md) en [Uitbetalingsrapporten](payouts.md), in Canadese dollars (CAD).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2710 -->[!DNL Payment Services] is nu compatibel met [PHP 8.1](https://www.php.net/releases/8.1/en.php).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3017 --> De verbeterde wijze van Sandbox alarm om juiste alarm met veelvoudige opslag te tonen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2742 --> U kunt nu beschikbare betalingsmethoden, zoals Venmo, in- en uitschakelen op het weergaveniveau van de winkel. Eerder kon u alleen betalingsmethoden per website configureren.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2277 --> U kunt nu selectief [afzonderlijke PayPal-betalingsknoppen in- of uitschakelen](settings.md#payment-buttons).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2561 --> Eerder verwijderde producten komen niet voor in het winkelwagentje op de _Revisievolgorde_ pagina.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2842 --> Creditcardtransacties testen [kan mislukken met PayPal](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-cc-sandbox-failure.html) bij het verwerken van betalingen in een sandbox-omgeving.

## v1.0.0

_29 november 2021_

[!BADGE Ondersteund]{type=Informative tooltip="Ondersteund"}

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease—[[!DNL Payment Services]](https://commercemarketplace.adobe.com/magento-payment-services.html) wordt nu ondersteund door [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot 2.4.3-p1.

![Nieuw](../assets/new.svg)<!-- Issue PAY-124 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] kan worden geïnstalleerd voor [[!DNL Adobe Commerce] over cloudinfrastructuur](install.md#adobe-commerce-on-cloud-infrastructure) of [In de bedrijfsruimten](install.md#on-premises) instanties. Deze methoden vereisen het gebruik van een opdrachtregelinterface.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] ondersteunt een [sandboxaccount](sandbox.md) die handelaren in staat stelt de uitbreiding in testmodus te beoordelen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-666 --> Handelaren kunnen [betalingsservices configureren](settings.md) uitbreiding met elementair betalingsgedrag, zoals [`Authorize and Capture`](production.md#set-payment-services-as-payment-method) schakelen tussen sandbox- of productieomgevingen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-780 --> Je kopers kunnen uitchecken met [!DNL Payment Services] of via [handbestelling maken](create-order.md).

![Nieuw](../assets/new.svg)<!-- Issue PAY-1856 --> Uitgebreide rapportage, via [Betalingsstatus bestellen](order-payment-status.md) en [Uitbetalingsrapporten](payouts.md), zijn beschikbaar voor [!DNL Payment Services] om je een duidelijk beeld te geven van de bestellingen en daarmee samenhangende betalingen van je winkel.

![Nieuw](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] ondersteunt flexibele, gedifferentieerde prijzen, gebaseerd op het totale verwerkingsvolume, aangepast aan elke handelaar.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1443 --> U kunt gemakkelijk [de vormgeving aanpassen](payments-options.md) van PayPal-betalingsknoppen en creditcardvelden voor de [!DNL Payment Services] extensie.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2473 --> Gebruiken [onjuiste Composer-sleutels](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-install.html) tijdens de installatie van de extensie voorkomt dat de gebruiker [verifiëren](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) met de juiste `MAGEID`.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] rapporten [kan niet meteen synchroniseren](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-report-info-delayed.html).

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2475 --> Uw [PayPal-sandboxaccount](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/payments/payservices-paypal-acct.html) for [!DNL Payment Services] kan niet worden geverifieerd als u dat account maakt tijdens het instappen.
