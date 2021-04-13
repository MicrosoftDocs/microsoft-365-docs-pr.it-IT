---
title: Eseguire e personalizzare le analisi su richiesta in Microsoft Defender AV
description: Eseguire e configurare analisi su richiesta tramite PowerShell, Strumentazione gestione Windows o singolarmente sugli endpoint con l'app Sicurezza di Windows
keywords: analisi, su richiesta, dos, intune, analisi istantanea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690542"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile eseguire un'analisi su richiesta su singoli endpoint. Queste analisi verranno avviate immediatamente ed è possibile definire i parametri per l'analisi, ad esempio la posizione o il tipo.

## <a name="quick-scan-versus-full-scan"></a>Analisi rapida e analisi completa

L'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio note di Windows.

> [!IMPORTANT]
> Microsoft Defender Antivirus viene eseguito nel contesto dell'account [LocalSystem](/windows/win32/services/localsystem-account) quando si esegue un'analisi locale. Per le analisi di rete, usa il contesto dell'account del dispositivo. Se l'account del dispositivo di dominio non dispone delle autorizzazioni appropriate per accedere alla condivisione, l'analisi non funzionerà. Assicurati che il dispositivo abbia le autorizzazioni per la condivisione di rete di accesso.

In [](configure-real-time-protection-microsoft-defender-antivirus.md)combinazione con la funzionalità di protezione sempre in tempo reale, che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.  

Nella maggior parte dei casi, un'analisi rapida è adeguata per individuare malware non raccolto dalla protezione in tempo reale.

Un'analisi completa può essere utile per gli endpoint che hanno segnalato una minaccia malware. L'analisi può identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita. Questo è l'ideale se l'organizzazione esegue analisi su richiesta.

> [!NOTE]
> Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Usare Microsoft Endpoint Manager per eseguire un'analisi

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.
2. Scegliere **Endpoint security**  >  **Antivirus**.
3. Nell'elenco delle schede seleziona **Endpoint non integri di Windows 10.**
4. Nell'elenco delle azioni fornite, selezionare **Analisi rapida** o **Analisi completa.**

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Per ulteriori informazioni sull'utilizzo di Microsoft Endpoint Manager per eseguire un'analisi, vedere [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Utilizzare l'mpcmdrun.exe da riga di comando per eseguire un'analisi

Utilizzare il parametro `-scan` seguente:

```console
mpcmdrun.exe -scan -scantype 1
```

Per ulteriori informazioni su come usare lo strumento e parametri aggiuntivi, tra cui l'avvio di un'analisi completa o la definizione di percorsi, vedere [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Usare Microsoft Intune per eseguire un'analisi

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.
2. Nella barra laterale seleziona Dispositivi > **Tutti i dispositivi** e scegli il dispositivo che vuoi analizzare.
3. Selezionare **... Altro**. Nelle opzioni selezionare **Analisi rapida o** Analisi **completa.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Usare l'app Sicurezza di Windows per eseguire un'analisi

Vedi [Eseguire un'analisi nell'app Sicurezza](microsoft-defender-security-center-antivirus.md) di Windows per istruzioni sull'esecuzione di un'analisi su singoli endpoint.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Utilizzare i cmdlet di PowerShell per eseguire un'analisi

Utilizzare il cmdlet seguente:

```PowerShell
Start-MpScan
```

Per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi

Utilizzare il [ **metodo Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) della **classe MSFT_MpScan.**

Per altre informazioni sui parametri consentiti, vedi Windows Defender [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Articoli correlati

- [Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurare le analisi pianificate di Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)