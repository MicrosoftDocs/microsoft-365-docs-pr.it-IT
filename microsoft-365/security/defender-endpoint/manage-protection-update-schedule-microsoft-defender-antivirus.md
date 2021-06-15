---
title: Pianificare Antivirus Microsoft Defender aggiornamenti della protezione
description: Pianificare il giorno, l'ora e l'intervallo per il download degli aggiornamenti della protezione
keywords: aggiornamenti, linee di base della sicurezza, pianificare gli aggiornamenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: abb656586d6a7bd779b109fcad3c777016fef980
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926056"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Gestire la pianificazione del momento in cui devono essere scaricati e applicati gli aggiornamenti della protezione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender consente di determinare quando cercare e scaricare gli aggiornamenti.

Puoi pianificare gli aggiornamenti per gli endpoint: 

- Specifica del giorno della settimana per la verifica della disponibilità di aggiornamenti della protezione 
- Specifica dell'intervallo per la verifica della disponibilità di aggiornamenti della protezione
- Specifica del tempo necessario per verificare la disponibilità di aggiornamenti della protezione

È inoltre possibile impostare in modo casuale i tempi in cui ogni endpoint controlla e scarica gli aggiornamenti della protezione. Per ulteriori [informazioni, vedere l'argomento](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Pianifica analisi.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Utilizzare Configuration Manager per pianificare gli aggiornamenti della protezione

1.  Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)

2.  Passare alla sezione **Aggiornamenti di Intelligence per la sicurezza.**

3. Per controllare e scaricare gli aggiornamenti in un determinato momento:
      1. Impostare Verifica disponibilità Endpoint Protection aggiornamenti delle funzionalità di intelligence per la **sicurezza a un intervallo specifico...** su **0**.
      2. Imposta **Verifica disponibilità Endpoint Protection aggiornamenti delle funzionalità di intelligence** per la sicurezza ogni giorno all'ora in cui devono essere controllati gli aggiornamenti.
      3
4. Per controllare e scaricare gli aggiornamenti a intervalli continui, impostare Verifica disponibilità aggiornamenti di intelligence per la sicurezza Endpoint Protection un intervallo **specifico...** sul numero di ore che devono verificarsi tra gli aggiornamenti.

5.  [Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="use-group-policy-to-schedule-protection-updates"></a>Utilizzare Criteri di gruppo per pianificare gli aggiornamenti della protezione

> [!IMPORTANT]
> Per impostazione predefinita, Antivirus Microsoft Defender un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata. L'abilitazione di queste impostazioni avrà la precedenza su quella predefinita.

1.  Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

5.  Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Signature Intelligence** e configurare le impostazioni seguenti:

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

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

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

- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)