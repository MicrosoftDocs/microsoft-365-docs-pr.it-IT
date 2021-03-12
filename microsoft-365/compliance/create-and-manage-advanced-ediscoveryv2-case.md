---
title: Creare e gestire casi di eDiscovery avanzato in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365initiative-scenario
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come creare e gestire i casi di Advanced eDiscovery. Il primo passaggio consiste nel creare un caso e iniziare a usare funzionalità e funzionalità avanzate di eDiscovery.
ms.openlocfilehash: 80cfe31a86060cb3603a101b314273cc67750bd8
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727543"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Creare e gestire un caso advanced eDiscovery

Dopo aver impostato Advanced eDiscovery e aver assegnato le autorizzazioni ai responsabili [di eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) nell'organizzazione che gestiranno i casi, il passaggio successivo consiste nel creare e gestire un caso.

In questo articolo viene inoltre fornita una panoramica generale dell'utilizzo dei casi per gestire il flusso di lavoro advanced eDiscovery per un'indagine legale.

## <a name="create-a-case"></a>Creare un caso

Completare la procedura seguente per creare un caso e aggiungere membri. L'utente che crea il caso viene aggiunto automaticamente come membro.

1. Accedere a [https://compliance.microsoft.com](https://compliance.microsoft.com) e accedere utilizzando le credenziali per l'account utente a cui sono state assegnate le autorizzazioni di eDiscovery. I membri del gruppo di ruoli Gestione organizzazione possono inoltre creare casi di Advanced eDiscovery.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365 fare clic su **Mostra** tutto e quindi su **eDiscovery > avanzate**.

3. Nella pagina **Advanced eDiscovery** fare clic sulla **scheda Cases** e quindi su Create **a case.**

4. Nella pagina riquadro a comparsa **Nuovo caso di eDiscovery** assegnare un nome al caso (obbligatorio), quindi digitare un numero e una descrizione facoltativi per il caso. Il nome del caso deve essere univoco nell'organizzazione.

5. Fare **clic su** Salva per creare il caso.

   Il nuovo caso viene creato e **viene visualizzata** la scheda Impostazioni nel nuovo caso.

6. Nel riquadro **Autorizzazioni &** accesso nella **scheda Impostazioni** fare clic su **Seleziona** e quindi su **Aggiorna.**

7. Fare clic su **Aggiorna**.

8. Nella pagina a comparsa Gestisci **questo caso,** in **Gestisci membri,** fare clic su **Aggiungi** per aggiungere membri al caso.

9. Nell'elenco delle persone selezionare la casella di controllo accanto ai nomi delle persone che si desidera aggiungere al caso. Come spiegato in precedenza, assicurarsi che alle persone che si aggiungono al caso siano state assegnate le autorizzazioni di eDiscovery appropriate.

10. Dopo aver selezionato le persone da aggiungere come membri del caso, fare clic su **Aggiungi.**

11. Nella pagina **a comparsa Gestisci questo caso** fare clic su **Salva** per salvare il nuovo elenco di membri del caso.

12. Fare clic **sulla scheda Home** per passare alla home page del caso.

## <a name="manage-the-workflow"></a>Gestire il flusso di lavoro

Per iniziare a usare Advanced eDiscovery, ecco un flusso di lavoro di base in linea con [le procedure comuni di eDiscovery.](advanced-ediscovery-edrm.md) In ognuno di questi passaggi verranno evidenziate anche alcune funzionalità avanzate di eDiscovery che è possibile esplorare.

![Flusso di lavoro advanced eDiscovery](../media/AeDWorkflow.png)

1. **[Aggiungere i custodi](add-custodians-to-case.md) e le origini dati [non depositario](non-custodial-data-sources.md) al caso**. Il primo passaggio dopo la creazione di un caso consiste nell'aggiungere i custodi. Un *responsabile è* una persona che ha il controllo amministrativo di un documento o di un file elettronico che può essere rilevante per il caso. Inoltre, è possibile aggiungere origini dati non associate a un utente specifico, ma che potrebbero essere rilevanti per il caso.

   Ecco alcune operazioni che si verificano (o che è possibile eseguire) quando si aggiungono i custodi a un caso:

   - I dati nella cassetta postale di Exchange del responsabile, nell'account OneDrive e in qualsiasi gruppo di Microsoft Teams o Yammer di cui il responsabile è membro possono essere "contrassegnati" come dati di custodia nel caso.
  
   - I dati di custodia vengono reindicizzati (tramite un processo denominato *indicizzazione avanzata).* Ciò consente di ottimizzare la ricerca nel passaggio successivo.
  
   - È possibile impostare un blocco sui dati del responsabile. In questo modo vengono mantenuti i dati che possono essere rilevanti per il caso durante l'indagine.
  
   - È possibile associare altre origini dati a un responsabile(ad esempio, è possibile associare un sito di SharePoint o un gruppo di Microsoft 365 a un responsabile) in modo che questi dati possano essere reindicizzati, messi in attesa e ricercati, proprio come i dati nella cassetta postale del responsabile o nell'account OneDrive.

   - È possibile utilizzare il flusso [di lavoro delle comunicazioni](managing-custodian-communications.md) in Advanced eDiscovery per inviare una notifica di blocco legale ai custodi.

2. **[Cercare nelle origini dati i dati rilevanti per il caso](collecting-data-for-ediscovery.md)**. Dopo aver aggiunto i custodi e le origini dati non di custodia a un caso, utilizzare lo strumento di ricerca incorporato per cercare in tali origini dati i dati che potrebbero essere rilevanti per il caso. Le parole chiave, le proprietà e le condizioni vengono utilizzate per creare [query](building-search-queries.md) di ricerca che restituiscono risultati di ricerca con i dati più rilevanti per il caso. È inoltre possibile:

   - Visualizzare [le statistiche di](search-statistics-in-advanced-ediscovery.md) ricerca che consentono di perfezionare una query di ricerca per restringere i risultati.

   - Visualizzare in anteprima i risultati della ricerca per verificare rapidamente se vengono trovati i dati pertinenti.

   - Rivedere una query ed eseguire di nuovo la ricerca.

3. **[Aggiungere dati a un set di revisione](add-data-to-review-set.md)**. Dopo aver configurato e verificato che una ricerca restituisca i dati desiderati, il passaggio successivo consiste nell'aggiungere i risultati della ricerca a un set di recensioni. Quando si aggiungono dati a un set di revisione, gli elementi vengono copiati dalla posizione originale in una posizione sicura di Archiviazione di Azure. I dati vengono reindicizzati per ottimizzarlo per ricerche approfondite e veloci durante la revisione e l'analisi degli elementi nel set di recensioni. Inoltre, è anche possibile [aggiungere dati non di Office 365 in un set di recensioni.](load-non-office-365-data-into-a-review-set.md)

   Esiste anche un tipo speciale di set di recensioni a cui è possibile aggiungere dati, denominato insieme *di revisione delle conversazioni.* Questi tipi di set di recensioni offrono funzionalità di ricostruzione delle conversazioni per ricostruire, rivedere ed esportare conversazioni a thread come quelle in Microsoft Teams. Per ulteriori informazioni, vedere [Review conversations in Advanced eDiscovery.](conversation-review-sets.md)

4. **Esaminare e analizzare i dati in un set di recensioni.** Ora che i dati sono in un set di revisione, è possibile utilizzare un'ampia gamma di strumenti e funzionalità per visualizzare e analizzare i dati del caso con l'obiettivo di ridurre il set di dati a ciò che è più rilevante per il caso in esame. Ecco un elenco di alcuni strumenti e funzionalità che puoi usare durante questo processo.

   - [Visualizzare i documenti](view-documents-in-review-set.md). Ciò include la visualizzazione dei metadati per ogni documento in un set di revisioni e la visualizzazione del documento nella versione nativa o nella versione di testo.

   - [Creare query e filtri](review-set-search.md). È possibile creare query di ricerca utilizzando vari criteri di ricerca (inclusa la possibilità di eseguire ricerche in tutte le proprietà dei metadati [dei file)](document-metadata-fields-in-advanced-ediscovery.md)per affinare ulteriormente e aggiungere i dati del caso a ciò che è più rilevante per il caso. È inoltre possibile utilizzare i filtri dei set di revisione per applicare rapidamente altre condizioni ai risultati di una query di ricerca per affinare ulteriormente tali risultati. 

   - [Creare e utilizzare tag](tagging-documents.md). È possibile applicare tag ai documenti in un set di revisioni per identificare quali sono reattivi (o non reattivi al caso) e quindi utilizzarli durante la creazione di query di ricerca per includere o escludere i documenti con tag. È inoltre possibile aggiungere tag per determinare quali documenti esportare.

   - [Annotare e redigere documenti](view-documents-in-review-set.md#annotate-view). È possibile utilizzare lo strumento di annotazione in una revisione per annotare i documenti e redigere il contenuto nei documenti come prodotto di lavoro. Durante la revisione viene generata una versione PDF di un documento annotato o redatto per ridurre il rischio di esportare la versione nativa non modificata del documento.

   - [Analizzare i dati del caso](analyzing-data-in-review-set.md). La funzionalità di analisi in Advanced eDiscovery è potente. Dopo aver eseguito l'analisi sui dati nel set di revisione, eseguono analisi come il rilevamento quasi dei duplicati, il threading della posta elettronica e i temi che consentono di ridurre il volume di documenti da esaminare. Vengono inoltre generati report di analisi che riepilogano il risultato dell'esecuzione dell'analisi. Come spiegato in precedenza, l'esecuzione dell'analisi esegue anche il modello di rilevamento [dei privilegi avvocato-client.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Esportare e scaricare i dati del caso**. Un passaggio finale dopo la raccolta, la revisione e l'analisi dei dati dei casi consiste nell'esportarlo da Advanced eDiscovery per la revisione esterna o per la revisione da parte di persone esterne al team di indagine. L'esportazione dei dati è un processo in due passaggi. Il primo passaggio [](export-documents-from-review-set.md) consiste nell'esportare i dati dal set di revisione e copiare i dati in un percorso di archiviazione di Azure diverso (uno fornito da Microsoft o uno gestito dall'organizzazione). Quindi si usa Azure Storage Explorer per [scaricare](download-export-jobs.md) i dati in un computer locale. Oltre ai file di dati esportati, il contenuto del pacchetto di esportazione contiene anche un report di esportazione, un rapporto riepilogativo e un rapporto errori.
