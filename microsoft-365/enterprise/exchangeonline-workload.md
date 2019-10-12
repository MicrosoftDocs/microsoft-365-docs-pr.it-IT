---
title: Distribuire Exchange Online per Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Eseguire il processo di pianificazione, implementazione e guida del valore di Exchange online in Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453862"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Distribuire Exchange Online per Microsoft 365 Enterprise

*Questo carico di lavoro è incluso sia nelle versioni E3 che E5 di Microsoft 365 Enterprise*

Exchange Online è il servizio cloud principale per la posta elettronica e il calendario che consente agli utenti di collaborare in modalità che non richiedono chat in tempo reale o spazio di archiviazione centralizzato dei documenti. Exchange Online è un elemento chiave del valore costruito per il lavoro di squadra di Microsoft 365 Enterprise. Exchange Online consente di ottenere ulteriori informazioni e di lavorare in modo più efficace con l'applicazione Outlook ben nota, indipendentemente dal dispositivo in uso.

Exchange Online include anche funzionalità avanzate di sicurezza, tra cui il filtro antimalware e della posta indesiderata per proteggere le cassette postali e le funzionalità di prevenzione della perdita dei dati, per impedire agli utenti di inviare per errore informazioni riservate a persone non autorizzate. La sicurezza di Exchange Online è un elemento chiave del valore di sicurezza intelligente di Microsoft 365 Enterprise.

