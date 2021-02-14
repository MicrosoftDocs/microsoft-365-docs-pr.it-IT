---
title: Esportare un report di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
description: Anziché esportare i risultati effettivi di una ricerca di contenuto nel Centro sicurezza & conformità in Office 365, è possibile esportare un report dei risultati della ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento da esportare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de27e25945f14f6a6119b4c1776eebca5e84d8ce
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358302"
---
# <a name="export-a-content-search-report"></a>Esportare un report di Ricerca contenuto

Anziché esportare il set completo di risultati della ricerca da una ricerca di contenuto nel Centro sicurezza & e conformità (e da una ricerca di contenuto associata a un caso di eDiscovery), è possibile esportare gli stessi report generati quando si esportano i risultati della ricerca.
  
Quando si esporta un report, questo viene scaricato in una cartella con lo stesso nome della ricerca di contenuto, ma che viene aggiunta a *_ReportsOnly*. Ad esempio, se la ricerca di contenuto è denominata  *ContosoCase0815,* il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly*. Per un elenco dei documenti inclusi nel report, vedere Elementi [inclusi nel report.](#whats-included-in-the-report)

## <a name="assign-roles-and-check-system-requirements"></a>Assegnare ruoli e controllare i requisiti di sistema

- Per esportare un report Ricerca contenuto, è necessario disporre del ruolo di gestione Ricerca di conformità nel Centro sicurezza & conformità. Questo ruolo viene assegnato per impostazione predefinita ai gruppi di ruoli Gestore di eDiscovery e Gestione organizzazione incorporati. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).

- Quando si esporta un report, i dati vengono temporaneamente archiviati in un'area di Archiviazione di Azure univoca nel cloud Microsoft prima di essere scaricati nel computer locale. Assicurarsi che l'organizzazione possa connettersi all'endpoint in Azure, ovvero **\* .blob.core.windows.net** (il carattere jolly rappresenta un identificatore univoco per l'esportazione). I dati dei risultati della ricerca vengono eliminati dall'area di archiviazione di Azure due settimane dopo la creazione. 
    
- Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:
    
  - Versioni a 32 bit o a 64 bit di Windows 7 e versioni successive
    
  - Microsoft .NET Framework 4.7
    
- È necessario utilizzare uno dei browser supportati seguenti per eseguire lo strumento di esportazione di eDiscovery<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>

    OPPURE

  - Microsoft Internet Explorer 10 e versioni successive

  > [!NOTE]
  > <sup>1</sup> Microsoft non produce estensioni o componenti aggiuntivi di terze parti per ClickOnce applicazioni. L'esportazione dei risultati della ricerca con un browser non supportato con estensioni o componenti aggiuntivi di terze parti non è supportata.<br/>
  > <sup>2</sup> In seguito alle recenti modifiche apportate a Microsoft Edge, ClickOnce il supporto non è più abilitato per impostazione predefinita. Per istruzioni sull'abilitazione ClickOnce supporto in Edge, vedere Usare lo strumento di esportazione [di eDiscovery in Microsoft Edge.](configure-edge-to-export-search-results.md)

- Se la dimensione totale stimata dei risultati restituiti da una ricerca di contenuto supera i 2 TB, l'esportazione del report ha esito negativo. Per esportare correttamente il report, provare a restringere l'ambito ed eseguire di nuovo la ricerca in modo che la dimensione stimata dei risultati sia inferiore a 2 TB.

- L'esportazione dei report di Ricerca contenuto viene eseguita in base al numero massimo di esportazioni eseguite contemporaneamente e al numero massimo di esportazioni che un singolo utente può eseguire. Per ulteriori informazioni sui limiti di esportazione, vedere [Esportare i risultati di Ricerca contenuto.](export-search-results.md#export-limits)

## <a name="generate-and-download-a-content-search-report"></a>Generare e scaricare un report Ricerca contenuto

La procedura per generare e scaricare un report Ricerca contenuto è simile all'esportazione dei risultati di ricerca.
  
## <a name="step-1-generate-the-report-for-export"></a>Passaggio 1: Generare il report per l'esportazione

Il primo passaggio consiste nel preparare il report per il download nel computer in uso. Quando si esegue il report, i documenti del report vengono caricati in un'area di Archiviazione di Azure nel cloud Microsoft.
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere usando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro del Centro sicurezza & conformità fare clic **su Ricerca** \> **contenuto.**
    
4. Nella pagina **Ricerca contenuto** selezionare una ricerca. 
    
5. Nel riquadro dei dettagli, in **Esporta report in un computer,** fare clic su Genera **report.**
    
    > [!NOTE]
    > Se i risultati di una ricerca hanno più di 7 giorni, viene chiesto di aggiornare i risultati di ricerca. In questo caso, annullare  l'esportazione, fare clic su Aggiorna risultati della ricerca nel riquadro dei dettagli per la ricerca selezionata e quindi avviare di nuovo l'esportazione del report dopo l'aggiornamento dei risultati. 
  
6. Nella pagina **Esporta report,** in Includi questi elementi dalla **ricerca,** scegliere una delle opzioni seguenti:
    
    - Esportare solo gli elementi indicizzati
    
    - Esportare gli elementi indicizzati e non
    
    - Esportare solo gli elementi non indicizzati
    
    Per ulteriori informazioni sugli elementi non indicizzati, vedere [Elementi parzialmente indicizzati in Ricerca contenuto.](partially-indexed-items-in-content-search.md)
    
