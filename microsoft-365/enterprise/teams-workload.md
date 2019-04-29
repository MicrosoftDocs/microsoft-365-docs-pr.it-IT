---
title: Distribuire Microsoft Teams per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Procedura di pianificazione, implementazione e aumento del valore di Microsoft Teams in Microsoft 365 Enterprise nell'organizzazione.
ms.openlocfilehash: bfc9e76211779aa960ff7633dd7d59b2b01e9f98
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400210"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Distribuire Microsoft Teams per Microsoft 365 Enterprise

*Questo carico di lavoro è incluso sia nelle versioni E3 che E5 di Microsoft 365 Enterprise*

Microsoft Teams raggruppa chat, conferenze, condivisione di documenti e thread in un modo che semplifica la creazione e la condivisione di contenuti nei gruppi. Teams consente di eseguire il lavoro in team e la collaborazione per Microsoft 365 Enterprise ed è un elemento essenziale per consentire il lavoro di squadra con Microsoft 365. Se non si conosce Teams, vedere [Panoramica di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).
 
Se si usa Skype for Business, stiamo integrando funzionalità di Skype for Business in Teams. Questa operazione verrà eseguita nel corso del tempo e alla fine Teams diventerà un'esperienza client unica. Microsoft è qui per aiutare i clienti importanti di Skype for Business. Vedere [Journey from Skype for Business to Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) (Passaggio da Skype for Business a Microsoft Teams) per ulteriori informazioni.

Le seguenti fasi e i seguenti passaggi illustrano il processo di definizione del ruolo di Teams nell'organizzazione, di adozione di Teams da parte dell'organizzazione attraverso una serie di implementazioni progressive e l'uso di Teams e della sua importanza per gli utenti finali. 

Prima di iniziare, assicurarsi di aver configurato le fasi corrette dell’[infrastruttura di base](deploy-foundation-infrastructure.md) cosicché i team abbiano le funzionalità di sicurezza necessarie.

## <a name="phase-1-envision"></a>Fase 1: concezione

In questa fase, si raggruppano le persone per l'implementazione di Teams e si determina il modo in cui l'organizzazione utilizzerà Teams per soddisfare le proprie esigenze aziendali.

### <a name="step-1-gather-your-teams-deployment-members"></a>Passaggio 1: raccogliere i membri per l'implementazione di Teams
Per una distribuzione corretta di Teams in nell'[infrastruttura di base](deploy-foundation-infrastructure.md) di Microsoft 365, è necessario raccogliere le persone corrette per input e commenti e suggerimenti. Le persone chiave includono decision maker dell'azienda, personale IT come architetti e responsabili dell'implementazione e rappresentanti degli utenti finali. 

Questi tre gruppi assicurano che la distribuzione di Teams includa analisi che soddisfino le esigenze aziendali, aspetti tecnici su licenze e sicurezza e che Teams sia uno strumento di facile utilizzo per l'utente tipico.

#### <a name="result"></a>Risultato

Un elenco di persone che rappresentano gli aspetti aziendali, tecnici e relativi agli utenti finali dell'organizzazione.

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>Passaggio 2: determinare e assegnare priorità agli scenari aziendali di Teams
Teams può essere usato per diversi scopi. È necessario capire gli scopi delle esigenze aziendali sui livelli separati dell'organizzazione, i gruppi aziendali, i reparti e i team che lavorano singolarmente o in progetto. Per esempi che aiutino a definire gli scenari di Teams, vedere [Raccolta di produttività di Microsoft 365](https://www.microsoft.com/microsoft-365/success/?rtc=1). 

Teams deve saper soddisfare team altamente collaborativi e velocissimi che lavorano a stretto contatto e richiedono molti più servizi che la sola posta elettronica che Exchange Online è in grado di fornire. Per fare un esempio, live chat di gruppo con una cronologia registrata e un percorso comune e facile da trovare dove archiviare file e appunti. 

Un modo per vedere i vantaggi di Teams è quello di esaminare il modo in cui un team o un team virtuale interagisce oggi e poi trovare uno scenario di Teams appropriato che sostituisca l'interazione e offra modi più semplici di collaborazione con maggiori funzionalità.

Teams consente i seguenti scenari aziendali per Microsoft 365 Enterprise:

- Comunicare con il team per restare aggiornati, sollecitare input e creare coesione e consenso
- Coinvolgere i firstline worker per consentire la trasformazione digitale
- Comprendere le abitudini di lavoro per migliorare la propria influenza e il proprio impatto

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

