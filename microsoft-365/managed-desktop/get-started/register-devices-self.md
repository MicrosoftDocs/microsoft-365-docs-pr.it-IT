---
title: Registrare manualmente i nuovi dispositivi
description: Registrare i dispositivi manualmente in modo che possano essere gestiti da Microsoft Managed Desktop
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

Microsoft Managed Desktop può funzionare con dispositivi completamente nuovi oppure è possibile riutilizzare i dispositivi già disponibili (che richiederanno di ricrearne l'immagine). Puoi registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.

> [!NOTE]
> Collaborare con un partner per ottenere i dispositivi? In tal caso, non è necessario preoccuparsi di ottenere gli hash hardware; si occuperà di questo per te. Assicurati che il partner stabilirà una relazione con te nel [Centro per i partner.](https://partner.microsoft.com/dashboard) Il partner può trovare altre informazioni nella [Guida del Centro per i partner.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Una volta stabilita questa relazione, il partner registrerà semplicemente i dispositivi per conto dell'utente. Non sono necessarie ulteriori azioni da parte dell'utente. Se vuoi visualizzare i dettagli o se il tuo partner ha domande, vedi [La procedura per i partner per registrare i dispositivi.](register-devices-partner.md) Dopo aver registrato i dispositivi, puoi procedere con il [controllo dell'immagine](#check-the-image) e [la consegna dei dispositivi](#deliver-the-device) agli utenti.

## <a name="prepare-to-register-brand-new-devices"></a>Preparare la registrazione di dispositivi nuovi


Dopo aver a disposizione i nuovi dispositivi, segui questi passaggi:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Verifica che l'immagine sia corretta.](#check-the-image)
5. [Recapitare il dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili tre opzioni per ottenere queste informazioni:

- Chiedere al fornitore OEM il file di registrazione AutoPilot, che includerà gli hash hardware.
- Esegui uno [script Windows PowerShell in](#powershell-script-method) ogni dispositivo e raccogli i risultati in un file.
- Avvia ogni dispositivo, ma non completa l'esperienza di installazione di Windows, e raccogli gli hash in un'unità [flash rimovibile.](#flash-drive-method)

#### <a name="powershell-script-method"></a>Metodo di script di PowerShell

È possibile utilizzare lo script [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell nel sito Web PowerShell Gallery. Per altre informazioni sull'identificazione dei dispositivi e sull'hash hardware, vedi [Aggiunta di dispositivi a Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)

1.  Apri un prompt di PowerShell con diritti amministrativi.
2.  Correre `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Eseguire `powershell -ExecutionPolicy restricted` per impedire l'esecuzione di script senza restrizioni successivi.


#### <a name="flash-drive-method"></a>Metodo di unità flash

1. In un dispositivo diverso da quello che stai registrando, inserisci un'unità USB.
2. Apri un prompt di PowerShell con diritti amministrativi.
3. Correre `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione.* Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare l'immagine del dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC+F10.
6. Aprire un prompt di PowerShell con diritti amministrativi ed eseguire `cd <pathToUsb>` .
7. Correre `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo `shutdown -s -t 0`

>[!IMPORTANT]
>Non accensione del dispositivo che stai registrando di nuovo fino a quando non hai completato la registrazione. 


### <a name="merge-hash-data"></a>Unire dati hash

Dovrai combinare i dati nei file CSV in un unico file per completare la registrazione. Ecco uno script di PowerShell di esempio per semplificare:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)seleziona Dispositivi **nel** riquadro di spostamento sinistro. Cerca la sezione Microsoft Managed Desktop del menu e seleziona **Dispositivi.** Nell'area di lavoro Microsoft Managed Desktop Devices seleziona **+ Registra** dispositivi, che apre un riquadro a comparsa per registrare i nuovi dispositivi.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


attenersi alla seguente procedura:

1. In **Caricamento file** specificare il percorso del file CSV creato in precedenza.
3. Selezionare **Registra dispositivi.** Il sistema aggiungerà i dispositivi all'elenco dei dispositivi **nei** dispositivi, contrassegnati come **in sospeso per la registrazione.** La registrazione in genere richiede meno di 10  minuti e, se l'operazione riesce, il dispositivo viene visualizzato come Pronto per l'utente, ovvero è pronto e in attesa che l'utente inizi a usare.


Puoi monitorare l'avanzamento della registrazione del dispositivo nella pagina principale. Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata eseguita. Riestrarlo in un secondo momento. |
| Registrazione non riuscita | Impossibile completare la registrazione. Per altre [informazioni, fai](#troubleshooting-device-registration) riferimento a Risoluzione dei problemi di registrazione dei dispositivi. |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente. Microsoft Managed Desktop li guiderà nella configurazione della prima volta, quindi non è necessario eseguire ulteriori operazioni di preparazione. |
| Attivazione | Il dispositivo è stato recapitato all'utente e registrato nel tenant. Questo stato indica anche che usano regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente e registrato nel tenant. Tuttavia, non hanno usato il dispositivo di recente (negli ultimi 7 giorni).  | 

#### <a name="troubleshooting-device-registration"></a>Risoluzione dei problemi di registrazione dei dispositivi

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare questo dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Confermare questi valori con il fornitore del dispositivo. |
| Hash hardware non valido | L'hash hardware fornito per questo dispositivo non è stato formattato correttamente. Controlla l'hash hardware e quindi invia di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo richiesto da un'altra organizzazione | Questo dispositivo è già stato richiesto da un'altra organizzazione. Rivolgersi al fornitore del dispositivo. |
| Errore imprevisto | Non è stato possibile elaborare automaticamente la richiesta. Contattare il supporto tecnico e fornire l'ID richiesta: <requestId> |

### <a name="check-the-image"></a>Controllare l'immagine

Se il dispositivo è stato provengono da un fornitore partner Microsoft Managed Desktop, l'immagine dovrebbe essere corretta.

Se preferisci, puoi anche applicare l'immagine da solo. To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="deliver-the-device"></a>Recapitare il dispositivo

> [!IMPORTANT]
> Prima di consegnare il dispositivo all'utente, assicurati di aver ottenuto e applicato le [licenze appropriate](../get-ready/prerequisites.md) per tale utente.

Se vengono applicate tutte le [](get-started-devices.md)licenze, puoi fare in modo che gli utenti siano pronti a usare i dispositivi e quindi l'utente può avviare il dispositivo e procedere con l'esperienza di installazione di Windows.