7. Scegliere di includere le statistiche di ricerca per tutte le versioni dei documenti di SharePoint. Questa opzione viene visualizzata solo se le origini di contenuto della ricerca includono siti di SharePoint o OneDrive for Business.
    
8. Fare **clic su Genera report.**
    
    Il report dei risultati della ricerca è pronto per il download, il che significa che i documenti del report verranno caricati nell'area di archiviazione di Azure nel cloud Microsoft. Quando il report è pronto per il download, il collegamento scarica **report** viene visualizzato in Esporta report in **un computer** nel riquadro dei dettagli. 
    
> [!NOTE]
> È inoltre possibile esportare un report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, passare a  \> **eDiscovery eDiscovery,** selezionare un caso e fare clic **sull'icona** ![ Modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica. Nella pagina **Ricerche selezionare** una ricerca  e quindi fare clic sull'icona Esporta risultati di ![ ricerca ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Esportare un report.** 
  
## <a name="step-2-download-the-report"></a>Passaggio 2: scaricare il report

Il passaggio successivo consiste nel scaricare il report dall'area di archiviazione di Azure nel computer locale.
  
1. Nel riquadro dei dettagli per la ricerca per cui è stato generato il report, in **Esporta report in un computer** fare clic su Scarica **report.**
    
    Verrà **visualizzata la** pagina Scarica report contenente le informazioni seguenti sul report scaricato nel computer. 
    
    - Il numero di elementi che verranno scaricati.
    
    - La dimensione totale stimata degli elementi che verranno scaricati.
    
    - Se gli elementi esportati saranno indicizzati o non indicizzati. Gli elementi non indicizzati sono elementi con un formato riconosciuto, crittografati o non indicizzati per altri motivi.
    
    - Indica se verranno scaricate le versioni dei documenti di SharePoint.
    
    - Stato del processo di esportazione dei report. È possibile iniziare a scaricare il report anche se la preparazione del report non è stata completata.
    
2. In **Chiave di esportazione**, fare clic su **Copia negli Appunti**. Utilizzare questa chiave nel passaggio 5 per scaricare il report.
    
    > [!IMPORTANT]
    > Poiché chiunque può installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di adottare le dovute precauzioni per proteggere questa chiave proprio come si proteggono le password o altre informazioni relative alla sicurezza. 
  
3. Fare **clic su Scarica report.**
    
4. Se viene richiesto di installare lo strumento di esportazione **di eDiscovery,** fare clic su **Installa.**
    
5. Nello **Strumento di esportazione eDiscovery**, incollare la chiave di esportazione copiata nel passaggio 2 nella casella appropriata.
    
6. Fare **clic** su Sfoglia per specificare il percorso in cui si desidera scaricare il report. 
    
7. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    Lo **Strumento di esportazione eDiscovery** consente di visualizzare informazioni sullo stato delle informazioni relative al processo di esportazione, incluso il numero stimato (e le dimensioni) degli elementi rimanenti da scaricare. Al termine del processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati. 
    
> [!NOTE]
> È possibile scaricare il report per una ricerca di contenuto associata a un caso di eDiscovery. A tale scopo, passare a  \> **eDiscovery eDiscovery,** selezionare un caso e fare clic **sull'icona** ![ Modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica. Nella pagina **Esportazioni** selezionare un'esportazione di report e quindi fare clic su **Scarica report** nel riquadro dei dettagli. 
  
## <a name="whats-included-in-the-report"></a>Contenuto del report

Quando si genera ed esporta un report sui risultati di una ricerca di contenuto, vengono scaricati i documenti seguenti:
  
- **Riepilogo esportazione:** Documento di Excel contenente un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini di contenuto in cui è stata ricercata, il numero di risultati della ricerca da ogni percorso di contenuto, il numero stimato di elementi, il numero effettivo di elementi da esportare e la dimensione stimata ed effettiva degli elementi che verranno esportati. 
    
    > [!NOTE]
    > Se si includono elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati di ricerca stimati e nel numero totale di risultati di ricerca scaricati (se si dovevano esportare i risultati della ricerca) elencati nel rapporto Riepilogo esportazione. In altre parole, il numero totale di elementi che verrebbero scaricati è pari al numero totale di risultati stimati e al numero totale di elementi non indicizzati. 
  
- **Manifesto:** File manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. 
    
- **Risultati:** Documento di Excel contenente una riga con informazioni su ogni elemento indicizzato che verrebbe esportato con i risultati della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
    Per i documenti dei siti di SharePoint e OneDrive for Business, il log dei risultati contiene informazioni su ogni documento, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
    > [!NOTE]
    > Il numero di righe nel **report** Risultati deve essere uguale al numero totale di risultati della ricerca meno il numero totale di elementi elencati nel report **Elementi non** indicizzati. 
  
- **Elementi non indicizzati:** Documento di Excel che contiene informazioni sugli elementi non indicizzati inclusi nei risultati della ricerca. Se non si includono elementi non indicizzati quando si genera il report dei risultati della ricerca, il report continuerà a essere scaricato, ma sarà vuoto.
