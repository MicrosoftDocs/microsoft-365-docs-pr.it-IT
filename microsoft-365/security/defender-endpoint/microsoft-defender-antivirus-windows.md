---
title: Antivirus Microsoft Defender
description: Informazioni su come gestire, configurare e usare Antivirus Microsoft Defender, protezione antimalware e antivirus integrata.
keywords: Antivirus Microsoft Defender, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, minaccia, rilevamento, protezione, sicurezza
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323054"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Microsoft Defender Antivirus in Windows

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender è il componente principale della protezione di ultima generazione di Microsoft Defender per endpoint. Questa protezione raggruppa l'apprendimento automatico, l'analisi dei Big Data, la ricerca approfondita sulla resistenza alle minacce e l'infrastruttura cloud Microsoft per proteggere i dispositivi (o gli endpoint) dell'organizzazione. Antivirus Microsoft Defender è integrato in Windows e compatibile con Microsoft Defender per endpoint per garantire al protezione sul dispositivo e nel cloud. 

## <a name="compatibility-with-other-antivirus-products"></a>Compatibilità con altri prodotti antivirus

Se si sta usando sul dispositivo un antivirus/prodotto antimalware non Microsoft, si potrebbe riuscire ad eseguire Antivirus Microsoft Defender in modalità passiva assieme alla soluzione antivirus non Microsoft. Ciò dipende dal sistema operativo usato e se per il dispositivo è stato eseguito l’onboarding su Defender per endpoint. Per altre informazioni, vedere [Compatibilità con Antivirus Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Confronto tra modalità attiva, modalità passiva e modalità di disattivazione

La tabella seguente descrive cosa aspettarsi quando Antivirus Microsoft Defender è in modalità attiva, modalità passiva o è disattivato.

| Modalità  | Effetto  |
|---------|---------|
| Modalità attiva | In modalità attiva, Antivirus Microsoft Defender è usato sul dispositivo come app antivirus primaria. I file sono analizzati, le minacce corrette e le minacce rilevate sono elencate nei report sulla sicurezza dell’organizzazione e nell’app di sicurezza di Windows. |
| Modalità passiva | In modalità passiva, Antivirus Microsoft Defender non è usato sul dispositivo come app antivirus primaria. I file sono analizzati e le minacce rilevate sono segnalate ma non corrette da Antivirus Microsoft Defender.   |
| Disattivato o disinstallato  | Se disattivato o disabilitato, Antivirus Microsoft Defender non è in uso. I file non sono analizzati e le minacce non sono corrette. In generale, non si consiglia di disabilitare o disinstallare Antivirus Microsoft Defender.  |

Per altre informazioni, vedere [Compatibilità con Antivirus Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Controllare lo stato di Antivirus Microsoft Defender sul dispositivo

Se si vuole controllare lo stato di Antivirus Microsoft Defender sul dispositivo, è possibile usare uno dei diversi metodi, ad esempio l’app di sicurezza di Windows o Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Usare l’app di sicurezza di Windows per controllare lo stato di Antivirus Microsoft Defender

1. Sul dispositivo Windows, selezionare il menu Start e iniziare a digitare `Security`. Quindi aprire l’app di sicurezza di Windows nei risultati.

2. Selezionare **Protezione da virus e minacce**.

3. In **Impostazioni di Protezione da virus e minacce** scegliere **Gestisci impostazioni**.

Si visualizzerà il nome della soluzione antivirus/antimalware sulla pagina delle impostazioni.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Usare PowerShell per controllare lo stato di Antivirus Microsoft Defender

1. Selezionare il menu Start e iniziare a digitare `PowerShell`. Quindi aprire Windows PowerShell nei risultati.

2. Tipo `Get-MpComputerStatus`.

3. Nell’elenco dei risultati, osservare la riga **AMRunningMode**.

   - **Normale** indica che Antivirus Microsoft Defender è in esecuzione in modalità attiva.
   - **Modalità passiva** indica che Antivirus Microsoft Defender è in esecuzione, ma che non è l’antivirus/prodotto antimalware primario sul dispositivo.
   - **EDR in modalità di blocco** indica che Antivirus Microsoft Defender è in esecuzione e che in Microsoft Defender per endpoint è abilitata una funzione chiamata "EDR in modalità di blocco". (Vedere [Rilevamento e reazione dagli endpoint (EDR) in modalità di blocco](edr-in-block-mode.md).)
   - **SxS in modalità passive Mode** indica che Antivirus Microsoft Defender è in esecuzione in modalità passiva assieme a un altro prodotto antivirus/antimalwaree che per il dispositivo non è stato eseguito l’onboarding su Microsoft Defender per endpoint. In questo caso, vengono usate le analisi periodiche limitate in Antivirus Microsoft Defender. Per ulteriori informazioni, vedere [Usare analisi periodiche limitate in Antivirus Microsoft Defender](limited-periodic-scanning-microsoft-defender-antivirus.md).

Per ulteriori informazioni sul cmdlet Get-MpComputerStatus PowerShell, consultare l’articolo di riferimento [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Ottenere gli aggiornamenti per la piattaforma antivirus/antimalware

È importante tenere aggiornato Antivirus Microsoft Defender, o qualsiasi soluzione antivirus/antimalware in uso. Microsoft rilascia aggiornamenti periodici per garantire che i dispositivi dispongano della tecnologia più recente per la protezione contro i nuovi malware e le tecniche di attacco più recenti. Per ulteriori informazioni, vedere [Gestire gli aggiornamenti in Antivirus Microsoft Defender e applicare i valori di riferimento](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Vedere anche

- [Microsoft Defender Antivirus su Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Gestione e configurazione di Antivirus Microsoft Defender](configuration-management-reference-microsoft-defender-antivirus.md)
- [Valutare la protezione di Antivirus Microsoft Defender](evaluate-microsoft-defender-antivirus.md)
