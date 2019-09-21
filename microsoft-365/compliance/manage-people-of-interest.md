---
title: Gestire gli utenti che interessano le indagini sui dati (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e374509dccd235ef689609acc1c4f99db6594d4c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083780"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>Gestire gli utenti che interessano le indagini sui dati (anteprima)

Le indagini sui dati coinvolgono spesso persone di interesse. In genere, si tratta di persone proprietarie dei dati non posizionati, sensibili o dannosi che si sta indagando o che si desidera correggere. In **indagini sui dati (Preview)**, è possibile aggiungerli per individuare le origini dati da utilizzare nell'ambito della ricerca o per visualizzare informazioni aggiuntive, ad esempio i registri contatti, percorso e attività. 


## <a name="add-people-of-interest"></a>Aggiungere persone di interesse

Nella scheda **utenti di interesse** è possibile aggiungere persone di interesse e individuare le origini dati, ad esempio le cassette postali di Exchange o il sito di OneDrive for business, che è possibile utilizzare per l'ambito della ricerca. Quando gli utenti sono interessati, le ricerche sono più performanti e accurate perché lo strumento rielabora tutti i dati non indicizzati, ad esempio immagini o tipi di file non supportati. È inoltre possibile visualizzare le informazioni di contatto, le informazioni sulla posizione e i registri delle attività che è possibile utilizzare per avviare le comunicazioni o approfondire le proprie attività. 

Per aggiungere persone di interesse a un'indagine:

1. Dalla pagina **indagini dati (anteprima)** , andare all'inchiesta.
 
2. Dopo aver selezionato un'indagine, passare alla scheda **persone interessate** e fare clic su **+ Aggiungi persone di interesse**. 
 
3. Scegliere gli utenti che si desidera aggiungere all'indagine. È possibile iniziare digitando la ricerca e selezionando gli utenti dall'Azure Active Directory dell'organizzazione.
 
4. Dopo aver completato l'elenco di persone di interesse, fare clic su **Avanti** per mappare le origini dati. 

5. Optional Per ogni persona, selezionare **Exchange** per aggiungere la cassetta postale di Exchange principale della persona e **OneDrive** per aggiungere il sito principale di OneDrive for business della persona.

6. Optional Fare clic su **Avanti** per aggiungere eventuali origini dati aggiuntive che si desidera associare ai propri utenti.

7. Optional Selezionare **Aggiorna** per assegnare le posizioni di contenuto, come le cassette postali, i siti e i team a un utente. 

8. Optional Nel riquadro a comparsa:
   
    -  **Cassette postali di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** . Per aggiungere altre cassette postali, utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione. È inoltre possibile aggiungere cassette postali utilizzate per l'archiviazione di un gruppo di Office 365 o di una Microsoft Team Information. Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.

        > [!NOTE]
        > Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca.
     
     - **Siti di SharePoint** -fare clic su **Choose sites** , quindi fare clic su **Choose sites** again per specificare altri siti di SharePoint e OneDrive for business che è possibile aggiungere a una persona. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Office 365 o un team di Microsoft. Digitare l'URL per ogni sito che si desidera assegnare. Fare clic su **Scegli**e quindi su **fine**.
     - **Microsoft teams** -fare clic su **Scegli team** e quindi fare di nuovo clic su **Scegli squadre** per visualizzare un elenco di gruppi di team Microsoft che la persona è un membro di oggi. Selezionare i team che si desidera aggiungere alla persona. Una volta selezionata, il sistema identificherà automaticamente & selezionare il sito di SharePoint associato e la cassetta postale del gruppo associata a quel team Microsoft. Fare clic su **Scegli**e quindi su **fine**.
        
      > [!NOTE]
      > Per aggiungere ulteriori Microsoft teams, sarà necessario aggiungere separatamente la cassetta postale e il sito di SharePoint come illustrato in alto.

Dopo aver completato la mappatura delle origini dati alle persone di interesse, è possibile visualizzare il riepilogo di tutte le cassette postali, i siti e i team appena aggiunti. [! Nota] Se si mappano altre origini dati a persone di interesse e l'ambito della ricerca da parte di persone di interesse, la mappatura del documento a persone di interesse persiste durante l'indagine, facilitando l'organizzazione di prove o la generazione di report da parte di persone di interesse . 

## <a name="view-additional-people-of-interest-information"></a>Visualizzazione di altre persone di informazioni sugli interessi

Nella scheda **persone di interesse** , fare clic su una persona che si Adeed. In un riquadro a comparsa, vedrai:

- Informazioni di contatto

  - **Nome**visualizzato: il nome del Peron visualizzato nella rubrica. Questo è in genere la combinazione del nome, dell'iniziale e del cognome.
  - **Posta/SMTP**: indirizzo SMTP della persona, ad esempio Jeff@contoso.onmicrosoft.com.  
  - **Titolo**: titolo del processo.
  - **Reparto**: il nome del reparto in cui lavora la persona.
  - **Responsabile**: responsabile del personale. Manager riceve tutte le comunicazioni di escalation per questa persona.
  
- Informazioni sulle posizioni

  - **Città**: la città in cui si trova la persona.
  - **Stato**: lo stato o la provincia in cui si trova l'utente.
  - **Paese/area geografica**: il paese/area geografica in cui si trova la persona; ad esempio, "US" o "UK".
  - **Office**: posizione dell'ufficio dell'utente.

- Stato di elaborazione

  - **Stato di indicizzazione**: stato del Deep indicizzazione delle origini dati
  - **Indicizzazione dell'ultimo aggiornamento**: timestamp del momento in cui il processo di indicizzazione Deep è stato attivato.
  - **Origini dati**: Visualizza il numero di cassette postali, siti e team mappati alla persona

- Indice di aggiornamento
    - È possibile reindicizzare le origini dati di questa persona. 

- Visualizzazione attività 

    - È possibile visualizzare e cercare i registri delle attività dell'utente. Per ulteriori informazioni, vedere [View people of interest Activity](view-people-of-interest-activity.md) 
