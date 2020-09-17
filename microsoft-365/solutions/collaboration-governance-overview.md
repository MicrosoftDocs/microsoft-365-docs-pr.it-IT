---
title: Panoramica della governance della collaborazione in Microsoft 365
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informazioni su come gestire le funzionalità correlate nei gruppi di Microsoft 365, teams, SharePoint e Yammer.
ms.openlocfilehash: b217dc089eb150d01eed9cd720b2caa290d54bf1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950713"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Panoramica della governance della collaborazione in Microsoft 365

Microsoft 365 è dotato di un insieme completo di strumenti per implementare tutte le funzionalità di governance che l'organizzazione potrebbe richiedere. In questo articolo vengono illustrati i professionisti IT per porre le domande giuste per determinare i propri requisiti per la governance e come soddisfarli in base al profilo dell'organizzazione.

## <a name="what-are-microsoft-365-groups"></a>Che cosa sono i gruppi di Microsoft 365?

Sappiamo che oggi le organizzazioni utilizzano un set di strumenti diversificato. C'è il team di sviluppatori che utilizza Team Chat, i dirigenti che inviano messaggi di posta elettronica e l'intera organizzazione che si connette a Enterprise Social. Gli strumenti di collaborazione multipli sono in uso perché ogni gruppo è univoco e ha le proprie esigenze funzionali e lo stile di lavoro. Alcuni utilizzeranno solo messaggi di posta elettronica, mentre altri vivranno principalmente in chat. 

Se gli utenti avvertono che gli strumenti forniti da IT non soddisfano le proprie esigenze, è probabile che scaricheranno l'app consumer preferita che supporta gli scenari. Sebbene questo processo consenta agli utenti di iniziare rapidamente, comporta una frustrante esperienza utente all'interno dell'organizzazione con più accessi, difficoltà di condivisione e nessun singolo luogo per la visualizzazione del contenuto. Questo concetto è denominato "Shadow IT" e rappresenta un rischio significativo per le organizzazioni. Riduce la possibilità di gestire in modo uniforme l'accesso degli utenti, garantire la sicurezza e le esigenze di conformità dei servizi.

Servizi quali Microsoft 365 groups, teams e Yammer Empower Users e riduce il rischio di Shadow IT fornendo gli strumenti necessari per collaborare. I gruppi di Microsoft 365 consentono di scegliere un insieme di persone con cui si desidera collaborare e di configurare facilmente una raccolta di risorse per la condivisione di tali utenti. L'aggiunta di membri al gruppo concede automaticamente le autorizzazioni necessarie a tutte le risorse fornite dal gruppo. Entrambe le squadre e Yammer utilizzano i gruppi di Microsoft 365 per gestire la propria appartenenza.

![Diagramma che mostra i gruppi di Microsoft 365 e i servizi correlati](../media/microsoft-365-groups-hub-spoke.png)

I gruppi Microsoft 365 includono una vasta gamma di controlli di governance, tra cui un criterio di scadenza, convenzioni di denominazione e un criterio di parole bloccate, che consentono di gestire i gruppi nell'organizzazione. Per informazioni dettagliate, vedere [pianificare l'organizzazione e la governance del ciclo di vita per i gruppi microsoft 365 e Microsoft Team](plan-organization-lifecycle-governance.md)

## <a name="technical-architecture"></a>Architettura tecnica

Sono disponibili tre metodi di comunicazione principali supportati da Microsoft 365:

- Outlook: collaborazione tramite posta elettronica con un gruppo condiviso posta in arrivo e calendario
- Microsoft teams: un'area di lavoro basata su Chat persistente in cui è possibile avere conversazioni informali e in tempo reale su una serie di argomenti, organizzati da sottogruppi specifici
- Yammer: Enterprise Social Experience for Collaboration

> [!NOTE]
> La creazione di un nuovo gruppo tramite altre applicazioni di teamwork, ad esempio SharePoint, planner o stream, creerà un gruppo con una casella di posta in arrivo di Outlook e la possibilità di connettersi ai team.

