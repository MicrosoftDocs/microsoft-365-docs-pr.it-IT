---
title: Distribuzione di Exchange Online per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: Passaggi del processo di pianificazione, distribuzione e che influisce sul valore di Exchange Online in Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: 36b24290acd4467400eab86b4c2760ccad65deab
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868901"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Distribuzione di Exchange Online per Microsoft 365 Enterprise

Exchange Online è il servizio cloud primario per la posta elettronica e calendario che consente agli utenti collaborano in modo che non richiedono in tempo reale in una chat o centralizzati memorizzazione dei documenti. Exchange Online è la modalità di conversione di comunicazione tramite gruppi singoli e piccolo di breve durata e la pianificazione e un elemento chiave di realizzato per valore il lavoro del team di Microsoft 365 Enterprise. Exchange Online consente di ottenere informazioni e lavorare in modo più efficace con l'applicazione Outlook conosciuto, indipendentemente dalla quale dispositivo si è in.

Exchange Online anche con avanzate funzionalità di protezione inclusi anti-malware e filtro di protezione da posta indesiderata per proteggere le cassette postali e funzionalità di prevenzione della perdita di dati che impediscono agli utenti di inviare inavvertitamente informazioni riservate a persone non autorizzate. Protezione Exchange Online è un elemento chiave del valore intelligente protezione di Microsoft 365 Enterprise.

