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
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro in Microsoft Service Trust Portal. Questo consente di tenere traccia, assegnare e verificare le attività di conformità correlate ai servizi cloud Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595803"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager e GDPR

Il Regolamento generale sulla protezione dei dati (GDPR) emanato dall'Unione Europea può influire sulla tua strategia di conformità e imporre azioni specifiche per gestire le informazioni su utenti e clienti usate in Compliance Manager.

## <a name="user-privacy-settings"></a>Impostazioni di privacy dell'utente

Alcune normative richiedono che un'organizzazione debba essere in grado di eliminare i dati della cronologia utente. Compliance Manager offre le funzioni **Impostazioni privacy dell'utente** che consentono agli amministratori di:
  
- [Cercare un utente](#search-for-a-user)
- [Esportare un report di cronologia dei dati dell'account](#export-a-report-of-account-data-history)
- [Eliminare la cronologia dei dati dell'utente](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Cercare un utente

Cercare un account utente:
  
1. Immettere l'alias di posta elettronica utente (le informazioni a sinistra del simbolo @) e scegliere il nome di dominio nell'elenco di suffissi di dominio a destra. Per le organizzazioni con più domini registrati, controllare il suffisso del nome di dominio per verificare che sia corretto.

2. Dopo aver immesso correttamente il nome utente, fare clic su **Cerca**.

3. Per gli account utente non restituiti, la pagina mostra **Utente non trovato**. Controllare le informazioni dell'indirizzo di posta elettronica dell'utente e apportare le correzioni necessarie. Per riprovare, selezionare **Cerca**.

4. Per gli account utente restituiti, il testo del pulsante cambia da **Cerca** a **Cancella**. Ciò indica che l'account utente restituito è il contesto operativo per le funzioni aggiuntive e che queste funzioni si applicano a questo account utente.

5. Per cancellare i risultati della ricerca e cercare un altro utente, fare clic su **Cancella**.

## <a name="export-a-report-of-account-data-history"></a>Esportare un report di cronologia dei dati dell'account

Per ogni account utente identificato, è possibile generare un report delle dipendenze collegate all'account. Queste informazioni consentono di riassegnare attività aperte o di verificare l'accesso alle prove caricate in precedenza.
  
 Per generare ed esportare un report:
  
1. Selezionare **Esporta** per generare e scaricare un report delle attività di controllo di Compliance Manager attualmente assegnate all'account utente restituito e l'elenco dei documenti caricati dall'utente. Se non ci sono azioni assegnate o documenti caricati, un messaggio di errore indica che non ci sono dati per l'utente.

2. Il report viene scaricato sullo sfondo della finestra del browser attiva - se non si visualizza il popup di download, controllare la cronologia dei download del browser.

3. Aprire il documento per visualizzare i dati del report.

> [!IMPORTANT]
> Non si tratta di un elenco cronologico che conserva e indica le modifiche di stato alla cronologia delle assegnazioni delle attività. Il report generato è un'istantanea delle attività di controllo assegnate al momento dell'esecuzione del report (data e ora scritti nel report). Ad esempio, qualsiasi successiva riassegnazione delle attività genererà dati del report snapshot diversi se questo report viene generato di nuovo per lo stesso utente.
  
## <a name="delete-user-data-history"></a>Eliminare la cronologia dei dati dell'utente

Imposta tutte le attività di controllo assegnate all'utente restituito su "non assegnate". Imposta il valore **caricato da** per tutti i documenti caricati dall'utente restituito in "utente rimosso".
  
Per eliminare l'attività dell'account utente e la cronologia di caricamento dei documenti:
  
1. Selezionare **Elimina**.

    Viene visualizzata una finestra di dialogo di conferma: "*Vengono rimosse tutte le assegnazioni dell'attività di controllo e la cronologia di caricamento del documento per l'utente selezionato. Questa azione è permanente. Vuoi continuare?*"

2. Per continuare, selezionare **OK**, altrimenti selezionare **Annulla**.
