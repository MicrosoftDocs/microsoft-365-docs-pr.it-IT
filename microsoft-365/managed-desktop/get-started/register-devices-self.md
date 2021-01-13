---
title: Registrare manualmente i nuovi dispositivi
description: Registrare i dispositivi da soli in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840682"
---
# <a name="register-new-devices-yourself"></a>Registrare manualmente i nuovi dispositivi

Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi già presenti (che richiedono di rivisualizzarli). È possibile registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.

> [!NOTE]
> Utilizzo di un partner per ottenere i dispositivi In caso affermativo, non è necessario preoccuparsi di ottenere gli hash hardware; si occuperà di questo per voi. Assicurarsi che il partner stabilisca una relazione con l'utente al [centro partner](https://partner.microsoft.com/dashboard). Il partner può ottenere ulteriori informazioni nella [Guida di partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Una volta che questa relazione è stata stabilita, il partner registrerà semplicemente i dispositivi per conto dell'utente: nessuna ulteriore azione necessaria. Se si desidera visualizzare i dettagli o il proprio partner ha domande, vedere la [procedura per i partner per la registrazione dei dispositivi](register-devices-partner.md). Dopo la registrazione dei dispositivi, è possibile procedere con la [Verifica dell'immagine](#check-the-image) e [la distribuzione dei dispositivi](#deliver-the-device) agli utenti.

## <a name="prepare-to-register-brand-new-devices"></a>Preparare la registrazione di dispositivi nuovi di zecca


Una volta che i nuovi dispositivi sono disponibili, è necessario eseguire la procedura seguente:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapito del dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili tre opzioni per ottenere queste informazioni:

- Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.
- Eseguire uno [script di Windows PowerShell](#powershell-script-method) su ogni dispositivo e raccogliere i risultati in un file.
- Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).

#### <a name="powershell-script-method"></a>Metodo script di PowerShell

È possibile utilizzare lo script di PowerShell [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) nel sito Web della raccolta di PowerShell. Per ulteriori informazioni sull'identificazione dei dispositivi e sull'hash hardware, vedere [aggiunta di dispositivi a Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Eseguire `powershell -ExecutionPolicy restricted` per impedire l'esecuzione di script successivi senza restrizioni.


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

>[!IMPORTANT]
>Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione. 


### <a name="merge-hash-data"></a>Unire i dati hash

Per completare la registrazione, è necessario che i dati dei file CSV siano combinati in un unico file. Di seguito è indicato uno script PowerShell di esempio per agevolare le operazioni seguenti:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)selezionare **dispositivi** nel riquadro di spostamento a sinistra. Cercare la sezione Microsoft Managed Desktop del menu e selezionare **dispositivi**. Nell'area di lavoro Microsoft Managed Desktop Devices selezionare **+ Register Devices**, che consente di aprire un Fly-in per registrare i nuovi dispositivi.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


attenersi alla seguente procedura:

1. In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.
3. Selezionare **registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco dei dispositivi sui **dispositivi**, contrassegnati come **registrazione in sospeso**. La registrazione richiede in genere meno di 10 minuti e, in caso di esito positivo, il dispositivo verrà visualizzato come **pronto per il significato dell'utente** è pronto e in attesa che un utente inizi a utilizzare.


È possibile monitorare lo stato di avanzamento della registrazione dei dispositivi nella pagina principale. Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata completata. Controllare in un secondo momento. |
| Registrazione non riuscita | La registrazione non è stata completata. Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](#troubleshooting-device-registration) . |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente. Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi. |
| Attivazione | Il dispositivo è stato recapitato all'utente ed è stato registrato con il tenant. Questo stato indica anche che stanno usando regolarmente il dispositivo. |
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





