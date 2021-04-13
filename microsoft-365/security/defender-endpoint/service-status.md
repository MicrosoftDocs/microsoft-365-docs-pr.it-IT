---
title: Controllare l'integrità del servizio endpoint in Microsoft Defender
description: Controlla Microsoft Defender per l'integrità del servizio endpoint, verifica se si verificano problemi nel servizio ed esamina i problemi precedenti che sono stati risolti.
keywords: dashboard, servizio, problemi, integrità del servizio, stato corrente, cronologia dello stato, riepilogo dell'impatto, causa radice preliminare, risoluzione, tempo di risoluzione, tempo di risoluzione previsto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687626"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a>Controllare l'integrità del servizio endpoint in Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)



>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

**L'integrità** del servizio fornisce informazioni sullo stato corrente del servizio Defender for Endpoint. Sarà possibile verificare che l'integrità del servizio sia integra o se sono presenti problemi correnti. In caso di problemi, verranno visualizzate informazioni quali il momento in cui è stato rilevato il problema, la causa principale preliminare e il tempo di risoluzione previsto.

Verranno inoltre visualizzate informazioni sui problemi cronologici risolti e dettagli quali la data e l'ora in cui il problema è stato risolto. Quando non si verificano problemi nel servizio, verrà visualizzato uno stato integro.

È possibile visualizzare i dettagli sull'integrità del servizio facendo clic sul riquadro nel **dashboard** Operazioni di sicurezza o selezionando il menu **Integrità servizio** nel riquadro di spostamento.

Nella **pagina Dettagli integrità** servizio sono disponibili le schede seguenti:

- **Stato corrente**
- **Cronologia stato**

## <a name="current-status"></a>Stato corrente
La **scheda Stato** corrente mostra lo stato corrente del servizio Defender per endpoint. Quando il servizio viene eseguito senza problemi, viene visualizzata un'integrità del servizio integra. In caso di problemi, vengono mostrati i dettagli del servizio seguenti per ottenere informazioni più approfondite sul problema:

- Data e ora in cui è stato rilevato il problema
- Breve descrizione del problema
- Ora aggiornamento
- Riepilogo dell'impatto
- Causa radice preliminare
- Passaggi successivi
- Tempo di risoluzione previsto

Gli aggiornamenti sullo stato di avanzamento di un problema vengono visualizzati nella pagina quando il problema viene risolto. Verranno visualizzati aggiornamenti sulle informazioni, ad esempio il tempo di risoluzione della stima aggiornato o i passaggi successivi.

Quando un problema viene risolto, viene registrato nella **scheda Cronologia** stato.

## <a name="status-history"></a>Cronologia stato
La **scheda Cronologia** stato riflette tutti i problemi cronologici che sono stati visti e risolti. Verranno visualizzati i dettagli dei problemi risolti insieme alle altre informazioni incluse durante la risoluzione.

### <a name="related-topic"></a>Argomento correlato
- [Visualizzare il dashboard delle operazioni di sicurezza](security-operations-dashboard.md)
