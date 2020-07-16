---
title: Attività rapide per iniziare a eseguire la conformità a Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Informazioni sulle attività che consentiranno di iniziare rapidamente a eseguire la conformità in Microsoft 365.
ms.openlocfilehash: a946d4711111089ba6074b2c264b8edd36a01315
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126615"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Attività rapide per iniziare a eseguire la conformità a Microsoft 365

Se si è nuovi a Microsoft 365 compliance e si chiede da dove iniziare, in questo articolo vengono fornite indicazioni sulle nozioni di base e vengono classificate in priorità importanti attività di conformità. In questo articolo vengono fornite informazioni utili per iniziare con la gestione e il monitoraggio dei dati, per proteggerli e ridurre al minimo i rischi Insider.

Questo articolo è utile anche per capire come gestire i rischi, proteggere i dati e restare conformi alle normative e agli standard con una nuova forza lavoro remota. I dipendenti collaborano e si connettono tra loro in modo nuovo e questo significa che potrebbe essere necessario adattare i processi e i controlli di conformità esistenti. L'identificazione e la gestione di questi nuovi rischi di conformità all'interno dell'organizzazione sono fondamentali per la salvaguardia dei dati e la riduzione al minimo delle minacce e dei rischi.

Dopo aver completato le attività di conformità di base, valutare la possibilità di espandere la copertura di conformità nell'organizzazione implementando soluzioni aggiuntive per la conformità a Microsoft 365.

## <a name="task-1-configure-compliance-permissions"></a>Attività 1: configurare le autorizzazioni di conformità

È importante gestire gli utenti dell'organizzazione che dispongono dell'accesso al centro conformità Microsoft 365 per visualizzare il contenuto ed eseguire le attività di gestione. Microsoft 365 fornisce ruoli amministrativi specifici per la conformità e per l'utilizzo degli strumenti inclusi nel centro conformità di Microsoft 365.

Iniziare assegnando le autorizzazioni di conformità agli utenti dell'organizzazione in modo che possano eseguire queste attività e impedire agli utenti non autorizzati di accedere a aree esterne alle proprie responsabilità. È necessario assicurarsi di aver assegnato le persone appropriate all' **amministratore dei dati di conformità** e ai ruoli amministratore di **conformità** prima di iniziare a configurare e implementare le soluzioni di conformità incluse in Microsoft 365. È inoltre necessario assegnare agli utenti il ruolo di lettura globale di Azure Active Directory per visualizzare i dati in Punteggio di conformità.

