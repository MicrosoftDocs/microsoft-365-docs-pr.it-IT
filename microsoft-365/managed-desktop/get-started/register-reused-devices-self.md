---
title: Registrare manualmente i dispositivi già presenti
description: Registrare i dispositivi riutilizzati che potresti già avere in modo che possano essere gestiti da Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f2b3e109493331a4b63d669501525a48cb996809
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689222"
---
# <a name="register-existing-devices-yourself"></a>Registrare manualmente i dispositivi già presenti

>[!NOTE]
>In questo argomento vengono descritti i passaggi necessari per riutilizzare i dispositivi già presenti e registrarli in Microsoft Managed Desktop. Se stai lavorando con dispositivi nuovi, segui i passaggi descritti in Registrare i [nuovi dispositivi in Microsoft Managed Desktop.](register-devices-self.md)

Il processo per i partner è documentato in [Passaggi per i partner per registrare i dispositivi](register-devices-partner.md).

Microsoft Managed Desktop può funzionare con dispositivi nuovi o puoi riutilizzare i dispositivi che potresti già avere (che richiederanno di ricrearne l'immagine). Puoi registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.

## <a name="prepare-to-register-existing-devices"></a>Preparare la registrazione dei dispositivi esistenti


Per registrare i dispositivi esistenti, segui questi passaggi:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapita il dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili quattro opzioni per ottenere queste informazioni dai dispositivi già in uso:

- Chiedere al fornitore OEM il file di registrazione AutoPilot, che includerà gli hash hardware.
- Raccogliere informazioni in [Microsoft Endpoint Configuration Manager.](#microsoft-endpoint-configuration-manager)
- Eseguire uno script Windows PowerShell, utilizzando [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) in ogni dispositivo, e raccogliere i risultati in un file.
- Avviare ogni dispositivo, ma non completare l'esperienza di installazione di Windows, e raccogliere gli [hash in un'unità flash rimovibile.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Puoi usare Microsoft Endpoint Configuration Manager per raccogliere gli hash hardware dai dispositivi esistenti che vuoi registrare con Microsoft Managed Desktop.

> [!IMPORTANT]
> Tutti i dispositivi per cui vuoi ottenere queste informazioni devono eseguire Windows 10 versione 1703 o successiva. 

Se sono stati soddisfatti tutti questi prerequisiti, è possibile raccogliere le informazioni seguendo questi passaggi:

1. Nella console di Configuration Manager selezionare **Monitoraggio**. 
2. Nell'area di lavoro Monitoraggio espandere il **nodo Report,** espandere **Report** e selezionare il **nodo Hardware - Generale.** 
3. Eseguire il report, **Windows Autopilot Device Information** e visualizzare i risultati.
4. Nel visualizzatore di report seleziona **l'icona** Esporta e scegli l'opzione **CSV (delimitato da virgole).**
5. Dopo aver salvato il file, sarà necessario filtrare i risultati solo nei dispositivi che si prevede di registrare in Microsoft Managed Desktop e caricare i dati in Microsoft Managed Desktop. Apri Microsoft Endpoint Manager e passa al menu **Dispositivi,** quindi cerca la sezione Microsoft Managed Desktop e seleziona **Dispositivi**. Seleziona **+ Registra dispositivi**, che apre un fly-in per registrare nuovi dispositivi.


Per altre [informazioni, vedere Registrare i dispositivi](#register-devices-by-using-the-admin-portal) tramite il portale di amministrazione.


#### <a name="active-directory-powershell-script-method"></a>Metodo script di PowerShell di Active Directory

In un ambiente Active Directory, è possibile utilizzare il cmdlet PowerShell per raccogliere in remoto le informazioni dai dispositivi nei gruppi di `Get-WindowsAutoPilotInfo` Active Directory tramite WinRM. È inoltre possibile utilizzare il `Get-AD Computer` cmdlet e ottenere risultati filtrati per un nome di modello hardware specifico incluso nel catalogo. Prima di procedere, verificare prima questi prerequisiti e quindi procedere con i passaggi seguenti:

- WinRM è abilitato.
- I dispositivi da registrare sono attivi nella rete, ovvero non sono disconnessi o disattivati.
- Assicurati di disporre di un parametro delle credenziali di dominio che dispone dell'autorizzazione per l'esecuzione in remoto nei dispositivi.
- Assicurarsi che Windows Firewall consenta l'accesso a WMI. A tale scopo, attenersi alla seguente procedura:

    1. Apri il **Windows Defender di controllo firewall** e seleziona Consenti **un'app** o una funzionalità tramite Windows Defender Firewall .
    
    2. Trova **Strumentazione gestione Windows (WMI)** nell'elenco, abilita sia per **Private che per Public** e quindi seleziona **OK.**

1.  Aprire un prompt di PowerShell con diritti amministrativi.

2.  Eseguire *uno di* questi script:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Accedere a tutte le directory in cui potrebbero essere presenti voci per i dispositivi. Rimuovere le voci per ogni dispositivo da *tutte le* directory, inclusi Servizi di dominio Active Directory di Windows Server e Azure Active Directory. Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.

4. Accedere ai servizi di gestione in cui potrebbero essere presenti voci per i dispositivi. Rimuovi le voci per ogni dispositivo da *tutti i* servizi di gestione, tra cui Microsoft Endpoint Configuration Manager, Microsoft Intune e Windows Autopilot. Tenere presente che l'elaborazione completa della rimozione potrebbe richiedere alcune ore.

Ora puoi procedere con la [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Metodo di script manuale di PowerShell

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Unire i dati hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive, metodo

1. In un dispositivo diverso da quello che stai registrando, inserisci un'unità USB.
2. Aprire un prompt di PowerShell con diritti amministrativi.
3. Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione.* Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare l'immagine del dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC + F10.
6. Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguire `cd <pathToUsb>` .
7. Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`
10. [Unire i dati hash.](#merge-hash-data)

>[!IMPORTANT]
>Non alimentare il dispositivo che stai registrando di nuovo finché non hai completato la registrazione. 



### <a name="merge-hash-data"></a>Unire dati hash

Se i dati hash hardware sono stati raccolti tramite i metodi manuali di PowerShell o dell'unità flash, è ora necessario che i dati nei file CSV si unino in un unico file per completare la registrazione. Ecco uno script di PowerShell di esempio per semplificare:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Con i dati hash uniti in un unico file CSV, ora puoi procedere alla [registrazione dei dispositivi](#register-devices-by-using-the-admin-portal).


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)seleziona Dispositivi **nel** riquadro di spostamento a sinistra. Cerca la sezione Microsoft Managed Desktop del menu e seleziona **Dispositivi.** Nell'area di lavoro Dispositivi desktop gestiti Microsoft seleziona **+ Registra dispositivi**, che apre un riquadro a comparsa per registrare nuovi dispositivi.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Eseguire la procedura seguente:

1. In **Caricamento file** specificare il percorso del file CSV creato in precedenza.
2. Seleziona un [profilo di](../service-description/profiles.md) dispositivo nel menu a discesa.
3. Selezionare **Registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco dei dispositivi nel **pannello Dispositivi,** contrassegnati come **Registrazione in sospeso.** La registrazione in genere richiede meno di 10 minuti e quando il dispositivo ha esito positivo il dispositivo viene visualizzato come **Pronto** per l'utente, ovvero è pronto e in attesa che un utente inizi a usare.

> [!NOTE]
> Se si modifica manualmente l'appartenenza al gruppo di Azure Active Directory (AAD) di un dispositivo, questo verrà automaticamente riassegnato al gruppo per il profilo del dispositivo e rimosso da eventuali gruppi in conflitto.

Puoi monitorare l'avanzamento della registrazione del dispositivo nella pagina principale. Tra i possibili stati segnalati vi sono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata eseguita. Eseguire il check back in un secondo momento. |
| Registrazione non riuscita | Impossibile completare la registrazione. Per ulteriori [informazioni, vedere Risoluzione dei](#troubleshooting-device-registration) problemi di registrazione dei dispositivi. |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente. Microsoft Managed Desktop li guiderà nella configurazione della prima volta, quindi non è necessario eseguire ulteriori operazioni di preparazione. |
| Attivo | Il dispositivo è stato recapitato all'utente e si è registrato nel tenant. Questo indica anche che usano regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente e si è registrato nel tenant. Tuttavia, non hanno usato il dispositivo di recente (negli ultimi 7 giorni).  | 

#### <a name="troubleshooting-device-registration"></a>Risoluzione dei problemi di registrazione dei dispositivi

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare questo dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Conferma questi valori con il fornitore del dispositivo. |
| Hash hardware non valido | L'hash hardware specificato per questo dispositivo non è stato formattato correttamente. Controlla due volte l'hash hardware e quindi invia di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo richiesto da un'altra organizzazione | Questo dispositivo è già stato rivendicato da un'altra organizzazione. Rivolgersi al fornitore del dispositivo. |
| Errore imprevisto | Impossibile elaborare automaticamente la richiesta. Contattare il supporto tecnico e fornire l'ID richiesta: <requestId> |

### <a name="check-the-image"></a>Controllare l'immagine

Se il dispositivo è stato utilizzato da un fornitore di partner Microsoft Managed Desktop, l'immagine deve essere corretta.

Se preferisci, puoi anche applicare l'immagine da solo. To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="deliver-the-device"></a>Recapita il dispositivo

> [!IMPORTANT]
> Prima di consegnare il dispositivo all'utente, assicurati di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per tale utente.

Se vengono applicate tutte le licenze, puoi ottenere gli utenti pronti per l'uso dei dispositivi [e](get-started-devices.md)quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.









