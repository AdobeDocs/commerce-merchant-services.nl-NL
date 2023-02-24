---
title: Configuratie van Merchant Stores
description: Uitgebreide Inventory management-bronnen instellen als winkels.
role: User, Admin
level: Intermediate
exl-id: 7c3444d0-5ecb-4ac1-aa81-e48eea290f5d
source-git-commit: 4c10ab59ed304002cfde7398762bb70b223180ce
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Configuratie van Merchant Stores (bron)

Deze oplossing verbetert de native Inventory management-mogelijkheden door voorraadbronnen uit te breiden met op activiteiten gerichte functies voor handelaren.

- Geografische coördinaten toevoegen voor de opslaglocatie
- De bron aanwijzen als een [!DNL Store Pickup Location] en geef de beschikbare verzendmogelijkheden op (Verzenden naar winkel, Verzenden vanuit winkel)
- Geef beschikbare ophaalopties op (in-store of curbside), aangepaste ophaalinstructies en andere informatie om informatie over het ophalen van gegevens en instructies aan klanten door te geven

De voorwaarden _bron_ en _winkellocatie_ onderling verwisselbaar zijn. Alle verslagen zijn inventarisbronnen, maar de bronnen kunnen ook winkelplaatsen, afhankelijk van de configuratiemontages zijn.

Configuratie Merchant Stores beheren vanuit de beheerder: **[!UICONTROL Stores > Inventory > Sources >  Edit Source]**.

>[!NOTE]
>
>Tijdens het opstellingsproces, zou het noodzakelijk kunnen zijn om het geheime voorgeheugen te spoelen nadat u bronnen creeert of bestaande bronnen bijwerkt.

## **Algemeen**

<table>
<tbody>
<tr>
<th>Veld</th>
<th>Beschrijving</th>
<th>Toepassingsgebied</th>
<th>Vereist</th>
</tr>
<tr>
<td><strong>[!UICONTROL Latitude]</strong></br><code>Base Attribute: latitude</code></td>
<td>Coördinaat in de lengterichting van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Longitude]</strong></br><code>Base Attribute: Longitude</code></td>
<td>Lengtegraadcoördinaat van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Use as Pickup Location]</br></strong><code>Base Attribute: is_pickup_location_active</code></td>
<td>Wijs de bron aan als beschikbare ophaallocatie voor de winkel. Deze instelling bepaalt of de bron wordt gesynchroniseerd en aan bezoekers wordt weergegeven.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship to Store]</strong><br><code>Extension Attribute: allow_ship_to_store</code></td>
<td>Vorm schip-aan-opslagmogelijkheden op het bronniveau. Zie de optie [Algemene configuratie](enable-general.md) voor meer informatie. <strong>[!UICONTROL Enable Ship To Store]
</tr>
<tr>
<td><strong>[!UICONTROL Latitude]</strong></br><code>Base Attribute: latitude</code></td>
<td>Coördinaat in de lengterichting van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Longitude]</strong></br><code>Base Attribute: Longitude</code></td>
<td>Lengtegraadcoördinaat van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan.</td>
<td>Algemeen</td>
<td>Ja</td>
</tr>
<tr>
<td><strong>[!UICONTROL Use as Pickup Location]</br></strong><code>Base Attribute: is_pickup_location_active</code></td>
<td>Wijs de bron aan als beschikbare ophaallocatie voor de winkel. Deze instelling bepaalt of de bron wordt gesynchroniseerd en aan bezoekers wordt weergegeven.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship to Store]</strong></br> <code>Extension Attribute: [!DNL allow_ship_to_store]</code></td>
<td>Vorm schip-aan-opslagmogelijkheden op het bronniveau. Zie de optie [Algemene configuratie](enable-general.md) voor meer informatie. <strong>[!UICONTROL Enable Ship To Store]</strong>.</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong></br><code>Extension Attribute: [!DNL use_as_shipping_source]</code></td>
 <td>Vorm schip-van-opslag mogelijkheden op het bronniveau. Zie de optie [Algemene configuratie](enable-general.md) voor meer informatie. [!UICONTROL Enable Ship From Store].</td>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td>Algemeen</td>
<td>Nee</td>
</tr>
<tr>
<td><strong>[!UICONTROL Enable Ship From Store]</strong><code>Extension Attribute: [!DNL use_as_shipping_source]</code></td><td></td><td></td><td></td></tr></tbody></table>



| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Latitude]**</br>`Base Attribute: latitude` | Coördinaat in de lengterichting van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan. | Algemeen | Ja |
| **[!UICONTROL Longitude]**</br>`Base Attribute: Longitude` | Lengtegraadcoördinaat van de locatie van de winkel. Deze vereiste informatie wordt gebruikt in plaatsonderzoek en kaartplaatsing op de storefront ervaring. De waarde moet exact overeenkomen met het adres van de winkel om de validatie te kunnen doorstaan. | Algemeen | Ja |
| **[!UICONTROL Use as Pickup Location]**</br>`Base Attribute:[!DNL is_pickup_location_active]` | Wijs de bron aan als beschikbare ophaallocatie voor de winkel. Deze instelling bepaalt of de bron wordt gesynchroniseerd en aan bezoekers wordt weergegeven. | Algemeen | Nee |
| **[!UICONTROL Enable Ship to Store]**</br>`Extension Attribute: [!DNL allow_ship_to_store]` | Vorm schip-aan-opslagmogelijkheden op het bronniveau. Zie voor meer informatie de [Algemene configuratie](enable-general.md) optie, **[!UICONTROL Enable Ship To Store]**. | Algemeen | Nee |
| **[!UICONTROL Enable Ship From Store]**</br>`Extension Attribute: [!DNL use_as_shipping_source]` | Vorm schip-van-opslag mogelijkheden op het bronniveau. Zie voor meer informatie de [Algemene configuratie](enable-general.md) optie, [!UICONTROL Enable Ship From Store] | Algemeen | Nee |

{style=&quot;table-layout:auto&quot;}

## Configuratie van ophaallocatie

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Allow In-Store Pickup]**</br>`Extension Attribute: [!DNL store_pickup_enabled]` | Een van de twee ophaalopties. [!DNL In-Store Pickup] verwijst naar de mogelijkheid om een klant toe te staan de locatie van de winkel te betreden om zijn bestelling op te halen. </br></br>Als deze optie is ingeschakeld, wordt deze mogelijk tijdens het uitchecken aan de klant getoond. </br></br>Met deze optie wordt ook de algemene configuratie overschreven naar [!UICONTROL Enable In-store Pickup] dat op [!UICONTROL Delivery Method] for [!UICONTROL In-store Pickup] | Algemeen | Nee |
| **Instructies voor het in-store ophalen**</br>`Extension Attribute: store_pickup_instructions` | Een aanpasbaar bericht dat aan de klant in **Bestelling gereed voor afhalen in winkel** e-mailmelding. | Algemeen | Nee |
| **Curbside toestaan**</br>`Extension Attribute: curbside_enabled` | Een van de twee ophaalopties. Met de curbside-levering kan een klant zijn voertuig op een bepaalde plaats in de winkel parkeren. In dit scenario, wordt de orde geleverd aan de klant door een opslagvennoot. </br></br>Als deze optie ingeschakeld is, kan deze tijdens het afrekenen aan de klant worden getoond. Tijdens het inchecken kan de klant ook worden gevraagd om zijn voertuig en parkeerplaats te beschrijven. </br></br>Met deze optie wordt ook de algemene configuratie overschreven naar **Ophalen curbside inschakelen** dat op **Leveringsmethode** for **Ophalen in winkel** | Algemeen | Nee |
| **[!UICONTROL Curbside Instructions]**</br>`Extension Attribute: curbside_instructions` | Een aanpasbaar bericht dat aan de klant in [!UICONTROL Order Ready For Pickup in Store] e-mailmelding. | Algemeen | Nee |
| **[!UICONTROL Estimated Pickup Lead Time]**</br>`Extension Attribute: pickup_lead_time` | Het aantal minuten dat is vereist voordat een bestelling wordt ontvangen, opgepakt en klaar is om te worden opgepakt. </br></br>Met deze informatie worden geschatte tijden weergegeven voor het ophalen van bestellingen voor klanten op de website.</br></br> Als u deze optie instelt, wordt de algemene configuratie voor **Geschatte levertijd voor afhalen** geconfigureerd voor de **Leveringsmethode** in de **Ophalen in winkel** configuratie. | Algemeen | Nee |
| **[!UICONTROL Estimated Pickup Time Label]**</br>`Extension Attribute: pickup_time_label` | Label dat het aantal minuten weergeeft totdat een bestelling klaar is om te worden opgepakt.</br></br> Wanneer u dit label aanpast, kunt u de code %1 gebruiken om uw **Geschatte levertijd voor afhalen**.</br></br> Als u deze optie instelt, wordt de algemene configuratie voor [!UICONTROL Estimated Pickup Time Label] geconfigureerd voor de [!UICONTROL Delivery Method] in de [!UICONTROL In-store Pickup]. | Algemeen | Nee |

### **Openingstijden**

| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Location Timezone]**</br>`Extension Attribute: timezone` | The timezone of the merchant store location. Stel voor elke dag de openings- en sluitingstijden in.</br></br>Deze instellingen worden gebruikt voor het optimaliseren van geschatte ophaaltijden en voor het rapporteren van servicerapporten. | Algemeen | Ja |
| **[!UICONTROL Opening Hours]**</br>`Internal Attribute: inventory_source_opening_hours_dynamic_rows` | De openingstijden voor de locatie van de winkel. </br></br>Deze informatie kan worden gebruikt om geschatte ophaaltijden te optimaliseren, en in de rapportering van de uitvoeringsdienst. | Algemeen | Ja |

### Interfaceopties voor Inchecken van ervaring configureren



| **Veld** | **Beschrijving** | **Toepassingsgebied** | **Vereist** |
|---------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|--------------|
| **[!UICONTROL Use Parking Spots]**</br>`Extension Attribute: parking_spots_enabled` | Geef op of de locatie van de winkel parkeerplaatsen voor curbside heeft. </br></br>Wanneer toegelaten, kunt u beschikbare parkeerplaatsen vormen. | Algemeen | Nee |
| **[!UICONTROL Is Parking Spot a Mandatory Field?]**</br>`Extension Attribute: parking_spot_mandatory` | Geef tijdens het winkelen aan of parkeerplaatsidentificatie vereist is voor klanten.</br></br>Indien ingeschakeld, wordt de klant gevraagd zijn parkeerplaats bij aankomst op te geven. Als deze optie is uitgeschakeld, kan de klant deze invoer overslaan. | Algemeen | Nee |
| **[!UICONTROL Parking Spots List]**</br> `Internal Attribute: inventory_source_parking_spot_dynamic_rows` | De beschikbare parkeerplaatsen beschikbaar op deze winkelplaats van de koophandel voor krullende bestelwagen. Gebruik de opgegeven interface om elke vlek een naam te geven.</br></br> U hoeft niet elke parkeerplaats een naam te geven, alleen de plaatsen die voor de rand zijn aangewezen. U hebt bijvoorbeeld rijen A-G voor parkeren beschikbaar, maar alleen de eerste 8 punten van rij A zijn bedoeld voor ophalen op de rand. In dit scenario, zou u 8 vlekken kunnen bepalen; ex: A1, A2, A3, enzovoort. | Algemeen | Nee |
| **[!UICONTROL Allow "Other" Parking Spot Field]**</br>`Extension Attribute: custom_parking_spot_enabled` | Als deze instelling is ingeschakeld, kan de klant zijn parkeerplaats tijdens inchecken beschrijven. | Algemeen | Nee |
| **[!UICONTROL Use Car Color]**</br>`Extension Attribute: use_car_color` | Geef op of de verzameling van voertuigkleuren door de klant tijdens de inchecken moet worden ondersteund. </br></br> De beschikbare selecties voor [!UICONTROL Car Color] worden geconfigureerd in de beheerder [systeeminstellingen voor de ervaring van inchecken](check-in-experience-setup.md). | Algemeen | Nee |
| **[!UICONTROL Is Car Color a Mandatory Field?]**</br>`Extension Attribute: car_color_mandatory` | Geef tijdens het inchecken op of voor klanten kleuridentificatie van het voertuig is vereist.</br></br>Indien ingeschakeld, wordt de klant gevraagd de kleur van het voertuig bij aankomst aan te geven. Als deze optie is uitgeschakeld, kan de klant deze invoer overslaan. | Algemeen | Nee |
| **[!UICONTROL Use Car Make]** </br>`Extension Attribute: use_car_make` | Geef aan of de verzameling van voertuigproducten van de klant tijdens de inchecken moet worden ondersteund.</br></br> De beschikbare selecties voor [!UICONTROL Car Make] worden geconfigureerd in de beheerder [systeeminstellingen voor de ervaring van inchecken](check-in-experience-setup.md). | Algemeen | Nee |
| **[!UICONTROL Is Car Make a Mandatory Field?]**</br>`Extension Attribute: car_make_mandatory` | Geef tijdens het inchecken aan of identificatie van het voertuig vereist is voor klanten.</br></br>Indien dit mogelijk is, wordt de klant gevraagd het merk van het voertuig bij aankomst aan te geven. Als deze optie is uitgeschakeld, kan de klant deze invoer overslaan. | Algemeen | Nee |
| **[!UICONTROL Use Additional Information]**</br> `Extension Attribute: use_additional_information` | Specificeer of om inzameling van extra informatie van de klant tijdens Controle-binnen te steunen. | Algemeen | Nee |
| **[!UICONTROL Is Additional Information a Mandatory Field?]**</br>`Extension Attribute: additional_information_mandatory` | Geef tijdens het inchecken op of er aanvullende informatie nodig is voor klanten. </br></br>Indien ingeschakeld, wordt de klant gevraagd om aanvullende informatie bij aankomst in te voeren. Als deze optie is uitgeschakeld, kan de klant deze invoer overslaan. | Algemeen | Nee |