#### <a name="microsoft-teams-for-highly-regulated-data"></a>Microsoft Teams per dati altamente regolamentati

I dati altamente regolamentati sono soggetti a normative internazionali oppure sono i dati più importanti per l'organizzazione, ad esempio segreti commerciali, informazioni sulle risorse finanziare o umane e strategia dell'organizzazione. È possibile configurare un team per l'accesso con restrizioni, la classificazione dei dati, la prevenzione della perdita dei dati e la crittografia per questo tipo di dati. Per informazioni dettagliate, vedere [Siti di Microsoft Teams e di SharePoint Online per i dati altamente regolamentati](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Risultato

Elenco di scenari di Teams che rispondono alle esigenze della propria organizzazione per la collaborazione e il lavoro in team.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In questa fase, si pianificano gli aspetti tecnici di una distribuzione di Teams e si inizia l'implementazione per i gruppi di utenti selezionati.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Prerequisiti: configurazione di identità e accesso dei dispositivi

Per proteggere l'accesso ai team, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint Online consigliati](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Passaggio 1: completare la pianificazione tecnica

Prima di iniziare la pianificazione tecnica, determinare se si desidera utilizzare FastTrack. Se l'organizzazione ha più di 50 postazioni e partecipa a un [piano idoneo](https://technet.microsoft.com/library/dn783224.aspx), è possibile usare [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponibile senza costi aggiuntivi come guida per la pianificazione, distribuzione e l'adozione del servizio. In alternativa, è possibile completare questa operazione utilizzando le procedure guidate di FastTrack Onboarding, disponibili in [FastTrack](https://fasttrack.microsoft.com/) se si accede con il proprio account di Office 365.

Se si esegue la pianificazione autonomamente (o in combinazione con FastTrack), è necessario determinare se la rete e l'organizzazione sono pronte per Teams. È particolarmente importante che siano soddisfatti i criteri di uscita di rete nell'[infrastruttura di base](deploy-foundation-infrastructure.md), con una particolare attenzione alla larghezza di banda, alla velocità effettiva e ai ritardi dovuti al traffico per ottimizzare le prestazioni per le riunioni basate su Teams.

Usare queste risorse per preparare gli aspetti tecnici dell'organizzazione per un'implementazione di Teams: 

- [Valutazione della conformità dell'ambiente per Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [ Preparare la rete per Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

Per ulteriori informazioni sulla sicurezza in Teams, rivedere le risorse aggiuntive seguenti:

- [Panoramica sulla sicurezza e conformità in Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Gruppi di Office 365 e Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Accesso guest in Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

Usare queste risorse per comprendere la gestione delle licenze di Teams ed eseguire la configurazione di Teams per l'organizzazione:

- [Gestione delle licenze di Office 365 per Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Gestione degli accessi utente per Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Ottenere client per Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Attivare Microsoft Teams nell'organizzazione di Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Gestire le funzionalità di Microsoft Teams nell'organizzazione di Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a>Risultato

La pianificazione di rete, sicurezza e delle licenze di Office 365 viene effettuata e si è pronti a iniziare a distribuire Teams nei gruppi selezionati nell'organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Nella maggior parte delle organizzazioni di medie e grandi dimensioni, è necessario eseguire un'implementazione pilota con le parti interessate dalla fase 1 e appassionati di informatica. Durante la fase pilota:

- Scegliere uno scenario aziendale di Teams in cui i partecipanti alla fase IT possono fare pratica. Vedere il [kit introduttivo su Microsoft Teams](http://microsoft.com/download/56505) per alcuni suggerimenti.
- Assegnare a tutti i partecipanti della fase pilota una serie di esercitazioni per testare le chat, l'archiviazione dei file, le riunioni e altre funzionalità basate su Teams.
- Determinare la strategia di gestione delle modifiche e produrre materiali per guidare l'adozione da parte degli utenti a livello di organizzazione. I materiali sulla gestione delle modifiche possono includere testo per gli annunci tramite posta elettronica, piani di formazione interni, poster hallway e presentazioni. Questi materiali forniscono informazioni su Teams e sui suoi vantaggi all'organizzazione con l'obiettivo di aumentare la consapevolezza e l'utilizzo. Vedere [Strategia di gestione delle modifiche di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) per alcuni suggerimenti.
- I partecipanti della fase pilota devono analizzare i materiali sulla strategia di gestione delle modifiche in base alle proprie esperienza. I materiali possono fornire suggerimenti su best practice e su come meglio descrivere i vantaggi di Teams e su come usarli per la collaborazione e il lavoro in team.

#### <a name="result"></a>Risultato

La fase pilota di Teams è completa e i materiali sulla gestione delle modifiche iniziali sono stati sviluppati, rivisti e perfezionati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: implementazione in un gruppo aziendale

Dopo aver completato la fase pilota, implementare Teams in un gruppo aziendale o reparto dell'organizzazione. L'implementazione deve includere:

- Identificazione degli scenari aziendali chiave di Teams all'interno del gruppo aziendale.
- Attività di annuncio per informare gli utenti di aspettative e sequenze temporali relativa all'utilizzo di Teams per team di reparto, lavoro o progetto.
- Indirizzare gli utenti alla formazione su Teams o alle risorse per introdurre Teams e che spiegano come usarlo.
- Un meccanismo di commenti e suggerimenti, ad esempio un team centrale che contiene ogni gruppo aziendali, per raccogliere commenti e problemi degli utenti del gruppo aziendale.

Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale è pronto e ha iniziato a usare Teams e i materiali sulla gestione delle modifiche sono stati testati e perfezionati.

## <a name="phase-3-drive-value"></a>Fase 3: aumentare il valore

In questa fase, è stata completata l'implementazione di Teams nell'organizzazione e si offre supporto ai Teams affinché possano capirne i vantaggi.

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>Passaggio 1: implementazione di Teams nel resto dell'organizzazione

Dopo aver completato l'implementazione in un gruppo aziendale specifico, implementare Teams nel resto dell'organizzazione. L'implementazione deve includere:

- Identificazione degli scenari aziendali chiave di Teams all'interno di gruppi aziendali separati.
- Uso dei materiali di gestione delle modifiche perfezionati per attività di annuncio per informare l'organizzazione su aspettative e tempistiche relative all'uso di Teams per team di reparto, lavoro o progetto.
- Indirizzare gli utenti alla formazione su Teams o alle risorse per introdurre Teams e che spiegano come usarlo. Vedere le risorse di formazione in [Formazione dell'utente finale su Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).
- Un meccanismo di commenti e suggerimenti come, ad esempio, un team centrale che contiene tutti gli altri, per raccogliere commenti e gestire i problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato

L'organizzazione è pronta e la strategia di gestione delle modifiche è in essere per informare, formare e consentire agli utenti di iniziare a utilizzare Teams.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo aver distribuito Teams all'intera organizzazione, è necessario continuare a utilizzare la strategia di gestione delle modifiche affinché:

- I dirigenti promuovano Teams come strumento di lavoro in team e collaborazione nell'organizzazione.
- Incoraggino i singoli utenti a usarlo per le comunicazione e la collaborazione tra gruppi aziendali, di reparto, di lavoro e di progetto.

Ecco alcune attività suggerite:

- Vedere [Linee guida sull'adozione di Office 365](https://aka.ms/successfactors) per informazioni sulle procedure consigliate generali relative all'adozione di servizi cloud. 
- Vedere i [report attività di Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) per comprendere l'utilizzo del servizio di Office 365 nell'organizzazione. Se non si è un amministratore globale di Office 365 per l'organizzazione, chiedere a qualcun altro le autorizzazioni Lettore report per poter accedere ai report attività.
- Monitorare il luogo in cui vengono pubblicati i commenti e suggerimenti (un canale pubblico in un team centrale o Yammer) per i problemi e i commenti e suggerimenti degli utenti sulle loro esperienze con Teams. Risolvere problemi e rispondere alle domande il più velocemente possibile per impedire disagi e abbandono di Teams da parte degli utenti.
- Identificare e rafforzare i sostenitori in ogni gruppo aziendale ed evidenziarne gli obiettivi e le best practice relative all'uso di Teams. Riflettere i loro successi nell'organizzazione per mostrare i successi di progetto e l'adozione. L'endorsement da parte di figure leader tecniche in un gruppo aziendale può avere un'influenza potente su responsabili e colleghi.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato Teams come strumento di collaborazione e lavoro in team.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per scoprire come Microsoft ha distribuito e utilizza Microsoft Teams per la collaborazione, vedere:

- [La distribuzione di Microsoft Teams semplifica la collaborazione e migliora il lavoro in team](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [Microsoft Teams aumenta la collaborazione nella moderna rete aziendale di Microsoft](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>Passaggi successivi

- [Gestire le funzionalità di Microsoft Teams nell'organizzazione di Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Formazione degli amministratori per Microsoft Teams](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
