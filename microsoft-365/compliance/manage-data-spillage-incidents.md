---
title: Gestire un problema di fuoriuscita dei dati in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come utilizzare lo strumento nuovo data Investigation (Preview) nel centro sicurezza & conformità per gestire un problema di fuoriuscita dei dati.
ms.openlocfilehash: f02d5c42d42f6031202e874497f92fdfbe5d0bcf
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634294"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Gestire un problema di fuoriuscita dei dati in Microsoft 365

La fuoriuscita dei dati avviene quando un documento contenente informazioni riservate, sensibili o dannose viene rilasciato in un ambiente non attendibile. Quando viene rilevato un problema di fuoriuscita dei dati, è importante contenere rapidamente l'ambiente, valutare la dimensione e le posizioni del versamento, esaminare le attività degli utenti e quindi eliminare i dati versati dal servizio. Utilizzando lo strumento di analisi dei dati (Preview), è possibile eseguire la ricerca di dati sensibili, dannosi o fuori luogo tra Office 365, indagare per scoprire cosa è successo e quindi prendere le azioni appropriate.  

## <a name="scope-of-this-article"></a>Ambito di questo articolo

In questo articolo viene fornito un elenco di istruzioni su come eliminare definitivamente gli elementi dalle cassette postali di Office 365, in modo che non siano più accessibili o ripristinabili da parte di utenti o amministratori. 

> [!NOTE]
> Quando si eliminano gli elementi che si trovano in un sito di SharePoint o OneDrive for business, vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale.

## <a name="scenario"></a>Scenario

Si è informati di un problema di fuoriuscita dei dati in cui un dipendente ha condiviso inconsapevolmente un documento estremamente riservato con più persone tramite posta elettronica. Si desidera valutare rapidamente chi ha ricevuto il documento, sia all'interno che all'esterno dell'organizzazione. Dopo aver indagato sull'incidente, si prevede di condividere i risultati con altri ricercatori per esaminare e quindi rimuovere definitivamente i dati versati dall'organizzazione di Office 365. Al termine dell'analisi, si desidera rimuovere tutte le prove. 

> [!IMPORTANT]
> Anche se è possibile rimuovere definitivamente i dati versati all'interno dell'organizzazione, i dati riversati all'esterno dell'organizzazione non possono essere rimossi con queste funzionalità.

## <a name="workflow"></a>Flusso di lavoro

Di seguito è indicato il flusso di lavoro per l'utilizzo delle indagini sui dati (Preview) per gestire un problema di fuoriuscita dei dati:

1.  Creare un'analisi dei dati.

2.  Ricercare dati sensibili, dannosi o fuori luogo e raccoglierli come elementi di prova.

3.  Esaminare ed esaminare le evidenze.

4.  Elimina definitivamente i dati versati.

5.  Chiudere o eliminare l'indagine.


## <a name="before-you-begin"></a>Prima di iniziare

- Per creare un'analisi dei dati, ricercare il contenuto ed eliminare i dati versati, è necessario essere membri del gruppo di ruolo ricercatore di dati nel centro sicurezza & Compliance.

- Per controllare le cassette postali degli utenti e gli account di OneDrive che un ricercatore può cercare, l'organizzazione può impostare i limiti di conformità. Per ulteriori informazioni, [impostare i limiti di conformità per le indagini di eDiscovery](tagging-and-assessment-in-advanced-ediscovery.md). 

## <a name="step-1-create-a-data-investigation"></a>Passaggio 1: creare un'analisi dei dati

Per creare un'indagine nello strumento indagini dati (Preview):

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando un account membro del gruppo di ruolo ricercatore di dati.
    
3. Nel centro sicurezza e conformità fare clic su **indagini sui dati**.
 
4. Nella pagina **indagini dati (anteprima)** fare clic su **Crea nuova indagine**.
    
5. Nella pagina nuovo riquadro a comparsa **dei dati** , assegnare un nome all'indagine (obbligatorio) e quindi digitare un numero di ricerca facoltativo e una descrizione. Il nome deve essere univoco nell'organizzazione.

6. In **se si desidera configurare altre impostazioni dopo aver creato l'indagine**, eseguire una delle operazioni seguenti:

    - Fare clic su **Sì** per creare l'analisi e visualizzare la pagina **Impostazioni** nel nuovo caso. In questo modo è possibile aggiungere membri all'indagine.
    
    - Fare clic su **No** per creare l'analisi e visualizzarla nell'elenco dei casi della pagina **indagini dati (anteprima)** . Se si sceglie questa opzione, verrà aggiunto come unico membro dell'indagine e verranno utilizzate le impostazioni di ricerca e analisi predefinite. È possibile aggiungere membri o modificare le impostazioni in qualsiasi momento dopo la creazione dell'indagine.

7. Fare clic su **Salva** per creare l'indagine.

    La nuova analisi viene visualizzata nell'elenco nella pagina **indagini dati (anteprima)** . 

8. Per aprire un'indagine, fare clic sul nome dell'indagine. 

    Viene visualizzata la scheda **Home** per l'indagine. 

> [!TIP]
> Valutare la possibilità di stabilire una convenzione di denominazione per le indagini e fornire quante più informazioni possibile nel nome e nella descrizione, in modo da poter individuare e consultare in futuro, se necessario.
 
## <a name="step-2-search-for-the-spilled-data"></a>Passaggio 2: ricerca dei dati versati 
 
Se si conoscono gli utenti di cui si desidera eseguire la ricerca per i dati riversati, è possibile aggiungerli come persone di interesse per mappare le origini dati all'analisi e cercare rapidamente la propria cassetta postale e l'account OneDrive. Per aggiungere persone di interesse all'indagine, fare clic su **persone di interesse**, quindi fare clic su **Aggiungi persone di interesse**. Per ulteriori informazioni, vedere [Manage people of interest](manage-people-of-interest.md).

