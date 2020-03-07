---
title: Procedura per i partner per la registrazione dei dispositivi
description: Il modo in cui i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557564"
---
# <a name="steps-for-partners-to-register-devices"></a>Procedura per i partner per la registrazione dei dispositivi


In questo argomento vengono illustrati i passaggi da seguire per i partner per la registrazione dei dispositivi. Il processo di registrazione dei dispositivi manualmente è documentato in [dispositivi di registrazione in Microsoft Managed Desktop Yourself](register-devices-self.md).



## <a name="prepare-for-registration"></a>Prepararsi per la registrazione 
Prima di completare la registrazione per un cliente, è necessario innanzitutto stabilire una relazione con tali utenti nel [centro partner](https://partner.microsoft.com/dashboard). Assicurarsi di selezionare **Includi privilegi di amministrazione delegata per Azure Active Directory e Office 365**. Per ulteriori informazioni, vedere la [Guida di partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).

Per completare la registrazione per il cliente, creare innanzitutto un file CSV.

>[!NOTE]
>Per la vostra convenienza, è possibile scaricare un [file CSV di esempio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) per la *versione del partner*.

Il file deve includere le **intestazioni di colonna** identiche a quelle del campione (produttore, modello e così via), ma i propri dati per le altre righe. Se si utilizza il modello, aprirlo in uno strumento di modifica del testo, ad esempio Blocco note, e considerare di lasciare tutti i dati solo nella riga 1, immettendo solo i dati nelle righe 2 e seguenti. 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>Questo formato è solo per il processo del partner. Il processo per la registrazione automatica è documentato nei [dispositivi di registrazione in Microsoft Managed Desktop Yourself](register-devices-self.md).

>[!IMPORTANT]
>Questi valori devono corrispondere esattamente ai valori del produttore di SMBIOS, tra cui le maiuscole e i caratteri speciali. 

- Produttore del dispositivo (ad esempio: SpiralOrbit) 
- Modello di dispositivo (ad esempio: ContosoABC)
- Numero di serie del dispositivo

## <a name="register-devices-by-using-the-azure-portal"></a>Registrare i dispositivi tramite il portale di Azure

La registrazione tramite il portale di Azure è identica a quella del servizio self-service, tranne per il fatto che l'accesso al portale è diverso. Eseguire la procedura seguente:

1. Accedere a [centro partner](https://partner.microsoft.com/dashboard)
2. Seleziona **clienti**.
3. Selezionare il cliente che si desidera gestire.
4. Selezionare **amministrazione del servizio**.
5. Selezionare **Intune**.
6. Cercare "MMD" nella casella di ricerca superiore del portale di Azure.
7. Selezionare **dispositivi**.
8. In **caricamento file**, specificare un percorso per il file CSV creato in precedenza.
9. Facoltativamente, è possibile aggiungere un **ID ordine** o un **ID acquisto** per i propri scopi di verifica. Non sono presenti requisiti di formato per questi valori.
10. Selezionare **registra dispositivi**. Il sistema aggiungerà i dispositivi all'elenco di dispositivi sul Blade dei **dispositivi**, contrassegnati come **registrazione in sospeso**. La registrazione richiede in genere meno di 10 minuti e, quando il dispositivo verrà visualizzato come **pronto per il significato dell'utente** , è pronto e in attesa che l'utente finale inizi a utilizzare.


È possibile monitorare lo stato di registrazione dei dispositivi nella pagina principale di **Microsoft Managed Desktop-Devices** . Gli stati possibili segnalati includono:

| Stato | Descrizione |
|---------------|-------------|
| Registrazione in sospeso | La registrazione non è ancora stata completata. Controllare in un secondo momento. |
| Registrazione non riuscita | La registrazione non è stata completata. Per ulteriori informazioni, vedere [risoluzione dei problemi relativi alla registrazione del dispositivo](register-devices-self.md#troubleshooting-device-registration) . |
| Pronto per l'utente | La registrazione ha avuto esito positivo e il dispositivo è ora pronto per essere recapitato all'utente finale. Microsoft Managed Desktop li guiderà per la prima volta, quindi non è necessario eseguire ulteriori preparativi. |
| Attivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Questo indica anche che stanno usando regolarmente il dispositivo. |
| Inattivo | Il dispositivo è stato recapitato all'utente finale ed è stato registrato con il tenant. Tuttavia, non hanno utilizzato il dispositivo di recente (negli ultimi 7 giorni).  |



## <a name="troubleshooting"></a>Risoluzione dei problemi

| Messaggio di errore | Dettagli |
|---------------|-------------|
| Dispositivo non trovato | Non è stato possibile registrare il dispositivo perché non è stata trovata una corrispondenza per il produttore, il modello o il numero di serie specificato. Confermare questi valori con il fornitore del dispositivo. |
| Hash hardware non valido | L'hash hardware fornito per il dispositivo non è stato formattato correttamente. Fare doppio check sull'hash hardware e quindi inviare di nuovo. |
| Dispositivo già registrato | Questo dispositivo è già registrato nell'organizzazione. Non sono necessarie ulteriori azioni. |
| Dispositivo rivendicato da un'altra organizzazione | Questo dispositivo è già stato rivendicato da un'altra organizzazione. Controllare con il fornitore del dispositivo. |
| Errore imprevisto | La richiesta non è stata elaborata automaticamente. Contattare il supporto<support link>tecnico () e fornire l'ID richiesta:<requestId> |
