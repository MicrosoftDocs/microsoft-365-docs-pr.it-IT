---
title: Creare e gestire casi di Advanced eDiscovery in Microsoft 365
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
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come creare e gestire i casi di Advanced eDiscovery. Il primo passaggio consiste nel creare un caso e iniziare a usare le funzionalità e le funzionalità di Advanced eDiscovery.
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841623"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Creare e gestire un caso di Advanced eDiscovery

Dopo aver impostato Advanced eDiscovery e aver assegnato le autorizzazioni ai responsabili di [eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) nell'organizzazione che gestiranno i casi, il passaggio successivo consiste nel creare e gestire un caso.

In questo articolo viene inoltre fornita una panoramica generale dell'utilizzo dei casi per gestire il flusso di lavoro advanced eDiscovery per un'indagine legale.

## <a name="create-a-case"></a>Creare un caso

Completare la procedura seguente per creare un caso e aggiungere membri. L'utente che crea il caso viene aggiunto automaticamente come membro.

1. Accedere utilizzando le credenziali per l'account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) autorizzazioni di eDiscovery. I membri del gruppo di ruoli Gestione organizzazione possono anche creare casi di Advanced eDiscovery.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365 fare clic su Mostra tutto e quindi su **eDiscovery > Avanzate.**

3. Nella pagina **Advanced eDiscovery** fare clic sulla **scheda Casi** e quindi su Crea **un caso.**

4. Nella pagina riquadro a comparsa Nuovo **caso di eDiscovery** assegnare un nome al caso (obbligatorio), quindi digitare un numero e una descrizione facoltativi. Il nome del caso deve essere univoco nell'organizzazione.

5. Fare **clic su** Salva per creare il caso.

   Il nuovo caso viene creato e **viene visualizzata** la scheda Impostazioni nel nuovo caso.

6. Nel riquadro **Autorizzazioni &** accesso nella **scheda** Impostazioni fare clic su **Seleziona** e quindi su **Aggiorna.**

7. Fare clic su **Aggiorna**.

8. Nella pagina **Gestisci questo caso** a comparsa, in Gestisci **membri,** fare clic su **Aggiungi** per aggiungere membri al caso.

9. Nell'elenco di persone selezionare la casella di controllo accanto ai nomi delle persone che si desidera aggiungere al caso. Come spiegato in precedenza, assicurarsi che alle persone che si aggiungono al caso siano state assegnate le autorizzazioni di eDiscovery appropriate.

10. Dopo aver selezionato le persone da aggiungere come membri del caso, fare clic su **Aggiungi.**

11. Nella pagina **Gestisci questo caso** a comparsa fare clic su **Salva** per salvare il nuovo elenco di membri del caso.

12. Fare clic **sulla scheda Home** per passare alla home page del caso.

## <a name="manage-the-workflow"></a>Gestire il flusso di lavoro

Per iniziare a usare Advanced eDiscovery, ecco un flusso di lavoro di base in linea con [le procedure comuni di eDiscovery.](advanced-ediscovery-edrm.md) In ognuno di questi passaggi, verranno evidenziate anche alcune funzionalità avanzate di Advanced eDiscovery che è possibile esplorare.

![Flusso di lavoro advanced eDiscovery](../media/AeDWorkflow.png)

1. **[Aggiungere al](add-custodians-to-case.md) [](non-custodial-data-sources.md)** caso i responsabile e le origini dati non di tipo responsabile. Il primo passaggio dopo la creazione di un caso consiste nell'aggiungere i responsabile. Un *responsabile è* una persona che ha il controllo amministrativo di un documento o di un file elettronico che può essere rilevante per il caso. È inoltre possibile aggiungere origini dati non associate a un utente specifico, ma che potrebbero essere rilevanti per il caso.

   Ecco alcune operazioni che si verificano (o che è possibile eseguire) quando si aggiungono i responsabile a un caso:

   - I dati nella cassetta postale di Exchange del responsabile, nell'account OneDrive e in qualsiasi gruppo di Microsoft Teams o Yammer di cui il responsabile è membro possono essere "contrassegnati" come dati di responsabile nel caso.
  
   - I dati dei responsabile vengono reindicizzati (tramite un processo denominato *indicizzazione avanzata).* Ciò consente di ottimizzare la ricerca nel passaggio successivo.
  
   - È possibile impostare un blocco sui dati dei depositario. In questo modo vengono mantenuti i dati che potrebbero essere rilevanti per il caso durante l'indagine.
  
   - È possibile associare altre origini dati a un responsabile (ad esempio, è possibile associare un sito di SharePoint o un gruppo di Microsoft 365 a un responsabile) in modo che questi dati possano essere reindicizzati, messi in attesa e ricercati, proprio come i dati nella cassetta postale del responsabile o nell'account di OneDrive.

   - È possibile utilizzare il flusso [di lavoro delle](managing-custodian-communications.md) comunicazioni in Advanced eDiscovery per inviare una notifica di blocco a un responsabile.

