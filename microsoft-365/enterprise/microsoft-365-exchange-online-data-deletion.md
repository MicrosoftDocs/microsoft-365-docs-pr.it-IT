---
title: Eliminazione dei dati di Microsoft 365 Exchange Online
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come vengono gestite in Exchange Online le eliminazioni di dati di contenuti non consentiti per le cassette postali e gli elementi all'interno di
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4b4d30da70001967ca73377f10a4cd417577b72
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696073"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Eliminazione dei dati di Exchange online in Microsoft 365

In Exchange Online, esistono due tipi di eliminazioni: eliminazioni morbide e eliminazioni dure. Questo si applica alle cassette postali e agli elementi all'interno di una cassetta postale.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Cassette postali eliminate temporaneamente e eliminate definitivamente
Una cassetta postale utente eliminata temporaneamente è una cassetta postale che è stata eliminata utilizzando l'interfaccia di amministrazione di Microsoft 365 o il cmdlet Remove-Mailbox ed è ancora presente nel cestino di Azure Active Directory per meno di 30 giorni. Una cassetta postale può essere eliminata temporaneamente in uno dei modi seguenti:
- L'account utente Azure Active Directory associato alla cassetta postale dell'utente viene eliminato temporaneamente (l'oggetto utente non rientra nell'ambito o nel contenitore del cestino).
- L'account utente Azure Active Directory associato alla cassetta postale dell'utente è stato eliminato definitivamente ma la cassetta postale di Exchange Online è soggetta a un blocco per controversia legale o a un blocco di eDiscovery.
- L'account utente Azure Active Directory associato alla cassetta postale dell'utente è stato eliminato negli ultimi 30 giorni. che è la lunghezza massima di conservazione in Exchange Online, la cassetta postale non viene eliminata temporaneamente prima che venga eliminata definitivamente e irrecuperabile.

Una cassetta postale di un utente eliminato definitivamente è una cassetta postale che è stata eliminata in uno dei modi seguenti:
- La cassetta postale dell'utente è stata eliminata temporaneamente per più di 30 giorni e l'utente di Azure Active Directory associato è stato eliminato definitivamente. Tutti i contenuti delle cassette postali, ad esempio messaggi di posta elettronica, contatti e file vengono eliminati definitivamente.
- L'account utente associato alla cassetta postale dell'utente è stato eliminato definitivamente da Azure Active Directory. La cassetta postale dell'utente è stata eliminata temporaneamente in Exchange Online e rimane in uno stato di eliminazione temporanea per 30 giorni. Se nel periodo di 30 giorni un nuovo utente di Azure Active Directory è sincronizzato dall'account del destinatario originale con lo stesso **ExchangeGuid** o **proprietà ArchiveGuid**e questo nuovo account è concesso in licenza per Exchange Online, si verificherà un'eliminazione definitiva della cassetta postale dell'utente originale. Tutti i contenuti delle cassette postali, ad esempio messaggi di posta elettronica, contatti e file vengono eliminati definitivamente.
- Una cassetta postale eliminata temporaneamente viene eliminata utilizzando **Remove-Mailbox-PermanentlyDelete**.

Gli scenari di eliminazione precedenti presuppongono che la cassetta postale dell'utente non sia in uno degli Stati di blocco, come il blocco per controversia legale o la conservazione di eDiscovery. Se è presente qualsiasi tipo di blocco sulla cassetta postale, la cassetta postale non può essere eliminata. Per tutti i tipi di destinatari degli utenti di posta, tutte le impostazioni di [blocco](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) vengono ignorate e non hanno alcun effetto su eliminazioni o eliminazioni.

