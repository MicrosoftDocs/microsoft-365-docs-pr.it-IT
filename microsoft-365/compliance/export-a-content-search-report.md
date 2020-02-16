---
title: Esportare un report di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Invece di esportare i risultati effettivi di una ricerca contenuto nel centro sicurezza & conformità in Office 365, è possibile esportare un rapporto sui risultati di ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento che verrebbe esportato.
ms.openlocfilehash: 6730a1c406e02de26cbef964e445cfad31c948ec
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074393"
---
# <a name="export-a-content-search-report"></a>Esportare un report di Ricerca contenuto

Invece di esportare il set completo di risultati della ricerca da una ricerca di contenuto nel centro sicurezza & Compliance (e da una ricerca di contenuto associata a un caso di eDiscovery), è possibile esportare gli stessi rapporti generati quando si esportano i risultati della ricerca.
  
Quando si esporta un report, viene scaricato in una cartella con lo stesso nome della ricerca di contenuto, ma accodato con *_ReportsOnly*. Ad esempio, se la ricerca di contenuto è denominata *ContosoCase0815*, il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly*. Per un elenco dei documenti inclusi nel report, vedere [What ' s incluso nel report](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Informazioni preliminari

- Per esportare un rapporto di ricerca contenuto, è necessario assegnare il ruolo di gestione della ricerca di conformità nel centro sicurezza & Compliance. Questo ruolo viene assegnato ai gruppi di ruoli di gestione eDiscovery e dell'organizzazione incorporati. Non viene assegnato per impostazione predefinita al gruppo di ruoli Gestione organizzazione. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).
    
- Quando si esporta un report, i dati vengono temporaneamente archiviati in un'area di archiviazione di Azure univoca nel cloud Microsoft prima che vengano scaricati nel computer locale. Assicurarsi che l'organizzazione sia in grado di connettersi all'endpoint in Azure, che è ** \*. blob.Core.Windows.NET** (il carattere jolly rappresenta un identificatore univoco per l'esportazione). I dati dei risultati della ricerca vengono eliminati dall'area di archiviazione di Azure due settimane dopo la sua creazione. 
    
- Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:
    
  - versioni a 32 bit o 64 bit di Windows 7 e versioni successive
    
  - Microsoft .NET Framework 4.7
    
- Per eseguire lo strumento di esportazione di eDiscovery<sup>1</sup>, è necessario utilizzare uno dei seguenti browser supportati:

  - Microsoft Edge <sup>2</sup>

    OPPURE

  - Microsoft Internet Explorer 10 e versioni successive

  > [!NOTE]
  > <sup>1</sup> Microsoft non produce estensioni o componenti aggiuntivi di terze parti per le applicazioni ClickOnce. L'esportazione dei risultati di ricerca utilizzando un browser non supportato con le estensioni di terze parti o i componenti aggiuntivi non è supportata.<br/>
  > <sup>2</sup> come risultato delle recenti modifiche apportate a Microsoft Edge, il supporto ClickOnce non è più abilitato per impostazione predefinita. Per istruzioni sull'abilitazione del supporto ClickOnce in Edge, vedere [utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge](configure-edge-to-export-search-results.md).

- Se le dimensioni totali stimate dei risultati restituiti da una ricerca di contenuto superano 2 TB, l'esportazione del rapporto ha esito negativo. Per esportare correttamente il report, provare a restringere l'ambito e rieseguire la ricerca in modo che le dimensioni stimate dei risultati siano inferiori a 2 TB.

- L'esportazione dei rapporti di ricerca del contenuto conta sul numero massimo di esportazioni in esecuzione contemporaneamente e sul numero massimo di esportazioni che un singolo utente può eseguire. Per ulteriori informazioni sui limiti di esportazione, vedere [Export content search results](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Generare e scaricare un report di ricerca contenuto

I passaggi per generare e scaricare un report di ricerca contenuto sono simili all'esportazione dei risultati della ricerca.
  
## <a name="step-1-generate-the-report-for-export"></a>Passaggio 1: generare il report per l'esportazione

Il primo passaggio consiste nel preparare il report per il download nel computer che esporta. Quando si esegue il report, i documenti del report vengono caricati in un'area di archiviazione di Azure nel cloud Microsoft.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza & conformità fare clic su ricerca **** \> **contenuto**ricerca.
    
4. Nella pagina **Ricerca contenuto** selezionare una ricerca. 
    
5. Nel riquadro dei dettagli, in **Esporta rapporto in un computer**, fare clic su **genera report**.
    
    > [!NOTE]
    > Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornare i risultati di ricerca. In tal caso, annullare l'esportazione, fare clic su **Aggiorna i risultati della ricerca** nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione del rapporto dopo l'aggiornamento dei risultati. 
  
6. Nella pagina **Esporta un report** , in **Includi questi elementi della ricerca**, scegliere una delle seguenti opzioni:
    
    - Esportare solo gli elementi indicizzati
    
    - Esportare gli elementi indicizzati e non
    
    - Esportare solo gli elementi non indicizzati
    
    Per ulteriori informazioni sugli elementi non indicizzati, vedere [elementi indicizzati parzialmente nella ricerca contenuto](partially-indexed-items-in-content-search.md).
    
