---
title: Panoramica dei record
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
description: Per implementare una strategia di gestione dei record nella tua organizzazione Microsoft o Office 365, usare etichette di conservazione che dichiarino un contenuto come record. Quindi pubblicare o applicare automaticamente l'etichetta record di conservazione.
ms.openlocfilehash: d497f3e536a54226ad9e7b5bb9a399f66774c25e
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153834"
---
# <a name="overview-of-records"></a>Panoramica dei record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

La gestione dei record in Microsoft 365 consente alle organizzazioni di conformarsi alle politiche aziendali e agli obblighi legali e normativi, riducendo al contempo i rischi e le responsabilità legali.

A livelli elevati, dichiarare un contenuto come record significa che:

- L’elemento diventa non modificabile (non è possibile modificare o eliminare un record)

- Vengono registrate altre attività relative all'elemento

- I record vengono eliminati al termine del loro periodo di conservazione.

È possibile usare le [etichette di conservazione](labels.md) per classificare un contenuto come record. Dopo aver creato le etichette di conservazione che dichiarano i record, è possibile [pubblicare](labels.md#how-retention-labels-work-with-retention-label-policies) tali etichette, in modo che gli utenti possano usarle per classificare il contenuto come record, o [applicarle automaticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) al contenuto che si vuole classificare come record. È possibile usare le etichette di conservazione per dichiarare i record per implementare un'unica strategia di gestione dei record coerente in tutto Office 365. Altre funzionalità di gestione dei record, al contrario, ad esempio il Centro record, si applicano solo al contenuto di SharePoint Online.

Tenere presente quanto segue in relazione ai record:

  - **I record non sono modificabili.** Un'etichetta di conservazione che dichiara un contenuto come record può essere applicata al contenuto di Exchange, oltre a SharePoint e OneDrive for Business. Tuttavia, il [controllo delle versioni del record](#record-versioning) è disponibile solo in SharePoint e OneDrive e non in Exchange.

    In Exchange il contenuto etichettato come record non è modificabile fino all'eliminazione finale. Quando un elemento di Exchange viene classificato come record, si verificano i seguenti eventi:

    - L'elemento non può essere eliminato definitivamente.

    - L'elemento non può essere modificato.

    - L'etichetta non può essere modificata.

    - L'etichetta non può essere rimossa.

  - **Record e cartelle.** È possibile applicare un'etichetta di conservazione a una cartella di Exchange, SharePoint o OneDrive. Se una cartella viene etichettata come record e si sposta un elemento al suo interno, l'elemento viene identificato come record. Quando si sposta l'elemento dalla cartella, l'elemento rimarrà etichettato come record.

    Inoltre, se l'etichetta del record applicata a una cartella (in SharePoint e OneDrive) viene trasformata in etichetta di conservazione che non dichiara il contenuto come record, gli elementi nella cartella mantengono l'etichetta del record esistente.

    Per altre informazioni sull'applicazione di etichette di conservazione alle cartelle di SharePoint e OneDrive, vedere [Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).

  - **Non è possibile eliminare i record**. Se un utente prova a eliminare un record in Exchange, l'elemento viene spostato nella cartella Elementi ripristinabili, come descritto in [Funzionamento dei criteri di conservazione con il contenuto presente](retention-policies.md#content-in-mailboxes-and-public-folders).

    Se un utente prova a eliminare un record in SharePoint, viene visualizzato un messaggio di errore che indica che l'elemento non è stato eliminato e che rimane nella raccolta.

    ![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    Se un utente prova a eliminare un record in OneDrive, l'elemento viene spostato nella raccolta di archiviazione, come descritto in [Funzionamento dei criteri di conservazione con il contenuto presente](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites).

  - **Non è possibile rimuovere le etichette dei record.** Dopo aver applicato un'etichetta record a un elemento, solo l'amministratore di tale posizione, ad esempio l'amministratore di una raccolta siti di un sito di SharePoint, può rimuovere l’etichetta.

## <a name="using-retention-labels-to-declare-records"></a>Usare le etichette di conservazione per dichiarare i record

Quando si crea un'etichetta di conservazione, si può scegliere di usarla per classificare il contenuto come record. Per dichiarare il contenuto come record, eseguire le operazioni seguenti:

1. Creare un’etichetta di conservazione. Nel Centro conformità Microsoft 365 passare a **Gestione record** \> **Piano di archiviazione**. Nella pagina **Piano di archiviazione** fare clic su **Crea un'etichetta**.

2. Nella pagina **Impostazioni etichetta** della procedura guidata scegliere l'opzione di impostazione dell'etichetta di conservazione per dichiarare il contenuto come record.<br/>

   ![Fare clic sulla casella di controllo Utilizza l'etichetta per classificare il contenuto come Record](../media/recordversioning6.png)

3. [Pubblicare](labels.md#how-retention-labels-work-with-retention-label-policies) o [Applicare automaticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) l'etichetta di conservazione ai siti di SharePoint e/o agli account di OneDrive.

### <a name="applying-a-retention-label-to-content"></a>Applicare un'etichetta di conservazione al contenuto

Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare un'etichetta di conservazione a un messaggio di posta elettronica. Per il contenuto di SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare un'etichetta record al contenuto. Solo un amministratore della raccolta siti può rimuovere o modificare l’etichetta record dopo che è stata applicata. Come descritto in precedenza, un'etichetta di conservazione che classifica il contenuto come record può essere applicata automaticamente al contenuto.

Ecco l'aspetto di una etichetta record applicata a un documento in un sito di SharePoint o un account di OneDrive.
<br/><br/>

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="record-versioning"></a>Controllo delle versioni del record

Una parte essenziale della gestione record è la possibilità di dichiarare un documento come record e che tale record non sia modificabile. Allo stesso tempo, l’impossibilità di modificare i record impedisce la collaborazione al documento se si presenta la necessità di creare versioni successive. Ad esempio, può capitare di dichiarare come record un contratto di vendita, e che successivamente sia necessario aggiornare il contratto con nuovi termini e dichiarare l'ultima versione come nuovo record conservando comunque la versione precedente. Per scenari di questo tipo, in SharePoint Online e OneDrive for Business è ora supportato il *controllo delle versioni dei record*. Le cartelle del blocco appunti di OneNote non sono supportate.

Per usare il controllo delle versioni dei record, prima di tutto occorre usare il Centro conformità Microsoft 365 per creare e pubblicare etichette di conservazione che dichiarino i record in tutti i siti di SharePoint e/o account di OneDrive oppure pubblicarle in siti specifici di SharePoint e/o account di OneDrive. Il passaggio successivo consiste nell'applicare a un documento un'etichetta record di conservazione pubblicata. Una volta fatto ciò, accanto all'etichetta di conservazione viene visualizzata una proprietà del documento denominata *Stato del record*, con lo stato del record iniziale impostato su **Bloccato**. A questo punto, è possibile effettuare le operazioni seguenti:

  - **Modificare e dichiarare continuamente come record singole versioni del documento, sbloccando e bloccando la proprietà Stato del record.** Solo le versioni dichiarate come record vengono mantenute quando la proprietà **Stato del record** è impostata su **Bloccato**. Questo consente di ridurre il rischio di mantenere le versioni e le copie inutili del documento.

  - **Archiviare automaticamente i record in un archivio dei record sul posto all'interno della raccolta siti.** Ogni raccolta siti di SharePoint e OneDrive mantiene il contenuto nella propria raccolta di archiviazione. Le versioni dei record vengono archiviate nella cartella Record della raccolta.

  - **Conservare un documento sempre valido che contiene tutte le versioni.** Per impostazione predefinita, ogni documento di SharePoint e OneDrive ha una cronologia delle versioni disponibile nel menu dell’elemento. In questa cronologia delle versioni è possibile individuare facilmente le versioni record e visualizzare tali documenti.

Il controllo delle versioni del record è automaticamente disponibile per qualsiasi documento con un'etichetta di conservazione che dichiara l'elemento come record. Quando un utente visualizza le proprietà del documento tramite il riquadro dei dettagli, cambia lo **Stato del record** da **Bloccato** a **Sbloccato**. Questo singolo clic crea un record nella cartella Record della raccolta di archiviazione, dove rimane fino alla fine del periodo di conservazione. Quando il documento è sbloccato, qualsiasi utente con autorizzazioni può modificare il file. Tuttavia, gli utenti non possono eliminare il file, perché è considerato come un record dichiarato. Dopo aver apportato le modifiche necessarie, l'utente può quindi impostare lo **Stato del record** da **Sbloccato** a **Bloccato**, in modo che il documento venga di nuovo dichiarato come record e non possa essere modificato.
<br/><br/>

![Proprietà Stato del record nel documento taggato come record](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Bloccare e sbloccare un record

Una volta assegnata un'etichetta record di conservazione a un documento, qualsiasi utente con il livello di autorizzazione Collaborazione o inferiore può sbloccare un record o bloccare un record sbloccato.
<br/><br/>

![Lo stato del record mostra se il documento record è sbloccato](../media/recordversioning9.png)

Quando un utente sblocca un record, si verificano le operazioni seguenti:

1. Se la raccolta siti corrente non ha una raccolta di archiviazione, ne viene creata una.

2. Se nella raccolta di archiviazione non è presente una cartella Record, ne viene creata una.

3. Un’azione **Copia in** copia l'ultima versione del documento nella cartella Record. L'azione **Copia in** include solo la versione più recente e non quelle precedenti. Il documento copiato è ora considerato come versione record del documento e il suo nome file ha il formato: \[Titolo GUID Versione\#\]

4. La copia creata nella cartella Record viene aggiunta alla cronologia delle versioni del documento originale e questa versione riporta la parola **Record** nel campo Commenti.

5. Il documento originale è una nuova versione che può essere modificata (ma non eliminata). La colonna della raccolta del documento **L’elemento è un record** mostra ancora il valore **Sì** perché il documento è ancora considerato come un record, anche se ora può essere modificato.

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

Le azioni per bloccare e sbloccare i record vengono registrate nel log di controllo di Office 365. È possibile cercare le attività specifiche **Stato del record modificato in Bloccato** e **Stato del record modificato in Sbloccato**, che si trovano nella sezione **Attività su file e pagine** nell'elenco a discesa **Attività** nella pagina **Ricerca log di controllo** nel centro sicurezza e conformità.
<br/><br/>

![Cercare nel log di controllo gli eventi di controllo delle versioni del record](../media/recordversioning13.png)

Per altre informazioni su come cercare questi eventi, vedere la sezione "Attività su file e pagine" in [Ricerche nel log di controllo Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).
