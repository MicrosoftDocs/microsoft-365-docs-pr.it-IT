---
title: Distribuire Exchange Online per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Eseguire il processo di pianificazione, implementazione e guida del valore di Exchange online in Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: a13cb36dd313ef3e6763c6c48720bb2b3e935880
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981877"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Distribuire Exchange Online per Microsoft 365 Enterprise

*Questo carico di lavoro è incluso sia nelle versioni E3 che E5 di Microsoft 365 Enterprise*

Exchange Online è il servizio cloud principale per la posta elettronica e il calendario che consente agli utenti di collaborare in modo da non richiedere chat in tempo reale o archiviazione centralizzata dei documenti. Exchange Online è il modo in cui si esegue la comunicazione e la pianificazione di breve durata del gruppo individuale e di piccole dimensioni ed è un elemento chiave del valore costruito per il lavoro di squadra di Microsoft 365 Enterprise. Exchange Online consente di ottenere ulteriori informazioni e di lavorare in modo più efficace con l'applicazione Outlook ben nota, indipendentemente dal dispositivo in uso.

Exchange Online dispone anche di funzionalità di sicurezza avanzate, tra cui il filtro antimalware e antispam per proteggere le cassette postali e le funzionalità di prevenzione della perdita di dati che impediscono agli utenti di inviare messaggi di informazioni riservate a persone non autorizzate. La sicurezza di Exchange Online è un elemento chiave del valore di sicurezza intelligente di Microsoft 365 Enterprise.

