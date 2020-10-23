---
title: Opzioni di fine ciclo di vita per gruppi, team e Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opzioni di fine ciclo di vita per gruppi, team e Yammer.
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681711"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opzioni di fine ciclo di vita per gruppi, team e Yammer

I gruppi Microsoft 365 e Microsoft teams lavorano con una vasta gamma di servizi connessi. Quando un gruppo o un team viene eliminato, viene eliminata anche la maggior parte delle informazioni presenti nei servizi connessi. In questo articolo vengono descritte le opzioni per il mantenimento delle informazioni mediante lo spostamento fuori del gruppo o del team prima dell'eliminazione.

Una prassi comune per gruppi o team che non sono più necessari consiste nello spostare i file al di fuori del team e archiviarli in un altro percorso, ad esempio una raccolta documenti di SharePoint che funge da repository o archivio. Questa procedura si basa su uno stile legacy di lavoro in cui le informazioni vengono archiviate in file e cartelle e le comunicazioni vengono condotte tramite posta elettronica.

Nella tabella seguente vengono illustrati i servizi associati ai gruppi e ai team e ai tipi di contenuto principali disponibili in ognuno di essi:

|Servizio|Tipi di contenuto|
|:------|:---------------|
|Teams|Conversazioni dei canali, file nei canali|
|Forms|Struttura del sondaggio e risultati|
|OneNote|Blocco appunti|
|Outlook|Posta e calendario|
|Planner|Informazioni sullo stato e sulle attività del progetto|
|Automatizzare la potenza|Flussi di lavoro|
|Power BI|Dati, report e dashboard|
|Project sul Web|Piani di progetto|
|Roadmap|Roadmap|
|SharePoint|File, elenchi, dati wiki del canale Teams|
|Stream|Video|
|Yammer|Conversazioni|

Quando si elimina un gruppo o un team, vengono eliminate anche la maggior parte delle risorse associate. Alcune di queste eccezioni includono video in stream: queste restano e continuano a essere di proprietà della persona che le ha caricate/registrate, così come scorrono in Power automatizzate. I dati del progetto e della roadmap in Project sul Web rimangono nei CD e possono essere ripristinati separatamente.

I gruppi e i team restano in uno stato di eliminazione temporanea per 30 giorni e possono essere ripristinati in qualsiasi momento. Tuttavia, dopo i 30 giorni e tutte le risorse associate, come servizi e contenuto, vengono completamente eliminati dall'ambiente Microsoft 365. Tutti i contenuti protetti da un criterio di conservazione rimangono disponibili tramite le ricerche di eDiscovery.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerazioni sulla fine del ciclo di vita per i servizi connessi a gruppi

Per l'eliminazione di un gruppo o di un team, sono disponibili tre aree principali che i proprietari del team e del gruppo e gli amministratori IT devono considerare.

**Contenuto**

Il contenuto deve essere mantenuto dopo che il team non è più in funzione o in esistenza? È sufficiente affidarsi alle funzionalità di conservazione di Microsoft 365 oppure è parte del contenuto di app e servizi che non offrono la conservazione? È necessario conservare il contenuto per scopi di gestione dei record, per scopi di archiviazione o per usi e riferimenti futuri?

Queste domande devono essere poste prima che un team venga archiviato o eliminato, per evitare potenziali perdite di dati.

**Servizi**

Oltre ai contenuti tra diverse app e servizi, è necessario rimanere nel modulo di lavoro corrente? Ad esempio, se il rapporto Power BI deve continuare a essere accessibile, è necessario che i risultati del modulo siano disponibili nella visualizzazione riepilogo visivo, che sono gli elenchi di SharePoint collegati o incorporati in un punto qualsiasi?

Analogamente alle considerazioni sul contenuto, queste domande devono essere poste prima che il gruppo sottostante venga eliminato, in quanto semplicemente l'esportazione del contenuto potrebbe non essere sufficiente.

**Ospiti**