Per istruzioni dettagliate su come configurare le autorizzazioni e assegnare persone ai ruoli di amministratore, vedere [autorizzazioni nel centro sicurezza & conformità](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Attività 2: conoscere lo stato di conformità

È difficile sapere dove andare se non si conosce il luogo in cui si è. Se si soddisfano le esigenze di conformità, è necessario comprendere il livello di rischio corrente e gli aggiornamenti che possono essere necessari nei tempi di modifica. Se l'organizzazione è nuova ai requisiti di conformità o ha un'esperienza profonda con gli standard e i regolamenti che regolano l'industria, la cosa migliore che è possibile fare per migliorare la conformità è capire dove si trova l'organizzazione.

Il [Punteggio di conformità di Microsoft](compliance-score.md) può aiutare a capire la postura di conformità dell'organizzazione e le aree di evidenziazione che potrebbero essere utili. Punteggio di conformità utilizza un Dashboard centralizzato per calcolare un punteggio basato sui rischi, misurando i progressi compiuti nel completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi. È inoltre possibile utilizzare il Punteggio di conformità come strumento per tenere conto di tutte le valutazioni dei rischi. Offre funzionalità di flusso di lavoro che consentono di completare efficacemente le valutazioni dei rischi tramite uno strumento comune.

Per istruzioni dettagliate per iniziare a utilizzare il Punteggio di conformità, vedere [set up Compliance Score](compliance-score-setup.md).

>[!IMPORTANT]
>La sicurezza e la conformità sono strettamente integrate per la maggior parte delle organizzazioni. È importante che l'organizzazione affronti la sicurezza di base, la protezione dalle minacce e le aree di gestione delle identità e degli accessi per fornire un approccio di difesa approfondito alla sicurezza e alla conformità.
>
>Controllare il [Punteggio microsoft 365 Secure](../security/mtp/microsoft-secure-score.md) in Microsoft 365 Security Center e completare le attività descritte negli articoli seguenti:
>
> - [Roadmap sulla sicurezza-priorità principali per i primi 30 giorni, 90 giorni e oltre](../security/office-365-security/security-roadmap.md)
> - [Top 12 attività per i team di sicurezza per il supporto di lavoro da casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Attività 3: abilitare il controllo per l'organizzazione

Dopo aver determinato lo stato corrente dell'organizzazione e in grado di gestire le funzioni di conformità, il passaggio successivo consiste nel verificare di disporre dei dati per condurre indagini di conformità e generare report per le attività di rete e degli utenti nell'organizzazione. L'abilitazione del controllo è anche un prerequisito importante per le soluzioni di conformità descritte più avanti in questo articolo.

Gli approfondimenti forniti dal registro di controllo sono uno strumento valido per contribuire a soddisfare i requisiti di conformità per le soluzioni che consentono di gestire e monitorare le aree di conformità che devono essere migliorate. La registrazione di controllo deve essere abilitata prima che le attività vengano registrate e prima di poter eseguire una ricerca nel registro di controllo. Se attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni e fino a un anno, a seconda della licenza assegnata agli utenti.

Per istruzioni dettagliate su come abilitare il controllo, vedere [attivazione o disattivazione della ricerca del registro di controllo](turn-audit-log-search-on-or-off.md).

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Attività 4: creare criteri per avvisare l'utente sui potenziali problemi di conformità

Microsoft fornisce diversi criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore, l'attività antimalware, le potenziali minacce esterne e interne e i rischi di governance delle informazioni. Questi criteri sono attivati per impostazione predefinita, ma potrebbe essere necessario configurare avvisi personalizzati per consentire la gestione dei requisiti di conformità specifici dell'organizzazione.

Utilizzare i criteri di avviso e gli strumenti del dashboard di avviso per creare criteri di avviso personalizzati e visualizzare gli avvisi generati quando gli utenti eseguono attività che soddisfano le condizioni dei criteri. Alcuni esempi possono essere l'utilizzo di criteri di avviso per tenere conto delle attività degli utenti e degli amministratori che influiscono sui requisiti di conformità, sulle autorizzazioni e sulla perdita di dati nella propria organizzazione.

Per istruzioni dettagliate sulla creazione di criteri di avviso personalizzati, vedere Criteri di [avviso nel centro sicurezza e conformità](alert-policies.md).

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>Attività 5: configurare l'accesso just-in-time per gli amministratori

L'accesso permanente da parte di alcuni utenti a informazioni riservate o a impostazioni di configurazione di rete critiche è un percorso potenziale per gli account compromessi o le attività di minacce interne. La [gestione degli accessi con privilegi](privileged-access-management-overview.md) consente di proteggere l'organizzazione da violazioni e contribuisce a soddisfare le procedure consigliate per la conformità limitando l'accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche. Anziché gli amministratori che hanno accesso costante, le regole di accesso just-in-time vengono implementate per le attività che richiedono autorizzazioni elevate. L'abilitazione della gestione degli accessi con privilegi in Microsoft 365 consente all'organizzazione di operare con privilegi zero e di fornire un livello di difesa contro le vulnerabilità di accesso amministrativo permanenti.

Per informazioni dettagliate sulla configurazione della gestione degli accessi con privilegi, vedere [Introduzione alla gestione degli accessi con privilegi](privileged-access-management-configuration.md). Per informazioni sulle licenze per la gestione degli accessi con privilegi, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365).

## <a name="task-6-classify-and-protect-sensitive-data"></a>Attività 6: classificare e proteggere i dati sensibili

Per svolgere il proprio lavoro, i membri dell'organizzazione collaborano con altri utenti, sia interni che esterni all'organizzazione stessa. Questo significa che i contenuti non sono più protetti da un firewall, ma possono spostarsi tra dispositivi, applicazioni e servizi. E quando si spostano, è preferibile che lo facciano in modo sicuro e protetto, nel rispetto dei criteri aziendali e di conformità dell'organizzazione.

Le [etichette di riservatezza](sensitivity-labels.md) consentono di classificare e proteggere i dati dell'organizzazione, assicurando che la produttività degli utenti e la loro capacità di collaborare non vengano ostacolate. Utilizzare le etichette di riservatezza per applicare la crittografia e le restrizioni di utilizzo applicano le indicazioni visive e proteggono le informazioni tra piattaforme e dispositivi, in locale e nel cloud.

Per istruzioni dettagliate su come configurare e utilizzare le etichette di riservatezza, vedere [Introduzione alle etichette di riservatezza](get-started-with-sensitivity-labels.md). Per informazioni sulle licenze per le etichette di riservatezza, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-7-configure-a-retention-policy"></a>Attività 7: configurare un criterio di conservazione

Un [criterio di conservazione](retention.md) consente di decidere in modo proattivo se conservare il contenuto, eliminare il contenuto o entrambi: mantenere e quindi eliminare il contenuto al termine di un periodo di conservazione specificato. Tali azioni potrebbero essere necessarie per conformarsi alle normative industriali e ai criteri interni, oltre a ridurre i rischi in caso di controversia legale o violazione della sicurezza.

Quando il contenuto è soggetto a un criterio di conservazione, gli utenti possono continuare a modificare e utilizzare il contenuto come se nulla fosse cambiato. Il contenuto viene conservato sul posto, nella posizione originale. Tuttavia, se qualcuno modifica o Elimina il contenuto soggetto al criterio di conservazione, una copia del contenuto originale viene salvata in una posizione sicura in cui viene conservata mentre il criterio di conservazione per il contenuto è attivo.

È possibile inserire rapidamente un criterio di conservazione sul posto per più posizioni nell'ambiente Microsoft 365: posta elettronica di Exchange e cartelle pubbliche, siti di SharePoint, account di OneDrive e gruppi di Microsoft 365. Conosciuto come un criterio di conservazione a livello di organizzazione, non vi sono limiti al numero di cassette postali o di siti che il criterio può includere. Tuttavia, se è necessario ottenere maggiore specifica, è possibile farlo configurando un criterio di conservazione per posizioni specifiche e quindi includere o escludere siti o utenti.

Per istruzioni dettagliate per la configurazione di un criterio di conservazione, vedere [creare e configurare i criteri di conservazione](create-retention-policies.md). Per informazioni sulle licenze di gestione dei record, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management).

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>Attività 8: configurare le informazioni riservate e i criteri per i linguaggi offensivi

