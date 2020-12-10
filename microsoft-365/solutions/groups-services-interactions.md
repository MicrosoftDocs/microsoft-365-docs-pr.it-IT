---
title: Interazioni dei servizi di gruppo
ms.reviewer: ''
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
description: Interazioni dei servizi di gruppo
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613227"
---
# <a name="groups-services-interactions"></a>Interazioni dei servizi di gruppo

I gruppi Microsoft 365 forniscono un tessuto comune per una serie di servizi e carichi di lavoro all'interno della piattaforma Microsoft 365 per fornire un'esperienza connessa per gli utenti finali. Al suo interno, esiste un gruppo di Microsoft 365 per fornire:

- Modalità di gestione dell'appartenenza (Azure AD)
- Una posizione per i messaggi e le conversazioni che devono essere effettuate (cassette postali di Exchange, Microsoft teams, Yammer)
- Un luogo in cui archiviare i file (SharePoint)
- Calendario per la pianificazione (Exchange)
- Un blocco appunti per le note di acquisizione (OneNote)

Al momento della creazione di un gruppo, vengono provisioning anche diverse altre risorse, tuttavia non sono visibili fino a quando non si accede per la prima volta dal servizio:

- Una scheda per la gestione delle attività dei gruppi (Planner)
- Un'area di lavoro per la creazione di report (Power BI)
- Un'area per i video condivisi (Microsoft Stream)
- Un'area per i moduli condivisi (maschere)

In Microsoft 365, gli altri servizi sono in grado di interagire con i gruppi di Microsoft 365 per fornire funzionalità aggiuntive e funzionalità ai membri del gruppo.
Di seguito sono riportati alcuni esempi:

- Applicazioni di alimentazione per le app
- Automatizzare l'alimentazione per i flussi di lavoro
- Project sul Web e guida di orientamento per la gestione di progetti basati su cascata
- Teams per le conversazioni basate su canale
- Yammer per le community di interesse

## <a name="user-interactions-with-groups"></a>Interazioni degli utenti con i gruppi

È possibile creare e gestire i gruppi di Microsoft 365 da diverse interfacce, sia dagli amministratori che dagli utenti finali. 

### <a name="administrative-experiences"></a>Esperienze amministrative

Gli amministratori possono creare e gestire i gruppi di Microsoft 365 da diversi centri di amministrazione del carico di lavoro, interfacce della riga di comando che supportano lo scripting, nonché app personalizzate che interagiscono con l'API del grafico. L'unica eccezione è rappresentata dai gruppi di Yammer, che devono essere creati dall'interno dell'interfaccia Web di Yammer.

**Impostazioni correlate**

Tra le diverse interfacce amministrative in grado di gestire le impostazioni di gruppo esistono diverse sovrapposizioni di cui è necessario essere a conoscenza.

**Interfaccia di amministrazione di Microsoft 365**

Nell'interfaccia di amministrazione di Microsoft 365, l'accesso Guest ai gruppi è abilitato per impostazione predefinita, così come la possibilità di consentire ai proprietari di aggiungere gli utenti. Non sono disponibili ulteriori controlli a livello di organizzazione per i gruppi provenienti da questo interfaccia di amministrazione.

**Interfaccia di amministrazione di Azure AD**

L'interfaccia di amministrazione di Azure AD offre controlli che consentono agli utenti di creare gruppi o di assegnare proprietari nei portali di Azure, nonché di definire le impostazioni dei criteri di scadenza e di denominazione.

L'interfaccia di amministrazione fornisce anche numerose misure di controllo degli inviti che vanno oltre quelle dell'interfaccia di amministrazione di Microsoft 365, ad esempio la possibilità di limitare se gli utenti non proprietari possono invitare anche gli ospiti

**SharePoint**

I siti di SharePoint vengono creati con i gruppi di sicurezza Owner, Member e Visitor, con i primi due corrispondenti alle controparti del gruppo Microsoft 365. Anche se l'appartenenza ai siti di SharePoint Online è generalmente gestita dal gruppo Microsoft 365 associato, non è una relazione bidirezionale. Tutte le modifiche apportate all'appartenenza a livello di gruppo di Microsoft 365 si riflettono in SharePoint, tuttavia se l'appartenenza viene modificata nel gruppo di SharePoint, questo non viene riflesso nel gruppo Microsoft 365.

