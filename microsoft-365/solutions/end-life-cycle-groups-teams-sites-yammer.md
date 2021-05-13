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
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346427"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opzioni di fine ciclo di vita per gruppi, team e Yammer

Microsoft 365 I gruppi e Microsoft Teams funzionano con più servizi connessi. Quando un gruppo o un team viene eliminato, viene eliminata anche la maggior parte delle informazioni nei servizi connessi. In questo articolo vengono descritte le opzioni per conservare le informazioni spostando le informazioni dal gruppo o dal team prima dell'eliminazione.

Una pratica comune per i gruppi o i team che non sono più necessari consiste nello spostare i file fuori dal team e archiviarli in un'altra posizione, ad esempio una raccolta documenti SharePoint documenti. Questa procedura si basa su uno stile di lavoro legacy in cui le informazioni vengono archiviate in file e cartelle e le comunicazioni vengono condotte tramite posta elettronica.

Nella tabella seguente vengono descritti i servizi associati a gruppi e team e i tipi principali di contenuto presenti in ognuno di essi:

|Servizio|Tipi di contenuto|
|:------|:---------------|
|Teams|Conversazioni di canale, file nei canali|
|Moduli|Struttura e risultati del sondaggio|
|OneNote|Blocco appunti|
|Outlook|Posta e calendario|
|Planner|Project informazioni sullo stato e sull'attività|
|Power Automate|Flussi di lavoro|
|Power BI|Dati, report e dashboard|
|Project sul Web|Project piani|
|Roadmap|Roadmap|
|SharePoint|File, elenchi, Teams wiki del canale|
|Stream|Video|
|Yammer|Conversazioni|

Quando si elimina un gruppo o un team, viene eliminata anche la maggior parte delle risorse associate. Le eccezioni includono:

- I video in Stream rimangono e sono di proprietà della persona che li ha caricati/registrati
- I flussi Power Automate rimangono e sono di proprietà della persona che li ha creati.
- Project e i dati della roadmap Project sul Web rimangono nel CDS e possono essere ripristinati separatamente.

I gruppi e i team rimangono in uno stato di eliminazione recidiva per 30 giorni e possono essere ripristinati in qualsiasi momento. Tuttavia, dopo i 30 giorni, le risorse associate, ad esempio i servizi e il contenuto, vengono eliminate dall'Microsoft 365 locale. Qualsiasi contenuto protetto da un criterio di conservazione rimane disponibile tramite le ricerche eDiscovery.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerazioni sulla fine del ciclo di vita per i servizi connessi a gruppi

Esistono tre aree chiave che i proprietari di team e gruppi e gli amministratori IT devono considerare quando si elimina un gruppo o un team.

**Contenuto**

Il contenuto deve essere conservato dopo che il team non è più presente? È sufficiente affidarsi alle funzionalità di conservazione di Microsoft 365 o parte del contenuto nelle app e nei servizi che non offrono la conservazione? È necessario conservare il contenuto per la gestione dei record, l'archiviazione o l'utilizzo futuro e per scopi di riferimento?

Per evitare potenziali perdite di dati, queste domande devono essere poste prima dell'archiviazione o dell'eliminazione di qualsiasi team.

**Servizi**

Il contenuto deve rimanere nella forma di lavoro corrente? Ad esempio, il report Power BI deve continuare ad essere accessibile? I risultati del modulo devono essere disponibili nella visualizzazione riepilogo visivo? Gli elenchi in SharePoint sono collegati o incorporati in qualsiasi posizione?

Queste domande devono essere poste prima che il gruppo sottostante venga eliminato perché l'esportazione del contenuto potrebbe non essere sufficiente.

**Guest**

Quando gli utenti guest vengono invitati a un team, viene creato un account guest nel Azure Active Directory dell'organizzazione host prima di aggiungerli al team. Quando un team viene eliminato, gli utenti guest non vengono rimossi da Azure Active Directory. Anche se gli utenti guest non possono accedere a gruppi, siti, team o contenuti che non sono stati condivisi con loro, possono comunque usare funzionalità all'interno di Microsoft Teams come l'avvio di chat, chiamate vocali e videochiamate e l'uso di app.

Il proprietario di un team o di un gruppo può invitare un utente esterno all'organizzazione a diventare guest in Azure Active Directory aggiungendolo a un team. Un proprietario del team non può tuttavia rimuovere il guest da Azure Active Directory. L'eliminazione di account può essere eseguita solo da un amministratore globale o da un amministratore utente.

È importante eseguire le recensioni degli utenti guest e capire se gli utenti guest devono essere rimossi Azure Active Directory al momento dell'eliminazione del team. Può essere valido che gli utenti guest rimangano nella directory, ad esempio essere membri di altri team o usare altri servizi Microsoft 365 o Azure.

