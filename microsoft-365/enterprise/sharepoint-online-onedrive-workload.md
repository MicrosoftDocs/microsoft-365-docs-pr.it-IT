---
title: Distribuzione di SharePoint Online e OneDrive for Business per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sulla procedura di pianificazione, implementazione e aumento del valore di SharePoint Online in Microsoft 365 Enterprise nell'organizzazione.
ms.openlocfilehash: 30fe3a971a869a4609d6b8ef2809692b4d4e5420
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400180"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a>Distribuzione di SharePoint Online e OneDrive for Business per Microsoft 365 Enterprise

*Questo carico di lavoro è incluso sia nelle versioni E3 che E5 di Microsoft 365 Enterprise*

SharePoint Online e Microsoft Teams consentono l'archiviazione e la condivisione dei file, la gestione dei contenuti e la collaborazione è un elemento essenziale del valore di collaborazione di Built for Teamwork di Microsoft 365 Enterprise. 

SharePoint Online dispone inoltre di funzionalità di protezione avanzate, tra cui il controllo dell'accesso e le autorizzazioni oltre che la crittografia in-flight e non. La sicurezza di SharePoint Online è un elemento essenziale del valore di intelligent security di Microsoft 365 Enterprise.

I nuovi utenti di SharePoint Online possono vedere [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) e [Introduzione a SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).

Le seguenti fasi e i seguenti passaggi illustrano il processo di definizione del ruolo di SharePoint Online nell'organizzazione attraverso una serie di implementazioni progressive e l'uso e la sua importanza per gli utenti finali. Prima di iniziare, assicurarsi di aver configurato le fasi corrette dell'[infrastruttura di base](deploy-foundation-infrastructure.md) cosicché i team abbiano le funzionalità di sicurezza necessarie. 

