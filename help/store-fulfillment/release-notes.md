---
title: '[!DNL Store Fulfillment by Walmart Commerce Technologies] Aanvullende informatie'
description: "Controleer de opmerkingen bij de release voor informatie over alle [!DNL Store Fulfillment by Walmart Commerce Technologies] releases."
role: Admin, User, Leader
feature: Shipping/Delivery, Release Notes
exl-id: 04dcec10-fff8-483d-a2c1-4b58e063e0f0
source-git-commit: 78b09113e72382053b01d6016276bae3aa545fa3
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 2%

---

# Aanvullende informatie

In deze releaseopmerkingen wordt de eerste release van [!DNL Store Fulfillment Services by Walmart Commerce Technologies] en omvatten:

![Nieuw](../assets/new.svg) Nieuwe functies
![Probleem opgelost](../assets/fix.svg) Oplossingen en verbeteringen
![Bekend probleem](../assets/bug.svg) Bekende problemen

## v1.5.0

*3 augustus 2023*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}[Adobe Commerce 2.4.4 tot en met 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html), inclusief de beveiligingspatchreleases 2.4.6-p1, 2.4.5-p3 en 2.4.4-p4.

Deze release bevat de volgende updates:

![Nieuw](../assets/fix.svg) De extensie is bijgewerkt voor ondersteuning [Adobe Commerce Security patch releases](https://experienceleague.adobe.com/docs/commerce-operations/release/notes/security-patches/overview.html) 2.4.6-p1, 2.4.5-p3, en 2.4.4-p4.

![Nieuw](../assets/new.svg)<!-- WMTP-918 --> Extra ondersteuning voor de [Asynchroon verzenden](sales-emails.md) configuratieoptie voor verkoopberichten. Handelaars die een upgrade naar versie 1.5.0 uitvoeren, kunnen e-mailberichten direct (standaard) of asynchroon verzenden.

![Nieuw](../assets/new.svg)<!-- WMTP-916--> De [Bronconfiguratie](merchant-store-configuration.md) ter ondersteuning van internationale telefoonnummerformaten.

![Nieuw](../assets/new.svg) Toegevoegde logica om te voorkomen dat terugbetalingsbedragen het resterende of gefactureerde bedrag overschrijden.

![Nieuw](../assets/new.svg)<!-- WMTP-882 --> Vervangen `google.map.LatLng` object met JSON-literals ter ondersteuning van compatibiliteit met oudere versies van [!DNL Google Maps].

![Probleem opgelost](../assets/fix.svg)<!-- WMTP- --> Het script waarmee het `[!DNL Available for Store Pickup]` en `[!DNL Available for Home Delivery]` productkenmerken om conflicten met kenmerkcategorieën te voorkomen.

![Probleem opgelost](../assets/fix.svg)<!-- WMTP-915 --> Probleem met compatibiliteit verholpen waarbij een oneindige lus werd veroorzaakt bij het laden en opslaan van bepaalde entiteiten.

![Probleem opgelost](../assets/fix.svg)<!-- WMTP-921 --> Probleem verholpen dat was voorkomen [!DNL Ship to Store] De bevestiging van citaten van het teweegbrengen wanneer een punt aan het karretje van een productdetailpagina (PDP) wordt toegevoegd.

![Probleem opgelost](../assets/fix.svg)<!-- WMTP- 932 --> Probleem met uitchecken waarbij klanten de methode voor thuislevering konden selecteren voor items die niet in aanmerking kwamen voor thuislevering, is opgelost.

![Probleem opgelost](../assets/fix.svg) Installatie-updates:

- <!-- WMTP-880--> Probleem verholpen waarbij een onjuiste websitecode werd geretourneerd tijdens de installatie van de [!DNL Store Fulfillment] extensie.

- <!-- WMTP-878--> Probleem verholpen met betrekking tot SKU-gehele getallen waarbij het gegevenstype tijdens de installatie naar tekenreekstype moest worden gecast.

![Probleem opgelost](../assets/fix.svg)<!-- WMTP-915--> Probleem verholpen die werd veroorzaakt door een ontbrekende code voor een incheckfout.

![Probleem opgelost](../assets/fix.svg)<!-- WMTP-932 --> Oplossing voor een probleem met betrekking tot gedeeltelijke afwijzing tijdens dispensatiebewerkingen.

![Nieuw](../assets/new.svg)<!-- WMTP-953 --> Het eindpunt van de API voor annuleren is bijgewerkt zodat de statusparameter als een optioneel object kan worden gebruikt.

![Nieuw](../assets/new.svg)<!-- WMTP-960 --> Verbeterde logboekdetails voor het eindpunt van Dispense API.

## v1.4.0

*13 april 2023*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

![Nieuw](../assets/fix.svg) [!DNL Store Fulfillment] is nu [compatibel met [!DNL Adobe Commerce] 2.4.4 tot en met 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).


## v1.3.0

*27 februari 2023*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Deze release bevat de volgende update:

![Nieuw](../assets/fix.svg)<!-- WMTP-795 --> De mogelijkheid toegevoegd om de oplossing Opslaglimiet voor een specifieke site uit te schakelen door het standaardbereik voor de instelling Systeemconfiguratie te wijzigen van de website in global.

## v1.2.0

*27 september 2022*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Deze release bevat de volgende update:

![Nieuw](../assets/fix.svg) [!DNL Store Fulfillment] is nu [compatibel met [!DNL Adobe Commerce] 2.4.4 t/m 2.4.5](https://experienceleague.adobe.com/docs/commerce-operations/release/product-availability.html).


## v1.1.0

*15 juli 2022*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Stabiliteit: algemene beschikbaarheid

![Nieuw](../assets/fix.svg)<!-- WMTP-731 --> Vereenvoudigd [Configuratie voor inchecken van ervaringen](check-in-experience-setup.md) voor de app Winkelassistentie door standaardselecties voor auto&#39;s en modellen toe te voegen. In de vorige versie moesten handelaren de selecties van het merk en het model van de auto handmatig configureren.

## v1.0.0

*4 maart 2022*

[!BADGE Compatibiliteit]{type=Informative tooltip="Compatibiliteit"}

Stabiliteit: algemene beschikbaarheid

## App Winkelassistentie

Voor informatie over nieuwe releases van de app Store Assist raadpleegt u de toepassingsinformatie in het gedeelte [Apple App Store](https://apps.apple.com/us/app/store-assist-by-walmart/id1609281539){target="_blank"} or [Google Play store](https://play.google.com/store/apps/details?id=com.walmart.faas.storeassist){target="_blank"}.
