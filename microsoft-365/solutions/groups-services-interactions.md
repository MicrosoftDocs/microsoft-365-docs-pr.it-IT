---
title: Raggruppa le interazioni dei servizi
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
recommendations: false
description: Raggruppa le interazioni dei servizi
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539204"
---
# <a name="groups-services-interactions"></a>Raggruppa le interazioni dei servizi

Microsoft 365 I gruppi forniscono un'infrastruttura comune per una serie di servizi e carichi di lavoro all'interno della piattaforma Microsoft 365 per offrire un'esperienza connessa per gli utenti finali. Di base, esiste un Microsoft 365 di lavoro per fornire:

- Un modo per gestire l'appartenenza (Azure AD)
- Un luogo per la messaggistica e le conversazioni (Exchange cassetta postale, Microsoft Teams, Yammer)
- Posizione in cui archiviare i file (SharePoint)
- Calendario per la pianificazione (Exchange)
- Blocco appunti per l'acquisizione di note (OneNote)

Al momento della creazione del gruppo, viene eseguito anche il provisioning di una serie di altre risorse, ma non sono visibili finché non si accede per la prima volta dal servizio:

- Una bacheca per la gestione delle attività di gruppo (Planner)
- Area di lavoro per i report (Power BI)
- Un'area per i video condivisi (Microsoft Stream)
- Area per moduli condivisi (moduli)

In Microsoft 365, altri servizi sono in grado di interagire con Microsoft 365 per offrire funzionalità e funzionalità aggiuntive ai membri del gruppo.
Di seguito sono riportati alcuni esempi:

- Power Apps per le app
- Power Automate per i flussi di lavoro
- Project sul Web e Roadmap per la gestione dei progetti basata su cascata
- Teams per le conversazioni basate sul canale
- Yammer per le community di interesse

## <a name="user-interactions-with-groups"></a>Interazioni degli utenti con i gruppi

Microsoft 365 I gruppi possono essere creati e gestiti da un'ampia gamma di interfacce, sia da amministratori che da utenti finali. 

### <a name="administrative-experiences"></a>Esperienze amministrative

Gli amministratori possono creare e gestire gruppi di Microsoft 365 da diverse interfacce di amministrazione del carico di lavoro, interfacce da riga di comando che supportano gli script, nonché app personalizzate che interagiscono con l'API di Graph. L'unica eccezione è Yammer gruppi, che devono essere creati dall'interno dell'Yammer Web.

**Impostazioni correlate**

Tra le varie interfacce amministrative in grado di gestire le impostazioni di gruppo esistono diverse sovrapposizioni di cui è necessario tenere conto.

**Interfaccia di amministrazione di Microsoft 365**

Nell'Microsoft 365 di amministrazione, l'accesso guest ai gruppi è abilitato per impostazione predefinita, così come la possibilità di consentire ai proprietari di aggiungere utenti guest. Non sono disponibili altri controlli a livello di organizzazione per i gruppi di questa interfaccia di amministrazione.

**Interfaccia di amministrazione di Azure AD**

L'interfaccia di amministrazione di Azure AD offre controlli che consentono agli utenti di creare gruppi o assegnare proprietari nei portali di Azure, nonché le impostazioni dei criteri di scadenza e denominazione.

L'interfaccia di amministrazione offre anche una serie di misure di controllo degli inviti guest che vanno oltre quella dell'interfaccia di amministrazione di Microsoft 365, ad esempio la possibilità di limitare se i non proprietari possono anche invitare utenti guest

**SharePoint**

SharePoint vengono creati con i gruppi di sicurezza Proprietario, Membro e Visitatore, con i primi due che corrispondono alle rispettive controparti Microsoft 365 gruppo. Sebbene l'appartenenza SharePoint siti online sia in genere gestita dal gruppo di Microsoft 365 associato, non è una relazione bidirezionale. Qualsiasi modifica apportata all'appartenenza a livello di gruppo di Microsoft 365 viene riflessa in SharePoint, tuttavia se l'appartenenza viene modificata nel gruppo SharePoint, questa non viene riflessa nel gruppo di Microsoft 365.

### <a name="user-experiences"></a>Esperienze utente

