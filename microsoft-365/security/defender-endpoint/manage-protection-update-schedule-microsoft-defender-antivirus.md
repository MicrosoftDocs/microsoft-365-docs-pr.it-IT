---
title: Pianificare gli aggiornamenti di protezione di Microsoft Defender Antivirus
description: Pianificare il giorno, l'ora e l'intervallo per il download degli aggiornamenti della protezione
keywords: aggiornamenti, linee di base della sicurezza, pianificare gli aggiornamenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690423"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Gestire la pianificazione per il download e l'applicazione degli aggiornamenti di protezione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus ti consente di determinare quando cercare e scaricare gli aggiornamenti.

Puoi pianificare gli aggiornamenti per gli endpoint: 

- Specifica del giorno della settimana per la verifica della disponibilità di aggiornamenti della protezione 
- Specifica dell'intervallo per la verifica della disponibilità di aggiornamenti della protezione
- Specifica del tempo necessario per verificare la disponibilità di aggiornamenti della protezione

È inoltre possibile impostare in modo casuale i tempi in cui ogni endpoint controlla e scarica gli aggiornamenti della protezione. Per ulteriori [informazioni, vedere l'argomento](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Pianifica analisi.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Utilizzare Configuration Manager per pianificare gli aggiornamenti della protezione

1.  Nella console di Microsoft Endpoint Manager apri i criteri antimalware che vuoi modificare (fai clic su Asset  **e** conformità nel riquadro di spostamento a sinistra, quindi espandi l'albero fino a Panoramica criteri  >    >  **antimalware** di Endpoint Protection)

2.  Passare alla sezione **Aggiornamenti di Intelligence per la sicurezza.**

3. Per controllare e scaricare gli aggiornamenti in un determinato momento:
      1. Impostare **Controlla aggiornamenti dell'intelligence di sicurezza** di Endpoint Protection a un intervallo specifico... su **0**.
      2. Imposta Controlla aggiornamenti di Intelligence per la sicurezza di Endpoint Protection ogni giorno **in...** al momento in cui devono essere controllati gli aggiornamenti.
      3
4. Per controllare e scaricare gli aggiornamenti a intervalli continui, impostare Controlla aggiornamenti di Intelligence per la sicurezza di Endpoint Protection a un intervallo **specifico...** sul numero di ore che devono verificarsi tra gli aggiornamenti.

5.  [Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Utilizzare Criteri di gruppo per pianificare gli aggiornamenti della protezione

> [!IMPORTANT]
> Per impostazione predefinita, Microsoft Defender Antivirus verifica la disponibilità di un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata. L'abilitazione di queste impostazioni avrà la precedenza su quella predefinita.

1.  Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

5.  Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Signature  >  **Intelligence Updates** e configurare le impostazioni seguenti:

    1. Fare doppio clic **sull'impostazione Specifica il giorno della** settimana per verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.** Immettere il giorno della settimana per verificare la disponibilità di aggiornamenti. Fare clic su **OK**.
    2. Fare doppio clic **sull'impostazione Specifica l'intervallo per controllare la** disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.** Immettere il numero di ore tra gli aggiornamenti. Fare clic su **OK**.
    3. Fare doppio clic **sull'impostazione Specifica il tempo di** verifica della disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.** Immettere l'ora in cui controllare gli aggiornamenti. L'ora è basata sull'ora locale dell'endpoint. Fare clic su **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Utilizzare i cmdlet di PowerShell per pianificare gli aggiornamenti di protezione

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Utilizzare Windows Management Instruction (WMI) per pianificare gli aggiornamenti della protezione

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Articoli correlati

- [Distribuire Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)