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
description: Impostare le autorizzazioni utente e i ruoli di Microsoft Compliance Manager e configurare test automatizzati delle azioni. Gestire la cronologia utente e filtrare la visualizzazione del dashboard.
ms.openlocfilehash: 3c8f3f30741d4b0fac5c940bc6ec3fb56ea4f79e
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405796"
---
# <a name="get-started-with-compliance-manager"></a>Introduzione a Compliance Manager

**In questo articolo:** Questo articolo consente di configurare Compliance Manager. Informazioni su come **accedere a** Compliance Manager, impostare ruoli **e autorizzazioni** e configurare il test automatico delle azioni **di miglioramento.** Passare attraverso **il dashboard di Compliance Manager** e comprendere le pagine principali: la pagina delle azioni di miglioramento, la pagina delle soluzioni, la pagina delle valutazioni e la pagina dei modelli di valutazione.

## <a name="who-can-access-compliance-manager"></a>Chi può accedere a Compliance Manager

Compliance Manager è disponibile per le organizzazioni con licenze di Office 365 e Microsoft 365 e per i clienti di US Government Community Cloud (GCC) Moderate e GCC High. Le funzionalità di gestione e disponibilità della valutazione dipendono dal contratto di licenza.  [Visualizzare i dettagli della descrizione del servizio.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="before-you-begin"></a>Prima di iniziare

L'amministratore globale di Microsoft 365 per l'organizzazione sarà probabilmente il primo utente ad accedere a Compliance Manager. Si consiglia all'amministratore globale di accedere e impostare le autorizzazioni utente come descritto di seguito quando visita Compliance Manager per la prima volta.

## <a name="sign-in"></a>Accesso

1. Accedere al [Centro conformità Microsoft 365](https://compliance.microsoft.com/) con l'account di amministratore globale di Microsoft 365. 
2. Selezionare **Compliance Manager** nel riquadro di spostamento sinistro. Si arriva al [dashboard di Compliance Manager.](#understand-the-compliance-manager-dashboard)

Il collegamento diretto per accedere a Compliance Manager è [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Impostare le autorizzazioni utente e assegnare ruoli

Compliance Manager usa un modello di autorizzazione del controllo di accesso basato sui ruoli (RBAC, Role-Based Access Control). Solo gli utenti a cui è assegnato un ruolo possono accedere a Compliance Manager e le azioni consentite da ogni utente sono limitate per [tipo di ruolo.](#role-types)

### <a name="where-to-set-permissions"></a>Dove impostare le autorizzazioni

La persona che ha il ruolo di amministratore globale per l'organizzazione può impostare le autorizzazioni utente per Compliance Manager. Le autorizzazioni possono essere impostate nel Centro sicurezza & e conformità di Office 365 e in Azure Active Directory (Azure AD).

> [!NOTE]
> I clienti negli ambienti GCC (Us Government Community) High possono impostare solo le autorizzazioni utente e i ruoli per Compliance Manager in Azure AD. Vedere di seguito per le istruzioni di Azure AD e le definizioni dei tipi di ruolo.

Per impostare le autorizzazioni e assegnare ruoli nel Centro sicurezza & e conformità di Office 365, eseguire la procedura seguente:

1. Passare al Centro [sicurezza e conformità di Office 365 & e](https://protection.office.com/) selezionare **Autorizzazioni** nel riquadro di spostamento sinistro.

2. Individuare il gruppo di ruoli a cui si desidera aggiungere uno o più utenti e selezionare la casella a sinistra del nome del gruppo. Vedere [l'elenco dei ruoli e delle funzioni correlate di seguito.](#role-types) I nomi dei gruppi di ruoli simulano il nome del ruolo.

3. Nel riquadro a comparsa per il gruppo, selezionare **Modifica sotto** **l'intestazione** Membri.

4. Selezionare **Scegli membri.** Verrà visualizzata un'altra finestra a comparsa.

5. Selezionare **+ Aggiungi** per scegliere uno o più utenti da aggiungere al gruppo.

6. Seleziona la casella di controllo accanto ai nomi che vuoi aggiungere, quindi seleziona il **pulsante** Aggiungi nella parte inferiore.

7. Al termine dell'assegnazione degli utenti, selezionare **Fine,** quindi **salva** e **chiudi.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Ulteriori informazioni sul Centro sicurezza e conformità & di Office 365

Ulteriori informazioni sulle autorizzazioni sono disponibili nel Centro sicurezza [& Conformità di Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Se non si ha accesso al Centro sicurezza e conformità di Office 365 o se è necessario accedere alla versione classica di Compliance Manager in Microsoft Service Trust Portal, le impostazioni di amministratore nel Service Trust Portal forniscono un altro modo per assegnare ruoli[(](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)visualizzare le istruzioni ). Tenere presente che tali ruoli sono più limitati nelle loro funzionalità.

##### <a name="more-about-azure-ad"></a>Altre informazioni su Azure AD

Per assegnare ruoli e impostare le autorizzazioni in Azure AD, vedere Assegnare ruoli di amministratore e non amministratore agli utenti [con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

Gli utenti con identità di Azure AD che non dispongono di abbonamenti a Office 365 o Microsoft 365 non potranno accedere a Compliance Manager nel Centro conformità Microsoft 365. Per richiedere assistenza per accedere a Compliance Manager, contattare [cmresearch@microsoft.com.](mailto:cmresearch@microsoft.com)

### <a name="role-types"></a>Tipi di ruolo

La tabella seguente mostra le funzioni consentite da ogni ruolo in Compliance Manager. La tabella mostra anche il mapping di [ogni ruolo di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) ai ruoli di Compliance Manager. Per accedere a Compliance Manager, gli utenti dovranno disporre almeno del ruolo di lettore Compliance Manager o del ruolo di lettore globale di Azure AD.


| L'utente può: | Ruolo Compliance Manager | Ruolo Azure AD | 
| :------------- | :-------------: | :------------: |
| **Lettura ma non modifica dei dati**| Lettore di Compliance Manager  | Lettore globale di Azure AD, lettore di sicurezza | 
| **Modificare i dati**| Contributo di Compliance Manager | Amministratore di conformità | 
| **Modificare i risultati dei test**| Valutazione di Compliance Manager | Amministratore di conformità | 
| **Gestire le valutazioni e i dati del modello e del tenant**| Amministrazione di Compliance Manager | Amministratore della conformità, Amministratore dati di conformità, Amministratore della sicurezza  | 
| **Assegnare utenti**| Amministratore globale | Amministratore globale | 

## <a name="settings-for-automated-testing-and-user-history"></a>Impostazioni per i test automatizzati e la cronologia utente

Le impostazioni di Compliance Manager nel Centro conformità Microsoft 365 consentono di abilitare e disabilitare il test automatico delle azioni di miglioramento. Le impostazioni consentono inoltre di gestire i dati degli utenti associati alle azioni di miglioramento, inclusa la possibilità di riassegnare le azioni di miglioramento a un altro utente.  Solo gli utenti con un ruolo di amministratore globale o amministratore di Compliance Manager possono accedere alle impostazioni di Compliance Manager.

> [!NOTE]
> La funzionalità di test automatizzato non è disponibile per i clienti in ambienti GCC High perché Secure Score non è disponibile in questi ambienti. I clienti GCC High dovranno implementare e testare manualmente le azioni di miglioramento.

### <a name="set-up-automated-testing"></a>Configurare test automatizzati

Alcune azioni di miglioramento in Compliance Manager vengono monitorate anche da [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) È possibile configurare test automatizzati delle azioni che vengono monitorate congiuntamente, il che significa che quando un'azione viene testata e aggiornata in Secure Score, tali risultati vengono sincronizzati con le stesse azioni in Compliance Manager e vengono conteggiati per il punteggio di conformità.

Il test automatico è attivato per impostazione predefinita per le organizzazioni nuove di Compliance Manager. Quando si distribuisce per la prima volta Microsoft 365 o Office 365, secure score impiega circa sette giorni per raccogliere completamente i dati e fattoriarlo nel punteggio di conformità.  Quando il test automatizzato è attivato, la data del test dell'azione non verrà aggiornata, ma lo stato del test verrà aggiornato. Quando vengono create nuove valutazioni, i punteggi includono automaticamente i punteggi di controllo Microsoft e l'integrazione di Secure Score.

L'amministratore globale dell'organizzazione può modificare le impostazioni per i test automatizzati in qualsiasi momento. È possibile disattivare i test automatizzati per le azioni di miglioramento comuni o attivarlo per singole azioni. Seguire le istruzioni riportate di seguito per modificare le impostazioni di test automatizzato.

#### <a name="to-manage-your-automated-testing-settings"></a>Per gestire le impostazioni di test automatizzati:

1. Selezionare **Impostazioni** nel riquadro di spostamento sinistro da qualsiasi punto del [Centro conformità Microsoft 365.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Seleziona **Test automatizzato** dal riquadro di spostamento sinistro.

4. Selezionare il pulsante applicabile per attivare il test automatico per tutte le azioni di miglioramento, disattivarlo per tutte le azioni o attivarlo per azione individuale.

5. Se si seleziona **Attiva per azione di miglioramento,** in un elenco verranno mostrate tutte le azioni di miglioramento disponibili tra cui scegliere.  Selezionare la casella accanto a qualsiasi azione che si desidera testare automaticamente.

6. Selezionare **Salva** per salvare le impostazioni. Nella parte superiore dello schermo verrà visualizzato un messaggio di conferma che indica che la selezione è stata salvata. Se si riceve un avviso di errore, riprovare.

**Nota:** Solo l'amministratore globale può attivare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può attivare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

### <a name="manage-user-history"></a>Gestire la cronologia degli utenti

Le **impostazioni di Gestione cronologia utenti** consentono di identificare rapidamente quali utenti hanno lavorato con le azioni di miglioramento in Compliance Manager. I dati utente identificabili associati alle azioni di miglioramento includono tutte le operazioni di implementazione e test eseguite, i documenti caricati e le note immesse. La comprensione e il recupero di questo tipo di dati potrebbero essere necessari per le esigenze di conformità dell'organizzazione.

Le impostazioni della cronologia utente consentono inoltre di riassegnare tutte le azioni di miglioramento da un utente a un altro.

**Per trovare le impostazioni della cronologia utente:**

1. Selezionare Impostazioni nel riquadro di spostamento sinistro da qualsiasi punto del [Centro conformità Microsoft 365.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Selezionare **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

Nella **pagina Gestisci cronologia utenti** viene visualizzato un elenco di tutti gli utenti in base all'indirizzo di posta elettronica assegnato a un'azione di miglioramento. Utilizzare il **pulsante Cerca** per trovare rapidamente un utente specifico digitando l'indirizzo di posta elettronica.

A destra dell'indirizzo di posta  elettronica di ogni utente, nel menu a discesa Seleziona sono disponibili opzioni per esportare un report, riassegnare azioni di miglioramento o eliminare la cronologia. Vedi ogni sezione di seguito per informazioni dettagliate su ogni opzione.

#### <a name="export-a-report-of-user-history-data"></a>Esportare un report di dati della cronologia utente

È possibile esportare un file di Excel contenente un elenco delle azioni di miglioramento attualmente assegnate a un utente.  Il report elenca anche tutti i file di prova caricati dall'utente. Queste informazioni consentono di riassegnare le azioni di miglioramento aperte.

Il report riflette lo stato dell'azione di miglioramento alla data di creazione. Non si tratta di un report cronologico di tutte le modifiche precedenti apportate al relativo stato o assegnazione (informazioni su come esportare un [report dalla pagina delle azioni di miglioramento).](compliance-manager-improvement-actions.md#export-a-report)

**Seguire i passaggi seguenti per esportare un report in base all'utente:**

1. Selezionare **Impostazioni** nel riquadro di spostamento sinistro da qualsiasi punto del [Centro conformità Microsoft 365.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Selezionare **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare l'utente desiderato cercando gli indirizzi di posta elettronica dell'elenco oppure selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Esporta** report dal menu **a discesa Seleziona.**

6. Dopo aver generato il file excel del report, è possibile aprirlo e salvarlo nel computer locale.

#### <a name="reassign-improvement-actions-to-another-user"></a>Riassegnare le azioni di miglioramento a un altro utente

È possibile riassegnare le azioni di miglioramento da un utente a un altro. Quando si riassegna un'azione, la cronologia di caricamento dei documenti non cambia, ma il nome dell'utente che ha caricato originariamente la documentazione non viene più visualizzato nell'azione di miglioramento.

**Seguire i passaggi seguenti per riassegnare le azioni di miglioramento a un altro utente:**

1. Selezionare **Impostazioni** nel riquadro di spostamento sinistro da qualsiasi punto del [Centro conformità Microsoft 365.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Selezionare **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare un utente cercando gli indirizzi di posta elettronica dell'elenco oppure selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Riassegna** azioni di miglioramento dal menu **a discesa Seleziona.** Verrà visualizzato il riquadro a comparsa Delle **azioni di miglioramento riassegnazione.**

6. Nel campo **Cerca utenti** immettere il nome o l'indirizzo di posta elettronica dell'utente a cui si desidera assegnare le azioni *di miglioramento.*

7. Quando viene visualizzato il nome dell'utente desiderato in **Azioni** di miglioramento, selezionare l'utente e quindi **selezionare Assegna azioni.**

8. Una volta completata la riassegnazione, nel riquadro a comparsa verrà visualizzato un messaggio di conferma per confermare che tutte le azioni di miglioramento dell'utente precedente sono state riassegnate al nuovo utente. Se si riceve un avviso di errore di riassegnazione, chiudere la finestra e riprovare. Per chiudere il riquadro a comparsa, selezionare **Fine.**

Il nuovo assegnataio riceve un messaggio di posta elettronica a cui è stato assegnato un'azione di miglioramento. Il messaggio di posta elettronica contiene un collegamento diretto alla pagina dei dettagli dell'azione di miglioramento.
 
 > [!NOTE]
> Se si riassegna un'azione con un aggiornamento in sospeso, il collegamento diretto all'azione nel messaggio di posta elettronica di riassegnazione si interromperà se l'aggiornamento viene accettato dopo la riassegnazione. Puoi risolvere il problema assegnando nuovamente l'azione all'utente dopo l'accettazione dell'aggiornamento. Ulteriori informazioni sugli [aggiornamenti alle azioni di miglioramento.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Eliminare la cronologia degli utenti

L'eliminazione della cronologia di un utente li rimuoverà come proprietari delle azioni di miglioramento e rimuoverà il nome da tutti gli altri campi in Compliance Manager. Quando si elimina la cronologia di un utente, le  azioni di miglioramento di cui era proprietario non visualizzano un valore Assegnato a fino a quando non viene assegnato un nuovo utente. Tutti i documenti caricati nell'azione di miglioramento mostreranno **l'utente** rimosso al posto del nome dell'utente eliminato. L'eliminazione della cronologia utente è permanente.

Per eliminare la cronologia di un utente, eseguire la procedura seguente:

1. Selezionare **Impostazioni** nel riquadro di spostamento sinistro da qualsiasi punto del [Centro conformità Microsoft 365.](https://compliance.microsoft.com/)

2. Nella pagina delle impostazioni selezionare **Compliance Manager.**

3. Selezionare **Gestisci cronologia utente** dal riquadro di spostamento a sinistra.

4. Trovare un utente cercando gli indirizzi di posta elettronica dell'elenco oppure selezionando **Cerca** e immettendo l'indirizzo di posta elettronica dell'utente.

5. Scegliere **Elimina** cronologia dal menu **a discesa Seleziona.**

6. Viene visualizzata una finestra che richiede di confermare l'eliminazione definitiva della cronologia dell'utente. Per continuare con l'eliminazione, selezionare **Elimina cronologia.** Per uscire senza eliminare la cronologia, selezionare **Annulla.**

7. Si arriva di nuovo alla **pagina** Gestisci cronologia utenti con un messaggio di conferma nella parte superiore che indica che la cronologia per l'utente è stata eliminata.

## <a name="understand-the-compliance-manager-dashboard"></a>Informazioni sul dashboard di Compliance Manager

Il dashboard di Compliance Manager è progettato per fornire una visualizzazione a colpo d'occhio della posizione attuale di conformità.

![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Dashboard di Compliance Manager")

### <a name="overall-compliance-score"></a>Punteggio di conformità complessivo

Il punteggio di conformità è in primo piano. Mostra una percentuale in base ai punti raggiungibili per il completamento delle azioni di miglioramento che rispendono i principali standard e normative di protezione dei dati. Anche i [punti delle azioni di Microsoft,](compliance-manager-assessments.md#microsoft-actions-tab)gestite da Microsoft, vengono conteggiati per il punteggio di conformità.

Quando si arriva a Compliance Manager per la prima volta, il punteggio iniziale si basa sulla baseline di protezione dei dati di [Microsoft 365.](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Questa valutazione di base, disponibile per tutte le organizzazioni, è un insieme di controlli che include standard e normative comuni del settore. Compliance Manager analizza le soluzioni Microsoft 365 esistenti e fornisce una valutazione iniziale in base alle impostazioni di privacy e sicurezza correnti. Quando si aggiungono valutazioni rilevanti per l'organizzazione, il punteggio diventa più significativo per l'utente.

**Ulteriori informazioni: Comprendere** [come viene calcolato il punteggio di conformità.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Azioni di miglioramento chiave

In questa sezione sono elencate le principali azioni di miglioramento che è possibile eseguire in questo momento per ottenere il massimo impatto positivo sul punteggio di conformità complessivo. Selezionare **Visualizza tutte le azioni di miglioramento** per passare alla pagina delle azioni di miglioramento.

### <a name="solutions-that-affect-your-score"></a>Soluzioni che influiscono sul punteggio

In questa sezione vengono evidenziate le soluzioni contenenti azioni di miglioramento che possono influire negativamente sul punteggio e il numero di azioni di miglioramento in sospeso in tali soluzioni. Selezionare **Visualizza tutte le soluzioni** per visitare la pagina delle soluzioni.

### <a name="compliance-score-breakdown"></a>Suddivisione del punteggio di conformità

Questa sezione offre una visualizzazione più dettagliata del punteggio in due modi diversi:

- **Categorie:** mostra la percentuale del punteggio complessivo nelle categorie di protezione dei dati, ad esempio "proteggere le informazioni" o "gestire i dispositivi".
- **Valutazioni:** mostra la percentuale di progressi nella gestione delle valutazioni per standard, normative o leggi specifici di conformità e protezione dei dati, ad esempio GDPR o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Applicazione di filtri alla visualizzazione dashboard

È possibile filtrare la visualizzazione dashboard per visualizzare solo gli elementi correlati a normative e standard specifici, soluzioni, tipo di azione, gruppi di valutazione o categorie di protezione dei dati. Filtrare la visualizzazione in questo modo consente anche di filtrare il punteggio nel dashboard, mostrando il numero di punti ottenuti dal totale dei punti possibili in base ai criteri di filtro.

Per applicare i filtri:

1. Selezionare **Filtro** sul lato superiore destro del dashboard.
2. Selezionare i criteri di filtro nel **riquadro a** comparsa Filtri, quindi selezionare **Applica.**

Dopo aver applicato un filtro, il punteggio verrà modificato in tempo reale. La percentuale di punteggio di conformità e le informazioni di scomposizione e le azioni di miglioramento e le soluzioni, ora riguardano solo i dati coperti dai criteri di filtro. Se ci si disconnette da Compliance Manager, la visualizzazione filtrata rimane al momento dell'accesso.

Per rimuovere i filtri:

- **Nell'intestazione Filtri applicati** sopra il punteggio di conformità, selezionare la **X** accanto al singolo filtro che si desidera rimuovere; oppure
- Selezionare **Filtro** sul lato superiore destro del dashboard, quindi nel riquadro **a** comparsa Filtri selezionare **Cancella filtri.**

## <a name="improvement-actions-page"></a>Pagina Azioni di miglioramento

[Le azioni di](compliance-manager-improvement-actions.md) miglioramento sono azioni gestite dall'organizzazione. L'utilizzo delle azioni di miglioramento consente di centralizzare le attività di conformità e allinearsi alle normative e agli standard di protezione dei dati. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione e un collegamento per avviare l'utente nella soluzione appropriata. Le azioni di miglioramento possono essere assegnate agli utenti dell'organizzazione per eseguire attività di implementazione e test. È inoltre possibile archiviare documentazione, note e registrare gli aggiornamenti dello stato all'interno dell'azione di miglioramento.

### <a name="view-your-improvement-actions"></a>Visualizzare le azioni di miglioramento

Il dashboard di Compliance Manager mostra le **azioni principali di miglioramento.** Per visualizzare tutte le azioni di miglioramento, selezionare la scheda Azioni di miglioramento nel dashboard, che consente di visualizzare la pagina delle azioni di miglioramento. È inoltre possibile selezionare Visualizza tutte le azioni di miglioramento sotto l'elenco delle azioni di miglioramento principali nel dashboard per accedere alla pagina delle azioni di miglioramento.

Nella pagina delle azioni di miglioramento vengono visualizzate tutte le azioni di miglioramento gestite dall'organizzazione. Le azioni gestite da Microsoft possono essere visualizzate all'interno di ogni valutazione (ulteriori informazioni [sulle azioni di Microsoft).](compliance-manager-assessments.md#microsoft-actions-tab)

Se nella pagina delle azioni di miglioramento è disponibile un lungo elenco di azioni, può essere utile filtrare la visualizzazione. Selezionare **Filtro** nell'angolo superiore destro dell'elenco delle azioni. Quando viene **visualizzato il** riquadro a comparsa Filtri, selezionare i criteri in base alle normative e agli standard, alla soluzione e al gruppo. Puoi anche personalizzare la visualizzazione selezionando **Raggruppa** nell'angolo superiore destro. Dal menu a discesa selezionare per visualizzare per gruppo, soluzione, categoria, tipo di azione o stato.

La visualizzazione predefinita per questa pagina non mostra le azioni di miglioramento con stato Test **superato.** Per visualizzare le azioni che hanno superato i test, selezionare la **casella** Superato nel riquadro a comparsa Filtri. Solo le azioni con stato test **superato vengono** conteggiati verso il punteggio. Alcune azioni potrebbero mostrare un'etichetta **di aggiornamento in sospeso.** Ulteriori informazioni sugli [aggiornamenti alle azioni di miglioramento.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

Nella pagina delle azioni di miglioramento vengono mostrati i punti dati seguenti per ogni azione di miglioramento:

- **Punti ottenuti:** numero di punti ottenuti sul totale disponibile completando l'azione
- **Normative**: le normative o gli standard relativi all'azione
- **Gruppo**: il gruppo a cui è stata assegnata l'azione
- **Soluzioni**: la soluzione in cui è possibile eseguire l'azione
- **Valutazioni**: le valutazioni che contengono l'azione
- **Categorie**: la categoria di protezione dei dati correlata (ad esempio, proteggere le informazioni, gestire i dispositivi e così via)
- **Stato test:**
    - **Nessuno:** nessun aggiornamento dello stato registrato
    - **Non valutato:** il test non è stato avviato
    - **Superato** : implementazione testata correttamente
    - **Rischio basso non riuscito** - test non riuscito, basso rischio
    - **Rischio medio non riuscito** - test non riuscito, rischio medio
    - **Rischio elevato non riuscito** - test non riuscito, rischio elevato
    - **Fuori ambito:** l'azione non è nell'ambito della valutazione e non influisce sul punteggio
    - **Da verificare:** per il test manuale, indica che un'azione è stata implementata ma non testata; per il test automatizzato, indica che un'azione è in attesa del risultato dell'automazione
    - **Impossibile essere rilevato:** impossibile determinare lo stato automatico
    - **Parzialmente testato:** punteggio automatizzato che premia punti parziali

**Ulteriori informazioni:** [Informazioni su come assegnare ed eseguire operazioni sulle azioni di miglioramento.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Pagina Soluzioni

La pagina delle soluzioni mostra la quota di punti ottenuti e potenziali organizzati in base alla soluzione. La visualizzazione dei punti rimanenti e delle azioni di miglioramento da questa visualizzazione consente di comprendere quali soluzioni necessitano di un'attenzione più immediata.

Trovare la pagina delle soluzioni selezionando la **scheda Soluzioni** nel dashboard di Compliance Manager. È inoltre possibile selezionare **Visualizza tutte le soluzioni** sotto Soluzioni che influiscono sul **punteggio** nella sezione in alto a destra del dashboard.

### <a name="filtering-your-solutions-view"></a>Applicazione di filtri alla visualizzazione delle soluzioni

Per filtrare la visualizzazione delle soluzioni:

1. Selezionare **Filtro** nell'angolo superiore sinistro dell'elenco delle valutazioni.
2. Nel riquadro **a comparsa** Filtri, posizionare un controllo accanto ai criteri desiderati (standard e normative, soluzione, tipo di azione, gruppo compliance manager, categoria).
3. Seleziona il **pulsante** Applica. Il riquadro del filtro verrà chiuso e verrà visualizzata la visualizzazione filtrata.

Puoi anche modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o  regolamento selezionando il tipo di raggruppamento dal menu a discesa Gruppo sopra l'elenco delle valutazioni.

### <a name="taking-action-from-the-solution-page"></a>Eseguire un'azione dalla pagina della soluzione

Nella pagina delle soluzioni vengono visualizzate le soluzioni dell'organizzazione connesse alle azioni di miglioramento. Nella tabella sono elencati il contributo di ogni soluzione al punteggio complessivo, i punti ottenuti e possibili all'interno di tale soluzione e il numero rimanente di azioni di miglioramento raggruppate in tale soluzione che possono aumentare il punteggio.

Da questa schermata puoi eseguire un'azione in due modi:

1. Nella riga della soluzione prevista, nella colonna **Azioni rimanenti,** selezionare il numero con collegamento ipertestuale. Verrà visualizzata una visualizzazione filtrata della schermata delle azioni di miglioramento che mostra le azioni di miglioramento non testate per la soluzione.

2. Nella riga della soluzione prevista selezionare Apri nella colonna **Apri** **soluzione.** La soluzione o la posizione verranno visualizzati nei Centri sicurezza e conformità di Microsoft 365 e Office 365 in cui è possibile eseguire l'azione consigliata.

## <a name="assessments-page"></a>Pagina Valutazioni

Nella pagina delle valutazioni sono elencate tutte [le](compliance-manager-assessments.md) valutazioni impostate per l'organizzazione. Il denominatore del punteggio di conformità è determinato da tutte le valutazioni monitorate. Quando aggiungi altre valutazioni, vedrai più azioni di miglioramento elencate nella pagina delle azioni di miglioramento e il denominatore del punteggio di conformità aumenta.

Il **contatore dei** modelli attivati nella parte superiore della pagina mostra il numero di modelli di valutazione attivi attualmente in uso fuori dal numero totale di modelli disponibili per l'organizzazione. Per [ulteriori informazioni, vedere](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Tipo di modello.

Nella pagina delle valutazioni sono riepilogate le informazioni chiave su ogni valutazione:

- **Valutazione**: nome della valutazione
- **Stato**:
    - **Completa:** tutti i controlli hanno lo stato "superato" o almeno uno è stato superato e gli altri sono "fuori ambito"
    - **Incompleto:** almeno un controllo ha lo stato "failed"
    - **Nessuno:** tutti i controlli non sono stati testati
    - **In corso:** le azioni di miglioramento hanno qualsiasi altro stato, tra cui "in corso", "credito parziale" o "non rilevato"
- **Avanzamento della** valutazione: percentuale del lavoro svolto verso il completamento, misurata in base al numero di controlli testati correttamente
- **Azioni di miglioramento:** numero di azioni completate per soddisfare l'implementazione dei controlli
- **Azioni Microsoft**: numero di azioni completate per soddisfare l'implementazione dei controlli Microsoft
- **Gruppo**: nome del gruppo a cui appartiene la valutazione
- **Prodotto:** servizio Microsoft 365 associato
- **Regolamento**: standard normativo, criterio o legge applicabile alla valutazione

### <a name="filtering-your-assessments-view"></a>Filtro della visualizzazione delle valutazioni

Per filtrare la visualizzazione delle valutazioni:

1. Selezionare **Filtro** nell'angolo superiore sinistro dell'elenco delle valutazioni.
2. Nel riquadro **a comparsa** Filtri controllare i criteri desiderati.
3. Seleziona il **pulsante** Applica. Il riquadro del filtro verrà chiuso e verrà visualizzata la visualizzazione filtrata.

Puoi anche modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o  regolamento selezionando il tipo di raggruppamento dal menu a discesa Gruppo sopra l'elenco delle valutazioni.

### <a name="default-assessment"></a>Valutazione predefinita

Per impostazione predefinita, nella pagina delle valutazioni viene visualizzata la valutazione [di](compliance-manager-assessments.md#data-protection-baseline-default-assessment) base per la protezione dei dati. Compliance Manager fornisce inoltre diversi modelli predefiniti [per](compliance-manager-templates-list.md) la creazione di valutazioni.

## <a name="assessment-templates-page"></a>Pagina Modelli di valutazione

Un modello è un framework per la creazione di una valutazione in Compliance Manager. Nella pagina modelli di valutazione viene visualizzato un elenco di modelli e dettagli chiave. L'elenco include i modelli forniti da Compliance Manager e tutti i modelli modificati o creati dall'organizzazione. È possibile applicare filtri per trovare un modello basato sulla certificazione, l'ambito del prodotto, il paese, il settore e l'utente che lo ha creato.

Il **contatore dei** modelli attivati nella parte superiore della pagina mostra il numero di modelli di valutazione attivi attualmente in uso fuori dal numero totale di modelli disponibili per l'organizzazione. Per [ulteriori informazioni, vedere](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Tipo di modello.

Selezionare un modello dalla riga corrispondente per visualizzare la relativa pagina dei dettagli, che contiene una descrizione del modello e ulteriori informazioni sulla certificazione, l'ambito e i dettagli dei controlli. Da questa pagina è possibile selezionare i pulsanti appropriati per creare una valutazione, esportare i dati del modello in Excel o modificare il modello.

**Altre informazioni:** [Informazioni su come utilizzare i modelli di valutazione.](compliance-manager-templates.md)

## <a name="next-step"></a>Passaggio successivo
Personalizzare Compliance Manager [configurando le valutazioni.](compliance-manager-assessments.md)
