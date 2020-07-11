---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potrebbero essere già disponibili in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101486"
---
# <a name="register-existing-devices-yourself"></a>Registrare manualmente i dispositivi già presenti

>[!NOTE]
>In questo argomento vengono illustrati i passaggi da eseguire per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop. Se si utilizzano dispositivi nuovi di zecca, eseguire i passaggi descritti in [registrare i nuovi dispositivi in Microsoft Managed Desktop](register-devices-self.md) .

Il processo per i partner è documentato nei [passaggi per i partner per la registrazione dei dispositivi](register-devices-partner.md).

Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi che potrebbero essere già presenti (il che richiede che vengano ristampati). È possibile registrare i dispositivi tramite il portale di amministrazione di Microsoft Managed Desktop.

## <a name="prepare-to-register-existing-devices"></a>Preparare la registrazione di dispositivi esistenti


Per registrare i dispositivi esistenti, eseguire la procedura seguente:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop](#register-devices).
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapito del dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi che si stanno già usando:

- Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.
- Creare un report personalizzato in [Configuration Manager](#configuration-manager).
- Eseguire uno script di Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) su ogni dispositivo, e raccogliere i risultati in un file.
- Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).

#### <a name="configuration-manager"></a>Configuration Manager

È possibile utilizzare Gestione configurazione endpoint Microsoft per raccogliere gli hash hardware dai dispositivi esistenti che si desidera registrare con Microsoft Managed Desktop.

> [!IMPORTANT]
> Tutti i dispositivi per i quali si desidera ottenere queste informazioni devono essere in esecuzione Windows 10, versione 1703 o successiva. È inoltre necessario un dispositivo che sia un client di Configuration Manager connesso al sito Gestione configurazione (succursale corrente). È inoltre necessario impostare il ruolo di sistema dei siti di Reporting Point configurato nell'ambiente in cui è abilitato SQL Server Reporting Services. 

Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni attenendosi alla procedura seguente:

1. Nella console di Configuration Manager, selezionare **monitoraggio**. 
2. Nell'area di lavoro Monitoraggio espandere **report**e quindi selezionare **report**. 
3. Nella sezione **Crea** della scheda **Home** selezionare **Crea rapporto** per aprire la creazione guidata report. 
4. Nella pagina delle **informazioni** , impostare le seguenti impostazioni: 
    - **Nome:** Specificare un nome per il report. 
    - **Descrizione:** Specificare una descrizione per il report. 
    - **Server:** Visualizza il nome del server di report in cui si sta creando il report. 
    - **Percorso:** Selezionare **Sfoglia** per specificare una cartella nella quale si desidera archiviare il report. 
5. Selezionare **Avanti**. 
6. Nella pagina **Riepilogo** , esaminare le impostazioni. Selezionare **Previous** per modificare le impostazioni oppure fare clic su **Avanti** per creare il report in Configuration Manager. 
7. Nella pagina **completamento** , selezionare **Chiudi** per uscire dalla procedura guidata e aprire **Generatore report** per immettere le impostazioni del report. Immettere l'account utente e la password, se richiesto, quindi selezionare **OK.** Se il generatore di report non è installato nel dispositivo, viene richiesto di installarlo. Selezionare **Esegui per installare Generatore di report**, necessario per modificare e creare report. 


**In Microsoft Report Builder**fornire l'istruzione SQL per il report e attenersi alla seguente procedura:

1. Nel riquadro a sinistra, selezionare **set**di dati, quindi fare clic con il pulsante destro del mouse per **aggiungere un oggetto DataSet**.
2. Passare alla scheda **query** e quindi immettere il nome come *DataSet0*. 
3. Selezionare **utilizza un set di dati incorporato nel report**. Verrà aperto generatore di report.
4. In **Generatore report**selezionare **origine dati:**. Selezionare l'origine dati predefinita, che dovrebbe iniziare con "AutoGen". 
5. Scegliere **tipo di query come testo**e quindi immettere la query seguente:




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. Passare alla scheda **campo** , i valori wehre per il **nome del campo** e l' **origine campo** devono essere già inseriti. Se non lo sono, fare clic su **Aggiungi**, quindi selezionare **campo query**. Immettere il **nome del campo** e l' **origine del campo**.
6. Ripetere questa procedura per ognuno di questi valori: 
    - Produttore 
    - Modello 
    - Serial_Number 
    - HardwareHash
7. Selezionare **OK**.

**Successivamente, definire la visualizzazione del report e creare il report** attenendosi alla procedura seguente:

