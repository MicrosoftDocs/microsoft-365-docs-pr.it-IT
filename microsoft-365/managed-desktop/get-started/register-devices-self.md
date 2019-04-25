---
title: Registrare i dispositivi in Microsoft Managed Desktop
description: Registrare i dispositivi da soli in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: cf77e4bf69e6ae144563f1e764ea3437ed6fc836
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2019
ms.locfileid: "33296166"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Registrare i dispositivi in Microsoft Managed Desktop

>[!NOTE]
>In questo argomento vengono illustrati i passaggi da eseguire per la registrazione dei dispositivi. Il processo per i partner è documentato nei [dispositivi di registrazione in Microsoft managEd Desktop for partners](register-devices-partner.md).

Microsoft Managed Desktop è in grado di lavorare con dispositivi nuovi di zecca oppure è possibile riutilizzare i dispositivi che potrebbero essere già presenti (il che richiede che vengano ristampati). È possibile registrare i dispositivi tramite Microsoft Managed Desktop sul portale di Azure o ottenere flessibilità utilizzando un'API.

## <a name="prepare-to-register-devices"></a>Preparare la registrazione di dispositivi

Se non sono già stati ottenuti i dispositivi che si desidera utilizzare, controllare i [dispositivi Microsoft managEd desktop](../service-description/device-list.md) e collaborare con un partner dispositivo per procurarsi dispositivi supportati.

Se si lavora con dispositivi completamente nuovi o si riutilizzano quelli esistenti, per registrarli con Microsoft Managed Desktop, è necessario preparare un **file CSV (delimitato da virgole)**. Questo file deve includere le informazioni seguenti per ogni dispositivo:

>[!NOTE]
>Questo formato è solo per la registrazione in modalità self-service. Il formato dei partner dovrebbe essere utilizzato è documentato nei [dispositivi di registrazione in Microsoft managEd Desktop for partners](register-devices-partner.md).

Questi valori vengono utilizzati per scopi di visualizzazione e non è necessario corrispondere esattamente alle proprietà del dispositivo.
- Produttore del dispositivo (ad esempio: SpiralOrbit) 
- Modello di dispositivo (ad esempio: ContosoABC)
- Numero di serie del dispositivo

L'hash hardware deve essere una corrispondenza esatta.
- Hash hardware

Per ottenere l'hash hardware, è possibile richiedere assistenza all'OEM o al partner oppure eseguire la procedura seguente per ogni dispositivo:

1.  Aprire un prompt di PowerShell con diritti amministrativi.
2.  Correre`Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Correre`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`


In alternativa, è possibile eseguire questa procedura in un dispositivo nuovo di zecca (prima di passare per la prima volta tramite OOBE):

1. In un altro dispositivo, inserire un'unità USB.
2. Aprire un prompt di PowerShell con diritti amministrativi.
3. Correre`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Attivare il dispositivo di destinazione, ma non avviare l'esperienza di installazione. Se si avvia accidentalmente l'esperienza di installazione, sarà necessario reimpostare o ricreare il dispositivo.
5. Inserire l'unità USB e quindi premere MAIUSC + F10.
6. Aprire un prompt di PowerShell con diritti amministrativi e quindi eseguirlo `cd <pathToUsb>`.
7. Correre`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Correre`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
3. Rimuovere l'unità USB e quindi arrestare il dispositivo eseguendo`shutdown -s -t 0`

>[!IMPORTANT]
>Non accendere nuovamente il dispositivo di destinazione fino a quando non si è completata la registrazione. 

>[!NOTE]
>Per comodità, è possibile scaricare un [modello](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) per questo file CSV.

Il file deve includere le **intestazioni di colonna** identiche a quelle del campione (produttore, modello e così via), ma i propri dati per le altre righe. Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio Blocco note, e considerare di lasciare tutti i dati solo nella riga 1, immettendo solo i dati nelle righe 2 e seguenti. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Se si dimentica di modificare i dati di esempio, la registrazione avrà esito negativo.   


## <a name="register-devices-by-using-the-azure-portal"></a>Registrare i dispositivi tramite il portale di Azure

Dal portale Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal)selezionare **dispositivi** nel riquadro di spostamento a sinistra. Selezionare **+ registra dispositivi**; verrà aperto il volo:

[![Fly-in dopo aver selezionato i dispositivi di registrazione](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Purtroppo questo non è vero. È possibile rimuovere questa nota, lasciandola adesso fino a quando non avremo la possibilità di chattare.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Eseguire la procedura seguente:

1. In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.
2. Facoltativamente, è possibile aggiungere un **ID ordine** o un **ID acquisto** per i propri scopi di verifica. Non sono presenti requisiti di formato per questi valori.
3. Selezionare **registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**. La registrazione richiede in genere meno di 10 minuti e, quando il dispositivo verrà visualizzato come **pronto per il significato dell'utente** , è pronto e in attesa che l'utente finale inizi a utilizzare.


È possibile monitorare lo stato di registrazione dei dispositivi nella pagina principale di **Microsoft managEd desktop-Devices** . Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata completata. Controllare in un secondo momento. |
| Registrazione non riuscita | La registrazione non è stata completata. Per ulteriori informazioni, fare riferimento a [risoluzione dei problemi](register-devices-self.md#troubleshooting) . |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente finale. Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi. |
| Attivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Questo indica anche che stanno usando regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).  | 


## <a name="register-devices-by-using-an-api"></a>Registrare i dispositivi tramite un'API

È disponibile un'API REST per consentire una maggiore flessibilità e ripetibilità con frequenti registrazioni di dispositivi separate. Al momento, per utilizzare l'API, chiedere assistenza al contatto Microsoft per partecipare a un'anteprima di questa funzionalità.



## <a name="troubleshooting"></a>Risoluzione dei problemi

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Confermare questi valori con il fornitore del dispositivo. |
| Dispositivo non trovato | Non è stato possibile annullare la registrazione di questo dispositivo perché non esiste nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Hash hardware non valido | L'hash hardware fornito per il dispositivo non è stato formattato correttamente. Fare doppio check sull'hash hardware e quindi inviare di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo rivendicato da un'altra organizzazione | Questo dispositivo è già stato rivendicato da un'altra organizzazione. Controllare con il fornitore del dispositivo. |
| Errore imPrevisto | La richiesta non è stata elaborata automaticamente. Contattare il supporto tecnico e fornire l'ID richiesta:<requestId> |