La protezione delle informazioni riservate e l'individuazione e l'azione degli incidenti di molestie sul posto di lavoro è una parte importante della conformità con gli standard e i criteri interni. La [conformità alla comunicazione](communication-compliance-feature-reference.md) in Microsoft 365 consente di ridurre al minimo tali rischi, contribuendo a rilevare, acquisire e adottare rapidamente azioni correttive per le comunicazioni di posta elettronica e Microsoft teams. Sono incluse comunicazioni inappropriate che contengono parolacce, minacce e molestie e comunicazioni che condividono informazioni riservate all'interno e all'esterno dell'organizzazione.

Un modello di criteri di *anti-molestia e linguaggio offensivo* predefinito consente di analizzare le comunicazioni interne ed esterne per le corrispondenze dei criteri in modo che possano essere esaminate da revisori designati. I revisori possono esaminare la posta elettronica digitalizzata, Microsoft teams, Yammer o le comunicazioni di terze parti nell'organizzazione e intraprendere le azioni correttive appropriate per assicurarsi che siano conformi agli standard dell'organizzazione.

Il modello di criteri di *informazioni riservate* predefinito consente di creare rapidamente un criterio per analizzare la posta elettronica e le comunicazioni di Microsoft Team contenenti tipi di informazioni riservate definite o parole chiave per garantire che i dati importanti non siano condivisi con utenti che non devono avere accesso. Tali attività potrebbero includere comunicazioni non autorizzate su progetti riservati o su regole specifiche per l'industria su Insider trading o su altre attività di collusione.

Per istruzioni dettagliate su come pianificare e configurare la conformità delle comunicazioni, vedere [Plan for Communication Compliance](communication-compliance-plan.md) and [Get Started with Communication Compliance](communication-compliance-configure.md). Per informazioni sulle licenze per la conformità alla comunicazione, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato le nozioni di base per la gestione della conformità per l'organizzazione, prendere in considerazione le seguenti soluzioni di conformità in Microsoft 365 che consentono di proteggere le informazioni riservate e di rilevare e agire su ulteriori rischi Insider.