Gli utenti finali possono creare gruppi da diversi servizi all'interno di Microsoft 365 e in altri possono condividere solo con un gruppo.

I servizi seguenti consentono la creazione di gruppi da parte degli utenti finali:
                         
Outlook Planner Project per il flusso di SharePoint Web Microsoft Teams Yammer

**Limitazione della creazione di gruppi**

Un approccio comune per controllare l'espansione dei team consiste nel limitare gli utenti che possono crearli. Questa operazione può essere eseguita solo limitando la creazione di gruppi. Questa operazione influisce sulla possibilità di creare gruppi da altri servizi in cui potrebbe essere necessario per l'utente finale. Microsoft 365 I gruppi non supportano la possibilità di limitare la creazione di gruppi da alcune app o servizi consentendo al tempo stesso di farlo da altri.

L'esperienza delle restrizioni per la creazione di gruppi varia a seconda delle app e dei servizi:


|App o servizio|Funzionalità|
|:-------------|:---------|
|Outlook|**L'opzione** Nuovo gruppo viene rimossa dal menu Nuovo nella pagina utenti|
|Planner|**Il nuovo piano** spiega che la creazione del gruppo è stata disattivata e offre di aggiungere il piano a un gruppo esistente|
|Project per il Web e roadmap|**Il** menu Crea gruppo spiega che la creazione del gruppo è limitata e suggerisce di usare un gruppo esistente.|
|SharePoint|È comunque possibile creare un sito del team non connesso a un gruppo.|
|Stream|**L'opzione** Gruppo non viene visualizzata nel **menu Crea.**|
|Teams|L'utente non può creare un team con un nuovo gruppo, ma può comunque creare un team che utilizza un gruppo esistente.<br><br>**Il pulsante Crea team** viene sostituito con **Crea team da un gruppo.**|
|Yammer|**L'opzione Crea** un gruppo viene rimossa dalla struttura di spostamento principale gruppi/community.|

## <a name="services-interactions-with-groups"></a>Interazioni dei servizi con i gruppi

Vedi il poster Gruppi in Microsoft 365 per informazioni sui diversi tipi di gruppi, su come vengono creati e gestiti e su alcuni consigli sulla governance.

