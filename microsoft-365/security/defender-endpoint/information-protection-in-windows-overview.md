---
title: Panoramica di protezione delle informazioni in Windows
ms.reviewer: ''
description: Informazioni sul funzionamento della protezione delle informazioni in Windows per identificare e proteggere le informazioni riservate
keywords: informazioni, protezione, dlp, dati, perdita, prevenzione, protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 803c0af0c495eedfd26023d4e71d98df6a1b1b64
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904023"
---
# <a name="information-protection-in-windows-overview"></a>Panoramica di protezione delle informazioni in Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

La protezione delle informazioni è parte integrante della famiglia di prodotti Microsoft 365 Enterprise, offrendo una protezione intelligente per proteggere i dati sensibili, consentendo al contempo la produttività sul luogo di lavoro.


>[!TIP]
> Leggi il post di blog su come Microsoft Defender for Endpoint (in precedenza noto come Microsoft Defender ATP) si integra con Microsoft Information Protection per individuare, proteggere e monitorare i dati sensibili nei [dispositivi Windows.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)

Defender for Endpoint applica i metodi seguenti per individuare, classificare e proteggere i dati:

- **Individuazione dei dati** - Identificare i dati sensibili nei dispositivi Windows a rischio
- **Classificazione dei** dati: classifica automaticamente i dati in base ai criteri comuni di Microsoft Information Protection (MIP) gestiti nel Centro sicurezza e conformità & di Office 365. La classificazione automatica consente di proteggere i dati sensibili anche se l'utente finale non lo ha classificato manualmente.


## <a name="data-discovery-and-data-classification"></a>Individuazione e classificazione dei dati

Defender for Endpoint individua automaticamente i file con etichette di riservatezza e i file che contengono tipi di informazioni riservate.

Le etichette di riservatezza classificano e proteggono i contenuti sensibili.

I tipi di informazioni riservate nell'implementazione della prevenzione della perdita dei dati (DLP) di Office 365 rientrano in due categorie:

- Impostazione predefinita
- Personalizzato

I tipi di informazioni riservate predefiniti includono informazioni quali numeri di conto corrente bancario, numeri di previdenza sociale o ID nazionali. Per ulteriori informazioni, vedere [Ricerca del tipo di informazioni riservate](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).

I tipi personalizzati sono definiti dall'utente ed è progettato per proteggere un tipo diverso di informazioni riservate, ad esempio ID dipendenti o numeri di progetto. Per ulteriori informazioni, vedere [Creare un tipo di informazioni riservate personalizzato.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)

Quando un file viene creato o modificato in un dispositivo Windows, Defender for Endpoint analizza il contenuto per valutare se contiene informazioni riservate.

Attivare l'integrazione di Azure Information Protection in modo che quando un file che contiene informazioni riservate viene individuato da Defender per Endpoint anche se etichette o tipi di informazioni, viene automaticamente inoltrato ad Azure Information Protection dal dispositivo.

![Immagine della pagina delle impostazioni con Azure Information Protection](images/atp-settings-aip.png)

I segnali segnalati possono essere visualizzati nel dashboard azure Information Protection - Individuazione dati.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection - Dashboard di individuazione dei dati

Questo dashboard presenta un riepilogo delle informazioni di individuazione dei dati individuati da Defender per Endpoint e Azure Information Protection. I dati di Defender per Endpoint sono contrassegnati con Location Type - Endpoint.

![Immagine di Azure Information Protection - Individuazione dati](images/azure-data-discovery.png)

Nota la colonna Rischio dispositivo a destra, questo rischio del dispositivo deriva direttamente da Defender per Endpoint, che indica il livello di rischio del dispositivo di sicurezza in cui è stato individuato il file, in base alle minacce alla sicurezza attive rilevate da Defender per Endpoint.

Fai clic su un dispositivo per visualizzare un elenco dei file osservati su questo dispositivo, con le etichette di riservatezza e i tipi di informazioni.

>[!NOTE]
>Attendere circa 15-20 minuti perché l'individuazione del dashboard di Azure Information Protection rifletta i file individuati.

## <a name="log-analytics"></a>Log Analytics

L'individuazione dei dati basata su Defender per Endpoint è disponibile anche in [Azure Log Analytics,](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)in cui è possibile eseguire query complesse sui dati non elaborati.

Per ulteriori informazioni sull'analisi di Azure Information Protection, vedere [Creazione di report centrali per Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/reports-aip)

Aprire Azure Log Analytics nel portale di Azure e aprire un generatore di query (standard o classico).

Per visualizzare i dati di Defender for Endpoint, eseguire una query contenente:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Prerequisiti:**

- I clienti devono avere una sottoscrizione per Azure Information Protection.
- Abilitare l'integrazione di Azure Information Protection in Microsoft Defender Security Center:
    - Vai a **Impostazioni** in Microsoft Defender Security Center, fai clic su **Impostazioni avanzate** in **Generale.**



