---
title: Esportare e scaricare contenuto da un caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come esportare e scaricare contenuto da un caso di eDiscovery di base.
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551421"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Esportare il contenuto da un caso di eDiscovery di base

Dopo aver eseguito correttamente una ricerca, è possibile esportare i risultati della ricerca. Quando si esportano i risultati della ricerca, gli elementi della cassetta postale vengono scaricati nei file PST o come singoli messaggi. Quando si esporta contenuto da siti di SharePoint e OneDrive for business, vengono esportate copie dei documenti di Office native e di altri documenti. Un file results. csv che contiene informazioni su tutti gli elementi esportati e un file manifesto (in formato XML) che contiene informazioni su tutti i risultati di ricerca viene esportato.
  
È possibile esportare i risultati di una [singola ricerca associata a un caso](#export-the-results-of-a-single-search) oppure esportare i risultati di [più ricerche associate a un caso](#export-the-results-of-multiple-searches).
  
## <a name="export-the-results-of-a-single-search"></a>Esportare i risultati di una singola ricerca

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e accedere con le credenziali per l'account utente a cui sono state assegnate le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento a sinistra del centro conformità di Microsoft 365 fare clic su **Mostra tutto**e quindi su **eDiscovery > Core**.

3. Nella pagina **Core eDiscovery** selezionare il caso in cui si desidera esportare i risultati della ricerca e quindi fare clic su **Apri caso**.

4. Nella **Home** page del caso, fare clic sulla scheda **ricerche** .

5. Nell'elenco delle ricerche per il caso, fare clic sulla ricerca di cui si desidera esportare i risultati della ricerca, quindi fare clic su **Esporta risultati** nel riquadro a comparsa.

    Viene visualizzata la pagina dei **risultati di esportazione** . 

    ![Pagina Export results](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Il flusso di lavoro per esportare i risultati di una ricerca associata a un caso di eDiscovery di base è uguale all'esportazione dei risultati della ricerca per una ricerca nella pagina **Ricerca contenuto** . Per istruzioni dettagliate, vedere [Export content search results](export-search-results.md).

    > [!NOTE]
    > Quando si esportano i risultati della ricerca, è possibile abilitare la deduplicazione in modo che venga esportata una sola copia di un messaggio di posta elettronica anche se sono state trovate più istanze dello stesso messaggio nelle cassette postali di cui è stata eseguita la ricerca. Per ulteriori informazioni sulla deduplicazione e sulla modalità di identificazione degli elementi duplicati, vedere [de-duplication nei risultati della ricerca di eDiscovery](de-duplication-in-ediscovery-search-results.md).

    Dopo aver avviato l'esportazione, i risultati della ricerca sono pronti per il download, il che significa che vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft nel cloud Microsoft.
  
6. Fare clic sulla scheda **Esporta** per visualizzare l'elenco dei processi di esportazione per il caso.
  
    Potrebbe essere necessario fare clic su **Aggiorna** per aggiornare l'elenco dei processi di esportazione in modo che venga visualizzato il processo di esportazione creato. I processi di esportazione hanno lo stesso nome della ricerca corrispondente con **_Export** accodati al nome della ricerca.

7. Fare clic sul processo di esportazione creato per visualizzare le informazioni sullo stato nella pagina a comparsa. Queste informazioni includono la percentuale di elementi che sono stati trasferiti nel percorso di archiviazione di Azure.

8. Dopo aver trasferito tutti gli elementi, fare clic su **Scarica risultati** per scaricare i risultati della ricerca nel computer locale. Per ulteriori informazioni sul download dei risultati della ricerca, vedere passaggio 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>Esportare i risultati di più ricerche

Come alternativa all'esportazione dei risultati di una singola ricerca associata a un caso, è possibile esportare i risultati di più ricerche dallo stesso caso in un singolo processo di esportazione. L'esportazione dei risultati di più ricerche è più semplice e veloce rispetto all'esportazione dei risultati di una ricerca alla volta.
  
> [!NOTE]
> Non è possibile esportare i risultati di più ricerche se una di queste ricerche è stata configurata per la ricerca di percorsi in attesa.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e accedere con le credenziali per l'account utente a cui sono state assegnate le autorizzazioni di eDiscovery appropriate.

2. Nel riquadro di spostamento a sinistra del centro conformità di Microsoft 365 fare clic su **Mostra tutto**e quindi su **eDiscovery > Core**.

3. Nella pagina **Core eDiscovery** selezionare il caso in cui si desidera esportare i risultati della ricerca e quindi fare clic su **Apri caso**.

4. Nella **Home** page del caso, fare clic sulla scheda **ricerche** .
    
5. Nell'elenco delle ricerche per il caso, selezionare la casella di controllo accanto a due o più ricerche da cui si desidera esportare i risultati della ricerca. 

   Viene visualizzata la pagina del riquadro a comparsa **azioni in blocco** . 

    ![Nella pagina azioni in blocco fare clic su Esporta risultati](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. Fare clic su **Esporta risultati**.

   Viene visualizzata la pagina dei **risultati di esportazione** . 

    ![Pagina Export results](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    A questo punto, il flusso di lavoro per esportare i risultati di più ricerche associate a un caso di eDiscovery di base è uguale all'esportazione dei risultati della ricerca per una singola ricerca. Vedere il passaggio 5 nella sezione precedente.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Ulteriori informazioni sull'esportazione dei risultati di più ricerche

- Quando si esportano i risultati di più ricerche, le query di ricerca provenienti da tutte le ricerche vengono combinate **tramite gli operatori e** quindi viene avviata la ricerca combinata. I risultati stimati della ricerca combinata vengono visualizzati nella pagina a comparsa del processo di esportazione selezionato. I risultati della ricerca vengono quindi copiati nel percorso di archiviazione di Azure nel cloud Microsoft. Lo stato del processo di copia viene visualizzato anche nella pagina a comparsa. Come indicato in precedenza, dopo che tutti i risultati della ricerca sono stati copiati, è possibile scaricarli in un computer locale.

- Il numero massimo di parole chiave dalle query per tutte le ricerche che si desidera esportare è 500. Questo è lo stesso limite per una singola ricerca. Ciò è dovuto al fatto che il processo di esportazione combina tutte le query di ricerca utilizzando l'operatore **or** . Se si supera questo limite, verrà restituito un errore. In questo caso, è necessario esportare i risultati da meno ricerche o semplificare le query di ricerca delle ricerche originali che si desidera esportare.

- I risultati della ricerca esportati vengono organizzati in base alla posizione di contenuto in cui è stato trovato l'elemento. Questo significa che un percorso di contenuto nei risultati di esportazione potrebbe avere elementi restituiti da ricerche diverse. Ad esempio, se si sceglie di esportare i messaggi di posta elettronica in un unico file PST per ogni cassetta postale, il file PST potrebbe avere risultati da più ricerche.

- Se lo stesso elemento di posta elettronica o documento proveniente dallo stesso percorso di contenuto viene restituito da più di una delle ricerche esportate, verrà esportata solo una copia dell'elemento.

- Non è possibile modificare un'esportazione per più ricerche dopo averlo creato. Ad esempio, non è possibile aggiungere o rimuovere ricerche dal processo di esportazione. È necessario creare un processo di esportazione per modificare i risultati di ricerca esportati. Dopo la creazione di un processo di esportazione, è possibile scaricare i risultati solo in un computer, riavviare l'esportazione o eliminare il processo di esportazione.

- Se si riavvia l'esportazione, le eventuali modifiche apportate alle query delle ricerche che compongono il processo di esportazione non influiscono sui risultati della ricerca recuperati. Quando si riavvia un'esportazione, viene eseguito di nuovo lo stesso processo di query di ricerca combinato eseguito al momento della creazione del processo di esportazione.

- Inoltre, se si riavvia un'esportazione, i risultati della ricerca copiati nel percorso di archiviazione di Azure sovrascrivono i risultati precedenti. I risultati precedenti che sono stati copiati non saranno disponibili per il download.

- La preparazione dei risultati di più ricerche per l'analisi in Advanced eDiscovery (Classic) non è disponibile. È possibile preparare solo i risultati di una singola ricerca per l'analisi in Advanced eDiscovery (Classic).
