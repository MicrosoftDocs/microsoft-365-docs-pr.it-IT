---
title: Panoramica dell'analisi e della risposta automatizzata (AIR)
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
keywords: risposta agli incidenti automatici, analisi, correzione, protezione dalle minacce
ms.date: 09/29/2020
description: Ottenere una panoramica delle funzionalità di ricerca e risposta automatizzate in Microsoft Defender per Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 850291966c2f2da51782d8e70de23ff4f06d6136
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413963"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Panoramica dell'analisi automatizzata e della risposta (AIR) in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Quando vengono attivati gli avvisi di sicurezza, spetta al team delle operazioni di sicurezza esaminare gli avvisi e procedere per proteggere l'organizzazione. A volte, i team delle operazioni di sicurezza possono sentirsi sopraffatti dal volume degli avvisi attivati. Le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 possono essere utili. 

AIR consente al team di operazioni di sicurezza di operare in modo più efficiente ed efficace. Le funzionalità AEREe includono processi di analisi automatizzati in risposta a minacce ben note che esistono oggi. Le azioni correttive appropriate attendono l'approvazione, consentendo al team di operazioni di sicurezza di rispondere alle minacce rilevate. 

In questo articolo viene fornita una panoramica di AIR. Quando si è pronti per iniziare a usare AIR, vedere [indagare e rispondere automaticamente alle minacce](office-365-air.md).

## <a name="at-a-high-level"></a>Ad alto livello

Quando gli avvisi vengono attivati, i PlayBook di sicurezza entrano in vigore. A seconda della situazione, è possibile avviare un [processo di analisi automatizzato](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) . Durante e dopo un'indagine automatizzata, è consigliabile utilizzare le [operazioni di correzione](air-remediation-actions.md) . Nessuna azione viene eseguita automaticamente in Microsoft Defender per Office 365. Le revisioni del team per le operazioni di sicurezza, quindi [approva o rifiuta ogni azione di correzione](air-review-approve-pending-completed-actions.md). Dopo aver approvato o rifiutato tutte le azioni successive all'analisi, l'inchiesta è stata completata. Tutte queste attività sono registrate e visualizzabili nel centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ). Per ulteriori informazioni, vedere [visualizzare i dettagli di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation).

Nelle sezioni seguenti vengono fornite ulteriori informazioni sugli avvisi, gli schemi di sicurezza e gli esempi di aria in azione.

## <a name="alerts"></a>Avvisi