A seconda della posizione in cui viene creato un gruppo, vengono automaticamente provisionate alcune risorse, ad esempio:
- [Posta in arrivo](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -per le conversazioni di posta elettronica tra i membri del gruppo. La posta in arrivo ha un indirizzo di posta elettronica e può essere impostata in modo da accettare i messaggi provenienti da utenti esterni al gruppo e persino all'esterno dell'organizzazione, analogamente a una lista di distribuzione tradizionale.
 - [Calendario](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – per la pianificazione degli eventi relativi al gruppo
- [Sito del team di SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – archivio centrale per informazioni, collegamenti e contenuti relativi al gruppo
- [Blocco appunti di OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – per raccogliere idee, ricerche e informazioni
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – per l'assegnazione e la gestione delle attività del progetto tra i membri del gruppo
- [Yammer Group](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – un luogo comune per avere conversazioni e condividere informazioni
- Teams-un'area di lavoro basata su chat in Microsoft 365
- Stream-un servizio di streaming video

> [!NOTE]
> Quando viene creato un nuovo gruppo di Office 365 tramite Yammer o teams, il gruppo non è visibile in Outlook o nella rubrica perché la comunicazione principale tra gli utenti avviene nei rispettivi client. I gruppi di Yammer non possono essere connessi a teams.

## <a name="collaboration-options"></a>Opzioni di collaborazione

Sono disponibili più posizioni per collaborare e avere conversazioni all'interno di Microsoft 365. Il modo in cui avviare una conversazione può essere utile per definire una strategia per la comunicazione.

![Diagramma che mostra quando utilizzare Team, Yammer e Outlook](../media/inner-loop-outer-loop.png)

- Teams: area di lavoro basata su chat (collaborazione ad alta velocità) – ciclo interno
  - Creato per la collaborazione con le persone con cui lavori ogni giorno
  - Inserisce informazioni a portata di mano degli utenti in una singola esperienza
  - Aggiungere schede, connettori e bot
  - Chat dal vivo, conferenze audio/video, riunioni registrate

- Yammer: Connect across the org (Enterprise Social) – ciclo esterno
  - Community of practice-gruppi interfunzionali di persone che condividono un interesse o un'esperienza comune ma non lavorano necessariamente insieme in base alla giornata.
  - Connessione di leadership, community di apprendimento, community basate sui ruoli

- Cassetta postale e calendario (collaborazione basata su posta elettronica)
  - Utilizzo per comunicazioni mirate con un gruppo di persone
  - Calendario condiviso per le riunioni con altri membri del gruppo
 
Ogni gruppo ottiene un sito del team di SharePoint connesso in cui gli utenti possono condividere il contenuto, creare pagine personalizzate e notizie sull'autore. È inoltre possibile [connettere i siti del team di SharePoint esistenti ai nuovi gruppi di Microsoft 365](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview).

## <a name="illustrations"></a>Illustrazioni

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams e servizi di produttività correlati in Microsoft 365 per architetti IT
L'architettura logica dei servizi di produttività in Microsoft 365, con Microsoft Teams.

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di scorrimento per poster dell'architettura logica di Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Aggiornato nell'aprile 2019   |Microsoft offre una serie di servizi di produttività che interagiscono tra loro per offrire esperienze di collaborazione con governance dei dati, sicurezza e conformità integrate. <br/> <br/>Questa serie di immagini consente di visualizzare l'architettura logica di servizi di produttività per enterprise architect, con Microsoft Teams.|


### <a name="groups-in-microsoft-365-for-it-architects"></a>Gruppi in Microsoft 365 per architetti IT
Cosa devono sapere gli architetti IT sui gruppi di Microsoft 365

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Aggiornato nel giugno 2019|Queste immagini mostrano dettagliatamente i diversi gruppi, come questi vengono creati e gestiti, e alcuni consigli di governance.|

## <a name="conference-sessions"></a>Sessioni conferenza

Per ulteriori informazioni sulla governance per i gruppi e i team di Microsoft 365, vedere le sessioni di conferenza.

**Aspetti fondamentali**

Informazioni sui principi fondamentali e le nuove innovazioni nei gruppi di Microsoft 365, tra cui la gestione e la governance in scala, procedure consigliate per l'utilizzo e l'adozione di guida e self-service.

- [Abbraccia i gruppi di Microsoft 365](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Governance**

Informazioni su come configurare i gruppi del ciclo di vita di scadenza, i criteri di denominazione, le etichette di classificazione, la collaborazione con gli utenti esterni e la gestione delle autorizzazioni per la creazione del gruppo.

- [Trasformare la collaborazione e la lotta Shadow IT con i gruppi di Office 365](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Esempio di cliente**

Vedere un esempio dietro le quinte del modo in cui Microsoft 365 groups, SharePoint, teams e Yammer collaborano per fornire una piattaforma di collaborazione globale.

- [Trovare la propria collaborazione Sweet spot con i gruppi di Office 365, SharePoint, teams e Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
