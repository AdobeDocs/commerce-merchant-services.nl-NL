---
title: Beveiliging en naleving
description: Beoordeel de beveiligings- en compatibiliteitsvereisten voor uw site.
exl-id: 083c5a12-1d78-48b5-b9e3-612b104ce7e0
feature: Payments, Checkout, Compliance
redirect_from: https://experienceleague.adobe.com/docs/commerce-merchant-services/payment-services/security.html
source-git-commit: fef972355565472f0d0851a2e3cace692fb2db67
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# Beveiliging en naleving

Veiligheid is een van de belangrijkste aandachtspunten in [!DNL Payment Services] en er worden geen door de private sector of de betaalkaartindustrie (PCI) gereguleerde gegevens doorgegeven aan uw [!DNL Payment Services].

## Handelsbeveiliging

[!DNL Adobe Commerce] en [!DNL Magento Open Source] omvat ondersteuning voor verschillende beveiligingsfuncties.

Zie [Beveiliging](https://docs.magento.com/user-guide/stores/security.html){target="_blank"} in de basisgebruikershandleiding voor het controleren van best practices op het gebied van beveiliging en het beheren van Admin-sessies en -gegevens, het implementeren van CAPTCHA en het beheren van websitebeperkingen.

## PCI-compatibiliteit

De betaalkaartindustrie (PCI) heeft een reeks vereisten vastgesteld voor bedrijven die betalingen via een creditcard via internet accepteren. Naast het handhaven van een veilige omgeving, zijn de handelaren die de informatie van de klantencreditcard behandelen verantwoordelijk voor het voldoen aan sommige standaardrichtlijnen.

Zie [PCI-compatibiliteitsrichtlijnen](https://docs.magento.com/user-guide/stores/compliance-pci.html){target="_blank"} voor meer informatie .

Handelaren kunnen een [vragenlijst voor zelfbeoordeling (SAQ)](https://www.pcisecuritystandards.org/pci_security/completing_self_assessment){target="_blank"}, een zelfvalideringsinstrument voor het beoordelen van de beveiliging van gegevens van kaarthouders.

### Creditcardvelden

Met de Gebieden van de Kaart, worden geen PCI-Gereglementeerde gegevens overgegaan over uw diensten. U hoeft die gegevens niet op te slaan of te onderhouden, wat de bezorgdheid over PCI-compatibiliteit aanzienlijk vermindert.

### 3DS

PCI 3-D Secure (3DS) maakt kopersverificatie mogelijk met hun creditcardmaatschappij wanneer ze online aankopen doen op creditcards. Deze extra veiligheidslaag helpt fraude op het internet te voorkomen en is vereist in het kader van de EU-regelgeving inzake naleving.

[!UICONTROL Payment Services] biedt 3DS-functionaliteit om handelaren in staat te stellen te voldoen aan de EU-regelgeving en om klanten en handelaren te beschermen tegen frauduleuze activiteiten in hun winkels.

Als u een handelaar bent binnen de EU of Groot-Brittannië waar 3DS-compatibiliteit vereist is, moet u 3DS handmatig inschakelen (het is `Off` standaard) in [Instellingen](settings.md#credit-card-fields).

>[!NOTE]
>
>Het 3DS-vereiste is van toepassing op transacties waarbij het bedrijf en de bank van de kaarthouder zich in de [Europese Economische Ruimte](https://www.efta.int/eea) (EER) en Groot-Brittannië. Handelaren in de Verenigde Staten hebben geen 3DS nodig, maar kunnen deze desgewenst inschakelen voor hun transacties.

Orders die door het bedrijfs-/winkelpersoneel voor de koper worden geplaatst, zijn niet geconfigureerd met 3DS-compatibiliteitsmaatregelen.

Zie [3DS in instellingen](settings.md#3ds) voor meer informatie .

### Kaart vauleren

Wanneer een winkelier [vaults—of &quot;save&quot;—hun creditcardgegevens](vaulting.md) voor toekomstige aankopen in uw winkels worden minimale creditcardgegevens gedeeld met de winkel (laatste vier cijfers, vervaldatum van de kaart en het merk kaart). Creditcardgegevens worden opgeslagen bij de betalingsdienstaanbieder. Wanneer een kaart verloopt of wanneer de gegevens niet meer hoeven te worden opgeslagen, kunnen zij die token verwijderen, zodat de informatie niet langer door de betalingsdienstaanbieder wordt opgeslagen.

Zie [Creditcard vaulting](vaulting.md) voor meer informatie .

### Slimme PayPal-knoppen

Met de slimme knoppen van PayPal worden er geen gegevens doorgegeven die door PCI zijn gereguleerd. U hoeft die gegevens niet op te slaan of te onderhouden, wat de bezorgdheid over PCI-compatibiliteit aanzienlijk vermindert.

Om veiligheidsredenen geeft PayPal het factuuradres niet door tijdens het afrekenen. Land, e-mail en naam zijn de enige factuurgegevens die worden gebruikt. U kunt desgewenst het PayPal-afhandeling van uw site inschakelen om het volledige factureringsadres te retourneren door contact op te nemen met PayPal en een controleproces te voltooien.

PayPal heeft ook geïntegreerde fraudebescherming die computerleren gebruikt om fraude te bestrijden. Zie PayPal&#39;s [Documentatie voor kopersbescherming](https://www.paypal.com/us/webapps/mpp/security/seller-protection) voor meer informatie .

## Fraudebescherming

U kunt automatische fraudebescherming voor Betalingsdiensten inschakelen met de [Extensie ondertekenen](https://commercemarketplace.adobe.com/signifyd-module-connect.html).

Zie [Ondertekening van de fraudebescherming](fraud-protection.md) voor meer informatie .

