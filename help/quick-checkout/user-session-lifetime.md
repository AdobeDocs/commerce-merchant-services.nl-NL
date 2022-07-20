---
title: Gebruikssessielevensduur
description: De beheerder biedt de mogelijkheid om de levensduur van de cookie van uw Adobe Commerce-gebruiker te configureren voor de [!DNL Quick Checkout] extensie.
source-git-commit: a95d2ed92c69feba03d1b84d44abf08c1d1b4029
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# Gebruikssessielevensduur

De levensduur van een winkelsessie wordt bepaald door verschillende factoren die in uw Adobe Commerce-beheerder kunnen worden geconfigureerd. Zie [De cookielevensduur configureren](https://docs.magento.com/user-guide/customers/customer-online-options.html){target=_blank} voor meer informatie.

De geconfigureerde levensduur van cookies kan van invloed zijn op uw [!DNL Quick Checkout] if:

1. Door inactiviteit, wordt de verkoopster geregistreerd uit Adobe Commerce.
1. De [!DNL Bolt] sessie verloopt.

Als een winkelier een order plaatst wanneer [!DNL Bolt] sessie verloopt, wordt de volgorde correct geplaatst, maar de gebruiker wordt afgemeld via beide netwerken.

Als de gebruiker na een geslaagde afhandeling nog steeds actief is, wordt hij niet afgemeld bij zowel Adobe Commerce als [!DNL Bolt].
