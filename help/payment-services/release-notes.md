---
title: '"[!DNL Payment Services] Opmerkingen bij de release"'
description: Lees de opmerkingen bij de release voor meer informatie over alle [!DNL Payment Services] lozingen.
exl-id: 104aa2c7-7735-4ac2-8ed1-a03cd9911273
source-git-commit: eb8fdba65b4b64730d0ad4fa6e0c9b64bdadc7df
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Opmerkingen bij de release

In deze releaseopmerkingen wordt de eerste release van [!DNL Payment Services] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

## v1.0.0

![Nieuw](../assets/new.svg)<!-- Issue PAY-2127 --> Algemene beschikbaarheidsrelease. [Betalingsdiensten](https://marketplace.magento.com/magento-payment-services.html) is nu compatibel met Adobe Commerce en Magento Open Source versies 2.4.0 tot en met 2.4.3-p1.

![Nieuw](../assets/new.svg)<!-- Issue PAY-124 --> De [!DNL Payment Services] extensie voor Adobe Commerce en Magento Open Source kunnen worden geïnstalleerd voor [Adobe Commerce over cloudinfrastructuur](install.md#magento-commerce-cloud) of [In de bedrijfsruimten](install.md#on-premises) instanties. Deze methodes vereisen het gebruik van een Interface van de Lijn van het Bevel.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1986 --> [!DNL Payment Services] ondersteunt een [sandboxaccount](onboard.md#enable-sandbox-testing) die handelaren in staat stelt de uitbreiding in testmodus te beoordelen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-666 --> Handelaren kunnen [Betalingsservices configureren](configure-admin.md) uitbreiding met elementair betalingsgedrag (zoals Auth-capture samen en schakelen tussen sandbox- of productieomgevingen).

![Nieuw](../assets/new.svg)<!-- Issue PAY-780 --> Kopers kunnen uitchecken met [!DNL Payment Services] of u kunt de orde over de telefoon nemen en [een volledige volgorde maken](create-order.md) in de Admin voor hen.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1856 --> [!DNL Payment Services] biedt handelaren uitgebreide rapportering aan, zodat u uw orders en betalingen in uw winkel duidelijk kunt bekijken.

![Nieuw](../assets/new.svg)<!-- Issue PAY-311 --> [!DNL Payment Services] ondersteunt gedifferentieerde prijzen (gebaseerd op TPV), aangepast aan elke handelaar.

![Nieuw](../assets/new.svg)<!-- Issue PAY-1443 --> Het is mogelijk om het uiterlijk van de PayPal-knoppen en de CC-velden voor de [Betalingsdiensten](https://devdocs.magento.com/payment-services/customize-buttons-messaging.html) extensie.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2473 --> Gebruiken [onjuiste componentsleutels](https://support.magento.com/hc/en-us/articles/4406603542541) tijdens de installatie van de extensie voorkomt dat de gebruiker [authenticate](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) correct `MAGEID`.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2474 --> [!DNL Payment Services] [rapporten](https://support.magento.com/hc/en-us/articles/4406114741517) voor betalingsstatus voor betaling via betaling en bestelling mag niet meteen worden gesynchroniseerd.

![Bekend probleem](../assets/bug.svg)<!-- Issue PAY-2475 --> [PayPal-sandboxaccount](https://support.magento.com/hc/en-us/articles/4406954952461) for [!DNL Payment Services] kan niet worden geverifieerd.
