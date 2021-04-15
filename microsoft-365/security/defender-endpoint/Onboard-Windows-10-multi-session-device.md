---
title: Aggiungere dispositivi Windows 10 multi-sessione in Windows Virtual Desktop
description: Altre informazioni in questo articolo sull'onboarding di dispositivi Windows 10 multi-sessione in Desktop virtuale Windows
keywords: Desktop virtuale Windows, WVD, microsoft defender, endpoint, onboard
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
ms.openlocfilehash: 6ad61d583815f669affe989d7519ba0ade6fe08d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760087"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Aggiungere dispositivi Windows 10 multi-sessione in Windows Virtual Desktop 
6 minuti per leggere 

Si applica a: 
- Windows 10 multi-sessione in esecuzione su Desktop virtuale Windows (WVD) 

Microsoft Defender for Endpoint supporta il monitoraggio sia delle sessioni VDI che di Desktop virtuale Windows. A seconda delle esigenze dell'organizzazione, potrebbe essere necessario implementare sessioni VDI o Desktop virtuale Windows per consentire ai dipendenti di accedere ai dati aziendali e alle app da un dispositivo non gestito, da una posizione remota o da uno scenario simile. Con Microsoft Defender per Endpoint, puoi monitorare queste macchine virtuali per individuare attività anomase.

 ## <a name="before-you-begin"></a>Prima di iniziare
