---
title: Aggiungere dispositivi Windows 10 multi-sessione in Windows Virtual Desktop
description: Altre informazioni in questo articolo sull'onboarding Windows 10 dispositivi multi-sessione in Windows Desktop virtuale
keywords: Windows Desktop virtuale, WVD, microsoft defender, endpoint, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339479"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Aggiungere dispositivi Windows 10 multi-sessione in Windows Virtual Desktop 
6 minuti per leggere 

Si applica a: 
- Windows 10 multi-sessione in esecuzione Windows Virtual Desktop (WVD) 

Microsoft Defender for Endpoint supporta il monitoraggio di sessioni VDI Windows virtual desktop. A seconda delle esigenze dell'organizzazione, potrebbe essere necessario implementare sessioni VDI o desktop virtuale Windows per consentire ai dipendenti di accedere ai dati aziendali e alle app da un dispositivo non gestito, da una posizione remota o da uno scenario simile. Con Microsoft Defender per Endpoint, puoi monitorare queste macchine virtuali per individuare attività anomase.

 ## <a name="before-you-begin"></a>Prima di iniziare
Acquisire familiarità con le considerazioni [relative a VDI non persistente.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Anche [Windows Desktop](/azure/virtual-desktop/overview) virtuale non fornisce opzioni di non persistenza, offre modi per usare un'immagine Windows dorata che può essere usata per effettuare il provisioning di nuovi host e ridistribuire i computer. Ciò aumenta la volatilità nell'ambiente e influisce quindi sulle voci create e gestite nel portale di Microsoft Defender for Endpoint, riducendo potenzialmente la visibilità per gli analisti della sicurezza.

> [!NOTE]
> A seconda del metodo di onboarding scelto, i dispositivi possono essere visualizzati nel portale di Microsoft Defender per endpoint come uno dei seguenti: 
> - Voce singola per ogni desktop virtuale 
> - Più voci per ogni desktop virtuale 

Microsoft consiglia l'onboarding Windows desktop virtuale come singola voce per ogni desktop virtuale. Ciò garantisce che l'esperienza di indagine nel portale di Microsoft Defender Endpoint sia nel contesto di un dispositivo basato sul nome del computer. Le organizzazioni che eliminano e ridistribuino frequentemente gli host WVD devono prendere in considerazione l'uso di questo metodo perché impedisce la creazione di più oggetti per lo stesso computer nel portale di Microsoft Defender for Endpoint. Ciò può causare confusione durante l'analisi degli eventi imprevisti. Per ambienti di test o non volatili, è possibile scegliere in modo diverso. 

Microsoft consiglia di aggiungere lo script di onboarding di Microsoft Defender for Endpoint all'immagine D'oro WVD. In questo modo, è possibile assicurarsi che questo script di onboarding venga eseguito immediatamente al primo avvio. Viene eseguito come script di avvio al primo avvio in tutti i computer WVD di cui viene eseguito il provisioning dall'immagine D'oro WVD. Tuttavia, se si utilizza una delle immagini della raccolta senza modifiche, posizionare lo script in un percorso condiviso e chiamarlo da Criteri di gruppo locali o di dominio. 

> [!NOTE]
> Il posizionamento e la configurazione dello script di avvio di onboarding VDI nell'immagine dorata WVD lo configura come script di avvio che viene eseguito all'avvio del WVD. NON è consigliabile eseguire l'onboardboard dell'immagine D'oro WVD effettiva. Un'altra considerazione è il metodo utilizzato per eseguire lo script. Dovrebbe essere eseguito il prima possibile nel processo di avvio/provisioning per ridurre il tempo tra il computer disponibile per ricevere le sessioni e l'onboarding del dispositivo nel servizio. Di seguito vengono descritti gli scenari 1 & 2.

### <a name="scenarios"></a>Scenari
Esistono diversi modi per eseguire l'onboard di un computer host WVD:There are several ways to onboard a WVD host machine:

- Eseguire lo script nell'immagine d'oro (o da un percorso condiviso) durante l'avvio.
- Utilizzare uno strumento di gestione per eseguire lo script.

#### <a name="scenario-1-using-local-group-policy"></a>*Scenario 1: utilizzo di Criteri di gruppo locali*
Questo scenario richiede l'inserimento dello script in un'immagine d'oro e usa Criteri di gruppo locali per l'esecuzione all'inizio del processo di avvio.

Seguire le istruzioni riportate in [Onboard the non-persistent virtual desktop infrastructure (VDI) devices](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices).

Segui le istruzioni per una singola voce per ogni dispositivo.

#### <a name="scenario-2-using-domain-group-policy"></a>*Scenario 2: utilizzo di Criteri di gruppo di dominio*
In questo scenario viene utilizzato uno script situato centralmente ed eseguito utilizzando criteri di gruppo basati su dominio. Puoi anche inserire lo script nell'immagine dorata ed eseguirlo nello stesso modo.

**Scaricare il file WindowsDefenderATPOnboardingPackage.zip dal Centro sicurezza Windows Defender sicurezza**

1. Aprire il file del pacchetto .zip VDI (WindowsDefenderATPOnboardingPackage.zip)  

    1. Nel riquadro Microsoft Defender Security Center di spostamento selezionare **Impostazioni**  >  **onboarding**. 
    1. Seleziona Windows 10 come sistema operativo. 
    1. Nel campo **Metodo di distribuzione** selezionare Gli script di onboarding VDI per gli endpoint non persistenti. 
    1. Fai **clic su Scarica pacchetto** e salva il file .zip file. 

2. Estrarre il contenuto del file .zip in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere una cartella denominata **OptionalParamsPolicy** e i file **WindowsDefenderATPOnboardingScript.cmd** **eOnboard-NonPersistentMachine.ps1**.

**Utilizzare la console Gestione Criteri di gruppo per eseguire lo script all'avvio della macchina virtuale**

1. Aprire console Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Nell'Editor Gestione Criteri di gruppo, vai a **Configurazione computer** Preferenze \> **Impostazioni pannello** di \> **controllo**. 

3. Fare clic con il **pulsante destro del mouse** su Attività pianificate, scegliere Nuovo e quindi Attività immediata (almeno Windows 7).   

4. Nella finestra Attività visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza fare** clic su Cambia utente o **gruppo** e digitare SISTEMA. Fare **clic su Controlla nomi** e quindi su OK. NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività. 

5. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati. 

6. Passare alla scheda **Azioni** e fare clic su **Nuovo.** Verificare che **l'opzione Avvia** un programma sia selezionata nel campo Azione. Immettere quanto segue: 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   Selezionare quindi **OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Scenario 3: onboarding tramite strumenti di gestione*

Se si prevede di gestire i computer con uno strumento di gestione, è possibile eseguire l'onboardboard dei dispositivi con Microsoft Endpoint Configuration Manager.

Per altre informazioni, vedi [Onboard Windows 10 dispositivi con Configuration Manager.](configure-endpoints-sccm.md)

> [!WARNING]
> Se si prevede di utilizzare le regole di riduzione della superficie di [attacco,](attack-surface-reduction.md)tenere presente che la regola " Bloccare le creazioni di processi originate dai[comandi PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)e WMI " non deve essere utilizzata, perché tale regola non è compatibile con la gestione tramite Microsoft Endpoint Configuration Manager. La regola blocca i comandi WMI utilizzati dal client di Configuration Manager per funzionare correttamente. 

> [!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che il dispositivo sia stato correttamente onboarding nel servizio. Per altre informazioni, vedi [Eseguire un test di rilevamento su un dispositivo Microsoft Defender for Endpoint appena onboarded.](run-detection-test.md) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Tagging dei computer durante la creazione dell'immagine d'oro 

Nell'ambito dell'onboarding, è consigliabile impostare un tag del computer su in grado di differenziare più facilmente i computer WVD nel Centro sicurezza Microsoft. Per altre informazioni, vedi [Aggiungere tag dispositivo impostando un valore di chiave del Registro di sistema.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Altre impostazioni di configurazione consigliate 

Quando si compila l'immagine dorata, è possibile configurare anche le impostazioni di protezione iniziali. Per ulteriori informazioni, vedere [Altre impostazioni di configurazione consigliate.](configure-endpoints-gp.md#other-recommended-configuration-settings) 

Inoltre, se si utilizzano profili utente FSlogix, è consigliabile escludere i file seguenti dalla protezione always-on: 

**Escludi file:** 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**Escludi processi:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>Requisiti di licenza 

Nota sulle licenze: quando si usa Windows 10 Enterprise più sessioni, Windows 10 Enterprise base alle proprie esigenze, è possibile scegliere di disporre della licenza per tutti gli utenti tramite Microsoft Defender for Endpoint (per utente), Windows Enterprise E5, Microsoft 365 Security o Microsoft 365 E5 oppure disporre della licenza per la macchina virtuale tramite Azure Defender.
I requisiti di licenza per Microsoft Defender per endpoint sono disponibili all'indirizzo: [Licensing requirements](minimum-requirements.md#licensing-requirements).

#### <a name="related-links"></a>Collegamenti correlati

[Aggiungere esclusioni per Microsoft Defender tramite PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