Gli [avvisi](../../compliance/alert-policies.md#viewing-alerts) rappresentano trigger per i flussi di lavoro del team di operazioni di sicurezza per la risposta agli incidenti. Definire la priorità del set di avvisi appropriato per l'analisi, assicurandosi che non vi siano minacce non indirizzate. Quando le indagini sugli avvisi vengono eseguite manualmente, i team delle operazioni di sicurezza devono cercare e correlare le entità (ad esempio, il contenuto, i dispositivi e gli utenti) a rischio di minacce. Tali attività e flussi di lavoro possono richiedere molto tempo e coinvolgere più strumenti e sistemi. Con AIR, l'analisi e la risposta per gli eventi di sicurezza vengono automatizzati grazie alla sicurezza degli avvisi e alla gestione delle minacce che attivano automaticamente gli schemi di risposta alla sicurezza. 

Attualmente per l'aria, gli avvisi generati dai seguenti tipi di criteri di avviso vengono analizzati automaticamente:  

- È stato rilevato un clic URL potenzialmente dannoso
- Messaggi di posta elettronica segnalati dall'utente come phishing`*`
- Messaggi di posta elettronica contenenti malware rimossi dopo il recapito`*`
- Messaggi di posta elettronica contenenti gli URL di phishing rimossi dopo il recapito`*`
- Modelli di invio di messaggi di posta elettronica sospetti
- Utente con limitazioni all'invio di posta elettronica
- Indagine manuale dell'amministratore attivato per la posta elettronica`*`

> [!NOTE]
> Agli avvisi contrassegnati da un asterisco ( `*` ) viene assegnata una gravità *informativa* nei rispettivi criteri di avviso all'interno del centro sicurezza Microsoft 365, con le notifiche di posta elettronica disattivate. Le notifiche tramite posta elettronica possono essere attivate tramite la [configurazione del criterio di avviso](../../compliance/alert-policies.md#alert-policy-settings). 

Per visualizzare gli avvisi, nel centro sicurezza & conformità scegliere **avvisi**  >  **Visualizza avvisi**. Selezionare un avviso per visualizzare i dettagli, quindi utilizzare il collegamento **Visualizza analisi** per passare all' [analisi](air-view-investigation-results.md#investigation-graph)corrispondente.  

> [!NOTE]
> Gli avvisi informativi sono nascosti nella visualizzazione avviso per impostazione predefinita. Per visualizzarli, modificare il filtro degli avvisi per includere gli avvisi informativi.

Se l'organizzazione gestisce gli avvisi di sicurezza tramite un sistema di gestione degli avvisi, un sistema di gestione dei servizi o un sistema di gestione degli eventi (SIEM), è possibile inviare avvisi a tale sistema tramite la notifica tramite posta elettronica o tramite l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Le notifiche degli avvisi di analisi tramite posta elettronica o API includono collegamenti per accedere agli avvisi nel centro sicurezza Microsoft 365, consentendo all'amministratore della sicurezza assegnato di passare rapidamente all'indagine.

![Avvisi relativi al collegamento alle indagini](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Schemi di sicurezza

Gli schemi di sicurezza sono criteri di back-end che sono al centro dell'automazione in Microsoft Defender per Office 365 e Microsoft Threat Protection. Gli schemi di sicurezza forniti in AIR sono basati su scenari comuni di sicurezza del mondo reale e sviluppati in base ai commenti e suggerimenti dei team di operazioni di sicurezza. Una sicurezza PlayBook viene avviata automaticamente quando vengono attivati avvisi specifici all'interno dell'organizzazione. Dopo che l'avviso è stato attivato, l'oggetto PlayBook associato viene eseguito dal sistema di analisi e risposta automatizzato. L'analisi analizza l'avviso in base al Playbook di quel particolare avviso, analizzando tutti i metadati associati (compresi messaggi di posta elettronica, utenti, soggetti, mittenti e così via). In base ai risultati dell'indagine del PlayBook, AIR consiglia una serie di azioni che il team di sicurezza dell'organizzazione può intraprendere per controllare e mitigare la minaccia. 

Gli schemi di sicurezza che otterrete con AIR sono studiati per affrontare le minacce più frequenti che le organizzazioni incontrano oggi con la posta elettronica. Sono basati sull'input dalle operazioni di sicurezza e dai team di risposta agli incidenti, compresi quelli che aiutano a difendere Microsoft e le risorse dei clienti.

- Messaggio phishing visualizzato dall'utente
- URL-fare clic su modifica verdetto
- Malware rilevato dopo il recapito (ZAP malware)
- Phishing rilevato dopo il recapito dello ZAP (phishing ZAP)
- Utente segnalato come compromesso 
- Ricerca di messaggi di posta elettronica manuale (attivato dall'amministratore da malware Explorer, phishing o tutte le visualizzazioni di posta elettronica)

Altri PlayBook e gli aggiornamenti di PlayBook verranno rilasciati Man mano che sono stati completati. Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cos'altro è pianificato e disponibile a breve.

### <a name="playbooks-include-investigation-and-recommendations"></a>I PlayBook includono analisi e suggerimenti

In AIR, ogni PlayBook di sicurezza include: 

- un'analisi radice delle entità di un messaggio di posta elettronica, ad esempio file, URL, destinatari, indirizzi IP e altro ancora.
- ulteriore ricerca di messaggi di posta elettronica simili ricevuti dall'organizzazione 
- passaggi necessari per identificare e correlare altre potenziali minacce e 
- azioni di correzione delle minacce consigliate.

Ogni passaggio di alto livello include una serie di passaggi che vengono eseguiti per fornire una risposta profonda, dettagliata ed esaustiva alle minacce.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Esempio: un messaggio di phishing riferito dall'utente avvia un playbook di analisi

Si supponga che un utente dell'organizzazione riceva un messaggio di posta elettronica che ritengono essere un tentativo di phishing. L'utente, addestrato a segnalare tali messaggi, utilizza il [componente aggiuntivo segnala messaggio](enable-the-report-message-add-in.md) per inviarlo a Microsoft per l'analisi. L'invio viene inviato anche al sistema ed è visibile in Esplora nella visualizzazione **invii** (in precedenza denominato visualizzazione **segnalata dall'utente** ). Inoltre, il messaggio visualizzato dall'utente ora attiva un avviso informativo basato sul sistema, che avvia automaticamente il PlayBook di analisi.

Durante la fase di analisi radice, vengono valutati vari aspetti del messaggio di posta elettronica. Tra questi aspetti sono inclusi:

- Determinazione del tipo di minaccia che potrebbe essere;
- Chi lo ha inviato;
- In cui è stato inviato il messaggio di posta elettronica (infrastruttura di invio);
- Se sono state recapitate o bloccate altre istanze del messaggio di posta elettronica;
- Una valutazione dei nostri analisti;
- Se il messaggio di posta elettronica è associato a qualsiasi campagna Nota;
- e altro ancora.

Dopo aver completato l'analisi radice, il PlayBook fornisce un elenco delle azioni consigliate da intraprendere sul messaggio di posta elettronica originale e le entità ad esso associate.
  
Successivamente, vengono eseguiti diversi passaggi di indagine e di ricerca di minacce:

- I messaggi di posta elettronica simili vengono identificati tramite ricerche cluster di posta elettronica.
- Il segnale viene condiviso con altre piattaforme, ad esempio [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Si determina se gli utenti hanno fatto clic su eventuali collegamenti dannosi nei messaggi di posta elettronica sospetti.
- Viene effettuato un controllo tramite Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) e Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.
- Viene effettuato un controllo per verificare se un utente è stato compromesso. Questa verifica utilizza i segnali di Office 365, [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security)e [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlando eventuali anomalie relative alle attività degli utenti.

Durante la fase di caccia, i rischi e le minacce sono assegnati a vari passaggi di caccia. 

La correzione è la fase finale del PlayBook. Durante questa fase, vengono eseguite le operazioni di correzione, in base alle fasi di ricerca e caccia. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Esempio: un amministratore della sicurezza attiva un'indagine da Esplora minacce

Oltre alle indagini automatizzate attivate da un avviso, il team delle operazioni di sicurezza dell'organizzazione può attivare un'analisi automatizzata da una visualizzazione in [Esplora minacce](threat-explorer.md).  Questa indagine crea anche un avviso, in modo che gli incidenti di Microsoft Defender e gli strumenti di SIEM esterni possano vedere che questa indagine è stata attivata. 

Si supponga, ad esempio, di utilizzare la visualizzazione **antimalware** in Esplora risorse. Utilizzando le schede sotto il grafico, è possibile selezionare la scheda **posta elettronica** . Se si seleziona uno o più elementi nell'elenco, viene attivato il pulsante **+ Actions** . 

![Esplora risorse con i messaggi selezionati](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Utilizzando il menu **azioni** , è possibile selezionare **Avvia analisi**.

![Menu azioni per i messaggi selezionati](../../media/explorer-malwareview-selectedemails-actions.jpg)

Analogamente ai PlayBook attivati da un avviso, le indagini automatiche che vengono attivate da una visualizzazione in Esplora risorse includono un'analisi radice, procedure per identificare e correlare le minacce e le azioni consigliate per attenuare tali minacce.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Esempio: un team di operazioni di sicurezza integra l'aria con i propri SIEM utilizzando l'API di gestione delle attività di Office 365

Le funzionalità AEREe in Microsoft Defender per Office 365 includono [rapporti & dettagli che i](air-view-investigation-results.md) team delle operazioni di sicurezza possono utilizzare per monitorare e risolvere le minacce. Tuttavia, è anche possibile integrare le funzionalità AEREe con altre soluzioni. Tra gli esempi sono inclusi un sistema di gestione delle informazioni e di gestione eventi (SIEM), un System Management case o una soluzione per la creazione di report personalizzati. Questo tipo di integrazione può essere effettuato utilizzando l'API di [attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Ad esempio, di recente, un'organizzazione ha configurato un modo per il team delle operazioni di sicurezza per visualizzare gli avvisi di phishing segnalati dall'utente già elaborati in base all'aria. La soluzione integra avvisi rilevanti con il server SIEM dell'organizzazione e il sistema di gestione dei casi. La soluzione riduce notevolmente il numero di falsi positivi, in modo che il team delle operazioni di sicurezza possa concentrare il proprio tempo e lo sforzo su minacce effettive. Per ulteriori informazioni su questa soluzione personalizzata, vedere [Tech Community Blog: migliorare l'efficacia del SOC con Office 365 ATP e l'API di gestione di O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Passaggi successivi

- [Iniziare a usare AIR](office-365-air.md)

- [Visitare la roadmap di Microsoft 365 per vedere cosa è stato pianificato e rilasciarlo presto](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Informazioni su ulteriori funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