Se si è nuova in Exchange Online, vedere [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Le fasi e i passaggi seguenti viene illustrato il processo di definizione degli obiettivi il ruolo di Exchange Online nell'organizzazione, onboarding all'organizzazione di Exchange Online tramite una serie di implementazioni progressive e che influisce sui dati di utilizzo di Exchange Online e la relativa proprietà valore per gli utenti finali.

>[!Note]
>In queste istruzioni distribuzione devono essere seguite solo dopo aver completato l' [infrastruttura foundation](deploy-foundation-infrastructure.md) Microsoft 365 Enterprise.
>

## <a name="phase-1-envision"></a>Fase 1: concezione

In questa fase, raccogliere le persone per la distribuzione di Exchange Online e determinare come verrà utilizzata dall'organizzazione Exchange Online per soddisfare le esigenze aziendali.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Passaggio 1: Raccogliere i membri di distribuzione di Exchange Online

Per una corretta distribuzione di Exchange Online in primo piano rispetto a Microsoft 365 [infrastruttura foundation](deploy-foundation-infrastructure.md), è necessario ottenere le persone giuste per l'input e commenti e suggerimenti. Utenti principali includono dirigenti aziendali, il personale IT, ad esempio gli architetti e ai responsabili dell'implementazione e sostenitori per gli utenti finali. 

Questi tre gruppi verificare che la distribuzione di Exchange Online include considerazioni che soddisfare le esigenze aziendali, aspetti tecnici di sicurezza e la migrazione delle cassette postali e che il risultato è un elemento che verrà utilizzato dagli utenti tipici.

#### <a name="result"></a>Risultato

Un elenco di persone che rappresentano gli aspetti aziendali, tecnici e relativi agli utenti finali dell'organizzazione.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Passaggio 2: Determinare e impostare la priorità gli scenari aziendali Exchange Online

Exchange Online può essere utilizzato per diversi scopi. È necessario capire quali scopi mappare alle esigenze aziendali in diversi livelli della propria organizzazione, i gruppi aziendali, i reparti o i singoli team di progetto e utilizzo. Si deve essere indirizzata a Exchange Online per soddisfare le comunicazioni di breve durata gruppo singoli e piccolo e pianificazione delle esigenze. 

Per visualizzare i vantaggi di Exchange Online è possibile esaminare come singoli utenti, un team o un team v interagire oggi e quindi individuare uno scenario adatto che fornisce i metodi più semplici per comunicare, pianificano le riunioni e collaborare. Tenere presente che i [Team Microsoft che](teams-workload.md) potrebbe essere la soluzione migliore per alcuni degli scenari di collaborazione.

Exchange Online consente i seguenti scenari aziendali per Microsoft 365 Enterprise:

- Collaborare su documenti in tempo reale e non, per semplificare il processo di cooperazione
- Gestire progetti, attività e scadenze per soddisfare gli obiettivi di business
- Comprendere le abitudini di lavoro per migliorare la propria influenza e il proprio impatto
- Comunicare con il team per restare aggiornati, sollecitare input e creare coesione e consenso
- Archiviare e condividere file all'interno e all'esterno dell'organizzazione per collaborare facilmente nell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Rileva problemi e protezione contro le minacce esterne 
- Monitoraggio, report e analizzare l'attività per rispondere immediatamente per garantire la sicurezza dell'organizzazione
- Supportare l'organizzazione con privacy e conformità avanzate per soddisfare il regolamento generale sulla protezione dei dati (GDPR)

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Risultato
Un elenco di scenari di Exchange Online che consente di risolvere le esigenze dell'organizzazione per la comunicazione e di pianificazione e collaborazione di breve durata.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In questa fase, pianificare gli aspetti tecnici di una distribuzione di Exchange Online e avviare attuare a gruppi di utenti selezionati.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Prerequisiti: Configurazione di accesso di identità e il dispositivo

Per proteggere l'accesso alle cassette postali di Exchange Online, verificare di aver configurato [identity e il dispositivo le regole di accesso](identity-access-policies.md) e [consigliati i criteri di accesso Exchange Online](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Passaggio 1: completare la pianificazione tecnica

Prima di iniziare la pianificazione tecnici, determinare se si desidera utilizzare FastTrack. Se l'organizzazione dispone di più di 50 postazioni e fa parte di un [piano idoneo](https://technet.microsoft.com/library/dn783224.aspx), è possibile utilizzare [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponibile all'indirizzo senza costi aggiuntivi per eseguire i passaggi di pianificazione, distribuzione e adozione di servizio. In alternativa, è possibile completare il lavoro familiarità con le procedure guidate Onboarding FastTrack, che sono state realizzate da [FastTrack](https://fasttrack.microsoft.com/) una volta che si accede con l'account di Office 365.

Se si sta eseguendo la propria pianificazione o in combinazione con FastTrack, è necessario determinare se la rete e l'organizzazione è pronte per Exchange Online. È particolarmente importante soddisfano i criteri di uscita per la rete all'interno dell'infrastruttura di base, con particolare attenzione a larghezza di banda Internet, velocità effettiva e ritardi traffico per ottimizzare le prestazioni per il traffico aggiuntivo per Exchange Posta elettronica in linea di base e gli allegati.

Utilizzare le risorse per preparare gli aspetti tecnici di un'implementazione di Exchange Online: 

- [Modalità di migrazione della posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- [Advisor migrazione della posta di Office 365](https://portal.office.com/onboarding/mailsetupadvisor#/) (deve essere eseguito l'accesso alla sottoscrizione Office 365)
- [Collaborazione in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatari in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Per una migliore comprensione della protezione in Exchange Online, vedere le risorse seguenti:

- [Autorizzazioni in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Sicurezza e conformità per Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Protezione antispam e antimalware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Successivamente, utilizzare le risorse per acquisire familiarità con gestione delle cassette postali Exchange Online:

- [Creare cassette postali degli utenti in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Gestire le cassette postali degli utenti](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Creazione e gestione dei gruppi di distribuzione](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Risultato

Si acquisire familiarità con gestione, protezione e la migrazione delle cassette postali e pronti iniziare a distribuzione Exchange Online a gruppi selezionati nella propria organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Nella maggior parte delle organizzazioni di medie e grandi dimensioni, è necessario eseguire un'implementazione pilota con le parti interessate dalla fase 1 e appassionati di informatica. Durante la fase pilota:

- Scegliere uno scenario business Exchange Online in cui è possono practice partecipanti pilota IT.
- Assegnare licenze di Office 365 partecipanti pilota e migrare le cassette postali locali a Exchange Online.
- Fornire una serie di esercitazioni di posta elettronica di Exchange Online, la pianificazione e altre funzionalità di test pilota partecipanti.
- Determinare la strategia di gestione di modifica e produrre materiale per stimolarne l'adozione utente a livello di organizzazione di Exchange Online. Modifica gestione materiali possono includere testo annuncio di posta elettronica, piani di formazione interni, poster aziendale e le presentazioni. Questi materiali verranno segnalare l'organizzazione Exchange Online e i relativi vantaggi con gli obiettivi di rilevamento della generazione e sull'utilizzo che gestisce. Vedere l'articolo [Modifica strategia di gestione per team di Microsoft](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) per ulteriori suggerimenti.
- Disporre i partecipanti pilota IT esaminare i materiali gestione cambia in base alla loro esperienza. Forniscono suggerimenti sulle procedure consigliate e consigli su come meglio descrivono i vantaggi di Exchange Online e su come utilizzarlo per la comunicazione e la pianificazione.

#### <a name="result"></a>Risultato

Progetto pilota di Exchange Online per è stata completata e materiali di gestione di modifica iniziale sviluppati, rivisto e aggiornati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: implementazione in un gruppo aziendale

Dopo aver completato il pilot IT, è possibile distribuire Exchange Online a un gruppo aziendale o un reparto all'interno dell'organizzazione. Se l'organizzazione utilizza un servizio di posta elettronica locale, ad esempio Server di Exchange, questa distribuzione è costituita da migrazione delle cassette postali. Implementazione in questione deve includere:

- Identificazione di scenari aziendali principali per Exchange Online all'interno del gruppo di business.
- Attività degli annunci per informare gli utenti delle aspettative e sequenza temporale per l'utilizzo di Exchange Online per i reparti e team di lavoro o del progetto.
- Migrazione delle cassette postali locali dei membri del gruppo aziendale a Exchange Online.
- Fornitura di formazione su Exchange Online o collegamenti a risorse per introdurre Exchange Online e su come utilizzarlo.
- Un meccanismo di feedback, ad esempio un team Microsoft Teams centrale contenente tutti i membri del gruppo aziendale, per raccogliere commenti e agire sui problemi degli utenti del gruppo aziendale.

Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale sia attivo e in esecuzione con Exchange Online e i materiali di gestione modifiche sono stati testati e notte.

## <a name="phase-3-drive-value"></a>Fase 3: aumentare il valore

In questa fase, eseguire la distribuzione di Exchange Online e supportare gli utenti per migliorare la relativa vantaggi.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Passaggio 1: È possibile distribuire Exchange Online per il resto dell'organizzazione

L'implementazione nel resto dell'organizzazione deve includere:

- Identificazione di scenari aziendali principali per Exchange Online all'interno dei gruppi aziendali separate.
- Utilizzo della sequenza temporale per l'utilizzo di Exchange Online e i materiali gestione cambia dettagliati per le attività di annuncio informare l'organizzazione delle aspettative.
- Migrazione delle cassette postali per il resto dell'organizzazione di Exchange Online.
- Fornitura di formazione su Exchange Online o forniti i collegamenti a risorse per introdurre Exchange Online e su come utilizzarlo.
- Un meccanismo di commenti e suggerimenti come, ad esempio, Team centrale che contiene tutti gli altri, per raccogliere commenti e problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato

L'organizzazione sia attivo ed è in esecuzione e la strategia di gestione di modifica sul posto di informare, formazione e consentire agli utenti di utilizzare Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo la distribuzione Exchange Online per l'intera organizzazione, è necessario continuare a utilizzare i caratteri della strategia di gestione di modifica per:

- Dispone il leader promuovere Exchange Online come strumento principale per le comunicazioni di breve durata e singoli e pianificazione.
- Invitare persone da utilizzare per gruppo aziendale, reparto, work e comunicazioni tra team, calendario e collaborazione di project.

Ecco alcune attività suggerite:

- Vedere [Linee guida sull'adozione di Office 365](https://aka.ms/successfactors) per informazioni sulle procedure consigliate generali relative all'adozione di servizi cloud. 
- Vedere i [report attività di Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) per comprendere l'utilizzo del servizio di Office 365 nell'organizzazione. Se non si è un amministratore globale di Office 365 per l'organizzazione, chiedere a qualcun altro le autorizzazioni Lettore report per poter accedere ai report attività.
- Monitorare l'ambito della commenti e suggerimenti (un canale pubblico in un team di team o di Yammer centrale) per i problemi e commenti dei singoli utenti sulle proprie esperienze con Exchange Online. Risolvere rapidamente è possibile evitare riesca singoli utenti e viene illustrato il supporto per la distribuzione di domande e problemi.
- Identificare e coltivare e rafforzare champions in ogni categoria business ed evidenziare i risultati e le procedure consigliate con Exchange Online. Riflettono i successi fuori all'organizzazione di visualizzare l'adozione e la riuscita del progetto. Visto responsabili tecnici all'interno di un gruppo aziendale può esercitare un fattore determinante su coordinatori e forme di pari livello.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato Exchange Online come strumento di pianificazione e la comunicazione tramite gruppi di singoli e piccole primario di breve durata.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per informazioni su come la società la migrazione a Exchange Online e utilizza Exchange Online Protection per la protezione da attacchi cyber comparsa all'interno di Microsoft, vedere:

- [Microsoft esegue la migrazione di 150.000 cassette postali a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft utilizza l'intelligence per le minacce per proteggere, rilevare e rispondere alle minacce](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft contrasta i tentativi di phishing con Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Passaggi successivi

Consultare queste risorse per la manutenzione di Exchange Online:

- [Interfaccia di amministrazione di Exchange in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Monitoraggio, report e traccia dei messaggi in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Back up della posta elettronica in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
