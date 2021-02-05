---
title: 'Case study: Contoso configura rapidamente un criterio linguistico offensivo per le comunicazioni di Microsoft Teams, Exchange e Yammer'
description: Un case study per Contoso e come configurano rapidamente un criterio di conformità delle comunicazioni per monitorare il linguaggio offensivo nelle comunicazioni di Microsoft Teams, Exchange Online e Yammer.
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
ms.openlocfilehash: 5925ad7641370b26d0a272968a13028b74b81ef4
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109997"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Case study: Contoso configura rapidamente un criterio linguistico offensivo per le comunicazioni di Microsoft Teams, Exchange e Yammer

La conformità delle comunicazioni in Microsoft 365 consente di ridurre al minimo i rischi di comunicazione consentendo di rilevare, acquisire e agire su messaggi inappropriati nell'organizzazione. I criteri predefiniti e personalizzati consentono di analizzare le comunicazioni interne ed esterne alla ricerca di corrispondenze dei criteri in modo che possano essere esaminate dai revisori designati. I revisori possono analizzare la posta elettronica analizzata, Microsoft Teams, Yammer o le comunicazioni di terze parti nell'organizzazione e intraprendere le azioni correttive appropriate per assicurarsi che siano conformi agli standard dei messaggi dell'organizzazione.

Contoso Corporation è un'organizzazione fittizia che deve configurare rapidamente un criterio per monitorare il linguaggio offensivo. Hanno usato Microsoft 365 principalmente per il supporto di posta elettronica, Microsoft Teams e Yammer per gli utenti, ma hanno nuovi requisiti per applicare i criteri aziendali sulle molestie sul luogo di lavoro. Gli amministratori IT e gli esperti di conformità di Contoso hanno una conoscenza di base delle nozioni fondamentali dell'utilizzo di Microsoft 365 e cercano indicazioni end-to-end su come iniziare rapidamente a usare la conformità delle comunicazioni.

Questo case study tratta le nozioni di base per la configurazione rapida di un criterio di conformità delle comunicazioni per monitorare le comunicazioni per il linguaggio offensivo. Queste indicazioni includono:

- Passaggio 1 - Pianificazione della conformità delle comunicazioni
- Passaggio 2 - Accesso alla conformità delle comunicazioni in Microsoft 365
- Passaggio 3 - Configurazione dei prerequisiti e creazione di un criterio di conformità delle comunicazioni
- Passaggio 4 - Analisi e correzione degli avvisi

## <a name="step-1-planning-for-communication-compliance"></a>Passaggio 1: pianificazione della conformità delle comunicazioni

Gli amministratori IT e gli esperti di conformità di Contoso hanno partecipato a webinar online sulle soluzioni di conformità in Microsoft 365 e hanno deciso che i criteri di conformità delle comunicazioni li aiuteranno a soddisfare i requisiti dei criteri aziendali aggiornati per ridurre le molestie sul luogo di lavoro. Collaborando, hanno sviluppato un piano per creare e abilitare criteri di conformità delle comunicazioni che monitoreranno la presenza di linguaggi offensivi per le chat inviate in Microsoft Teams, i messaggi privati e le conversazioni della community in Yammer e nei messaggi di posta elettronica inviati in Exchange Online. Il piano include l'identificazione di:

- Gli amministratori IT che devono accedere alle funzionalità di conformità delle comunicazioni.
- Gli esperti di conformità che devono creare e gestire i criteri di comunicazione.
- Gli esperti di conformità e altri colleghi di altri reparti (Risorse umane, Legali e così via) che devono analizzare e correggere gli avvisi di conformità delle comunicazioni.
- Gli utenti che saranno nell'ambito dei criteri linguistici offensivi di conformità delle comunicazioni.

### <a name="licensing"></a>Licenze

Il primo passaggio consiste nel verificare che le licenze di Microsoft 365 di Contoso includano il supporto per la soluzione di conformità delle comunicazioni. Per accedere e utilizzare la conformità delle comunicazioni, gli amministratori IT di Contoso devono verificare che Contoso abbia uno degli elementi seguenti:

- Abbonamento a Microsoft 365 E5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Conformità Microsoft 365 E5
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Abbonamento a Microsoft 365 A5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Conformità Microsoft 365 A5
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Microsoft 365 A5 Insider Risk Management
- Abbonamento a Microsoft 365 G5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 G5 + componente aggiuntivo conformità Microsoft 365 G5
- Abbonamento a Microsoft 365 G5 + componente aggiuntivo Microsoft 365 G5 Insider Risk Management
- Abbonamento a Office 365 Enterprise E5 (versione di valutazione o a pagamento)
- Abbonamento a Office 365 Enterprise E3 + componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per i nuovi abbonamenti, vedere la nota)

