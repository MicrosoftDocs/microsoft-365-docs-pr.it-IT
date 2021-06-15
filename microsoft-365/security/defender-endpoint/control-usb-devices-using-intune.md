---
title: Come controllare i dispositivi USB e altri supporti rimovibili con Intune (Windows 10)
description: È possibile configurare le impostazioni di Intune per ridurre le minacce dall'archiviazione rimovibile, ad esempio i dispositivi USB.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cd489cae21b9140463d4ede72813ec014b3bb
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926356"
---
# <a name="how-to-control-usb-devices-and-other-removable-media-using-microsoft-defender-for-endpoint"></a>Come controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender for Endpoint

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Microsoft consiglia un approccio [a](https://aka.ms/devicecontrolblog)più livelli alla protezione dei supporti rimovibili e Microsoft Defender for Endpoint offre più funzionalità di monitoraggio e controllo per evitare che le minacce nelle periferiche non autorizzate compromettentino i dispositivi:

1. [Scopri gli eventi connessi plug and play per le periferiche in Microsoft Defender for Endpoint advanced hunting.](#discover-plug-and-play-connected-events) Identificare o analizzare attività di utilizzo sospette.

2. Configurare per consentire o bloccare solo determinati dispositivi rimovibili e prevenire le minacce.
    1. [Consentire o bloccare i dispositivi rimovibili](#allow-or-block-removable-devices) in base alla configurazione granulare per negare l'accesso in scrittura ai dischi rimovibili e approvare o negare i dispositivi tramite ID dispositivo USB. Assegnazione flessibile dei criteri delle impostazioni di installazione dei dispositivi in base a un singolo utente o gruppo di utenti e dispositivi di Azure Active Directory (Azure AD).

    2. [Impedisci minacce dall'archiviazione rimovibile](#prevent-threats-from-removable-storage) introdotta dai dispositivi di archiviazione rimovibili abilitando:  
        - Antivirus Microsoft Defender protezione in tempo reale (RTP) per analizzare l'archiviazione rimovibile alla ricerca di malware.  
        - La regola USB di riduzione della superficie di attacco (ASR) per bloccare i processi non attendibili e non firmati eseguiti da USB.  
        - Impostazioni di protezione DMA (Direct Memory Access) per ridurre gli attacchi DMA, inclusa la protezione DMA kernel per Thunderbolt e il blocco di DMA fino all'accesso di un utente.  

3. [Crea avvisi e](#create-customized-alerts-and-response-actions) azioni di risposta personalizzati per monitorare l'utilizzo di dispositivi rimovibili in base a questi eventi Plug and Play o a qualsiasi altro evento di Microsoft Defender for Endpoint con [regole di rilevamento personalizzate.](/microsoft-365/security/defender-endpoint/custom-detection-rules)

4. [Rispondere alle minacce](#respond-to-threats) provenienti dalle periferiche in tempo reale in base alle proprietà segnalate da ogni periferica.

>[!Note]
>Queste misure di riduzione delle minacce consentono di impedire l'arrivo di malware nell'ambiente. Per proteggere i dati aziendali dall'uscita dall'ambiente, è anche possibile configurare misure di prevenzione della perdita dei dati. Ad esempio, nei dispositivi Windows 10 è possibile configurare [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) e [Windows Information Protection](/windows/security/information-protection/create-wip-policy-using-intune-azure.md), che crittograferà i dati aziendali anche se sono archiviati in un dispositivo personale oppure utilizzare il [CSP Archiviazione/RemovableDiskDenyWriteAccess](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess) per negare l'accesso in scrittura ai dischi rimovibili. Inoltre, puoi classificare e proteggere i file nei dispositivi [Windows](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview) (inclusi i dispositivi USB montati) usando Microsoft Defender per Endpoint e Azure Information Protection.

## <a name="discover-plug-and-play-connected-events"></a>Individuare gli eventi connessi plug and play

Puoi visualizzare gli eventi connessi plug and play in Microsoft Defender for Endpoint advanced hunting per identificare attività di utilizzo sospette o eseguire indagini interne.
Per esempi di query di ricerca avanzata di Defender per Endpoint, vedi l'articolo [microsoft Defender for Endpoint hunting queries GitHub repo](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).

Esempi Power BI modelli di report sono disponibili per Microsoft Defender per Endpoint che puoi usare per le query di ricerca avanzate. Con questi modelli di esempio, incluso uno per il controllo dei dispositivi, puoi integrare la potenza della ricerca avanzata in Power BI. Per ulteriori informazioni, GitHub repository dei modelli [PowerBI.](https://github.com/microsoft/MDATP-PowerBI-Templates) Vedi [Creare report personalizzati con Power BI](/microsoft-365/security/defender-endpoint/api-power-bi) per altre informazioni sull'Power BI integrazione.

## <a name="allow-or-block-removable-devices"></a>Consentire o bloccare i dispositivi rimovibili
Nella tabella seguente vengono descritti i modi in cui Microsoft Defender for Endpoint può consentire o bloccare i dispositivi rimovibili in base alla configurazione granulare.

| Controllo  | Descrizione |
|----------|-------------|
| [Limitare le unità USB e altre periferiche](#restrict-usb-drives-and-other-peripherals) | Puoi consentire o impedire agli utenti di installare solo le unità USB e altre periferiche incluse in un elenco di dispositivi o tipi di dispositivi autorizzati/non autorizzati. |
| [Bloccare l'installazione e l'utilizzo dell'archiviazione rimovibile](#block-installation-and-usage-of-removable-storage) | Non è possibile installare o usare l'archiviazione rimovibile. |
| [Consentire l'installazione e l'utilizzo di periferiche approvate in modo specifico](#allow-installation-and-usage-of-specifically-approved-peripherals)   | È possibile installare e utilizzare solo periferiche approvate che segnalano proprietà specifiche nel firmware. |
| [Impedire l'installazione di periferiche specificamente proibite](#prevent-installation-of-specifically-prohibited-peripherals) | Non è possibile installare o utilizzare periferiche proibite che segnalano proprietà specifiche nel firmware. |
| [Consentire l'installazione e l'utilizzo di periferiche approvate in modo specifico con ID istanza dispositivo corrispondenti](#allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids) | Puoi installare e usare solo periferiche approvate che corrispondono a uno qualsiasi di questi ID di istanza del dispositivo. |
| [Impedire l'installazione e l'utilizzo di periferiche specificamente proibite con ID istanza dispositivo corrispondenti](#prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids) | Non è possibile installare o usare periferiche non consentite che corrispondono a uno qualsiasi di questi ID di istanza del dispositivo. |
| [Limitare i servizi che utilizzano Bluetooth](#limit-services-that-use-bluetooth) | È possibile limitare i servizi che possono utilizzare Bluetooth. |
| [Usare Le impostazioni di base di Microsoft Defender per endpoint](#use-microsoft-defender-for-endpoint-baseline-settings) | Puoi impostare la configurazione consigliata per ATP usando la baseline di sicurezza defender per endpoint. |

### <a name="restrict-usb-drives-and-other-peripherals"></a>Limitare le unità USB e altre periferiche

Per evitare infezioni da malware o perdita di dati, un'organizzazione può limitare le unità USB e altre periferiche. Nella tabella seguente vengono descritti i modi in cui Microsoft Defender for Endpoint può impedire l'installazione e l'utilizzo di unità USB e altre periferiche.

| Controllo  | Descrizione
|----------|-------------|
| [Consentire l'installazione e l'utilizzo di unità USB e altre periferiche](#allow-installation-and-usage-of-usb-drives-and-other-peripherals) | Consentire agli utenti di installare solo le unità USB e altre periferiche incluse in un elenco di dispositivi o tipi di dispositivi autorizzati |
| [Impedire l'installazione e l'utilizzo di unità USB e altre periferiche](#prevent-installation-and-usage-of-usb-drives-and-other-peripherals) | Impedire agli utenti di installare unità USB e altre periferiche incluse in un elenco di dispositivi e tipi di dispositivi non autorizzati |

Tutti i controlli precedenti possono essere impostati tramite i modelli [amministrativi di](/intune/administrative-templates-windows)Intune. I criteri pertinenti si trovano qui nei modelli di amministratore di Intune:

![Screenshot of list of Admin Templates](images/admintemplates.png)

>[!Note]
>Usando Intune, puoi applicare criteri di configurazione dei dispositivi a utenti e/o gruppi di dispositivi di Azure AD.
I criteri precedenti possono essere impostati anche tramite le impostazioni [del provider di](/windows/client-management/mdm/policy-csp-deviceinstallation) servizi di configurazione per l'installazione dei dispositivi e gli oggetti Criteri di gruppo Installazione [dispositivi](/previous-versions/dotnet/articles/bb530324(v=msdn.10)).

> [!Note]
> Testare e perfezionare sempre queste impostazioni con un gruppo pilota di utenti e dispositivi prima di applicarle nell'ambiente di produzione.
Per altre informazioni sul controllo dei dispositivi USB, vedi il [blog di Microsoft Defender for Endpoint.](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)

#### <a name="allow-installation-and-usage-of-usb-drives-and-other-peripherals"></a>Consentire l'installazione e l'utilizzo di unità USB e altre periferiche

Un modo per approcciare l'installazione e l'uso di unità USB e altre periferiche consiste nell'iniziare consentendo tutto. In seguito, puoi iniziare a ridurre i driver USB consentiti e altre periferiche.

>[!Note]
>Poiché una periferica USB non autorizzata può avere firmware che falsifica le proprietà USB, ti consigliamo di consentire solo periferiche USB approvate in modo specifico e limitare gli utenti che possono accedervi.

1. Abilita **Impedisci l'installazione di dispositivi non descritti da altre impostazioni dei criteri** per tutti gli utenti.
2. Abilita **Consenti l'installazione dei dispositivi usando driver che corrispondono a queste classi di configurazione** dei dispositivi per tutte le classi di installazione dei [dispositivi.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)

Per applicare il criterio per i dispositivi già installati, applica i criteri di prevenzione con questa impostazione.

Quando configuri il criterio Consenti installazione dispositivi, devi consentire anche tutti gli attributi padre. Puoi visualizzare gli elementi padre di un dispositivo aprendo Gestione dispositivi e visualizzando in base alla connessione.

![Dispositivi tramite connessione](images/devicesbyconnection.png)

In questo esempio è necessario aggiungere le classi seguenti: HID, Keyboard e {36fc9e60-c465-11cf-8056-444553540000}. Per [altre informazioni, vedi Driver USB](/windows-hardware/drivers/usbcon/supported-usb-classes) forniti da Microsoft.

![Controller host dispositivo](images/devicehostcontroller.jpg)

Se vuoi limitare determinati dispositivi, rimuovi la classe di configurazione del dispositivo della periferica che vuoi limitare. Aggiungi quindi l'ID dispositivo che vuoi aggiungere. L'ID dispositivo si basa sull'ID fornitore e sui valori dell'ID prodotto per un dispositivo. Per informazioni sui formati degli ID dispositivo, vedi [Identificatori USB standard.](/windows-hardware/drivers/install/standard-usb-identifiers) 

Per trovare gli ID del dispositivo, vedi [Cercare l'ID dispositivo.](#look-up-device-id) 

Ad esempio:

1. Rimuovi la classe USBDevice **dall'opzione Consenti l'installazione dei dispositivi usando driver che corrispondono alla configurazione del dispositivo.**
2. Aggiungi l'ID del dispositivo per consentire l'installazione del dispositivo **che corrisponde a uno qualsiasi di questi ID dispositivo.** 


#### <a name="prevent-installation-and-usage-of-usb-drives-and-other-peripherals"></a>Impedire l'installazione e l'utilizzo di unità USB e altre periferiche

Se vuoi impedire l'installazione di una classe di dispositivi o di alcuni dispositivi, puoi usare i criteri impedisci l'installazione dei dispositivi:

1. Abilita **Impedisci l'installazione dei dispositivi che corrispondono a uno di** questi ID dispositivo e aggiungi questi dispositivi all'elenco.
2. Abilita **Impedisci l'installazione dei dispositivi usando driver che corrispondono a queste classi di configurazione dei dispositivi.**

> [!Note]
> I criteri impedisci l'installazione dei dispositivi hanno la precedenza sui criteri consenti l'installazione dei dispositivi.

Il **criterio** Impedisci l'installazione di dispositivi che corrispondono a uno di questi ID dispositivo consente di specificare un elenco di dispositivi a cui Windows non è consentita l'installazione. 

Per impedire l'installazione di dispositivi che corrispondono a uno di questi ID dispositivo: 

1. [Cerca l'ID](#look-up-device-id) del dispositivo per i dispositivi che Windows impedire l'installazione.

   ![Cercare l'ID del fornitore o del prodotto](images/lookup-vendor-product-id.png)

2. Abilita **Impedisci l'installazione** dei dispositivi che corrispondono a uno di questi ID dispositivo e aggiungi gli ID fornitore o prodotto all'elenco.

    ![Aggiungere l'ID fornitore per impedire l'elenco](images/add-vendor-id-to-prevent-list.png)

#### <a name="look-up-device-id"></a>Cercare l'ID dispositivo

Puoi usare Gestione dispositivi per cercare un ID dispositivo.

1. Aprire Gestione dispositivi.
2. Fare **clic su** Visualizza e selezionare Dispositivi per **connessione.**
3. Nell'albero fare clic con il pulsante destro del mouse sul dispositivo e scegliere **Proprietà.**
4. Nella finestra di dialogo del dispositivo selezionato fare clic sulla **scheda** Dettagli.
5. Fare clic **sull'elenco** a discesa Proprietà e selezionare **ID hardware.**
6. Fai clic con il pulsante destro del mouse sul valore ID superiore e scegli **Copia.**

Per informazioni sui formati di ID dispositivo, vedi [Identificatori USB standard.](/windows-hardware/drivers/install/standard-usb-identifiers)

Per informazioni sugli ID fornitore, vedere [Membri USB.](https://www.usb.org/members)

Di seguito è riportato un esempio per cercare un ID fornitore di dispositivo o un ID prodotto (che fa parte dell'ID del dispositivo) tramite PowerShell: 

```powershell
Get-WMIObject -Class Win32_DiskDrive |
Select-Object -Property * 
```

Il **criterio Impedisci** l'installazione di dispositivi che usano driver che corrispondono a queste classi di installazione dei dispositivi consente di specificare le classi di installazione dei dispositivi a cui Windows non è consentita l'installazione. 

Per impedire l'installazione di determinate classi di dispositivi: 

1. Trova il GUID della classe di installazione del dispositivo da Classi di installazione dispositivi definite dal sistema [disponibili per i fornitori.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)

2. Abilita **Impedisci l'installazione dei dispositivi usando driver che corrispondono a** queste classi di installazione dei dispositivi e aggiungi il GUID della classe all'elenco.

    > [!div class="mx-imgBorder"]
    > ![Aggiungere la classe di configurazione del dispositivo per impedire l'elenco](images/Add-device-setup-class-to-prevent-list.png)

### <a name="block-installation-and-usage-of-removable-storage"></a>Bloccare l'installazione e l'utilizzo dell'archiviazione rimovibile

1. Accedere all'interfaccia [Microsoft Endpoint Manager di amministrazione](https://endpoint.microsoft.com/).

2. Fare **clic su Profili** di configurazione  >  **dispositivi** Crea  >  **profilo**.

    > [!div class="mx-imgBorder"]
    > ![Creare un profilo di configurazione del dispositivo](images/create-device-configuration-profile.png)

3. Utilizzare le seguenti impostazioni:

   - Nome: digitare un nome per il profilo
   - Descrizione: digitare una descrizione
   - Piattaforma: Windows 10 e versioni successive
   - Tipo di profilo: Restrizioni del dispositivo

   > [!div class="mx-imgBorder"]
   > ![Creare un profilo](images/create-profile.png)

4. Fare **clic su Configura**  >  **generale**.  

5. Per **Archivi rimovibili** e **connessione USB (solo per dispositivi mobili)** scegliere **Blocca.** **L'archiviazione rimovibile** include unità USB, mentre la connessione **USB (solo** per dispositivi mobili) esclude la ricarica USB, ma include altre connessioni USB solo su dispositivi mobili. 

   ![Impostazioni generali](images/general-settings.png)

6. Fare **clic su OK** per chiudere **Impostazioni** generali e **Restrizioni dispositivo.**

7. Fare **clic su** Crea per salvare il profilo.

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals"></a>Consentire l'installazione e l'utilizzo di periferiche approvate in modo specifico

Le periferiche che possono essere installate possono essere specificate [dall'identità hardware.](/windows-hardware/drivers/install/device-identification-strings) Per un elenco delle strutture di identificatori comuni, vedere [Formati degli identificatori di dispositivo.](/windows-hardware/drivers/install/device-identifier-formats) Testare la configurazione prima della distribuzione per assicurarsi che blocchi e consenta i dispositivi previsti. Testare idealmente diverse istanze dell'hardware. Ad esempio, testare più chiavi USB anziché una sola.

Per un esempio SyncML che consente l'installazione di ID dispositivo specifici, vedi [CSP DeviceInstallation/AllowInstallationOfMatchingDeviceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids) Per consentire classi di dispositivi specifiche, vedi [CSP DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses)
Consentire l'installazione di dispositivi specifici richiede anche l'abilitazione di [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings)

### <a name="prevent-installation-of-specifically-prohibited-peripherals"></a>Impedire l'installazione di periferiche specificamente proibite

Microsoft Defender for Endpoint blocca l'installazione e l'utilizzo delle periferiche proibite utilizzando una delle opzioni seguenti:

- [I modelli amministrativi](/intune/administrative-templates-windows) possono bloccare qualsiasi dispositivo con un ID hardware o una classe di installazione corrispondente.  
- [Impostazioni CSP per l'installazione dei](/windows/client-management/mdm/policy-csp-deviceinstallation) dispositivi con un profilo personalizzato in Intune. Puoi impedire [l'installazione di ID dispositivo specifici](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) o impedire classi di dispositivi [specifiche.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses)

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids"></a>Consentire l'installazione e l'utilizzo di periferiche approvate in modo specifico con ID istanza dispositivo corrispondenti

Le periferiche che possono essere installate possono essere specificate dagli [ID istanza del dispositivo.](/windows-hardware/drivers/install/device-instance-ids) Testare la configurazione prima di implementazione per assicurarsi che consenta i dispositivi previsti. Testare idealmente diverse istanze dell'hardware. Ad esempio, testare più chiavi USB anziché una sola.

Puoi consentire l'installazione e l'uso di periferiche approvate con ID istanza dispositivo corrispondenti configurando l'impostazione dei criteri [DeviceInstallation/AllowInstallationOfMatchingDeviceInstanceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids)

### <a name="prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids"></a>Impedire l'installazione e l'utilizzo di periferiche specificamente proibite con ID istanza dispositivo corrispondenti

Le periferiche non consentite per l'installazione possono essere specificate dagli [ID istanza del dispositivo.](/windows-hardware/drivers/install/device-instance-ids) Testare la configurazione prima di implementazione per assicurarsi che consenta i dispositivi previsti. Testare idealmente diverse istanze dell'hardware. Ad esempio, testare più chiavi USB anziché una sola.

Puoi impedire l'installazione delle periferiche proibite con ID istanza dispositivo corrispondenti configurando l'impostazione dei criteri [DeviceInstallation/PreventInstallationOfMatchingDeviceInstanceIDs.](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids)

### <a name="limit-services-that-use-bluetooth"></a>Limitare i servizi che utilizzano Bluetooth

Usando Intune, puoi limitare i servizi che possono usare Bluetooth tramite [i "Bluetooth consentiti".](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) Lo stato predefinito delle impostazioni "Bluetooth servizi consentiti" indica che tutto è consentito.  Non appena viene aggiunto un servizio, questo diventa l'elenco di elementi consentiti. Se il cliente aggiunge i valori Keyboards e Mice e non aggiunge i GUID di trasferimento file, il trasferimento di file dovrebbe essere bloccato.

> [!div class="mx-imgBorder"]
> ![Screenshot della pagina Bluetooth impostazioni](images/bluetooth.png)

### <a name="use-microsoft-defender-for-endpoint-baseline-settings"></a>Usare Le impostazioni di base di Microsoft Defender per endpoint

Le impostazioni di base di Microsoft Defender for Endpoint rappresentano la configurazione consigliata per la protezione dalle minacce. Le impostazioni di configurazione per la linea di base si trovano nella pagina di modifica del profilo delle impostazioni di configurazione.

> [!div class="mx-imgBorder"]
> ![Linee di base in MEM](images/baselines.png)

## <a name="prevent-threats-from-removable-storage"></a>Impedire alle minacce di archivi rimovibili
  
I dispositivi di archiviazione rimovibili possono introdurre ulteriori rischi per la sicurezza per l'organizzazione. Microsoft Defender for Endpoint può aiutare a identificare e bloccare i file dannosi nei dispositivi di archiviazione rimovibili.

Microsoft Defender for Endpoint può anche impedire l'uso di periferiche USB nei dispositivi per evitare minacce esterne. A tale scopo, usa le proprietà segnalate dalle periferiche USB per determinare se possono essere installate e usate nel dispositivo.

Tieni presente che se blocchi dispositivi USB o altre classi di dispositivi usando i criteri di installazione dei dispositivi, i dispositivi connessi, ad esempio i telefoni, possono comunque caricarsi.

>[!NOTE]
>Testare e perfezionare sempre queste impostazioni con un gruppo pilota di utenti e dispositivi prima di distribuire ampiamente all'organizzazione. 

Nella tabella seguente vengono descritti i modi in cui Microsoft Defender for Endpoint può aiutare a prevenire le minacce dall'archiviazione rimovibile.

Per altre informazioni sul controllo dei dispositivi USB, vedi il [blog di Microsoft Defender for Endpoint.](https://aka.ms/devicecontrolblog)

| Controllo  | Descrizione |
|----------|-------------|
| [Abilitare Antivirus Microsoft Defender scansione](#enable-microsoft-defender-antivirus-scanning) | Abilitare Antivirus Microsoft Defender per la protezione in tempo reale o le analisi pianificate.|
| [Bloccare i processi non attendibili e non firmati nelle periferiche USB](#block-untrusted-and-unsigned-processes-on-usb-peripherals) | Bloccare i file USB non firmati o non attendibili. |
| [Protezione dagli attacchi DMA (Direct Memory Access)](#protect-against-direct-memory-access-dma-attacks) | Configurare le impostazioni per la protezione dagli attacchi DMA. |

>[!NOTE]
>Poiché una periferica USB non autorizzata può avere firmware che falsifica le proprietà USB, ti consigliamo di consentire solo periferiche USB approvate in modo specifico e limitare gli utenti che possono accedervi.

### <a name="enable-microsoft-defender-antivirus-scanning"></a>Abilitare Antivirus Microsoft Defender scansione

La protezione dell'archiviazione rimovibile [](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus) autorizzata con Antivirus Microsoft Defender richiede l'abilitazione della protezione in tempo reale o la pianificazione delle analisi e la configurazione delle unità rimovibili per le analisi.

- Se la protezione in tempo reale è abilitata, i file vengono analizzati prima dell'accesso e dell'esecuzione. L'ambito di analisi include tutti i file, inclusi quelli nei dispositivi rimovibili montati, ad esempio le unità USB. Facoltativamente, è possibile eseguire uno [script di PowerShell](/samples/browse/?redirectedfrom=TechNet-Gallery) per eseguire un'analisi personalizzata di un'unità USB dopo l'installazione, in modo che Antivirus Microsoft Defender inizi l'analisi di tutti i file su un dispositivo rimovibile dopo aver collegato il dispositivo rimovibile. Tuttavia, è consigliabile abilitare la protezione in tempo reale per migliorare le prestazioni di analisi, in particolare per i dispositivi di archiviazione di grandi dimensioni.

- Se vengono utilizzate analisi pianificate, è necessario disabilitare l'impostazione DisableRemovableDriveScanning (abilitata per impostazione predefinita) per analizzare il dispositivo rimovibile durante un'analisi completa. I dispositivi rimovibili vengono analizzati durante un'analisi rapida o personalizzata indipendentemente dall'impostazione DisableRemovableDriveScanning.

>[!NOTE]
>Ti consigliamo di abilitare il monitoraggio in tempo reale per l'analisi. In Intune, è possibile abilitare il monitoraggio in tempo reale per Windows 10 in **Restrizioni** dispositivo Configurare Antivirus Microsoft Defender  >    >    >  **monitoraggio in tempo reale**.

<!-- Need to build out point in the preceding note. 
-->

### <a name="block-untrusted-and-unsigned-processes-on-usb-peripherals"></a>Bloccare i processi non attendibili e non firmati nelle periferiche USB

Gli utenti finali potrebbero collegare dispositivi rimovibili infettati da malware.
Per evitare infezioni, una società può bloccare i file USB non firmati o non attendibili.
In alternativa, le aziende possono [](/microsoft-365/security/defender-endpoint/attack-surface-reduction) sfruttare la funzionalità di controllo delle regole di riduzione della superficie di attacco per monitorare l'attività di processi non attendibili e non firmati eseguiti su una periferica USB.
Questa operazione può essere eseguita impostando rispettivamente i processi non attendibili e non firmati eseguiti da **USB** su **Blocca** o **Controlla** solo.
Con questa regola, gli amministratori possono impedire o controllare l'esecuzione di file eseguibili non firmati o non attendibili da unità rimovibili USB, incluse le schede SD.
I tipi di file interessati includono file eseguibili (ad esempio .exe, .dll o scr) e file di script, ad esempio file di PowerShell (ps), VisualBasic (con estensione vbs) o JavaScript (.js).

Queste impostazioni richiedono [l'abilitazione della protezione in tempo reale.](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)

1. Accedere al Microsoft Endpoint Manager [.](https://endpoint.microsoft.com/)

2. Fare **clic su**  >  **Windows** Criteri di configurazione  >  **Crea**  >  **profilo**. 

    ![Creare un profilo di configurazione del dispositivo](images/create-device-configuration-profile.png)

3. Utilizzare le seguenti impostazioni:
   - Piattaforma: Windows 10 e versioni successive 
   - Tipo di profilo: Restrizioni del dispositivo

   > [!div class="mx-imgBorder"]
   > ![Creare il profilo di endpoint protection](images/create-endpoint-protection-profile.png)

4. Fare clic su **Crea**.  

5. Per Processi non firmati e non attendibili **eseguiti da USB,** scegliere **Blocca**.

   ![Bloccare processi non attendibili](images/block-untrusted-processes.png)

6. Fare **clic su OK** per chiudere le impostazioni e Le restrizioni del **dispositivo**.

### <a name="protect-against-direct-memory-access-dma-attacks"></a>Protezione dagli attacchi DMA (Direct Memory Access)

Gli attacchi DMA possono portare alla divulgazione di informazioni riservate che risiedono su un PC o persino all'inserimento di malware che consente agli utenti malintenzionati di ignorare la schermata di blocco o controllare i PC in remoto. Le impostazioni seguenti consentono di evitare attacchi DMA:

1. A partire dalla Windows 10 1803, Microsoft ha introdotto [kernel DMA Protection for Thunderbolt](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md) per fornire protezione nativa dagli attacchi DMA tramite porte Thunderbolt. Kernel DMA Protection for Thunderbolt è abilitato dai produttori di sistemi e non può essere attivato o disattivato dagli utenti.

   A partire Windows 10 versione 1809, è possibile regolare il livello di protezione DMA kernel configurando [il CSP DMA Guard.](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy) Si tratta di un controllo aggiuntivo per le periferiche che non supportano l'isolamento della memoria del dispositivo (noto anche come remapping DMA). L'isolamento della memoria consente al sistema operativo di sfruttare l'I/O Memory Management Unit (IOMMU) di un dispositivo per bloccare l'I/O non consentito o l'accesso alla memoria dalla periferica (sandboxing della memoria). In altre parole, il sistema operativo assegna un determinato intervallo di memoria alla periferica. Se la periferica tenta di leggere/scrivere in memoria al di fuori dell'intervallo assegnato, il sistema operativo la blocca.

   Le periferiche che supportano l'isolamento della memoria del dispositivo possono sempre connettersi. Periferiche che non possono essere bloccate, consentite o consentite solo dopo l'accesso dell'utente (impostazione predefinita).

2. Nei Windows 10 che non supportano Kernel DMA Protection, è possibile:

   - [Blocca DMA finché un utente non accede](/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)
   - [Bloccare tutte le connessioni tramite le porte Thunderbolt (inclusi i dispositivi USB)](https://support.microsoft.com/help/2516445/blocking-the-sbp-2-driver-and-thunderbolt-controllers-to-reduce-1394-d)

## <a name="create-customized-alerts-and-response-actions"></a>Creare avvisi e azioni di risposta personalizzati

È possibile creare avvisi e azioni di risposta personalizzati con il connettore WDATP e le regole di rilevamento personalizzate:

**Azioni di risposta del connettore Wdatp:**

**Analizzare:** Avviare indagini, raccogliere pacchetti di indagini e isolare un computer.

**Analisi delle minacce** nei dispositivi USB.

**Limitare** l'esecuzione di tutte le applicazioni nel computer, ad eccezione di un connettore MDATP predefinito impostato è uno degli oltre 200 connettori predefiniti, tra cui Outlook, Teams, Slack e così via. È possibile creare connettori personalizzati.
- [Ulteriori informazioni sulle azioni di risposta del connettore WDATP](/connectors/wdatp/)

**Azione di risposta alle regole di rilevamento personalizzate:** È possibile applicare azioni sia a livello di computer che a livello di file.
- [Ulteriori informazioni sulle azioni di risposta alle regole di rilevamento personalizzate](/microsoft-365/security/defender-endpoint/custom-detection-rules)

Per informazioni sugli eventi di ricerca avanzata correlati al controllo dei dispositivi ed esempi su come creare avvisi personalizzati, vedi Aggiornamenti di ricerca [avanzata: eventi USB,](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152)azioni a livello di computer e modifiche allo schema.

## <a name="respond-to-threats"></a>Rispondere alle minacce

Puoi creare avvisi personalizzati e azioni di risposta automatica con [Microsoft Defender for Endpoint Custom Detection Rules.](/microsoft-365/security/defender-endpoint/custom-detection-rules) Le azioni di risposta all'interno del rilevamento personalizzato riguardano sia le azioni a livello di computer che di file. Puoi anche creare avvisi e azioni di risposta automatica usando [PowerApps](https://powerapps.microsoft.com/) [e Flow](https://flow.microsoft.com/) con [il connettore Microsoft Defender for Endpoint.](/connectors/wdatp/) Il connettore supporta azioni per l'indagine, l'analisi delle minacce e la limitazione delle applicazioni in esecuzione. Si tratta di uno degli oltre 200 connettori predefiniti, tra cui Outlook, Teams, Slack e altro ancora. È inoltre possibile creare connettori personalizzati. Per [ulteriori informazioni sui](/connectors/) connettori, vedere Connectors.
 
Ad esempio, usando entrambi gli approcci, puoi fare in modo che l'Antivirus Microsoft Defender quando un dispositivo USB viene montato su un computer.

## <a name="related-topics"></a>Argomenti correlati

- [Configurare la protezione in tempo reale per Antivirus Microsoft Defender](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
- [Defender/AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)
- [Policy/DeviceInstallation CSP](/windows/client-management/mdm/policy-csp-deviceinstallation)
- [Eseguire un'analisi personalizzata di un dispositivo rimovibile](/samples/browse/?redirectedfrom=TechNet-Gallery)
- [Modello PowerBI di Controllo dispositivo per la creazione di report personalizzati](https://github.com/microsoft/MDATP-PowerBI-Templates)
- [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) 
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure.md)