### <a name="user-experiences"></a>Esperienze degli utenti

Gli utenti finali possono creare gruppi da diversi servizi all'interno di Microsoft 365 e in altri possono condividerli solo con un gruppo.

I servizi seguenti consentono la creazione di gruppi per gli utenti finali:
                         
Progetto di pianificazione di Outlook per il flusso di lavoro Microsoft teams di SharePoint Yammer

**Limitazione della creazione di gruppi**

Un approccio comune per controllare la proliferazione dei team consiste nel limitare gli utenti che possono crearli. Questa operazione può essere svolta solo limitando la creazione di gruppi. In questo modo si può influire sulla possibilità di creare gruppi da altri servizi che potrebbero essere necessari per gli utenti finali. I gruppi di Microsoft 365 non supportano la possibilità di limitare la creazione di gruppi da alcune app o servizi mentre lo consentono ad altri utenti.

L'esperienza della limitazione della creazione del gruppo varia tra le applicazioni e i servizi:


|App o servizio|Funzionalità|
|:-------------|:---------|
|Outlook|L'opzione **nuovo gruppo** è stata rimossa dal menu nuovo nella pagina utenti|
|Planner|**Nuovo piano** spiega che la creazione del gruppo è stata disattivata e che offre di aggiungere il piano a un gruppo esistente.|
|Progetto per il Web e la Guida di orientamento|**Crea menu gruppo** spiega che la creazione del gruppo è limitata e suggerisce l'utilizzo di un gruppo esistente.|
|SharePoint|È ancora in grado di creare un sito del team che non sia connesso a un gruppo.|
|Stream|L'opzione **gruppo** non viene visualizzata nel **menu Crea**.|
|Teams|L'utente non è in grado di creare un team con un nuovo gruppo, ma può comunque creare un team che utilizza un gruppo esistente.<br><br>**La creazione di un** pulsante del team viene sostituita con **create team da un gruppo**.|
|Yammer|**Creare un'** opzione di gruppo viene rimossa dall'esplorazione gruppi principali/comunità.|

## <a name="services-interactions-with-groups"></a>Interazioni dei servizi con i gruppi

Vedere i gruppi nel poster di Microsoft 365 per informazioni sui diversi tipi di gruppi, sul modo in cui vengono creati e gestiti e su alcuni consigli di governance.

