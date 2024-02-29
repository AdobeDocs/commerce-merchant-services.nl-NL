---
title: Profielrecords
description: Leer welke gegevens een profielrecord vastlegt.
role: Admin, Developer
feature: Personalization, Integration, Eventing
source-git-commit: 99d1097b98ea18c8a317613b2366a97db131432f
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# [!DNL Data Connection] Profielrecords

Hieronder worden de recordgegevens van het Commerce-profiel beschreven die beschikbaar zijn wanneer u de [!DNL Data Connection] extensie. De gegevens in profielrecords worden naar de Adobe Experience Platform verzonden.

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
| `userAccount` | Hiermee geeft u eventuele loyaliteitsdetails, voorkeuren, aanmeldingsprocessen en andere accountvoorkeuren aan. |
| `userAccount.startDate` | De datum waarop het profiel voor het eerst is gemaakt. |

>[!NOTE]
>
>Elke profielrecord bevat ook de [`identityMap`](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/identitymap.html) veld, dat het e-mailadres van de verkoper, indien beschikbaar, en de ECID bevat.

Leer hoe u [een profielrecordspecifiek schema maken](profile-data.md) die de gegevens uit uw profielrecords kunnen opnemen.