Se sei nuovo di zecca per Exchange Online, consulta [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Nelle fasi e nei passaggi seguenti viene illustrato il processo di definizione del ruolo di Exchange Online nell'organizzazione, l'onboarding dell'organizzazione a Exchange Online tramite una serie di graduali progressivi e l'utilizzo della Guida di Exchange Online e del relativo valore per gli utenti finali.

>[!Note]
>Queste istruzioni per la distribuzione devono essere seguite solo dopo aver completato la [fase 2-Identity](identity-infrastructure.md) dell'infrastruttura di Microsoft 365 Enterprise Foundation.
>

## <a name="phase-1-envision"></a>Fase 1: concezione

In questa fase, si raccolgono gli utenti per la distribuzione di Exchange Online e si determina il modo in cui l'organizzazione utilizzerà Exchange Online per soddisfare le proprie esigenze aziendali.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Passaggio 1: raccogliere i membri della distribuzione di Exchange Online

Per una distribuzione di Exchange Online con esito positivo sulla [fase 2-identità](identity-infrastructure.md) dell'infrastruttura di Microsoft 365 Enterprise Foundation, è necessario ottenere gli utenti giusti per gli input e i commenti e suggerimenti. Le persone principali includono responsabili decisionali aziendali, personale IT come architetti e implementatori e sostenitori per gli utenti finali. 

Questi tre gruppi assicurano che la distribuzione di Exchange Online includa considerazioni che soddisfano le esigenze aziendali, gli aspetti tecnici della migrazione delle cassette postali e la sicurezza e che il risultato sarà qualcosa che utilizzerà gli utenti tipici.

#### <a name="result"></a>Risultato

Un elenco di persone che rappresentano gli aspetti aziendali, tecnici e relativi agli utenti finali dell'organizzazione.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Passaggio 2: determinare e assegnare priorità agli scenari aziendali di Exchange Online

Exchange Online può essere utilizzato per scopi diversi. È necessario capire quali scopi devono essere mappati alle proprie esigenze aziendali sui livelli distinti dell'organizzazione, i gruppi aziendali, i reparti o i singoli team di lavoro e di progetto. È consigliabile rivolgersi a Exchange Online per soddisfare le esigenze di pianificazione e comunicazione individuali e di piccolo gruppo. 

Un modo per visualizzare i vantaggi di Exchange Online consiste nell'esaminare in che modo gli utenti, un team o un v-team interagiscono oggi e quindi individuare uno scenario appropriato che consente di comunicare, pianificare riunioni e collaborare. Tenere presente che [Microsoft teams](teams-workload.md) potrebbe essere una scelta migliore per alcuni degli scenari di collaborazione.

#### <a name="result"></a>Risultato
Un elenco di scenari di Exchange Online che soddisfano le esigenze dell'organizzazione per la comunicazione, la pianificazione e la collaborazione di breve durata.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In questa fase, si pianificano gli aspetti tecnici di una distribuzione di Exchange Online e si inizia l'implementazione per i gruppi di utenti selezionati.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Prerequisiti: configurazione di identità e accesso dei dispositivi

Per proteggere l'accesso alle cassette postali di Exchange Online, verificare che siano stati configurati i [criteri di identità e accesso ai dispositivi](identity-access-policies.md) e i [criteri di accesso di Exchange Online consigliati](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Passaggio 1: completare la pianificazione tecnica

Prima di iniziare la pianificazione tecnica, determinare se si desidera utilizzare FastTrack. Se l'organizzazione ha più di 50 seggi e partecipa a un [piano idoneo](https://technet.microsoft.com/library/dn783224.aspx), è possibile utilizzare [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponibile senza costi aggiuntivi per guidare l'utente attraverso la pianificazione, la distribuzione e l'adozione dei servizi. In alternativa, è possibile eseguire questa operazione manualmente utilizzando le procedure guidate di onboarding di FastTrack, disponibili da [FastTrack](https://fasttrack.microsoft.com/) una volta che si accede con l'account di Office 365.

Se si sta eseguendo la propria pianificazione o in combinazione con FastTrack, è necessario determinare se la rete e l'organizzazione sono pronte per Exchange Online. È particolarmente importante che vengano soddisfatti i criteri di uscita per la rete nell'infrastruttura di base, con particolare attenzione alla larghezza di banda Internet, alla velocità effettiva e ai ritardi del traffico per massimizzare le prestazioni per il traffico aggiuntivo per Exchange Messaggi di posta elettronica e allegati basati su online.

Utilizzare queste risorse per preparare gli aspetti tecnici di un'implementazione di Exchange Online: 

- [Modalità di migrazione della posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Collaborazione in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatari in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Per una migliore comprensione della sicurezza in Exchange Online, vedere le risorse seguenti:

- [Autorizzazioni in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Sicurezza e conformità per Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Protezione antispam e antimalware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Successivamente, utilizzare queste risorse per comprendere la gestione delle cassette postali di Exchange Online:

- [Creare cassette postali degli utenti in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Gestire le cassette postali degli utenti](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Creazione e gestione dei gruppi di distribuzione](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Risultato

Si capisce che la migrazione, la sicurezza e la gestione delle cassette postali sono pronte per iniziare a eseguire la distribuzione di Exchange Online ai gruppi selezionati nell'organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Nella maggior parte delle organizzazioni di medie e grandi dimensioni, è necessario eseguire un'implementazione pilota con le parti interessate dalla fase 1 e appassionati di informatica. Durante la fase pilota:

- Scegliere uno scenario aziendale di Exchange online in cui è possibile praticare i partecipanti pilota IT.
- Fornire ai partecipanti pilota le licenze di Office 365 e migrare le cassette postali locali a Exchange Online.
- Offrire ai partecipanti piloti una serie di esercitazioni per testare la posta elettronica, la pianificazione e altre funzionalità di Exchange Online.
- Determinare la strategia di gestione delle modifiche e produrre materiali per guidare l'adozione da parte dell'utente a livello di organizzazione di Exchange Online. I materiali di gestione delle modifiche possono includere testo dell'annuncio di posta elettronica, piani di formazione interni, manifesti dei corridoi e presentazioni. Questi materiali informeranno l'organizzazione su Exchange Online e i suoi vantaggi con gli obiettivi di sensibilizzazione e utilizzo della guida. Per alcune idee, vedere l'articolo relativo alla [strategia di gestione delle modifiche per Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) .
- È necessario che i partecipanti al progetto IT rivedano i materiali di gestione delle modifiche in base alle proprie esperienze. Sono in grado di fornire suggerimenti su procedure consigliate e consigli su come descrivere al meglio i vantaggi di Exchange Online e su come utilizzarlo per la comunicazione e la pianificazione.

#### <a name="result"></a>Risultato

Il pilota IT di Exchange Online è completo e i materiali di gestione delle modifiche iniziali sono stati sviluppati, rivisti e perfezionati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: implementazione in un gruppo aziendale

Dopo aver completato il pilota IT, eseguire l'implementazione di Exchange online in un gruppo o reparto aziendale dell'organizzazione. Se l'organizzazione utilizza un servizio di posta elettronica locale, ad esempio Exchange Server, questa implementazione è costituita dalla migrazione delle cassette postali. Questa implementazione deve includere:

- Identificazione degli scenari aziendali chiave per Exchange Online all'interno del gruppo aziendale.
- Attività di annuncio per informare gli utenti delle aspettative e delle sequenze temporali per l'utilizzo di Exchange Online per i reparti e i team di lavoro o di progetto.
- La migrazione delle cassette postali locali dei membri del gruppo aziendale a Exchange Online.
- Fornire formazione utente su Exchange Online o collegamenti a risorse per introdurre Exchange Online e come utilizzarlo.
- Un meccanismo di feedback, ad esempio un team Microsoft Teams centrale contenente tutti i membri del gruppo aziendale, per raccogliere commenti e agire sui problemi degli utenti del gruppo aziendale.

Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale è attivo e funzionante con Exchange Online e i materiali di gestione delle modifiche sono stati testati e perfezionati.

## <a name="phase-3-drive-value"></a>Fase 3: aumentare il valore

In questa fase, è possibile completare l'implementazione di Exchange Online e supportare gli utenti per aiutarli a realizzare i propri vantaggi.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Passaggio 1: implementazione di Exchange Online per il resto dell'organizzazione

L'implementazione nel resto dell'organizzazione deve includere:

- Identificazione degli scenari aziendali chiave per Exchange Online all'interno di gruppi aziendali distinti.
- Utilizzo dei materiali di gestione delle modifiche raffinati per le attività di annuncio per informare l'organizzazione delle aspettative e delle sequenze temporali per l'utilizzo di Exchange Online.
- La migrazione delle cassette postali per il resto dell'organizzazione a Exchange Online.
- Offrire la formazione degli utenti in Exchange Online o fornire collegamenti alle risorse per introdurre Exchange Online e come utilizzarlo.
- Un meccanismo di commenti e suggerimenti come, ad esempio, Team centrale che contiene tutti gli altri, per raccogliere commenti e problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato

L'organizzazione è in esecuzione e la strategia di gestione delle modifiche è in atto per informare, formare e consentire agli utenti di utilizzare Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo aver eseguito l'implementazione di Exchange Online all'intera organizzazione, è necessario continuare a utilizzare la strategia di gestione delle modifiche per eseguire le operazioni seguenti:

- Fare in modo che la leadership promuova Exchange Online come strumento principale per la comunicazione e la pianificazione individuali e di breve durata.
- Incoraggiare gli utenti a usarlo per le comunicazioni, il calendario e la collaborazione di team di business, di reparto, di lavoro e di progetto.

Ecco alcune attività suggerite:

- Vedere [Linee guida sull'adozione di Office 365](https://aka.ms/successfactors) per informazioni sulle procedure consigliate generali relative all'adozione di servizi cloud. 
- Vedere i [report attività di Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) per comprendere l'utilizzo del servizio di Office 365 nell'organizzazione. Se non si è un amministratore globale di Office 365 per l'organizzazione, chiedere a qualcun altro le autorizzazioni Lettore report per poter accedere ai report attività.
- Monitorare la sede dei commenti e suggerimenti (un canale pubblico di un team o un Yammer di team centrale) per problemi e commenti e suggerimenti da parte di utenti in merito alle proprie esperienze con Exchange Online. Risolvere le domande e i problemi più velocemente possibile per evitare che gli utenti siano frustrati e dimostrare il supporto per l'implementazione.
- Identificare e alimentare i campioni di ogni gruppo aziendale ed evidenziare i risultati e le procedure consigliate con Exchange Online. Tenere conto dei successi ottenuti nell'organizzazione per mostrare il successo e l'adozione del progetto. L'approvazione da parte dei responsabili tecnici all'interno di un gruppo aziendale può esercitare un'influenza potente su leader e coetanei.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato Exchange Online come strumento di comunicazione e pianificazione di breve durata individuale e di piccolo gruppo.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per sbirciare all'interno di Microsoft e scoprire come la società ha eseguito la migrazione a Exchange Online e utilizza Exchange Online Protection per proteggersi dagli attacchi informatici, vedere:

- [Microsoft esegue la migrazione di 150.000 cassette postali a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft utilizza l'intelligence per le minacce per proteggere, rilevare e rispondere alle minacce](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft contrasta i tentativi di phishing con Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Passaggi successivi

Vedere queste risorse per la manutenzione in esecuzione di Exchange Online:

- [Interfaccia di amministrazione di Exchange in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Monitoraggio, creazione di rapporti e traccia dei messaggi in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Back up della posta elettronica in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
