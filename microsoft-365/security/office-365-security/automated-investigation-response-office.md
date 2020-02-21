---
title: Indagine automatizzata e risposta (AIR) in Office 365
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
ms.collection: M365-security-compliance
description: Ottenere una panoramica delle funzionalità di ricerca e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 8f781687047f39d4d038e293e50c9caad83d051a
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179247"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Indagine automatizzata e risposta (AIR) in Office 365

Quando vengono attivati gli avvisi di sicurezza, spetta al team delle operazioni di sicurezza esaminare gli avvisi e procedere per proteggere l'organizzazione. A volte, i team delle operazioni di sicurezza possono sentirsi sopraffatti dal volume degli avvisi attivati. L'analisi automatizzata e le funzionalità di risposta (aria) in Office 365 possono essere utili. AIR consente al team di operazioni di sicurezza di operare in modo più efficiente ed efficace. Le funzionalità AEREe includono processi di analisi automatizzati in risposta a minacce ben note che esistono oggi. Le azioni correttive appropriate attendono l'approvazione, consentendo al team di operazioni di sicurezza di rispondere alle minacce rilevate. 

In questo articolo viene fornita una panoramica di AIR e dei relativi componenti. Quando si è pronti per iniziare a usare AIR, vedere [indagare e rispondere automaticamente alle minacce in Office 365](office-365-air.md).

> [!TIP]
> Si possiedono Microsoft 365 E5 o Microsoft 365 E3 con identità e protezione dalle minacce? È consigliabile provare [Microsoft Threat Protection](../mtp/microsoft-threat-protection.md).

## <a name="at-a-high-level"></a>Ad alto livello

Quando gli avvisi vengono attivati, i PlayBook di sicurezza entrano in vigore. A seconda della situazione, è possibile avviare un [processo di analisi automatizzato](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) . Durante e dopo un'indagine automatizzata, è consigliabile utilizzare le [operazioni di correzione](air-remediation-actions.md) . Nessuna azione viene eseguita automaticamente in Office 365 Advanced Threat Protection. Le revisioni del team di sicurezza Operations, quindi [approva o rifiuta ogni azione di correzione](air-remediation-actions.md#approve-or-reject-pending-actions)e, al termine, vengono completate le indagini. Tutte queste attività sono registrate e visualizzabili nel centro sicurezza & conformità di Office 365 (vedere [visualizzare i dettagli di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation)).

Nelle sezioni seguenti vengono fornite ulteriori informazioni sugli avvisi, gli schemi di sicurezza e gli esempi di aria in azione.

## <a name="alerts"></a>Avvisi

