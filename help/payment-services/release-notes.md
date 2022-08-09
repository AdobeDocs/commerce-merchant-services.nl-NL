---
title: '"[!DNL Payment Services] Opmerkingen bij de release"'
description: Lees de opmerkingen bij de release voor meer informatie over alle [!DNL Payment Services] lozingen.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
source-git-commit: 2c3211d5a6574f84fa499608f5ef0cb8c6ffcfed
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# Opmerkingen bij de release

In deze releaseopmerkingen wordt de eerste release van [!DNL Payment Services] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

Voor eigenschapveranderingen en moeilijke situaties die buiten de regelmatige versieversie worden vrijgegeven, zie de Gehoste sectie van de de dienstupdates.

Zie [Volgende releases](https://devdocs.magento.com/release/) om over versieschema&#39;s en steun te leren.

Zie [Beschikbaarheid](https://devdocs.magento.com/release/availability.html) in de documentatie voor ontwikkelaars voor meer informatie over productcompatibiliteit.

## v1.3.0

_9 augustus 2022_

![Nieuw](../assets/new.svg)<!-- Issue PAY-XX --> Algemene beschikbaarheidsrelease—[!DNL Payment Services] is nu [compatibel met [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.5](https://devdocs.magento.com/release/availability.html#compatibility).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-x --> Apple Pay is nu compatibel met Safari browser v15.5 op mobiele apparaten en desktops.

## v1.2.0

_29 juni 2022_

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-x --> Apple Pay is niet compatibel met Safari browser v15.5 op mobiele apparaten en desktops. Als je Safari versie 15.5 gebruikt, kun je het afrekenen met Apple Pay niet voltooien.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3264 --> Eerder, toen een aangemelde gebruiker een ander facturerings/verzendadres dan het standaardadres voor zijn account selecteerde, mislukte het afrekenen. We hebben dit probleem opgelost en nu wordt het geselecteerde factuuradres/verzendadres verzonden (in plaats van het standaard opgeslagen adres) en wordt het afrekenen voltooid.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3314 --> Als u de slimme PayPal-knoppen uitschakelt voor afhandeling, worden geen fouten weergegeven.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3330 --> Betalingen mislukken niet meer tijdens het afrekenen wanneer een gastgebruiker een telefoonnummer invoert dat streepjes bevat.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3338 PAY-2502 --> Wanneer de referenties van de Commerce Services ongeldig zijn, wordt [!DNL Payment Services] Thuis wordt nu weergegeven in Beheer. Er wordt een verificatiefout weergegeven om u te waarschuwen dat uw referenties ongeldig zijn.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-0 --> [!DNL Payment Services] is momenteel onverenigbaar met de [`commerce-data-export` v101.20 en hoger](https://github.com/magento-commerce/commerce-data-export/releases/tag/v101.2.0), waardoor deze onverenigbaar is met de [[!DNL Channel manager] extension](https://experienceleague.adobe.com/docs/commerce-channels/channel-manager/guide-overview.html).

### Gehoste service-updates

Deze versienota&#39;s beschrijven eigenschapveranderingen en moeilijke situaties die voorkwamen en buiten de regelmatige versieversies van de eigenschapsuitgave, tussen de huidige versie v1.2.0 en vorige 1.1.0 versie voor de ontvangen dienst werden vrijgegeven.

![Nieuw](../assets/new.svg)<!-- Issue PAY-3420 --> Apple Pay is nu beschikbaar als een slimme PayPal-knop. Dit [betalingsoptie](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/payments-options.html#apple-pay-button) biedt klanten de mogelijkheid om met Touch ID op hun apparaten Apple Pay te gebruiken. Hierbij worden de betalingsgegevens van de creditcard en de bankpas gebruikt die op hun iOS- of macOS-apparaten zijn opgeslagen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1720 --> Geschillen met betrekking tot winkelbestellingen zijn nu beschikbaar in [het rapport betreffende de betalingsstatus van de opdracht](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html#view-disputes). U kunt rechtstreeks naar het PayPal Resolution Center navigeren vanuit [!DNL Payment Services] om geschillen te beslechten.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2854 --> Verbeteringen in gebruikerservaring van [!DNL Payment Services] Het huis omvat de capaciteit om een configuratie op het huidige overervingsniveau en verbeteringen aan vertoning van de kopbal en de navigatie te wijzigen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2854 --> U kunt nu waarschuwingen zien wanneer u overschakelt van de sandboxmodus naar de productiemodus en wanneer u probeert weg te navigeren van een weergave met updates die niet zijn opgeslagen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2761 --> U kunt nu de gegevens aanpassen die worden weergegeven in het dialoogvenster [Betalingsstatusrapport bestellen](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/order-payment-status.html#show-and-hide-columns) en de [Uitbetalingsrapport](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/reporting/payouts.html#show-and-hide-columns) door kolommen te tonen of te verbergen gebruikend de de montagecontrole van de Kolom.

## v1.1.0

_31 maart 2022_

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease—[!DNL Payment Services] is nu [compatibel met [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.4](https://devdocs.magento.com/release/availability.html#compatibility).

![Nieuw](../assets/new.svg)<!-- Issue PAY-2682 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] is nu beschikbaar voor Canadese handelaren. Handelaren kunnen de configuratie van betalingen in of bekijken [Frans](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.md#accepted-credit-cards-and-currencies) of [Engels](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.md#accepted-credit-cards-and-currencies).

![Nieuw](../assets/new.svg)<!-- Issue PAY-2681 --> [!DNL Payment Services] supports [Canadese dollars (CAD)](overview.md#accepted-credit-cards-and-currencies) voor creditcards en PayPal-transacties.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2680 --> Handelaren kunnen [aan boord [!DNL Payment Services]](onboard.md) uitbreiding in de Engelse of Franse taal.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2678 --> Handelaren kunnen nu financiële rapporten bekijken, beide [Betalingsstatus bestellen](order-payment-status.md) en [Uitbetalingsrapporten](payouts.md), in Canadese dollars (CAD).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2710 --> [!DNL Payment Services] is nu compatibel met [PHP 8.1](https://www.php.net/releases/8.1/en.php).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3017 --> De verbeterde wijze van Sandbox alarm om juiste alarm met veelvoudige opslag te tonen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2742 --> U kunt nu beschikbare betalingsmethoden, zoals Venmo, in- en uitschakelen op het weergaveniveau van de winkel. Eerder kon u alleen betalingsmethoden per website configureren.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2277 --> U kunt nu selectief [individuele PayPal smart-knoppen in- of uitschakelen](settings.md#payment-buttons).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2561 --> Eerder verwijderde producten komen niet voor in het winkelwagentje op de _Revisievolgorde_ pagina.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2842 --> Creditcardtransacties testen [kan mislukken met PayPal](https://support.magento.com/hc/en-us/articles/5201041963917) bij het verwerken van betalingen in een sandbox-omgeving.

## v1.0.0

_29 november 2021_

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease—[[!DNL Payment Services]](https://marketplace.magento.com/magento-payment-services.html) is nu compatibel met [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.3-p1.

![Nieuw](../assets/new.svg)<!-- Issue PAY-124 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] kan worden geïnstalleerd voor [[!DNL Adobe Commerce] over cloudinfrastructuur](install.md#adobe-commerce-on-cloud-infrastructure) of [In de bedrijfsruimten](install.md#on-premises) instanties. Deze methodes vereisen het gebruik van een Interface van de Lijn van het Bevel.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] ondersteunt een [sandboxaccount](sandbox.md) die handelaren in staat stelt de uitbreiding in testmodus te beoordelen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-666 --> Handelaren kunnen [betalingsservices configureren](settings.md) uitbreiding met elementair betalingsgedrag, zoals [`Authorize and Capture`](production.md#set-payment-services-as-payment-method) schakelen tussen sandbox- of productieomgevingen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-780 --> Je kopers kunnen uitchecken met [!DNL Payment Services] of via [handbestelling maken](create-order.md).

![Nieuw](../assets/new.svg)<!-- Issue PAY-1856 --> Uitgebreide rapportage, via [Betalingsstatus bestellen](order-payment-status.md) en [Uitbetalingsrapporten](payouts.md), zijn beschikbaar voor [!DNL Payment Services] om je een duidelijk beeld te geven van de bestellingen en daarmee samenhangende betalingen van je winkel.

![Nieuw](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] ondersteunt flexibele, gedifferentieerde prijzen, gebaseerd op het totale verwerkingsvolume, aangepast aan elke handelaar.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1443 --> U kunt gemakkelijk [de vormgeving aanpassen](payments-options.md) van PayPal slimme knoppen en creditcardvelden voor de [!DNL Payment Services] extensie.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2473 --> Gebruiken [onjuiste Composer-sleutels](https://support.magento.com/hc/en-us/articles/4406603542541) tijdens de installatie van de extensie voorkomt dat de gebruiker [verifiëren](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) met de juiste `MAGEID`.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] rapporten [kan niet meteen synchroniseren](https://support.magento.com/hc/en-us/articles/4406114741517).

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2475 --> Uw [PayPal-sandboxaccount](https://support.magento.com/hc/en-us/articles/4406954952461) for [!DNL Payment Services] kan niet worden geverifieerd als u dat account maakt tijdens het instappen.
