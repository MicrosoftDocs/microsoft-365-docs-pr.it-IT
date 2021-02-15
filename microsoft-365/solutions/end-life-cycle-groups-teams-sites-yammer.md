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

I gruppi di Microsoft 365 e Microsoft Teams funzionano con un'ampia gamma di servizi connessi. Quando un gruppo o un team viene eliminato, viene eliminata anche la maggior parte delle informazioni nei servizi connessi. In questo articolo vengono descritte le opzioni per conservare le informazioni spostando le informazioni fuori dal gruppo o dal team prima dell'eliminazione.

Una procedura comune per i gruppi o i team che non sono più necessari consiste nello spostare i file fuori dal team e archiviarli in un'altra posizione, ad esempio una raccolta documenti di SharePoint che funge da archivio o archivio. Questa procedura si basa su uno stile legacy di lavoro in cui le informazioni vengono archiviate all'interno di file e cartelle e le comunicazioni vengono condotte tramite posta elettronica.

Nella tabella seguente vengono descritti i servizi associati a gruppi e team e i tipi principali di contenuto disponibili in ognuno di essi:

|Servizio|Tipi di contenuto|
|:------|:---------------|
|Teams|Conversazioni di canale, file nei canali|
|Forms|Struttura e risultati del sondaggio|
|OneNote|Blocco appunti|
|Outlook|Posta e calendario|
|Planner|Informazioni sullo stato del progetto e sulle attività|
|Power Automate|Flussi di lavoro|
|Power BI|Dati, report e dashboard|
|Project sul Web|Piani di progetto|
|Roadmap|Roadmap|
|SharePoint|File, elenchi, dati wiki del canale di Teams|
|Stream|Video|
|Yammer|Conversazioni|

Quando si elimina un gruppo o un team, viene eliminata anche la maggior parte delle risorse associate. Alcune delle eccezioni includono i video in Stream, che rimangono e sono ancora di proprietà della persona che li ha caricati/registrati, così come i flussi in Power Automate. I dati di project e roadmap in Project sul Web rimangono nel CDS e possono essere ripristinati separatamente.

I gruppi e i team rimangono in uno stato di eliminazione recisa per 30 giorni e possono essere ripristinati in qualsiasi momento. Tuttavia, dopo i 30 giorni, le risorse associate, ad esempio servizi e contenuto, vengono completamente eliminate dall'ambiente Microsoft 365. Qualsiasi contenuto protetto da un criterio di conservazione rimane disponibile tramite le ricerche eDiscovery.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerazioni sulla fine del ciclo di vita per i servizi connessi a gruppi

Esistono tre aree chiave che i proprietari del team e del gruppo e gli amministratori IT devono considerare quando eliminano un gruppo o un team.

**Contenuto**

Il contenuto deve essere conservato dopo che il team non è più funzionante o esistente? È sufficiente affidarsi alle funzionalità di conservazione di Microsoft 365 o parte dei contenuti nelle app e nei servizi che non offrono la conservazione? Il contenuto deve essere conservato a scopo di gestione dei record, per scopi di archiviazione o per scopi futuri e di riferimento?

Queste domande devono essere poste prima dell'archiviazione o dell'eliminazione di qualsiasi team, per evitare potenziali perdite di dati.

**Servizi**

Oltre al contenuto in varie app e servizi, è necessario che rimangano nel modulo funzionante corrente? Ad esempio, il report di Power BI deve continuare a essere accessibile, i risultati del modulo devono essere disponibili nella visualizzazione di riepilogo visiva, gli elenchi in SharePoint sono collegati o incorporati in qualsiasi posizione?

In modo analogo alle considerazioni relative al contenuto, queste domande devono essere poste prima dell'eliminazione del gruppo sottostante, in quanto la semplice esportazione del contenuto potrebbe non essere sufficiente.

**Guest**

Quando gli utenti guest vengono invitati a un team, il flusso di lavoro crea la propria identità in Azure Active Directory dell'organizzazione host prima di aggiungerli al team. Quando un team viene eliminato, gli utenti guest non vengono rimossi da Azure Active Directory e, di conseguenza, esistono ancora nell'ambiente di Microsoft Teams. Anche se gli utenti guest non possono accedere a gruppi, siti, team o contenuti che non sono stati condivisi con loro, possono comunque utilizzare potenzialmente funzionalità all'interno di Microsoft Teams, ad esempio l'avvio di chat, chiamate vocali e video e l'uso di app.

Il proprietario di un team o di un gruppo può invitare un utente esterno a diventare guest in Azure Active Directory, aggiungerlo al team e rimuoverlo dal team. Un proprietario del team non può tuttavia rimuovere il guest da Azure Active Directory. Questa operazione può essere eseguita solo da un amministratore globale o da un amministratore utente.