[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

Nella tabella seguente viene fornita una panoramica delle interazioni tra i gruppi di Microsoft 365 e diversi servizi:

|Prodotto|Funzionalità|Il servizio<br>esistere senza un gruppo?|Il servizio può essere<br>creare un gruppo?|Elimina l'<br>istanza eliminare il gruppo?|
|:---|:---|:---|:---|:---|
|Azure AD|Appartenenza, controlli di gruppo, ospiti|Sì|Sì|Sì|
|Exchange|Calendario, cassetta postale|Sì|Sì|Sì|
|Forms|Forma|Sì|No|No|
|OneNote|Blocco appunti|Sì|No|No|
|Planner|Scheda attività|No|Sì|Sì|
|App Power Apps|App|Sì|No|No|
|Automatizzare la potenza|Flusso di lavoro|Sì|No|No|
|Power BI (classica)|Workspace|No|Sì|Sì|
|Power BI (nuovo)|Workspace|Sì|No|Sì|
|Project per il web|Piano di progetto|Sì|Sì|No|
|Roadmap|Roadmap|Sì|Sì|No|
|SharePoint|Sito|Sì|Sì|Sì|
|Stream|Canale, video|Sì|Sì|Sì|
|Teams|Del team|No|Sì|Sì|
|Yammer|Gruppo|Sì|Sì|Sì|

Anche se nella tabella precedente viene fornita una panoramica generale delle interazioni di gruppo con i servizi Microsoft 365, esistono numerose sfumature e complessità che è necessario comprendere. Nelle sezioni seguenti vengono esaminati in modo più approfondito i carichi di lavoro specifici e le interazioni con i gruppi.

## <a name="azure-ad"></a>Azure AD

Azure AD fornisce le funzionalità di gestione delle identità sottostanti in Microsoft 365.

**Caratteristiche principali fornite ai gruppi**

- Appartenenza al gruppo
- Criteri di denominazione
- Criteri di scadenza
- Ospiti
- Limitazione della creazione di gruppi

**È possibile creare un gruppo in Azure AD?**

Sì, i gruppi di Microsoft 365 possono essere creati da Azure AD tramite il portale Web di amministrazione, tramite PowerShell o l'API del grafico.

**Azure AD esiste senza un gruppo?**

Sì, Azure AD esegue un gran numero di servizi che non hanno alcuna relazione con i gruppi di Microsoft 365. Ogni gruppo di Microsoft 365 è rappresentato come un oggetto in Azure AD.

**È possibile che vi siano più istanze di Azure AD per gruppo?**

No, è presente una sola istanza di Azure AD.

**È possibile associare Azure AD a più gruppi?**

Sì, perché Azure AD è la piattaforma sottostante che fornisce il servizio di appartenenza a un gruppo.

**È possibile che l'associazione di Azure AD sia associata a un gruppo?**

No, Azure AD è la piattaforma sottostante in cui sono presenti i gruppi.

**L'eliminazione dell'istanza elimina il gruppo?**

L'eliminazione del gruppo in Azure AD eliminerà i servizi e i contenuti associati a un gruppo rilevanti.

## <a name="teams"></a>Teams

Teams è un'area di lavoro basata su chat che mira a migliorare la collaborazione fornendo un'interfaccia singolare per interagire con una vasta gamma di servizi Microsoft e di terze parti.

Per impostazione predefinita, quando viene creato un team, la cassetta postale e il calendario associati al gruppo Microsoft 365 sono nascosti sia dall'elenco indirizzi globale in Exchange sia da Outlook. Questo può essere sottoposto a override manualmente da un amministratore se l'utente desidera utilizzare sia Outlook che i team nello stesso gruppo di Microsoft 365.

**Caratteristiche principali fornite ai gruppi**

- Conversazioni
- Schede & canali
- Riunioni

**I team possono creare un gruppo?**

Sì, la creazione di un nuovo team creerà un nuovo gruppo di Microsoft 365. È anche possibile creare un team per un gruppo esistente che attualmente non ne ha uno.

**I team esistono senza un gruppo?**

No, non è possibile che un team esista senza un gruppo.

**Possono essere presenti più team per gruppo?**

No, la relazione tra un team e un gruppo è 1:1.

**Un team può essere associato a più gruppi?**

No, il team può essere associato solo a un singolo gruppo.

**È possibile che l'associazione di un team con un gruppo venga modificata?**

No, il team può sempre essere associato al gruppo a cui era originariamente associato.

**L'eliminazione del team deve essere eliminata dal gruppo?**

Sì, l'eliminazione del team in Microsoft teams eliminerà il gruppo, i servizi associati al gruppo e il contenuto.

## <a name="exchange"></a>Exchange

Exchange Online fornisce messaggistica, calendario, contatti e funzionalità associate. Nel contesto di un gruppo, è associata una sola risorsa, invece di un'intera istanza del servizio.

**Caratteristiche principali fornite ai gruppi**

- Cassetta postale e calendario
- Possibilità di inviare tramite posta elettronica tutti i membri del gruppo
- Archiviazione delle conversazioni dei canali di teams per scopi eDiscovery, commenti Planner

**Exchange può creare un gruppo?**

Sì, è possibile creare un gruppo dall'interfaccia di amministrazione di Exchange Online, così come da Outlook. È inoltre possibile convertire le liste di distribuzione di Exchange in gruppi di Microsoft 365.

**Exchange esiste senza un gruppo?**

Sì, Exchange Online offre una serie di servizi, tra cui le cassette postali condivise e i calendari, senza alcuna associazione di gruppo.

**Possono essere presenti più istanze di cassette postali di Exchange o calendari per gruppo?**

No, può trattarsi solo di una singola cassetta postale di Exchange Online e di un calendario per un gruppo.

**Le cassette postali e i calendari di Exchange possono essere associati a più gruppi?**

No, la cassetta postale e il calendario hanno una relazione di 1:1 con il gruppo. È possibile condividere la cassetta postale con altri utenti o gruppi, ma questo non stabilisce alcuna forma di associazione di servizi.

**È possibile che la cassetta postale di Exchange o l'associazione del calendario con un gruppo siano cambiate?**

No, la cassetta postale e il calendario non possono essere cambiati in un gruppo diverso. Tuttavia, il contenuto può essere spostato da una cassetta postale all'altra all'interno di Outlook o tramite uno strumento di terze parti.

**L'eliminazione della cassetta postale Elimina il gruppo?**

Sì, l'eliminazione della cassetta postale in Exchange eliminerà il gruppo, nonché i servizi e i contenuti associati al gruppo.

## <a name="forms"></a>Forms

Moduli fornisce sondaggi e quiz basati sul Web.

**Caratteristiche principali fornite ai gruppi**

- Proprietà dei moduli

**I moduli possono creare un gruppo?**

No, i moduli non possono creare un gruppo.

**I moduli sono presenti senza un gruppo?**

Sì, è possibile creare sondaggi e quiz direttamente nell'account di un utente finale.

**Possono essere presenti più moduli per gruppo?**

Sì, possono essere presenti più moduli associati a un gruppo.

**I moduli possono essere associati a più gruppi?**

No, un modulo può essere associato solo a un singolo gruppo.

**È possibile modificare l'associazione di un modulo con un gruppo?**

No, una volta che un modulo è associato a un gruppo (creato direttamente all'interno o a una proprietà trasferita da un singolo), non può essere spostato in un altro gruppo.

**L'eliminazione del modulo può essere eliminata dal gruppo?**

No, non è possibile eliminare un gruppo dall'interfaccia moduli, solo singoli moduli.

## <a name="onenote"></a>OneNote

OneNote è un'applicazione per notebook digitale. Il blocco appunti di OneNote creato con un gruppo è un file nel sito di SharePoint associato anziché in un servizio connesso a un gruppo.

**Caratteristiche principali fornite ai gruppi**

- Blocco appunti condiviso (archiviato nella raccolta di SharePoint associata a un gruppo)

**OneNote è in grado di creare un gruppo?**

No, l'applicazione OneNote non è in grado di creare un gruppo.

**I blocchi appunti di OneNote esistono senza un gruppo?**

Sì, è possibile creare taccuini direttamente in OneDrive o in altre posizioni condivise.

**Possono essere presenti più blocchi appunti di OneNote per gruppo?**

Sì, un blocco appunti viene creato per impostazione predefinita e altri possono essere aggiunti, tuttavia qualsiasi collegamento a OneNote dai servizi associati al gruppo passerà sempre al blocco appunti predefinito.

**Un blocco appunti di OneNote può essere associato a più gruppi?**

No, il blocco appunti è archiviato nella raccolta siti di SharePoint associata a un gruppo e collegato da diverse interfacce. Tuttavia, può essere condiviso con altri gruppi nello stesso modo in cui può essere condiviso con gli utenti.

**L'associazione del blocco appunti può essere modificata da un gruppo?**

No, il blocco appunti stesso è associato al gruppo e può accedervi direttamente da altri servizi connessi al gruppo, tuttavia il contenuto può essere spostato da un blocco appunti all'altro all'interno dell'applicazione OneNote.

**L'eliminazione del blocco appunti viene eliminata dal gruppo?**

No, tuttavia, se il blocco appunti di OneNote è stato eliminato, potrebbero essere presenti collegamenti interrotti in alcuni dei servizi associati al gruppo.

## <a name="planner"></a>Planner

Planner è un servizio di gestione delle attività di gruppo Lightweight.

**Caratteristiche principali fornite ai gruppi**

- Scheda per la gestione delle attività del gruppo

**Planner è in grado di creare un gruppo?**

Sì, la creazione di un piano creerà un nuovo gruppo.

**Esiste una scheda pianificazione senza un gruppo?**

No, è necessario che un piano sia associato a un gruppo.

**Possono essere presenti più piani per gruppo?**

Sì, possono essere presenti più piani per gruppo.

**Un piano può essere associato a più gruppi?**

No, un piano si basa esclusivamente sull'appartenenza ai gruppi per determinare l'accesso.

**L'associazione di un piano può essere modificata con un gruppo?**

No, tuttavia, la copia di un piano crea un nuovo gruppo.

> [!NOTE]
> Un gruppo creato da qualsiasi altra applicazione non verrà visualizzato automaticamente in Planner per un utente. Per accedere alla scheda iniziale, sarà necessario aprirla da un'altra interfaccia basata su gruppo, ad esempio Outlook.

**L'eliminazione del piano può essere eliminata dal gruppo?**

Sì, eliminando il piano verrà eliminato il gruppo e i servizi associati a un gruppo e il relativo contenuto.

## <a name="power-apps"></a>Power Apps

Power Apps fornisce un'area di disegno per lo sviluppo di app senza codice.

**Caratteristiche principali fornite ai gruppi**

- Le app possono essere condivise con un gruppo per l'esecuzione e la modifica

**Le app di potenza possono creare un gruppo?**

No, Power Apps non è in grado di creare un gruppo di Microsoft 365.

**Le app di alimentazione esistono senza un gruppo?**

Sì, le app possono essere create all'interno di Power Apps e risiedono all'interno dell'account Creators fino alla condivisione o alla pubblicazione.

**Possono essere presenti più app per gruppo?**

Sì, possono essere presenti più app condivise con un gruppo.

**Le app possono essere associate a più gruppi?**

Sì, un'app può essere condivisa con più gruppi.

**È possibile modificare l'associazione di un'app con un gruppo?**

Sì, poiché l'associazione tra le app di alimentazione e un gruppo di Microsoft 365 è solo la condivisione, l'app risiede ancora con il creatore.

> [!IMPORTANT]
> I [gruppi devono essere abilitati alla sicurezza prima che le app possano essere condivise con esse](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**L'eliminazione dell'app elimina il gruppo?**

No, le app non sono connesse a un gruppo diverso da quello condiviso con esse.

## <a name="power-automate"></a>Automatizzare la potenza

Power automatizzate (in precedenza noto come Microsoft Flow) fornisce flussi di lavoro e servizi di automazione.

**Caratteristiche principali fornite ai gruppi**

- I flussi di lavoro possono essere condivisi con un gruppo da eseguire e modificare.

**È possibile automatizzare l'alimentazione per creare un gruppo?**

No, Power automatizzate non è in grado di creare un gruppo di Microsoft 365 nel contesto di essere associato a uno.

È tuttavia possibile creare un flusso che esegua diverse operazioni, ad esempio la creazione di un gruppo di sicurezza di Azure AD o l'aggiornamento dell'appartenenza a un gruppo di Microsoft 365.

**I flussi esistono senza un gruppo?**

Sì, i flussi possono essere creati all'interno del Power automatizzate e risiedono all'interno dell'account Creators fino alla condivisione o alla pubblicazione.

**Possono essere presenti più flussi per gruppo?**

Sì, possono essere presenti più flussi condivisi con un gruppo.

**È possibile associare un flusso a più gruppi?**

Sì, un flusso può essere condiviso con più gruppi.

**È possibile modificare l'associazione di un flusso con un gruppo?**

Sì, poiché l'associazione tra Power automatizzate e un gruppo di Microsoft 365 è solo la condivisione, il flusso risiede ancora con il creatore.

**L'eliminazione di un flusso Elimina il gruppo?**

No, come le app di alimentazione, i flussi non sono connessi al gruppo diverso da quello condiviso con essi.

## <a name="power-bi-classic"></a>Power BI (classica)

Power BI fornisce dashboard e report basati su dati interattivi.

**Caratteristiche principali fornite ai gruppi**

- Report di dati

**Power BI può creare un gruppo?**

Sì, la creazione di un'area di lavoro classica creerà un gruppo di Microsoft 365.

**L'area di lavoro Power BI Classic esiste senza un gruppo?**

No, [un'area di lavoro classica in Power BI deve essere associata a un gruppo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Possono essere presenti più aree di lavoro di Power BI per ogni gruppo?**

No, la relazione tra un'area di lavoro classica e un gruppo è 1:1.

**È possibile associare un'area di lavoro a più gruppi?**

Tecnicamente no, mentre l'area di lavoro classica viene creata con il gruppo, il contenuto può essere condiviso al di fuori del gruppo con gli utenti e i gruppi di sicurezza.

**L'associazione dell'area di lavoro può essere modificata con un gruppo?**

No, l'area di lavoro classica è associata al gruppo, tuttavia il contenuto può essere spostato da un'area di lavoro all'altra all'interno dell'interfaccia di Power BI o esportando i contenuti localmente.

**L'eliminazione dell'area di lavoro elimina il gruppo?**

Sì, eliminando l'area di lavoro in Power BI, verranno eliminati i contenuti e i servizi associati a gruppi e gruppi.

## <a name="power-bi-new"></a>Power BI (nuovo)

Power BI fornisce dashboard e report basati su dati interattivi.

Durante la creazione di una nuova area di lavoro in Power BI non viene creato un gruppo di Microsoft 365, la creazione di un gruppo con qualsiasi altro mezzo crea un nuovo Workspace (non classico) in Power BI.

**Caratteristiche principali fornite ai gruppi**

- Report di dati

**Power BI può creare un gruppo?**

No, non è possibile creare un gruppo di Microsoft 365 dalla nuova interfaccia di Power BI.

**La nuova area di lavoro Power BI esiste senza un gruppo?**

Sì, è possibile che i report e le aree di lavoro vengano creati in Power BI non associati ai gruppi di Microsoft 365.

**Possono essere presenti più aree di lavoro per gruppo?**

Sì, [più aree di lavoro create da Power bi possono essere condivise con un solo gruppo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**È possibile associare un'area di lavoro a più gruppi?**

No, un'area di lavoro creata da Power BI può essere associata a un solo gruppo.

**È possibile modificare l'associazione di un'area di lavoro con un gruppo?**

Sì e no. Un'area di lavoro creata da Power BI può essere associata a un solo gruppo alla volta, ma può cambiare l'associazione in qualsiasi momento. Un'area di lavoro creata in Power BI da un gruppo è associata definitivamente a quel gruppo.

**L'eliminazione dell'area di lavoro elimina il gruppo?**

Sì, eliminare l'area di lavoro in Power BI eliminerà il gruppo e i servizi associati a un gruppo e il contenuto.

## <a name="project-for-the-web"></a>Project per il web

Project per il Web offre la possibilità di creare piani di progetto, diagrammi di Gantt e roadmap.
Caratteristiche principali fornite ai gruppi.

- Piani di progetto

**È possibile Project per il Web creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Project per il Web.

**I progetti esistono senza un gruppo?**

Sì, i progetti possono esistere senza essere associati a un gruppo di Microsoft 365, tuttavia l'assegnazione delle attività richiede l'associazione di gruppo.

**Possono essere presenti più progetti per gruppo?**

Sì, è possibile connettere più progetti in un singolo gruppo.

**Il progetto può essere associato a più gruppi?**

No, un progetto può essere associato solo a un singolo gruppo.

**È possibile modificare l'associazione di un progetto con un gruppo?**

No, una volta stabilita l'associazione con un gruppo, non può essere modificata.

**L'eliminazione del progetto viene eliminata dal gruppo?**

No, l'eliminazione del progetto in Project per il Web non consente di eliminare il gruppo.

## <a name="roadmap"></a>Roadmap

Roadmap fornisce la possibilità di creare roadmap di progetti con Project per il Web e Project online.

**Caratteristiche principali fornite ai gruppi**

- Roadmap del progetto

**Roadmap può creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente dalla roadmap.

**La Guida di orientamento esiste senza un gruppo?**

Sì, le roadmap possono esistere senza essere associate a un gruppo di Microsoft 365, tuttavia la condivisione della roadmap richiede l'associazione di gruppo.

**Possono esserci più roadmap per gruppo?**

Sì, è possibile connettere più roadmap a un singolo gruppo.

**È possibile associare una roadmap a più gruppi?**

No, una guida di orientamento può essere associata solo a un singolo gruppo.

**L'associazione di una roadmap può essere modificata con un gruppo?**

No, una volta stabilita l'associazione con un gruppo, non può essere modificata.

**L'eliminazione della roadmap Elimina il gruppo?**

No, eliminando la roadmap non verrà eliminato il gruppo.

## <a name="sharepoint"></a>SharePoint

SharePoint è una piattaforma di gestione del contenuto basata sul Web che fornisce tra le altre cose servizi di archiviazione per diversi servizi di Microsoft 365.

**Caratteristiche principali fornite ai gruppi**

- Raccolta documenti
- Raccolta per l'archiviazione del blocco appunti di OneNote
- Archiviazione dei file wiki di Teams

**SharePoint può creare un gruppo?**

Sì, la creazione di un sito del team in SharePoint creerà un gruppo di Microsoft 365 per impostazione predefinita. È anche possibile creare un gruppo e, facoltativamente, un team per un sito esistente.

**I siti di SharePoint esistono senza un gruppo?**

Sì, SharePoint offre numerosi servizi e siti non associati a un gruppo, ad esempio i siti di comunicazione e Hub. 

**Possono essere presenti più siti per gruppo?**

No, può essere presente solo un singolo sito per gruppo. I canali privati nei team utilizzano siti aggiuntivi che non sono connessi al gruppo.

**I siti possono essere associati a più gruppi?**

Tecnicamente no, ma durante la creazione di un sito con un gruppo, il contenuto può essere condiviso con altri gruppi.

**È possibile modificare l'associazione di un sito con un gruppo?**

No, il sito stesso è associato al gruppo, tuttavia il contenuto può essere spostato da un sito a un altro all'interno dell'interfaccia di SharePoint, esportando il contenuto localmente o utilizzando uno strumento di terze parti.

**L'eliminazione del sito Elimina il gruppo?**

Sì, l'eliminazione del sito in SharePoint eliminerà i servizi e i contenuti associati a gruppi e gruppi.

## <a name="stream"></a>Stream

Microsoft Stream è una piattaforma di hosting e condivisione di video.

**Caratteristiche principali fornite ai gruppi**

- Archiviazione video
- Registrazione riunione di Teams
- Canali video

**Stream può creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Stream.

**Il flusso esiste senza un gruppo?**

Sì, i canali video e i video possono esistere in Stream senza essere associati a un gruppo.

**Possono essere presenti più video e canali per gruppo?**

Sì, possono essere presenti più video e canali in ogni gruppo.

**Un video o un canale può essere associato a più gruppi?**

Sì, mentre un video o un canale viene creato con un gruppo, può essere condiviso con altri gruppi.

**La sua associazione con un gruppo può cambiare?**

Sì e no; i video in streaming sono di proprietà dell'Uploader o del registratore di riunioni originale e pertanto possono essere associati a qualsiasi gruppo, ma i canali video possono essere associati solo al gruppo in cui sono stati originariamente creati.

**L'eliminazione di video o canali Elimina il gruppo?**

No, l'eliminazione di video o canali non comporta l'eliminazione del gruppo. Tuttavia, l'eliminazione del gruppo stesso in Stream eliminerà i servizi e i contenuti associati a un gruppo, ad eccezione dei video effettivi.

## <a name="yammer"></a>Yammer

Yammer è una piattaforma sociale aziendale progettata per favorire l'impegno della community all'interno e tra organizzazioni.

La creazione di una community (in precedenza nota come "gruppo") in Yammer crea una cassetta postale, ma al momento non viene utilizzata.

Un gruppo di Microsoft 365 associato a Yammer non può essere utilizzato con un team di Microsoft teams.

**Caratteristiche principali fornite ai gruppi**

- Area di conversazione

**È possibile Yammer creare un gruppo di Microsoft 365?**

Sì, la creazione di un nuovo gruppo in Yammer creerà un nuovo gruppo di Microsoft 365, se le piattaforme sono connesse e l'utente ha la possibilità di creare un gruppo.

Non è possibile creare un gruppo di Yammer con un gruppo di Microsoft 365 associato in nessuna interfaccia o servizio diverso da Yammer stesso.

**Esiste un gruppo di Yammer senza un gruppo di Microsoft 365?**

Sì, è possibile creare un gruppo di Yammer senza un gruppo di Microsoft 365.

Se la piattaforma Yammer non è connessa ai gruppi di Microsoft 365 o gli utenti non hanno la possibilità di creare un gruppo di Microsoft 365, i gruppi di Yammer vengono creati senza un'associazione di gruppo di Microsoft 365.

**Possono essere presenti più gruppi di Yammer per gruppo di Microsoft 365?**

No, la relazione tra un gruppo di Yammer e un gruppo di Microsoft 365 è 1:1.

**Un gruppo di Yammer può essere associato a più gruppi di Microsoft 365?**

No, il gruppo Yammer può essere associato solo a un singolo gruppo di Microsoft 365. È possibile che i post vengano condivisi con o spostati in altri gruppi di Yammer.

**È possibile che l'associazione di un gruppo di Yammer con un gruppo di Microsoft 365 venga modificata?**

No, il gruppo Yammer può essere sempre associato al gruppo Microsoft 365 a cui è stato associato originariamente.

**Eliminazione del gruppo Yammer eliminare il gruppo Microsoft 365?**

Sì, l'eliminazione del gruppo in Yammer eliminerà i contenuti e i servizi associati a un gruppo e il relativo contenuto.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance di collaborazione](collaboration-governance-first.md)