## <a name="soft-deleted-and-hard-deleted-items"></a>Elementi eliminati temporaneamente e eliminati in modo irreversibile
Quando un utente elimina un elemento della cassetta postale, ad esempio un messaggio di posta elettronica, un contatto, un appuntamento di calendario o un'attività, l'elemento viene spostato nella cartella elementi ripristinabili e in una sottocartella denominata "Deletions". Si tratta di un'eliminazione morbida. La durata di conservazione degli elementi eliminati nella cartella Deletions dipende dal periodo di mantenimento degli elementi eliminati impostato per la cassetta postale. Una cassetta postale di Exchange Online conserva gli elementi eliminati per 14 giorni per impostazione predefinita, ma gli amministratori di Exchange Online possono modificare questa impostazione per aumentare il periodo fino a un massimo di 30 giorni. Per la procedura dettagliata per aumentare il periodo di conservazione degli elementi eliminati per una cassetta postale di Exchange Online, vedere [modificare la durata degli elementi eliminati in modo permanente per una cassetta postale di Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention). Gli utenti possono recuperare o eliminare gli elementi eliminati prima della scadenza del periodo di conservazione per un elemento eliminato. A tale scopo, utilizzano la funzionalità Recupera elementi eliminati in Microsoft Outlook o Outlook sul Web.

Se un utente elimina un elemento eliminato utilizzando la funzionalità Recupera elementi eliminati in Outlook o Outlook sul Web, questa operazione è nota come eliminazione definitiva. In Exchange Online, il ripristino di un singolo elemento è abilitato per impostazione predefinita al momento della creazione di una nuova cassetta postale, quindi un amministratore può comunque [recuperare](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) gli elementi eliminati definitivamente prima della scadenza del periodo di conservazione degli elementi eliminati. Inoltre, se il messaggio viene modificato da un utente o da un processo, le copie dell'elemento originale vengono conservate quando il ripristino del singolo elemento viene abilitato.

## <a name="page-zeroing"></a>Azzeramento delle pagine
L' *azzeramento* è un meccanismo di sicurezza che scrive gli zeri o un modello binario su dati eliminati in modo che i dati eliminati siano più difficili da recuperare. In Exchange Online, i database delle cassette postali utilizzano le *pagine* come unità di archiviazione e implementano un processo di sovrascrittura denominato *azzeramento pagine*. L'azzeramento delle pagine è abilitato per impostazione predefinita e non può essere disabilitato dai clienti o da Microsoft. Le operazioni di azzeramento delle pagine vengono registrate nei file di registro delle transazioni in modo che tutte le copie di un determinato database vengano azzerate a pagina in modo analogo. Se si azzera una pagina su una copia attiva del database, la pagina verrà azzerata su copie passive del database.

L'azzeramento delle pagine scrive un modello binario su record eliminati definitivamente. Il modello di azzeramento delle pagine è specifico delle operazioni ESE (Extensible Storage Engine) (il nome del motore di database interno utilizzato dai server in Exchange Online) ed è diverso per le operazioni di run-time rispetto alle operazioni di manutenzione del database in background. La manutenzione in background del database è un processo che esegue continuamente il checksum e analizza ogni database. La sua funzione principale consiste nell'eseguire il checksum delle pagine del database, ma gestisce anche la pulizia dello spazio e l'azzeramento dei record e delle pagine che non sono state azzerate a causa di un arresto anomalo dell'archivio.

La tabella seguente elenca le sequenze di riempimento che corrispondono a specifiche operazioni runtime.

| Operazione runtime di ESE   | Sequenza di riempimento |
|--------------------------|--------------|
| Sostituisci                  | R            |
| Elimina record/valore lungo | D            |
| Spazio pagina liberato         | H            |


La tabella che segue elenca le sequenze di riempimento che corrispondono alle specifiche operazioni che avvengono durante le operazioni di manutenzione in background di ESE.

| Operazioni di manutenzione in background del database ESE | Motivo riempimento |
|-----------------------------------------------|--------------|
| Elimina record                                 | D            |
| Elimina valore lungo                             | L            |
| Spazio pagina liberato della pagina parzialmente utilizzata       | Z            |
| Spazio pagina liberato della pagina inutilizzata               | U            |


### <a name="page-zeroing-process"></a>Processo di azzeramento delle pagine
Il processo per l'azzeramento delle pagine dipende dallo scenario di eliminazione. La tabella seguente illustra gli scenari di eliminazione nel database e quando viene attivata la funzione di azzeramento delle pagine.

