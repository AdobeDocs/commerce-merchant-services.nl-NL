---
title: Gebruikssessielevensduur
description: De beheerder biedt de mogelijkheid om de levensduur van de cookie van uw Adobe Commerce-gebruiker te configureren voor de [!DNL Quick Checkout] extensie.
exl-id: 32cf5d70-9a50-49ca-8b40-5f04bc1e24b7
source-git-commit: 2f14cd437be6d48e24e56b3b31a1c640357b27e3
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# Gebruikssessielevensduur

De levensduur van een winkelsessie wordt bepaald door verschillende factoren die in uw Adobe Commerce-beheerder kunnen worden geconfigureerd. Zie [De cookielevensduur configureren](https://experienceleague.adobe.com/docs/commerce-admin/customers/customer-accounts/configure/customer-online-options.html){target=_blank} voor meer informatie.

De geconfigureerde levensduur van cookies kan van invloed zijn op uw [!DNL Quick Checkout] if:

1. Door inactiviteit, wordt de verkoopster geregistreerd uit Adobe Commerce.
1. De [!DNL Bolt] sessie verloopt.

Als een winkelier een order plaatst wanneer [!DNL Bolt] sessie verloopt, wordt de volgorde correct geplaatst, maar de gebruiker wordt afgemeld via beide netwerken.

Als de gebruiker na een geslaagde afhandeling nog steeds actief is, wordt hij niet afgemeld bij zowel Adobe Commerce als [!DNL Bolt].
