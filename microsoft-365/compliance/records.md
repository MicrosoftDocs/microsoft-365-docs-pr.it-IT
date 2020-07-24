---
title: Informazioni sui record
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
description: Informazioni sui record utili per implementare una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372521"
---
# <a name="learn-about-records"></a>Informazioni sui record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

La gestione dei record in Microsoft 365 consente alle organizzazioni di conformarsi alle politiche aziendali e agli obblighi legali o normativi, riducendo inoltre i rischi e le responsabilità legali.

Quando un contenuto viene contrassegnato come record:

- Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Vengono registrate altre attività relative all'elemento.

- Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.

Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record. È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.

Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Confronto tra le restrizioni relative alle azioni consentite o bloccate

Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record. 

Un'etichetta di conservazione standard include la configurazione per mantenere i dati senza contrassegnare il contenuto come record.

>[!NOTE] 
> Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange. Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](#record-versioning), che non è supportato per gli elementi di Exchange. Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.


|Azione| Etichetta di conservazione |Record: bloccato| Record: sbloccato|
|:-----|:-----|:-----|:-----|:-----|
|Modifica contenuti|Consentito | **Bloccato** | Consentito|
|Modifica le proprietà, tra cui Rinomina|Consentito |Consentito | Consentito|
|Elimina|Consentito <sup>1</sup> |**Bloccato** | **Bloccato**|
|Copia|Consentito |Consentito | Consentito|
|Sposta all'interno del container <sup>2</sup>|Consentito |Consentito | Consentito|
|Sposta tra container <sup>2</sup>|Consentito |Consentito se mai sbloccato | Consentito|
|Apri/leggi|Consentito |Consentito | Consentito|
|Cambia etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container|
|Rimuovi etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container|

Note a piè di pagina:

<sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.

Messaggio che un utente vede se tenta di eliminare un documento con etichetta in SharePoint:

![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.


## <a name="using-retention-labels-to-declare-records"></a>Usare le etichette di conservazione per dichiarare i record

Quando si crea un'etichetta di conservazione, si può scegliere di usarla per contrassegnare il contenuto come record:

1. Nel Centro conformità Microsoft 365 passare a **Gestione record** \> **Piano di archiviazione**. Nella pagina **Piano di archiviazione**, selezionare **Crea un'etichetta**.

2. Nella pagina **Impostazioni etichetta** della procedura guidata scegliere l'opzione di impostazione dell'etichetta di conservazione per contrassegnare il contenuto come record.
    
   ![Fare clic sulla casella di controllo Utilizza l'etichetta per contrassegnare il contenuto come Record](../media/recordversioning6.png)

3. Applicare l'etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario. Per istruzioni:
    
    - [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)
    
    - [Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a>Applicare l'etichetta di conservazione configurata al contenuto

Quando le etichette di conservazione che classificano il contenuto come record vengono rese disponibili agli utenti per applicarle nelle app:

- Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette. 
- Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.

Esempio di documento contrassegnato come record da un'etichetta di conservazione:

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="record-versioning"></a>Controllo delle versioni del record

La possibilità di contrassegnare un documento come record e limitare le azioni che è possibile eseguire sul record rappresenta un obiettivo essenziale per qualsiasi soluzione di gestione dei record. Tuttavia, la collaborazione potrebbe essere necessaria anche per le persone che creano versioni successive.

Ad esempio, può capitare di contrassegnare come record un contratto di vendita, e che successivamente sia necessario aggiornare il contratto con nuovi termini e contrassegnare l'ultima versione come nuovo record conservando comunque la versione precedente. Per scenari di questo tipo, SharePoint e OneDrive supportano il *controllo delle versioni dei record*. Le cartelle del blocco appunti di OneNote non supportano il controllo delle versioni dei record.

Per usare il controllo delle versioni dei record, è necessario prima di tutto etichettare un documento e contrassegnarlo come record. Una volta fatto ciò, accanto all'etichetta di conservazione viene visualizzata una proprietà del documento denominata *Stato del record*, con lo stato del record iniziale impostato su **Bloccato**. 

È possibile eseguire le operazioni seguenti:

  - **Modificare e conservare continuamente come record singole versioni del documento, sbloccando e bloccando la proprietà Stato del record.** Solo quando la proprietà **Stato del record** è impostata su **Bloccato** è una nuova versione del record conservata. Questo consente di ridurre il rischio di mantenere le versioni e le copie inutili del documento.

  - **Archiviare automaticamente i record in un archivio dei record sul posto all'interno della raccolta siti.** Ogni raccolta siti di SharePoint e OneDrive mantiene il contenuto nella propria raccolta di archiviazione. Le versioni dei record vengono archiviate nella cartella Record della raccolta.

  - **Conservare un documento sempre valido che contiene tutte le versioni.** Per impostazione predefinita, ogni documento di SharePoint e OneDrive ha una cronologia delle versioni disponibile nel menu dell’elemento. In questa cronologia delle versioni è possibile individuare facilmente le versioni record e visualizzare tali documenti.

Il controllo delle versioni del record è automaticamente disponibile per qualsiasi documento con un'etichetta di conservazione che contrassegna l'elemento come record. Quando un utente visualizza le proprietà del documento tramite il riquadro dei dettagli, può cambiare lo **Stato del record** da **Bloccato** a **Sbloccato**. Questa azione crea un record nella cartella Record della raccolta di archiviazione, dove rimane fino alla fine del periodo di conservazione. 

Quando il documento è sbloccato, qualsiasi utente con autorizzazioni di modifica standard può modificare il file. Tuttavia, gli utenti non possono eliminare il file, perché è ancora considerato un record. Una volta completato il processo di modifica, l'utente può quindi impostare lo **Stato del record** da **Sbloccato** a **Bloccato**, che impedisce ulteriori modifiche in questo stato.
<br/><br/>

![Proprietà Stato del record nel documento taggato come record](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Bloccare e sbloccare un record

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

### <a name="record-versions"></a>Versioni del record

Ogni volta che un utente sblocca un record, la versione più recente viene copiata nella cartella Record della raccolta di archiviazione, che contiene il valore di **Record** nel campo **Commenti** della cronologia delle versioni.
<br/><br/>

![Record mostrato nella raccolta di archiviazione](../media/recordversioning10.png)

Per visualizzare la cronologia delle versioni, selezionare un documento nella raccolta documenti e quindi fare clic su **Cronologia delle versioni** nel menu dell’elemento.

### <a name="where-records-are-stored"></a>Dove vengono archiviati i record

I record vengono archiviati nella cartella Record della raccolta di archiviazione nel sito principale della raccolta siti. Nel riquadro di spostamento sinistro del sito principale scegliere **Contenuto del sito** \> **Raccolta di archiviazione**.
<br/><br/>

![Raccolta di archiviazione](../media/recordversioning11.png)

<br/><br/>

![Cartella Record nella raccolta di archiviazione](../media/recordversioning12.png)

La raccolta di archiviazione è visibile solo agli amministratori della raccolta siti. Inoltre, la raccolta di archiviazione non esiste per impostazione predefinita. Viene creata solo quando il contenuto soggetto a un'etichetta o a un criterio di conservazione viene eliminato per la prima volta nella raccolta siti.

### <a name="searching-the-audit-log-for-record-versioning-events"></a>Cercare nel log di controllo gli eventi di controllo delle versioni del record

Le azioni per bloccare e sbloccare i record vengono registrate nel log di controllo. È possibile cercare le attività specifiche **Stato del record modificato in Bloccato** e **Stato del record modificato in Sbloccato**, che si trovano nella sezione **Attività su file e pagine** nell'elenco a discesa **Attività** nella pagina **Ricerca log di controllo** nel centro sicurezza e conformità.
<br/><br/>

![Cercare nel log di controllo gli eventi di controllo delle versioni del record](../media/recordversioning13.png)

Per altre informazioni su come cercare questi eventi, vedere la sezione "Attività su file e pagine" in [Ricerche nel log di controllo Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Passaggi successivi

Se non si hanno ancora etichette di conservazione da usare per la gestione dei record, vedere [Introduzione ai criteri e alle etichette di conservazione](get-started-with-retention.md).

Per ulteriori informazioni sull'eliminazone dei record, vedere [Eliminazione dei record](disposition.md).
