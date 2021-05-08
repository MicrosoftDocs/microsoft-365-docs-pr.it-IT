---
title: Applicare Antivirus Microsoft Defender aggiornamenti dopo determinati eventi
description: Gestire il modo Antivirus Microsoft Defender gli aggiornamenti delle funzionalità di intelligence per la sicurezza dopo l'avvio o la ricezione di report di rilevamento recapitati nel cloud.
keywords: aggiornamenti, protezione, forzare gli aggiornamenti, eventi, avvio, controllare la presenza di più recenti, notifiche
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274701"
---
# <a name="manage-event-based-forced-updates"></a>Gestire gli aggiornamenti forzati basati su eventi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender consente di determinare se gli aggiornamenti devono verificarsi (o meno) dopo determinati eventi, ad esempio all'avvio o dopo la ricezione di report specifici dal servizio di protezione fornito dal cloud.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi

È possibile utilizzare Microsoft Endpoint Configuration Manager, Criteri di gruppo, cmdlet di PowerShell e WMI per forzare Antivirus Microsoft Defender controllare e scaricare gli aggiornamenti di protezione prima di eseguire un'analisi pianificata.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Usare Configuration Manager per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi

1. Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)

2. Vai alla sezione **Analisi pianificate** e imposta Verifica la disponibilità degli ultimi aggiornamenti delle funzionalità di intelligence per la sicurezza **prima di eseguire un'analisi** su **Sì.**

3. Fare clic su **OK**.

4. [Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Utilizzare Criteri di gruppo per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **scan**.

5. Fare doppio clic **su Controlla le definizioni più** recenti di virus e spyware prima di eseguire un'analisi pianificata e impostare l'opzione su **Abilitato**.

6. Fare clic su **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Utilizzare i cmdlet di PowerShell per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Utilizzare Windows Management Instruction (WMI) per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
CheckForSignaturesBeforeRunningScan
```

Per altre informazioni, [vedi Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Verificare la disponibilità di aggiornamenti della protezione all'avvio

È possibile utilizzare Criteri di gruppo per forzare Antivirus Microsoft Defender controllare e scaricare gli aggiornamenti di protezione all'avvio del computer.

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence**.

5. Fare doppio clic **su Controlla le definizioni più** recenti di virus e spyware all'avvio e impostare l'opzione su **Abilitato**. 

6. Fare clic su **OK**.

È inoltre possibile utilizzare Criteri di gruppo, PowerShell o WMI per configurare Antivirus Microsoft Defender per verificare la disponibilità di aggiornamenti all'avvio anche quando non è in esecuzione.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usare Criteri di gruppo per scaricare gli aggiornamenti Antivirus Microsoft Defender non è presente

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo,** passare a **Configurazione computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence**.

5. Fare doppio clic su **Avvia aggiornamento intelligence per la sicurezza all'avvio** e impostare l'opzione su **Abilitato**.

6. Fare clic su **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usare i cmdlet di PowerShell per scaricare gli aggiornamenti Antivirus Microsoft Defender non è presente

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to manage Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Antivirus Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Utilizzare Windows Management Instruction (WMI) per scaricare gli aggiornamenti quando Antivirus Microsoft Defender non è presente

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Per altre informazioni, [vedi Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Consentire modifiche ad hoc alla protezione basata sulla protezione basata sul cloud

Microsoft Defender AV può apportare modifiche alla protezione in base alla protezione basata sul cloud. Tali modifiche possono verificarsi al di fuori degli aggiornamenti di protezione normali o pianificati.

Se è stata abilitata la protezione con distribuzione cloud, Microsoft Defender AV invierà file sospetti al cloud Windows Defender cloud. Se il servizio cloud segnala che il file è dannoso e il file viene rilevato in un aggiornamento di protezione recente, è possibile utilizzare Criteri di gruppo per configurare Microsoft Defender AV per ricevere automaticamente tale aggiornamento di protezione. È inoltre possibile applicare altri importanti aggiornamenti della protezione.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Usare Criteri di gruppo per scaricare automaticamente gli aggiornamenti recenti in base alla protezione consegnata dal cloud

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence**.

5. Fare doppio clic **su Consenti aggiornamenti delle** funzionalità di intelligence per la sicurezza in tempo reale in base ai report di Microsoft MAPS e impostare l'opzione su **Abilitato**. Fare clic su **OK**.

6. **Consenti alle notifiche di disabilitare i report basati sulle definizioni in Microsoft MAPS** e imposta l'opzione su **Abilitato.** Fare clic su **OK**.
    
> [!NOTE]
> **Consenti notifiche per disabilitare i report basati sulle** definizioni consente a Microsoft MAPS di disabilitare tali definizioni note per causare report falsi positivi. È necessario configurare il computer per l'aggiunta a Microsoft MAPS per il funzionamento di questa funzione.

## <a name="see-also"></a>Vedere anche

- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)