Quando gli ospiti sono invitati a un team, il flusso di lavoro crea la propria identità nell'Azure Active Directory dell'organizzazione host prima di aggiungerli al team. Quando un team viene eliminato, gli utenti non vengono rimossi da Azure Active Directory e come tali sono ancora presenti nell'ambiente Microsoft teams. Anche se gli utenti non possono accedere a gruppi, siti, team o contenuti che non sono stati condivisi con essi, possono comunque utilizzare le funzionalità all'interno di Microsoft teams, ad esempio l'avvio di chat, le chiamate vocali e video e l'utilizzo delle app.

Un proprietario di un team o di un gruppo può invitare un utente esterno a diventare Guest in Azure Active Directory, aggiungerli al team, nonché rimuoverli dal team. Un proprietario del team non può, tuttavia, rimuovere l'ospite da Azure Active Directory, ma può essere eseguito solo da un amministratore globale o da un amministratore utente.

Pertanto, è importante eseguire le recensioni dei clienti, nonché capire se gli utenti devono essere rimossi da Azure Active Directory dopo l'eliminazione del team. Potrebbe essere valido un caso in cui gli ospiti possano rimanere nella directory, ad esempio essere membri di uno o più team o altri servizi Microsoft 365 o Azure.

## <a name="teams"></a>Teams

Il contenuto specifico di teams è principalmente costituito da conversazioni.

Le conversazioni nei canali non possono essere copiate o spostate utilizzando la funzionalità native di Microsoft teams. Possono tuttavia essere esportati utilizzando l'API del grafico.

Inoltre, se viene applicato un criterio di conservazione ai team, le conversazioni vengono mantenute e rese disponibili tramite le ricerche di eDiscovery. (Gli elementi trovati nelle ricerche di eDiscovery possono essere esportati, tuttavia non esiste alcun contesto o struttura dalla loro origine originale – sono semplicemente singoli messaggi.)

### <a name="archiving-a-team"></a>Archiviazione di un team

Il vantaggio dell' [archiviazione di un team](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) consiste nel fatto che consente di accedere completamente al team, in modo che gli utenti possano ancora visualizzare le conversazioni dei canali e aprire i file anche se non sono attivi. Inoltre, i team possono essere archiviati se è necessario continuare a lavorare su di essi (come nel caso di un'estensione del progetto).

Quando un team viene archiviato da un proprietario, viene impostato come di sola lettura per i membri sia per il contenuto all'interno del team, sia per il sito di SharePoint associato. L'obiettivo di questa azione è garantire che le conversazioni nei canali siano conservate nello stato esistente, insieme a contenuti basati su SharePoint, ad esempio file e wiki.

Nel sito di SharePoint non vi sono modifiche visibili, ma non è possibile apportare modifiche a nessun file o elenco poiché il gruppo di autorizzazioni basato su SharePoint per il gruppo Microsoft 365 è impostato sul livello di visitatori del sito. Questo include il blocco appunti di OneNote per il team, poiché viene archiviato nella raccolta risorse del sito all'interno del sito di SharePoint.

Quando un team viene archiviato, il gruppo Microsoft 365 sottostante è ancora soggetto ai criteri di scadenza (se impostato) e, come tale, il proprietario deve continuare a rinnovare il team.

Anche se le conversazioni del canale del team e il contenuto del sito di SharePoint sono impostati come di sola lettura, lo stesso non viene applicato ad altri servizi associati:

- È ancora possibile creare, modificare ed eliminare le attività e i bucket di pianificazione.
- I moduli possono comunque ricevere invii
- La cassetta postale di Outlook può ancora ricevere messaggi di posta elettronica
- È ancora possibile modificare i dashboard Power BI, i report e i dati
- I progetti e le roadmap possono essere ancora modificati in Project sul Web
- I video possono ancora essere caricati, modificati ed eliminati in Stream
- I flussi nell'automazione di alimentazione possono ancora essere creati, modificati, eliminati e continueranno a essere eseguiti (avranno esito negativo, se necessario, per inviare un messaggio a un canale del team archiviato)

