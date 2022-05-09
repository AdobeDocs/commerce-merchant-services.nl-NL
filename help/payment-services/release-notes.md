---
title: '"[!DNL Payment Services] Opmerkingen bij de release"'
description: Lees de opmerkingen bij de release voor meer informatie over alle [!DNL Payment Services] lozingen.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
source-git-commit: 9596815e31402f23b399b223f3221074331c1773
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Opmerkingen bij de release

In deze releaseopmerkingen wordt de eerste release van [!DNL Payment Services] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

## v1.1.0

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> [[!DNL Payment Services]](https://marketplace.magento.com/magento-payment-services.html) is nu compatibel met [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.4.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2682 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] is beschikbaar voor Canadese handelaren. Handelaren kunnen de configuratie van betalingen in of bekijken [Frans](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.html?lang=fr) of [Engels](https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/overview.html?lang=en).

![Nieuw](../assets/new.svg)<!-- Issue PAY-2681 --> [!DNL Payment Services] supports [Canadese dollars (CAD)](overview.md#accepted-credit-cards-and-currencies) met creditcard en PayPal. Klanten kunnen een winkelervaring hebben in hun voorkeurstaal, afhankelijk van de landinstelling van de winkel waar ze winkelen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2680 --> Handelaren kunnen [aan boord [!DNL Payment Services]](onboard.md) in de voorkeurstaal.

![Nieuw](../assets/new.svg)<!-- Issue PAY-2678 --> Handelaars kunnen nu bekijken [financiële verslagen](order-payment-status.md) in Canadese dollars (CAD).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2710 --> [!DNL Payment Services] is nu compatibel met [PHP 8.1](https://www.php.net/releases/8.1/en.php).

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3035 --> Verbeterde beheerderscontrole voor de [!DNL Payment Services] extensie.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-3017 --> De verbeterde wijze van Sandbox alarm om juiste alarm met veelvoudige opslag te tonen.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2742 --> [!DNL Payment Services] staat toe om beschikbare betalingsmethodes zoals Venmo op het voorraadniveau toe te laten/onbruikbaar te maken.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2277 --> Verbeterde mogelijkheden van de handelaar in Admin om slimme knopen van PayPal selectief onbruikbaar te maken/toe te laten.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2561 --> Eerder verwijderde producten komen niet voor in het winkelwagentje op de _Revisievolgorde_ pagina.

![Probleem opgelost](../assets/fix.svg)<!-- Issue PAY-2456 --> [!DNL Payment Services] verbetert de labels van de betalingsmethode in de beheerder.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2473 --> Gebruiken [onjuiste componentsleutels](https://support.magento.com/hc/en-us/articles/4406603542541) tijdens de installatie van de extensie voorkomt dat de gebruiker [authenticate](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) correct `MAGEID`.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] [rapporten](https://support.magento.com/hc/en-us/articles/4406114741517) voor betalingsstatus voor betaling via betaling en bestelling mag niet meteen worden gesynchroniseerd.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2475 --> [PayPal-sandboxaccount](https://support.magento.com/hc/en-us/articles/4406954952461) for [!DNL Payment Services] kan niet worden geverifieerd als er een account wordt gemaakt tijdens het instappen.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2842 --> [Kredietkaart testen mislukt](https://support.magento.com/hc/en-us/articles/5201041963917) met PayPal bij het verwerken van betalingen in een Sandbox-omgeving.

## v1.0.0

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease. [Betalingsdiensten](https://marketplace.magento.com/magento-payment-services.html) is nu compatibel met [!DNL Adobe Commerce] en [!DNL Magento Open Source] versies 2.4.0 tot en met 2.4.3-p1.

![Nieuw](../assets/new.svg)<!-- Issue PAY-124 --> De [!DNL Payment Services] verlenging voor [!DNL Adobe Commerce] en [!DNL Magento Open Source] kan worden geïnstalleerd voor [[!DNL Adobe Commerce] over cloudinfrastructuur](install.md#magento-commerce-cloud) of [In de bedrijfsruimten](install.md#on-premises) instanties. Deze methodes vereisen het gebruik van een Interface van de Lijn van het Bevel.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] ondersteunt een [sandboxaccount](onboard.md#enable-sandbox-testing) die handelaren in staat stelt de uitbreiding in testmodus te beoordelen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-666 --> Handelaren kunnen [Betalingsservices configureren](settings.md) uitbreiding met elementair betalingsgedrag (zoals Auth-capture samen en schakelen tussen sandbox- of productieomgevingen).

![Nieuw](../assets/new.svg)<!-- Issue PAY-780 --> Kopers kunnen uitchecken met [!DNL Payment Services] of u kunt de orde over de telefoon nemen en [een volledige volgorde maken](create-order.md) in de Admin voor hen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1856 --> [!DNL Payment Services] biedt handelaren uitgebreide rapportering aan, zodat u uw orders en betalingen in uw winkel duidelijk kunt bekijken.

![Nieuw](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] ondersteunt gedifferentieerde prijzen (gebaseerd op TPV), aangepast aan elke handelaar.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1443 --> Het is mogelijk om het uiterlijk van de PayPal-knoppen en de CC-velden voor de [Betalingsdiensten](payments-options.md) extensie.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2473 --> Gebruiken [onjuiste componentsleutels](https://support.magento.com/hc/en-us/articles/4406603542541) tijdens de installatie van de extensie voorkomt dat de gebruiker [authenticate](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) correct `MAGEID`.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] [rapporten](https://support.magento.com/hc/en-us/articles/4406114741517) voor betalingsstatus voor betaling via betaling en bestelling mag niet meteen worden gesynchroniseerd.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2475 --> [PayPal-sandboxaccount](https://support.magento.com/hc/en-us/articles/4406954952461) for [!DNL Payment Services] kan niet worden geverifieerd.