### <a name="configure-retention-labels"></a>Configurare le etichette di conservazione

Anche se i criteri di conservazione vengono applicati a livello di contenitore a posizioni quali i siti di SharePoint e le cassette postali di Exchange, le [etichette di conservazione](retention.md#retention-labels) consentono di assegnare una destinazione più specifica per i criteri di conservazione e eliminazione. Ad esempio, al livello del messaggio di posta elettronica o di documento che gli utenti finali possono applicare manualmente oltre all'applicazione automatica da parte degli amministratori. È inoltre possibile applicare un'etichetta di conservazione a una raccolta documenti, una cartella o un set di documenti in SharePoint, in modo che tutti i documenti archiviati in tale percorso ereditino l'etichetta di conservazione predefinita.

Le etichette di conservazione supportano inoltre la [gestione dei record](records-management.md) per contrassegnare il contenuto come record. In questo caso, non è possibile modificare o rimuovere l'etichetta e il contenuto non può essere modificato o eliminato. Queste restrizioni potrebbero essere necessarie per aiutare l'organizzazione a rispettare i requisiti normativi.

Per istruzioni dettagliate per la creazione e la pubblicazione di etichette di conservazione, vedere le indicazioni seguenti:
- [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)
- [Applicazione automatica di un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)

Per informazioni sulle licenze di gestione dei record, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management).

### <a name="identify-and-define-sensitive-information-types"></a>Identificare e definire i tipi di informazioni riservate

Definire i tipi di informazioni riservate in base al modello contenuto nelle informazioni nei dati dell'organizzazione. Utilizzo [di tipi di informazioni riservate incorporate](what-the-sensitive-information-types-look-for.md) consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. O creare tipi di [informazioni di riservatezza personalizzati](custom-sensitive-info-types.md) specifici per l'organizzazione.

Per istruzioni dettagliate sulla definizione di tipi di informazioni riservate personalizzate, vedere [creare un tipo di informazioni riservate personalizzato nel centro sicurezza & Compliance](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type).

### <a name="prevent-data-loss"></a>Evitare la perdita di dati

[I criteri di prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md) consentono di identificare, monitorare e proteggere automaticamente le informazioni riservate all'interno dell'organizzazione Microsoft 365. Utilizzare i criteri DLP per identificare le informazioni riservate tra i servizi Microsoft, impedire la condivisione accidentale di informazioni riservate e aiutare gli utenti a imparare a rimanere conformi senza interrompere il flusso di lavoro.

Per istruzioni dettagliate su come configurare i criteri DLP, vedere [Introduzione ai consigli sui criteri DLP](get-started-with-dlp-policy-recommendations.md) e iniziare [a utilizzare il criterio DLP predefinito](get-started-with-the-default-dlp-policy.md). Per informazioni sulle licenze per la gestione della perdita di dati, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Rilevare e agire sui rischi Insider

Sempre più, i dipendenti hanno sempre più accesso alla creazione, gestione e condivisione dei dati in un ampio spettro di piattaforme e servizi. Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e mitigare i rischi a livello di organizzazione, nonché soddisfare i requisiti di conformità e gli standard di privacy dei dipendenti. Tali rischi possono includere il furto dei dati derivanti dalla disattivazione dei dipendenti e dalla perdita di dati di informazioni all'esterno dell'organizzazione tramite una condivisione accidentale o dolo.

La [gestione dei rischi Insider](insider-risk-management-policies.md) in Microsoft 365 utilizza l'intera gamma di indicatori di servizio e di terze parti che consentono di identificare, valutare e agire rapidamente sulle attività degli utenti a rischio. Utilizzando i registri di Microsoft 365 e Microsoft Graph, Insider Risk Management consente di definire criteri specifici per identificare gli indicatori di rischio e di intervenire per attenuare tali rischi.

Per informazioni dettagliate su come pianificare e configurare i criteri di gestione dei rischi Insider, vedere [pianificare la gestione dei rischi Insider](insider-risk-management-plan.md) e iniziare a [utilizzare la gestione dei rischi Insider](insider-risk-management-configure.md). Per informazioni sulle licenze per la gestione dei rischi Insider, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).
