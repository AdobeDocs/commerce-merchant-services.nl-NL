---
title: Beveiliging en naleving
description: Beoordeel de beveiligings- en compatibiliteitsvereisten voor uw site.
exl-id: 083c5a12-1d78-48b5-b9e3-612b104ce7e0
source-git-commit: c993a2afe5b4da478ab57cbb391bb524d83c3d1a
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Beveiliging en naleving

Veiligheid is een van de belangrijkste aandachtspunten in [!DNL Payment Services] en er worden geen door de private sector of de betaalkaartindustrie (PCI) gereguleerde gegevens doorgegeven aan uw [!DNL Payment Services].

## Handelsbeveiliging

[!DNL Adobe Commerce] en [!DNL Magento Open Source] omvat ondersteuning voor verschillende beveiligingsfuncties.

Zie [Beveiliging](https://docs.magento.com/user-guide/stores/security.html){target=&quot;_blank&quot;} in de core user guide om de best practices op het gebied van beveiliging te bekijken en te leren hoe u Admin-sessies en -gegevens beheert, CAPTCHA implementeert en websitebeperkingen beheert.

## PCI-compatibiliteit

De betaalkaartindustrie (PCI) heeft een reeks vereisten vastgesteld voor bedrijven die betalingen via een creditcard via internet accepteren. Naast het handhaven van een veilige omgeving, zijn de handelaren die de informatie van de klantencreditcard behandelen verantwoordelijk voor het voldoen aan sommige standaardrichtlijnen.

Zie [PCI-richtlijnen voor compatibiliteit](https://docs.magento.com/user-guide/stores/compliance-pci.html){target=&quot;_blank&quot;} voor meer informatie.

Handelaren kunnen een [vragenlijst voor zelfbeoordeling (SAQ)](https://www.pcisecuritystandards.org/pci_security/completing_self_assessment){target=&quot;_blank&quot;}. Dit is een zelfvalidatieprogramma voor het beoordelen van de beveiliging van gegevens van kaarthouders.

### Creditcardvelden

Met de Gebieden van de Kaart, worden geen PCI-Gereglementeerde gegevens overgegaan over uw diensten. U hoeft die gegevens niet op te slaan of te onderhouden, wat de bezorgdheid over PCI-compatibiliteit aanzienlijk vermindert.

### Kaart vauleren

Wanneer een winkelier [vaults—of &quot;save&quot;—hun creditcardgegevens](vaulting.md) voor toekomstige aankopen in uw winkels worden minimale creditcardgegevens gedeeld met de winkel (laatste vier cijfers, vervaldatum van de kaart en het merk kaart). Creditcardgegevens worden opgeslagen bij de betalingsdienstaanbieder. Wanneer een kaart verloopt of wanneer de gegevens niet meer hoeven te worden opgeslagen, kunnen zij die token verwijderen, zodat de informatie niet langer door de betalingsdienstaanbieder wordt opgeslagen.

### Slimme PayPal-knoppen

Met de slimme knoppen van PayPal worden er geen gegevens doorgegeven die door PCI zijn gereguleerd. U hoeft die gegevens niet op te slaan of te onderhouden, wat de bezorgdheid over PCI-compatibiliteit aanzienlijk vermindert.

Om veiligheidsredenen geeft PayPal het factuuradres niet door tijdens het afrekenen. Land, e-mail en naam zijn de enige factuurgegevens die worden gebruikt. U kunt desgewenst het PayPal-afhandeling van uw site inschakelen om het volledige factureringsadres te retourneren door contact op te nemen met PayPal en een controleproces te voltooien.

PayPal heeft ook geïntegreerde fraudebescherming die computerleren gebruikt om fraude te bestrijden. Zie PayPal&#39;s [Documentatie voor kopersbescherming](https://www.paypal.com/us/webapps/mpp/security/seller-protection) voor meer informatie .
