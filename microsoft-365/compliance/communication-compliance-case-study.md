---
title: Case Study-Contoso configura rapidamente un criterio di lingua offensivo per le comunicazioni di Microsoft teams, Exchange e Yammer
description: Un case study per Contoso e la modalità di configurazione rapida di un criterio di conformità della comunicazione da monitorare per la lingua offensiva in Microsoft teams, Exchange Online e Yammer Communications.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 9c20b322d4da0339d7c8711abcee38f19f556423
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289389"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Case Study-Contoso configura rapidamente un criterio di lingua offensivo per le comunicazioni di Microsoft teams, Exchange e Yammer

La conformità alla comunicazione in Microsoft 365 consente di ridurre al minimo i rischi di comunicazione contribuendo a rilevare, acquisire e agire su messaggi inopportuni nell'organizzazione. I criteri predefiniti e personalizzati consentono di analizzare le comunicazioni interne ed esterne per le corrispondenze dei criteri in modo che possano essere esaminate da revisori designati. I revisori possono esaminare la posta elettronica digitalizzata, Microsoft teams, Yammer o le comunicazioni di terze parti nell'organizzazione e intraprendere le azioni correttive appropriate per assicurarsi che siano conformi agli standard dei messaggi dell'organizzazione.

Contoso Corporation è un'organizzazione fittizia che deve configurare rapidamente un criterio da monitorare per il linguaggio offensivo. Sono stati utilizzati Microsoft 365 principalmente per la posta elettronica, Microsoft teams e il supporto di Yammer per gli utenti, ma hanno nuovi requisiti per applicare la politica aziendale in merito alle molestie sul posto di lavoro. Gli amministratori IT di Contoso e gli specialisti della conformità hanno una conoscenza di base dei concetti fondamentali relativi all'utilizzo di Microsoft 365 e sono alla ricerca di linee guida end-to-end su come iniziare rapidamente a utilizzare la conformità alla comunicazione.

Questo caso di studio riguarderà le nozioni di base per la configurazione rapida di un criterio di conformità comunicazione per monitorare le comunicazioni per il linguaggio offensivo. In questa guida sono incluse le seguenti:

- Passaggio 1-pianificazione della conformità della comunicazione
- Passaggio 2: accesso alla conformità della comunicazione in Microsoft 365
- Passaggio 3: Configuring Prerequisites e Creating a Communication Compliance Policy
- Passaggio 4: analisi e correzione degli avvisi

## <a name="step-1-planning-for-communication-compliance"></a>Passaggio 1: pianificazione della conformità alla comunicazione

Gli amministratori IT di Contoso e gli specialisti della conformità hanno partecipato a webinar online sulle soluzioni di conformità in Microsoft 365 e hanno deciso che i criteri di conformità della comunicazione consentiranno di soddisfare i requisiti dei criteri aziendali aggiornati per la riduzione delle molestie sul posto Lavorando insieme, sono stati sviluppati un piano per la creazione e l'abilitazione di un criterio di conformità di comunicazione che monitorerà la lingua offensiva per le chat inviate in Microsoft teams, i messaggi privati e le conversazioni della community in Yammer e nei messaggi di posta elettronica inviati in Exchange Online. Il piano include l'identificazione:

- Gli amministratori IT che devono accedere alle funzionalità di conformità della comunicazione.
- Gli specialisti della conformità che devono creare e gestire i criteri di comunicazione.
- Gli specialisti del Compliance e altri colleghi in altri reparti (risorse umane, legali e così via) che devono indagare e correggere gli avvisi di conformità alla comunicazione.
- Gli utenti che rientrano nell'ambito dei criteri del linguaggio offensivo per la conformità di comunicazione.

### <a name="licensing"></a>Licenze

Il primo passaggio consiste nel confermare che la licenza Microsoft 365 di Contoso include il supporto per la soluzione di conformità alla comunicazione. Per accedere e utilizzare la conformità di comunicazione, gli amministratori IT di Contoso devono verificare che Contoso abbia uno dei seguenti elementi:

- Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 E3 + il componente aggiuntivo Microsoft 365 E5 Compliance
- Sottoscrizione Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Compliance
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Insider Risk Management
- Sottoscrizione Microsoft 365 G5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 G5 + componente aggiuntivo Microsoft 365 G5 Compliance
- Microsoft 365 G5 Subscription + Microsoft 365 G5 Insider Risk Management componente aggiuntivo
- Abbonamento a Office 365 Enterprise E5 (a pagamento o versione di valutazione)
- Abbonamento a Office 365 Enterprise E3 + il componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per le nuove sottoscrizioni, vedere note)

È inoltre necessario confermare che agli utenti inclusi nei criteri di conformità della comunicazione deve essere assegnata una delle licenze sopra riportate.

