---
title: Profielrecords
description: Leer welke gegevens een profielrecord vastlegt.
role: Admin, Developer
feature: Personalization, Integration, Eventing
exl-id: bd04730d-e37a-48a9-822b-0f4aa68a4651
source-git-commit: 89607d22ba8e69e0c98fce97e041022e33d01c07
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# [!DNL Data Connection] Profielrecords (bèta)

Hieronder worden de Commerce-profielrecordgegevens beschreven die beschikbaar zijn wanneer u de [!DNL Data Connection] extensie. De gegevens in profielrecords worden naar de Adobe Experience Platform verzonden.

## Profielrecord

De recordupdates van het profiel zijn beschikbaar in het Experience Platform wanneer een nieuw profiel wordt gemaakt, bijgewerkt of verwijderd.

### Gegevens verzameld uit profielrecord

Hieronder worden de gegevens beschreven die zijn vastgelegd voor een profielrecord.

| Veld | Beschrijving |
|---|---|
| `channel` | Bevat informatie over de bron van de gegevens. Beide `_id` en `_type` bevatten [naamruimte waarden](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/namespaces.html). |
| `channel._id` | De unieke id van het kanaal, zoals `"https://ns.adobe.com/xdm/channels/web"`. |
| `channel._type` | Hiermee wordt de bron van de kanaalgegevens geïdentificeerd, zoals `"https://ns.adobe.com/xdm/channel-types/web"`. |
| `person` | Bevat informatie over de klant. |
| `person.name` | Bevat informatie over de naam van de klant. |
| `person.name.firstName` | Bevat de voornaam van de klant. |
| `person.name.lastName` | Bevat de achternaam van de klant. |
| `person.birthDate` | Geboortedatum van de verkoopster. |
| `personalEmail` | Een persoonlijk e-mailadres. |
| `personalEmail.address` | Het technische adres, bijvoorbeeld `name@domain.com` zoals algemeen gedefinieerd in RFC2822 en volgende normen. |
| `billingAddress` | Het postadres van de facturering. |
| `billingAddress.street1` | Primaire straatinformatie, appartementnummer, straatnummer en straatnaam. |
| `billingAddress.street2` | Optionele straatinformatie, tweede regel. |
| `billingAddress.city` | De naam van de stad. |
| `billingAddress.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `billingAddress.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `billingAddressPhone` | Het telefoonnummer dat aan het factuuradres is gekoppeld. |
| `billingAddressPhone.number` | Het telefoonnummer. Het telefoonnummer is een tekenreeks en kan betekenisvolle tekens bevatten, zoals vierkante haakjes `()`, koppeltekens `-`of tekens om subdialing-id&#39;s aan te geven, zoals extensies `x` bijvoorbeeld:  `1-353(0)18391111` of `+613 9403600x1234`. |
| `shippingAddress` | Het postadres voor verzending. |
| `shippingAddress.street1` | Primaire straatinformatie, appartementnummer, straatnummer en straatnaam. |
| `shippingAddress.street2` | Optionele straatinformatie, tweede regel. |
| `shippingAddress.city` | De naam van de stad. |
| `shippingAddress.state` | De naam van de staat. Dit is een veld met vrije vorm. |
| `shippingAddress.country` | De naam van het door de overheid bestuurde gebied. andere dan `xdm:countryCode`Dit is een veld met vrije vorm dat de naam van het land in elke taal kan hebben. |
| `shippingAddressPhone` | Telefoonnummer gekoppeld aan het verzendadres. |
| `shippingAddressPhone.number` | Het telefoonnummer. Het telefoonnummer is een tekenreeks en kan betekenisvolle tekens bevatten, zoals vierkante haakjes `()`, koppeltekens `-`of tekens om subdialing-id&#39;s aan te geven, zoals extensies `x` bijvoorbeeld:  `1-353(0)18391111` of `+613 9403600x1234`. |
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.startDate` | De datum waarop het profiel voor het eerst is gemaakt. |

>[!NOTE]
>
>Elke profielrecord bevat ook de [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) veld, waarin de door het systeem gegenereerde Commerce-klant-id als primaire id voor het profiel en een e-mailid die als secundaire id wordt gebruikt, zijn opgenomen.

Leer hoe u [een profielrecordspecifiek schema maken](profile-data.md) die de gegevens uit uw profielrecords kunnen opnemen.