7. Scegliere di includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint. Questa opzione viene visualizzata solo se le origini di contenuto della ricerca includono i siti di SharePoint o OneDrive for business.
    
8. Fare clic su **genera report**.
    
    Il report dei risultati della ricerca è pronto per il download, il che significa che i documenti del rapporto verranno caricati nell'area di archiviazione di Azure nel cloud Microsoft. Quando il report è pronto per il download, il collegamento del **rapporto di download** viene visualizzato in **Esporta rapporto in un computer** nel riquadro dei dettagli. 
    
> [!NOTE]
> È inoltre possibile esportare un report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, accedere a **eDiscovery** \> **eDiscovery**, selezionare un caso e fare clic su **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica. Nella pagina **ricerche** selezionare una ricerca e **quindi fare clic su** ![Esporta esportazione dei risultati della ricerca](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **l'icona Esporta un report**. 
  
## <a name="step-2-download-the-report"></a>Passaggio 2: scaricare il report

Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione di Azure nel computer locale.
  
1. Nel riquadro dei dettagli per la ricerca per la quale è stato generato il report, in **Esporta rapporto in un computer**, fare clic su **Scarica report**.
    
    Viene visualizzata la pagina **download report** che contiene le seguenti informazioni sul rapporto scaricato nel computer. 
    
    - Il numero di elementi che verranno scaricati.
    
    - La dimensione totale stimata degli elementi che verranno scaricati.
    
    - Se gli elementi esportati saranno indicizzati o non indicizzati. Gli elementi non indicizzati sono elementi che hanno un formato riconosciuto, sono crittografati o non sono stati indicizzati per altri motivi.
    
    - Se verranno scaricate le versioni dei documenti di SharePoint.
    
    - Lo stato del processo di esportazione del report. È possibile iniziare a scaricare il report anche se la preparazione del report non è stata completata.
    
2. In **Chiave di esportazione**, fare clic su **Copia negli Appunti**. È possibile utilizzare questa chiave nel passaggio 5 per scaricare il report.
    
    > [!IMPORTANT]
    > Poiché tutti gli utenti possono installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di prendere precauzioni per proteggere questa chiave come se si proteggessero le password o altre informazioni relative alla sicurezza. 
  
3. Fare clic su **download report**.
    
4. Se viene richiesto di installare lo **strumento di esportazione di MicrosoftOffice 365 eDiscovery**, fare clic su **Installa**.
    
5. Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.
    
6. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare il report. 
    
7. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    Lo **Strumento di esportazione eDiscovery** consente di visualizzare informazioni sullo stato delle informazioni relative al processo di esportazione, incluso il numero stimato (e le dimensioni) degli elementi rimanenti da scaricare. Al termine del processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati. 
    
> [!NOTE]
> È possibile scaricare il report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, accedere a **eDiscovery** \> **eDiscovery**, selezionare un caso e fare clic su **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica. Nella pagina **esportazioni** selezionare l'esportazione di un report e quindi fare clic su **Scarica report** nel riquadro dei dettagli. 
  
## <a name="whats-included-in-the-report"></a>Elementi inclusi nel report

Quando si genera ed esporta un report sui risultati di una ricerca di contenuto, vengono scaricati i documenti seguenti:
  
- **Riepilogo esportazione:** Documento di Excel che contiene un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini di contenuto di cui è stata eseguita la ricerca, il numero di risultati di ricerca di ogni percorso del contenuto, il numero stimato di elementi, il numero effettivo di elementi che verrebbero esportati e le dimensioni stimate e effettive degli elementi. che verrebbe esportato. 
    
    > [!NOTE]
    > Se si includono gli elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati della ricerca stimati e nel numero totale di risultati della ricerca scaricati (se si desidera esportare i risultati della ricerca) elencati nel Esporta rapporto riepilogativo. In altre parole, il numero totale di elementi che verrebbero scaricati è uguale al numero totale di risultati stimati e al numero totale di elementi non indicizzati. 
  
- **Manifesto:** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. 
    
- **Risultati:** Documento di Excel che contiene una riga contenente informazioni su ogni elemento indicizzato che verrebbe esportato con i risultati della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
    Per i documenti provenienti da siti di SharePoint e OneDrive for business, il registro dei risultati contiene informazioni su ogni documento, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
    > [!NOTE]
    > Il numero di righe del rapporto **risultati** deve essere uguale al numero totale di risultati della ricerca meno il numero totale di elementi elencati nel rapporto **elementi non indicizzati** . 
  
- **Elementi non indicizzati:** Documento di Excel che contiene informazioni su eventuali elementi non indicizzati inclusi nei risultati della ricerca. Se non si includono gli elementi non indicizzati durante la generazione del report dei risultati della ricerca, il report verrà comunque scaricato, ma sarà vuoto.