Acquisire familiarità con le considerazioni [relative a VDI non persistente.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Desktop [virtuale Windows](https://docs.microsoft.com/azure/virtual-desktop/overview) non offre opzioni di non persistenza, ma offre modi per usare un'immagine Windows dorata che può essere usata per effettuare il provisioning di nuovi host e ridistribuire i computer. Ciò aumenta la volatilità nell'ambiente e influisce quindi sulle voci create e gestite nel portale di Microsoft Defender for Endpoint, riducendo potenzialmente la visibilità per gli analisti della sicurezza.

> [!NOTE]
> A seconda del metodo di onboarding scelto, i dispositivi possono essere visualizzati nel portale di Microsoft Defender per endpoint come uno dei seguenti: 
> - Voce singola per ogni desktop virtuale 
> - Più voci per ogni desktop virtuale 

Microsoft consiglia l'onboarding di Desktop virtuale Windows come singola voce per ogni desktop virtuale. Ciò garantisce che l'esperienza di indagine nel portale di Microsoft Defender Endpoint sia nel contesto di un dispositivo basato sul nome del computer. Le organizzazioni che eliminano e ridistribuino frequentemente gli host WVD devono prendere in considerazione l'uso di questo metodo perché impedisce la creazione di più oggetti per lo stesso computer nel portale di Microsoft Defender for Endpoint. Ciò può causare confusione durante l'analisi degli eventi imprevisti. Per ambienti di test o non volatili, è possibile scegliere in modo diverso. 

Microsoft consiglia di aggiungere lo script di onboarding di Microsoft Defender for Endpoint all'immagine D'oro WVD. In questo modo, è possibile assicurarsi che questo script di onboarding venga eseguito immediatamente al primo avvio. Viene eseguito come script di avvio al primo avvio in tutti i computer WVD di cui viene eseguito il provisioning dall'immagine D'oro WVD. Tuttavia, se si utilizza una delle immagini della raccolta senza modifiche, posizionare lo script in un percorso condiviso e chiamarlo da Criteri di gruppo locali o di dominio. 

> [!NOTE]
> Il posizionamento e la configurazione dello script di avvio di onboarding VDI nell'immagine dorata WVD lo configura come script di avvio che viene eseguito all'avvio del WVD. NON è consigliabile eseguire l'onboardboard dell'immagine D'oro WVD effettiva. Un'altra considerazione è il metodo utilizzato per eseguire lo script. Dovrebbe essere eseguito il prima possibile nel processo di avvio/provisioning per ridurre il tempo tra il computer disponibile per ricevere le sessioni e l'onboarding del dispositivo nel servizio. Di seguito vengono descritti gli scenari 1 & 2.

### <a name="scenarios"></a>Scenari
Esistono diversi modi per eseguire l'onboard di un computer host WVD:There are several ways to onboard a WVD host machine:

- Eseguire lo script nell'immagine d'oro (o da un percorso condiviso) durante l'avvio.
- Utilizzare uno strumento di gestione per eseguire lo script.

#### <a name="scenario-1-using-local-group-policy"></a>*Scenario 1: utilizzo di Criteri di gruppo locali*
Questo scenario richiede l'inserimento dello script in un'immagine d'oro e usa Criteri di gruppo locali per l'esecuzione all'inizio del processo di avvio.

Seguire le istruzioni riportate in [Onboard non persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).

Segui le istruzioni per una singola voce per ogni dispositivo.

#### <a name="scenario-2-using-domain-group-policy"></a>*Scenario 2: utilizzo di Criteri di gruppo di dominio*
In questo scenario viene utilizzato uno script situato centralmente ed eseguito utilizzando criteri di gruppo basati su dominio. Puoi anche inserire lo script nell'immagine dorata ed eseguirlo nello stesso modo.

**Scaricare il file WindowsDefenderATPOnboardingPackage.zip dal Centro sicurezza Windows Defender sicurezza**

1. Aprire il file ZIP del pacchetto di configurazione VDI (WindowsDefenderATPOnboardingPackage.zip)  

    1. Nel riquadro di spostamento di Microsoft Defender Security Center seleziona  >  **Impostazioni Onboarding.** 
    1. Seleziona Windows 10 come sistema operativo. 
    1. Nel campo **Metodo di distribuzione** selezionare Gli script di onboarding VDI per gli endpoint non persistenti. 
    1. Fai **clic su Scarica** pacchetto e salva il file ZIP. 

2. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dal dispositivo. Dovresti avere una cartella denominata **OptionalParamsPolicy** e i file **WindowsDefenderATPOnboardingScript.cmd** **eOnboard-NonPersistentMachine.ps1**.

**Utilizzare la console Gestione Criteri di gruppo per eseguire lo script all'avvio della macchina virtuale**

1. Aprire console Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

1. Nell'Editor Gestione Criteri di gruppo, vai a **Configurazione computer** Preferenze \> **Impostazioni pannello** di \> **controllo**. 

1. Fai clic con il **pulsante destro del mouse** su Attività pianificate, fai clic su Nuovo e quindi su **Attività** immediata (almeno Windows 7).  

1. Nella finestra Attività visualizzata passare alla **scheda** Generale. In **Opzioni di sicurezza fare** clic su Cambia utente o **gruppo** e digitare SISTEMA. Fare **clic su Controlla nomi** e quindi su OK. NT AUTHORITY\SYSTEM viene visualizzato come account utente con cui verrà eseguita l'attività. 

1. Selezionare **Esegui se l'utente è connesso o meno** e selezionare la casella di controllo Esegui con **privilegi** più elevati. 

1. Passare alla scheda **Azioni** e fare clic su **Nuovo.** Verificare che **l'opzione Avvia** un programma sia selezionata nel campo Azione. Immettere quanto segue: 

    > Action = "Avviare un programma" <br>
    > Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe <br>
    > Add Arguments (facoltativo) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"

1. Fare **clic su OK** e chiudere tutte le finestre della Console Gestione Criteri di gruppo aperte.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Scenario 3: onboarding tramite strumenti di gestione*

Se si prevede di gestire i computer con uno strumento di gestione, è possibile eseguire l'onboardboard dei dispositivi con Microsoft Endpoint Configuration Manager.

Per altre informazioni, vedi [Onboard di dispositivi Windows 10 con Configuration Manager.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) 

> [!WARNING]
> Se si prevede di utilizzare le regole di riduzione della superficie di [attacco,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)tenere presente che la regola " Bloccare le creazioni di processi originate dai comandi[PSExec](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)e WMI " non deve essere utilizzata perché non è compatibile con la gestione tramite Microsoft Endpoint Configuration Manager perché questa regola blocca i comandi WMI utilizzati dal client di Configuration Manager per funzionare correttamente. 

> [!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che il dispositivo sia stato correttamente onboarding nel servizio. Per altre informazioni, vedi [Eseguire un test di rilevamento su un dispositivo Microsoft Defender for Endpoint appena onboarded.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test) 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Tagging dei computer durante la creazione dell'immagine d'oro 

Nell'ambito dell'onboarding, è consigliabile impostare un tag del computer su in grado di differenziare più facilmente i computer WVD nel Centro sicurezza Microsoft. Per altre informazioni, vedi [Aggiungere tag dispositivo impostando un valore di chiave del Registro di sistema.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value) 

#### <a name="other-recommended-configuration-settings"></a>Altre impostazioni di configurazione consigliate 

Quando si compila l'immagine dorata, è possibile configurare anche le impostazioni di protezione iniziali. Per ulteriori informazioni, vedere [Altre impostazioni di configurazione consigliate.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings) 

Inoltre, se si utilizzano profili utente FSlogix, è consigliabile escludere i file seguenti dalla protezione always-on: 

**Escludi file:** 

> %ProgramFiles%\FSLogix\Apps\frxdrv.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxdrvvt.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxccd.sys <br>
> %TEMP% \* . Disco rigido virtuale <br>
> %TEMP% \* . VHDX <br>
> %Windir%\TEMP \* . Disco rigido virtuale <br>
> %Windir%\TEMP \* . VHDX <br>
> \\storageaccount.file.core.windows.net\share \* \* . Disco rigido virtuale <br>
> \\storageaccount.file.core.windows.net\share \* \* . VHDX <br>

**Escludi processi:**

> %ProgramFiles%\FSLogix\Apps\frxccd.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxccds.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxsvc.exe <br>

#### <a name="licensing-requirements"></a>Requisiti per la licenza 

Windows 10 Multi-session è un sistema operativo client. I requisiti di licenza per Microsoft Defender per endpoint sono disponibili all'indirizzo: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).
