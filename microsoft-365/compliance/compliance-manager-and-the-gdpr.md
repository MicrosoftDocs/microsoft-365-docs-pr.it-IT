---
title: Microsoft Compliance Manager e GDPR
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
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: e41b28972dc2ada5c0591de0e73c04ea3306e039
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083241"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager e GDPR

Il regolamento generale sulla protezione dei dati (GDPR) emanato dall'Unione europea può influire sulla strategia di conformità e sul mandato azioni specifiche per la gestione delle informazioni relative agli utenti e ai clienti utilizzati in Compliance Manager.

## <a name="user-privacy-settings"></a>Impostazioni di privacy dell'utente

Alcune normative richiedono che un'organizzazione debba essere in grado di eliminare i dati della cronologia degli utenti. Compliance Manager fornisce **le funzioni delle impostazioni per la privacy degli utenti** che consentono agli amministratori di:
  
- [Cercare un utente](#search-for-a-user)
- [Esportare un report di cronologia dei dati dell'account](#export-a-report-of-account-data-history)
- [Eliminare la cronologia dei dati dell'utente](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Cercare un utente

Cercare un account utente:
  
1. Immettere l'alias di posta elettronica dell'utente (le informazioni a sinistra del simbolo @) e scegliere il nome del dominio dall'elenco dei suffissi di dominio a destra. Per le organizzazioni con più domini registrati, controllare il suffisso del nome di dominio per assicurarsi che sia corretto.

2. Se il nome utente è stato immesso correttamente, selezionare **Cerca**.

3. Per gli account utente non restituiti, la pagina Visualizza l' **utente non trovato**. Controllare le informazioni sull'indirizzo di posta elettronica dell'utente e apportare le correzioni in base alle esigenze. Per riprovare, selezionare **Cerca**.

4. Per gli account utente restituiti, il testo del pulsante cambia dalla **ricerca** alla **cancellazione**. Ciò indica che l'account utente restituito è il contesto operativo per le funzioni aggiuntive e che queste funzioni sono valide per questo account utente.

5. Per cancellare i risultati della ricerca e cercare un altro utente, selezionare **Annulla**.

## <a name="export-a-report-of-account-data-history"></a>Esportare un report di cronologia dei dati dell'account

Per ogni account utente identificato, è possibile generare un report delle dipendenze collegate a questo account. Queste informazioni consentono di riassegnare gli elementi dell'azione aperta o di garantire l'accesso alle prove precedentemente caricate.
  
 Per generare ed esportare un report:
  
1. Selezionare **Esporta** per generare e scaricare un report degli elementi azione di controllo di Compliance Manager attualmente assegnati all'account utente restituito e l'elenco dei documenti caricati da tale utente. Se non sono state assegnate azioni o documenti caricati, un messaggio di errore indica che non sono presenti dati per questo utente.

2. Il report viene scaricato nello sfondo della finestra del browser attiva, se non viene visualizzato un popup per il download che si desidera controllare nella cronologia dei download del browser.

3. Aprire il documento per visualizzare i dati del report.

> [!IMPORTANT]
> I dati del report non sono un elenco cronologico che conserva e visualizza le modifiche di stato alla cronologia delle assegnazioni degli elementi di azione. Il report generato è uno snapshot degli elementi azione di controllo assegnati al momento dell'esecuzione del report (data e timestamp scritti nel report). Ad esempio, eventuali riassegnazioni successive di elementi azione determinano i diversi dati del rapporto snapshot se il report viene generato di nuovo per lo stesso utente.
  
## <a name="delete-user-data-history"></a>Eliminare la cronologia dei dati dell'utente

Imposta tutti gli elementi azione di controllo assegnati all'utente restituito su' non assegnato '. Imposta il valore **caricato** per tutti i documenti caricati dall'utente restituito su "rimosso dall'utente".
  
Per eliminare l'elemento di azione dell'account utente e la cronologia del caricamento del documento:
  
1. Selezionare **Elimina**.

    Viene visualizzata una finestra di dialogo di conferma, "*questo rimuove tutte le assegnazioni di elementi di azione di controllo e la cronologia del caricamento del documento per l'utente selezionato. Questa azione è permanente. Si è sicuri di voler continuare?*"

2. Per continuare seleziona **OK**, altrimenti seleziona **Annulla**.
