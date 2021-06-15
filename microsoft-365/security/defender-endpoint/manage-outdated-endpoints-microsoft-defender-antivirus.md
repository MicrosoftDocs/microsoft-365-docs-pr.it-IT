---
title: Applicare gli aggiornamenti della protezione di Microsoft Defender AV agli endpoint non aggiornati
description: Definire quando e come applicare gli aggiornamenti per gli endpoint che non sono stati aggiornati da un po'.
keywords: aggiornamenti, protezione, non aggiornato, obsoleto, vecchio, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b141c9b745e560b3c2236a9d073a7b2f3500623c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926044"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Gestire gli aggiornamenti e le analisi di Microsoft Defender Antivirus per gli endpoint non aggiornati

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender consente di definire per quanto tempo un endpoint può evitare un aggiornamento o il numero di analisi che può mancare prima di essere necessario per l'aggiornamento e l'analisi. Ciò è particolarmente utile in ambienti in cui i dispositivi non sono spesso connessi a una rete aziendale o esterna o in dispositivi che non vengono utilizzati quotidianamente.

Ad esempio, un dipendente che usa un PC specifico è in pausa per tre giorni e non accede al PC durante tale periodo.

Quando l'utente torna a lavorare e accede al PC, Antivirus Microsoft Defender controlla immediatamente e scarica gli aggiornamenti di protezione più recenti ed esegue un'analisi.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Configurare gli aggiornamenti di protezione da recuperare per gli endpoint che non sono stati aggiornati per un po' di tempo

Se Antivirus Microsoft Defender non ha scaricato gli aggiornamenti di protezione per un periodo specificato, è possibile configurarlo per controllare e scaricare automaticamente l'aggiornamento più recente all'accesso successivo. Ciò è utile se all'avvio sono stati disabilitati a livello globale i [download degli aggiornamenti automatici.](manage-event-based-updates-microsoft-defender-antivirus.md)

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Usare Configuration Manager per configurare gli aggiornamenti di protezione di blocco

1.  Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)

2.  Passare alla sezione **Aggiornamenti di Intelligence per la** sicurezza e configurare le impostazioni seguenti:

    1. Impostare Forza un aggiornamento della sicurezza intelligence se il computer client è offline per più di **due aggiornamenti pianificati consecutivi** su **Sì.**
    2. Per se Configuration Manager viene utilizzato come origine per gli aggiornamenti delle funzionalità di intelligence per la  **sicurezza...**, specificare le ore prima delle quali gli aggiornamenti di protezione recapitati da Configuration Manager devono essere considerati non aggiornati. In questo modo verrà utilizzato il percorso di aggiornamento successivo, in base all'ordine di [origine di fallback definito.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Fare clic su **OK**.

4.  [Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Usare Criteri di gruppo per abilitare e configurare la funzionalità di aggiornamento di blocco

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > aggiornamenti delle firme**.

5. Fare doppio clic sull'impostazione Definisci il numero di giorni dopo il quale è necessario un aggiornamento **di intelligence** per la sicurezza e impostare l'opzione su **Abilitato**. Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV controlli e scarii il più recente aggiornamento della protezione.

6. Fare clic su **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Utilizzare i cmdlet di PowerShell per configurare gli aggiornamenti di protezione da recuperare

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Utilizzare Windows Management Instruction (WMI) per configurare gli aggiornamenti di protezione di aggiornamento

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
SignatureUpdateCatchupInterval
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Impostare il numero di giorni prima che la protezione venga segnalata come non aggiornata

È inoltre possibile specificare il numero di giorni dopo i quali la protezione Antivirus Microsoft Defender è considerata precedente o non aggiornata. Dopo il numero di giorni specificato, il client segnala se stesso come non aggiornato e visualizza un errore all'utente del PC. Può anche causare Antivirus Microsoft Defender di tentare di scaricare un aggiornamento da altre origini (in base all'ordine di [origine di fallback](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)definito), ad esempio quando si utilizza MMPC come origine secondaria dopo aver impostato WSUS o Microsoft Update come prima origine.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Utilizzare Criteri di gruppo per specificare il numero di giorni prima che la protezione venga considerata non aggiornata

1.  Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

5.  Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > aggiornamenti delle firme** e configurare le impostazioni seguenti:

    1.  Fare doppio clic su Definisci il numero di giorni prima che le definizioni **di spyware** siano considerate non aggiornate e impostare l'opzione su **Abilitato**. Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence di sicurezza spyware non aggiornata.

    2. Fare clic su **OK**.

    3.  Fare doppio clic **su Definisci il numero di giorni** prima che le definizioni di virus siano considerate non aggiornate e impostare l'opzione su **Abilitato.** Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence per la sicurezza antivirus non aggiornata.

    4. Fare clic su **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Configurare le analisi di catch-up per gli endpoint che non sono stati analizzati per un po' di tempo

È possibile impostare il numero di analisi pianificate consecutive che possono essere perse prima Antivirus Microsoft Defender forzare un'analisi.

Il processo per l'abilitazione di questa funzionalità è il seguente:

1. Configurare almeno un'analisi pianificata (vedere [l'argomento Pianificare le](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi).
2. Abilitare la funzionalità di analisi di acquisizione dati.
3. Definire il numero di analisi che possono essere ignorate prima che si verifichi un'analisi di aggiornamento.

Questa funzionalità può essere abilitata sia per le analisi complete che per le analisi rapide.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Utilizzare Criteri di gruppo per abilitare e configurare la funzionalità di analisi di catch-up

1.  Assicurarsi di aver configurato almeno un'analisi pianificata.

2.  Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

5.  Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > analisi** e configurare le impostazioni seguenti:

    1.  Se sono state impostate analisi rapide pianificate, fare doppio clic sull'impostazione Attiva analisi rapida di acquisizione e impostare l'opzione su **Abilitato.**  
    2. Se sono state impostate analisi complete pianificate, fare doppio clic sull'impostazione Attiva analisi completa di acquisizione completa e impostare l'opzione su **Abilitato.**  Fare clic su **OK**.
    3. Fare doppio clic sull'impostazione Definisci il numero di giorni dopo i quali viene forzata un'analisi di **catch-up** e impostare l'opzione su **Abilitato.** 
    4. Immetti il numero di analisi che possono essere perse prima che un'analisi venga eseguita automaticamente quando l'utente accede al PC. Il tipo di analisi eseguito è determinato dall'argomento Specificare il tipo di analisi da **utilizzare** per un'analisi pianificata (vedere l'argomento [Pianifica](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi). Fare clic su **OK**.

> [!NOTE]
> Il titolo dell'impostazione di Criteri di gruppo fa riferimento al numero di giorni. L'impostazione, tuttavia, viene applicata al numero di analisi (non giorni) prima dell'esecuzione dell'analisi di aggiornamento.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Utilizzare i cmdlet di PowerShell per configurare le analisi di aggiornamento

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Per ulteriori informazioni su come usare [PowerShell con Antivirus Microsoft Defender,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Usare i cmdlet di Power Antivirus Microsoft Defender Shell per gestire i cmdlet di Antivirus Microsoft Defender e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Utilizzare Windows Management Instruction (WMI) per configurare le analisi di catch-up

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Usare Configuration Manager per configurare le analisi di catch-up

1.  Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)

2.  Passare alla sezione **Analisi pianificate** e **Forzare un'analisi** del tipo di analisi selezionato se il computer client è offline... su **Sì**. 

3. Fare clic su **OK**.

4.  [Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)

## <a name="related-articles"></a>Articoli correlati

- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)