---
title: Creare e gestire i casi di eDiscovery avanzati in Microsoft 365
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
description: In questo articolo viene descritto come creare e gestire i casi di eDiscovery avanzati. Il primo passaggio consiste nel creare un caso e iniziare a usare caratteristiche e funzionalità avanzate di eDiscovery.
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841623"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Creazione e gestione di un caso di eDiscovery avanzato

Dopo aver configurato Advanced eDiscovery e aver [assegnato le autorizzazioni ai responsabili di eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) nell'organizzazione che gestirà i casi, il passaggio successivo consiste nel creare e gestire un caso.

In questo articolo viene inoltre fornita una panoramica generale dell'utilizzo dei casi per gestire il flusso di lavoro avanzato di eDiscovery per un'indagine legale.

## <a name="create-a-case"></a>Creare un caso

Completare la procedura seguente per creare un caso e aggiungere membri. L'utente che crea il caso viene aggiunto automaticamente come membro.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e accedere con le credenziali per l'account utente a cui sono state assegnate le autorizzazioni di eDiscovery. I membri del gruppo di ruoli Gestione organizzazione possono anche creare casi avanzati di eDiscovery.

2. Nel riquadro di spostamento a sinistra del centro conformità di Microsoft 365 fare clic su **Mostra tutto**, quindi fare clic su **eDiscovery > avanzate**.

3. Nella pagina **Advanced eDiscovery** , fare clic sulla scheda **case** , quindi fare clic su **Crea un caso**.

4. Nella pagina **nuovo** riquadro a comparsa del caso di eDiscovery, assegnare un nome al caso (obbligatorio) e quindi digitare un numero di caso facoltativo e una descrizione. Il nome del caso deve essere univoco nell'organizzazione.

5. Fare clic su **Salva** per creare il caso.

   Viene creato il nuovo caso e viene visualizzata la scheda **Impostazioni** del nuovo caso.

6. Nella sezione **accesso & autorizzazioni** della scheda **Impostazioni** fare clic su **Seleziona** e quindi su **Aggiorna**.

7. Fare clic su **Aggiorna**.

8. Nella pagina **Gestisci** il riquadro a comparsa di questo caso, in **Manage members** fare clic su **Aggiungi** per aggiungere membri al caso.

9. Nell'elenco di utenti selezionare la casella di controllo accanto ai nomi degli utenti che si desidera aggiungere al caso. Come spiegato in precedenza, accertarsi che alle persone aggiunte al caso siano state assegnate le autorizzazioni di eDiscovery appropriate.

10. Dopo aver selezionato gli utenti da aggiungere come membri del caso, fare clic su **Aggiungi**.

11. Nella pagina **Gestisci** il riquadro a comparsa di questo caso, fare clic su **Salva** per salvare il nuovo elenco dei membri del caso.

12. Fare clic sulla scheda **Home** per passare alla Home page del case.

## <a name="manage-the-workflow"></a>Gestire il flusso di lavoro

Per iniziare a utilizzare Advanced eDiscovery, ecco un flusso di lavoro di base che si allinea con le [procedure di eDiscovery comuni](advanced-ediscovery-edrm.md). In ognuno di questi passaggi verranno evidenziate anche alcune funzionalità estese avanzate di eDiscovery che è possibile esplorare.

![Flusso di lavoro avanzato di eDiscovery](../media/AeDWorkflow.png)

1. **[Aggiungere depositari](add-custodians-to-case.md) e [origini dati non detentive](non-custodial-data-sources.md) al caso**. Il primo passaggio dopo la creazione di un caso consiste nell'aggiungere depositari. Un *custode* è una persona che ha il controllo amministrativo di un documento o di un file elettronico che potrebbe essere pertinente alla causa. È inoltre possibile aggiungere origini dati che non sono associate a un utente specifico, ma che potrebbero essere rilevanti per il caso.

   Di seguito sono riportate alcune operazioni che possono essere eseguite (o che è possibile eseguire) quando si aggiungono i depositari a un caso:

   - I dati nella cassetta postale di Exchange del custode, nell'account OneDrive e in tutti i gruppi di Microsoft teams o Yammer a cui il custode è membro possono essere "contrassegnati" come dati di custodia nel caso.
  
   - I dati del custode vengono reindicizzati (tramite un processo denominato *Advanced indicizzazione*). Questo consente di ottimizzare la ricerca nel passaggio successivo.
  
   - È possibile applicare un'esenzione ai dati del custode. Questo consente di conservare i dati che potrebbero essere rilevanti per il caso durante l'inchiesta.
  
   - È possibile associare altre origini dati a un custode (ad esempio, è possibile associare un sito di SharePoint o un gruppo di Microsoft 365 a un custode), in modo che i dati possano essere reindicizzati, conservati e ricercati, come i dati della cassetta postale o dell'account di OneDrive della banca depositaria.

   - È possibile utilizzare il [flusso di lavoro comunicazioni](managing-custodian-communications.md) in Advanced eDiscovery per inviare una notifica di conservazione legale ai depositari.

