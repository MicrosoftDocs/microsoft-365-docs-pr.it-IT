---
title: Registrare manualmente i nuovi dispositivi
description: Registrare manualmente i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
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
ms.openlocfilehash: 3aff3bdc1260e9aa2a23760020aeabd71d6b28fd
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445579"
---
# <a name="register-new-devices-yourself"></a>Registrare manualmente i nuovi dispositivi

Microsoft Managed Desktop può funzionare con dispositivi nuovi o puoi riutilizzare i dispositivi che potresti già avere (che richiederanno di ricrearne l'immagine). Puoi registrare i dispositivi con Microsoft Managed Desktop nel portale di Microsoft Endpoint Manager.

> [!NOTE]
> Collaborare con un partner per ottenere dispositivi? In tal caso, non è necessario preoccuparsi di ottenere gli hash hardware; si occuperà di questo per te. Assicurati che il partner stabilirà una relazione con te nel [Centro per i partner.](https://partner.microsoft.com/dashboard) Per altre informazioni, vedere la Guida [del Centro per i partner.](/partner-center/request-a-relationship-with-a-customer) Una volta stabilita questa relazione, il partner registrerà semplicemente i dispositivi per conto dell'utente. Non sono necessarie ulteriori azioni da parte dell'utente. Se vuoi visualizzare i dettagli o il tuo partner ha domande, vedi Passaggi per i [partner per registrare i dispositivi.](register-devices-partner.md) Una volta registrati i dispositivi, puoi procedere con il [controllo dell'immagine](#check-the-image) e [la consegna dei dispositivi](#deliver-the-device) agli utenti.

## <a name="prepare-to-register-brand-new-devices"></a>Preparare la registrazione di nuovi dispositivi


Una volta che hai a disposizione i nuovi dispositivi, segui questi passaggi:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapita il dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili tre opzioni per ottenere queste informazioni:

- Chiedere al fornitore OEM il file di registrazione AutoPilot, che includerà gli hash hardware.
- Esegui uno [script Windows PowerShell su](#powershell-script-method) ogni dispositivo e raccogli i risultati in un file.
- Avviare ogni dispositivo, ma non completare l'esperienza di installazione di Windows, e raccogliere gli [hash in un'unità flash rimovibile.](#flash-drive-method)

#### <a name="powershell-script-method"></a>Metodo script di PowerShell

È possibile utilizzare lo script [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell nel sito Web PowerShell Gallery. Per altre informazioni sull'identificazione del dispositivo e sull'hash hardware, vedi [Aggiunta di dispositivi a Windows Autopilot.](/mem/autopilot/add-devices#device-identification)

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Eseguire `powershell -ExecutionPolicy restricted` per impedire l'esecuzione di script senza restrizioni successivi.


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

>[!IMPORTANT]
>Non alimentare il dispositivo che stai registrando di nuovo finché non hai completato la registrazione. 


### <a name="merge-hash-data"></a>Unire dati hash

Dovrai combinare i dati nei file CSV in un singolo file per completare la registrazione. Ecco uno script di PowerShell di esempio per semplificare:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrare i dispositivi tramite il portale di amministrazione

In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)seleziona Dispositivi **nel** riquadro di spostamento a sinistra. Cerca la sezione Microsoft Managed Desktop del menu e seleziona **Dispositivi.** Nell'area di lavoro Dispositivi desktop gestiti Microsoft seleziona **+ Registra dispositivi**, che apre un riquadro a comparsa per registrare nuovi dispositivi.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Eseguire la procedura seguente:

1. In **Caricamento file** specificare il percorso del file CSV creato in precedenza.
3. Selezionare **Registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco dei dispositivi in **Dispositivi**, contrassegnati come **Registrazione in sospeso**. La registrazione in genere richiede meno di 10 minuti e quando il dispositivo ha esito positivo il dispositivo viene visualizzato come **Pronto** per l'utente, ovvero è pronto e in attesa che un utente inizi a usare.


Puoi monitorare l'avanzamento della registrazione del dispositivo nella pagina principale. Tra i possibili stati segnalati vi sono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata eseguita. Eseguire il check back in un secondo momento. |
| Registrazione non riuscita | Impossibile completare la registrazione. Per ulteriori [informazioni, vedere Risoluzione dei](#troubleshooting-device-registration) problemi di registrazione dei dispositivi. |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente. Microsoft Managed Desktop li guiderà nella configurazione della prima volta, quindi non è necessario eseguire ulteriori operazioni di preparazione. |
| Attivo | Il dispositivo è stato recapitato all'utente e si è registrato nel tenant. Questo stato indica anche che usano regolarmente il dispositivo. |
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