[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

Nella tabella seguente viene fornita una panoramica delle interazioni Microsoft 365 gruppi con vari servizi:

|Prodotto|Funzionalità|Il servizio<br>esiste senza un gruppo?|Può il servizio<br>creare un gruppo?|L'eliminazione del file<br>eliminare il gruppo?|
|:---|:---|:---|:---|:---|
|Azure AD|Appartenenza, Controlli gruppo, Guest|Sì|Sì|Sì|
|Exchange|Calendario, cassetta postale|Sì|Sì|Sì|
|Moduli|Modulo|Sì|No|No|
|OneNote|Blocco appunti|Sì|No|No|
|Planner|Bacheca attività|No|Sì|Sì|
|Power Apps app|App|Sì|No|No|
|Power Automate|Flusso di lavoro|Sì|No|No|
|Power BI (classico)|Workspace|No|Sì|Sì|
|Power BI (nuovo)|Workspace|Sì|No|Sì|
|Project per il Web|Project piano|Sì|Sì|No|
|Roadmap|Roadmap|Sì|Sì|No|
|SharePoint|Sito|Sì|Sì|Sì|
|Stream|Canale, video|Sì|Sì|Sì|
|Teams|Teams|No|Sì|Sì|
|Yammer|Gruppo|Sì|Sì|Sì|

Anche se la tabella precedente fornisce una panoramica generale delle interazioni di gruppo con i servizi Microsoft 365, esistono diverse sfumature e complessità da comprendere. Le sezioni seguenti illustrano in modo più approfondito i carichi di lavoro specifici e le relative interazioni con i gruppi.

## <a name="azure-ad"></a>Azure AD

Azure AD offre le funzionalità di gestione delle identità sottostanti Microsoft 365.

**Funzionalità principali fornite ai gruppi**

- Appartenenza al gruppo
- Criterio di denominazione
- Criteri di scadenza
- Guest
- Restrizione della creazione di gruppi

**Azure AD può creare un gruppo?**

Sì, Microsoft 365 gruppi possono essere creati da Azure AD tramite il portale Web di amministrazione, tramite PowerShell o Graph API.

**Azure AD esiste senza un gruppo?**

Sì, Azure AD esegue un gran numero di servizi che non hanno alcuna relazione con Microsoft 365 gruppi. Ogni Microsoft 365 gruppo è rappresentato come oggetto in Azure AD.

**Possono essere presenti più istanze di Azure AD per gruppo?**

No, esiste una sola istanza di Azure AD.

**Azure AD può essere associato a più gruppi?**

Sì, perché Azure AD è la piattaforma sottostante che fornisce il servizio di appartenenza ai gruppi.

**L'associazione di Azure AD a un gruppo può cambiare?**

No, Azure AD è la piattaforma sottostante in cui sono presenti gruppi.

**L'eliminazione dell'istanza elimina il gruppo?**

L'eliminazione del gruppo in Azure AD eliminerà i servizi e il contenuto associati al gruppo pertinenti.

## <a name="teams"></a>Teams

Teams è un'area di lavoro basata su chat finalizzata a migliorare la collaborazione fornendo un'interfaccia singolare per interagire con un'ampia gamma di servizi Microsoft e di terze parti.

Per impostazione predefinita, quando viene creato un team, la cassetta postale e il calendario associati al gruppo di Microsoft 365 vengono nascosti sia dall'elenco indirizzi globale in Exchange che da Outlook. Questo può essere sostituito manualmente da un amministratore se l'utente desidera utilizzare sia Outlook che Teams nello stesso gruppo Microsoft 365 gruppo.

**Funzionalità principali fornite ai gruppi**

- Conversazioni
- Canali & schede
- Riunioni

**È Teams creare un gruppo?**

Sì, la creazione di un nuovo team creerà un nuovo Microsoft 365 gruppo. È inoltre possibile creare un team per un gruppo esistente che attualmente non ne dispone.

**I team esistono senza un gruppo?**

No, non è possibile che un team esista senza un gruppo.

**Possono essere presenti più team per gruppo?**

No, la relazione tra un team e un gruppo è 1:1.

**Un team può essere associato a più gruppi?**

No, il team stesso può essere associato solo a un singolo gruppo.

**L'associazione di un team a un gruppo può cambiare?**

No, il team può essere associato solo al gruppo a cui è stato originariamente associato.

**L'eliminazione del team elimina il gruppo?**

Sì, l'eliminazione del team in Microsoft Teams eliminerà il gruppo, i servizi associati al gruppo e il contenuto.

## <a name="exchange"></a>Exchange

Exchange Online fornisce funzionalità di messaggistica, calendario, contatto e associate. Nel contesto di un gruppo, viene associata una sola risorsa, anziché un'intera istanza del servizio.

**Funzionalità principali fornite ai gruppi**

- Cassetta postale e calendario
- Possibilità di inviare un messaggio di posta elettronica a tutti i membri del gruppo
- Archiviazione conversazioni Teams canale per eDiscovery, commenti di Planner

**È Exchange creare un gruppo?**

Sì, è possibile creare un gruppo dall'Exchange Online di amministrazione e da Outlook. È inoltre possibile convertire Exchange di distribuzione in Microsoft 365 gruppi.

**Esiste Exchange senza un gruppo?**

Sì, Exchange Online fornisce una serie di servizi, incluse cassette postali e calendari condivisi, senza alcuna associazione di gruppo.

**Possono essere presenti più istanze di Exchange cassette postali o calendari per gruppo?**

No, può essere presente solo una singola cassetta Exchange Online e un calendario per un gruppo.

**È Exchange le cassette postali e i calendari possono essere associati a più gruppi?**

No, la cassetta postale e il calendario hanno una relazione 1:1 con il gruppo. È possibile condividere la cassetta postale con altri utenti o gruppi, ma ciò non stabilisce alcuna forma di associazione del servizio.

**L'Exchange cassetta postale o l'associazione del calendario a un gruppo può cambiare?**

No, la cassetta postale e il calendario non possono essere modificati in un gruppo diverso. Tuttavia, il contenuto può essere spostato da una cassetta postale a un'altra all'interno Outlook o utilizzando uno strumento di terze parti.

**L'eliminazione della cassetta postale elimina il gruppo?**

Sì, l'eliminazione della cassetta postale in Exchange eliminerà il gruppo, nonché i servizi e il contenuto associati al gruppo.

## <a name="forms"></a>Moduli

I moduli forniscono sondaggi e quiz basati sul Web.

**Funzionalità chiave fornite ai gruppi**

- Proprietà dei moduli

**I moduli possono creare un gruppo?**

No, i moduli non possono creare un gruppo.

**I moduli esistono senza un gruppo?**

Sì, i sondaggi e i quiz possono essere creati direttamente nell'account di un utente finale.

**Possono essere presenti più moduli per gruppo?**

Sì, a un gruppo possono essere associati più moduli.

**I moduli possono essere associati a più gruppi?**

No, un modulo può essere associato solo a un singolo gruppo.

**L'associazione di un modulo a un gruppo può cambiare?**

No, una volta che un modulo è associato a un gruppo (creato direttamente all'interno o trasferito dalla proprietà da un singolo utente) non può essere spostato in un altro gruppo.

**L'eliminazione del modulo elimina il gruppo?**

No, non è possibile eliminare un gruppo dall'interfaccia Forms, ma solo singoli moduli.

## <a name="onenote"></a>OneNote

OneNote è un'applicazione di blocco appunti digitale. Il OneNote blocco appunti creato con un gruppo è un file nel sito SharePoint e non un servizio connesso a un gruppo.

**Funzionalità chiave fornite ai gruppi**

- Blocco appunti condiviso (archiviato nella raccolta SharePoint gruppo)

**È OneNote creare un gruppo?**

No, l'OneNote non può creare un gruppo.

**Esistono OneNote blocchi appunti senza un gruppo?**

Sì, i blocchi appunti possono essere creati direttamente in OneDrive o in altri percorsi condivisi.

**Possono essere presenti più OneNote blocchi appunti per gruppo?**

Sì, un blocco appunti viene creato per impostazione predefinita e altri possono essere aggiunti, tuttavia qualsiasi collegamento a un OneNote da servizi associati al gruppo verrà sempre visualizzato nel blocco appunti predefinito.

**È possibile associare OneNote blocco appunti a più gruppi?**

No, il blocco appunti viene archiviato nella raccolta siti SharePoint associata al gruppo e collegato da diverse interfacce. Tuttavia, può essere condiviso con altri gruppi nello stesso modo in cui può essere condiviso con gli utenti.

**L'associazione del blocco appunti a un gruppo può cambiare?**

No, il blocco appunti stesso è associato al gruppo ed è possibile accedervi direttamente da altri servizi connessi al gruppo, tuttavia il contenuto può essere spostato da un blocco appunti a un altro all'interno dell'applicazione OneNote.

**L'eliminazione del blocco appunti elimina il gruppo?**

No, tuttavia, se OneNote blocco appunti viene eliminato, potrebbero essere presenti collegamenti interrotti in alcuni dei servizi associati al gruppo.

## <a name="planner"></a>Planner

Planner è un servizio di gestione delle attività di gruppo leggero.

**Funzionalità chiave fornite ai gruppi**

- Scheda per la gestione delle attività di gruppo

**Planner può creare un gruppo?**

Sì, la creazione di un piano creerà un nuovo gruppo.

**Esiste una bacheca di Planner senza un gruppo?**

No, un piano deve essere associato a un gruppo.

**Possono essere presenti più piani per gruppo?**

Sì, possono essere presenti più piani per gruppo.

**È possibile associare un piano a più gruppi?**

No, un piano si basa esclusivamente sull'appartenenza al gruppo per determinare l'accesso.

**L'associazione di un piano a un gruppo può cambiare?**

No, tuttavia, la copia di un piano crea un nuovo gruppo.

> [!NOTE]
> Un gruppo creato da qualsiasi altra applicazione non verrà visualizzato automaticamente in Planner per un utente. Per accedere alla scheda inizialmente, dovrà aprirla da un'altra interfaccia basata su gruppo, ad esempio Outlook.

**L'eliminazione del piano elimina il gruppo?**

Sì, l'eliminazione del piano eliminerà il contenuto e i servizi associati al gruppo.

## <a name="power-apps"></a>Power Apps

Power Apps fornisce un canvas per lo sviluppo di app senza codice.

**Funzionalità principali fornite ai gruppi**

- Le app possono essere condivise con un gruppo da eseguire e modificare

**È Power Apps creare un gruppo?**

No, Power Apps non è possibile creare un Microsoft 365 gruppo.

**Esiste Power Apps senza un gruppo?**

Sì, le app possono essere create all'interno Power Apps e risiedono nell'account creators fino a quando non vengono condivise o pubblicate.

**Possono essere presenti più app per gruppo?**

Sì, possono essere presenti più app condivise con un gruppo.

**Le app possono essere associate a più gruppi?**

Sì, un'app può essere condivisa con più gruppi.

**L'associazione di un'app a un gruppo può cambiare?**

Sì, poiché l'associazione tra Power Apps e un gruppo Microsoft 365 è solo la condivisione: l'app risiede ancora con il creatore.

> [!IMPORTANT]
> [I gruppi devono essere abilitati per la sicurezza prima che le app possano essere condivise con essi.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**L'eliminazione dell'app elimina il gruppo?**

No, le app non sono connesse al gruppo oltre a essere condivise con loro.

## <a name="power-automate"></a>Power Automate

Power Automate (in precedenza noto come Microsoft Flow) fornisce flussi di lavoro e servizi di automazione.

**Funzionalità chiave fornite ai gruppi**

- I flussi di lavoro possono essere condivisi con un gruppo da eseguire e modificare.

**È Power Automate creare un gruppo?**

No, Power Automate non è possibile creare Microsoft 365 gruppo nel contesto di essere associato a un gruppo.

È tuttavia possibile creare un flusso che esegua diverse operazioni, ad esempio la creazione di un gruppo di sicurezza di Azure AD o l'aggiornamento dell'appartenenza a Microsoft 365 gruppo.

**I flussi esistono senza un gruppo?**

Sì, i flussi possono essere creati all'interno Power Automate e risiedono all'interno dell'account creators fino a quando non vengono condivisi o pubblicati.

**Possono essere presenti più flussi per gruppo?**

Sì, possono essere presenti più flussi condivisi con un gruppo.

**Un flusso può essere associato a più gruppi?**

Sì, un flusso può essere condiviso con più gruppi.

**L'associazione di un flusso a un gruppo può cambiare?**

Sì, poiché l'associazione tra Power Automate e un gruppo Microsoft 365 è solo in condivisione: il flusso risiede ancora con il creatore.

**L'eliminazione di un flusso elimina il gruppo?**

No, come Power Apps, i flussi non sono connessi al gruppo se non condivisi con loro.

## <a name="power-bi-classic"></a>Power BI (classico)

Power BI fornisce dashboard e report interattivi guidati da dati.

**Funzionalità chiave fornite ai gruppi**

- Creazione di report sui dati

**È Power BI creare un gruppo?**

Sì, la creazione di un'area di lavoro classica creerà Microsoft 365 gruppo.

**Esiste Power BI'area di lavoro classica senza un gruppo?**

No, [un'area di lavoro classica Power BI deve essere associata a un gruppo.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)

**Possono essere presenti più Power BI di lavoro per gruppo?**

No, la relazione tra un'area di lavoro classica e un gruppo è 1:1.

**Un'area di lavoro può essere associata a più gruppi?**

Tecnicamente no, mentre l'area di lavoro classica viene creata con il gruppo, il contenuto può essere condiviso all'esterno del gruppo con utenti e gruppi di sicurezza.

**L'associazione dell'area di lavoro a un gruppo può cambiare?**

No, l'area di lavoro classica è associata al gruppo, ma il contenuto può essere spostato da un'area di lavoro a un'altra nell'interfaccia Power BI o esportando il contenuto in locale.

**L'eliminazione dell'area di lavoro elimina il gruppo?**

Sì, l'eliminazione dell'area di lavoro in Power BI eliminerà i servizi e il contenuto associati a gruppi e gruppi.

## <a name="power-bi-new"></a>Power BI (nuovo)

Power BI fornisce dashboard e report interattivi guidati da dati.

Durante la creazione di una nuova area di lavoro in Power BI non viene creato un gruppo di Microsoft 365, la creazione di un gruppo con altri mezzi crea una nuova area di lavoro (non classica) in Power BI.

**Funzionalità chiave fornite ai gruppi**

- Creazione di report sui dati

**È Power BI creare un gruppo?**

No, non è possibile creare un gruppo Microsoft 365 dalla nuova interfaccia Power BI.

**La nuova area Power BI esistente senza un gruppo?**

Sì, è possibile creare report e aree di lavoro in Power BI non associati a Microsoft 365 gruppi.

**Possono essere presenti più aree di lavoro per gruppo?**

Sì, [più aree di lavoro create Power BI possono essere condivise con un singolo gruppo.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)

**Un'area di lavoro può essere associata a più gruppi?**

No, un'area di lavoro creata Power BI può essere associata solo a un singolo gruppo.

**L'associazione di un'area di lavoro a un gruppo può cambiare?**

Sì e no. Un'area di Power BI può essere associata a un solo gruppo alla volta, ma può modificare l'associazione in qualsiasi momento. Un'area di lavoro creata Power BI da un gruppo viene associata in modo permanente a tale gruppo.

**L'eliminazione dell'area di lavoro elimina il gruppo?**

Sì, l'eliminazione dell'area di lavoro Power BI il contenuto e i servizi associati al gruppo.

## <a name="project-for-the-web"></a>Project per il Web

Project web offre la possibilità di creare piani di progetto, diagrammi di Gantt e roadmap.
Funzionalità principali fornite ai gruppi.

- Project piani

**È Project per il Web creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Project per il Web.

**I progetti esistono senza un gruppo?**

Sì, i progetti possono esistere senza essere associati a un gruppo Microsoft 365, tuttavia l'assegnazione delle attività richiede l'associazione di gruppo.

**Possono essere presenti più progetti per gruppo?**

Sì, è possibile connettere più progetti in un singolo gruppo.

**Il progetto può essere associato a più gruppi?**

No, un progetto può essere associato solo a un singolo gruppo.

**L'associazione di un progetto a un gruppo può cambiare?**

No, una volta stabilita l'associazione a un gruppo, non può essere modificato.

**L'eliminazione del progetto elimina il gruppo?**

No, l'eliminazione del progetto Project per il Web non eliminerà il gruppo.

## <a name="roadmap"></a>Roadmap

Roadmap offre la possibilità di creare roadmap di progetto con Project web e Project Online.

**Funzionalità principali fornite ai gruppi**

- Project roadmap

**La roadmap può creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente dalla roadmap.

**La roadmap esiste senza un gruppo?**

Sì, le roadmap possono esistere senza essere associate a un gruppo Microsoft 365, tuttavia la condivisione della roadmap richiede l'associazione di gruppo.

**Possono essere presenti più roadmap per gruppo?**

Sì, è possibile connettere più roadmap a un singolo gruppo.

**È possibile associare una roadmap a più gruppi?**

No, una roadmap può essere associata solo a un singolo gruppo.

**L'associazione di una roadmap a un gruppo può cambiare?**

No, una volta stabilita l'associazione a un gruppo, non può essere modificato.

**L'eliminazione della roadmap elimina il gruppo?**

No, l'eliminazione della roadmap non eliminerà il gruppo.

## <a name="sharepoint"></a>SharePoint

SharePoint è una piattaforma di gestione dei contenuti basata sul Web che fornisce, tra le altre cose, servizi di archiviazione per una serie di Microsoft 365 servizi.

**Funzionalità principali fornite ai gruppi**

- Raccolta documenti
- Raccolta per l'archiviazione di OneNote blocco appunti
- Archiviazione di Teams wiki

**È SharePoint creare un gruppo?**

Sì, la creazione di un sito del team SharePoint un gruppo Microsoft 365 per impostazione predefinita. È inoltre possibile creare un gruppo e, facoltativamente, un team per un sito esistente.

**Esistono SharePoint siti senza un gruppo?**

Sì, SharePoint offre una serie di servizi e siti non associati al gruppo, ad esempio siti hub e di comunicazione. 

**Possono essere presenti più siti per gruppo?**

No, può essere presente un solo sito per gruppo. I canali privati Teams siti aggiuntivi non connessi al gruppo.

**I siti possono essere associati a più gruppi?**

Tecnicamente no, ma mentre un sito viene creato con un gruppo, il contenuto può essere condiviso con altri gruppi.

**L'associazione di un sito a un gruppo può cambiare?**

No, il sito stesso è associato al gruppo, tuttavia il contenuto può essere spostato da un sito a un altro nell'interfaccia di SharePoint, esportando il contenuto in locale o utilizzando uno strumento di terze parti.

**L'eliminazione del sito elimina il gruppo?**

Sì, l'eliminazione del sito in SharePoint eliminerà i servizi e il contenuto associati a gruppi e gruppi.

## <a name="stream"></a>Stream

Microsoft Stream è una piattaforma di hosting e condivisione di video.

**Funzionalità principali fornite ai gruppi**

- Archiviazione video
- Teams riunione
- Canali video

**Stream può creare un gruppo?**

Sì, è possibile creare un nuovo gruppo di Microsoft 365 direttamente da Stream.

**Stream esiste senza un gruppo?**

Sì, i canali video e i video possono esistere in Stream senza essere associati a un gruppo.

**Possono essere presenti più video e canali per gruppo?**

Sì, possono essere presenti più video e canali in ogni gruppo.

**È possibile associare un video o un canale a più gruppi?**

Sì, mentre un video o un canale viene creato con un gruppo, può essere condiviso con altri gruppi.

**L'associazione con un gruppo può cambiare?**

Sì e no; I video in Stream sono di proprietà del programma di caricamento o del registratore di riunioni originale e quindi possono essere associati a qualsiasi gruppo, tuttavia i canali video possono essere associati solo al gruppo in cui sono stati originariamente creati.

**L'eliminazione di video o canali elimina il gruppo?**

No, l'eliminazione di video o canali non elimina il gruppo. Tuttavia, l'eliminazione del gruppo stesso in Stream eliminerà i servizi e il contenuto associati al gruppo, ad eccezione dei video effettivi.

## <a name="yammer"></a>Yammer

Yammer è una piattaforma social aziendale progettata per favorire il coinvolgimento della community all'interno e tra organizzazioni.

La creazione di una community (in precedenza nota come "gruppo") Yammer una cassetta postale, ma attualmente non viene utilizzata.

Un Microsoft 365 di lavoro associato a Yammer non può essere utilizzato con un team in Microsoft Teams.

**Funzionalità principali fornite ai gruppi**

- Area conversazione

**È Yammer creare un Microsoft 365 gruppo?**

Sì, la creazione di un nuovo gruppo in Yammer creerà un nuovo gruppo di Microsoft 365, se le piattaforme sono connesse e l'utente ha la possibilità di creare un gruppo.

Non è Yammer un gruppo di Microsoft 365 associato in un'interfaccia o in un servizio diverso da Yammer stesso.

**Esiste un Yammer esistente senza un Microsoft 365 esistente?**

Sì, è possibile creare un gruppo Yammer senza un Microsoft 365 gruppo.

Se la piattaforma Yammer non è connessa a gruppi di Microsoft 365 o gli utenti non hanno la possibilità di creare un gruppo di Microsoft 365, i gruppi di Yammer vengono creati senza un'associazione Microsoft 365 gruppo.

**Possono essere presenti più Yammer gruppi per Microsoft 365 gruppo?**

No, la relazione tra un Yammer e un gruppo Microsoft 365 è 1:1.

**Un gruppo Yammer può essere associato a più Microsoft 365 gruppi?**

No, il Yammer può essere associato solo a un singolo Microsoft 365 gruppo. È possibile che i post siano condivisi o spostati in altri Yammer gruppi.

**Un gruppo Yammer può cambiare l'associazione di un Microsoft 365 gruppo?**

No, il Yammer può essere associato solo al gruppo Microsoft 365 cui è stato originariamente associato.

**L'eliminazione Yammer gruppo di archiviazione elimina il Microsoft 365 gruppo?**

Sì, l'eliminazione del gruppo in Yammer eliminerà i servizi e i contenuti associati al gruppo e al gruppo Microsoft correlati.

## <a name="related-topics"></a>Argomenti correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)