È quindi importante eseguire le recensioni degli utenti guest, oltre a capire se gli utenti guest devono essere rimossi da Azure Active Directory al momento dell'eliminazione del team. Potrebbe essere valido che gli utenti guest rimangano nella directory, ad esempio essere membri di uno o più altri team o usare altri servizi di Microsoft 365 o Azure.

## <a name="teams"></a>Teams

Il contenuto specifico di Teams è principalmente sotto forma di conversazioni.

Le conversazioni nei canali non possono essere copiate o spostate usando la funzionalità nativa di Microsoft Teams. Possono tuttavia essere esportati con l'API Graph.

Inoltre, se un criterio di conservazione viene applicato a Teams, le conversazioni vengono mantenute e disponibili tramite le ricerche eDiscovery. Gli elementi trovati nelle ricerche eDiscovery possono essere esportati, ma non rimane alcun contesto o struttura dall'origine originale, ma sono semplicemente singoli messaggi.

### <a name="archiving-a-team"></a>Archiviazione di un team

Il vantaggio dell'archiviazione di un [team](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) è che offre accesso completo al team così come lo era, in modo che gli utenti possano comunque sfogliare le conversazioni dei canali e aprire i file anche se non sono attivi. È inoltre possibile annullare l'archiviazione dei team se è necessario continuare a lavorarvi, ad esempio nel caso di un'estensione del progetto.

Quando un team viene archiviato da un proprietario, è impostato in sola lettura per i membri sia per il contenuto all'interno del team che, se selezionato, per il sito di SharePoint associato. L'obiettivo di questa azione è garantire che le conversazioni nei canali siano conservate nello stato esistente, insieme al contenuto basato su SharePoint, ad esempio file e wiki.

Nel sito di SharePoint non sono presenti modifiche visibili, ma non è possibile apportare modifiche a file o elenchi poiché il gruppo di autorizzazioni basato su SharePoint per il gruppo di Microsoft 365 è impostato sul livello Visitatori del sito. Include il blocco appunti di OneNote per il team, in quanto è archiviato nella raccolta Risorse del sito all'interno del sito di SharePoint.

Quando un team viene archiviato, il gruppo di Microsoft 365 sottostante è ancora soggetto ai criteri di scadenza (se impostato) e di conseguenza il proprietario deve continuare a rinnovare il team.

Mentre le conversazioni del canale del team e il contenuto del sito di SharePoint sono impostati come di sola lettura, lo stesso non viene applicato ad altri servizi associati:

- I bucket e le attività di Planner possono comunque essere creati, modificati ed eliminati
- I moduli possono comunque ricevere invii
- La cassetta postale di Outlook può comunque ricevere messaggi di posta elettronica
- I dashboard, i report e i dati di Power BI possono comunque essere modificati
- I progetti e le guide di orientamento possono comunque essere modificati in Project sul Web
- I video possono comunque essere caricati, modificati ed eliminati in Stream
- I flussi in Power Automate possono comunque essere creati, modificati, eliminati e continueranno a essere eseguiti (avranno tuttavia esito negativo, se necessario per inviare un messaggio a un canale del team archiviato)

## <a name="forms"></a>Forms

Anche se un modulo può essere spostato da un singolo account a un gruppo, non può essere spostato o copiato da un gruppo a un altro. Quando un team viene eliminato, sono disponibili tre opzioni per un modulo.

**Duplicare il modulo**

I moduli possono [essere condivisi come modelli,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)consentendo ad altri utenti di copiarlo nel proprio account o in un gruppo. In questo modo non vengono mantenuti i dati degli invii di risultati; solo la struttura del modulo, ad esempio domande e impostazioni.

**Esportare i risultati in un foglio di calcolo**