Nella scheda **ricerche** è possibile creare ricerche per individuare i dati versati. Per ulteriori informazioni sulla creazione di ricerche, vedere [Search for data in an Investigation](search-for-data.md).

Dopo aver eseguito la ricerca, è possibile visualizzare in anteprima esempi di risultati della ricerca e visualizzarne le statistiche per valutare l'efficacia della query di ricerca. Dopo aver identificato gli elementi che si desidera eliminare da Office 365, è possibile aggiungere i risultati della ricerca a un set di evidenze. A tale scopo, fare clic sulla ricerca che si desidera esaminare. Nella pagina a comparsa fare clic su **Aggiungi risultati a prova** e seguire le istruzioni. Nel set di prove è quindi possibile esaminare singoli documenti, esaminare gli utenti che hanno accesso ai documenti ed esportare i documenti. Per eliminare i documenti (o un sottoinsieme di documenti) anziché esaminarli, passare al [passaggio 4](#step-4-delete-the-spilled-data). 

> [!IMPORTANT]
> Le parole chiave utilizzate nella query di ricerca possono contenere i dati di cui è stata eseguita la ricerca. Ad esempio, se si cercano documenti che contengono un numero di previdenza sociale e lo si usa come parola chiave nella query di ricerca, è necessario eliminare la query in seguito per evitare un ulteriore fuoriuscita. È possibile eliminare la ricerca o eliminare l'intera analisi nel [passaggio 5](#step-5-close-or-delete-the-investigation). 

## <a name="step-3-review-and-investigate"></a>Passaggio 3: Revisione e analisi 

Nell'analisi passare alla scheda **Evidence** e fare clic sul set di prove creato nel passaggio precedente. Dopo che il processo di elaborazione è stato completato e i risultati della ricerca vengono aggiunti all'evidenza, è possibile esaminare i singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo. È possibile creare query aggiuntive per limitare l'elenco dei documenti e contrassegnare i documenti per indicare i risultati dell'indagine. Per ulteriori informazioni, vedere [Review data in evidence](review-data-in-evidence.md)

Per raggruppare i documenti e ottenere assistenza per la revisione, fare clic su **Gestisci evidenza**. Nel riquadro **analisi** fare clic su **analizza**. In questo modo vengono eseguite analisi avanzate, come il rilevamento duplicati, il threading di posta elettronica e il tema. Per altre informazioni, vedere:

- [Eseguire analisi per velocizzare le indagini](run-analytics-to-investigate-faster.md)
- [Rilevamento dei documenti simili](near-duplicates.md)
- [Threading posta elettronica](email-threading.md)
- [Temi](themes.md)

Per determinare gli utenti coinvolti nella fuoriuscita di dati, è possibile creare una query nel set di evidenze e quindi utilizzare le condizioni mittente/autore e destinatari. In questo modo viene creato un elenco di tutti i mittenti, i destinatari e gli autori trovati nei dati raccolti che sono stati aggiunti all'evidenza. Assicurarsi di esaminare l'elenco per determinare se sono presenti utenti esterni. Per ulteriori informazioni sull'utilizzo delle condizioni per limitare i risultati della ricerca, vedere [condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-delete-the-spilled-data"></a>Passaggio 4: eliminare i dati versati

Utilizzando lo strumento indagini dati, è possibile eliminare gli elementi dai percorsi originali. Ad esempio, è possibile eliminare gli elementi delle cassette postali, dei siti di SharePoint e degli account di OneDrive all'interno dell'organizzazione. Tenere presente che, poiché gli elementi sono stati raccolti come prova (aggiungendo i risultati della ricerca al set di evidenze del passaggio 2), si dispone di copie degli elementi del set di prove per approfondire o conservarli.

Per eliminare gli elementi dai percorsi originali:

1. Nel set di evidenze selezionare gli elementi che si desidera eliminare. Se si selezionano gli elementi associati a un messaggio di posta elettronica, il messaggio di posta elettronica padre verrà selezionato ed eliminato. 
 
2. Fare clic su **azione** e quindi su **Elimina elementi da percorsi originali**.

   ![Fare clic su azione e quindi su Elimina elementi da percorsi originali](../media/DataInvestigationsDeleteItems1.png)

3. Nella pagina riquadro a comparsa verificare il numero di elementi e i documenti figlio correlati che verranno eliminati e quindi fare clic su **Elimina**.

Al momento, quando si eliminano gli elementi dal percorso originale, gli elementi vengono eliminati temporaneamente. Questo significa che gli elementi eliminati verranno mantenuti fino alla scadenza del periodo di ripristino dell'elemento eliminato. Questo significa anche che è possibile che gli utenti recuperino questi elementi. Per ulteriori informazioni su ciò che accade quando gli elementi vengono eliminati da cassette postali e siti, vedere [eliminare gli elementi dal percorso originale](delete-items-from-original-locations.md).

## <a name="step-5-close-or-delete-the-investigation"></a>Passaggio 5: chiudere o eliminare l'analisi

Dopo aver eliminato i documenti nelle posizioni di contenuto di origine (cassette postali o siti) nel servizio Live, si avranno comunque copie di questi documenti che sono stati aggiunti a Evidence come parte dell'indagine. Per evitare un ulteriore versamento dei dati, è consigliabile eliminare l'analisi stessa.

Per eliminare un'analisi:

1. Nella scheda **Impostazioni** fare clic su **informazioni di analisi**.

2. Fare clic su **Elimina analisi**. 

Se non è necessario eliminare l'analisi o se si desidera salvare le informazioni raccolte durante l'indagine, è possibile fare clic su **Chiudi caso**. Successivamente, è possibile riaprire le indagini chiuse.
