---
title: Correzione degli errori dei singoli elementi
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: È possibile correggere un errore di elaborazione in un documento in un set di revisione in Advanced eDiscovery senza dover seguire il processo di correzione degli errori in blocco.
ms.openlocfilehash: c049ce4b5d3f8fc12a015a61ea927b744ae76eb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601493"
---
# <a name="single-item-error-remediation"></a>Correzione degli errori dei singoli elementi

La correzione degli errori garantisce agli utenti avanzati di eDiscovery la possibilità di correggere i problemi relativi ai dati che impediscono l'elaborazione corretta del contenuto da parte di Advanced eDiscovery. Ad esempio, i file protetti da password non possono essere elaborati perché tali file sono bloccati o crittografati. In precedenza, è possibile correggere solo gli errori in blocco utilizzando [questo flusso di lavoro](error-remediation-when-processing-data-in-advanced-ediscovery.md). Tuttavia, a volte, non ha senso correggere gli errori in più file quando non si è sicuri se uno qualsiasi di questi file risponde al caso in cui si sta indagando. Potrebbe anche non essere opportuno correggere gli errori prima di aver avuto la possibilità di esaminare i metadati dei file (come il percorso del file o chi aveva accesso) per aiutarti a prendere decisioni in anticipo sulla reattività. Una nuova funzionalità denominata correzione degli errori di un *singolo elemento* fornisce ai responsabili di eDiscovery la possibilità di visualizzare i metadati dei file con un errore di elaborazione e, se necessario, correggere l'errore direttamente nel set di revisione. In questo articolo viene illustrato come identificare, ignorare e correggere i file con errori di elaborazione in un set di revisione.

## <a name="identify-documents-with-errors"></a>Identificare i documenti con errori

I documenti con errori di elaborazione in un set di revisione sono ora identificati (con un banner). È possibile correggere o ignorare l'errore. Nella schermata seguente viene mostrato il banner di errore di elaborazione per un documento di Word in un set di revisione che è protetto da password. Si noti inoltre che è possibile visualizzare i metadati dei file di documenti con errori di elaborazione.

![Banner visualizzato per il documento con errore di elaborazione](media/SIERimage1.png)

È inoltre possibile cercare i documenti che presentano errori di elaborazione utilizzando la condizione di **elaborazione dello stato** durante [l'esecuzione di query sui documenti in un set di revisione](review-set-search.md).

![Utilizzare la condizione di elaborazione dello stato per cercare i documenti di errore](media/SIERimage2.png)

### <a name="ignore-errors"></a>Ignorare gli errori

È possibile ignorare un errore di elaborazione facendo clic su **Ignora** nel banner di errore di elaborazione. Quando si ignora un errore, il documento viene rimosso dal flusso di lavoro per la [correzione degli errori di massa](error-remediation-when-processing-data-in-advanced-ediscovery.md). Dopo aver ignorato un errore, il banner del documento cambia colore e indica che l'errore di elaborazione è stato ignorato. In qualsiasi momento, è possibile annullare la decisione di ignorare l'errore facendo clic su **Ripristina**.

![Fare clic su Ignora per ignorare l'errore di elaborazione](media/SIERimage3.png)

È inoltre possibile cercare tutti i documenti in cui si è verificato un errore di elaborazione ignorato utilizzando la condizione relativa agli *errori di elaborazione ignorati* durante l'esecuzione di query sui documenti in un set di revisione.

![Utilizzare la condizione relativa agli errori di elaborazione ignorati per cercare i documenti di errore ignorati](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Correggere gli errori di un documento

A volte potrebbe essere necessario correggere un errore di elaborazione nei documenti (tramite la rimozione di una password, la decrittografia di un file crittografato o il ripristino di un documento danneggiato) e quindi aggiungere il documento correttivo al set di revisione. In questo modo è possibile esaminare ed esportare il documento di errore insieme agli altri documenti nel set di revisione. 

Per correggere un singolo documento, attenersi alla procedura seguente:

1.  > Fare **clic su download download****originale** per scaricare una copia del file in un computer locale.

   ![Scaricare il documento con l'errore di elaborazione](media/SIERimage5.png)

2. Correggere l'errore nel file offline. Per i file crittografati, che richiedono un software di decrittografia, per rimuovere la protezione dalle password, fornire la password e salvare il file oppure utilizzare un programma di cracking delle password. Dopo aver rimediato il file, passare al passaggio successivo.

3. Nel set di Revisione selezionare il file con l'errore di elaborazione da correggere e quindi fare clic su **correzione**.

   ![Fare clic su correzione nel banner del documento con errore di elaborazione](media/SIERimage6.png)


4. Fare clic su **Sfoglia**, passare al percorso del file di correzione nel computer locale e quindi selezionare il file.

   ![Fare clic su Sfoglia e selezionare il file corretti nel computer locale](media/SIERimage7.png)

    Dopo aver selezionato il file di correzione, viene caricato automaticamente nel set di revisione. È possibile monitorare lo stato di elaborazione del file.

    ![Lo stato del processo di correzione viene visualizzato](media/SIERimage8.png)

   Al termine dell'elaborazione, è possibile visualizzare il documento correttivo.

    ![È possibile visualizzare il file di correzione nel formato nativo nel set di Revisione](media/SIERimage9.png)

Per ulteriori informazioni sugli elementi che si verificano quando un documento viene correttivo, vedere [cosa succede quando i file vengono corretti](error-remediation.md#what-happens-when-files-are-remediated).

## <a name="search-for-remediated-documents"></a>Ricerca di documenti corretti

È possibile cercare tutti i documenti in un set di revisione che sono stati corretti utilizzando la condizione **Keywords** e specificando la proprietà seguente: coppia valore: **IsFromErrorRemediation: true**. Questa proprietà è disponibile anche nel file di caricamento dell'esportazione quando si esportano i documenti da un set di revisione.