2. **[Cerca origini dati per i dati rilevanti per il caso](collecting-data-for-ediscovery.md)**. Dopo aver aggiunto depositari e origini dati non detentive a un caso, utilizzare lo strumento di ricerca incorporato per eseguire una ricerca in queste origini dati per i dati rilevanti per il caso. È possibile utilizzare parole chiave, proprietà e condizioni per [creare query di ricerca](building-search-queries.md) che restituiscono i risultati della ricerca con i dati più probabili rilevanti per il caso. È inoltre possibile:

   - Visualizzare le [statistiche di ricerca](search-statistics-in-advanced-ediscovery.md) che consentono di affinare una query di ricerca per restringere i risultati.

   - Visualizzare in anteprima i risultati della ricerca per verificare rapidamente se i dati rilevanti sono stati trovati.

   - Rivedere una query ed eseguire nuovamente la ricerca.

3. **[Aggiungere dati a un set di revisione](add-data-to-review-set.md)**. Dopo aver configurato e verificato che una ricerca restituisce i dati desiderati, il passaggio successivo consiste nell'aggiungere i risultati della ricerca a un set di revisione. Quando si aggiungono dati a un set di revisione, gli elementi vengono copiati dal percorso originale a un percorso di archiviazione di Azure sicuro. I dati vengono riindicizzati di nuovo per ottimizzare le ricerche accurate e veloci quando si esaminano e analizzano gli elementi nel set di revisione. Inoltre, è anche possibile [aggiungere dati non di Office 365 in un set di revisione](load-non-office-365-data-into-a-review-set.md).

   È inoltre disponibile un tipo speciale di recensione a cui è possibile aggiungere dati, denominato set di *recensioni di conversazione*. Questi tipi di recensioni consentono di fornire funzionalità di ricostruzione delle conversazioni per ricostruire, rivedere ed esportare conversazioni filettate come quelle di Microsoft teams. Per ulteriori informazioni, vedere [rivedere le conversazioni in Advanced eDiscovery](conversation-review-sets.md).

4. **Esaminare e analizzare i dati in un set di revisione**. Ora che i dati si trova in un set di revisione, è possibile utilizzare una vasta gamma di strumenti e funzionalità per visualizzare e analizzare i dati del caso con l'obiettivo di ridurre il set di dati a ciò che è più pertinente per il caso in cui si sta indagando. Ecco un elenco di alcuni strumenti e funzionalità che è possibile utilizzare durante questo processo.

   - [Visualizzare i documenti](view-documents-in-review-set.md). Ciò include la visualizzazione dei metadati per ogni documento in un set di revisione e la visualizzazione del documento nella versione nativa o nella versione di testo.

   - [Creare query e filtri](review-set-search.md). È possibile creare query di ricerca utilizzando vari criteri di ricerca (inclusa la possibilità di eseguire una ricerca in tutte le [proprietà dei metadati di file](document-metadata-fields-in-advanced-ediscovery.md)) per affinare ulteriormente e abbattere i dati del caso in elementi più rilevanti per il caso. È inoltre possibile utilizzare i filtri set di revisione per applicare rapidamente altre condizioni ai risultati di una query di ricerca per affinare ulteriormente i risultati. 

   - [Creare e utilizzare i tag](tagging-documents.md). È possibile applicare tag ai documenti in un set di revisione per identificare quali reattivi (o non rispondere al caso) e quindi utilizzare tali tag durante la creazione di query di ricerca per includere o escludere i documenti contrassegnati. È inoltre possibile contrassegnare per determinare i documenti da esportare.

   - [Annota e redigere i documenti](view-documents-in-review-set.md#annotate-view). È possibile utilizzare lo strumento annotazione in una recensione per annotare i documenti e il contenuto di redigere in documenti come prodotto di lavoro. Durante la revisione viene generata una versione in formato PDF di un documento annotato o redatto per ridurre il rischio di esportare la versione nativa di unredacted del documento.

   - [Analizzare i dati del caso](analyzing-data-in-review-set.md). La funzionalità di analisi in Advanced eDiscovery è potente. Dopo aver eseguito l'analisi sui dati del set di revisione, vengono eseguiti i risultati analizzati, ad esempio, il rilevamento di duplicati, il threading di posta elettronica e i temi che possono contribuire a ridurre il volume di documenti che è necessario esaminare. È inoltre possibile generare un report di analisi che riepiloga il risultato dell'esecuzione di analisi. Come spiegato in precedenza, l'esecuzione di analisi esegue anche [il modello di rilevamento dei privilegi del procuratore client](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).

5. **Esportare e scaricare i dati del caso**. Un passaggio finale dopo la raccolta, la revisione e l'analisi dei dati del caso consiste nell'esportarlo da Advanced eDiscovery per la revisione esterna o per la verifica da parte di utenti esterni al team di analisi. L'esportazione dei dati è un processo in due passaggi. Il primo passaggio consiste nell' [esportare](export-documents-from-review-set.md) i dati dall'insieme di revisione e copiarli in una posizione di archiviazione di Azure diversa (uno fornito da Microsoft o da uno gestito dall'organizzazione). Utilizzare quindi Esplora archivi di Azure per [scaricare](download-export-jobs.md) i dati in un computer locale. Oltre ai file di dati esportati, il contenuto del pacchetto di esportazione contiene anche un rapporto di esportazione, un rapporto riepilogativo e un report di errore.