1. Selezionare **tabella o matrice**; verrà aperta una nuova procedura guidata.
2. In **Scegli un set di dati**, selezionare **Scegli un set di dati esistente nel rapporto o un set**di dati condiviso.  
3. Selezionare **DataSet0** (impostazione predefinita) e quindi fare clic su **Avanti**.
4. Trascinare il **produttore**, il **modello**e il **numero di serie** nella casella gruppi di **righe** . Trascinare **HardwareHash** nella casella **valori** e quindi fare clic su **Avanti**.
5. Cancellare le caselle di controllo per **Mostra i subtotali e i totali** complessivi e i **gruppi Espandi/Comprimi**. Selezionare **Avanti**.
6. Select **Finish**.
7. Selezionare **Esegui** per eseguire il report. Verificare che nel report siano disponibili le informazioni prevedibili. Se necessario, selezionare **progetta** per tornare alla visualizzazione struttura per modificare il report.
8. Fare clic su **Salva** per salvare il report nel server di report. È possibile eseguire il nuovo rapporto nel nodo rapporti nell'area di lavoro di monitoraggio. 

**Infine, esportare il report e utilizzarlo per registrare i dispositivi** attenendosi alla procedura seguente. (È necessario seguire i passaggi 1 e 2 di questa sezione se si è passati dopo i passaggi precedenti):

1. Nella console di Configuration Manager, selezionare **monitoraggio**.
2. In **monitoraggio**, espandere **report**e quindi fare clic su **report**.
3. Trovare il report utilizzando il nome creato in precedenza.
4. Fare clic con il pulsante destro del mouse su questo report e scegliere **Esegui**.
5. Nella finestra di dialogo visualizzata, selezionare **Esporta** e quindi fare clic su **Salva come CSV**.
6. Questa versione del report estrae gli hash da tutti i dispositivi Windows 10 a cui comunica Gestione configurazione. Sarà necessario filtrare i risultati in base ai soli dispositivi che si intende registrare con Microsoft Managed Desktop.


> [!IMPORTANT]
> La query in Configuration Manager non consente l'esecuzione di spazi nei nomi di colonna esportati. Questo è il motivo per cui i passaggi sono stati immessi "Serial_Number" e "HardwareHash". Dopo aver esportato il file CSV, è necessario modificare le intestazioni dei rapporti per leggere il *numero di serie* e l' *hash hardware* come illustrato di seguito prima di procedere con la registrazione dei dispositivi.