## <a name="forms"></a>Forms

Quando un modulo può essere spostato da un singolo account a un gruppo, non è possibile spostarlo o copiarlo da un gruppo all'altro. Per una maschera sono disponibili tre opzioni per l'eliminazione di un team.

**Duplicare il modulo**

I moduli possono essere [condivisi come modelli](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), consentendo ad altri utenti di copiarli nel proprio account o in un gruppo. Questo non conserva i dati provenienti da invii di risultati; solo la struttura del modulo, ad esempio le domande e le impostazioni.

**Esportare i risultati in un foglio di calcolo**

Se i dati delle risposte ai moduli devono essere conservati, è possibile [esportarli in un foglio di calcolo di Excel](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). In questo modo vengono esportate solo le domande e le loro risposte come dati, che non includono i grafici creati dai moduli.


**Eliminare il modulo**

Anche se l'eliminazione del gruppo provocherà l'eliminazione di tutti i moduli associati, i membri del gruppo possono [eliminarli direttamente](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) senza essere proprietari del gruppo, ma questo è un passaggio manuale che non fornisce alcun vantaggio aggiuntivo.

## <a name="onenote"></a>OneNote

Il blocco appunti di OneNote incluso in un gruppo è memorizzato nella raccolta risorse del sito all'interno del sito di SharePoint associato. Anche se i file del blocco appunti possono essere distribuiti in più singoli file, non possono essere semplicemente copiati e aperti in modo indipendente. Al contrario, il contenuto del blocco appunti di OneNote deve essere spostato o esportato utilizzando OneNote 2016.

**Spostare pagine e sezioni in un altro blocco appunti**

Lo [spostamento individuale di pagine o sezioni in un altro blocco appunti](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) fornisce ai proprietari la possibilità di ripulire i propri dati e di accettare solo ciò che deve essere mantenuto.

**Esportare l'intero blocco appunti come pacchetto**

Se l'intero blocco appunti deve essere mantenuto con la struttura esistente, può essere [esportato come](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) file del pacchetto di OneNote e quindi importato in un nuovo percorso. In alternativa, può essere utilizzato come metodo per conservare il contenuto in un singolo file anziché la struttura a più file esistente.

**Stampa su PDF**

