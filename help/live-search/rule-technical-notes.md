---
title: '"Technische opmerkingen van de regel"'
description: '"Technische opmerkingen over het gebruik [!DNL Live Search] regels."'
exl-id: 24ff6a19-f7cd-42f7-b466-fc18f9091504
source-git-commit: bffbede99865e9085f60392e474065a454446370
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 0%

---

# Technische opmerkingen regel

[!DNL Live Search] de regels brengen acties teweeg die op een verscheidenheid van vraagvoorwaarden worden gebaseerd en geven verkopers de capaciteit om de onderzoekservaring voor diverse scenario&#39;s te vormen.

De huidige release van [!DNL Live Search] de regels zijn gebaseerd op het vraagkoord dat door de verkoopster, eerder dan op de reeks teruggekeerde resultaten is ingegaan. Een queryreeks kan alfanumerieke tekens bevatten en het hoofdlettergebruik wordt genegeerd. Net als bij facetten en synoniemen worden regels opgeslagen in `protobuf dynamo`. Bij vraagtijd, wint de onderzoeksdienst regels door terug `grpc` oproepen aan `search-admin-service`.
