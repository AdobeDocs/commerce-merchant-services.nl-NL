---
title: Fraudebescherming ondertekenen
description: Automatische fraudebescherming inschakelen voor [!DNL Payment Services] met handtekening.
role: Admin, User
level: Intermediate
feature: Payments, Checkout, Configuration, Security
exl-id: 440296bb-a6ff-408b-8195-3027916e4f84
source-git-commit: 480b35fbc57b8528dbc305aa7db52483ba49d98c
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# Ondertekening van de fraudebescherming

U kunt automatische fraudebescherming inschakelen voor [!DNL Payment Services] met de [Extensie ondertekenen](https://commercemarketplace.adobe.com/signifyd-module-connect.html).

Adobe Commerce ondersteunt ondertekenende versies 5.4.0 en hoger. [!DNL Payment Services] ondersteunt pre-auth- en post-auth-Signifyd-stromen.

De handtekening/[!DNL Payment Services] Deze integratie biedt dekking voor creditcards, debetkaarten, kluizen, uitchecken via de betalingsmethoden Admin en PayPal en Apple Pay. Hoewel sommige details van de transacties niet worden gedeeld door Betalingsdiensten en Ondertekenen, biedt Signifyd uitgebreide risicodekking voor alle betalingsmethoden, waardoor een maximale bescherming wordt geboden.

Zie [Ondertekeningsdocumentatie](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#downloadandinstallingmagento2extension) voor meer informatie over het installeren en configureren van de extensie.

## Onboarding

U moet rechtstreeks communiceren met Handtekening aan boord van de extensie voor gebruik met [!DNL Payment Services]—er is geen [!DNL Payment Services] benodigde configuratie. U kunt de extensie Handtekening configureren in Beheer nadat deze is geïnstalleerd. Alle ondersteuning met betrekking tot deze extensie wordt beheerd door Ondertekenen.

Wanneer u aan boord gaat met handtekening, moet u:

1. Neem contact op met de ondertekenaar om een nieuwe account in te stellen.
1. Standaard is Ondertekenen [gevoegd op lijst van gewenste personen](https://github.com/signifyd/magento2/blob/main/docs/RESTRICT-PAYMENTS.md) om ervoor te zorgen dat de handtekening niet wordt geactiveerd voor andere betalingsopties die momenteel niet worden ondersteund. Als u een bepaalde betalingsmethode wilt verbieden, moet u wijzigingen aanbrengen.
1. Bevestig met Ondertekenen dat PayPal geen bestellingen afwijst die via de instelling voor fraudebescherming van de handelaar in Paypal kunnen worden goedgekeurd door Ondertekenen.
1. De extensie Ondertekenen compatibel maken met [!DNL Payment Services]:
   * Wanneer u [!DNL Payment Services] in _Live_ modus, moet Ondertekenen zich in de productiemodus bevinden.
   * Wanneer u [!DNL Payment Services] in _Sandbox_ in de modus Ondertekenen moet de modus Testen zijn ingeschakeld.

## Configuratie

Omdat Signifyd enige actie op uw orden neemt, is het noodzakelijk om de uitbreiding te vormen om zich geschikt gebaseerd op de betalingsactie te gedragen u plaatst voor [!DNL Payment Services].

Deze configuratieopties zijn niet compatibel met Betalingsservices en de integratie Ondertekenen:

* Wanneer [!DNL Payment Services] is geconfigureerd met de `Authorize` betalingsactie _en_ Ondertekening bevindt zich in `PostAuth` met de _[!UICONTROL Decline Guarantees]_optie ingesteld op **Creditnota maken**.

  Reden: [!DNL Payment Services] maakt een machtigingstransactie die wordt uitgevoerd met Signify en vervolgens probeert de waarde te herstellen.


* [!DNL Payment Services] is geconfigureerd met de `Authorize and Capture` betalingsactie _en_ Ondertekening bevindt zich in `PostAuth` met de _[!UICONTROL Decline Guarantees]_optie ingesteld op **Bestelling annuleren**.

  Reden: [!DNL Payment Services] maakt een vastleggingstransactie die tijdens de ondertekening wordt geannuleerd.


Zie Ondertekende documentatie voor informatie over [configureren, extensie](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#configuringmagento2extension).

Zie Ondertekende documentatie voor [meer informatie over de workflows voor bestellingen](https://community.signifyd.com/support/s/article/magento-2-extension-install-guide?language=en_US#howmagento2works).