Negli scenari in cui alcuni contenuti del blocco appunti devono essere conservati solo per riferimento o come record, è possibile stampare singole pagine [in formato PDF e archiviarle altrove](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Cassetta postale e calendario

Non è raro che la cassetta postale associata a un gruppo venga utilizzata, anche se molte conversazioni potrebbero essere state eseguite all'interno dei canali del team. La cassetta postale archivia solo messaggi di posta elettronica che sono stati inviati direttamente a esso e non include messaggi di posta inviata direttamente ai canali.

In alcuni casi, i messaggi di posta elettronica archiviati all'interno della cassetta postale possono essere semplicemente notifiche di riunioni, aggiornamenti delle attività del pianificatore e altro messaggio generato dall'applicazione o dal sistema. È importante che il contenuto della cassetta postale venga esaminato per determinare se il contenuto deve essere conservato o eliminato.

Se un criterio di conservazione viene applicato a Exchange, i messaggi di posta elettronica e gli elementi del calendario vengono mantenuti e disponibili tramite le ricerche di eDiscovery.

**Esportare la posta e il calendario**

I membri del team o del gruppo possono [esportare il contenuto della cassetta postale e del calendario in un file di dati di Outlook/Personal Storage (pst)](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Questo file può quindi essere memorizzato altrove oppure il contenuto può essere importato in una cassetta postale diversa. Il primo non è consigliato poiché il contenuto del file PST non è disponibile per la ricerca senza aprirlo in Outlook e il file stesso può essere danneggiato nel tempo.

**Migrazione del contenuto eseguita da IT**

Gli amministratori possono utilizzare gli strumenti di terze parti per eseguire la migrazione del contenuto della posta elettronica e del calendario tra le cassette postali senza alcuna operazione Un potenziale percorso di archiviazione potrebbe essere una cassetta postale condivisa creata esclusivamente per fungere da "archivio" del contenuto della cassetta postale di gruppo.

## <a name="planner"></a>Planner

Ogni gruppo o team può disporre di più piani. È importante durante il processo di Offboarding garantire che ogni piano venga considerato se il relativo contenuto viene mantenuto. Come gli altri prodotti, esistono diversi approcci per il contenuto di trasferisce in Planner.

**Esportare il piano in un foglio di calcolo**

Se è necessario solo mantenere una copia del piano per la conservazione dei record, l'approccio più semplice consiste nell' [esportare il piano in un foglio di calcolo di Excel](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Si tratta di un'azione unidirezionale, in quanto non è disponibile alcuna opzione per importare i piani da un foglio di calcolo.

> [!IMPORTANT]
> L'esportazione di un piano in Excel richiederà la maggior parte delle informazioni all'interno del piano, ma non includerà commenti, collegamenti o file.

**Copiare e spostare le attività in un altro piano**

Anche se questa è una soluzione, è possibile [copiare o spostare](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) singole attività solo tra i piani all'interno dello stesso gruppo, che nega il vantaggio se il gruppo associato al piano viene eliminato.

**Copia intero piano**

È anche possibile [copiare l'intero piano](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Tuttavia, questo non può essere per un gruppo esistente o anche all'interno dello stesso gruppo. La copia del piano creerà un nuovo gruppo. Inoltre, la copia dell'intero piano non includerà commenti, assegnazioni, collegamenti, allegati o date.

## <a name="power-automate"></a>Automatizzare la potenza

I flussi creati in Power automatizzate e associati a un gruppo o a un team non appartengono al gruppo e, invece, sono di proprietà del creatore e sono semplicemente condivisi con altri utenti e gruppi. In quanto tali, non sono intaccate se un gruppo o un team è stato eliminato.

**Modificare la proprietà del flusso**

Se il flusso di lavoro deve continuare a funzionare, tutti i proprietari possono semplicemente aggiungere altri utenti o gruppi di Microsoft 365 come proprietari.

**Esportare il flusso**

Se il flusso di lavoro non deve continuare a funzionare, ma è necessario conservarlo per un eventuale utilizzo futuro, è possibile [esportarlo come file](https://flow.microsoft.com/blog/import-export-bap-packages/) e importarlo di nuovo in un secondo momento.

## <a name="power-bi"></a>Power BI

I dati e le aree di lavoro di Power BI possono funzionare indipendentemente da gruppi e team e, come altri carichi di lavoro, offrono diversi modi di essere offboarded.

**Copiare i report in un'altra area di lavoro**

Se il report deve essere mantenuto nel relativo stato funzionale oltre la durata del gruppo o del team, è possibile [copiarlo dall'area di lavoro esistente in un'altra area di lavoro all'interno di Power bi](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Esportare dati da un dashboard o da un report**

In alternativa, se il report non deve più essere attivo ma i dati devono essere conservati, è possibile [esportarlo in Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

I progetti e le roadmap creati in Project sul Web possono essere associati ai gruppi di Microsoft 365 e offrono approcci a offboarding simili a Power BI.

**Assegnare il progetto a un altro gruppo**

Se il progetto deve essere mantenuto nello stato funzionale oltre la durata del gruppo o del team, è possibile [assegnarlo a un altro gruppo di Microsoft 365](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) utilizzando l'interfaccia di amministrazione di Dynamics 365.

**Esportare i dati dal progetto o dalla roadmap**

Utilizzando l'interfaccia di amministrazione di Dynamics 365 è possibile [esportare i dati degli utenti dal progetto](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) in un foglio di calcolo oppure, se si utilizza uno script di PowerShell, i dati possono essere esportati in un file di progetto (. MPP) e i formati di file XML.

## <a name="sharepoint"></a>SharePoint
Tutti i file nei canali del team sono archiviati nella raccolta documenti nel sito di SharePoint del gruppo associato. In alcuni casi, potrebbe esistere contenuto diverso da quello dei documenti in SharePoint, ad esempio elenchi o pagine.
I file vengono in genere archiviati in tre posizioni principali all'interno di un sito di SharePoint:

- Pagine-raccolta pagine del sito
- Immagini utilizzate nelle pagine – raccolta di risorse del sito
- File nei canali – raccolta documenti
- Pagine wiki – raccolta dati wiki Teams

Se nel sito sono presenti uno o più siti secondari nidificati, sarà necessario ripetere il processo di Offboarding per ogni sito secondario. Se il team contiene canali privati, è presente un sito di SharePoint separato per ogni canale.

È importante quando si rimuovono file da un gruppo o da un team per considerare che possono essere condivisi con gli utenti che non sono membri del gruppo o del team (sia interni che esterni all'organizzazione) e, come tale, potrebbe essere utile comunicargli la modifica imminente.

**Scaricare file**

Nel caso dei file archiviati all'interno di SharePoint in una delle raccolte sopra riportate, queste possono essere [scaricate in un computer locale](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Spostare i file**

Inoltre, è possibile spostare i file in un'altra posizione all'interno di SharePoint, ad esempio una raccolta in un altro sito.
Riferimento https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Esporta elenco** I dati archiviati negli elenchi di SharePoint possono essere [esportati in un foglio di calcolo di Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)e importati di nuovo in un elenco di un altro sito.

In alternativa, è possibile utilizzare uno strumento di terze parti per eseguire la migrazione dell'elenco tra i siti per mantenere la funzione, le visualizzazioni elenco, la formattazione e altri attributi.

**"Esporta" file wiki**

I contenuti wiki all'interno dei canali del team sono archiviati in un file HTML formattato in una raccolta dedicata del sito di SharePoint associato. Non possono essere esportati e importati facilmente in un altro canale wiki, ma possono essere convertiti in un file HTML e aperti come pagina Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Analogamente al potere automatizzato, i video in streaming associati a un gruppo o a un team non sono effettivamente di proprietà del gruppo e non vengono eliminati quando il gruppo viene eliminato. I video in Stream appartengono alla persona che ha caricato o creato il video, anche se aggiungono utenti o gruppi come proprietari. Questo è il caso anche per le riunioni registrate in un canale di teams. sono di proprietà della persona che ha avviato la registrazione.

**Aggiunta di altri proprietari**

Poiché il video viene mantenuto in streaming indipendentemente dall'eliminazione del gruppo, il proprietario originale può [condividere il video con altri utenti e gruppi, aggiungendoli anche come proprietari](https://docs.microsoft.com/stream/portal-edit-video).

**Scaricare il video**

Negli scenari in cui il video non deve essere conservato in stream o deve essere archiviato in una posizione alternativa, ad esempio un sistema di gestione dei record, [è possibile scaricarlo localmente](https://docs.microsoft.com/stream/portal-download-video) dal proprietario.

## <a name="yammer"></a>Yammer

A differenza delle conversazioni in Microsoft teams, Yammer offre sia gli utenti che le opzioni degli amministratori per spostare o esportare conversazioni.

**Spostare le conversazioni in un altro gruppo o community**

Le conversazioni possono essere spostate in un altro gruppo di Yammer da qualsiasi utente, non solo da proprietari o amministratori. Questo è possibile sia nelle [classiche Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872), sia nelle nuove interfacce [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) .

**Esportare i dati di rete**

Gli amministratori di rete di Yammer possono eseguire un' [esportazione dei dati di rete](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), ma in questo modo verranno esportate tutte le conversazioni per l'intera rete. L'esportazione risultante elenca tuttavia l'ID del gruppo, quindi è possibile filtrare le conversazioni in base a questo.