Se non si ha familiarità con Exchange Online, vedere [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Nelle fasi e nei passaggi seguenti viene illustrato il processo di definizione del ruolo di Exchange Online nell'organizzazione, l'onboarding dell'organizzazione a Exchange Online tramite una serie di graduali progressivi e l'utilizzo della Guida di Exchange Online e del relativo valore per gli utenti finali.

>[!Note]
>Queste istruzioni per la distribuzione devono essere seguite solo dopo aver completato [la fase 2-Identity dell'infrastruttura di Microsoft 365 Enterprise Foundation](identity-infrastructure.md).
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fase 1: immaginare la distribuzione di Exchange Online

In questa fase, si raccolgono gli utenti per la distribuzione di Exchange Online e si determina il modo in cui l'organizzazione utilizzerà Exchange Online per soddisfare le proprie esigenze aziendali.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Passaggio 1: raccogliere i membri della distribuzione di Exchange Online

Per una distribuzione di Exchange Online con esito positivo sulla [fase 2-identità](identity-infrastructure.md) dell'infrastruttura di Microsoft 365 Enterprise Foundation, è necessario raccogliere gli utenti giusti per gli input e i commenti e suggerimenti. Le persone principali includono responsabili decisionali aziendali, personale IT come architetti e implementatori e sostenitori per gli utenti finali. 

Questi tre gruppi assicurano che la distribuzione di Exchange Online includa considerazioni che soddisfano le esigenze aziendali, gli aspetti tecnici della migrazione delle cassette postali e la sicurezza e che il risultato è qualcosa che utilizzerà gli utenti tipici.

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

Prima di avviare la pianificazione tecnica, stabilire se si intende usare FastTrack. Se l'organizzazione ha più di 50 seggi e partecipa a un [piano idoneo](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), è possibile utilizzare [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *disponibile senza costi aggiuntivi* per guidare l'utente attraverso la pianificazione, la distribuzione e l'adozione dei servizi. In alternativa, è possibile completare autonomamente queste operazioni utilizzando le procedure guidate di onboarding FastTrack, disponibili in [FastTrack](https://fasttrack.microsoft.com/) quando si esegue l'accesso con l'account Microsoft 365.

Se si sta eseguendo la propria pianificazione o in combinazione con FastTrack, è necessario determinare se la rete e l'organizzazione sono pronte per Exchange Online. È particolarmente importante che vengano soddisfatti i criteri di uscita per la [rete nell'infrastruttura](networking-infrastructure.md) di base per gli utenti connessi alla rete dell'organizzazione. Prestare particolare attenzione alla larghezza di banda, alla velocità effettiva e ai ritardi del traffico di Internet per massimizzare le prestazioni per il traffico aggiuntivo per la posta elettronica e gli allegati basati su Exchange Online.

Utilizzare queste risorse per preparare gli aspetti tecnici di un'implementazione di Exchange Online: 

- [Modalità di migrazione della posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Eseguire la migrazione delle cartelle pubbliche di Exchange Server a Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Eseguire la migrazione delle cartelle pubbliche di Exchange Server ai gruppi di Office 365](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Collaborazione in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Destinatari in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook per iOS e Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

Per una migliore comprensione della sicurezza in Exchange Online, vedere le risorse seguenti:

- [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Sicurezza e conformità per Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Protezione antispam e antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

Successivamente, utilizzare queste risorse per comprendere la gestione delle cassette postali di Exchange Online:

- [Creare cassette postali degli utenti in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Gestire le cassette postali degli utenti](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Creazione e gestione dei gruppi di distribuzione](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Risultato

Si capisce che la migrazione, la sicurezza e la gestione delle cassette postali sono pronte per iniziare a eseguire la distribuzione di Exchange Online ai gruppi selezionati nell'organizzazione.

### <a name="step-2-run-an-it-pilot"></a>Passaggio 2: eseguire un'implementazione pilota

Per la maggior parte delle organizzazioni di medie e grandi dimensioni, è consigliabile eseguire un progetto pilota IT con le parti interessate dalla fase 1, dai primi adottanti e dagli appassionati di tecnologia. Durante la fase pilota:

- Fornire ai partecipanti pilota le licenze Microsoft 365 e migrare le cassette postali locali a Exchange Online.
- Offrire ai partecipanti piloti una serie di esercitazioni per testare la posta elettronica, la pianificazione e altre funzionalità di Exchange Online.
- Determinare la strategia di gestione delle modifiche e produrre materiali per guidare l'adozione da parte dell'utente a livello di organizzazione di Outlook ed Exchange Online. 
 
  I materiali per la gestione delle modifiche possono includere il testo dell'annuncio tramite posta elettronica, i piani di formazione interna, poster e presentazioni. Questi materiali informeranno l'organizzazione su Exchange Online e i suoi vantaggi con gli obiettivi di sensibilizzazione e utilizzo della guida. Per alcune idee, vedere l'articolo relativo alla [strategia di gestione delle modifiche per Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) .

- Fare in modo che i partecipanti al programma pilota IT prendano visione dei materiali per la gestione delle modifiche in base alle proprie esperienze. Sono in grado di fornire suggerimenti su procedure consigliate e consigli su come descrivere al meglio i vantaggi di Outlook ed Exchange Online e su come utilizzarlo per la comunicazione e la pianificazione.

#### <a name="result"></a>Risultato

Il pilota IT di Exchange Online è completo e i materiali di gestione delle modifiche iniziali sono stati sviluppati, rivisti e perfezionati.

### <a name="step-3-roll-out-to-a-business-group"></a>Passaggio 3: eseguire l'implementazione in un gruppo aziendale

Dopo aver completato il pilota IT, eseguire l'implementazione di Exchange online in un gruppo o reparto aziendale dell'organizzazione. Se l'organizzazione utilizza un servizio di posta elettronica locale, ad esempio Exchange Server, questa implementazione è costituita dalla migrazione delle cassette postali. L'implementazione deve includere:

- Identificazione degli scenari aziendali chiave per Exchange Online all'interno del gruppo aziendale.
- Attività di annuncio per informare gli utenti delle aspettative e delle sequenze temporali per l'utilizzo di Exchange Online per i reparti e i team di lavoro o di progetto.
- La migrazione delle cassette postali locali dei membri del gruppo aziendale a Exchange Online.
- Fornire [formazione utente](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) su Outlook o collegamenti a risorse per introdurre Outlook e come utilizzarlo.
- Un meccanismo di feedback, ad esempio un team Microsoft Teams centrale contenente tutti i membri del gruppo aziendale, per raccogliere commenti e agire sui problemi degli utenti del gruppo aziendale.

Durante l'implementazione, è possibile perfezionare i materiali di gestione delle modifiche in preparazione dell'implementazione a livello dell'organizzazione.

#### <a name="result"></a>Risultato

Un gruppo aziendale è attivo e in esecuzione con Outlook ed Exchange Online e i materiali di gestione delle modifiche sono stati testati e perfezionati.

## <a name="phase-3-drive-value"></a>Fase 3: promuovere il valore

In questa fase, è possibile completare l'implementazione di Exchange Online e supportare gli utenti per aiutarli a realizzare i propri vantaggi.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Passaggio 1: implementazione di Exchange Online per il resto dell'organizzazione

L'implementazione nel resto dell'organizzazione deve includere:

- Identificazione degli scenari aziendali chiave per Exchange Online all'interno di gruppi aziendali distinti.
- Utilizzo dei materiali di gestione delle modifiche raffinati per le attività di annuncio per informare l'organizzazione delle aspettative e delle sequenze temporali per l'utilizzo di Exchange Online.
- La migrazione delle cassette postali per il resto dell'organizzazione a Exchange Online.
- Offrire la [formazione degli utenti](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) in Outlook o fornire collegamenti alle risorse per introdurre Outlook e come utilizzarlo.
- Un meccanismo di commenti e suggerimenti come, ad esempio, Team centrale che contiene tutti gli altri, per raccogliere commenti e problemi degli utenti dell'organizzazione. Se l'organizzazione ha meno di 2500 utenti, è possibile usare un canale pubblico in Teams. In caso contrario, è possibile usare un gruppo pubblico in Yammer.

#### <a name="result"></a>Risultato

L'organizzazione è in esecuzione e la strategia di gestione delle modifiche è in atto per informare, formare e consentire agli utenti di utilizzare Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Passaggio 2: misurare l'utilizzo, gestire la soddisfazione e favorire l'adozione

Dopo aver eseguito l'implementazione di Exchange Online all'intera organizzazione, è necessario continuare a utilizzare la strategia di gestione delle modifiche per eseguire le operazioni seguenti:

- Fare in modo che la leadership promuova Exchange Online come strumento principale per la comunicazione e la pianificazione individuali e di breve durata.
- Incoraggiare gli utenti a usarlo per le comunicazioni, il calendario e la collaborazione di team di business, di reparto, di lavoro e di progetto.

Ecco alcune attività suggerite:

- Vedere [Fattori di successo per Office 365](https://aka.ms/successfactors) per informazioni sulle procedure consigliate generali relative all'adozione di servizi cloud. 
- Vedere i [report attività di Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) per comprendere l'utilizzo del servizio di Office 365 nell'organizzazione. Se non si è un amministratore globale di Office 365 per l'organizzazione, chiedere a qualcun altro le autorizzazioni Lettore report per poter accedere ai report attività.
- Monitorare la sede dei commenti e suggerimenti (un canale pubblico di un team o un Yammer di team centrale) per problemi e commenti e suggerimenti da parte di utenti in merito alle proprie esperienze con Exchange Online. Rispondere alle domande e ai problemi nel più breve tempo possibile per evitare che gli utenti siano frustrati e dimostrare il supporto per l'implementazione.
- Identificare e alimentare i campioni di ogni gruppo aziendale ed evidenziare le procedure consigliate tramite Outlook. Far conoscere i loro risultati all'interno dell'organizzazione per dimostrare il successo del progetto e l'adozione. L'approvazione da parte dei responsabili tecnici all'interno di un gruppo aziendale può esercitare un'influenza potente su leader e coetanei.

#### <a name="result"></a>Risultato

L'organizzazione ha adottato Exchange Online e Outlook come principale strumento di comunicazione e pianificazione di breve durata per singoli e gruppi di piccole dimensioni.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per sbirciare all'interno di Microsoft e scoprire come è stata eseguita la migrazione a Exchange Online e utilizzando Exchange Online Protection per proteggersi dagli attacchi informatici, vedere:

- [Microsoft esegue la migrazione di 150.000 cassette postali a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft utilizza l'intelligence per le minacce per proteggere, rilevare e rispondere alle minacce](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft contrasta i tentativi di phishing con Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Passaggi successivi

Vedere queste risorse per la manutenzione in esecuzione di Exchange Online:

- [Interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Monitoraggio, creazione di rapporti e traccia dei messaggi in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Back up della posta elettronica in Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