>[!IMPORTANT]
>La conformità avanzata di Office 365 non viene più venduta come sottoscrizione autonoma. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse funzionalità di conformità o aggiuntive.

Gli amministratori IT di Contoso eseguono la procedura seguente per verificare il supporto delle licenze per contoso:

1. Gli amministratori IT possono accedere all'interfaccia di **amministrazione di Microsoft 365** [( https://admin.microsoft.com) ](https://admin.microsoft.com) e passare a **Microsoft 365 Admin Center**  >  **Billing**  >  **licenses**.

2. Qui confermano di disporre di una delle [Opzioni di licenza](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) che include il supporto per la conformità alla comunicazione.

![Licensing Compliance Communications](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Autorizzazioni per la conformità alla comunicazione

Sono disponibili cinque gruppi di ruoli che consentono di configurare le autorizzazioni per la gestione delle funzionalità di conformità della comunicazione. Per rendere la **conformità di comunicazione** disponibile come opzione di menu nel centro conformità di Microsoft 365 e continuare con questi passaggi di configurazione, agli amministratori di Contoso viene assegnato il ruolo di amministratore della conformità di *comunicazione* .

Contoso decide di utilizzare il gruppo di ruolo *comunicazione Compliance* assegnare tutti gli amministratori di conformità di comunicazione, analisti, investigatori e visualizzatori al gruppo. In questo modo è più facile per contoso iniziare rapidamente e meglio si adatta ai propri requisiti di gestione della conformità.

|**Ruolo**|**Autorizzazioni di ruolo**|
|:-----|:-----|
| **Conformità alla comunicazione** | Utilizzare questo gruppo di ruoli per gestire la conformità di comunicazione per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per gli amministratori, gli analisti, gli investigatori e i visualizzatori designati, è possibile configurare le autorizzazioni di conformità per le comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di conformità di comunicazione. Questa configurazione è il modo più semplice per iniziare rapidamente con la conformità alla comunicazione ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati. |
| **Amministratore della conformità alla comunicazione** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità della comunicazione e successivamente per separare gli amministratori della conformità di comunicazione in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di conformità della comunicazione, le impostazioni globali e le assegnazioni dei gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Analista conformità comunicazione** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti di conformità della comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui vengono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto del messaggio), inoltrare a revisori aggiuntivi o inviare notifiche agli utenti. Gli analisti non sono in grado di risolvere gli avvisi in sospeso. |
| **Ricercatore conformità comunicazione** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che agiranno come ricercatori per la conformità della comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto del messaggio, inoltrare ai revisori aggiuntivi, inoltrare a un caso avanzato di eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore conformità comunicazione** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che gestiscono i rapporti di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget per la creazione di report nella Home page conformità di comunicazione e visualizzare tutti i report di conformità della comunicazione. |

