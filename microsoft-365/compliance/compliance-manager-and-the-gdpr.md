---
title: Microsoft Compliance Manager e GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento gratuito di valutazione dei rischi basato sul flusso di lavoro in Microsoft Service Trust Portal. Compliance Manager consente di tenere traccia, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595803"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager e GDPR

Il Regolamento generale sulla protezione dei dati (GDPR) evaso dall'Unione Europea può influire sulla strategia di conformità e impone azioni specifiche per gestire le informazioni su utenti e clienti utilizzate in Compliance Manager.

## <a name="user-privacy-settings"></a>Impostazioni di privacy dell'utente

Alcune normative richiedono che un'organizzazione sia in grado di eliminare i dati della cronologia utente. Compliance Manager fornisce **funzioni per le impostazioni di privacy** degli utenti che consentono agli amministratori di:
  
- [Cercare un utente](#search-for-a-user)
- [Esportare un report di cronologia dei dati dell'account](#export-a-report-of-account-data-history)
- [Eliminare la cronologia dei dati dell'utente](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Cercare un utente

Cercare un account utente:
  
1. Immettere l'alias di posta elettronica dell'utente (le informazioni a sinistra del simbolo @) e scegliere il nome di dominio dall'elenco dei suffissi di dominio a destra. Per le organizzazioni con più domini registrati, controllare il suffisso del nome di dominio per verificare che sia corretto.

2. Dopo aver immesso correttamente il nome utente, selezionare **Cerca.**

3. Per gli account utente non restituiti, nella pagina viene visualizzato **Utente non trovato.** Controllare le informazioni sull'indirizzo di posta elettronica dell'utente e apportare le correzioni necessarie. Per riprovare, selezionare **Cerca.**

4. Per gli account utente restituiti, il testo del pulsante cambia da **Ricerca** a **Cancella.** Ciò indica che l'account utente restituito è il contesto operativo per le funzioni aggiuntive e che queste funzioni si applicano a questo account utente.

5. Per cancellare i risultati della ricerca e cercare un altro utente, selezionare **Cancella.**

## <a name="export-a-report-of-account-data-history"></a>Esportare un report di cronologia dei dati dell'account

Per ogni account utente identificato, puoi generare un report delle dipendenze collegate all'account. Queste informazioni consentono di riassegnare le attività aperte o di garantire l'accesso alle prove caricate in precedenza.
  
 Per generare ed esportare un report:
  
1. Selezionare **Esporta** per generare e scaricare un report delle attività di controllo di Compliance Manager attualmente assegnate all'account utente restituito e l'elenco dei documenti caricati da tale utente. Se non sono presenti azioni assegnate o documenti caricati, viene visualizzato il messaggio di errore "Nessun dato per questo utente".

2. Il report viene scaricato in background nella finestra del browser attiva, se non viene visualizzata una finestra popup di download che si desidera controllare la cronologia di download del browser.

3. Aprire il documento per visualizzare i dati del report.

> [!IMPORTANT]
> I dati del report non sono un elenco cronologico che mantiene e visualizza le modifiche di stato alla cronologia delle assegnazioni delle attività. Il report generato è uno snapshot delle attività di controllo assegnate al momento dell'esecuzione del report (data e timestamp scritti nel report). Ad esempio, qualsiasi successiva riassegnazione delle attività comporta dati di report snapshot diversi se il report viene generato di nuovo per lo stesso utente.
  
## <a name="delete-user-data-history"></a>Eliminare la cronologia dei dati dell'utente

Imposta tutte le attività di controllo assegnate all'utente restituito su "non assegnato". Imposta il **valore caricato per** i documenti caricati dall'utente restituito su "utente rimosso".
  
Per eliminare l'elemento azione dell'account utente e la cronologia di caricamento dei documenti:
  
1. Selezionare **Elimina**.

    Viene visualizzata una finestra di dialogo di conferma: " In questo modo vengono rimosse tutte le assegnazioni dell'elemento azione di controllo e la cronologia di caricamento del documento *per l'utente selezionato. Questa azione è permanente. Si è sicuri di voler continuare?*"

2. Per continuare selezionare **OK,** altrimenti scegliere **Annulla.**
