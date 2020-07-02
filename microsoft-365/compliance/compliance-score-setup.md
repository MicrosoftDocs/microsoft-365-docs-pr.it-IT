---
title: Configurazione del Punteggio di conformità Microsoft (anteprima)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come configurare e iniziare a utilizzare Microsoft Compliance score, che semplifica e automatizza le valutazioni dei rischi.
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016191"
---
# <a name="compliance-score-preview-setup"></a>Configurazione del Punteggio di conformità (anteprima)

**In questo articolo:** Informazioni su come **accedere** a Punteggio di conformità, impostare i **ruoli e le autorizzazioni**e configurare **gli aggiornamenti automatici del Punteggio sicuro**. In questo articolo vengono inoltre illustrate le pagine principali del Punteggio di conformità: la pagina **Dashboard**, le azioni di miglioramento, la pagina soluzioni e la pagina valutazioni.

## <a name="before-you-begin"></a>Informazioni preliminari

L'amministratore globale di Microsoft 365 per l'organizzazione sarà probabilmente il primo utente ad accedere al Punteggio di conformità. Si consiglia di accedere all'amministratore globale e di impostare le autorizzazioni utente come indicato di seguito quando si visita il Punteggio di conformità per la prima volta.

## <a name="sign-in"></a>Accesso

