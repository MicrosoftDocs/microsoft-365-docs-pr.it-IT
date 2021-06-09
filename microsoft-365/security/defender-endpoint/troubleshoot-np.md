---
title: Risolvere i problemi relativi a Protezione di rete
description: Risorse e codice di esempio per la risoluzione dei problemi relativi a Protezione di rete in Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, errore, correzione, windows defender ad esempio, asr, regole, hip, risoluzione dei problemi, controllo, esclusione, falso positivo, interrotto, blocco, Microsoft Defender per Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844059"
---
# <a name="troubleshoot-network-protection"></a>Risolvere i problemi di protezione di rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
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
> - Gli endpoint eseguono Windows 10 Pro o Enterprise edition, versione 1709 o successiva.
> - Gli endpoint usano il Antivirus Microsoft Defender come unica app di protezione antivirus. [Vedere cosa succede quando si utilizza una soluzione antivirus non Microsoft.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [La protezione in tempo reale](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) è abilitata.
> - [La protezione consegnata dal cloud](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) è abilitata.
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

3. Allegare il file al modulo di invio. Per impostazione predefinita, i log di diagnostica vengono salvati in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Risolvere i problemi di connettività con la protezione di rete (per i clienti E5)

A causa dell'ambiente in cui viene eseguita la protezione di rete, Microsoft non è in grado di visualizzare le impostazioni proxy del sistema operativo. In alcuni casi, i client di protezione di rete non sono in grado di raggiungere il servizio cloud. Per risolvere i problemi di connettività con la protezione di rete, configurare una delle seguenti chiavi del Registro di sistema in modo che la protezione di rete sia a conoscenza della configurazione del proxy:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

È possibile configurare la chiave del Registro di sistema utilizzando PowerShell, Microsoft Endpoint Manager o Criteri di gruppo. Ecco alcune risorse utili:
- [Utilizzo delle chiavi del Registro di sistema](/powershell/scripting/samples/working-with-registry-keys)
- [Configurare le impostazioni client personalizzate per Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Usare le impostazioni di Criteri di gruppo per gestire Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Vedere anche

- [Protezione di rete](network-protection.md)
- [Valutare la protezione di rete](evaluate-network-protection.md)
- [Abilitare la protezione di rete](enable-network-protection.md)
- [Risolvere i falsi positivi/negativi in Defender for Endpoint](defender-endpoint-false-positives-negatives.md)
