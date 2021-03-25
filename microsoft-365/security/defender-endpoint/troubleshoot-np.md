---
title: Risolvere i problemi relativi a Protezione di rete
description: Risorse e codice di esempio per la risoluzione dei problemi relativi a Protezione di rete in Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, errore, correzione, windows defender ad esempio, asr, regole, hips, risoluzione dei problemi, controllo, esclusione, falso positivo, interrotto, blocco, microsoft defender per endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 165c17bc820403ebfbbe5cdfe3ca856e8416c593
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066042"
---
# <a name="troubleshoot-network-protection"></a>Risolvere i problemi di protezione di rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Quando si utilizza [Protezione di rete,](network-protection.md) è possibile che si verifichino problemi, ad esempio:

- Protezione di rete blocca un sito Web sicuro (falso positivo)
- La protezione di rete non riesce a bloccare un sito Web dannoso sospetto o noto (falso negativo)

Per risolvere questi problemi, è necessario eseguire quattro passaggi:

1. Verificare i prerequisiti
2. Usare la modalità di controllo per testare la regola
3. Aggiungere esclusioni per la regola specificata (per falsi positivi)
4. Inviare i log di supporto

## <a name="confirm-prerequisites"></a>Verificare i prerequisiti

La protezione di rete funzionerà solo nei dispositivi con le condizioni seguenti:

>[!div class="checklist"]
> - Gli endpoint eseguono Windows 10 Pro o Enterprise Edition, versione 1709 o successiva.
> - Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus. [Vedere cosa succede quando si utilizza una soluzione antivirus non Microsoft.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) è abilitata.
> - [La protezione consegnata dal cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) è abilitata.
> - La modalità di controllo non è abilitata. Utilizzare [Criteri di gruppo](enable-network-protection.md#group-policy) per impostare la regola su **Disabilitato** (valore: **0**).

## <a name="use-audit-mode"></a>Usare la modalità di controllo

È possibile abilitare la protezione di rete in modalità di controllo e quindi visitare un sito Web creato per la dimostrazione della funzionalità. Tutte le connessioni al sito Web saranno consentite dalla protezione di rete, ma verrà registrato un evento per indicare qualsiasi connessione che sarebbe stata bloccata se la protezione di rete fosse stata abilitata.

1. Impostare protezione di rete su **Modalità di controllo**.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Eseguire l'attività di connessione che causa un problema( ad esempio, tentare di visitare il sito o connettersi all'indirizzo IP che si esegue o non si desidera bloccare).

3. [Esaminare i registri eventi di protezione](network-protection.md#review-network-protection-events-in-windows-event-viewer) di rete per verificare se la funzionalità avrebbe bloccato la connessione se fosse stata impostata su **Abilitato**.
   
   Se la protezione di rete non blocca una connessione che si prevede che dovrebbe bloccare, abilitare la funzionalità.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Segnalare un falso positivo o falso negativo

Se la funzionalità è stata testata con il sito demo e con la modalità di controllo e la protezione di rete funziona su scenari preconfigurati, ma non funziona come previsto per una connessione specifica, utilizzare il modulo di invio basato sul Web di [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) per segnalare un falso negativo o un falso positivo per la protezione di rete. Con una sottoscrizione E5 puoi anche [fornire un collegamento a qualsiasi avviso associato.](alerts-queue.md)

Vedi [Indirizzo falsi positivi/negativi in Microsoft Defender per Endpoint.](defender-endpoint-false-positives-negatives.md)

## <a name="exclude-website-from-network-protection-scope"></a>Escludere il sito Web dall'ambito di protezione di rete

Per consentire il sito Web bloccato (falso positivo), aggiungere il relativo URL [all'elenco dei siti attendibili.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/) Le risorse Web di questo elenco ignorano il controllo della protezione di rete.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Raccogliere dati di diagnostica per gli invii di file

Quando si segnala un problema con la protezione di rete, viene richiesto di raccogliere e inviare dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi.

1. Aprire un prompt dei comandi con privilegi elevati e passare alla directory Windows Defender:

   ```console
   cd c:\program files\windows defender
   ```

2. Eseguire questo comando per generare i log di diagnostica:

   ```console
   mpcmdrun -getfiles
   ```

3. Per impostazione predefinita, vengono salvati in C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab. Allegare il file al modulo di invio.

## <a name="related-topics"></a>Argomenti correlati

- [Protezione di rete](network-protection.md)
- [Valutare la protezione di rete](evaluate-network-protection.md)
- [Abilitare la protezione di rete](enable-network-protection.md)
- [Risolvere i falsi positivi/negativi in Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
