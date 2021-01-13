---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potrebbero essere già disponibili in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840516"
---
# <a name="register-existing-devices-yourself"></a>Registrare manualmente i dispositivi già presenti

>[!NOTE]
>In questo argomento vengono descritti i passaggi necessari per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop. Se si utilizzano dispositivi nuovi di zecca, eseguire i passaggi descritti in [registrare i nuovi dispositivi in Microsoft Managed Desktop](register-devices-self.md) .

Il processo per i partner è documentato nei [passaggi per i partner per la registrazione dei dispositivi](register-devices-partner.md).

Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi già presenti (che richiedono di rivisualizzarli). È possibile registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.

## <a name="prepare-to-register-existing-devices"></a>Preparare la registrazione di dispositivi esistenti


Per registrare i dispositivi esistenti, eseguire la procedura seguente:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapito del dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi che si stanno già usando:

- Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.
- Raccogliere informazioni in [Microsoft endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Eseguire uno script di Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) su ogni dispositivo, e raccogliere i risultati in un file.
- Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

È possibile utilizzare Gestione configurazione endpoint Microsoft per raccogliere gli hash hardware dai dispositivi esistenti che si desidera registrare con Microsoft Managed Desktop.

> [!IMPORTANT]
> Tutti i dispositivi per i quali si desidera ottenere queste informazioni devono essere in esecuzione Windows 10, versione 1703 o successiva. 

Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni attenendosi alla procedura seguente:

1. Nella console di Configuration Manager, selezionare **monitoraggio**. 
2. Nell'area di lavoro Monitoraggio espandere il nodo **report** , espandere **report** e selezionare il nodo **hardware-generale** . 
3. Eseguire il report, le **informazioni sul dispositivo Autopilot di Windows** e visualizzare i risultati.
4. Nel Visualizzatore di report selezionare l'icona **Esporta** e scegliere l'opzione **CSV (delimitato da virgole)** .
5. Dopo aver salvato il file, è necessario filtrare i risultati in base ai soli dispositivi che si intende registrare con Microsoft Managed Desktop e caricare i dati in Microsoft Managed Desktop. Aprire Microsoft Endpoint Manager e passare al menu **dispositivi** , quindi cercare la sezione Microsoft Managed Desktop e selezionare **dispositivi**. Selezionare **+ registra dispositivi**, che consente di aprire un Fly-in per registrare i nuovi dispositivi.


