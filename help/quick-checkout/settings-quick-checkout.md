---
title: Configureer de [!DNL Quick Checkout] voor Adobe Commerce-extensie
description: Leer de configuratieopties voor de [!DNL Quick Checkout] en hoe u de extensie met succes aan boord kunt instellen.
exl-id: 892e04dc-17d6-45e9-b2ab-c7a0735a75bc
source-git-commit: b89427124cf76e7f36076454949191ee1d88f52c
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# [!DNL Quick Checkout] Instellingen

[!DNL Quick Checkout] voor Adobe Commerce en Magento Open Source verstrekt een configuratiemening met alle noodzakelijke informatie aan opstelling de uitbreiding.

Deze configuratie-instellingen openen:

1. Op de _Beheer_ zijbalk, ga naar **Winkels** > _Instellingen_ > **Configuratie**.
1. Vouw in het linkerdeelvenster uit **Verkoop** en selecteert u **Afhandeling**.

   ![Snelle afhandeling](assets/configuration-view.png)

Zie de [Onboarding](../quick-checkout/onboarding.md) onderwerp voor meer informatie over hoe te om te vormen [!DNL Quick Checkout] voor Adobe Commerce.

## Extensie inschakelen

![Snelle afhandeling](assets/enable-method.png)

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Enable] | website | In- of uitschakelen [!DNL Quick Checkout] voor uw website. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Method] | website | Stel de methode of omgeving in voor uw [!DNL Quick Checkout]. Opties: [!UICONTROL Sandbox] / [!UICONTROL Production] |

{style=&quot;table-layout:auto&quot;}

## Accountgegevens

![Snelle afhandeling](assets/account-creds.png)

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL API key] | website | Een persoonlijke sleutel die door uw achterste eind wordt gebruikt om met elkaar in wisselwerking te staan [!DNL Bolt] API&#39;s. |
| [!UICONTROL Publishable key] | website | Een toets die door uw voorzijde wordt gebruikt om te communiceren met [!DNL Bolt] API&#39;s. |
| [!UICONTROL Signing secret] | website | Wordt gebruikt voor handtekeningverificatie op aanvragen die zijn ontvangen van [!DNL Bolt]. |

{style=&quot;table-layout:auto&quot;}

## Service-instellingen

![Snelle afhandeling](assets/service-settings.png)

| Veld | Toepassingsgebied | Beschrijving |
|---|---|---|
| [!UICONTROL Title] | winkelweergave | Voeg de tekst die tijdens het afrekenen wordt weergegeven als titel voor deze betalingsoptie toe aan de weergave Betalingsmethode. Opties: [!UICONTROL text field] |
| [!UICONTROL Payment Action] | website | De [betalingsactie](https://docs.magento.com/user-guide/configuration/sales/payment-methods.html#payment-actions){target="_blank"} voor de opgegeven betalingsmethode. Opties: [!UICONTROL Authorize] / [!UICONTROL Authorize and Capture] |
| [!UICONTROL Debug Mode] | website | De foutopsporingsmodus in- of uitschakelen. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Enable checkout tracking] | website | Definieer of Adobe Commerce het delen van trackinggegevens voor afhandeling met Bolt toestaat. Standaard ingeschakeld. Als deze optie is uitgeschakeld, heeft dit gevolgen voor de rapportage. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Next Stage After Login Mode] | website | Navigatiestroom wijzigen nadat de klant is aangemeld. Opties: [!UICONTROL Payment] / [!UICONTROL Shipping] |
| [!UICONTROL Automatic Login Enabled] | website | Definiëren als [!DNL Quick Checkout] Hiermee kunt u zich automatisch aanmelden tijdens het afrekenen. Standaard ingeschakeld. Opties: [!UICONTROL Yes] / [!UICONTROL No] |
| [!UICONTROL Automatic Login Network] | website | Selecteer het netwerk waar de klant zich automatisch aanmeldt. Standaard ingeschakeld. Opties: [!UICONTROL Bolt + Merchant] / [!UICONTROL Bolt] |

{style=&quot;table-layout:auto&quot;}
