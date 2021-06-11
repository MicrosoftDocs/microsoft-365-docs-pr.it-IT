---
title: Eseguire e personalizzare le analisi su richiesta in Antivirus Microsoft Defender
description: Eseguire e configurare analisi su richiesta tramite PowerShell, Windows Management Instrumentation o singolarmente sugli endpoint con l'app Sicurezza di Windows
keywords: analisi, su richiesta, dos, intune, analisi istantanea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878809"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile eseguire un'analisi su richiesta su singoli endpoint. Queste analisi verranno avviate immediatamente ed è possibile definire i parametri per l'analisi, ad esempio la posizione o il tipo. Quando si esegue un'analisi, è possibile scegliere tra tre tipi: analisi rapida, analisi completa e analisi personalizzata. Nella maggior parte dei casi, utilizzare un'analisi rapida. Un'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note. 

In combinazione con la protezione sempre in tempo reale, che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una protezione avanzata dal malware che inizia con il malware a livello di sistema e kernel. Nella maggior parte dei casi, un'analisi rapida è sufficiente ed è l'opzione consigliata per le analisi pianificate o su richiesta.  [Ulteriori informazioni sui tipi di analisi](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).

> [!IMPORTANT]
> Antivirus Microsoft Defender viene eseguito nel contesto dell'account [LocalSystem](/windows/win32/services/localsystem-account) quando si esegue un'analisi locale. Per le analisi di rete, usa il contesto dell'account del dispositivo. Se l'account del dispositivo di dominio non dispone delle autorizzazioni appropriate per accedere alla condivisione, l'analisi non funzionerà. Assicurati che il dispositivo abbia le autorizzazioni per la condivisione di rete di accesso.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Utilizzare Microsoft Endpoint Manager per eseguire un'analisi

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.

2. Scegliere **Endpoint security**  >  **Antivirus**.

3. Nell'elenco di schede selezionare **Windows 10 endpoint non integri.**

4. Nell'elenco delle azioni fornite, selezionare **Analisi rapida** (scelta consigliata) o **Analisi completa.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Per ulteriori informazioni sull'Microsoft Endpoint Manager per eseguire un'analisi, vedere [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Utilizzare l'mpcmdrun.exe da riga di comando per eseguire un'analisi

Utilizzare il parametro `-scan` seguente:

```console
mpcmdrun.exe -scan -scantype 1
```

Per ulteriori informazioni su come utilizzare lo strumento e parametri aggiuntivi, tra cui l'avvio di un'analisi completa o la definizione di percorsi, vedere [Use the mpcmdrun.exe commandline tool to configure and manage Antivirus Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).

## <a name="use-microsoft-intune-to-run-a-scan"></a>Utilizzare Microsoft Intune per eseguire un'analisi

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.

2. Nella barra laterale seleziona **Dispositivi**  >  **tutti i dispositivi** e scegli il dispositivo che vuoi analizzare.

3. Selezionare **... Altro**. Nelle opzioni selezionare **Analisi rapida** (scelta consigliata) o Analisi **completa.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Usare l'app Sicurezza di Windows per eseguire un'analisi

Vedi [Eseguire un'analisi nell'app Sicurezza di Windows per](microsoft-defender-security-center-antivirus.md) istruzioni sull'esecuzione di un'analisi su singoli endpoint.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Utilizzare i cmdlet di PowerShell per eseguire un'analisi

Utilizzare il cmdlet seguente:

```PowerShell
Start-MpScan
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi

Utilizzare il [ **metodo Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) della **classe MSFT_MpScan.**

Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