| Scenario di eliminazione dal database | Processo di ESE e tempi di azzeramento dei dati del database |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| L'elemento scade in base al periodo di conservazione degli elementi eliminati. | Un thread asincrono scrive una sequenza binaria sui dati eliminati. Questa azione si verifica entro pochi millisecondi dall'eliminazione del record. Se il processo di archiviazione si blocca mentre il lavoro di azzeramento asincrono è ancora in sospeso (o la pulizia dell'archivio versioni viene annullata a causa dello sviluppo dell'archivio versioni), l'azzeramento viene completato quando la manutenzione in background del database elabora quella sezione del database. |
| Scenario di visualizzazione: scadenza degli elementi dalla visualizzazione di Outlook/Outlook nella cartella Web (ad esempio, visualizzazione conversazione) | L'azzeramento dei dati avviene quando la manutenzione in background del database elabora questa sezione del database. |
| Spostare lo scenario cassetta postale/eliminazione cassetta postale: cassetta postale di origine eliminata (scadenza della cassetta postale eliminata) | L'azzeramento dei dati avviene quando la manutenzione in background del database elabora questa sezione del database. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Tipo di dati delle cassette postali senza azzeramento delle pagine
I tipi di dati delle cassette postali seguenti non dispongono di alcuna disposizione per l'azzeramento delle pagine:
- **Registri delle transazioni del database delle cassette postali** -quando i registri delle transazioni vengono eliminati come parte di operazioni normali, non esiste alcun processo per azzerare i blocchi nel file System in cui sono stati archiviati i file di registro eliminati. È probabile che il file System riutilizzerà rapidamente lo spazio libero per i log appena creati, ma non vi è alcuna garanzia che questo accada.
- **File di catalogo dell'indice di contenuto** -Exchange Online utilizza Search Foundation (noto anche come Fast) per la funzionalità di indicizzazione della ricerca. Il catalogo di indicizzazione della ricerca è costituito da diverse dozzine di file archiviati nello stesso volume del file di database delle cassette postali. Quando un messaggio viene eliminato in modo definitivo dal database delle cassette postali, il contenuto nel catalogo di ricerca ad esso associato non viene eliminato immediatamente. L'eliminazione del contenuto viene eseguita quando Search Foundation esegue un'ombreggiatura o un'unione master di molti file di catalogo di piccole dimensioni in un singolo file di dimensioni maggiori. Una volta completata l'unione master, i piccoli file del catalogo vengono eliminati. I blocchi in cui erano archiviati i file di catalogo eliminati non vengono azzerati.

## <a name="continuous-replication"></a>Replica continua
La replica continua (nota anche come log shipping and Replay) è la tecnologia in Exchange Online che consente di creare e gestire copie di ogni database delle cassette postali per fornire disponibilità elevata, resilienza del sito e ripristino di emergenza. La replica continua utilizza il supporto del ripristino dell'arresto anomalo del database di Exchange Server per fornire una tecnologia che esegua l'aggiornamento asincrono di una o più copie di un database delle cassette postali. Ogni server cassette postali registra gli aggiornamenti del database effettuati su un database attivo (ad esempio, attività di posta elettronica degli utenti) come record di log in un set sequenziale di file di registro delle transazioni di 1 MB. Questo set di file è denominato flusso di log. In una replica continua, il flusso di registro viene utilizzato anche per aggiornare in modo asincrono una o più copie di un database. Questa operazione viene eseguita trasmettendo i registri in una posizione contenente una copia passiva del database attivo e quindi rieseguendoli nella copia passiva del database. Se tutti i registri dal database attivo vengono riprodotti su una copia passiva del database, i due database sono equivalenti ed è attraverso questo processo che ogni modifica fisica apportata a un database attivo viene replicata in tutte le copie passive del database.

Qualsiasi eliminazione da un database delle cassette postali, sia che si tratti di una cassetta postale o di un'intera cassetta postale, sia che si tratti di un'eliminazione temporanea o di un'eliminazione definitiva, rappresenta una modifica fisica per il database attivo. L'azzeramento delle pagine comporta anche l'esecuzione di modifiche fisiche al database attivo. Tali modifiche vengono scritte nei file di registro tramite un processo denominato replica continua e quando tali file di registro vengono riprodotti in base alle copie passive del database, vengono apportate le stesse modifiche fisiche ai database passivi.