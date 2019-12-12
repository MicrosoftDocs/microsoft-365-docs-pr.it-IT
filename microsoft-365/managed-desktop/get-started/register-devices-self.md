---
title: Registrare manualmente i nuovi dispositivi
description: Registrare i dispositivi da soli in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a1dbb5708cad32a0e37ddc25c97c70a765580f86
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962523"
---
# <a name="register-new-devices-yourself"></a>Registrare manualmente i nuovi dispositivi

Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi che potrebbero essere già presenti (il che richiede che vengano ristampati). È possibile registrare i dispositivi tramite Microsoft Managed Desktop sul portale di Azure.

> [!NOTE]
> Utilizzo di un partner per ottenere i dispositivi In caso affermativo, non è necessario preoccuparsi di ottenere gli hash hardware; si occuperà di questo per voi. Assicurarsi che il partner stabilisca una relazione con l'utente al [centro partner](https://partner.microsoft.com/dashboard) e che includa i privilegi di Amministrazione delegati per Azure Active Directory e Office 365. Il partner può ottenere ulteriori informazioni nella [Guida di partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Una volta che questa relazione è stata stabilita, il partner registrerà semplicemente i dispositivi per conto dell'utente: nessuna ulteriore azione necessaria. Se si desidera visualizzare i dettagli o il proprio partner ha domande, vedere la [procedura per i partner per la registrazione dei dispositivi](register-devices-partner.md). Dopo la registrazione dei dispositivi, è possibile procedere con la [Verifica dell'immagine](#check-the-image) e [la distribuzione dei dispositivi](#deliver-the-device) agli utenti.

## <a name="prepare-to-register-brand-new-devices"></a>Preparare la registrazione di dispositivi nuovi di zecca


Una volta che i nuovi dispositivi sono disponibili, è necessario eseguire la procedura seguente:

1. [Ottenere l'hash hardware per ogni dispositivo.](#obtain-the-hardware-hash)
2. [Unire i dati hash](#merge-hash-data)
3. [Registrare i dispositivi in Microsoft Managed Desktop](#register-devices).
4. [Verificare che l'immagine sia corretta.](#check-the-image)
5. [Recapito del dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Ottenere l'hash hardware

Microsoft Managed Desktop identifica ogni dispositivo in modo univoco facendo riferimento al relativo hash hardware. Sono disponibili tre opzioni per ottenere queste informazioni:

- Rivolgersi al fornitore OEM per il file di registrazione Autopilot, che includerà gli hash hardware.
- Eseguire uno [script di Windows PowerShell](#powershell-script-method) su ogni dispositivo e raccogliere i risultati in un file.
- Avviare ogni dispositivo--ma non completare l'esperienza di installazione di Windows--e [raccogliere gli hash su un'unità flash rimovibile](#flash-drive-method).

#### <a name="powershell-script-method"></a>Metodo script di PowerShell

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre`Install-Script -Name Get-MMDRegistrationInfo`
3.  Correre`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>Metodo dell'unità flash

1. In un dispositivo diverso da quello che si sta registrando, inserire un'unità USB.
2. Aprire un prompt di PowerShell con diritti amministrativi.
3. Correre`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Attivare il dispositivo che si sta registrando, ma *non avviare l'esperienza di installazione*. Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC + F10.
6. Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>`.
7. Correre`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo`shutdown -s -t 0`

>[!IMPORTANT]
>Non accendere il dispositivo che si sta registrando di nuovo fino a quando non si è completata la registrazione. 


### <a name="merge-hash-data"></a>Unire i dati hash

Per completare la registrazione, è necessario che i dati dei file CSV siano combinati in un unico file. Di seguito è indicato uno script di PowerShell di esempio per semplificare le operazioni seguenti:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

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

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrare i dispositivi tramite il portale di Azure

Dal portale Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal)selezionare **dispositivi** nel riquadro di spostamento a sinistra. Selezionare **+ registra dispositivi**; verrà aperto il volo:

[![Fly-in dopo aver selezionato i dispositivi di registrazione, elencare i dispositivi con colonne per gli utenti assegnati, il numero di serie, lo stato, la data dell'ultima visualizzazione e l'età](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


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
| Attivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Questo indica anche che stanno usando regolarmente il dispositivo. |
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






