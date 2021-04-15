---
title: Microsoft Defender Offline in Windows 10
description: Puoi usare Microsoft Defender Offline direttamente dall'app Windows Defender Antivirus. È inoltre possibile gestire la modalità di distribuzione nella rete.
keywords: analisi, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765336"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Eseguire ed esaminare i risultati di un'analisi di Microsoft Defender Offline

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline è uno strumento di analisi antimalware che consente di avviare ed eseguire un'analisi da un ambiente attendibile. L'analisi viene eseguita dall'esterno del normale kernel di Windows in modo che possa essere mirata al malware che tenta di ignorare la shell di Windows, ad esempio virus e rootkit che infettano o sovrascrivono il record di avvio master (MBR).

Puoi usare Microsoft Defender Offline se sospetti un'infezione da malware o vuoi confermare una pulizia completa dell'endpoint dopo un'epidemia di malware.

In Windows 10, Microsoft Defender Offline può essere eseguito con un solo clic direttamente [dall'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md) Nelle versioni precedenti di Windows, un utente doveva installare Microsoft Defender Offline nei supporti di avvio, riavviare l'endpoint e caricare il supporto di avvio.

## <a name="prerequisites-and-requirements"></a>prerequisiti e requisiti

Microsoft Defender Offline in Windows 10 ha gli stessi requisiti hardware di Windows 10. 

Per altre informazioni sui requisiti di Windows 10, vedi gli argomenti seguenti:

- [Requisiti hardware minimi](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Linee guida per i componenti hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline non è supportato nei computer ARM processori o nelle unità di stock keeping di Windows Server.

Per eseguire Microsoft Defender Offline dall'endpoint, l'utente deve essere connesso con privilegi di amministratore.
 
## <a name="microsoft-defender-offline-updates"></a>Aggiornamenti di Microsoft Defender Offline

Microsoft Defender Offline usa gli aggiornamenti di protezione più recenti disponibili nell'endpoint. viene aggiornato ogni volta che Windows Defender antivirus viene aggiornato. 

> [!NOTE]
> Prima di eseguire un'analisi offline, è consigliabile tentare di aggiornare la protezione di Microsoft Defender AV. È possibile forzare un aggiornamento con Criteri di gruppo o, in genere, distribuire gli aggiornamenti agli endpoint oppure scaricare e installare manualmente gli aggiornamenti di protezione più recenti [da Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Per ulteriori informazioni, vedere l'argomento Manage [Microsoft Defender Antivirus Security intelligence updates.](manage-protection-updates-microsoft-defender-antivirus.md)

## <a name="usage-scenarios"></a>Scenari di utilizzo

In Windows 10, versione 1607, puoi forzare manualmente un'analisi offline. In alternativa, se Windows Defender che è necessario eseguire Microsoft Defender Offline, verrà richiesto all'utente nell'endpoint. 

La necessità di eseguire un'analisi offline verrà rivelata anche in Microsoft Endpoint Manager se viene utilizzata per gestire gli endpoint.

Il prompt può verificarsi tramite una notifica, simile alla seguente:

![Notifica di Windows che mostra il requisito per eseguire Microsoft Defender Offline](images/defender/notification.png)

L'utente riceverà anche una notifica all'interno del client Windows Defender client.

In Configuration Manager è possibile identificare lo stato degli endpoint accedendo a Monitoraggio > Panoramica > Sicurezza > Stato di Endpoint Protection > **Stato di System Center Endpoint Protection.** 

Le analisi di Microsoft Defender Offline sono indicate in Stato correzione **malware** come **Analisi offline necessaria.**

![Microsoft Endpoint Manager che indica che è necessaria un'analisi offline di Microsoft Defender](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurare le notifiche

Le notifiche di Microsoft Defender Offline sono configurate nella stessa impostazione dei criteri di altre notifiche di Microsoft Defender AV.

Per altre informazioni sulle notifiche in Windows Defender, vedi [l'argomento Configurare le notifiche visualizzate negli endpoint.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Eseguire un'analisi 

> [!IMPORTANT]
> Prima di usare Microsoft Defender Offline, assicurati di salvare i file e arrestare i programmi in esecuzione. L'esecuzione dell'analisi di Microsoft Defender Offline richiede circa 15 minuti. L'endpoint verrà riavviato al termine dell'analisi. L'analisi viene eseguita al di fuori dell'ambiente operativo Windows consueto. L'interfaccia utente sarà diversa da una normale analisi eseguita da Windows Defender. Al termine dell'analisi, l'endpoint verrà riavviato e Windows verrà caricato normalmente.

Puoi eseguire un'analisi di Microsoft Defender Offline con quanto segue:

- PowerShell
- Strumentazione gestione Windows (WMI)
- App Sicurezza di Windows



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Utilizzare i cmdlet di PowerShell per eseguire un'analisi offline

Utilizzare i cmdlet seguenti:

```PowerShell
Start-MpWDOScan
```

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi offline

Utilizzare la [**classe MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per eseguire un'analisi offline.

Il frammento di script WMI seguente eseguirà immediatamente un'analisi di Microsoft Defender Offline, che causerà il riavvio dell'endpoint, l'esecuzione dell'analisi offline e quindi il riavvio e l'avvio in Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Per ulteriori informazioni, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usare l'app Windows Defender Security per eseguire un'analisi offline

1. Apri l'app Sicurezza di Windows facendo clic sull'icona scudo nella barra delle applicazioni o cercando **Defender** nel menu Start.

2. Fai clic **sul riquadro Protezione da &** virus (o sull'icona scudo sulla barra dei menu sinistra) e quindi sull'etichetta **Analisi** avanzata:
    
3. Seleziona **Analisi offline di Microsoft Defender** e fai clic su Analizza **ora.**

    > [!NOTE]
    > In Windows 10, versione 1607, l'analisi offline può essere eseguita da in **Windows Settings** Update & security Windows Defender o dal  >    >   client Windows Defender.


## <a name="review-scan-results"></a>Esaminare i risultati dell'analisi

I risultati dell'analisi di Microsoft Defender Offline verranno elencati nella sezione [Cronologia analisi dell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Articoli correlati

- [Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)