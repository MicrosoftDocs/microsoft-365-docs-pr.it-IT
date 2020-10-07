---
title: Introduzione a Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Impostare le autorizzazioni e i ruoli utente di Microsoft Compliance Manager e configurare il testing automatizzato delle azioni. Gestire la cronologia degli utenti e filtrare la visualizzazione del dashboard.
ms.openlocfilehash: 043a52e2817e770671c2ef8876049f6bbe0285ee
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368139"
---
# <a name="get-started-with-compliance-manager"></a>Introduzione a Compliance Manager

**In questo articolo:** In questo articolo viene illustrato come configurare Compliance Manager. Informazioni su come **accedere** a Compliance Manager, **impostare i ruoli e le autorizzazioni**e configurare il **test automatico delle azioni di miglioramento**. Scorrere il **dashboard di Compliance Manager** e comprendere le pagine principali: la pagina azioni di miglioramento, la pagina soluzioni, la pagina valutazioni e la pagina modelli di valutazione.

## <a name="who-can-access-compliance-manager"></a>Chi può accedere a Compliance Manager

Compliance Manager è disponibile per le organizzazioni con licenza di Office 365 e Microsoft 365. La disponibilità e le funzionalità di gestione della valutazione dipendono dal contratto di licenza.  [Visualizzare i dettagli della descrizione del servizio](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="before-you-begin"></a>Informazioni preliminari

L'amministratore globale di Microsoft 365 per l'organizzazione sarà probabilmente il primo utente a accedere a Compliance Manager. È consigliabile accedere all'amministratore globale e impostare le autorizzazioni utente come indicato di seguito quando si visita Compliance Manager per la prima volta.

## <a name="sign-in"></a>Accesso

1. Accedere al [centro conformità microsoft 365](https://compliance.microsoft.com/) e **accedere** con l'account di amministratore globale di Microsoft 365.
2. Selezionare **Compliance Manager** nel riquadro di spostamento a sinistra. Si arriva al [Dashboard Compliance Manager](#understand-the-compliance-manger-dashboard).

Il collegamento diretto a Access Compliance Manager è [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Impostazione delle autorizzazioni utente e assegnazione dei ruoli

Compliance Manager utilizza un modello di autorizzazione di controllo di accesso basato sui ruoli (RBAC). Solo gli utenti a cui è assegnato un ruolo possono accedere a Compliance Manager e le azioni consentite da ogni utente sono limitate dal [tipo di ruolo](#role-types).

### <a name="where-to-set-permissions"></a>Dove impostare le autorizzazioni

La persona che detiene il ruolo di amministratore globale per l'organizzazione può impostare le autorizzazioni utente nel centro conformità di Microsoft 365, nonché in Azure Active Directory (Azure AD).

Per impostare le autorizzazioni e assegnare i ruoli dall'interno del centro conformità di Microsoft 365, attenersi alla procedura seguente:

1. Selezionare **autorizzazioni** sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella parte superiore, selezionare il collegamento **"per visualizzare e gestire i ruoli in Office 365, andare qui".** Una nuova scheda verrà aperta al centro sicurezza & conformità di Office 365 ([informazioni sul motivo per cui è stato reindirizzato](microsoft-365-compliance-center.md#frequently-asked-questions)).

3. Individuare il gruppo di ruoli a cui si desidera aggiungere uno o più utenti e selezionare la casella a sinistra del nome del gruppo. Vedere l' [elenco dei ruoli e delle funzioni correlate seguenti](#role-types). I nomi dei gruppi di ruoli simulano il nome del ruolo.

4. Nel riquadro a comparsa del gruppo, selezionare **modifica** sotto l'intestazione **membri** .

5. Selezionare **Scegli membri**. Verrà visualizzata un'altra finestra a comparsa.

6. Selezionare **+ Aggiungi** per scegliere uno o più utenti da aggiungere al gruppo.

7. Selezionare la casella di controllo accanto ai nomi che si desidera aggiungere, quindi selezionare il pulsante **Aggiungi** nella parte inferiore.

8. Al termine dell'assegnazione degli utenti, selezionare fine, quindi **fare**clic su **Salva**e quindi su **Chiudi**.

##### <a name="more-about-the-office-365-secruity--compliance-center"></a>Ulteriori informazioni sul centro conformità di Office 365 Secruity &

Per ulteriori informazioni sulle autorizzazioni, vedere [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

Se non si ha accesso al centro sicurezza e conformità di Office 365 o se è necessario accedere alla versione classica di Compliance Manager in Microsoft Service Trust Portal, le impostazioni di amministratore nel Service Trust Portal offrono un altro modo per assegnare i ruoli ([vedere le istruzioni](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)). Tenere presente che tali ruoli sono più limitati nelle loro funzionalità.

##### <a name="more-about-azure-ad"></a>Altre informazioni su Azure AD

Per assegnare i ruoli e impostare le autorizzazioni in Azure AD, vedere [assegnare ruoli di amministratore e non di amministratore agli utenti con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Gli utenti con identità di Azure AD che non dispongono di sottoscrizioni di Office 365 o Microsoft 365 non saranno in grado di accedere a Compliance Manager nel centro conformità di Microsoft 365. Per richiedere assistenza nell'accesso a Compliance Manager, contattare [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipi di ruolo

Nella tabella seguente vengono illustrate le funzioni consentite da ogni ruolo in Compliance Manager. La tabella illustra inoltre in che modo ogni [ruolo di Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) è mappato ai ruoli di gestione della conformità. Per accedere a Compliance Manager, gli utenti avranno bisogno almeno del ruolo di Reader di Compliance Manager o del ruolo di Reader globale di Azure AD.


| L'utente può: | Ruolo di Compliance Manager | Ruolo di Azure AD | 
| :------------- | :-------------: | :------------: |
| **Leggere ma non modificare i dati**| Compliance Manager - Lettore  | Lettore globale di Azure AD, lettore di sicurezza | 
| **Modificare i dati**| Contributo di Compliance Manager | Amministratore di conformità | 
| **Modificare i risultati dei test**| Valutazione di Compliance Manager | Amministratore di conformità | 
| **Gestire le valutazioni e i dati del modello e del tenant**| Amministrazione di Compliance Manager | Amministratore della conformità, amministratore dei dati di conformità, amministratore della sicurezza  | 
| **Assegnare gli utenti**| Amministratore globale | Amministratore globale | 

## <a name="settings-for-automated-testing-and-user-history"></a>Impostazioni per il testing automatizzato e la cronologia degli utenti

Le impostazioni di Compliance Manager nel centro conformità di Microsoft 365 consentono di abilitare e disabilitare il test automatico delle azioni di miglioramento. Le impostazioni consentono anche di gestire i dati degli utenti associati ad azioni di miglioramento, tra cui la possibilità di riassegnare azioni di miglioramento a un altro utente.  Solo gli utenti che dispongono di un ruolo amministratore globale o responsabile della conformità possono accedere alle impostazioni di Compliance Manager.

### <a name="set-up-automated-testing"></a>Configurare il testing automatizzato

Alcune azioni di miglioramento in Compliance Manager sono monitorate anche da [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). È possibile configurare il testing automatizzato delle azioni monitorate congiuntamente, il che significa che quando un'azione viene testata e aggiornata nel punteggio sicuro, questi risultati vengono sincronizzati con le stesse azioni in Compliance Manager e contano verso il Punteggio di conformità.

Il test automatico è attivato per impostazione predefinita per le organizzazioni nuove per la gestione della conformità. Quando si distribuisce per la prima volta Microsoft 365 o Office 365, sono necessari circa sette giorni per ottenere un punteggio sicuro per raccogliere completamente i dati e fattorizzarli nel punteggio di conformità.  Quando il testing automatizzato è attivato, la data di test dell'azione non verrà aggiornata, ma lo stato del test verrà aggiornato. Quando vengono create nuove valutazioni, i punteggi includono automaticamente i punteggi dei controlli di Microsoft e l'integrazione del Punteggio sicuro.

L'amministratore globale dell'organizzazione può modificare le impostazioni per il testing automatizzato in qualsiasi momento. È possibile disattivare il testing automatico per azioni di miglioramento comuni o attivarlo per singole azioni. Seguire le istruzioni riportate di seguito per modificare le impostazioni di testing automatizzati.

#### <a name="to-manage-your-automated-testing-settings"></a>Per gestire le impostazioni di testing automatizzati:

1. Selezionare **Impostazioni** sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella pagina Impostazioni selezionare **Compliance Manager**.

3. Selezionare **test automatizzati** dalla barra di spostamento a sinistra.

4. Selezionare il pulsante applicabile per abilitare il test automatico per tutte le azioni di miglioramento, disattivarlo per tutte le azioni o attivarlo per azione individuale.

5. Se si seleziona **attiva per azione di miglioramento**, un elenco mostrerà tutte le azioni di miglioramento disponibili tra cui scegliere.  Selezionare la casella accanto a qualsiasi azione che si desidera venga testata automaticamente.

6. Fare clic su **Salva** per salvare le impostazioni. Verrà visualizzato un messaggio di conferma nella parte superiore dello schermo in cui è stata salvata la selezione. Se si riceve un avviso di errore, riprovare.

**Nota:** Solo l'amministratore globale può abilitare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può abilitare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

### <a name="manage-user-history"></a>Gestire la cronologia degli utenti

Le impostazioni di **Gestione cronologia utenti** consentono di identificare rapidamente gli utenti che hanno collaborato con le azioni di miglioramento in gestore conformità. I dati degli utenti identificabili associati alle azioni di miglioramento includono qualsiasi operazione di implementazione e testing, i documenti caricati e tutte le note immesse. È possibile comprendere e recuperare questo tipo di dati per soddisfare i requisiti di conformità dell'organizzazione.

Le impostazioni della cronologia degli utenti consentono anche di riassegnare tutte le azioni di miglioramento da un utente a un altro.

**Per trovare le impostazioni della cronologia degli utenti:**

1. Selezionare impostazioni sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella pagina Impostazioni selezionare **Compliance Manager**.

3. Selezionare **Gestisci cronologia utenti** dalla barra di spostamento a sinistra.

Nella pagina **Gestisci cronologia utenti** viene visualizzato un elenco di tutti gli utenti tramite l'indirizzo di posta elettronica assegnato a un'azione di miglioramento. Utilizzare il pulsante di **ricerca** per trovare rapidamente un utente specifico digitando il proprio indirizzo di posta elettronica.

A destra dell'indirizzo di posta elettronica di ogni utente, nel menu a discesa **Seleziona** sono disponibili opzioni per esportare un report, riassegnare azioni di miglioramento o eliminare la cronologia. Per informazioni dettagliate su ogni opzione, vedere ogni sezione riportata di seguito.

#### <a name="export-a-report-of-user-history-data"></a>Esportare un report dei dati della cronologia degli utenti

È possibile esportare un file di Excel contenente un elenco di azioni di miglioramento attualmente assegnate a un utente.  Il rapporto elenca anche eventuali file di prova caricati da tale utente. Tali informazioni possono essere utili per riassegnare le azioni di miglioramento aperto.

Il rapporto riflette lo stato dell'azione di miglioramento alla data di creazione. Non si tratta di un report cronologico di tutte le modifiche precedenti allo stato o all'assegnazione (informazioni su come [esportare un rapporto dalla pagina azioni di miglioramento](compliance-manager-improvement-actions.md#export-a-report)).

**Seguire la procedura riportata di seguito per esportare un report in base all'utente:**

1. Selezionare **Impostazioni** sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella pagina Impostazioni selezionare **Compliance Manager**.

3. Selezionare **Gestisci cronologia utenti** dalla struttura di spostamento a sinistra.

4. Individuare l'utente desiderato eseguendo una ricerca nell'elenco degli indirizzi di posta elettronica o selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Nel menu a discesa **Seleziona** scegliere **Esporta rapporto**.

6. Dopo aver generato il file di Excel del report, è possibile aprirlo e salvarlo nel computer locale.

#### <a name="reassign-improvement-actions-to-another-user"></a>Riassegnare azioni di miglioramento a un altro utente

È possibile riassegnare le azioni di miglioramento da un utente a un altro. Quando si riassegna un'azione, la cronologia di caricamento del documento non cambia, ma il nome dell'utente che originariamente ha caricato la documentazione non viene più visualizzato all'interno dell'azione di miglioramento.

**Attenersi alla procedura riportata di seguito per riassegnare le azioni di miglioramento a un altro utente:**

1. Selezionare **Impostazioni** sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella pagina Impostazioni selezionare **Compliance Manager**.

3. Selezionare **Gestisci cronologia utenti** dalla struttura di spostamento a sinistra.

4. Trovare un utente eseguendo una ricerca nell'elenco indirizzi di posta elettronica o selezionando **Cerca** e inserendo l'indirizzo di posta elettronica dell'utente.

5. Nel menu a discesa **Seleziona** , scegliere **riassegna azioni di miglioramento**. Verrà visualizzato il riquadro a comparsa **riassegna azioni di miglioramento** .

6. Nel campo **Search Users** immettere il nome o l'indirizzo di posta elettronica dell'utente a cui si desidera assegnare le azioni *di*miglioramento.

7. Quando viene visualizzato il nome dell'utente desiderato in **azioni di miglioramento**, selezionare l'utente, quindi selezionare **assegna azioni**.

8. Al termine della riassegnazione, nel riquadro a comparsa verrà visualizzato un messaggio di conferma che conferma che tutte le azioni di miglioramento provenienti dall'utente precedente sono state riassegnate al nuovo utente. Se si riceve una notifica di errore di riassegnazione, chiudere la finestra e riprovare. Per chiudere il riquadro a comparsa, **fare**clic su fine.

Il nuovo assegnatario riceve un messaggio di posta elettronica che è stato assegnato a un'azione di miglioramento. Il messaggio di posta elettronica contiene un collegamento diretto alla pagina dei dettagli dell'azione di miglioramento.
 
 > [!NOTE]
> Se si riassegna un'azione con un aggiornamento in sospeso, il collegamento diretto all'azione nel messaggio di posta elettronica di riassegnazione si interromperà se l'aggiornamento viene accettato dopo la riassegnazione. È possibile risolvere il programma riassegnando l'azione all'utente dopo l'accettazione dell'aggiornamento. Ulteriori informazioni sugli [aggiornamenti per le azioni di miglioramento](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Eliminare la cronologia degli utenti

L'eliminazione della cronologia di un utente verrà rimossa come proprietaria di azioni di miglioramento e verrà rimosso il nome da tutti gli altri campi in Gestione conformità. Quando si elimina la cronologia di un utente, le azioni di miglioramento che sono state possedute non visualizzeranno un valore **assegnato** fino a quando non viene assegnato un nuovo utente. Qualsiasi documento caricato nell'azione di miglioramento mostrerà l' **utente rimosso** al posto del nome dell'utente eliminato. L'eliminazione della cronologia degli utenti è permanente.

Per eliminare la cronologia di un utente, eseguire la procedura seguente:

1. Selezionare **Impostazioni** sulla barra di spostamento sinistra da qualsiasi punto del [centro conformità di Microsoft 365](https://compliance.microsoft.com/).

2. Nella pagina Impostazioni selezionare **Compliance Manager**.

3. Selezionare **Gestisci cronologia utenti** dalla struttura di spostamento a sinistra.

4. Trovare un utente eseguendo una ricerca nell'elenco indirizzi di posta elettronica o selezionando **Cerca** e inserendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Elimina cronologia**dal menu a discesa **Seleziona** .

6. Viene visualizzata una finestra in cui viene chiesto di confermare l'eliminazione definitiva della cronologia dell'utente. Per continuare con l'eliminazione, selezionare **Elimina cronologia**. Per uscire senza eliminare la cronologia, selezionare **Annulla**.

7. È possibile tornare alla pagina **Gestisci cronologia utenti** con un messaggio di conferma nella parte superiore che la cronologia dell'utente è stata eliminata.

## <a name="understand-the-compliance-manger-dashboard"></a>Informazioni sul dashboard di gestione conformità

Il dashboard di Compliance Manager è stato creato per fornire una visualizzazione a colpo d'occhio della posizione di conformità corrente.

![Compliance Manager-dashboard](../media/compliance-manager-dashboard.png "Dashboard di Compliance Manager")

### <a name="overall-compliance-score"></a>Punteggio di conformità globale

Il Punteggio di conformità è evidenziato in primo piano. Visualizza una percentuale in base ai punti ottenibili per il completamento delle azioni di miglioramento che si rivolgono agli standard e alle normative sulla protezione dei dati. I punti di [Microsoft Actions](compliance-manager-assessments.md#microsoft-actions-tab), che sono Managed My Microsoft, contano anche verso il Punteggio di conformità.

Quando si viene a Compliance Manager per la prima volta, il punteggio iniziale è basato sulla [linea di base per la protezione dei dati di Microsoft 365](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Questa valutazione di base, disponibile per tutte le organizzazioni, è un insieme di controlli che include normative e standard industriali comuni. Compliance Manager analizza le soluzioni Microsoft 365 esistenti e fornisce una valutazione iniziale in base alle impostazioni di protezione e privacy correnti. Quando si aggiungono valutazioni rilevanti per la propria organizzazione, il punteggio risulta più significativo per l'utente.

Per **ulteriori informazioni** [, vedere come viene calcolato il Punteggio di conformità](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Azioni di miglioramento principali

In questa sezione sono elencate le operazioni di miglioramento più importanti che è possibile eseguire in questo momento per ottenere un impatto positivo maggiore sul punteggio di conformità globale. Selezionare **Visualizza tutte le azioni di miglioramento** per andare alla pagina azioni di miglioramento.

### <a name="solutions-that-affect-your-score"></a>Soluzioni che influiscono sul Punteggio

In questa sezione vengono illustrate le soluzioni che contengono azioni di miglioramento che possono influire positivamente sul punteggio e il numero di azioni di miglioramento eccezionali in tali soluzioni. Selezionare **Visualizza tutte le soluzioni** per visitare la pagina soluzioni.

### <a name="compliance-score-breakdown"></a>Ripartizione del Punteggio di conformità

In questa sezione viene fornita una visualizzazione più dettagliata del punteggio in due modi diversi:

- **Categorie**: indica la percentuale del Punteggio generale all'interno delle categorie di protezione dei dati, ad esempio "Protect Information" o "Manage Devices".
- **Valutazioni**: indica la percentuale di progressi nella gestione delle valutazioni per una particolare conformità e standard di protezione dei dati, normative o leggi, come GDPR o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrare la visualizzazione del dashboard

È possibile filtrare la visualizzazione del dashboard per visualizzare solo gli elementi relativi a specifiche normative e standard, soluzioni, tipo di azione, gruppi di valutazione o categorie di protezione dei dati. Il filtraggio della visualizzazione in questo modo consente di filtrare anche il punteggio nel dashboard, mostrando quanti punti sono stati raggiunti fuori dai possibili punti totali in base ai criteri di filtro.

Per applicare i filtri:

1. Selezionare **filtro** sul lato superiore destro del dashboard.
2. Selezionare i criteri di filtro dal riquadro a comparsa **filtri** , quindi fare clic su **applica**.

Dopo aver applicato un filtro, vedrai il tuo punteggio rettificato in tempo reale. La percentuale del Punteggio di conformità e le informazioni di ripartizione e le azioni e le soluzioni di miglioramento, ora riguardano solo i dati trattati dai criteri di filtro. Se si disattivano i responsabili della conformità, la visualizzazione filtrata rimane invariata quando si accede.

Per rimuovere i filtri:

- Nella sezione **filtri applicati** sopra il Punteggio di conformità, selezionare la **X** accanto al singolo filtro che si desidera rimuovere. o
- Seleziona **filtro** nella parte superiore destra del dashboard, quindi nel riquadro a comparsa **filtri** , seleziona **Pulisci filtri**.

## <a name="improvement-actions-page"></a>Pagina azioni di miglioramento

Le [azioni di miglioramento](compliance-manager-improvement-actions.md) sono azioni gestite dall'organizzazione. L'utilizzo di azioni di miglioramento contribuisce alla centralizzazione delle attività di conformità e alle normative e agli standard di protezione dei dati. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione e un collegamento per avviare la soluzione appropriata. Le azioni di miglioramento possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

### <a name="view-your-improvement-actions"></a>Visualizzare le azioni di miglioramento

Il dashboard di Compliance Manager consente di visualizzare le **azioni di miglioramento principali.** Per visualizzare tutte le azioni di miglioramento, selezionare la scheda azioni di miglioramento nel dashboard, in cui viene visualizzata la pagina azioni di miglioramento. È inoltre possibile selezionare Visualizza tutte le azioni di miglioramento al di sotto dell'elenco delle azioni di miglioramento chiave nel dashboard per accedere alla pagina azioni di miglioramento.

La pagina azioni di miglioramento Visualizza tutte le azioni di miglioramento gestite dall'organizzazione. Le azioni gestite da Microsoft possono essere visualizzate all'interno di ogni valutazione (per ulteriori informazioni sulle [azioni di Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Se si dispone di un lungo elenco di azioni nella pagina azioni di miglioramento, potrebbe essere utile filtrare la visualizzazione. Selezionare **filtro** nell'angolo in alto a destra dell'elenco delle azioni. Quando viene visualizzato il riquadro dei **filtri** a comparsa, selezionare i criteri in base alle normative e agli standard, alla soluzione e al gruppo. È inoltre possibile personalizzare la visualizzazione selezionando **gruppo** nell'angolo in alto a destra. Dal menu a discesa, selezionare per visualizzare per gruppo, soluzione, categoria, tipo di azione o stato.

La visualizzazione predefinita per questa pagina non Mostra azioni di miglioramento con uno stato di test **superato**. Per visualizzare le azioni che hanno superato il testing, selezionare la casella **passata** nel riquadro dei filtri a comparsa. Solo le azioni con uno stato di prova del conteggio **superato** verso il punteggio. Alcune azioni possono mostrare un' **etichetta di aggiornamento in sospeso.** Ulteriori informazioni sugli [aggiornamenti per le azioni di miglioramento](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

Nella pagina azioni di miglioramento vengono visualizzate le seguenti coordinate per ogni azione di miglioramento:

- **Punti ottenuti**: il numero di punti ottenuti al di fuori del totale disponibile completando l'azione
- **Regolamenti**: le normative o gli standard relativi all'azione
- **Gruppo**: gruppo a cui è stata assegnata l'azione
- **Solutions**: la soluzione in cui è possibile accedere per eseguire l'azione
- **Valutazioni**: le valutazioni che contengono l'azione
- **Categorie**: la categoria relativa alla protezione dei dati (ad esempio, protezione delle informazioni, gestione di dispositivi e così via)
- **Stato del test**:
    - **None** : non è stato registrato alcun aggiornamento dello stato
    - **Non valutato** : il testing non è stato avviato
    - L'implementazione **passata** ha testato correttamente
    - **Esito negativo** dei test a basso rischio non riuscito, rischio basso
    - **Esito** negativo del test di rischio medio non riuscito, rischio medio
    - **Errore di test ad alto rischio** non riuscito, ad alto rischio
    - **Fuori portata** : l'azione non rientra nell'ambito della valutazione e non influisce sul Punteggio
    - **Per essere rilevato** -per il test manuale, indica che è stata implementata un'azione ma non è stata testata. per il test automatizzato, indica che un'azione è in attesa di risultati dell'automazione
    - **Non è** stato possibile rilevare-non è possibile determinare lo stato automatico
    - **Parzialmente testato** – Punteggio automatizzato che premia i punti parziali

Per **ulteriori informazioni** , [vedere How to assign and perform work on Improvement actions](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Pagina soluzioni

La pagina soluzioni consente di visualizzare la quota dei punti guadagnati e potenziali organizzati dalla soluzione. La visualizzazione dei punti rimanenti e le azioni di miglioramento da questa visualizzazione consentono di comprendere quali soluzioni richiedono un'attenzione più immediata.

Individuare la pagina soluzioni selezionando la scheda **soluzioni** nel dashboard di Compliance Manager. È inoltre possibile selezionare **Visualizza tutte le soluzioni** al di sotto delle **soluzioni che influiscono sul punteggio** nella sezione in alto a destra del dashboard.

### <a name="filtering-your-solutions-view"></a>Applicazione del filtro alla visualizzazione soluzioni

Per filtrare la visualizzazione delle soluzioni:

1. Selezionare **filtro** nell'angolo in alto a sinistra dell'elenco di valutazioni.
2. Nel riquadro dei **filtri** a comparsa, inserire un controllo accanto ai criteri desiderati (standard e normative, soluzione, tipo di azione, gruppo di Compliance Manager, categoria).
3. Selezionare il pulsante **applica** . Il riquadro del filtro si chiude e vedrai la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="taking-action-from-the-solution-page"></a>Esecuzione dell'azione dalla pagina della soluzione

Nella pagina soluzioni vengono visualizzate le soluzioni dell'organizzazione connesse alle azioni di miglioramento. Nella tabella sono elencati i contributi di ogni soluzione per il Punteggio globale, i punti ottenuti e possibili all'interno di tale soluzione e il numero restante di azioni di miglioramento raggruppate in tale soluzione in grado di aumentare il punteggio.

È possibile eseguire un'azione da questa schermata in due modi:

1. Nella riga della soluzione desiderata fare clic sul numero di collegamenti ipertestuali nella colonna **azioni rimanenti** . Verrà visualizzata una visualizzazione filtrata della schermata azioni di miglioramento che mostra le azioni di miglioramento non testate per tale soluzione.

2. Nella riga della soluzione desiderata fare clic su **Apri**nella colonna **Apri soluzione** . Verrà visualizzata la soluzione o la posizione nei centri di sicurezza e conformità di Microsoft 365 e Office 365, in cui è possibile eseguire l'azione consigliata.

## <a name="assessments-page"></a>Pagina valutazioni

La pagina valutazioni elenca tutte le [valutazioni](compliance-manager-assessments.md) configurate per l'organizzazione. Il denominatore del Punteggio di conformità è determinato da tutte le valutazioni registrate. Quando si aggiungono ulteriori valutazioni, vengono visualizzate altre azioni di miglioramento elencate nella pagina azioni di miglioramento e il denominatore del Punteggio di conformità aumenta.

Nella pagina valutazioni vengono riepilogate le informazioni principali su ogni valutazione:

- **Valutazione**: nome della valutazione
- **Stato**:
    - **Complete** -tutti i controlli hanno lo stato "superato" o almeno uno viene superato e gli altri sono "fuori ambito"
    - **Incompleto** : almeno un controllo ha lo stato "non riuscito"
    - **None** -tutti i controlli non sono stati testati
    - **In Progress** -le azioni di miglioramento hanno qualsiasi altro stato, tra cui "in corso", "credito parziale" o "non rilevato
- **Progress Assessment**: la percentuale del lavoro eseguito verso il completamento, misurata in base al numero di controlli verificati con esito positivo
- **Azioni di miglioramento**: il numero di azioni completate per soddisfare l'implementazione dei controlli
- **Azioni Microsoft**: il numero di azioni completate per soddisfare l'implementazione dei controlli Microsoft
- **Gruppo**: nome del gruppo a cui appartiene la valutazione
- **Prodotto**: servizio Microsoft 365 associato
- **Regolamentazione**: lo standard normativo, la politica o la legge che si applica alla valutazione

### <a name="filtering-your-assessments-view"></a>Filtrare la visualizzazione delle valutazioni

Per filtrare la visualizzazione delle valutazioni:

1. Selezionare **filtro** nell'angolo in alto a sinistra dell'elenco di valutazioni.
2. Nel riquadro dei **filtri** a comparsa, controllare i criteri desiderati.
3. Selezionare il pulsante **applica** . Il riquadro del filtro si chiude e si vedrà la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="default-assessment"></a>Valutazione predefinita

Per impostazione predefinita, viene visualizzata la valutazione della [linea di base sulla protezione dei dati](compliance-manager-assessments.md#data-protection-baseline-default-assessment) nella pagina valutazioni. Compliance Manager fornisce inoltre diversi [modelli](compliance-manager-templates-list.md) predefiniti per la creazione di valutazioni.

## <a name="assessment-templates-page"></a>Pagina modelli di valutazione

Un modello è un Framework per la creazione di una valutazione in Compliance Manager. Nella pagina modelli di valutazione viene visualizzato un elenco di modelli e dettagli principali. L'elenco include modelli forniti da Compliance Manager così come tutti i modelli che l'organizzazione ha modificato o creato. È possibile applicare filtri per trovare un modello basato su certificazione, ambito di prodotto, paese, industria e chi lo ha creato.

Selezionare un modello dalla relativa riga per visualizzare la pagina dei dettagli, che contiene una descrizione del modello e ulteriori informazioni sui dettagli sulla certificazione, sull'ambito e sui controlli. Da questa pagina è possibile selezionare i pulsanti adatti per creare una valutazione, esportare i dati del modello in Excel o modificare il modello.

Per **ulteriori informazioni** [, vedere How to work with Assessment templates](compliance-manager-templates.md).

## <a name="next-step"></a>Passaggio successivo
Personalizzare Compliance Manager mediante [la configurazione di valutazioni](compliance-manager-assessments.md).