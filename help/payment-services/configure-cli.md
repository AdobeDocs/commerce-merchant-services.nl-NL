---
title: Configuratie opdrachtregel
description: Na installatie kunt u configureren [!DNL Payment Services] het gebruiken van de bevel-lijn Interface (CLI).
role: Admin, Developer
level: Intermediate
exl-id: 265ab1be-fe52-41f3-85cb-addbc2ddfb17
source-git-commit: 817a01e98876bddf5f41a253501984539b3351cd
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Configuratie opdrachtregel

Na de installatie [!DNL Payment Services]kunt u het eenvoudig configureren vanuit [binnen de woning](payments-home.md) of via de bevel-lijn Interface (CLI).

## Gegevens exporteren configureren

[!DNL Payment Services] combineert ordergegevens die zijn geëxporteerd van [!DNL Magento Open Source] en [!DNL Adobe Commerce] met geaggregeerde betalingsgegevens van betalingsdienstaanbieders om nuttige rapporten op te stellen. De [!DNL Payment Services] de uitbreiding gebruikt indexeerders om alle noodzakelijke gegevens voor de rapporten efficiënt te verzamelen.

Meer informatie over de gegevens die worden gebruikt in [!DNL Payment Services] melden, zie [Betalingsstatusrapport bestellen](order-payment-status.md#data-used-in-the-report).

### Uitsnede configureren ingeschakeld [!DNL Magento Open Source]

Als u een `BY SCHEDULE` indexmodus ingeschakeld [!DNL Magento Open Source]moet u uitsnijden configureren. Zie [Uitsnede configureren en uitvoeren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html).

### Indexeerders instellen

De gegevens van de orde worden uitgevoerd en in de Betalingsdienst voortgeduurd, gebruikend één van twee indexwijzen—`ON SAVE` (standaardwaarde) of `BY SCHEDULE` (aanbevolen).

De volgende indexen zijn bedoeld voor [!DNL Payment Services]:

| Code | Naam | Beschrijving |
|    ---    |  ---  |  ---  |
| `sales_order_data_exporter` | Feed verkooporder | Index van ordergegevens samenstellen |
| `sales_order_status_data_exporter` | Statussen verkooporder Feed | Index van statussen van verkooporders samenstellen |
| `store_data_exporter` | Winkelfeed | Index van opslaggegevens samenstellen |

Voer de volgende handelingen uit om de indexmodus voor alle drie de indexen te wijzigen:

```bash
bin/magento indexer:set-mode schedule sales_order_data_exporter sales_order_status_data_exporter store_data_exporter
```

>[!TIP]
>
>Als u geen indexeerders in uw bevel specificeert, worden alle indexeerders bijgewerkt aan de zelfde waarde. Als u een specifieke indexeerder wilt veranderen, moet u het in uw bevel vermelden.

Voor meer informatie over het manueel veranderen van de wijze van een indexeerder, zie [Indexeerders configureren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html#configure-indexers){target="_blank"} in the developer documentation. To learn how to change it in the Admin, see [Index management](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target="_blank"} in de basisgebruikershandleiding.

### Gegevens handmatig opnieuw indexeren

U kunt gegevens handmatig opnieuw indexeren in plaats van te wachten tot dit automatisch gebeurt. Zie [Opnieuw indexeren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html#reindex){target="_blank"} in [Manage the Indexers](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html){target="_blank"} voor meer informatie .

Wanneer `BY SCHEDULE` wordt ingesteld, worden entiteiten gewijzigd in de systeemtracks en wordt de index voor deze entiteiten bijgewerkt op basis van een ingestelde planning. Zie [Uitsnijden uitvoeren vanaf de opdrachtregel](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html#config-cli-cron-group-run) in [Uitsnede configureren en uitvoeren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-cron.html)) om te leren hoe u indexatie handmatig kunt activeren met behulp van uitsnijdtaken.

### Geïndexeerde gegevens naar betalingsservice verzenden

Nadat de gegevens zijn geïndexeerd, worden deze automatisch verzonden naar [!DNL Payment Services]. U kunt het proces van het verzenden van geïndexeerde gegevens met dit bevel ook manueel teweegbrengen:

```bash
bin/magento saas:resync --feed [feedName]
```

Gebruik de volgende opdrachtopties:

| Opdracht | Beschrijving |
|  ---  |  ---  |
| `bin/magento saas:resync --feed [feedName]` | Voert een herindexatie van de gespecificeerde voer uit en verzendt het naar de overeenkomstige dienst |
| `bin/magento saas:resync --no-reindex` | Hiermee slaat u de indexering over en verzendt u ongesynchroniseerde gegevens uit de indexen |

De `--feed` kunt u opgeven welke feed u wilt verzenden:

| Feed | Beschrijving |
|  ---  |  ---  |
| `paymentServicesOrdersProduction` | Voeding voor orders in productiemodus |
| `paymentServicesOrdersSandbox` | Voeding voor bestellingen in de modus Sandbox |
| `paymentServicesOrderStatusesProduction` | Statussen bestellen in productiemodus |
| `paymentServicesOrderStatusesSandbox` | Statussen ordenen in de modus Sandbox |
| `paymentServicesStoresProduction` | Winkels in productiemodus |
| `paymentServicesStoresSandbox` | Opgeslagen bestanden in de modus Sandbox |

Alle gegevens die nodig zijn voor de rapporten worden verzonden naar [!DNL Payment Services] automatisch als uitsnijden is geconfigureerd en geïnstalleerd. U kunt ook handmatig het verzenden van snijgegevens activeren naar [!DNL Payment Services].

```bash
bin/magento cron:run --group payment_services_data_export
```

Als u meer wilt weten over omvormen en indexeren, raadpleegt u de [De indexen beheren](https://devdocs.magento.com/guides/v2.4/config-guide/cli/config-cli-subcommands-index.html) onderwerp in de ontwikkelaarsdocumentatie.