Per ulteriori informazioni, vedere [registrazione dei dispositivi tramite il portale di amministrazione](#register-devices-by-using-the-admin-portal) .


#### <a name="active-directory-powershell-script-method"></a>Metodo script di PowerShell di Active Directory

In un ambiente Active Directory, è possibile utilizzare il `Get-WindowsAutoPilotInfo` cmdlet di PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di Active Directory tramite WinRM. È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere i risultati filtrati per uno specifico nome di modello hardware incluso nel catalogo. Prima di procedere, confermare i prerequisiti e quindi procedere come segue:

- Gestione remota Windows è abilitata.
- I dispositivi che si desidera registrare sono attivi sulla rete (ovvero non sono disconnessi o disattivati).
- Verificare di disporre di un parametro di credenziali di dominio che disponga dell'autorizzazione per l'esecuzione remota sui dispositivi.
- Verificare che Windows Firewall consenta l'accesso a WMI. A tale scopo, eseguire la procedura seguente:

    1. Aprire il pannello di controllo di **Windows Defender Firewall** e selezionare **Consenti un'app o una funzionalità tramite il firewall di Windows Defender**.
    
    2. Individuare **Windows Management Instrumentation (WMI)** nell'elenco, abilitare sia per il **privato che** per il pubblico, quindi selezionare **OK**.

1.  Aprire un prompt di PowerShell con diritti amministrativi.

2.  Eseguire *uno* di questi script:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Accedere a tutte le directory in cui possono essere presenti voci per i dispositivi. Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi i servizi di dominio di Windows Server Active Directory e Azure Active Directory. Tenere presente che la rimozione potrebbe richiedere alcune ore per elaborarla completamente.

4. Servizi di gestione accessi in cui possono essere presenti voci per i dispositivi. Rimuovere le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft endpoint Configuration Manager, Microsoft Intune e Windows Autopilot. Tenere presente che la rimozione potrebbe richiedere alcune ore per elaborarla completamente.

A questo punto è possibile procedere alla [registrazione di dispositivi](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Metodo script di PowerShell manuale

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Unire i dati hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Metodo dell'unità flash

1. In un dispositivo diverso da quello che si sta registrando, inserire un'unità USB.
2. Aprire un prompt di PowerShell con diritti amministrativi.
3. Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione*. Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC + F10.
6. Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>` .
7. Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`
10. [Unire i dati hash.](#merge-hash-data)

>[!IMPORTANT]
>Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione. 



### <a name="merge-hash-data"></a>Unire i dati hash

Se i dati dell'hash hardware sono stati raccolti tramite i metodi di PowerShell manuale o di unità flash, è necessario che i dati dei file CSV siano combinati in un unico file per completare la registrazione. Di seguito è indicato uno script PowerShell di esempio per agevolare le operazioni seguenti:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Con i dati hash Uniti in un unico file CSV, è ora possibile procedere alla [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)selezionare **dispositivi** nel riquadro di spostamento a sinistra. Cercare la sezione Microsoft Managed Desktop del menu e selezionare **dispositivi**. Nell'area di lavoro Microsoft Managed Desktop Devices selezionare **+ Register Devices**, che consente di aprire un Fly-in per registrare i nuovi dispositivi.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


attenersi alla seguente procedura:

1. In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.

1. Selezionare **registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**. La registrazione richiede in genere meno di 10 minuti e, in caso di esito positivo, il dispositivo verrà visualizzato come **pronto per il significato dell'utente** è pronto e in attesa che un utente inizi a utilizzare.


È possibile monitorare lo stato di avanzamento della registrazione dei dispositivi nella pagina principale. Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata completata. Controllare in un secondo momento. |
| Registrazione non riuscita | La registrazione non è stata completata. Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](#troubleshooting-device-registration) . |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente. Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi. |
| Attivazione | Il dispositivo è stato recapitato all'utente ed è stato registrato con il tenant. Questo indica anche che stanno usando regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente ed è stato registrato con il tenant. Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).  | 

#### <a name="troubleshooting-device-registration"></a>Risoluzione dei problemi relativi alla registrazione del dispositivo

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Confermare questi valori con il fornitore del dispositivo. |
| Hash hardware non valido | L'hash hardware fornito per il dispositivo non è stato formattato correttamente. Fare doppio check sull'hash hardware e quindi inviare di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo rivendicato da un'altra organizzazione | Questo dispositivo è già stato rivendicato da un'altra organizzazione. Controllare con il fornitore del dispositivo. |
| Errore imprevisto | La richiesta non è stata elaborata automaticamente. Contattare il supporto tecnico e fornire l'ID richiesta: <requestId> |

### <a name="check-the-image"></a>Controllare l'immagine

Se il dispositivo proviene da un fornitore di partner di Microsoft Managed Desktop, è necessario che l'immagine sia corretta.

Se si preferisce, è anche possibile applicare l'immagine da soli. Per iniziare, contattare il rappresentante Microsoft che si sta utilizzando e fornirà la posizione e i passaggi per l'applicazione dell'immagine.

### <a name="deliver-the-device"></a>Recapito del dispositivo

> [!IMPORTANT]
> Prima di distribuire il dispositivo all'utente, verificare di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per l'utente.

Se vengono applicate tutte le licenze, è possibile [ottenere gli utenti pronti per l'utilizzo dei dispositivi](get-started-devices.md)e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.