1. Gli amministratori IT di Contoso possono accedere alla pagina **Office 365 Security & Compliance Center** Permissions [( https://protection.office.com/permissions) ](https://protection.office.com/permissions) utilizzando le credenziali per un account di amministratore globale e selezionare il collegamento per visualizzare e gestire i ruoli in Microsoft 365.
2. Nel **Centro sicurezza & conformità**, accedere a **autorizzazioni** e selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.
3. Gli amministratori selezionano il gruppo di ruoli *conformità comunicazione* , quindi seleziona **modifica gruppo di ruoli**.
4. Gli amministratori selezionano **Scegli membri** nel riquadro di spostamento a sinistra, quindi seleziona **modifica**.
5. Seleziona **Aggiungi** e quindi seleziona la casella di controllo per tutti gli utenti di Contoso che gestiranno la conformità delle comunicazioni, analizzeranno e rivedranno gli avvisi.
6. Gli amministratori selezionano **Aggiungi**e quindi **fare**clic su fine.
7. Selezionare **Salva** per aggiungere gli utenti di Contoso al gruppo di ruoli. Seleziona **Chiudi** per completare la procedura.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Passaggio 2: accesso alla conformità delle comunicazioni in Microsoft 365

Dopo aver configurato le autorizzazioni per la conformità della comunicazione, gli amministratori IT di Contoso e gli specialisti di conformità assegnati al gruppo di ruolo conformità comunicazione possono accedere alla soluzione di conformità della comunicazione in Microsoft 365. Gli amministratori IT di Contoso e gli specialisti della conformità dispongono di diversi modi per accedere alla conformità della comunicazione e per iniziare a creare un nuovo criterio:

- Partendo direttamente dalla soluzione di conformità della comunicazione
- Partendo dal centro conformità di Microsoft 365
- A partire dal catalogo della soluzione Microsoft 365
- A partire dall'interfaccia di amministrazione di Microsoft 365

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Partendo direttamente dalla soluzione di conformità della comunicazione

Il modo più rapido per accedere alla soluzione consiste nell'eseguire l'accesso direttamente alla soluzione **Communication Compliance** ( <https://compliance.microsoft.com/supervisoryreview> ). Se si utilizza questo collegamento, contoso IT Administrators and Compliance Specialists verrà indirizzato al Dashboard Overview di Communication Compliance, in cui è possibile esaminare rapidamente lo stato degli avvisi e creare nuovi criteri dai modelli predefiniti.

![Panoramica della conformità alla comunicazione](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Partendo dal centro conformità di Microsoft 365

Un altro modo semplice per gli amministratori IT di Contoso e gli specialisti di conformità per accedere alla soluzione di conformità alla comunicazione consiste nell'eseguire l'accesso direttamente al **centro conformità di Microsoft 365** [( https://compliance.microsoft.com) ](https://compliance.microsoft.com). Dopo aver eseguito l'accesso, gli utenti devono semplicemente selezionare il controllo **Mostra tutto** per visualizzare tutte le soluzioni di conformità e quindi selezionare la soluzione di conformità per la **comunicazione** per iniziare.

![Centro conformità](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>A partire dal catalogo della soluzione Microsoft 365

Gli amministratori IT di Contoso e gli specialisti della conformità possono anche scegliere di accedere alla soluzione di conformità della comunicazione selezionando il catalogo della soluzione Microsoft 365. Scegliendo **Catalogo** nella sezione **soluzioni** del riquadro di spostamento sinistro, mentre nel **centro conformità di Microsoft 365**, è possibile aprire il catalogo della soluzione che elenca tutte le soluzioni di conformità di Microsoft 365. Scorrere verso il basso fino alla sezione **gestione dei rischi Insider** , contoso IT Administrators è in grado di selezionare la conformità della comunicazione per iniziare. Gli amministratori IT di Contoso decidono inoltre di utilizzare la funzionalità Mostra nel controllo di spostamento per aggiungere la soluzione di conformità alla comunicazione al riquadro di spostamento a sinistra per un accesso più rapido quando firmano per andare avanti.

![Catalogo delle soluzioni](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partire dall'interfaccia di amministrazione di Microsoft 365

Per accedere alla conformità della comunicazione quando si parte dall'interfaccia di amministrazione di Microsoft 365, gli amministratori IT di Contoso e gli specialisti della conformità accedono all'interfaccia di amministrazione di Microsoft 365 [( https://admin.microsoft.com) ](https://admin.microsoft.com) e accedono a **Microsoft 365 Admin Center**  >  **Compliance**.

![Collegamento di conformità di comunicazione](../media/communication-compliance-case-compliance-link.png)

Questa azione apre il **Centro sicurezza e conformità di Office 365**e deve selezionare il collegamento al **centro conformità di Microsoft 365** fornito nel banner nella parte superiore della pagina.

![Centro sicurezza e conformità di Office 365](../media/communication-compliance-case-scc.png)

Una volta nel **centro conformità di Microsoft 365**, gli amministratori IT di Contoso selezionano **Mostra tutto** per visualizzare l'elenco completo delle soluzioni di conformità.

![Menu conformità comunicazione](../media/communication-compliance-case-show-all.png)

Dopo aver selezionato **Mostra tutto**, gli amministratori IT di Contoso possono accedere alla soluzione di conformità della comunicazione.

![Panoramica della conformità alla comunicazione](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Passaggio 3: Configuring Prerequisites e Creating a Communication Compliance Policy

Per iniziare a utilizzare un criterio di conformità della comunicazione, sono disponibili diversi prerequisiti che gli amministratori IT di Contoso devono configurare prima di impostare il nuovo criterio per il monitoraggio per la lingua offensiva. Una volta completati questi prerequisiti, contoso IT Administrators and Compliance Specialists è in grado di configurare il nuovo criterio e gli specialisti della conformità possono avviare indagini e correggere eventuali avvisi generati.

### <a name="enabling-auditing-in-microsoft-365"></a>Abilitazione del controllo in Microsoft 365

La conformità alla comunicazione richiede i registri di controllo per visualizzare gli avvisi e tenere presenti le azioni di correzione eseguite dai revisori. I registri di controllo sono un riepilogo di tutte le attività associate a un criterio organizzativo definito o in qualsiasi momento si verifica una modifica a un criterio di conformità della comunicazione.

Gli amministratori IT di Contoso esaminano e completano le [istruzioni dettagliate](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) per l'attivazione del controllo. Dopo aver attivato il controllo, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. Gli amministratori IT di Contoso devono eseguire questa azione solo una volta.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configurazione del tenant di Yammer per la modalità nativa

La conformità alla comunicazione richiede che il tenant di Yammer per un'organizzazione sia in modalità nativa per monitorare la lingua offensiva nei messaggi privati e nelle conversazioni di community pubbliche.

Gli amministratori IT di Contoso assicurano che vengano esaminate le informazioni contenute in [Overview of Yammer native mode in microsoft 365 articolo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) e seguire i passaggi per l'esecuzione dello strumento di migrazione nell'articolo [Configure your Yammer Network for native mode for Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode) .

### <a name="setting-up-a-group-for-in-scope-users"></a>Configurazione di un gruppo per gli utenti in ambito

Gli specialisti della conformità di Contoso desiderano aggiungere tutti gli utenti ai criteri di comunicazione che verranno monitorati per la lingua offensiva. È possibile decidere di aggiungere tutti gli account utente ai criteri separatamente, ma è stato deciso che è molto più semplice e consente di risparmiare tempo per utilizzare un gruppo di distribuzione di **tutti gli utenti** per gli utenti per questo criterio.

È necessario creare un nuovo gruppo per includere tutti gli utenti di Contoso, in modo da eseguire le operazioni seguenti:

1. Amministratori IT di Contoso è possibile accedere all'interfaccia di **amministrazione di Microsoft 365** [( https://admin.microsoft.com) ](https://admin.microsoft.com) e accedere ai gruppi di gruppi di interfaccia di **amministrazione di Microsoft 365**  >  **Groups**  >  **Groups**.
2. Selezionare **Aggiungi un gruppo** e completare la procedura guidata per creare un nuovo gruppo o gruppo di *distribuzione*di *Microsoft 365* .

    ![Gruppi](../media/communication-compliance-case-all-employees.png)

3. Dopo aver creato il nuovo gruppo, è necessario aggiungere tutti gli utenti di Contoso al nuovo gruppo. Aprire l'interfaccia di **Amministrazione** [ https://outlook.office365.com/ecp) di Exchange e accedere](https://outlook.office365.com/ecp) ai gruppi di destinatari dell'interfaccia di **amministrazione di Exchange**  >  **recipients**  >  **groups**. Gli amministratori IT di Contoso selezionano l'area di appartenenza e il nuovo gruppo *tutti i dipendenti* che hanno creato e selezionano il controllo di **modifica** per aggiungere tutti gli utenti di Contoso al nuovo gruppo nella procedura guidata.

    ![Interfaccia di amministrazione di Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Creazione dei criteri da monitorare per il linguaggio offensivo

Con tutti i prerequisiti completati, gli amministratori IT e gli specialisti di conformità per Contoso sono pronti per configurare i criteri di conformità della comunicazione da monitorare per il linguaggio offensivo. Se si utilizza il nuovo modello di criteri per il linguaggio offensivo, la configurazione di questo criterio è semplice e veloce.

1. Gli amministratori IT di Contoso e gli specialisti della conformità vengono registrati nel **centro conformità Microsoft 365** e seleziona **conformità comunicazione** dal riquadro di spostamento a sinistra. Questa azione consente di aprire il dashboard **Panoramica** con collegamenti rapidi per i modelli di criteri di conformità della comunicazione. Scelgono il **Monitor per** il modello di lingua offensiva selezionando **inizia** per il modello.

    ![Modello di linguaggio offensivo per la conformità di comunicazione](../media/communication-compliance-case-template.png)

2. Nella procedura guidata dei modelli di criteri, gli amministratori IT di Contoso e gli specialisti della conformità si confrontano per completare i tre campi obbligatori: **nome del criterio**, **utenti o gruppi da supervisionare**e **revisori**.
3. Poiché la procedura guidata ha già suggerito un nome per il criterio, gli amministratori IT e gli specialisti della conformità decidono di mantenere il nome suggerito e lo stato attivo nei campi rimanenti. Selezionano il gruppo *tutti gli utenti* per gli **utenti o i gruppi a cui controllare** il campo e selezionano gli specialisti di conformità che dovrebbero esaminare e correggere gli avvisi dei criteri per il campo **revisori** . L'ultimo passaggio per configurare il criterio e iniziare a raccogliere informazioni sugli avvisi consiste nel selezionare **Crea criterio**.

    ![Procedura guidata per la conformità alla comunicazione](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Passaggio 4: indagare e correggere gli avvisi

Dopo aver configurato il criterio di conformità della comunicazione per il monitoraggio per la lingua offensiva, il passaggio successivo per gli specialisti della conformità di Contoso consiste nell'esaminare e correggere gli eventuali avvisi generati dal criterio. Il criterio richiederà fino a 24 ore per elaborare completamente le comunicazioni in tutti i canali di origine della comunicazione e per visualizzare gli avvisi nel **dashboard di avviso**.

Dopo la generazione degli avvisi, gli specialisti della conformità di Contoso seguiranno le [istruzioni relative al flusso di lavoro](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) per esaminare e correggere i problemi di lingua offensiva.