---
title: Antivirus Microsoft Defender Virtual Desktop Infrastructure guida alla distribuzione
description: Informazioni su come distribuire Antivirus Microsoft Defender in un ambiente desktop virtuale per il miglior equilibrio tra protezione e prestazioni.
keywords: vdi, hyper-v, vm, macchina virtuale, windows defender, antivirus, av, desktop virtuale, rds, desktop remoto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/11/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 83e37b6d59d7356b53e5024204e39473764cea72
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924916"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Guida alla distribuzione di Microsoft Defender Antivirus in un ambiente VDI (Virtual Desktop Infrastructure)

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Oltre alle configurazioni hardware o locali standard, è anche possibile utilizzare Antivirus Microsoft Defender in un ambiente desktop remoto (RDS) o VDI (Virtual Desktop Infrastructure).

Vedi [Windows documentazione sul desktop virtuale per](/azure/virtual-desktop) ulteriori dettagli su Desktop remoto Microsoft Services e il supporto VDI.

Per le macchine virtuali basate su Azure, vedere [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).

Con la possibilità di distribuire facilmente gli aggiornamenti alle macchine virtuali in esecuzione in VDI, questa guida è stata abbreviata per concentrarsi su come è possibile ottenere gli aggiornamenti nei computer in modo rapido e semplice. Non è più necessario creare e sigillare periodicamente le immagini dorate, poiché gli aggiornamenti vengono espansi nei bit dei componenti nel server host e quindi scaricati direttamente nella macchina virtuale quando è attivata.

In questa guida viene descritto come configurare le macchine virtuali per garantire prestazioni e protezione ottimali, tra cui:

- [Configurare una condivisione file VDI dedicata per gli aggiornamenti delle funzionalità di intelligence per la sicurezza](#set-up-a-dedicated-vdi-file-share)
- [Analisi pianificate casuali](#randomize-scheduled-scans)
- [Usare analisi rapide](#use-quick-scans)
- [Impedisci notifiche](#prevent-notifications)
- [Disabilitare l'esecuzione delle analisi dopo ogni aggiornamento](#disable-scans-after-an-update)
- [Eseguire l'analisi di computer o computer non aggiornati che sono stati offline per un po' di tempo](#scan-vms-that-have-been-offline)
- [Applicare esclusioni](#exclusions)

È inoltre possibile scaricare il white paper Antivirus Microsoft Defender su [Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), che esamina la nuova funzionalità di aggiornamento della sicurezza intelligence condivisa, oltre a test delle prestazioni e indicazioni su come testare le prestazioni dell'antivirus nel proprio VDI.

> [!IMPORTANT]
> Anche se la VDI può essere ospitata in Windows Server 2012 o Windows Server 2016, le macchine virtuali devono eseguire almeno Windows 10 1607, a causa di tecnologie e funzionalità di protezione più avanzate che non sono disponibili nelle versioni precedenti di Windows.<br/>Esistono miglioramenti delle prestazioni e delle funzionalità per il modo in cui Microsoft Defender AV opera sulle macchine virtuali in Windows 10 Insider Preview, build 18323 (e versioni successive). Ci identificheremo in questa guida se devi usare una build di Insider Preview; se non viene specificato, la versione minima richiesta per la protezione e le prestazioni migliori è Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Configurare una condivisione file VDI dedicata

In Windows 10, versione 1903, è stata introdotta la funzionalità di intelligence per la sicurezza condivisa, che scarica la decompressione degli aggiornamenti di security intelligence scaricati in un computer host, salvando così le risorse precedenti di CPU, disco e memoria nei singoli computer. Questa funzionalità è stata backported e ora funziona in Windows 10 1703 e versioni successive. È possibile impostare questa funzionalità con Criteri di gruppo o PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Utilizzare Criteri di gruppo per abilitare la funzionalità di intelligence per la sicurezza condivisa:

1. Nel computer di gestione di Criteri di gruppo aprire console Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence**.

5. Fare doppio clic **su Definisci percorso intelligence di sicurezza per i client VDI** e quindi impostare l'opzione su **Abilitato**. Viene visualizzato automaticamente un campo.

6. Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).

7. Fare clic su **OK**.

8. Distribuire l'oggetto Criteri di gruppo alle macchine virtuali che si desidera testare.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Usare PowerShell per abilitare la funzionalità di intelligence per la sicurezza condivisa

Utilizzare il cmdlet seguente per abilitare la funzionalità. Sarà quindi necessario eseguire il push di questo tipo come si farebbe normalmente per eseguire il push dei criteri di configurazione basati su PowerShell nelle macchine virtuali:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Vedi la [sezione Download e unpackage](#download-and-unpackage-the-latest-updates) per sapere \<shared location\> quale sarà il pacchetto.

## <a name="download-and-unpackage-the-latest-updates"></a>Scaricare e annullare il pacchetto degli aggiornamenti più recenti

Ora puoi iniziare a scaricare e installare nuovi aggiornamenti. Di seguito è stato creato uno script di PowerShell di esempio. Questo script è il modo più semplice per scaricare nuovi aggiornamenti e prepararli per le macchine virtuali. È quindi consigliabile impostare lo script per l'esecuzione in un determinato momento nel computer di gestione usando un'attività pianificata (o, se si ha familiarità con l'uso di script di PowerShell in Azure, Intune o SCCM, è possibile usare anche tali script).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

È possibile impostare un'attività pianificata per l'esecuzione una volta al giorno in modo che ogni volta che il pacchetto viene scaricato e decompresso, le macchine virtuali riceveranno il nuovo aggiornamento. Ti consigliamo di iniziare con una volta al giorno, ma dovresti provare ad aumentare o diminuire la frequenza per comprendere l'impatto. 

I pacchetti di intelligence per la sicurezza vengono in genere pubblicati una volta ogni tre o quattro ore. L'impostazione di una frequenza inferiore a quattro ore non è consigliata perché aumenterà il sovraccarico di rete sul computer di gestione senza alcun vantaggio.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Impostare un'attività pianificata per eseguire lo script di PowerShell

1. Nel computer di gestione apri il menu Start e digita **Utilità di pianificazione.** Aprirlo e selezionare **Crea attività...** sul pannello laterale.

2. Immetti il nome come **Decompressione di Security intelligence**. Vai alla **scheda Trigger.** Seleziona **Nuovo...** > **Daily** e selezionare **OK.**

3. Passare alla **scheda** Azioni. Seleziona **Nuovo...** Immettere **PowerShell** nel **campo Programma/Script.** Immettere `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` nel campo **Aggiungi** argomenti. Selezionare **OK**.

4. Se lo si desidera, è possibile scegliere di configurare impostazioni aggiuntive.

5. Selezionare **OK** per salvare l'attività pianificata.
 
È possibile avviare l'aggiornamento manualmente facendo clic con il pulsante destro del mouse sull'attività e scegliendo **Esegui**.

### <a name="download-and-unpackage-manually"></a>Scaricare e annullare il pacchetto manualmente

Se si preferisce eseguire tutte le attività manualmente, ecco cosa fare per replicare il comportamento dello script:

1. Creare una nuova cartella nella radice di sistema chiamata per archiviare gli aggiornamenti di intelligence, ad `wdav_update` esempio creare la cartella `c:\wdav_update` .

2. Creare una sottocartella *in wdav_update* con un nome GUID, ad esempio `{00000000-0000-0000-0000-000000000000}`

Ecco un esempio: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > Nello script viene impostato in modo che le ultime 12 cifre del GUID siano l'anno, il mese, il giorno e l'ora in cui il file è stato scaricato in modo da creare una nuova cartella ogni volta. È possibile modificare questa impostazione in modo che il file sia scaricato nella stessa cartella ogni volta.

3. Scaricare un pacchetto di intelligence per la [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  sicurezza dalla cartella GUID. Il file deve essere denominato `mpam-fe.exe` .

4. Aprire una finestra del prompt dei comandi e passare alla cartella GUID creata. Utilizzare il **comando /X** extraction per estrarre i file, ad esempio `mpam-fe.exe /X` .

   > [!NOTE]
   > Le macchine virtuali prelevano il pacchetto aggiornato ogni volta che viene creata una nuova cartella GUID con un pacchetto di aggiornamento estratto o ogni volta che una cartella esistente viene aggiornata con un nuovo pacchetto estratto.

## <a name="randomize-scheduled-scans"></a>Analisi pianificate casuali

Le analisi pianificate vengono eseguite oltre alla protezione [e all'analisi in tempo reale.](configure-real-time-protection-microsoft-defender-antivirus.md)

L'ora di inizio dell'analisi stessa è ancora basata sul criterio di analisi pianificato (**ScheduleDay,** **ScheduleTime** e **ScheduleQuickScanTime**). La casualità causerà Antivirus Microsoft Defender un'analisi su ogni computer entro un intervallo di 4 ore dall'ora impostata per l'analisi pianificata.

Vedere [Pianificare le analisi per](scheduled-catch-up-scans-microsoft-defender-antivirus.md) altre opzioni di configurazione disponibili per le analisi pianificate.

## <a name="use-quick-scans"></a>Usare analisi rapide

È possibile specificare il tipo di analisi da eseguire durante un'analisi pianificata. Le analisi rapide sono l'approccio preferito perché sono progettate per cercare in tutti i luoghi in cui il malware deve risiedere per essere attivo. Nella procedura seguente viene descritto come configurare analisi rapide tramite Criteri di gruppo.

1. Nell'Editor Criteri di gruppo passare a **Modelli amministrativi**  >  **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **Analisi**.

2. Selezionare **Specificare il tipo di analisi da utilizzare per un'analisi pianificata** e quindi modificare l'impostazione dei criteri.

3. Impostare il criterio su **Abilitato** e quindi in **Opzioni** selezionare **Analisi rapida.**

4. Selezionare **OK**. 

5. Distribuire l'oggetto Criteri di gruppo come di consueto.

## <a name="prevent-notifications"></a>Impedisci notifiche

A volte, Antivirus Microsoft Defender notifiche possono essere inviate o mantenute in più sessioni. Per ridurre al minimo il problema, è possibile bloccare l'interfaccia Antivirus Microsoft Defender utente. La procedura seguente descrive come eliminare le notifiche con Criteri di gruppo.

1. Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Client Interface**.

2. Selezionare **Elimina tutte le notifiche** e quindi modificare le impostazioni dei criteri. 

3. Impostare il criterio su **Abilitato** e quindi selezionare **OK.**

4. Distribuire l'oggetto Criteri di gruppo come di consueto.

L'eliminazione delle notifiche impedisce Antivirus Microsoft Defender notifiche di essere visualizzate nel centro notifiche in Windows 10 quando vengono eseguite analisi o vengono eseguite azioni di correzione. Tuttavia, il team delle operazioni di sicurezza visualizza i risultati dell'analisi [nel portale Microsoft 365 Defender.](microsoft-defender-security-center.md)

> [!TIP]
> Per aprire il Centro notifiche in Windows 10, eseguire una delle operazioni seguenti:
> - All'estremità destra della barra delle applicazioni seleziona l'icona del Centro notifiche.
> - Premi il Windows logo + A.
> - In un dispositivo touchscreen scorri rapidamente dal bordo destro dello schermo.

## <a name="disable-scans-after-an-update"></a>Disabilitare le analisi dopo un aggiornamento

La disabilitazione di un'analisi dopo un aggiornamento impedirà l'esecuzione di un'analisi dopo la ricezione di un aggiornamento. È possibile applicare questa impostazione durante la creazione dell'immagine di base se è stata eseguita anche un'analisi rapida. In questo modo, è possibile impedire alla macchina virtuale appena aggiornata di eseguire di nuovo un'analisi, poiché è già stata analizzata al momento della creazione dell'immagine di base.

> [!IMPORTANT]
> L'esecuzione di analisi dopo un aggiornamento garantisce che le macchine virtuali siano protette con gli ultimi aggiornamenti di Security intelligence. La disabilitazione di questa opzione riduce il livello di protezione delle macchine virtuali e deve essere usata solo quando si crea o distribuisce per la prima volta l'immagine di base.

1. Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Security Intelligence.**

2. Seleziona **Attiva analisi dopo l'aggiornamento delle funzionalità di intelligence** per la sicurezza e quindi modifica l'impostazione dei criteri.

3. Impostare il criterio su **Disabilitato**.

4. Selezionare **OK**.

5. Distribuire l'oggetto Criteri di gruppo come di consueto.

Questo criterio impedisce l'esecuzione di un'analisi immediatamente dopo un aggiornamento.

## <a name="scan-vms-that-have-been-offline"></a>Analizzare le macchine virtuali che sono state offline

1. Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Scansione**.

2. Seleziona **Attiva analisi rapida di acquisizione e** quindi modifica l'impostazione dei criteri.

3. Impostare il criterio su **Abilitato**.

4. Selezionare **OK**.

5. Distribuisci l'oggetto Criteri di gruppo come di solito.

Questo criterio forza un'analisi se la macchina virtuale ha perso due o più analisi pianificate consecutive.

## <a name="enable-headless-ui-mode"></a>Abilitare la modalità interfaccia utente headless

1. Nell'Editor Criteri di gruppo passare a Windows **componenti**  >  **Antivirus Microsoft Defender**  >  **Client Interface**.

2. Seleziona **Abilita modalità interfaccia utente headless** e modifica il criterio.

3. Impostare il criterio su **Abilitato**.

4. Fare clic su **OK**.

5. Distribuisci l'oggetto Criteri di gruppo come di solito.
 
Questo criterio nasconde l'intera Antivirus Microsoft Defender'interfaccia utente agli utenti finali dell'organizzazione.

## <a name="exclusions"></a>Esclusioni

Le esclusioni possono essere aggiunte, rimosse o personalizzate in base alle proprie esigenze.

Per ulteriori informazioni, vedere [Configure Antivirus Microsoft Defender exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Blog Community tech: Configurazione Antivirus Microsoft Defender per computer VDI non persistenti](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [Forum TechNet su Servizi Desktop remoto e VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [Script Di PowerShell SignatureDownloadCustomTask](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)