Gli [avvisi](../../compliance/alert-policies.md#viewing-alerts) rappresentano trigger per i flussi di lavoro del team di operazioni di sicurezza per la risposta agli incidenti. Definire la priorità del set di avvisi appropriato per l'analisi, assicurandosi che non vi siano minacce non indirizzate. Quando le indagini sugli avvisi vengono eseguite manualmente, i team delle operazioni di sicurezza devono cercare e correlare le entità (ad esempio, il contenuto, i dispositivi e gli utenti) a rischio di minacce. Tali attività e flussi di lavoro possono richiedere molto tempo e coinvolgere più strumenti e sistemi. Con AIR, l'analisi e la risposta per gli eventi di sicurezza di Office 365 vengono automatizzati tramite gli avvisi di sicurezza e di gestione delle minacce che attivano automaticamente gli schemi di risposta alla sicurezza. 

Attualmente per l'aria, gli avvisi generati dai seguenti tipi di criteri di avviso vengono analizzati automaticamente:  

- È stato rilevato un clic URL potenzialmente dannoso
- Messaggi di posta elettronica segnalati dall'utente come phishing *
- Messaggi di posta elettronica contenenti malware rimossi dopo il recapito *
- Messaggi di posta elettronica contenenti gli URL di phishing rimossi dopo il recapito *
- Modelli di invio di messaggi di posta elettronica sospetti #
- Utente con limitazioni all'invio di posta elettronica #

> [!NOTE]
> Agli avvisi contrassegnati da un asterisco (*) viene assegnata una gravità *informativa* nei rispettivi criteri di avviso all'interno del centro sicurezza & conformità, con le notifiche di posta elettronica disattivate. Le notifiche tramite posta elettronica possono essere attivate tramite la [configurazione del criterio di avviso](../../compliance/alert-policies.md#alert-policy-settings). Gli avvisi contrassegnati con un hash (#) sono generalmente disponibili agli avvisi associati ai PlayBook di anteprima pubblica.

Per visualizzare gli avvisi, nel centro sicurezza & conformità scegliere **avvisi** > **Visualizza avvisi**. Selezionare un avviso per visualizzare i dettagli, quindi utilizzare il collegamento **Visualizza analisi** per passare all' [analisi](air-view-investigation-results.md#investigation-graph)corrispondente.  

> [!NOTE]
> Gli avvisi informativi sono nascosti nella visualizzazione avviso per impostazione predefinita. Per visualizzarli, modificare il filtro degli avvisi per includere gli avvisi informativi.

Se l'organizzazione gestisce gli avvisi di sicurezza tramite un sistema di gestione degli avvisi, un sistema di gestione dei servizi o un sistema di gestione eventi e informazioni di sicurezza, è possibile inviare avvisi di Office 365 a tale sistema tramite notifica tramite posta elettronica o tramite l' [API di gestione di office 365 Management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Le notifiche di avviso per l'analisi tramite posta elettronica o API includono collegamenti per accedere agli avvisi nel centro sicurezza & conformità, consentendo all'amministratore della sicurezza assegnato di passare rapidamente all'indagine.

![Avvisi relativi al collegamento alle indagini](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Schemi di sicurezza

Gli schemi di sicurezza sono criteri di back-end che sono al centro dell'automazione in Office Advanced Threat Protection e Microsoft Threat Protection. Gli schemi di sicurezza forniti in AIR sono basati su scenari comuni di sicurezza del mondo reale e sviluppati in base ai commenti e suggerimenti dei team di operazioni di sicurezza. Una sicurezza PlayBook viene avviata automaticamente quando vengono attivati avvisi specifici all'interno dell'organizzazione. Dopo che l'avviso è stato attivato, l'oggetto PlayBook associato viene eseguito dal sistema di analisi e risposta automatico (AIR). L'analisi analizza l'avviso in base al Playbook di quel particolare avviso, analizzando tutti i metadati associati (compresi messaggi di posta elettronica, utenti, soggetti, mittenti e così via). In base ai risultati dell'indagine del PlayBook, AIR consiglia una serie di azioni che il team di sicurezza dell'organizzazione può intraprendere per controllare e mitigare la minaccia. 

Gli schemi di sicurezza che otterrete con AIR sono studiati per affrontare le minacce più frequenti che le organizzazioni incontrano oggi con la posta elettronica. Sono basati sull'input dalle operazioni di sicurezza e dai team di risposta agli incidenti, compresi quelli che aiutano a difendere Microsoft e le risorse dei clienti.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Gli schemi di sicurezza vengono implementati in fasi

Come parte di AIR, i PlayBook di sicurezza stanno per essere implementati in fasi. La fase 1 è ora generalmente disponibile e include diversi PlayBook che forniscono suggerimenti per le azioni che gli amministratori della sicurezza possono rivedere e approvare:
- Messaggio phishing visualizzato dall'utente
- URL fare clic su modifica verdetto
- Malware rilevato dopo il recapito (ZAP malware)
- Phishing rilevato dopo il recapito dello ZAP (phishing ZAP)

La fase 1 include anche il supporto per le indagini di posta elettronica attivate dall'amministratore (tramite [Esplora minacce](threat-explorer.md)).

La fase 2 è ora in corso con i seguenti PlayBook nell' **anteprima pubblica**, fornendo suggerimenti per le azioni e aiutando gli amministratori della sicurezza a esaminare i problemi:
- Utente segnalato come compromesso (anteprima pubblica)

Ulteriori PlayBook verranno rilasciati Man mano che sono stati completati. Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cos'altro è pianificato e disponibile a breve.

### <a name="playbooks-include-investigation-and-recommendations"></a>I PlayBook includono analisi e suggerimenti

In AIR, ogni PlayBook di sicurezza include: 
- analisi radice delle entità di un messaggio di posta elettronica (file, URL, destinatari, indirizzi IP e così via)
- ulteriore ricerca di messaggi di posta elettronica simili ricevuti dall'organizzazione 
- passaggi necessari per identificare e correlare altre potenziali minacce e 
- azioni di correzione delle minacce consigliate.

Ogni passaggio di alto livello include una serie di passaggi che vengono eseguiti per fornire una risposta profonda, dettagliata ed esaustiva alle minacce.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Esempio: un messaggio di phishing riferito dall'utente avvia un playbook di analisi

Quando un utente dell'organizzazione invia un messaggio di posta elettronica e lo segnala a Microsoft utilizzando il [componente aggiuntivo per i messaggi di report per Outlook o Outlook Web App](enable-the-report-message-add-in.md), il report viene inviato anche al sistema ed è visibile in Esplora nella visualizzazione segnalata dall'utente. Questo messaggio visualizzato dall'utente ora attiva un avviso informativo basato sul sistema, che avvia automaticamente il PlayBook di analisi.

Durante la fase di analisi radice, vengono valutati vari aspetti del messaggio di posta elettronica. Ad esempio:
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
- Il segnale viene condiviso con altre piattaforme, ad esempio [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Si determina se gli utenti hanno fatto clic su eventuali collegamenti dannosi nei messaggi di posta elettronica sospetti.
- Viene effettuato un controllo in Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) e Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.
- Viene effettuato un controllo per verificare se un utente è stato compromesso. Questa verifica utilizza i segnali di Office 365, [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security)e [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlando eventuali anomalie relative alle attività degli utenti. 

Durante la fase di caccia, i rischi e le minacce sono assegnati a vari passaggi di caccia. 

La correzione è la fase finale del PlayBook. Durante questa fase, vengono eseguite le operazioni di correzione, in base alle fasi di ricerca e caccia. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Esempio: un amministratore della sicurezza attiva un'indagine da Esplora minacce

Oltre alle indagini automatiche attivate da un avviso, il team delle operazioni di sicurezza dell'organizzazione può attivare un'analisi automatica da una visualizzazione in [Esplora minacce](threat-explorer.md).

Si supponga, ad esempio, di visualizzare i dati in Esplora informazioni sui messaggi segnalati dall'utente. È possibile selezionare un elemento nell'elenco dei risultati e quindi fare clic su **indaga** dal menu azione (supponendo che si disponga delle autorizzazioni di correzione appropriate).

![Messaggi segnalati dall'utente in Esplora con il pulsante indaga](../../media/Explorer-UserReported-Investigate.png)

Come un altro esempio, si supponga di visualizzare i dati relativi ai messaggi di posta elettronica rilevati come contenenti malware e che sono stati rilevati diversi messaggi di posta elettronica come contenenti malware. È possibile selezionare la scheda **posta elettronica** , selezionare uno o più messaggi di posta elettronica e quindi scegliere **indaga**dal menu **azioni** . 

![Avvio di un'indagine per malware in Esplora risorse](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Analogamente ai PlayBook attivati da un avviso, le indagini automatiche che vengono attivate da una visualizzazione in Esplora risorse includono un'analisi radice, procedure per identificare e correlare le minacce e le azioni consigliate per attenuare tali minacce.

## <a name="how-to-get-air"></a>Come ottenere aria

Office 365 AIR è incluso negli abbonamenti seguenti:

- Microsoft 365 E5
- Office 365 E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection (Piano 2)

Se non si dispone di una o più di queste sottoscrizioni, [avviare una versione di valutazione gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Per ulteriori informazioni sulla disponibilità delle funzionalità, visitare la [disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe

Le autorizzazioni vengono concesse tramite alcuni ruoli, ad esempio quelli descritti nella tabella seguente: 

|Attività |Ruoli necessari |
|--|--|
|Per impostare le caratteristiche dell'aria |Uno dei ruoli seguenti: <br/>- **Amministratore globale**<br/>- **Amministratore della sicurezza** <br/>Questi ruoli possono essere assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Per approvare o rifiutare le azioni consigliate|Uno dei ruoli seguenti, assegnato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):<br/>- **Amministratore globale** <br/>- **Amministratore della sicurezza**<br/>- **Lettore di sicurezza** <br/>--- e ---<br/>- **Search and Purge** (questo ruolo è assegnato solo nel [Centro sicurezza & conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Potrebbe essere necessario creare un nuovo gruppo di ruoli e aggiungere il ruolo Search and Purge a quel nuovo gruppo di ruoli.

## <a name="next-steps"></a>Passaggi successivi

- [Iniziare a usare AIR in Office 365](office-365-air.md)

- [Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita](https://www.microsoft.com/microsoft-365/roadmap?filters=)