## <a name="teams"></a>Teams

Teams contenuto specifico è principalmente sotto forma di conversazioni.

Le conversazioni nei canali non possono essere copiate o spostate usando la funzionalità Microsoft Teams nativa. Tuttavia, possono essere esportati usando l'API Graph.

Inoltre, se un criterio di conservazione viene applicato a Teams, le conversazioni vengono mantenute e disponibili tramite le ricerche eDiscovery. Utilizzando eDiscovery avanzato è possibile [ricostruire una conversazione Teams chat.](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>Archiviazione di un team

Il vantaggio [dell'archiviazione di un team](/microsoftteams/archive-or-delete-a-team) è che fornisce l'accesso completo al team così come era. Gli utenti possono comunque esplorare le conversazioni dei canali e aprire i file anche se non sono attivi. Inoltre, i team possono essere disarchiviati se è necessario continuare a lavorare su di essi (ad esempio, se un progetto è esteso).

Quando un team viene archiviato da un proprietario, è impostato su sola lettura per i membri sia per il contenuto all'interno del team che, se selezionato, per il sito SharePoint associato. L'obiettivo di questa azione è garantire che le conversazioni nei canali siano mantenute nello stato esistente, insieme a contenuti basati su SharePoint, ad esempio file e wiki.

Nel sito SharePoint non sono presenti modifiche visibili. Tuttavia, non è possibile apportare modifiche a file o elenchi perché le autorizzazioni SharePoint per il gruppo di Microsoft 365 sono impostate su **Visitatori del sito**. Include il blocco appunti OneNote per il team, archiviato nella raccolta Risorse sito all'interno del SharePoint sito.

Quando un team viene archiviato, il gruppo Microsoft 365 sottostante è ancora soggetto ai criteri di scadenza (se impostato) e di conseguenza il proprietario deve continuare a rinnovare il team.

Mentre le conversazioni di canale del team SharePoint contenuto del sito sono impostate su sola lettura, lo stesso non viene applicato ad altri servizi associati:

- I bucket e le attività di Planner possono comunque essere creati, modificati ed eliminati.
- I moduli possono comunque ricevere invii.
- La Outlook cassetta postale può comunque ricevere messaggi di posta elettronica.
- Power BI dashboard, report e dati possono ancora essere modificati.
- I progetti e le roadmap possono ancora essere modificati in Project sul Web.
- I video possono comunque essere caricati, modificati ed eliminati in Stream.
- I flussi Power Automate possono ancora essere creati, modificati, eliminati e continueranno a essere eseguiti. Tuttavia, non riusciranno, se necessario, a inviare un messaggio a un canale del team archiviato.

## <a name="forms"></a>Moduli

Anche se un modulo può essere spostato da un singolo account a un gruppo, non può essere spostato o copiato da un gruppo a un altro. Quando un team viene eliminato, sono disponibili tre opzioni per un modulo.

**Duplicare il modulo**

I moduli possono [essere condivisi come modelli,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)consentendo ad altri utenti di copiarlo nel proprio account o in un gruppo. In questo modo non vengono conservati i dati dagli invii di risultati. solo la struttura del modulo, ad esempio domande e impostazioni.

**Esportare i risultati in un foglio di calcolo**

Se i dati delle risposte del modulo devono essere conservati, è possibile ottenere questo risultato esportando i risultati in un foglio Excel [foglio di calcolo.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Verranno esportate solo le domande e le relative risposte come dati, ma non i grafici creati dai moduli.

**Eliminare il modulo**

Anche se l'eliminazione del gruppo comporta l'eliminazione di [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) tutti i moduli associati, i membri del gruppo possono eliminarli direttamente senza essere proprietari del gruppo. Tuttavia, si tratta di un passaggio manuale che non offre alcun vantaggio aggiuntivo.

## <a name="onenote"></a>OneNote

Il OneNote blocco appunti incluso in un gruppo viene archiviato nella raccolta Risorse sito all'interno del SharePoint sito associato. Anche se a volte i file del blocco appunti possono essere distribuiti su più singoli file, non possono essere copiati e aperti in modo indipendente. Al contrario, il contenuto del OneNote blocco appunti deve essere spostato o esportato utilizzando OneNote 2016.

**Spostare pagine e sezioni in un altro blocco appunti**

[Lo spostamento individuale di pagine o sezioni in](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) un altro blocco appunti offre ai proprietari l'opportunità di ripulire i dati e di utilizzare solo gli elementi da conservare.

**Esportare l'intero blocco appunti come pacchetto**

Se l'intero blocco appunti deve essere conservato con la struttura esistente, può essere esportato come file di pacchetto OneNote e quindi importato [in](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) un nuovo percorso. Al contrario, può essere utilizzato come metodo per conservare il contenuto in un singolo file anziché nella struttura multi-file esistente.

**Stampa su PDF**

In scenari in cui parte del contenuto del blocco appunti deve essere conservata solo come riferimento o come record, le singole pagine possono essere stampate in formato PDF e archiviate [altrove.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Cassetta postale e calendario

Non è raro utilizzare la cassetta postale associata al gruppo, anche se è possibile che siano state condotte molte conversazioni all'interno dei canali del team. La cassetta postale archivia solo i messaggi di posta elettronica inviati direttamente a essa e non include i messaggi inviati direttamente ai canali.

In alcuni casi, i messaggi di posta elettronica archiviati nella cassetta postale possono essere notifiche di riunioni, aggiornamenti delle attività di Planner e altri messaggi generati dal sistema o dall'app. è importante che il contenuto della cassetta postale sia esaminato per determinare se il contenuto deve essere conservato o eliminato.

Se un criterio di conservazione viene applicato in Exchange, i messaggi di posta elettronica e gli elementi del calendario vengono conservati e disponibili tramite le ricerche eDiscovery.

**Esportare posta e calendario**

I membri del team o del gruppo possono esportare il contenuto della cassetta postale e del calendario in [un file Outlook PST (Personal Archiviazione Data/ Personal Archiviazione).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Questo file può quindi essere archiviato altrove oppure il contenuto può essere importato in una cassetta postale diversa. Il primo non è consigliato perché il contenuto del file PST non è ricercabile senza aprirlo in Outlook e il file stesso può danneggiarsi nel tempo.

**Migrazione del contenuto eseguita dall'IT**

Gli amministratori possono utilizzare strumenti di terze parti per eseguire la migrazione della posta elettronica e del contenuto del calendario tra le cassette postali senza alcun intervento da parte dell'utente. Un potenziale percorso di archiviazione potrebbe essere una cassetta postale condivisa creata esclusivamente per fungere da "archivio" del contenuto della cassetta postale di gruppo.

## <a name="planner"></a>Planner

Ogni gruppo o team può avere più piani. Durante il processo di off-boarding è importante assicurarsi che i requisiti di conservazione siano soddisfatti per ogni piano. Come gli altri servizi, in Planner sono disponibili diversi approcci per i contenuti off-board.

**Esportare il piano in un foglio di calcolo**

Se è necessario conservare una copia del piano solo a scopo di conservazione dei record, l'approccio più semplice consiste nell'esportare il piano in un foglio Excel [foglio di calcolo.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Si tratta di un'azione unidireistica: non è disponibile alcuna opzione per importare piani da un foglio di calcolo.

> [!IMPORTANT]
> L'esportazione di un piano Excel la maggior parte delle informazioni nel piano, ma non include commenti, collegamenti o file.

**Copiare e spostare attività in un altro piano**

Durante la copia o lo spostamento di attività in [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) un altro piano sembra una soluzione, le singole attività possono essere copiate o spostate solo tra piani all'interno dello stesso gruppo. Ciò non consente di eseguire il backup dei dati se il gruppo associato al piano viene eliminato.

**Copiare l'intero piano**

È anche possibile copiare [l'intero piano](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Non è possibile eseguire la copia in un gruppo esistente. Copiando il piano verrà creato un nuovo gruppo. Inoltre, la copia dell'intero piano non includerà commenti, assegnazioni, collegamenti, allegati o date.

## <a name="power-automate"></a>Power Automate

I flussi creati Power Automate e associati a un gruppo o a un team non appartengono al gruppo. Sono di proprietà del creatore e semplicemente condivisi con altri utenti e gruppi. Di conseguenza, non sono interessati se un gruppo o un team viene eliminato.

**Modificare la proprietà del flusso**

Se il flusso deve continuare a operare, tutti i proprietari possono aggiungere altri utenti o Microsoft 365 come proprietari.

**Esportare il flusso**

Se il flusso non deve continuare a operare, ma deve essere conservato per un uso futuro potenziale, può essere esportato come [file](https://flow.microsoft.com/blog/import-export-bap-packages/) e importato di nuovo in un secondo momento.

## <a name="power-bi"></a>Power BI

Power BI dati e aree di lavoro possono operare in modo indipendente dai gruppi e dai team e, come altri carichi di lavoro, offrono diversi modi di essere off-boarded.

**Copiare report in un'altra area di lavoro**

Se è necessario il report dopo l'eliminazione del gruppo o del team, è possibile copiarlo dall'area di lavoro esistente in un'altra area di lavoro [all'interno di Power BI](/power-bi/connect-data/service-datasets-copy-reports).

**Esportare dati da un dashboard o da un report**

Se invece il report non deve più essere attivo ma i dati devono essere conservati, è possibile esportarlo in [Excel](/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

I progetti e le roadmap creati in Project per il Web sono associati Microsoft 365 gruppi e hanno approcci per l'off-boarding simili a Power BI.

**Assegnare il progetto a un altro gruppo**

Se il progetto deve essere conservato nello stato funzionale oltre la durata del gruppo o del team, può essere assegnato a un gruppo Microsoft 365 [diverso.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) Questa operazione può essere eseguita tramite l'centro di amministrazione di Dynamics 365.

**Esportare i dati dal progetto o dalla roadmap**

Utilizzando l'interfaccia di amministrazione di Dynamics 365, è possibile esportare i dati utente [dal progetto](/project-for-the-web/export-user-data-from-project-for-the-web) a un foglio di calcolo. I dati possono essere esportati anche in Project file (. MPP) e formati di file XML tramite PowerShell.

## <a name="sharepoint"></a>SharePoint

Tutti i file nei canali del team vengono archiviati nel SharePoint del gruppo associato. In alcuni casi, il contenuto diverso da documenti può esistere in SharePoint, ad esempio elenchi o pagine.

I file vengono in genere archiviati in tre posizioni principali all'interno di SharePoint sito:

- Pagine - Raccolta pagine sito
- Immagini utilizzate nelle pagine - Raccolta Risorse del sito
- File nei canali - Raccolta documenti
- Pagine wiki : Teams raccolta dati wiki

Se il sito include uno o più siti secondari, il processo di off-boarding dovrà essere ripetuto per ogni sito secondario. Se il team contiene canali privati, esiste un sito SharePoint separato per ogni canale.

Quando si rimuovono file da un gruppo o da un team, è importante considerare che possono essere condivisi con utenti che non sono membri del gruppo o del team. È possibile comunicare loro la modifica imminente.

**Scaricare i file**

I file archiviati SharePoint in una delle librerie menzionate in precedenza possono essere [scaricati in un computer locale.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Spostare i file**

Inoltre, i file possono essere spostati in un altro [percorso all'interno di SharePoint, ad esempio](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)una raccolta in un sito diverso.

**Esporta elenco**

I dati archiviati SharePoint elenchi possono essere [esportati](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)in un Excel foglio di calcolo e importati di nuovo in un elenco in un altro sito.

In alternativa, è possibile utilizzare uno strumento di terze parti per eseguire la migrazione dell'elenco tra siti per mantenere funzioni, visualizzazioni elenco, formattazione e altri attributi.

**File wiki "Esporta"**

I contenuti wiki all'interno dei canali del team vengono archiviati in un file in formato HTML in una raccolta dedicata del sito SharePoint associato. Non possono essere esportati e importati in un altro wiki di canale, ma possono essere convertiti in un file HTML e aperti come pagina Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Come Power Automate, i video in Stream associati a un gruppo o team non sono effettivamente di proprietà del gruppo e non vengono eliminati quando il gruppo viene eliminato. I video in Stream sono di proprietà della persona che ha caricato o creato il video, anche se aggiungono utenti o gruppi come proprietari. Le riunioni registrate in un Teams sono di proprietà della persona che ha avviato la registrazione.

**Aggiunta di altri proprietari**

Poiché il video viene conservato in Stream quando il gruppo viene eliminato, il proprietario originale può condividere il video con altri utenti e [gruppi, aggiungendoli](/stream/portal-edit-video)anche come proprietari.

**Scaricare il video**

In scenari in cui il video non deve essere conservato in Stream o deve essere archiviato in una posizione alternativa, ad esempio un sistema di gestione dei record, un proprietario può [scaricarlo in locale.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

A differenza delle conversazioni Microsoft Teams, Yammer agli utenti e agli amministratori opzioni per spostare o esportare conversazioni.

**Spostare conversazioni in un altro gruppo o community**

Le conversazioni possono essere spostate in un altro Yammer da qualsiasi utente, non solo dai proprietari o dagli amministratori. Ciò è possibile sia nella [versione classica Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) che nelle nuove [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) interfacce.

**Esportare i dati di rete**

Yammer gli amministratori di rete [esportano i dati di rete.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) In questo modo, tuttavia, verranno esportate tutte le conversazioni per l'intera rete. L'esportazione risultante elenca l'ID gruppo. È possibile filtrare le conversazioni in base a questo ID.
