---
title: Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui record che semplificano l’implementazione di una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: 4b8209108564f0a75f8d70efecd57d2526d9face
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200547"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a>Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

>[!NOTE] 
> Poiché i record normativi bloccano la modifica, il controllo delle versioni dei record non è disponibile per i record normativi.

La possibilità di contrassegnare un documento come [record](records-management.md#records) e limitare le azioni che è possibile eseguire su di esso rappresenta un obiettivo essenziale per qualsiasi soluzione di gestione dei record. Tuttavia, la collaborazione potrebbe essere necessaria anche per le persone che creano versioni successive.

Ad esempio, può capitare di contrassegnare come record un contratto di vendita, e che successivamente sia necessario aggiornare il contratto con nuovi termini e contrassegnare l'ultima versione come nuovo record conservando comunque la versione precedente. Per scenari di questo tipo, SharePoint e OneDrive supportano il *controllo delle versioni dei record*. Le cartelle del blocco appunti di OneNote non supportano il controllo delle versioni dei record.

Per usare il controllo delle versioni dei record, è necessario prima di tutto [etichettare un documento e contrassegnarlo come record](declare-records.md). Una volta fatto ciò, accanto all'etichetta di conservazione viene visualizzata una proprietà del documento denominata *Stato del record*, con lo stato del record iniziale impostato su **Bloccato**. 

È possibile eseguire le operazioni seguenti:

  - **Modificare e conservare continuamente come record singole versioni del documento, sbloccando e bloccando la proprietà Stato del record.** Solo quando la proprietà **Stato del record** è impostata su **Bloccato** è una nuova versione del record conservata. Questo consente di ridurre il rischio di mantenere le versioni e le copie inutili del documento.

  - **Archiviare automaticamente i record in un archivio dei record sul posto all'interno della raccolta siti.** Ogni raccolta siti di SharePoint e OneDrive mantiene il contenuto nella propria raccolta di archiviazione. Le versioni dei record vengono archiviate nella cartella Record della raccolta.

  - **Conservare un documento sempre valido che contiene tutte le versioni.** Per impostazione predefinita, ogni documento di SharePoint e OneDrive ha una cronologia delle versioni disponibile nel menu dell’elemento. In questa cronologia delle versioni è possibile individuare facilmente le versioni record e visualizzare tali documenti.

Il controllo delle versioni del record è automaticamente disponibile per qualsiasi documento con un'etichetta di conservazione che contrassegna l'elemento come record. Quando un utente visualizza le proprietà del documento tramite il riquadro dei dettagli, può cambiare lo **Stato del record** da **Bloccato** a **Sbloccato**. Questa azione crea un record nella cartella Record della raccolta di archiviazione, dove rimane fino alla fine del periodo di conservazione. 

Quando il documento è sbloccato, qualsiasi utente con autorizzazioni di modifica standard può modificare il file. Tuttavia, gli utenti non possono eliminare il file, perché è ancora considerato un record. Una volta completato il processo di modifica, l'utente può quindi impostare lo **Stato del record** da **Sbloccato** a **Bloccato**, che impedisce ulteriori modifiche in questo stato.
<br/><br/>

![Proprietà Stato del record nel documento taggato come record](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a>Bloccare e sbloccare un record

Dopo aver applicato a un documento un'etichetta di conservazione che contrassegna un contenuto come record, qualsiasi utente con il livello di autorizzazione Collaborazione o inferiore può sbloccare un record o bloccare un record sbloccato.
<br/><br/>

![Lo stato del record mostra se il documento record è sbloccato](../media/recordversioning9.png)

Quando un utente sblocca un record, si verificano le operazioni seguenti:

1. Se la raccolta siti corrente non ha una raccolta di archiviazione, ne viene creata una.

2. Se nella raccolta di archiviazione non è presente una cartella Record, ne viene creata una.

3. Un’azione **Copia in** copia l'ultima versione del documento nella cartella Record. L'azione **Copia in** include solo la versione più recente e non quelle precedenti. Il documento copiato è ora considerato come versione record del documento e il suo nome file ha il formato: \[Titolo GUID Versione\#\]

4. La copia creata nella cartella Record viene aggiunta alla cronologia delle versioni del documento originale e questa versione riporta la parola **Record** nel campo Commenti.

5. Il documento originale è una nuova versione che può essere modificata ma non eliminata. La colonna della raccolta del documento **L’elemento è un record** mostra ancora il valore **Sì** perché il documento è ancora un record, anche se ora può essere modificato.

Quando un utente blocca un record, il documento originale torna a non essere modificabile. Ma è l'azione di sbloccare un record che ne copia una versione nella cartella Record della raccolta di archiviazione.

## <a name="record-versions"></a>Versioni del record

Ogni volta che un utente sblocca un record, la versione più recente viene copiata nella cartella Record della raccolta di archiviazione, che contiene il valore di **Record** nel campo **Commenti** della cronologia delle versioni.
<br/><br/>

![Record mostrato nella raccolta di archiviazione](../media/recordversioning10.png)

Per visualizzare la cronologia delle versioni, selezionare un documento nella raccolta documenti e quindi fare clic su **Cronologia delle versioni** nel menu dell’elemento.

## <a name="where-records-are-stored"></a>Dove vengono archiviati i record

I record vengono archiviati nella cartella Record della raccolta di archiviazione nel sito principale della raccolta siti. Nel riquadro di spostamento sinistro del sito principale scegliere **Contenuto del sito** \> **Raccolta di archiviazione**.
<br/><br/>

![Raccolta di archiviazione](../media/recordversioning11.png)

<br/><br/>

![Cartella Record nella raccolta di archiviazione](../media/recordversioning12.png)

La raccolta di archiviazione è visibile solo agli amministratori della raccolta siti. Inoltre, la raccolta di archiviazione non esiste per impostazione predefinita. Viene creata solo quando il contenuto soggetto a un'etichetta o a un criterio di conservazione viene eliminato per la prima volta nella raccolta siti.

## <a name="searching-the-audit-log-for-record-versioning-events"></a>Cercare nel log di controllo gli eventi di controllo delle versioni del record

Le azioni per bloccare e sbloccare i record vengono registrate nel log di controllo. È possibile cercare le attività specifiche **Stato del record modificato in Bloccato** e **Stato del record modificato in Sbloccato**, che si trovano nella sezione **Attività su file e pagine** nell'elenco a discesa **Attività** nella pagina **Ricerca log di controllo** nel centro sicurezza e conformità.
<br/><br/>

![Cercare nel log di controllo gli eventi di controllo delle versioni del record](../media/recordversioning13.png)

Per altre informazioni su come cercare questi eventi, vedere la sezione "Attività su file e pagine" in [Ricerche nel log di controllo Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Passaggi successivi

Per altri scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).
