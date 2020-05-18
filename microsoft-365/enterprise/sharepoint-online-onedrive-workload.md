---
title: Distribuire SharePoint e OneDrive per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Passaggi del processo di pianificazione, distribuzione e promozione del valore di SharePoint all'interno dell'organizzazione.
ms.openlocfilehash: 6b0483073a836f29b1faa5a30018848ef7b2df34
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268210"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Distribuire SharePoint e OneDrive per Microsoft 365 Enterprise

*Questo carico di lavoro è incluso sia nelle versioni E3 che E5 di Microsoft 365 Enterprise*

SharePoint e Microsoft Teams consentono l'archiviazione e la condivisione dei file, la gestione dei contenuti e la collaborazione e sono gli elementi fondamentali del valore di collaborazione di Built for Teamwork di Microsoft 365 Enterprise. 

SharePoint dispone inoltre di funzionalità di sicurezza avanzate, tra cui il controllo dell'accesso e le autorizzazioni, oltre alla crittografia in-flight e dei dati inattivi. La sicurezza di SharePoint è un elemento essenziale del valore di sicurezza intelligente di Microsoft 365 Enterprise.

I nuovi utenti di SharePoint possono vedere [SharePoint](https://products.office.com/sharepoint/collaboration) e [Introduzione a SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).

Le fasi e i passaggi riportati di seguito illustrano il processo di definizione del ruolo di SharePoint nell'organizzazione attraverso una serie di implementazioni progressive e la promozione del suo uso e della sua importanza presso gli utenti finali. Prima di iniziare, assicurarsi di aver configurato le fasi corrette dell'[infrastruttura di base](deploy-workloads.md#foundation-infrastructure-prerequisites) affinché i siti di SharePoint abbiano le funzionalità di sicurezza necessarie. 

Per implementare OneDrive per Microsoft 365 Enterprise, vedere la [Guida di OneDrive per le aziende](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fase 1: concezione
In questa fase, si raggruppano i partner dell'organizzazione per l'implementazione di SharePoint e si stabilisce in che modo l'organizzazione utilizzerà questa applicazione per soddisfare le proprie esigenze aziendali.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Passaggio 1: raccogliere i membri di distribuzione di SharePoint

Per una distribuzione corretta di SharePoint nell'[infrastruttura di base di Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), è necessario raccogliere le persone corrette per input e feedback. Le persone chiave includono i decision maker dell'azienda, il personale IT come architetti e responsabili dell'implementazione e i rappresentanti degli utenti finali. 

Questi tre gruppi assicurano che la distribuzione includa analisi che soddisfino le esigenze aziendali, aspetti tecnici sulla migrazione e la sicurezza di cartelle e documenti e che il risultato sia uno strumento di facile utilizzo per l'utente tipico.

#### <a name="result"></a>Risultato

Un elenco di persone rappresentative del punto di vista aziendale, tecnico e degli utenti finali dell'organizzazione.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Passaggio 2: determinare e assegnare priorità agli scenari aziendali di SharePoint

SharePoint può essere utilizzato per scopi diversi. Occorre associare i vari scopi alle esigenze aziendali. È consigliabile assegnare SharePoint alla risoluzione dei problemi di archiviazione e condivisione dei documenti, gestione dei contenuti ed esigenze di collaborazione dei team, del reparto o dell'intera organizzazione. 

Vedere l'elenco degli scenari e delle funzionalità in [SharePoint](https://products.office.com/sharepoint/collaboration ).

I pilastri aziendali seguenti possono soddisfare le esigenze dell'organizzazione:

|||
|:-----|:-----|
| Condivisione e collaborazione | Sfruttare i siti dei team, i siti di comunicazione e la sincronizzazione. |
| Informazione e impegno | Le informazioni arriveranno in futuro. |
| Trasformazione | Usa Flow per creare flussi di lavoro automatizzati tra app e servizi. |
| Sfruttamento delle conoscenze collettive | Utilizza la ricerca per fornire i risultati desiderati all'interno dell'organizzazione. |
| Protezione | Assicura la protezione dell'organizzazione e la giusta conformità. |
|||

Vedere [Amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-online) per le risorse su come configurare SharePoint per le proprie esigenze.

Un modo per scoprire i vantaggi di SharePoint consiste nell'esaminare come i singoli utenti, un team, un reparto o l'intera organizzazione interagiscono oggi e quindi individuare uno scenario adatto che fornisca modi più semplici per archiviare e condividere file. Tenere presente che [Microsoft Teams](teams-workload.md) potrebbe essere una soluzione migliore per alcuni scenari.

#### <a name="result"></a>Risultato
Un elenco di scenari di SharePoint che soddisfano le esigenze dell'organizzazione in termini di archiviazione e condivisione dei documenti, gestione dei contenuti, collaborazione e sicurezza.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In questa fase si pianificano gli aspetti tecnici di una distribuzione di SharePoint e si inizia l'implementazione per determinati gruppi di utenti.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Prerequisiti: configurazione di identità e accesso dei dispositivi

Per proteggere l'accesso ai siti di SharePoint, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint consigliati](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Passaggio 1: completare la pianificazione tecnica

Prima di avviare la pianificazione tecnica, stabilire se si intende usare FastTrack. Se l'organizzazione dispone di più di 50 postazioni e partecipa a un [piano idoneo](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), è possibile usufruire dei vantaggi FastTrack, disponibili senza costi aggiuntivi come aiuto per la pianificazione, la migrazione, la distribuzione e l'adozione dei servizi. In alternativa, è possibile completare autonomamente queste operazioni utilizzando le procedure guidate di onboarding FastTrack, disponibili in [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) quando si esegue l'accesso con l'account Microsoft 365.

Se si esegue la pianificazione autonomamente, o in combinazione con FastTrack, è necessario determinare se la rete e l'organizzazione sono pronte per SharePoint. È particolarmente importante che siano soddisfatti i [criteri di uscita di rete](networking-exit-criteria.md) nell'infrastruttura di base, con una particolare attenzione alla larghezza di banda Internet, alla velocità effettiva e ai ritardi dovuti al traffico per ottimizzare le prestazioni per il traffico aggiuntivo per i documenti basati su SharePoint.

Usare [Eseguire la migrazione a SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) per preparare l'implementazione di SharePoint: 

Per una migliore comprensione della sicurezza in SharePoint, vedere le risorse seguenti:

-     [In che modo SharePoint e OneDrive proteggono i dati nel cloud](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-     [Crittografia dei dati in OneDrive e SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Risultato

Vengono acquisite le informazioni sui siti di SharePoint e sulla migrazione di cartelle e documenti locali e si è pronti a distribuire SharePoint in determinati gruppi all'interno dell'organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Nella maggior parte delle organizzazioni di medie e grandi dimensioni, è necessario eseguire un'implementazione pilota con gli stakeholder della fase 1, early adopter e appassionati di informatica. Durante la fase pilota:

- Scegliere uno scenario aziendale di SharePoint in cui i partecipanti all'implementazione pilota possano esercitarsi.
- Assegnare a tutti i partecipanti una serie di esercitazioni per testare l'archiviazione dei documenti, la condivisione, la collaborazione e altre funzionalità di SharePoint.
- Determinare la strategia di gestione delle modifiche e produrre materiali per promuovere l'adozione di SharePoint nell'intera organizzazione. I materiali per la gestione delle modifiche possono includere il testo dell'annuncio tramite posta elettronica, i piani di formazione interna, poster e presentazioni. Questi materiali forniranno informazioni su SharePoint e sui suoi vantaggi, miranti a sensibilizzare e a promuovere l'utilizzo. Per iniziare, vedere le [risorse di adozione di SharePoint](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/).
- Fare in modo che i partecipanti al programma pilota IT prendano visione dei materiali per la gestione delle modifiche in base alle proprie esperienze. Possono fornire suggerimenti sulle procedure consigliate e consigli su come descrivere al meglio i vantaggi di SharePoint e su come usarlo.

#### <a name="result"></a>Risultato

La fase pilota di SharePoint è completa e i materiali per la gestione delle modifiche iniziali sono stati sviluppati, rivisti e perfezionati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: eseguire l'implementazione in un gruppo aziendale

Dopo aver completato la fase pilota, implementare SharePoint in un gruppo aziendale o in un reparto dell'organizzazione. L'implementazione deve includere:

- Identificazione degli scenari aziendali chiave di SharePoint all'interno del gruppo aziendale.
- Attività di annuncio per informare gli utenti circa le aspettative e le sequenze temporali per l'utilizzo di SharePoint per reparti o per team di lavoro o progetto.
- Migrazione di cartelle e documenti locali dei membri del gruppo aziendale a SharePoint.
- Offerta di formazione agli utenti o collegamenti a risorse che presentano SharePoint e spiegano come usarlo. Vedere il video di formazione su [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Un meccanismo di feedback, ad esempio un team Microsoft Teams centrale contenente tutti i membri del gruppo aziendale, per raccogliere commenti e agire sui problemi degli utenti del gruppo aziendale.
 
Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale è pronto e ha iniziato a usare SharePoint e i materiali per la gestione delle modifiche sono stati testati e perfezionati.

## <a name="phase-3-drive-value"></a>Fase 3: promuovere il valore

In questa fase viene completata l'implementazione di SharePoint e si aiutano gli utenti a sfruttarne i vantaggi.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Passaggio 1: implementazione nel resto dell'organizzazione

L'implementazione nel resto dell'organizzazione deve includere:

- Identificazione degli scenari aziendali chiave di SharePoint all'interno di gruppi aziendali distinti.
- Uso dei materiali per la gestione delle modifiche perfezionati per le attività di annuncio per informare l'organizzazione su aspettative e tempistiche relative all'uso.
- Migrazione di cartelle e documenti per il resto dell'organizzazione a SharePoint.
- Offerta di formazione agli utenti o collegamenti a risorse che presentano SharePoint e spiegano come usarlo.
- Un meccanismo di commenti e suggerimenti come, ad esempio, Team centrale che contiene tutti gli altri, per raccogliere commenti e problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato
L'organizzazione è pronta ed è stata predisposta la strategia di gestione delle modifiche per informare, formare e consentire agli utenti di utilizzare SharePoint.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo la distribuzione all'intera organizzazione, è necessario continuare a utilizzare la strategia di gestione delle modifiche affinché:

- La leadership promuova SharePoint come strumento principale per l'archiviazione e la condivisione di documenti.
- Le persone siano stimolate a usarlo per l'archiviazione e la condivisione di documenti tra gruppi di lavoro, reparti e team di lavoro e progetto.

Ecco alcune attività suggerite:

- Vedere [Fattori di successo per Microsoft 365](https://aka.ms/successfactors) per informazioni sulle procedure generali consigliate relative all'adozione di servizi cloud. 
- Vedere [Report di Microsoft 365 nell'interfaccia di amministrazione](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) per comprendere l'utilizzo del servizio nell'organizzazione. Se non si è un amministratore globale dell'organizzazione, chiedere a un utente con tale ruolo le autorizzazioni di lettura per i report in modo da poter accedere ai report attività.
- Monitorare il punto di raccolta feedback (un canale pubblico in un team di Teams o Yammer) per rilevare i problemi riscontrati o il feedback fornito dagli utenti sulle loro esperienze con SharePoint. Rispondere alle domande e ai problemi nel più breve tempo possibile per evitare che gli utenti siano frustrati e dimostrare il supporto per l'implementazione.
- Identificare e coltivare i campioni in ogni gruppo aziendale ed evidenziarne i risultati e le procedure consigliate per l'uso di SharePoint. Far conoscere i loro risultati all'interno dell'organizzazione per dimostrare il successo del progetto e l'adozione. L'appoggio dei leader tecnici all'interno di un gruppo aziendale può influenzare positivamente la leadership e i pari.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato SharePoint in Microsoft 365 Enterprise per supportare l'archiviazione della documentazione e la collaborazione.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per dare un'occhiata in casa Microsoft e scoprire in che modo ha distribuito SharePoint, vedere [SharePoint nel cloud: informazioni su come Microsoft ha eseguito la migrazione](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Passaggi successivi

Vedere le seguenti risorse per la manutenzione continua di SharePoint: 

- [Livelli delle autorizzazioni in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [Personalizzare le autorizzazioni del sito di SharePoint](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Attivare o disattivare la condivisione esterna per SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Configurare e gestire le richieste di accesso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
