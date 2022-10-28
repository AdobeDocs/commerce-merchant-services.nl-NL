---
title: Cookie-beperkingen verwerken
description: Leer hoe aanbevelingen voor producten cookie-beperkingen verwerken.
source-git-commit: 81ab2e22b0ec81e97d27ee135c88b50731a3986d
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Cookie-beperkingen verwerken

Zowel Adobe Commerce als Magento Open Source vragen om toestemming voordat gegevens in browsercookies worden opgeslagen. Raadpleeg voor meer informatie [Modus Koekjesbeperking](https://experienceleague.adobe.com/docs/commerce-admin/start/compliance/privacy/compliance-cookie-law.html).

Wanneer u `magento/product-recommendations` in plaats van te produceren, begint het winkelinteractiegebeurtenissen op je winkel te verzamelen. Omdat de gegevens voor deze gebeurtenissen in browser koekjes of lokale opslag kunnen worden opgeslagen, steunt de eigenschap koekjesbeperkingswijze door geen gebeurtenissen te verzamelen tot de verkoopster koekjestoestemming heeft gegeven.

Dit werkt mogelijk niet met oplossingen voor cookie van derden. Het is de verantwoordelijkheid van elke handelaar om ervoor te zorgen dat er geen gegevens worden verzameld voordat toestemming voor het gebruik van cookies is gegeven, zoals vaak wettelijk vereist is. Als u de toestemming van een cookie beheert met aangepaste code, kunt u een niet-bijgehouden cookie gebruiken met de naam `mg_dnt` het verzamelen van gegevens te beperken.

- Naam van de cookie:

   ```text
   `const DNT_COOKIE = "mg_dnt";`
   ```

- Stel het cookie niet bijhouden in om gegevensverzameling uit te schakelen:

   ```text
   `$.mage.cookies.set(DNT_COOKIE, true);`
   ```

- De cookie wissen wanneer de gebruiker cookies heeft geaccepteerd:

   ```text
   `$.mage.cookies.clear(DNT_COOKIE);`
   ```
