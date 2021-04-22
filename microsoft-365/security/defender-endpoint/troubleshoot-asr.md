---
title: Risolvere i problemi relativi alle regole di riduzione della superficie di attacco
description: Risorse e codice di esempio per la risoluzione dei problemi relativi alle regole di riduzione della superficie di attacco in Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, errore, correzione, windows defender ad esempio, asr, regole, hip, risoluzione dei problemi, controllo, esclusione, falso positivo, interrotto, blocco, Microsoft Defender per Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9ff00c706b0fb336c178e227b1cb33eff9e9ebbc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935222"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Risolvere i problemi relativi alle regole di riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Quando usi regole [di riduzione della superficie di](attack-surface-reduction.md) attacco potresti insoddirti in problemi, ad esempio:

- Una regola blocca un file, un processo o esegue un'altra azione che non dovrebbe essere eseguita (falso positivo)

- Una regola non funziona come descritto o non blocca un file o un processo che dovrebbe essere (falso negativo)

Per risolvere questi problemi, è necessario eseguire quattro passaggi:

1. [Verificare i prerequisiti](#confirm-prerequisites)

2. [Usare la modalità di controllo per testare la regola](#use-audit-mode-to-test-the-rule)

3. [Aggiungere esclusioni per la regola specificata](#add-exclusions-for-a-false-positive) (per falsi positivi)

4. [Inviare i log di supporto](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Verificare i prerequisiti

Le regole di riduzione della superficie di attacco funzionano solo nei dispositivi con le condizioni seguenti:

- Gli endpoint eseguono Windows 10 Enterprise versione 1709 (noto anche come Fall Creators Update).

- Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus. [L'uso di qualsiasi altra app antivirus causerà la disabilitazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)di Microsoft Defender AV.

- [La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) è abilitata.

- La modalità di controllo non è abilitata. Utilizzare Criteri di gruppo per impostare la regola su **Disabilitato** (valore: **0**) come descritto in Abilitare le regole di riduzione della superficie [di attacco.](enable-attack-surface-reduction.md)

Se tutti questi prerequisiti sono stati soddisfatti, andare al passaggio successivo per testare la regola in modalità di controllo.

## <a name="use-audit-mode-to-test-the-rule"></a>Usare la modalità di controllo per testare la regola

Puoi visitare il sito Web di base di Windows Defender Test all'indirizzo demo.wd.microsoft.com per verificare che le regole di riduzione della superficie di attacco funzionino [in](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) genere per scenari e processi preconfigurati in un dispositivo oppure puoi usare la modalità di controllo, che abilita le regole solo per la creazione di report.

Segui queste istruzioni in [Usare lo](evaluate-attack-surface-reduction.md) strumento demo per vedere come funzionano le regole di riduzione della superficie di attacco per testare la regola specifica con cui si verificano problemi.

1. Abilitare la modalità di controllo per la regola specifica che si desidera testare. Utilizzare Criteri di gruppo per impostare la regola sulla **modalità di** controllo (valore: **2**) come descritto in [Abilitare le regole di riduzione della superficie di attacco.](enable-attack-surface-reduction.md) La modalità di controllo consente alla regola di segnalare il file o il processo, ma ne consentirà comunque l'esecuzione.

2. Eseguire l'attività che causa un problema, ad esempio aprire o eseguire il file o il processo che deve essere bloccato ma che è consentito.

3. [Esaminare i registri eventi della](attack-surface-reduction.md) regola di riduzione della superficie di attacco per verificare se la regola avrebbe bloccato il file o il processo se la regola fosse stata impostata su **Enabled**.

Se una regola non blocca un file o un processo previsto che dovrebbe bloccarsi, controlla innanzitutto se la modalità di controllo è abilitata.

La modalità di controllo potrebbe essere stata abilitata per il test di un'altra funzionalità o da uno script di PowerShell automatizzato e potrebbe non essere stata disabilitata al termine dei test.

Se hai testato la regola con lo strumento demo e con la modalità di controllo e le regole di riduzione della superficie di attacco funzionano su scenari preconfigurati, ma la regola non funziona come previsto, passa a una delle sezioni seguenti in base alla situazione:

1. Se la regola di riduzione della superficie di attacco blocca qualcosa che non dovrebbe bloccare (noto anche come falso positivo), puoi innanzitutto aggiungere un'esclusione della regola di riduzione della superficie [di attacco.](#add-exclusions-for-a-false-positive)

2. Se la regola di riduzione della superficie di attacco non blocca un elemento che dovrebbe bloccare (noto anche come falso negativo), puoi procedere immediatamente all'ultimo passaggio, raccogliendo dati di diagnostica e inviando il problema a [Microsoft.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>Aggiungere esclusioni per un falso positivo

Se la regola di riduzione della superficie di attacco blocca qualcosa che non dovrebbe bloccare (noto anche come falso positivo), puoi aggiungere esclusioni per impedire alle regole di riduzione della superficie di attacco di valutare i file o le cartelle esclusi.

Per aggiungere un'esclusione, vedi [Personalizzare la riduzione della superficie di attacco.](customize-attack-surface-reduction.md)

>[!IMPORTANT]
>È possibile specificare singoli file e cartelle da escludere, ma non è possibile specificare singole regole.
>Ciò significa che tutti i file o le cartelle esclusi verranno esclusi da tutte le regole asr.

## <a name="report-a-false-positive-or-false-negative"></a>Segnalare un falso positivo o falso negativo

Utilizzare il Windows Defender di invio basato sul Web di [Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) per segnalare un falso negativo o un falso positivo per la protezione della rete. Con un abbonamento a Windows E5, puoi anche [fornire un collegamento a qualsiasi avviso associato.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>Raccogliere dati di diagnostica per gli invii di file

Quando si segnala un problema con le regole di riduzione della superficie di attacco, viene richiesto di raccogliere e inviare dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi.

1. Aprire un prompt dei comandi con privilegi elevati e passare alla directory Windows Defender:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Eseguire questo comando per generare i log di diagnostica:

   ```console
   mpcmdrun -getfiles
   ```

3. Per impostazione predefinita, vengono salvati in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . Allegare il file al modulo di invio.

## <a name="related-articles"></a>Articoli correlati

- [Regole per la riduzione della superficie di attacco](attack-surface-reduction.md)

- [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md)

- [Rilevare regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