2. **[Cercare i dati rilevanti per il caso nelle origini dati.](collecting-data-for-ediscovery.md)** Dopo aver aggiunto i responsabile e le origini dati non di tipo responsabile a un caso, utilizzare lo strumento di ricerca incorporato per cercare in tali origini dati i dati che potrebbero essere rilevanti per il caso. È possibile utilizzare parole chiave, proprietà e condizioni per creare [query](building-search-queries.md) di ricerca che restituiscono risultati di ricerca con i dati più rilevanti per il caso. È inoltre possibile:

   - Visualizzare [le statistiche di](search-statistics-in-advanced-ediscovery.md) ricerca che consentono di perfezionare una query di ricerca per restringere i risultati.

   - Visualizzare in anteprima i risultati della ricerca per verificare rapidamente se vengono trovati i dati pertinenti.

   - Rivedere una query ed eseguire di nuovo la ricerca.

3. **[Aggiungere dati a un insieme da rivedere.](add-data-to-review-set.md)** Dopo aver configurato e verificato che una ricerca restituisca i dati desiderati, il passaggio successivo consiste nell'aggiungere i risultati della ricerca a un insieme da rivedere. Quando si aggiungono dati a un insieme da rivedere, gli elementi vengono copiati dalla posizione originale in una posizione sicura di Archiviazione di Azure. I dati vengono reindicizzati per ottimizzare le ricerche complete e veloci durante la revisione e l'analisi degli elementi nel set di recensioni. Inoltre, è anche possibile [aggiungere dati non di Office 365 in un insieme da rivedere.](load-non-office-365-data-into-a-review-set.md)

   Esiste anche un tipo speciale di insieme di recensioni a cui è possibile aggiungere dati, denominato insieme *di revisione della conversazione.* Questi tipi di set di recensioni forniscono funzionalità di ricostruzione delle conversazioni per ricostruire, rivedere ed esportare conversazioni in thread come quelle in Microsoft Teams. Per ulteriori informazioni, vedere [Esaminare le conversazioni in Advanced eDiscovery.](conversation-review-sets.md)

4. **Esaminare e analizzare i dati in un insieme da rivedere.** Ora che i dati sono in un insieme da rivedere, è possibile utilizzare un'ampia gamma di strumenti e funzionalità per visualizzare e analizzare i dati del caso con l'obiettivo di ridurre il set di dati agli elementi più rilevanti per il caso in cui si sta analizzando. Ecco un elenco di alcuni strumenti e funzionalità che puoi usare durante questo processo.

   - [Visualizzare i documenti.](view-documents-in-review-set.md) Sono inclusi la visualizzazione dei metadati per ogni documento in un insieme da rivedere e la visualizzazione del documento nella versione nativa o nella versione di testo.

   - [Creare query e filtri.](review-set-search.md) È possibile creare query di ricerca utilizzando vari criteri di ricerca (inclusa la possibilità di eseguire ricerche in tutte le proprietà dei metadati dei [file)](document-metadata-fields-in-advanced-ediscovery.md)per perfezionare ulteriormente e culnare i dati del caso in base ai più rilevanti per il caso. È inoltre possibile utilizzare i filtri impostati per la revisione per applicare rapidamente altre condizioni ai risultati di una query di ricerca per perfezionare ulteriormente tali risultati. 

   - [Creare e utilizzare tag.](tagging-documents.md) È possibile applicare tag ai documenti in un insieme da rivedere per identificare quali sono reattivi (o non reattivi al caso) e quindi utilizzarli durante la creazione di query di ricerca per includere o escludere i documenti contrassegnati. È inoltre possibile aggiungere tag per determinare quali documenti esportare.

   - [Annotare e redigere documenti.](view-documents-in-review-set.md#annotate-view) È possibile utilizzare lo strumento di annotazione in una recensione per annotare i documenti e redigere il contenuto nei documenti come prodotto di lavoro. Durante la revisione viene generata una versione PDF di un documento annotato o redatto per ridurre il rischio di esportare la versione nativa non corretta del documento.

   - [Analizzare i dati del caso.](analyzing-data-in-review-set.md) La funzionalità di analisi in Advanced eDiscovery è potente. Dopo aver eseguito l'analisi sui dati nel set da rivedere, viene eseguita un'analisi come il rilevamento quasi duplicato, il threading della posta elettronica e i temi che consentono di ridurre il volume di documenti da esaminare. Vengono inoltre generati report di analisi che riepilogano il risultato dell'esecuzione dell'analisi. Come spiegato in precedenza, l'esecuzione dell'analisi esegue anche il modello di rilevamento dei [privilegi avvocato-client.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Esportare e scaricare i dati del caso.** Un passaggio finale dopo la raccolta, la revisione e l'analisi dei dati del caso consiste nell'esportarlo da Advanced eDiscovery per la revisione esterna o per la revisione da parte di persone esterne al team di indagine. L'esportazione dei dati è un processo in due passaggi. Il primo passaggio [](export-documents-from-review-set.md) consiste nell'esportare i dati dall'insieme da rivedere e copiare i dati in un percorso diverso di Archiviazione di Azure (uno fornito da Microsoft o uno gestito dall'organizzazione). Usare Quindi Azure Storage Explorer per [scaricare](download-export-jobs.md) i dati in un computer locale. Oltre ai file di dati esportati, il pacchetto di esportazione contiene anche un rapporto di esportazione, un rapporto riepilogativo e un rapporto errori.