Devono inoltre confermare che agli utenti inclusi nei criteri di conformità delle comunicazioni deve essere assegnata una delle licenze precedenti.

>[!IMPORTANT]
>Office 365 Advanced Compliance non viene più venduto come abbonamento autonomo. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse o funzionalità di conformità aggiuntive.

Gli amministratori IT di Contoso devono eseguire le operazioni seguenti per verificare il supporto delle licenze per Contoso:

1. Gli amministratori IT a sign in to the **Microsoft 365 admin center** [( https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center**  >  **Billing**  >  **Licenses**.

2. Qui confermano di avere una delle opzioni di [licenza che](communication-compliance-configure.md#subscriptions-and-licensing) include il supporto per la conformità delle comunicazioni.

![Licenze per la conformità delle comunicazioni](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Autorizzazioni per la conformità delle comunicazioni

Esistono cinque gruppi di ruoli utilizzati per configurare le autorizzazioni per gestire le funzionalità di conformità delle comunicazioni. Per rendere **disponibile la** conformità delle comunicazioni come opzione di menu nel Centro conformità Microsoft 365 e per continuare con questi passaggi di configurazione, agli amministratori di Contoso viene assegnato il ruolo di amministratore di *conformità della* comunicazione.

Contoso decide di  utilizzare il gruppo di ruoli Conformità comunicazioni per assegnare al gruppo tutti gli amministratori, gli analisti, gli investigatori e i visualizzatori della conformità delle comunicazioni. Ciò rende più semplice per Contoso iniziare rapidamente e soddisfare al meglio i requisiti di gestione della conformità.

|**Ruolo**|**Autorizzazioni di ruolo**|
|:-----|:-----|
| **Conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per gestire la conformità delle comunicazioni per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati, è possibile configurare le autorizzazioni di conformità delle comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la conformità delle comunicazioni. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la conformità delle comunicazioni ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati. |
| **Communication Compliance Admin** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità delle comunicazioni e successivamente per separare gli amministratori della conformità delle comunicazioni in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di conformità delle comunicazioni, le impostazioni globali e le assegnazioni dei gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Analista di conformità delle comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui sono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto dei messaggi), inoltrare ad altri revisori o inviare notifiche agli utenti. Gli analisti non possono risolvere gli avvisi in sospeso. |
| **Communication Compliance Investigator** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da investigatori della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto dei messaggi, inoltrare ad altri revisori, inoltrare a un caso di Advanced eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore conformità comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che gestiranno i report di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget di report nella home page di conformità delle comunicazioni e visualizzare tutti i report di conformità delle comunicazioni. |

1. Contoso IT administrators sign into the **Office 365 Security & Compliance center** permissions page [( https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Microsoft 365.
2. Nel **Centro sicurezza & conformità,** accedere **a** Autorizzazioni e selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.
3. Gli amministratori selezionano il *gruppo di ruoli Conformità* comunicazioni, quindi **selezionano Modifica gruppo di ruoli.**
4. Gli amministratori **selezionano Scegli** membri dal riquadro di spostamento a sinistra, quindi seleziona **Modifica.**
5. Selezionano **Aggiungi** e quindi selezionano la casella di controllo per tutti gli utenti di Contoso che gestiranno la conformità delle comunicazioni, analizzano ed esaminano gli avvisi.
6. Gli amministratori **selezionano Aggiungi** e **quindi** Fatto.
7. SelezionaNo **Salva** per aggiungere gli utenti contoso al gruppo di ruoli. Seleziona Close **per** completare i passaggi.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Passaggio 2: Accesso alla conformità delle comunicazioni in Microsoft 365

Dopo aver configurato le autorizzazioni per la conformità delle comunicazioni, gli amministratori IT di Contoso e gli esperti di conformità assegnati al gruppo di ruoli Conformità comunicazioni possono accedere alla soluzione di conformità delle comunicazioni in Microsoft 365. Gli amministratori IT e gli esperti di conformità di Contoso possono accedere alla conformità delle comunicazioni in diversi modi e iniziare a creare nuovi criteri:

- A partire direttamente dalla soluzione di conformità delle comunicazioni
- A partire dal Centro conformità Microsoft 365
- A partire dal catalogo delle soluzioni di Microsoft 365
- A partire dall'interfaccia di amministrazione di Microsoft 365

### <a name="starting-directly-from-the-communication-compliance-solution"></a>A partire direttamente dalla soluzione di conformità delle comunicazioni

Il modo più rapido per accedere alla soluzione consiste nell'accedere direttamente alla **soluzione conformità** alle comunicazioni ( <https://compliance.microsoft.com/supervisoryreview> ). Utilizzando questo collegamento, gli amministratori IT di Contoso e gli esperti di conformità verranno indirizzati al dashboard panoramica sulla conformità delle comunicazioni in cui è possibile esaminare rapidamente lo stato degli avvisi e creare nuovi criteri dai modelli predefiniti.

![Panoramica della conformità delle comunicazioni](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>A partire dal Centro conformità Microsoft 365

Un altro modo semplice per gli amministratori IT e gli esperti di conformità di Contoso per accedere alla soluzione di conformità delle comunicazioni consiste nell'accedere direttamente al Centro conformità **Microsoft 365** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Dopo l'accesso, gli utenti  devono semplicemente selezionare il controllo Mostra tutto per visualizzare tutte le soluzioni di conformità e quindi selezionare la soluzione conformità **di** comunicazione per iniziare.

![Centro conformità](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>A partire dal catalogo delle soluzioni di Microsoft 365

Gli amministratori IT di Contoso e gli esperti di conformità possono anche scegliere di accedere alla soluzione di conformità delle comunicazioni selezionando il catalogo delle soluzioni di Microsoft 365. Selezionando **Catalogo** nella sezione **Soluzioni** del riquadro di spostamento sinistro nel Centro conformità **Microsoft 365,** è possibile aprire il catalogo delle soluzioni in cui sono elencate tutte le soluzioni di conformità di Microsoft 365. Scorrendo verso il basso fino alla **sezione Gestione dei rischi Insider,** gli amministratori IT di Contoso possono selezionare Conformità delle comunicazioni per iniziare. Gli amministratori IT di Contoso decidono inoltre di usare il controllo Mostra nel riquadro di spostamento per aggiungere la soluzione di conformità delle comunicazioni al riquadro di spostamento sinistro per un accesso più rapido quando accedono in futuro.

![Catalogo soluzioni](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partire dall'interfaccia di amministrazione di Microsoft 365

Per accedere alla conformità delle comunicazioni all'avvio dall'interfaccia di amministrazione di Microsoft 365, gli amministratori IT di Contoso e gli esperti di conformità accedono all'interfaccia di amministrazione di Microsoft 365 [(e https://admin.microsoft.com)](https://admin.microsoft.com) passano a Conformità interfaccia di amministrazione di **Microsoft 365).**  >  

![Collegamento conformità comunicazione](../media/communication-compliance-case-compliance-link.png)

Questa azione apre il Centro sicurezza e conformità di **Office 365** e deve selezionare il collegamento al Centro conformità **Microsoft 365** fornito nel banner nella parte superiore della pagina.

![Centro sicurezza e conformità di Office 365](../media/communication-compliance-case-scc.png)

Una volta nel **Centro conformità Microsoft 365,** gli amministratori IT di Contoso selezionano Mostra tutto per visualizzare l'elenco completo delle soluzioni di conformità. 

![Menu Conformità comunicazioni](../media/communication-compliance-case-show-all.png)

Dopo aver **selezionato Mostra tutto,** gli amministratori IT di Contoso possono accedere alla soluzione di conformità delle comunicazioni.

![Panoramica della conformità delle comunicazioni](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Passaggio 3: Configurazione dei prerequisiti e creazione di un criterio di conformità delle comunicazioni

Per iniziare a usare un criterio di conformità delle comunicazioni, gli amministratori IT di Contoso devono configurare diversi prerequisiti prima di configurare il nuovo criterio per monitorare il linguaggio offensivo. Una volta completati questi prerequisiti, gli amministratori IT e gli esperti di conformità di Contoso possono configurare i nuovi criteri e specialisti di conformità per avviare l'indagine e correggere gli avvisi generati.

### <a name="enabling-auditing-in-microsoft-365"></a>Abilitazione del controllo in Microsoft 365

La conformità delle comunicazioni richiede che i log di controllo mostrino avvisi e monitorino le azioni di correzione eseguite dai revisori. I log di controllo sono un riepilogo di tutte le attività associate a un criterio organizzativo definito o ogni volta che viene apportata una modifica a un criterio di conformità delle comunicazioni.

Gli amministratori IT di Contoso esaminano e completano le istruzioni [dettagliate](turn-audit-log-search-on-or-off.md) per attivare il controllo. Dopo l'attivazione del controllo, viene visualizzato un messaggio che indica che il log di controllo è in fase di preparazione e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. Gli amministratori IT di Contoso devono eseguire questa azione una sola volta.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configurazione del tenant di Yammer per la modalità nativa

La conformità delle comunicazioni richiede che il tenant di Yammer per un'organizzazione sia in modalità nativa per monitorare il linguaggio offensivo nei messaggi privati e nelle conversazioni della community pubblica.

Gli amministratori IT di Contoso assicurarsi di leggere le informazioni nell'articolo Panoramica della modalità nativa di [Yammer in Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) e seguire la procedura per eseguire lo strumento di migrazione nell'articolo Configurare la rete Yammer per la modalità nativa per [Microsoft 365.](/yammer/configure-your-yammer-network/native-mode)

### <a name="setting-up-a-group-for-in-scope-users"></a>Configurazione di un gruppo per gli utenti nell'ambito

Gli esperti di conformità di Contoso desiderano aggiungere tutti gli utenti ai criteri di comunicazione che monitoreranno il linguaggio offensivo. Possono decidere di aggiungere ogni account utente al criterio separatamente, ma hanno deciso che  è molto più semplice e consente di risparmiare tempo per usare un gruppo di distribuzione Tutti gli utenti per gli utenti per questo criterio.

È necessario creare un nuovo gruppo per includere tutti gli utenti di Contoso, quindi devono eseguire le operazioni seguenti:

1. Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [( https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center**  >  **Groups**  >  **Groups**.
2. SelezionaNo **Aggiungi un gruppo e** completano la procedura guidata per creare un nuovo gruppo di Microsoft *365 o* un nuovo gruppo di *distribuzione.*

    ![Gruppi](../media/communication-compliance-case-all-employees.png)

3. Dopo aver creato il nuovo gruppo, è necessario aggiungere tutti gli utenti di Contoso al nuovo gruppo. Aprono **l'interfaccia di amministrazione di Exchange** [( https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) e passano ai gruppi di destinatari **dell'interfaccia** di amministrazione  >  **di**  >  Exchange. Gli amministratori IT di Contoso selezionano l'area Appartenenza  e il nuovo gruppo Tutti i dipendenti creati e selezionano il controllo Modifica per aggiungere tutti gli utenti di Contoso al nuovo gruppo nella procedura guidata. 

    ![Interfaccia di amministrazione di Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Creazione dei criteri per monitorare il linguaggio offensivo

Una volta completati tutti i prerequisiti, gli amministratori IT e gli esperti di conformità di Contoso sono pronti a configurare i criteri di conformità delle comunicazioni per monitorare il linguaggio offensivo. Usando il nuovo modello di criteri di linguaggio offensivo, la configurazione di questo criterio è semplice e veloce.

1. Gli amministratori IT di Contoso e gli esperti di conformità a sign-in the **Microsoft 365 compliance center** and select Communication **compliance** from the left navigation pane. Questa azione consente di aprire il dashboard **Panoramica** con collegamenti rapidi per i modelli di criteri di conformità delle comunicazioni. Seleziona il **modello Monitor per la lingua offensiva** selezionando **Introduzione** per il modello.

    ![Modello di linguaggio offensivo per la conformità delle comunicazioni](../media/communication-compliance-case-template.png)

2. Nella procedura guidata del modello di criteri, gli amministratori IT di Contoso e gli esperti di conformità lavorano insieme per completare i tre campi **obbligatori:** Nome criterio, Utenti o gruppi da **supervisionare** e **Revisori.**
3. Poiché la procedura guidata dei criteri ha già suggerito un nome per il criterio, gli amministratori IT e gli esperti di conformità decidono di mantenere il nome suggerito e concentrarsi sui campi rimanenti. Selezionano il *gruppo* Tutti  gli utenti per il campo Utenti o gruppi da supervisionare e selezionano gli esperti di conformità che devono analizzare e correggere gli avvisi dei criteri per il campo **Revisori.** L'ultimo passaggio per configurare il criterio e avviare la raccolta delle informazioni sugli avvisi consiste nel selezionare **Crea criterio.**

    ![Procedura guidata linguaggio offensivo per la conformità delle comunicazioni](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Passaggio 4: analizzare e correggere gli avvisi

Dopo aver configurato i criteri di conformità delle comunicazioni da monitorare per il linguaggio offensivo, il passaggio successivo per gli esperti di conformità di Contoso sarà quello di analizzare e correggere gli avvisi generati dal criterio. Saranno disponibili fino a 24 ore prima che il criterio elavi completamente le comunicazioni in tutti i canali di origine delle comunicazioni e che gli avvisi siano visualizzati nel **dashboard degli avvisi.**

Dopo la generazione degli avvisi, gli esperti di conformità di Contoso seguiranno le istruzioni del [flusso](communication-compliance-investigate-remediate.md) di lavoro per analizzare e correggere i problemi di linguaggio offensivo.