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
description: Impostare le autorizzazioni e i ruoli utente di Microsoft Compliance Manager e configurare test automatizzati delle azioni. Gestire la cronologia utente e filtrare la visualizzazione del dashboard.
ms.openlocfilehash: 8877a9a1e65a624708646c17a2517647c8a72f6a
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570558"
---
# <a name="get-started-with-compliance-manager"></a>Introduzione a Compliance Manager

**In questo articolo:** Questo articolo consente di configurare Compliance Manager. Informazioni su come **accedere a** Compliance Manager, impostare ruoli **e autorizzazioni** e configurare il test automatico delle azioni **di miglioramento.** Passare attraverso **il dashboard di Compliance Manager** e comprendere le pagine principali: la pagina delle azioni di miglioramento, la pagina delle soluzioni, la pagina delle valutazioni e la pagina dei modelli di valutazione.

## <a name="who-can-access-compliance-manager"></a>Who può accedere a Compliance Manager

Compliance Manager è disponibile per le organizzazioni con licenze Office 365 e Microsoft 365 e per i clienti di US Government Community Cloud (GCC) Moderate, GCC High e Department of Defense (DoD). La disponibilità della valutazione e le funzionalità di gestione dipendono dal contratto di licenza.  [Visualizzare i dettagli della descrizione del servizio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="before-you-begin"></a>Prima di iniziare

L Microsoft 365 amministratore globale dell'organizzazione sarà probabilmente il primo utente ad accedere a Compliance Manager. Si consiglia all'amministratore globale di accedere e impostare le autorizzazioni utente come descritto di seguito quando visita Compliance Manager per la prima volta.

## <a name="sign-in"></a>Accesso

1. Passare al Centro [Microsoft 365 conformità](https://compliance.microsoft.com/) e **accedere** con l'account Microsoft 365 amministratore globale.
2. Selezionare **Compliance Manager** nel riquadro di spostamento sinistro. Si arriva al dashboard di [Compliance Manager.](#understand-the-compliance-manager-dashboard)

Il collegamento diretto per accedere a Compliance Manager è [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Impostare le autorizzazioni utente e assegnare ruoli

Compliance Manager usa un modello di autorizzazione RBAC (Role-Based Access Control). Solo gli utenti a cui è assegnato un ruolo possono accedere a Compliance Manager e le azioni consentite da ogni utente sono limitate per [tipo di ruolo](#role-types).

### <a name="where-to-set-permissions"></a>Dove impostare le autorizzazioni

La persona che ha il ruolo di amministratore globale per l'organizzazione può impostare le autorizzazioni utente per Compliance Manager. Le autorizzazioni possono essere impostate nel Office 365 Sicurezza & centro conformità e in Azure Active Directory (Azure AD).

> [!NOTE]
> I clienti negli ambienti DoD (High and Department of Defense) di Us Government Community (GCC) possono impostare solo le autorizzazioni utente e i ruoli per Compliance Manager in Azure AD. Vedi di seguito per le istruzioni di Azure AD e le definizioni dei tipi di ruolo.

Per impostare le autorizzazioni e assegnare Office 365 ruoli nel Centro sicurezza & conformità, attenersi alla procedura seguente:

1. Passare al Centro [Office 365 sicurezza & e](https://protection.office.com/) selezionare **Autorizzazioni** nel riquadro di spostamento a sinistra.

2. Individuare il gruppo di ruoli a cui si desidera aggiungere uno o più utenti e selezionare la casella a sinistra del nome del gruppo. Vedere [l'elenco dei ruoli e delle funzioni correlate di seguito.](#role-types) I nomi dei gruppi di ruoli imitano il nome del ruolo.

3. Nel riquadro a comparsa del gruppo selezionare **Modifica nell'intestazione** Membri. 

4. Selezionare **Scegli membri**. Verrà visualizzata un'altra finestra a comparsa.

5. Selezionare **+ Aggiungi** per scegliere uno o più utenti da aggiungere al gruppo.

6. Seleziona la casella di controllo accanto ai nomi che vuoi aggiungere, quindi seleziona il **pulsante** Aggiungi nella parte inferiore.

7. Al termine dell'assegnazione degli utenti, selezionare **Fine,** quindi **salva** e **chiudi.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Altre informazioni sul Centro Office 365 sicurezza & Conformità

Per ulteriori informazioni [sulle autorizzazioni, vedere Office 365 Sicurezza & Centro conformità.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Se non si dispone dell'accesso al Centro sicurezza e conformità di Office 365 o se è necessario accedere alla versione classica di Compliance Manager in Microsoft Service Trust Portal, le impostazioni di amministrazione nel Service Trust Portal forniscono un altro modo per assegnare ruoli[(](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)visualizzare le istruzioni ). Tenere presente che tali ruoli sono più limitati nelle loro funzionalità.

##### <a name="more-about-azure-ad"></a>Altre informazioni su Azure AD

Per assegnare ruoli e impostare autorizzazioni in Azure AD, vedere [Assegnare](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)ruoli di amministratore e non amministratore agli utenti con Azure Active Directory .

Gli utenti con identità di Azure AD che non dispongono di Office 365 o Microsoft 365 non potranno accedere a Compliance Manager nel Centro Microsoft 365 conformità. Per richiedere assistenza per accedere a Compliance Manager, [contattare cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipi di ruolo

La tabella seguente mostra le funzioni consentite da ogni ruolo in Compliance Manager. La tabella mostra anche il mapping di [ogni ruolo di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) ai ruoli di Compliance Manager. Per accedere a Compliance Manager, gli utenti dovranno disporre almeno del ruolo lettore Compliance Manager o del ruolo di lettore globale di Azure AD.


| L'utente può: | Ruolo Compliance Manager | Ruolo Azure AD | 
| :------------- | :-------------: | :------------: |
| **Leggere i dati ma non modificarli**| Lettore di Compliance Manager  | Lettore globale di Azure AD, lettore di sicurezza | 
| **Modificare i dati**| Contributo di Compliance Manager | Amministratore di conformità | 
| **Modificare i risultati dei test**| Esperto di Compliance Manager | Amministratore di conformità | 
| **Gestire le valutazioni e i dati di modello e tenant**| Amministrazione di Compliance Manager | Compliance Administrator, Compliance Data Administrator, Security Administrator  | 
| **Assegnare utenti**| Amministratore globale | Amministratore globale | 

## <a name="settings-for-automated-testing-and-user-history"></a>Impostazioni per test automatizzati e cronologia utente

Le impostazioni di Compliance Manager nel Centro Microsoft 365 conformità consentono di abilitare e disabilitare il test automatico delle azioni di miglioramento. Le impostazioni consentono inoltre di gestire i dati degli utenti associati alle azioni di miglioramento, inclusa la possibilità di riassegnare le azioni di miglioramento a un altro utente.  Solo gli utenti con un ruolo di amministratore globale o amministratore di Compliance Manager possono accedere alle impostazioni di Compliance Manager.

> [!NOTE]
> La funzionalità di test automatizzato non è disponibile per i clienti in ambienti GCC High e DoD, perché secure score non è disponibile in questi ambienti. GCC I clienti High e DoD dovranno implementare e testare manualmente le azioni di miglioramento.

### <a name="set-up-automated-testing"></a>Configurare test automatizzati

Alcune azioni di miglioramento in Compliance Manager vengono monitorate anche da [Microsoft Secure Score.](../security/defender/microsoft-secure-score.md) È possibile configurare test automatizzati di azioni monitorate congiuntamente, il che significa che quando un'azione viene testata e aggiornata in Secure Score, tali risultati vengono sincronizzati con le stesse azioni in Compliance Manager e vengono conteggiati per il punteggio di conformità.

Il test automatico è attivato per impostazione predefinita per le organizzazioni nuove di Compliance Manager. Quando si distribuisce per la prima Microsoft 365 o Office 365, sono necessari circa sette giorni per ottenere il punteggio sicuro per raccogliere completamente i dati e fattoriarlo nel punteggio di conformità.  Quando il test automatizzato è attivato, la data del test dell'azione non verrà aggiornata, ma lo stato del test verrà aggiornato. Quando vengono create nuove valutazioni, i punteggi includono automaticamente i punteggi di controllo Microsoft e l'integrazione del punteggio sicuro.

L'amministratore globale dell'organizzazione può modificare le impostazioni per i test automatizzati in qualsiasi momento. È possibile disattivare i test automatizzati per azioni di miglioramento comuni o attivarlo per singole azioni. Segui le istruzioni seguenti per modificare le impostazioni di test automatizzati.

#### <a name="to-manage-your-automated-testing-settings"></a>Per gestire le impostazioni di test automatizzati:

1. Selezionare **Impostazioni** nella barra di spostamento sinistra da qualsiasi punto [del Centro Microsoft 365 conformità.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Test automatizzato** dal riquadro di spostamento sinistro.

4. Seleziona il pulsante applicabile per attivare il test automatico per tutte le azioni di miglioramento, disattivarlo per tutte le azioni o attivarlo per azione individuale.

5. Se si seleziona **Attiva per azione di miglioramento,** verrà visualizzato un elenco di tutte le azioni di miglioramento disponibili tra cui scegliere.  Seleziona la casella accanto a qualsiasi azione che vuoi testare automaticamente.

6. Selezionare **Salva** per salvare le impostazioni. Nella parte superiore dello schermo verrà visualizzato un messaggio di conferma che indica che la selezione è stata salvata. Se si riceve un avviso di errore, riprovare.

**Nota:** Solo l'amministratore globale può attivare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può attivare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

### <a name="manage-user-history"></a>Gestire la cronologia utente

Le **impostazioni gestisci cronologia utenti** consentono di identificare rapidamente gli utenti che hanno lavorato con le azioni di miglioramento in Compliance Manager. I dati utente identificabili associati alle azioni di miglioramento includono tutte le attività di implementazione e test eseguite, i documenti caricati e le note immesse. La comprensione e il recupero di questo tipo di dati potrebbero essere necessari per le esigenze di conformità dell'organizzazione.

Le impostazioni della cronologia utente consentono inoltre di riassegnare tutte le azioni di miglioramento da un utente a un altro.

**Per trovare le impostazioni della cronologia utente:**

1. Selezionare Impostazioni nella barra di spostamento sinistra da qualsiasi punto [del Centro Microsoft 365 conformità.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

Nella **pagina Gestisci cronologia utenti** viene visualizzato un elenco di tutti gli utenti in base all'indirizzo di posta elettronica assegnato a un'azione di miglioramento. Utilizzare il **pulsante Cerca** per trovare rapidamente un utente specifico digitando l'indirizzo di posta elettronica.

A destra dell'indirizzo di posta  elettronica di ogni utente, il menu a discesa Seleziona offre opzioni per esportare un report, riassegnare azioni di miglioramento o eliminare la cronologia. Vedi ogni sezione di seguito per informazioni dettagliate su ogni opzione.

#### <a name="export-a-report-of-user-history-data"></a>Esportare un report di dati della cronologia utente

È possibile esportare un Excel contenente un elenco delle azioni di miglioramento attualmente assegnate a un utente.  Nel report vengono inoltre elencati tutti i file di prova caricati dall'utente. Queste informazioni consentono di riassegnare azioni di miglioramento aperte.

Il report riflette lo stato dell'azione di miglioramento alla data di creazione. Non si tratta di un report cronologico di tutte le modifiche precedenti apportate al relativo stato o assegnazione (informazioni su come esportare un [report dalla pagina delle azioni di miglioramento).](compliance-manager-improvement-actions.md#export-a-report)

**Seguire la procedura seguente per esportare un report in base all'utente:**

1. Selezionare **Impostazioni** nella barra di spostamento sinistra da qualsiasi punto [del Centro Microsoft 365 conformità.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare l'utente desiderato cercando gli indirizzi di posta elettronica dell'elenco o selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Esporta** report dal menu a **discesa Seleziona.**

6. Dopo aver Excel il file del report, è possibile aprirlo e salvarlo nel computer locale.

#### <a name="reassign-improvement-actions-to-another-user"></a>Riassegnare azioni di miglioramento a un altro utente

È possibile riassegnare le azioni di miglioramento da un utente a un altro. Quando si riassegna un'azione, la cronologia di caricamento dei documenti non cambia, ma il nome dell'utente che ha caricato originariamente la documentazione non viene più visualizzato nell'azione di miglioramento.

**Seguire i passaggi seguenti per riassegnare le azioni di miglioramento a un altro utente:**

1. Selezionare **Impostazioni** nella barra di spostamento sinistra da qualsiasi punto [del Centro Microsoft 365 conformità.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare un utente eseguendo una ricerca nell'elenco degli indirizzi di posta elettronica oppure selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Riassegna** azioni di miglioramento dal menu **a discesa Seleziona.** Verrà visualizzato il riquadro a comparsa **Riassegna azioni** di miglioramento.

6. Nel campo **Cerca utenti** immettere il nome o l'indirizzo di posta elettronica dell'utente a cui si desidera assegnare le azioni *di miglioramento.*

7. Quando viene visualizzato il nome dell'utente desiderato in **Azioni di** miglioramento verrà assegnato a , selezionare l'utente, quindi selezionare **Assegna azioni**.

8. Al termine della riassegnazione, nel riquadro a comparsa verrà visualizzato un messaggio di conferma che conferma che tutte le azioni di miglioramento dell'utente precedente sono state riassegnate al nuovo utente. Se si riceve un avviso di errore di riassegnazione, chiudere la finestra e riprovare. Per chiudere il riquadro a comparsa, selezionare **Fatto.**

Il nuovo assegnatare riceve un messaggio di posta elettronica assegnato a un'azione di miglioramento. Il messaggio di posta elettronica contiene un collegamento diretto alla pagina dei dettagli dell'azione di miglioramento.
 
 > [!NOTE]
> Se si riassegna un'azione con un aggiornamento in sospeso, il collegamento diretto all'azione nel messaggio di posta elettronica di riassegnazione si interromperà se l'aggiornamento viene accettato dopo la riassegnazione. È possibile risolvere il problema assegnando nuovamente l'azione all'utente dopo l'accettazione dell'aggiornamento. Ulteriori informazioni sugli [aggiornamenti per le azioni di miglioramento.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Eliminare la cronologia utente

L'eliminazione della cronologia di un utente li rimuoverà come proprietari delle azioni di miglioramento e ne rimuoverà il nome da tutti gli altri campi in Compliance Manager. Quando si elimina la cronologia di un utente, le  azioni di miglioramento di cui erano proprietari non visualizzano un valore Assegnato a finché non viene assegnato un nuovo utente. Tutti i documenti caricati nell'azione di miglioramento mostreranno **l'utente** rimosso al posto del nome dell'utente eliminato. L'eliminazione della cronologia utente è permanente.

Per eliminare la cronologia di un utente, eseguire la procedura seguente:

1. Selezionare **Impostazioni** nella barra di spostamento sinistra da qualsiasi punto [del Centro Microsoft 365 conformità.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare un utente eseguendo una ricerca nell'elenco degli indirizzi di posta elettronica oppure selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Elimina** cronologia dal menu a **discesa Seleziona.**

6. Viene visualizzata una finestra in cui viene chiesto di confermare l'eliminazione definitiva della cronologia dell'utente. Per continuare con l'eliminazione, selezionare **Elimina cronologia.** Per uscire senza eliminare la cronologia, selezionare **Annulla.**

7. Si torna alla pagina Gestisci **cronologia** utente con un messaggio di conferma nella parte superiore che indica che la cronologia per l'utente è stata eliminata.

## <a name="understand-the-compliance-manager-dashboard"></a>Informazioni sul dashboard di Compliance Manager

Il dashboard di Compliance Manager è progettato per fornire una panoramica della posizione di conformità corrente.

![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Dashboard di Compliance Manager")

### <a name="overall-compliance-score"></a>Punteggio di conformità complessivo

Il punteggio di conformità è in primo piano. Mostra una percentuale in base ai punti raggiungibili per il completamento delle azioni di miglioramento che affrontano i principali standard e normative di protezione dei dati. Anche i [punti delle azioni Microsoft,](compliance-manager-assessments.md#microsoft-actions-tab)gestite da Microsoft, vengono conteggiati per il punteggio di conformità.

Quando si arriva a Compliance Manager per la prima volta, il punteggio iniziale si basa sulla Microsoft 365 [di protezione dei dati](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Questa valutazione di base, disponibile per tutte le organizzazioni, è un insieme di controlli che include standard e normative comuni del settore. Compliance Manager analizza le soluzioni Microsoft 365 esistenti e fornisce una valutazione iniziale in base alle impostazioni di privacy e sicurezza correnti. Quando aggiungi valutazioni rilevanti per l'organizzazione, il punteggio diventa più significativo per te.

**Ulteriori informazioni: Informazioni** [su come viene calcolato il punteggio di conformità.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Miglioramenti importanti

In questa sezione sono elencate le principali azioni di miglioramento che è possibile eseguire in questo momento per ottenere il massimo impatto positivo sul punteggio di conformità complessivo. Seleziona **Visualizza tutte le azioni di miglioramento** per passare alla pagina delle azioni di miglioramento.

### <a name="solutions-that-affect-your-score"></a>Soluzioni che modificano il punteggio dell'utente

In questa sezione vengono evidenziate le soluzioni contenenti azioni di miglioramento che possono influire positivamente sul punteggio e il numero di azioni di miglioramento in sospeso in tali soluzioni. Selezionare **Visualizza tutte le soluzioni** per visitare la pagina delle soluzioni.

### <a name="compliance-score-breakdown"></a>Dettagli sul punteggio di conformità

Questa sezione offre una visualizzazione più dettagliata del punteggio in due modi diversi:

- **Categorie**: mostra la percentuale del punteggio complessivo all'interno delle categorie di protezione dei dati, ad esempio "proteggere le informazioni" o "gestire i dispositivi".
- **Valutazioni**: mostra la percentuale di progressi nella gestione delle valutazioni per determinati standard, normative o leggi di conformità e protezione dei dati, ad esempio GDPR o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Applicazione di filtri alla visualizzazione dashboard

È possibile filtrare la visualizzazione del dashboard per visualizzare solo gli elementi correlati a normative e standard specifici, soluzioni, tipo di azione, gruppi di valutazione o categorie di protezione dei dati. Se si filtra la visualizzazione in questo modo, verrà filtrato anche il punteggio nel dashboard, che mostra quanti punti sono stati ottenuti dal totale dei punti possibili in base ai criteri di filtro.

Per applicare filtri:

1. Seleziona **Filtro** sul lato superiore destro del dashboard.
2. Selezionare i criteri di filtro nel **riquadro a** comparsa Filtri, quindi selezionare **Applica.**

Dopo aver applicato un filtro, vedrai il punteggio modificato in tempo reale. La percentuale di punteggio di conformità e le informazioni di scomposizione, le azioni e le soluzioni di miglioramento, ora riguardano solo i dati coperti dai criteri di filtro. Se ci si disconnette da Compliance Manager, la visualizzazione filtrata rimane quando si accede di nuovo.

Per rimuovere i filtri:

- **Nell'intestazione Filtri applicati** sopra il punteggio di conformità, selezionare la **X** accanto al singolo filtro che si desidera rimuovere. o
- Selezionare **Filtro** sul lato superiore destro del dashboard, quindi nel riquadro **a** comparsa Filtri selezionare **Cancella filtri.**

## <a name="improvement-actions-page"></a>Pagina Azioni di miglioramento

[Le azioni di](compliance-manager-improvement-actions.md) miglioramento sono azioni gestite dall'organizzazione. L'utilizzo delle azioni di miglioramento consente di centralizzare le attività di conformità e di allinearsi alle normative e agli standard di protezione dei dati. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione e un collegamento per avviare l'utente nella soluzione appropriata. Le azioni di miglioramento possono essere assegnate agli utenti dell'organizzazione per eseguire attività di implementazione e test. È inoltre possibile archiviare documentazione, note e registrare gli aggiornamenti dello stato all'interno dell'azione di miglioramento.

### <a name="view-your-improvement-actions"></a>Visualizzare le azioni di miglioramento

Il dashboard di Compliance Manager mostra le **azioni principali di miglioramento.** Per visualizzare tutte le azioni di miglioramento, selezionare la scheda Azioni di miglioramento nel dashboard, che consente di accedere alla pagina delle azioni di miglioramento. Puoi anche selezionare Visualizza tutte le azioni di miglioramento sotto l'elenco delle azioni di miglioramento chiave nel dashboard per accedere alla pagina delle azioni di miglioramento.

La pagina azioni di miglioramento mostra tutte le azioni di miglioramento gestite dall'organizzazione. Le azioni gestite da Microsoft possono essere visualizzate all'interno di ogni valutazione (ulteriori informazioni [sulle azioni Microsoft).](compliance-manager-assessments.md#microsoft-actions-tab)

Se nella pagina delle azioni di miglioramento è disponibile un lungo elenco di azioni, può essere utile filtrare la visualizzazione. Selezionare **Filtro** nell'angolo superiore destro dell'elenco delle azioni. Quando viene **visualizzato il** riquadro a comparsa Filtri, selezionare i criteri in base a normative e standard, soluzioni e gruppi. Puoi anche personalizzare la visualizzazione selezionando **Raggruppa** nell'angolo in alto a destra. Dal menu a discesa, selezionare per visualizzare per gruppo, soluzione, categoria, tipo di azione o stato.

La visualizzazione predefinita per questa pagina non mostra le azioni di miglioramento con stato di test **Superato.** Per visualizzare le azioni che hanno superato il test, selezionare la **casella** Superato nel riquadro a comparsa Filtri. Solo le azioni con stato di test **Superato** conteggio verso il punteggio. Alcune azioni potrebbero mostrare **un'etichetta di aggiornamento in sospeso.** Ulteriori informazioni sugli [aggiornamenti per le azioni di miglioramento.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

La pagina azioni di miglioramento mostra i seguenti punti dati per ogni azione di miglioramento:

- **Punti ottenuti**: numero di punti ottenuti sul totale disponibile completando l'azione
- **Normative**: norme o standard relativi all'azione
- **Gruppo**: gruppo a cui è stata assegnata l'azione
- **Soluzioni**: la soluzione in cui è possibile eseguire l'azione
- **Valutazioni**: valutazioni che contengono l'azione
- **Categorie**: categoria di protezione dei dati correlata (ad esempio, proteggere le informazioni, gestire i dispositivi e così via)
- **Stato test**:
    - **Nessuno:** nessun aggiornamento dello stato registrato
    - **Non valutato:** il test non è stato avviato
    - **Superato** : implementazione testata correttamente
    - **Rischio basso non riuscito** - Test non riuscito, basso rischio
    - **Rischio medio non riuscito** - Test non riuscito, rischio medio
    - **Rischio elevato non riuscito** - Test non riuscito, rischio elevato
    - **Fuori ambito:** l'azione non è nell'ambito della valutazione e non influisce sul punteggio
    - **To be detected** - for manual test, indicates an action has been implemented but not tested; per il test automatizzato, indica che un'azione è in attesa del risultato dell'automazione
    - **Impossibile rilevarsi** - Impossibile determinare lo stato automatico
    - **Parzialmente testato:** punteggio automatizzato che premia i punti parziali

**Per ulteriori informazioni,** [vedere Come assegnare ed eseguire operazioni sulle azioni di miglioramento.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Pagina Soluzioni

La pagina delle soluzioni mostra la quota di punti ottenuti e potenziali organizzati in base alla soluzione. La visualizzazione dei punti rimanenti e delle azioni di miglioramento da questa visualizzazione consente di comprendere quali soluzioni necessitano di un'attenzione più immediata.

Individuare la pagina delle soluzioni selezionando la **scheda Soluzioni** nel dashboard di Compliance Manager. Puoi anche selezionare **Visualizza tutte le soluzioni** sotto Soluzioni che influiscono sul **punteggio** nella sezione in alto a destra del dashboard.

### <a name="filtering-your-solutions-view"></a>Filtro della visualizzazione delle soluzioni

Per filtrare la visualizzazione delle soluzioni:

1. Seleziona **Filtro** nell'angolo superiore sinistro dell'elenco delle valutazioni.
2. Nel riquadro **a** comparsa Filtri, posizionare un controllo accanto ai criteri desiderati (standard e normative, soluzione, tipo di azione, gruppo compliance manager, categoria).
3. Selezionare il **pulsante** Applica. Il riquadro dei filtri verrà chiuso e verrà visualizzata la visualizzazione filtrata.

Puoi anche modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o  regolamento selezionando il tipo di raggruppamento dal menu a discesa Gruppo sopra l'elenco delle valutazioni.

### <a name="taking-action-from-the-solution-page"></a>Eseguire un'azione dalla pagina della soluzione

Nella pagina delle soluzioni vengono visualizzate le soluzioni dell'organizzazione connesse alle azioni di miglioramento. Nella tabella sono elencati il contributo di ogni soluzione al punteggio complessivo, i punti ottenuti e possibili all'interno di tale soluzione e il numero rimanente di azioni di miglioramento raggruppate in tale soluzione che possono aumentare il punteggio.

Da questa schermata è possibile eseguire un'azione in due modi:

1. Nella riga della soluzione prevista, nella colonna **Azioni rimanenti,** selezionare il numero con collegamento ipertestuale. Verrà visualizzata una visualizzazione filtrata della schermata delle azioni di miglioramento che mostra le azioni di miglioramento non testate per la soluzione.

2. Nella riga della soluzione prevista, nella colonna **Apri soluzione** selezionare **Apri**. Vedrai la soluzione o il percorso nei Microsoft 365 e Office 365 sicurezza e conformità in cui puoi eseguire l'azione consigliata.

## <a name="assessments-page"></a>Pagina Valutazioni

Nella pagina delle valutazioni sono [elencate](compliance-manager-assessments.md) tutte le valutazioni impostate per l'organizzazione. Il denominatore del punteggio di conformità è determinato da tutte le valutazioni rilevate. Quando aggiungi altre valutazioni, vedrai più azioni di miglioramento elencate nella pagina delle azioni di miglioramento e il denominatore del punteggio di conformità aumenta.

Il **contatore dei** modelli attivati nella parte superiore della pagina mostra il numero di modelli di valutazione attivi attualmente in uso al di fuori del numero totale di modelli disponibili per l'organizzazione. Per [ulteriori informazioni, vedere](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Tipo di modello.

Nella pagina delle valutazioni sono riepilogate le informazioni chiave su ogni valutazione:

- **Valutazione**: nome della valutazione
- **Stato**:
    - **Completa:** tutti i controlli hanno lo stato "superato" o ne viene superato almeno uno e il resto è "fuori ambito"
    - **Incompleto:** almeno un controllo ha lo stato "failed"
    - **Nessuno:** tutti i controlli non sono stati testati
    - **In corso:** le azioni di miglioramento hanno qualsiasi altro stato, tra cui "in corso", "credito parziale" o "non rilevato"
- **Stato di** valutazione : percentuale del lavoro svolto verso il completamento, misurata in base al numero di controlli testati correttamente
- **Azioni di miglioramento**: numero di azioni completate per soddisfare l'implementazione dei controlli
- **Azioni Microsoft**: numero di azioni completate per soddisfare l'implementazione dei controlli Microsoft
- **Gruppo**: nome del gruppo a cui appartiene la valutazione
- **Product**: servizio Microsoft 365 associato
- **Regolamento**: standard normativo, criterio o legge applicabile alla valutazione

### <a name="filtering-your-assessments-view"></a>Filtrare la visualizzazione delle valutazioni

Per filtrare la visualizzazione delle valutazioni:

1. Seleziona **Filtro** nell'angolo superiore sinistro dell'elenco delle valutazioni.
2. Nel riquadro **a** comparsa Filtri controllare i criteri desiderati.
3. Selezionare il **pulsante** Applica. Il riquadro dei filtri verrà chiuso e verrà visualizzata la visualizzazione filtrata.

Puoi anche modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o  regolamento selezionando il tipo di raggruppamento dal menu a discesa Gruppo sopra l'elenco delle valutazioni.

### <a name="default-assessment"></a>Valutazione predefinita

Per impostazione predefinita, nella pagina delle valutazioni viene visualizzata la valutazione [Di](compliance-manager-assessments.md#data-protection-baseline-default-assessment) base per la protezione dei dati. Compliance Manager fornisce inoltre diversi modelli predefiniti [per](compliance-manager-templates-list.md) la creazione di valutazioni.

## <a name="assessment-templates-page"></a>Pagina dei modelli di valutazione

Un modello è una struttura per la creazione di una valutazione in Compliance Manager. La pagina dei modelli di valutazione mostra un elenco di modelli e i dettagli principali. L'elenco include i modelli forniti da Compliance Manager e tutti i modelli modificati o creati dall'organizzazione. È possibile applicare filtri per trovare un modello basato su certificazione, ambito del prodotto, paese, settore e chi lo ha creato.

Il **contatore dei** modelli attivati nella parte superiore della pagina mostra il numero di modelli di valutazione attivi attualmente in uso al di fuori del numero totale di modelli disponibili per l'organizzazione. Per [ulteriori informazioni, vedere](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Tipo di modello.

Selezionare un modello dalla riga corrispondente per visualizzare la relativa pagina dei dettagli, contenente una descrizione del modello e ulteriori informazioni su certificazione, ambito e dettagli dei controlli. Da questa pagina è possibile selezionare i pulsanti appropriati per creare una valutazione, esportare i dati del modello Excel o modificare il modello.

**Per ulteriori informazioni,** [vedere Come utilizzare i modelli di valutazione.](compliance-manager-templates.md)

## <a name="next-step"></a>Passaggio successivo
Personalizzare Compliance Manager [configurando valutazioni](compliance-manager-assessments.md).