1. Accedere al [centro conformità di microsoft 365](https://compliance.microsoft.com/) e **accedere** con l'account di amministratore globale di Microsoft 365.
2. Seleziona **Punteggio di conformità** nel riquadro di spostamento a sinistra. Sarà quindi possibile visualizzare il [Dashboard Punteggio di conformità con il Punteggio](#understand-the-compliance-score-dashboard).

Il collegamento diretto per accedere al Punteggio di conformità è [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) .

## <a name="set-user-permissions-and-assign-roles"></a>Impostazione delle autorizzazioni utente e assegnazione dei ruoli

Il Punteggio di conformità utilizza un modello di autorizzazione di controllo di accesso basato sui ruoli (RBAC). Solo gli utenti a cui è assegnato un ruolo possono accedere al Punteggio di conformità e le azioni consentite da ogni utente sono limitate dal tipo di ruolo.

### <a name="where-to-set-permissions"></a>Dove impostare le autorizzazioni

La persona che detiene il ruolo di amministratore globale per l'organizzazione può impostare le autorizzazioni utente in [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) o in [Compliance Manager](compliance-manager-overview.md#permissions). Dopo aver impostato i ruoli in una di queste posizioni, gli utenti possono accedere al Punteggio di conformità e a Compliance Manager.

### <a name="role-types"></a>Tipi di ruolo

Nella tabella seguente viene illustrato il modo in cui ogni [ruolo di Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) è associato ai ruoli di gestione della conformità esistenti e le funzioni consentite da ogni ruolo. Gli utenti avranno bisogno almeno del ruolo di Reader globale di Azure AD per accedere al Punteggio di conformità.


| L'utente può: | Ruolo di Azure AD | Ruolo di Compliance Manager | 
| :------------- | :-------------: | :------------: |
| **Leggere ma non modificare i dati**| Lettore globale di Azure AD  | Lettore globale di Azure AD | 
| **Leggere ma non modificare i dati**| Ruolo con autorizzazioni di lettura per la sicurezza | Reader di Compliance Manager  | 
| **Modificare i dati**| Amministratore di conformità | Collaboratore di Compliance Manager | 
| **Modificare i risultati dei test**| Amministratore di conformità | Responsabile del giudizio di Compliance Manager | 
| **Gestire le valutazioni e i dati del modello e del tenant**| Amministratore di conformità<br>Amministratore dati di conformità<br>Amministratore della sicurezza | Amministratore di Compliance Manager | 
| **Assegnare gli utenti**| Amministratore globale | Amministratore portale | 

> [!NOTE]
> Quando si passa da Punteggio di conformità a Compliance Manager per completare un'attività durante l'anteprima pubblica, il browser aprirà una nuova scheda e verrà visualizzata una finestra di dialogo. Nella sezione superiore con l'intestazione, "già un cliente dei servizi cloud Microsoft? Accedi al tuo account, **"seleziona Accedi** per accedere a Compliance Manager. Non è necessario immettere di nuovo le credenziali.

## <a name="configure-automatic-secure-score-updates"></a>Configurare gli aggiornamenti automatici del Punteggio sicuro

Per impostazione predefinita, tutti i nuovi tenant dispongono degli aggiornamenti automatici di [Secure Score](../security/mtp/microsoft-secure-score-new.md) attivati. Tutte le azioni monitorate da Secure Score aggiorneranno automaticamente lo stato per la stessa azione nel punteggio di conformità.

L'amministratore globale può gestire questa impostazione per disattivare gli aggiornamenti automatici per tutte le azioni o impostare gli aggiornamenti per le azioni singolarmente.

Durante l'anteprima pubblica, è necessario accedere al Microsoft Service Trust Portal (in cui si trova la gestione della conformità) per gestire gli aggiornamenti dei punti di sicurezza.

Per gestire gli aggiornamenti automatici del Punteggio sicuro, attenersi alla seguente procedura:

1. Accedere al [Service Trust Portal](https://servicetrust.microsoft.com) con l'account di amministratore globale.

2. Nella barra dei menu del servizio di attendibilità del Service Top, in **altro**, selezionare **amministratore** e quindi scegliere **Impostazioni**.

3. Nella scheda **Punteggio sicuro** selezionare il pulsante corrispondente per **attivarla per tutte le azioni**, disattivarla **per tutte le azioni**o **impostare per azione.**

Se si sceglie **imposta per azione,** eseguire i passaggi aggiuntivi per abilitare gli aggiornamenti dei punti di sicurezza per le singole azioni:

4. Selezionare **Compliance Manager** dal menu in alto (non selezionare "Compliance Manager (Classic)").

5. Selezionare **gestione tenant** nell'angolo in alto a destra dello schermo.

6. Nel riquadro **azioni cliente** individuare l'azione desiderata con puntini di sospensione (**...**) nella colonna **azioni coinvolte** . Fare clic sui puntini di ellisse e selezionare **modifica.**

7. Cambiare l'opzione attiva/disattiva **aggiornamento continuo Punteggio** **su attivato.**

8. Selezionare **Salva.** Secure Score il monitoraggio continuo è ora attivato per tale azione.

**Nota:** Solo l'amministratore globale può abilitare o disattivare gli aggiornamenti automatici per tutte le azioni. L'amministratore di Compliance Manager può abilitare gli aggiornamenti automatici per singole azioni, ma non per tutte le azioni a livello globale.

#### <a name="learn-more"></a>Altre informazioni

[Informazioni su come gestire gli aggiornamenti dei punti di sicurezza](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Comprendere il dashboard del Punteggio di conformità

Il dashboard del Punteggio di conformità è stato creato per fornire una visualizzazione a colpo d'occhio della posizione di conformità corrente.

![Punteggio di conformità-dashboard](../media/compliance-score-dashboard.png "Dashboard del Punteggio di conformità")

### <a name="overall-compliance-score"></a>Punteggio di conformità globale

Il Punteggio di conformità è evidenziato in primo piano. Visualizza una percentuale in base ai punti ottenibili per il completamento delle azioni di miglioramento che si rivolgono agli standard e alle normative sulla protezione dei dati.

Quando si giunge al Punteggio di conformità per la prima volta, il punteggio iniziale è basato sulla [linea di base di protezione dei dati integrata di Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline), ovvero un insieme di controlli che include normative e standard di settore. Punteggio di conformità analizza le soluzioni Microsoft 365 esistenti e fornisce una valutazione iniziale in base alle impostazioni di protezione e privacy correnti. Quando si aggiungono valutazioni rilevanti per la propria organizzazione, il punteggio risulta più significativo per l'utente.

#### <a name="learn-more"></a>Altre informazioni
[Capire in che modo viene calcolato il Punteggio di conformità](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Azioni di miglioramento principali

In questa sezione sono elencate le operazioni di miglioramento più importanti che è possibile eseguire in questo momento per ottenere un impatto positivo maggiore sul punteggio di conformità globale.

### <a name="solutions-that-affect-your-score"></a>Soluzioni che influiscono sul Punteggio

In questa sezione vengono illustrate le soluzioni che contengono azioni con la maggiore possibilità di influenzare positivamente il punteggio e il numero di azioni di miglioramento eccezionali in ogni soluzione.

### <a name="compliance-score-breakdown"></a>Ripartizione del Punteggio di conformità

In questa sezione viene fornita una visualizzazione più dettagliata del punteggio in due modi diversi:

- **Categorie**: indica la percentuale del Punteggio generale all'interno delle categorie di protezione dei dati, ad esempio "Protect Information" o "Manage Devices".
- **Valutazioni**: indica la percentuale di progressi nella gestione delle valutazioni per una particolare conformità e standard di protezione dei dati, normative o leggi, come GDPR o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrare la visualizzazione del dashboard

È possibile filtrare la visualizzazione del dashboard per visualizzare solo gli elementi relativi a specifiche normative e standard, soluzioni, tipo di azione, gruppi di valutazione o categorie di protezione dei dati. Il filtraggio della visualizzazione in questo modo consente di filtrare anche il punteggio nel dashboard, mostrando quanti punti sono stati raggiunti fuori dai possibili punti totali in base ai criteri di filtro.

Per applicare i filtri:

1. Selezionare **filtro** sul lato superiore destro del dashboard.
2. Selezionare i criteri di filtro dal riquadro a comparsa **filtri** , quindi fare clic su **applica**.

Dopo aver applicato un filtro, vedrai il tuo punteggio rettificato in tempo reale. La percentuale del Punteggio di conformità e le informazioni di ripartizione e le azioni e le soluzioni di miglioramento, ora riguardano solo i dati trattati dai criteri di filtro. Se si disattiva il Punteggio di conformità, la visualizzazione filtrata rimane quando si effettua l'accesso.

Per rimuovere i filtri:

- Nella sezione **filtri applicati** sopra il Punteggio di conformità, selezionare la **X** accanto al singolo filtro che si desidera rimuovere. o
- Seleziona **filtro** nella parte superiore destra del dashboard, quindi seleziona **Pulisci filtri**.

## <a name="improvement-actions-page"></a>Pagina azioni di miglioramento

Le [azioni di miglioramento](compliance-score-improvement-actions.md) centralizzano le attività di conformità e consentono di allineare le normative e i criteri di protezione dei dati. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione e un collegamento per avviare la soluzione appropriata. Le azioni possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

### <a name="view-your-improvement-actions"></a>Visualizzare le azioni di miglioramento

Il dashboard del Punteggio di conformità Visualizza le **azioni di miglioramento principali**, ovvero quelle con i punti più disponibili che affrontano i problemi più importanti.

Per visualizzare tutte le azioni di miglioramento, selezionare la scheda **azioni di miglioramento** nel dashboard. In alternativa, seleziona **Visualizza tutte le azioni di miglioramento** sotto l'elenco delle azioni di miglioramento chiave nel dashboard.

Se si dispone di un lungo elenco di azioni, potrebbe essere utile filtrare la visualizzazione. Selezionare **filtro** nell'angolo in alto a destra dell'elenco delle azioni. Quando viene visualizzato il riquadro dei **filtri** a comparsa, selezionare i criteri in base alle normative e agli standard, alla soluzione e al gruppo. È inoltre possibile personalizzare la visualizzazione selezionando **gruppo** nell'angolo in alto a destra. Dal menu a discesa, selezionare per visualizzare per gruppo, soluzione, categoria, tipo di azione o stato.

La visualizzazione predefinita per questa pagina non Mostra azioni di miglioramento con uno stato di test **superato**. Per visualizzare le azioni che hanno superato il testing, selezionare la casella **passata** nel riquadro dei filtri a comparsa. Solo le azioni con uno stato di prova del conteggio **superato** verso il punteggio.

Nella pagina azioni di miglioramento vengono visualizzate le seguenti coordinate per ogni azione di miglioramento:

- **Impatto sul punteggio**: i punti in base ai quali il punteggio complessivo aumenterà al termine dell'azione
- **Regolamenti**: il regolamento o la norma pertinente all'azione
- **Gruppo**: gruppo a cui è stata assegnata l'azione
- **Solutions**: la soluzione in cui è possibile accedere per eseguire l'azione
- **Valutazioni**: la valutazione (che consente di organizzare i controlli per soddisfare un determinato obiettivo di conformità) in cui si trova l'azione
- **Categorie**: la categoria relativa alla protezione dei dati (ad esempio, protezione delle informazioni, gestione di dispositivi e così via)
- **Stato del test**:
    - **None** : non è stato registrato alcun aggiornamento dello stato
    - **Non valutato** : il testing non è stato avviato
    - L'implementazione **passata** ha testato correttamente
    - **Esito negativo** dei test a basso rischio non riuscito, rischio basso
    - **Esito** negativo del test di rischio medio non riuscito, rischio medio
    - **Errore di test ad alto rischio** non riuscito, ad alto rischio
    - **Non nell'ambito** – l'azione non rientra nell'ambito della valutazione e non incide sul Punteggio
    - **Per essere rilevato** -per il test manuale, indica che è stata implementata un'azione ma non è stata testata. per il test automatizzato, indica che un'azione è in attesa di risultati dell'automazione
    - **Non è** stato possibile rilevare-non è possibile determinare lo stato automatico
    - **Parzialmente testato** – Punteggio automatizzato che premia i punti parziali
- **Punti conseguiti**: numero di punti ottenuti dal massimo possibile

#### <a name="learn-more"></a>Altre informazioni
[Vedere come assegnare ed eseguire](compliance-score-improvement-actions.md)operazioni di miglioramento.

## <a name="solutions-page"></a>Pagina soluzioni

La pagina soluzioni consente di visualizzare la quota dei punti guadagnati e potenziali organizzati dalla soluzione. La visualizzazione dei punti rimanenti e le azioni di miglioramento da questa visualizzazione consentono di comprendere quali soluzioni richiedono un'attenzione più immediata.

Individuare la pagina soluzioni selezionando la scheda **soluzioni** nel dashboard Punteggio di conformità. È inoltre possibile selezionare **Visualizza tutte le soluzioni** al di sotto delle **soluzioni che influiscono sul punteggio** nella sezione in alto a destra del dashboard.

### <a name="filtering-your-solutions-view"></a>Applicazione del filtro alla visualizzazione soluzioni

Per filtrare la visualizzazione delle soluzioni:

1. Selezionare **filtro** nell'angolo in alto a sinistra dell'elenco di valutazioni.
2. Nel riquadro dei **filtri** a comparsa, inserire un controllo accanto ai criteri desiderati (standard e normative, soluzione, tipo di azione, gruppo di Compliance Manager, categoria).
3. Selezionare il pulsante **applica** . Il riquadro del filtro si chiude e vedrai la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="taking-actions-from-the-solution-page"></a>Esecuzione di azioni dalla pagina della soluzione

Nella pagina soluzioni vengono visualizzate le soluzioni dell'organizzazione connesse alle azioni di miglioramento. Nella tabella sono elencati i contributi di ogni soluzione per il Punteggio globale, i punti di miglioramento dei punteggi conseguiti e possibili all'interno di tale soluzione e il numero di azioni per migliorare che sono state raggruppate in tale soluzione in grado di aumentare il punteggio.

È possibile eseguire un'azione da questa schermata in due modi:

1. Nella riga della soluzione desiderata fare clic sul numero di collegamenti ipertestuali nella colonna **azioni rimanenti** . Verrà visualizzata una visualizzazione filtrata della schermata azioni di miglioramento che mostra le azioni di miglioramento non testate per tale soluzione.

2. Nella riga della soluzione desiderata fare clic su **Apri**nella colonna **Apri soluzione** . Verrà visualizzata la soluzione o la posizione nei centri di sicurezza e conformità di Microsoft 365 e Office 365, in cui è possibile eseguire l'azione consigliata.

## <a name="assessments-page"></a>Pagina valutazioni

La pagina valutazioni elenca tutte le [valutazioni](compliance-score-assessments.md) configurate per l'organizzazione. Il denominatore del Punteggio di conformità è determinato da tutte le valutazioni registrate. Le altre valutazioni aggiunte, le azioni di miglioramento più visibili nella pagina azioni di miglioramento e più alto è il denominatore del punteggio.

In questa pagina vengono riepilogate le informazioni principali su ogni valutazione:

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
3. Selezionare il pulsante Applica. Il riquadro del filtro si chiude e si vedrà la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="default-assessment"></a>Valutazione predefinita

Per impostazione predefinita, nella pagina valutazioni viene visualizzata la valutazione della linea di base per la [protezione dei dati di Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) . Il Punteggio di conformità fornisce anche diversi [modelli](compliance-score-templates.md) pronti per l'uso da cui creare valutazioni.

## <a name="next-step"></a>Passaggio successivo
Personalizzare il Punteggio di conformità mediante l' [impostazione di valutazioni](compliance-score-assessments.md).