Per implementare OneDrive for Business per Microsoft 365 Enterprise, vedere la [Guida di OneDrive per aziende](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fase 1: concezione
In questa fase, si raggruppano le persone per l'implementazione di SharePoint Online e si determina il modo in cui l'organizzazione utilizzerà questa applicazione per soddisfare le proprie esigenze aziendali.

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a>Passaggio 1: raccogliere i membri di distribuzione di SharePoint Online

Per una distribuzione corretta di SharePoint Online nell'[infrastruttura di base di Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), è necessario raccogliere le persone corrette per input e feedback. Le persone chiave includono decision maker dell'azienda, personale IT come architetti e responsabili dell'implementazione e rappresentanti degli utenti finali. 

Questi tre gruppi assicurano che la distribuzione includa analisi che soddisfino le esigenze aziendali, aspetti tecnici sulla migrazione e la sicurezza di cartelle e documenti e che il risultato sia uno strumento di facile utilizzo per l'utente tipico.

#### <a name="result"></a>Risultato

Un elenco di persone che rappresentano gli aspetti aziendali, tecnici e relativi agli utenti finali dell'organizzazione.

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a>Passaggio 2: determinare e assegnare priorità agli scenari aziendali di SharePoint Online

SharePoint Online può essere utilizzato per scopi diversi. È necessario capire quali sono gli obiettivi associati alle esigenze aziendali. È consigliabile assegnare SharePoint Online alla risoluzione dei problemi di archiviazione e condivisione dei documenti, gestione dei contenuti ed esigenze di collaborazione dei team, del reparto o dell'intera organizzazione. 

Vedere l'elenco degli scenari e delle funzionalità in [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).

Di seguito sono indicati i pilastri che possono risolvere le esigenze dell'organizzazion:

|||
|:-----|:-----|
| Condivisione e collaborazione | Sfruttare i siti dei team, i siti di collaborazione e la sincronizzazione. |
| Informazione e impegno | Le informazioni arriveranno in futuro. |
| Trasformazione | Usa il flusso per creare uno o un flusso di lavoro. |
| Sfruttamento delle conoscenze collettive | Utilizza la ricerca per fornire i risultati desiderati all'interno dell'organizzazione. |
| Protezione | Assicura la protezione dell'organizzazione e la giusta conformità. |
| Sviluppo/esterno | Consente alle organizzazioni di sviluppare soluzioni e app personalizzate utilizzando SharePoint Framework. |
|||

Vedere l'[Amministrazione di SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) per le risorse su come configurare SharePoint Online per le proprie esigenze.

Un modo per scoprire i vantaggi di SharePoint Online consiste nell'esaminare come singoli utenti, team, un reparto o l'intera organizzazione interagiscono oggi e quindi individuare uno scenario adatto che fornisca modi più semplici per archiviare e condividere file e per collaborare. Tenere presente che [Microsoft Teams](teams-workload.md) potrebbe essere una soluzione migliore per alcuni scenari.

SharePoint Online consente i seguenti scenari aziendali strategici per Microsoft 365 Enterprise:

- Comunicare con il team per restare aggiornati, sollecitare input e creare coesione e consenso
- Sfruttare le conoscenze collettive
- Consentire agli utenti di trasformare i processi aziendali
- Dare forma alla cultura dell'azienda
- Gestire progetti, attività e scadenze per soddisfare gli obiettivi di business
- Coinvolgere i firstline worker per consentire la trasformazione digitale
- Comprendere le abitudini di lavoro per migliorare la propria influenza e il proprio impatto
- Comunicare con i partner, i colleghi e i clienti
- Archiviare e condividere file all'interno e all'esterno dell'organizzazione per collaborare facilmente nell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Supportare l'organizzazione con privacy e conformità avanzate per soddisfare il regolamento generale sulla protezione dei dati (GDPR)

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a>Sito di SharePoint Online per dati altamente regolamentati

I dati altamente regolamentati sono soggetti a normative internazionali oppure sono i dati più importanti per l'organizzazione, ad esempio segreti commerciali, informazioni sulle risorse finanziare o umane e strategia dell'organizzazione. È possibile configurare un sito di SharePoint Online per l'accesso con restrizioni, la classificazione dei dati, la prevenzione della perdita dei dati e la crittografia per questo tipo di dati. Per informazioni dettagliate, vedere [Siti di Microsoft Teams e di SharePoint Online per i dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Risultato
Un elenco di scenari SharePoint Online che soddisfano le esigenze dell'organizzazione di archiviazione e condivisione dei documenti, gestione dei contenuti e collaborazione.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In questa fase, si pianificano gli aspetti tecnici di una distribuzione di SharePoint Online e si inizia l'implementazione per i gruppi di utenti selezionati.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Prerequisiti: configurazione di identità e accesso dei dispositivi

Per proteggere l'accesso ai siti di SharePoint Online, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint Online consigliati](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Passaggio 1: completare la pianificazione tecnica

Prima di iniziare la pianificazione tecnica, determinare se si desidera utilizzare FastTrack. Se l'organizzazione ha più di 50 postazioni e partecipa a un [piano idoneo](https://technet.microsoft.com/library/dn783224.aspx), è possibile usare i vantaggi di FastTrack, disponibile senza costi aggiuntivi come guida per la pianificazione, distribuzione e l'adozione del servizio. In alternativa, è possibile completare questa operazione utilizzando le procedure guidate di FastTrack Onboarding, disponibili in [FastTrack](https://fasttrack.microsoft.com/) se si accede con il proprio account Office 365.

Se si esegue la pianificazione autonomamente (o in combinazione con FastTrack), è necessario determinare se la rete e l'organizzazione sono pronte per SharePoint Online. È particolarmente importante che siano soddisfatti i criteri di uscita di rete nell'infrastruttura di base, con una particolare attenzione alla larghezza di banda Internet, alla velocità effettiva e ai ritardi dovuti al traffico per ottimizzare le prestazioni per il traffico aggiuntivo per i documenti basati su SharePoint Online.

Utilizzare queste risorse per preparare gli aspetti tecnici di un'implementazione di SharePoint Online: 

- [Guida alla pianificazione di SharePoint Online](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [Eseguire la migrazione a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

Per una migliore comprensione della sicurezza in SharePoint Online, vedere le risorse seguenti:

-   [In che modo SharePoint Online e OneDrive proteggono i dati nel cloud](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [Crittografia dei dati in OneDrive for Business e SharePoint Online](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a>Risultato

Vengono acquisite le informazioni sui siti SharePoint Online e sulla migrazione delle cartelle e dei documenti locali, e si è pronti a implementare SharePoint Online a gruppi selezionati all'interno dell'organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Nella maggior parte delle organizzazioni di medie e grandi dimensioni, è necessario eseguire un'implementazione pilota con le parti interessate dalla fase 1 e appassionati di informatica. Durante la fase pilota:

- Scegliere uno scenario aziendale di SharePoint Online in cui i partecipanti all'implementazione pilota possano esercitarsi.
- Assegnare a tutti i partecipanti una serie di esercitazioni per testare l'archiviazione dei documenti di SharePoint Online, la condivisione, la collaborazione, la pianificazione basata sul team e altre funzionalità.
- Determinare la strategia di gestione delle modifiche e produrre materiali per guidare l'adozione di SharePoint Online da parte degli utenti a livello di organizzazione. I materiali per la gestione delle modifiche possono includere testo per gli annunci tramite posta elettronica, piani di formazione interni, poster hallway e presentazioni. Questi materiali forniscono all'organizzazione informazioni su SharePoint Online e sui suoi vantaggi, con l'obiettivo di aumentare la consapevolezza e l'utilizzo. Vedere l'articolo sulla strategia di gestione delle modifiche di [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) per alcuni suggerimenti.
- I partecipanti alla fase pilota devono analizzare i materiali di gestione delle modifiche in base alle proprie esperienze. Tali materiali possono fornire suggerimenti su best practice e consigli su come descrivere al meglio i vantaggi di SharePoint Online e su come usarli per la collaborazione e la pianificazione.

#### <a name="result"></a>Risultato

La fase pilota di SharePoint Online è completa e i materiali sulla gestione delle modifiche iniziali sono stati sviluppati, rivisti e perfezionati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: implementazione in un gruppo aziendale

Dopo aver completato la fase pilota, implementare SharePoint Online in un gruppo aziendale o in un reparto dell'organizzazione. L'implementazione deve includere:

- Identificazione degli scenari aziendali chiave di SharePoint Online all'interno del gruppo aziendale.
- Attività di annuncio per informare gli utenti di aspettative e sequenze temporali relative all'utilizzo di SharePoint Online per team di reparto, lavoro o progetto.
- Migrazione di cartelle e documenti locali dei membri del gruppo aziendale a SharePoint Online.
- Invio all'utente di formazione o link alle risorse per la presentazione di SharePoint Online e su come usarlo. Vedere la formazione video relativa a [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Un meccanismo di feedback, ad esempio un team Microsoft Teams centrale contenente tutti i membri del gruppo aziendale, per raccogliere commenti e agire sui problemi degli utenti del gruppo aziendale.
 
Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale è pronto e ha iniziato a usare SharePoint Online e i materiali sulla gestione delle modifiche sono stati testati e perfezionati.

## <a name="phase-3-drive-value"></a>Fase 3: aumentare il valore

In questa fase, viene completata l'implementazione del supporto di SharePoint Online agli utenti, per aiutarli a sfruttarne i vantaggi.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Passaggio 1: implementazione nel resto dell'organizzazione

L'implementazione nel resto dell'organizzazione deve includere:

- Identificazione degli scenari aziendali chiave di SharePoint Online all'interno di gruppi aziendali distinti.
- Uso dei materiali di gestione delle modifiche perfezionati per attività di annuncio per informare l'organizzazione su aspettative e tempistiche relative all'uso.
- Migrazione di cartelle e documenti per il resto dell'organizzazione a SharePoint Online.
- Invio all'utente di formazione o link alle risorse per la presentazione di SharePoint Online e su come usarlo.
- Un meccanismo di commenti e suggerimenti come, ad esempio, Team centrale che contiene tutti gli altri, per raccogliere commenti e problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato
L'organizzazione è pronta e la strategia di gestione delle modifiche è in essere per informare, formare e consentire agli utenti di utilizzare SharePoint Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo la distribuzione all'intera organizzazione, è necessario continuare a utilizzare la strategia di gestione delle modifiche affinché:

- I dirigenti promuovano SharePoint Online come strumento principale per l'archiviazione e la condivisione dei documenti e la collaborazione di team, reparti o a livello di organizzazione.
- Gli utenti vengano incoraggiati a usarlo per la calendarizzazione e la collaborazione tra gruppi aziendali, reparti, team di lavoro e di progetto.

Ecco alcune attività suggerite:

- Vedere [Linee guida sull'adozione di Office 365](https://aka.ms/successfactors) per informazioni sulle procedure consigliate generali relative all'adozione di servizi cloud. 
- Vedere i [report attività di Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) per comprendere l'utilizzo del servizio di Office 365 nell'organizzazione. Se non si è un amministratore globale di Office 365 per l'organizzazione, chiedere a qualcun altro le autorizzazioni Lettore report per poter accedere ai report attività.
- Monitorare il luogo in cui vengono pubblicati i feedback (un canale pubblico in un team centrale di Teams o Yammer) per i problemi e i feedback degli utenti sulle loro esperienze con SharePoint Online. Risolvere problemi e rispondere alle domande il più velocemente possibile per impedire che gli utenti si sentano abbandonati e dimostrare supporto nell'implementazione.
- Identificare e rafforzare i sostenitori in ogni gruppo aziendale ed evidenziarne gli obiettivi e le best practice relative all'uso di SharePoint Online. Riflettere i loro successi nell'organizzazione per mostrare il successo e l'adozione del progeto. L'endorsement da parte di figure leader tecniche in un gruppo aziendale può avere un'influenza potente su responsabili e colleghi.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato SharePoint Online come servizio per supportare l'archiviazione della documentazione e la collaborazione.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per dare uno sguardo a Microsoft per scoprire in che modo l'azienda ha distribuito SharePoint Online, vedere [SharePoint nel cloud: informazioni su come Microsoft ha eseguito la migrazione](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Passaggi successivi

Vedere le seguenti risorse per la manutenzione continua di SharePoint Online: 

- [Informazioni sui i livelli di autorizzazione in SharePoint](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [Personalizzare le autorizzazioni del sito di SharePoint](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [Attivare o disattivare la condivisione per SharePoint Online esterna](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [Configurare e gestire le richieste di accesso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

