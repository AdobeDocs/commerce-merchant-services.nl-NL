---
title: '"[!DNL Quick Checkout] Opmerkingen bij de release"'
description: Lees de opmerkingen bij de release voor meer informatie over alle [!DNL Quick Checkout] lozingen.
source-git-commit: dc13c1e38c92341cfd3221a72e6568220b44690a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Opmerkingen bij de release

In deze releaseopmerkingen wordt de eerste release van [!DNL Quick Checkout] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

Zie [Volgende releases](https://devdocs.magento.com/release/) om over versieschema&#39;s en steun te leren.

Zie [Beschikbaarheid](https://devdocs.magento.com/release/availability.html) in de documentatie voor ontwikkelaars voor meer informatie over productcompatibiliteit.

## v1.0.0

![Nieuw](../assets/new.svg)<!-- Issue BOLT-341 --> Algemene beschikbaarheidsrelease—[[!DNL Quick Checkout]](https://marketplace.magento.com/magento-quick-checkout.html) is nu compatibel met Adobe Commerce-versies 2.4.1 tot en met 2.4.4.

![Nieuw](../assets/new.svg)<!-- Issue BOLT-340 --> De [!DNL Quick Checkout] voor Adobe Commerce kan ofwel voor Adobe Commerce worden geïnstalleerd [over cloudinfrastructuur](install.md#adobe-commerce-on-cloud-infrastructure) of [ter plaatse](install.md#on-premises) instanties. Deze methodes vereisen het gebruik van een bevel-lijn interface.

![Nieuw](../assets/new.svg)<!-- Issue BOLT-1 --> De [!DNL Quick Checkout] voor Adobe Commerce biedt een geoptimaliseerde winkel die een [één-klik het afrekenen ervaring](overview.md) zonder vulvelden die voor de consument vereist zijn.

![Nieuw](../assets/new.svg)<!-- Issue BOLT-1 --> De [!DNL Quick Checkout] voor Adobe Commerce herkent automatisch elke verkoopster in zijn netwerk voor [aankopen met één klik](checkout-flow.md) rechtstreeks op uw site.

![Nieuw](../assets/new.svg)<!-- Issue BOLT-218 --> [!DNL Quick Checkout] voor Adobe Commerce ondersteunt een [sandboxaccount](testing.md#testing-in-sandbox) die handelaren in staat stelt de uitbreiding in testmodus te beoordelen.

![Nieuw](../assets/new.svg)<!-- Issue BOLT-780 --> Je kopers kunnen uitchecken via de [[!DNL Quick Checkout]](checkout-page.md) of via een [handbestelling maken](create-order-admin.md).

![Nieuw](../assets/new.svg)<!-- Issue BOLT-666 --> Handelaars kunnen de [!DNL Quick Checkout] met basisbetalingsacties, zoals [`Authorize and Capture` of `Authorize` ](onboarding.md#complete-admin-configuration)of schakelen tussen sandbox- en productieomgevingen.

![Bekend probleem](../assets/bug.svg)<!-- Issue BOLT-342 --> Gebruiken [onjuiste Composer-sleutels](https://support.magento.com/hc/en-us/articles/6909450342541) tijdens de installatie van de [!DNL Quick Checkout] voorkomt dat de gebruiker [verifiëren](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) met de juiste `MAGEID`.