Se i dati del modulo devono essere conservati, è possibile esportare i risultati in un foglio [di calcolo di Excel.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Verranno esportate solo le domande e le relative risposte come dati, non includendo i grafici creati dai moduli.


**Eliminare il modulo**

Anche se l'eliminazione del gruppo comporta anche l'eliminazione [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) dei moduli associati, i membri del gruppo possono eliminarli direttamente senza essere proprietari del gruppo, ma si tratta di un passaggio manuale che non offre alcun vantaggio aggiuntivo.

## <a name="onenote"></a>OneNote

Il blocco appunti di OneNote incluso in un gruppo è archiviato nella raccolta Risorse del sito all'interno del sito di SharePoint associato. Anche se a volte i file del blocco appunti possono essere distribuiti su più singoli file, non possono essere semplicemente copiati e aperti in modo indipendente. Al contrario, il contenuto del blocco appunti di OneNote deve essere spostato o esportato utilizzando OneNote 2016.

**Spostare pagine e sezioni in un altro blocco appunti**

[Lo spostamento individuale di pagine o sezioni in](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) un altro blocco appunti offre ai proprietari l'opportunità di pulire i dati e di utilizzare solo gli elementi da conservare.

**Esportare l'intero blocco appunti come pacchetto**

Se l'intero blocco appunti deve essere conservato con la struttura esistente, può essere esportato come file di pacchetto di [OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) e quindi importato in un nuovo percorso. In alternativa, è possibile utilizzare questo metodo per conservare il contenuto in un singolo file anziché nella struttura multi-file esistente.

**Stampa su PDF**

In scenari in cui parte del contenuto del blocco appunti deve essere conservato solo come riferimento o come record, le singole pagine possono essere stampate in formato PDF e archiviate [altrove.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Cassetta postale e calendario

Non è raro che la cassetta postale associata al gruppo venga utilizzata, anche se è possibile che siano state condotte molte conversazioni all'interno dei canali del team. La cassetta postale archivia solo i messaggi di posta elettronica inviati direttamente a essa e non include i messaggi inviati direttamente ai canali.

In alcuni casi, i messaggi di posta elettronica archiviati all'interno della cassetta postale possono essere semplicemente notifiche di riunioni, aggiornamenti delle attività di Planner e altri messaggi generati dall'app o dal sistema. È importante esaminare il contenuto della cassetta postale per determinare se il contenuto deve essere conservato o eliminato.

Se un criterio di conservazione viene applicato a Exchange, i messaggi di posta elettronica e gli elementi del calendario vengono mantenuti e disponibili tramite le ricerche eDiscovery.

**Esportare posta e calendario**

I membri del team o del gruppo possono esportare il contenuto della cassetta postale e del calendario in un [file PST (Data/Personal Storage) di Outlook.](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Questo file può quindi essere archiviato altrove oppure il contenuto può essere importato in una cassetta postale diversa. Il primo non è consigliato perché il contenuto del file PST non è disponibile per la ricerca senza aprirlo in Outlook e il file stesso può danneggiarsi nel tempo.

**Migrazione del contenuto eseguita dall'IT**

Gli amministratori possono utilizzare strumenti di terze parti per eseguire la migrazione della posta elettronica e del contenuto del calendario tra le cassette postali senza alcun intervento dell'utente. Un possibile percorso di archiviazione potrebbe essere una cassetta postale condivisa creata esclusivamente per fungere da "archivio" del contenuto della cassetta postale del gruppo.

## <a name="planner"></a>Planner

Ogni gruppo o team può avere più piani. Durante il processo di offboarding è importante assicurarsi che ogni piano sia indirizzato alla conservazione del contenuto. Come gli altri prodotti, esistono diversi approcci per eseguire l'offboard del contenuto in Planner.

**Esportare il piano in un foglio di calcolo**

Se è necessario conservare una copia del piano solo a scopo di conservazione dei record, l'approccio più semplice consiste nell'esportare il piano in un [foglio di calcolo di Excel.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Si tratta di un'azione unidirestica, in quanto non è disponibile alcuna opzione per importare piani da un foglio di calcolo.

> [!IMPORTANT]
> L'esportazione di un piano in Excel includerà la maggior parte delle informazioni all'interno del piano, ma non includerà commenti, collegamenti o file.

**Copiare e spostare attività in un altro piano**

Anche se sembra una soluzione, le [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) singole attività possono essere copiate o spostate solo tra piani all'interno dello stesso gruppo, il che nega il vantaggio se il gruppo associato al piano viene eliminato.

**Copiare l'intero piano**

È inoltre possibile [copiare l'intero piano.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Tuttavia, non può essere per un gruppo esistente o anche all'interno dello stesso gruppo. Copiando il piano verrà creato un nuovo gruppo. Inoltre, la copia dell'intero piano non includerà commenti, assegnazioni, collegamenti, allegati o date.

## <a name="power-automate"></a>Power Automate

I flussi creati in Power Automate e associati a un gruppo o a un team non appartengono al gruppo e sono invece di proprietà dell'autore e semplicemente condivisi con altri utenti e gruppi. Di conseguenza, non sono interessati se un gruppo o un team viene eliminato.

**Modificare la proprietà del flusso**

Se il flusso di lavoro deve continuare a operare, tutti i proprietari possono semplicemente aggiungere altri utenti o gruppi di Microsoft 365 come proprietari.

**Esportare il flusso**

Se il flusso di lavoro non deve continuare a operare, ma deve essere conservato per un utilizzo futuro potenziale, può essere esportato come [file](https://flow.microsoft.com/blog/import-export-bap-packages/) e importato di nuovo in un secondo momento.

## <a name="power-bi"></a>Power BI

I dati e le aree di lavoro di Power BI possono operare in modo indipendente dai gruppi e dai team e, come altri carichi di lavoro, offrono diversi modi di eseguire l'offboarded.

**Copiare report in un'altra area di lavoro**

Se il report deve essere conservato nello stato funzionale oltre il ciclo di vita del gruppo o del team, può essere copiato dall'area di lavoro esistente in un'altra area di lavoro all'interno di [Power BI.](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)

**Esportare dati da un dashboard o da un report**

In alternativa, se il report non deve più essere attivo ma i dati devono essere conservati, è possibile [esportarlo in Excel.](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

I progetti e le roadmap creati in Project sul Web possono essere associati ai gruppi di Microsoft 365 e offrono approcci all'offboarding simili a Power BI.

**Assegnare il progetto a un altro gruppo**

Se il progetto deve essere conservato nello stato funzionale oltre la durata del gruppo o del team, può essere assegnato a un gruppo di [Microsoft 365](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) diverso tramite l'area di amministrazione di Dynamics 365.

**Esportare i dati dal progetto o dalla roadmap**

Utilizzando l'interfaccia di amministrazione di Dynamics [](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 365 è possibile esportare i dati utente dal progetto in un foglio di calcolo o se si usa uno script di PowerShell i dati possono essere esportati in un file di Progetto (. MPP) e formati di file XML.

## <a name="sharepoint"></a>SharePoint
Tutti i file nei canali del team vengono archiviati nella raccolta documenti nel sito di SharePoint del gruppo associato. In alcuni casi può esistere contenuto diverso da documenti in SharePoint, ad esempio elenchi o pagine.
I file vengono in genere archiviati in tre percorsi principali all'interno di un sito di SharePoint:

- Pagine - Raccolta pagine del sito
- Immagini utilizzate nelle pagine - Raccolta Risorse del sito
- File nei canali - Raccolta documenti
- Pagine wiki - Raccolta dati wiki di Teams

Se al sito sono annidati uno o più siti secondari, il processo di offboarding dovrà essere ripetuto per ogni sito secondario. Se il team contiene canali privati, esiste un sito di SharePoint separato per ogni canale.

Quando si rimuovono file da un gruppo o da un team, è importante considerare che possono essere condivisi con utenti che non sono membri del gruppo o del team (interni o esterni all'organizzazione) e di conseguenza può essere utile comunicare loro l'imminente modifica.

**Scaricare i file**

Nel caso di file archiviati all'interno di SharePoint in una delle raccolte menzionate in precedenza, questi possono essere [scaricati in un computer locale.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Spostare i file**

Inoltre, i file possono essere spostati in un'altra posizione all'interno di SharePoint, ad esempio una raccolta in un sito diverso.
Riferimento: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Esporta elenco** I dati archiviati negli elenchi di SharePoint possono essere [esportati](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)in un foglio di calcolo di Excel e importati di nuovo in un elenco in un altro sito.

In alternativa, è possibile utilizzare uno strumento di terze parti per eseguire la migrazione dell'elenco tra i siti per mantenere funzioni, visualizzazioni elenco, formattazione e altri attributi.

**File wiki "Esporta"**

I contenuti wiki all'interno dei canali del team vengono archiviati in un file in formato HTML in una raccolta dedicata del sito di SharePoint associato. Non possono essere esportati e importati in un altro wiki di canale, ma possono essere convertiti in un file HTML e aperti come pagina Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Come Power Automate, i video in Stream associati a un gruppo o a un team non sono effettivamente di proprietà del gruppo e non vengono eliminati quando il gruppo viene eliminato. I video in Stream sono di proprietà della persona che ha caricato o creato il video, anche se aggiungono utenti o gruppi come proprietari. Questo è anche il caso delle riunioni registrate in un canale di Teams; sono di proprietà della persona che ha avviato la registrazione.

**Aggiunta di altri proprietari**

Poiché il video viene conservato in Stream indipendentemente dall'eliminazione del gruppo, il proprietario originale può condividere il video con altri utenti e gruppi, anche aggiungendoli [come proprietari.](https://docs.microsoft.com/stream/portal-edit-video)

**Scaricare il video**

In scenari in cui il video non deve essere conservato in Stream o deve essere archiviato in un percorso alternativo, ad esempio un sistema di gestione dei record, un proprietario può scaricarlo in [locale](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

A differenza delle conversazioni in Microsoft Teams, Yammer offre agli utenti e agli amministratori opzioni per spostare o esportare conversazioni.

**Spostare conversazioni in un altro gruppo o community**

Le conversazioni possono essere spostate in un altro gruppo di Yammer da qualsiasi utente, non solo dai proprietari o dagli amministratori. Ciò è possibile sia in [Yammer classico,](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)sia nelle nuove interfacce di [Yammer.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Esportare i dati di rete**

Gli amministratori della rete Yammer possono eseguire [un'esportazione dei](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)dati di rete, ma in questo modo verranno esportate tutte le conversazioni per l'intera rete. L'esportazione risultante tuttavia elenca l'ID gruppo, quindi è possibile filtrare le conversazioni in base a questo.