A questo punto è possibile procedere alla [registrazione dei dispositivi tramite il portale di amministrazione](#register-devices-by-using-the-admin-portal).


#### <a name="active-directory-powershell-script-method"></a>Metodo script di PowerShell di Active Directory

In un ambiente Active Directory, è possibile utilizzare il `Get-MMDRegistrationInfo` cmdlet di PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di Active Directory tramite WinRM. È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere i risultati filtrati per uno specifico nome di modello hardware incluso nel catalogo. A tale scopo, prima di tutto confermare questi prerequisiti e quindi procedere come segue:

- Gestione remota Windows è abilitata.
- I dispositivi che si desidera registrare sono attivi sulla rete (ovvero non sono disconnessi o disattivati).
- Verificare di disporre di un parametro di credenziali di dominio che disponga dell'autorizzazione per l'esecuzione remota sui dispositivi.
- Verificare che Windows Firewall consenta l'accesso a WMI. A tale scopo, eseguire la procedura seguente:
    1. Aprire il pannello di controllo di **Windows Defender Firewall** e selezionare **Consenti un'app o una funzionalità tramite il firewall di Windows Defender**.
    2. Individuare **Windows Management Instrumentation (WMI)** nell'elenco, abilitare sia per il **privato che**per il pubblico, quindi selezionare **OK**.

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Eseguire *uno* di questi script:
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. Accedere a tutte le directory in cui possono essere presenti voci per i dispositivi. Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi i servizi di dominio di Windows Server Active Directory e Azure Active Directory. Tenere presente che questa rimozione potrebbe richiedere alcune ore per elaborarla completamente.
4. Servizi di gestione accessi in cui possono essere presenti voci per i dispositivi. Rimuovere le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft endpoint Configuration Manager, Microsoft Intune e Windows Autopilot. Tenere presente che questa rimozione potrebbe richiedere alcune ore per elaborarla completamente.

A questo punto è possibile procedere alla [registrazione di dispositivi](#register-devices).

#### <a name="manual-powershell-script-method"></a>Metodo script di PowerShell manuale

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre`Install-Script -Name Get-MMDRegistrationInfo`
3.  Correre`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Unire i dati hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Metodo dell'unità flash

1. In un dispositivo diverso da quello che si sta registrando, inserire un'unità USB.
2. Aprire un prompt di PowerShell con diritti amministrativi.
3. Correre`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione*. Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC + F10.
6. Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>` .
7. Correre`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo`shutdown -s -t 0`
10. [Unire i dati hash.](#merge-hash-data)

>[!IMPORTANT]
>Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione. 



### <a name="merge-hash-data"></a>Unire i dati hash

Se i dati dell'hash hardware sono stati raccolti tramite i metodi di PowerShell manuale o di unità flash, è necessario che i dati dei file CSV siano combinati in un unico file per completare la registrazione. Di seguito è indicato uno script di PowerShell di esempio per semplificare le operazioni seguenti:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

Con i dati hash Uniti in un unico file CSV, è ora possibile procedere alla [registrazione dei dispositivi](#register-devices).

### <a name="register-devices"></a>Registrare i dispositivi

Il file CSV deve trovarsi in un formato specifico per la registrazione. Se i dati sono stati raccolti nei passaggi precedenti, il file deve essere già nel formato corretto. Se si ottiene il file da un fornitore, potrebbe essere necessario modificare il formato.

>[!NOTE]
>Per comodità, è possibile scaricare un [modello](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) per questo file CSV.

Il file deve includere le **intestazioni di colonna** identiche a quelle del campione (produttore, modello e così via), ma i propri dati per le altre righe. Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio Blocco note, e considerare di lasciare tutti i dati solo nella riga 1, immettendo solo i dati nelle righe 2 e seguenti. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Se si dimentica di modificare i dati di esempio, la registrazione avrà esito negativo.

#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

Dal [portale di amministrazione](https://aka.ms/mmdportal)di Microsoft Managed Desktop, selezionare **dispositivi** nel riquadro di spostamento a sinistra. Selezionare **+ registra dispositivi**; verrà aperto il volo:

[![Fly-in dopo aver selezionato i dispositivi di registrazione, elencare i dispositivi con colonne per gli utenti assegnati, il numero di serie, lo stato, la data dell'ultima visualizzazione e l'età](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Purtroppo questo non è vero. È possibile rimuovere questa nota, lasciandola adesso fino a quando non avremo la possibilità di chattare.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Eseguire la procedura seguente:

1. In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.
2. Facoltativamente, è possibile aggiungere un **ID ordine** o un **ID acquisto** per i propri scopi di verifica. Non sono presenti requisiti di formato per questi valori.
3. Selezionare **registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**. La registrazione richiede in genere meno di 10 minuti e, quando il dispositivo verrà visualizzato come **pronto per il significato dell'utente** , è pronto e in attesa che l'utente finale inizi a utilizzare.


È possibile monitorare lo stato di registrazione dei dispositivi nella pagina principale di **Microsoft Managed Desktop-Devices** . Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata completata. Controllare in un secondo momento. |
| Registrazione non riuscita | La registrazione non è stata completata. Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](#troubleshooting-device-registration) . |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente finale. Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi. |
| Attivazione | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Questo indica anche che stanno usando regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).  | 

#### <a name="troubleshooting-device-registration"></a>Risoluzione dei problemi relativi alla registrazione del dispositivo

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Confermare questi valori con il fornitore del dispositivo. |
| Hash hardware non valido | L'hash hardware fornito per il dispositivo non è stato formattato correttamente. Fare doppio check sull'hash hardware e quindi inviare di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo rivendicato da un'altra organizzazione | Questo dispositivo è già stato rivendicato da un'altra organizzazione. Controllare con il fornitore del dispositivo. |
| Errore imprevisto | La richiesta non è stata elaborata automaticamente. Contattare il supporto tecnico e fornire l'ID richiesta:<requestId> |

### <a name="check-the-image"></a>Controllare l'immagine

Se il dispositivo proviene da un fornitore di partner di Microsoft Managed Desktop, è necessario che l'immagine sia corretta.

Se si preferisce, è anche possibile applicare l'immagine da soli. Per iniziare, contattare il rappresentante Microsoft che si sta utilizzando e fornirà la posizione e i passaggi per l'applicazione dell'immagine.

### <a name="deliver-the-device"></a>Recapito del dispositivo

> [!IMPORTANT]
> Prima di distribuire il dispositivo all'utente, verificare di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per l'utente.

Se vengono applicate tutte le licenze, è possibile [ottenere gli utenti pronti per l'utilizzo dei dispositivi](get-started-devices.md)e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.









