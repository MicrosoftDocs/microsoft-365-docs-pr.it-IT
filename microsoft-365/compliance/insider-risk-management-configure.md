---
title: Introduzione alla gestione dei rischi Insider
description: Configurare la gestione dei rischi Insider nell'organizzazione.
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: c53bfa58e36b2723d5227c38805482dcb629d864
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199690"
---
# <a name="get-started-with-insider-risk-management"></a>Introduzione alla gestione dei rischi Insider

Utilizzare i criteri di gestione dei rischi Insider per identificare le attività rischiose e gli strumenti di gestione per agire sugli avvisi di rischio nell'organizzazione. Completare la procedura seguente per impostare i prerequisiti e configurare un criterio di gestione dei rischi Insider.

>[!IMPORTANT]
>La soluzione Microsoft 365 Insider Risk Management fornisce un'opzione tenant level per consentire ai clienti di facilitare la governance interna a livello di utente. Gli amministratori dei livelli tenant possono configurare le autorizzazioni per consentire l'accesso a questa soluzione per i membri dell'organizzazione e configurare i connettori dei dati nel centro conformità di Microsoft 365 per importare i dati rilevanti per supportare l'identificazione a livello di utente di attività potenzialmente rischiose. I clienti possono essere calcolati dall'amministratore e resi disponibili ad altri utenti dell'organizzazione, in base al comportamento, al carattere o alle prestazioni del singolo utente.

Per ulteriori informazioni su come i criteri di rischio Insider consentono di gestire i rischi nell'organizzazione, vedere [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Informazioni preliminari

Prima di iniziare a utilizzare la gestione dei rischi Insider, è necessario confermare la [sottoscrizione Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi. Per accedere e utilizzare Gestione dei rischi Insider, è necessario che l'organizzazione disponga di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 E3 + il componente aggiuntivo Microsoft 365 E5 Compliance
- Sottoscrizione Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Compliance
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Insider Risk Management

Gli utenti inclusi nei criteri di gestione dei rischi Insider devono essere assegnati a una delle licenze sopra riportate.

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera tentare la gestione dei rischi Insider, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla sottoscrizione esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Passaggio 1: abilitare le autorizzazioni per la gestione dei rischi Insider

Sono disponibili quattro gruppi di ruoli che consentono di configurare le autorizzazioni per gestire le funzionalità di gestione dei rischi Insider. Per continuare con questi passaggi di configurazione, è necessario che gli amministratori del tenant debbano prima assegnare il gruppo di ruoli amministratore di gestione dei rischi **Insider** Management o **Insider Management** . Per accedere e gestire le funzionalità di gestione dei rischi Insider dopo la configurazione iniziale, è necessario che gli utenti siano membri di almeno un gruppo di ruoli Gestione dei rischi Insider.

A seconda della struttura del team di gestione della conformità, sono disponibili opzioni per assegnare gli utenti a specifici gruppi di ruoli per gestire diversi insiemi di funzionalità di gestione dei rischi Insider. Scegliere da queste opzioni del gruppo di ruolo durante la configurazione della gestione dei rischi Insider:

| **Gruppo di ruolo** | **Autorizzazioni di ruolo** |
| :---- | :---------------- |
| **Gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per la propria organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per gli amministratori, gli analisti e gli investigatori designati, è possibile configurare le autorizzazioni di gestione dei rischi insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di gestione dei rischi Insider. Questa configurazione è il modo più semplice per iniziare rapidamente con la gestione dei rischi Insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.|
| **Amministratore di gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi Insider e successivamente per separare gli amministratori del rischio insider in un gruppo definito.  Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider, le impostazioni globali e le assegnazioni di gruppi di ruoli. |
| **Analisti di gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti dei casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti i modelli di avvisi, casi e notifiche di gestione dei rischi Insider. Non possono accedere all'esploratore di contenuto a rischio Insider. |
| **Investigatori della gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare le autorizzazioni agli utenti che agiranno come investigatori dei dati di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi Insider, i casi, i modelli di avvisi e l'Esplora contenuto per tutti i casi. |

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Aggiungere gli utenti a un gruppo di ruoli di gestione dei rischi Insider

Completare la procedura seguente per aggiungere gli utenti a un gruppo di ruoli di gestione dei rischi Insider:

1. Accedere [https://protection.office.com/permissions](https://protection.office.com/permissions) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro sicurezza &amp; e conformità, accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli Gestione dei rischi Insider a cui si desidera aggiungere gli utenti, quindi selezionare **modifica gruppo di ruoli**.

4. Selezionare **Scegli membri** nel riquadro di spostamento a sinistra, quindi selezionare **modifica**.

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi**, quindi fare clic su **fine**.

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.

## <a name="step-2-enable-the-audit-log"></a>Passaggio 2: abilitare il log di controllo

Insider Risk Management utilizza i registri di controllo per le informazioni e le attività dell'utente configurate nei criteri. I registri di controllo sono un riepilogo di tutte le attività associate a un criterio di gestione dei rischi insider o in qualsiasi momento della modifica di un criterio.

Per istruzioni dettagliate su come abilitare il controllo, vedere [attivazione o disattivazione della ricerca del registro di controllo](turn-audit-log-search-on-or-off.md). Dopo aver attivato il controllo, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. È sufficiente eseguire questa operazione una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-configure-prerequisites-for-templates"></a>Passaggio 3: configurare i prerequisiti per i modelli

La maggior parte dei modelli di gestione del rischio Insider sono prerequisiti che devono essere configurati per gli indicatori dei criteri per generare avvisi attività rilevanti. Configurare i prerequisiti adeguati a seconda dei criteri che si intende configurare per l'organizzazione.

Se si sta configurando un criterio utilizzando la *lingua offensiva nel modello di criteri di posta elettronica* , è possibile ignorare questo passaggio e passare direttamente al **passaggio 4**.

### <a name="configure-microsoft-365-hr-connector"></a>Configurare il connettore Microsoft 365 HR

Gestione dei rischi Insider supporta l'importazione di dati di utenti e log importati da piattaforme di gestione dei rischi di terze parti. Il connettore di dati HR (Human Resources) Microsoft 365 consente di inserire i dati delle risorse umane da file CSV, incluse le date di terminazione degli utenti, le date dell'ultimo impiego, le notifiche relative al piano di miglioramento delle prestazioni, le azioni di revisione delle prestazioni e lo stato delle modifiche a livello di Questi dati consentono di indirizzare gli indicatori di avviso nei criteri di gestione dei rischi Insider ed è una parte importante della configurazione della copertura di gestione a rischio completo nell'organizzazione. Se si configurano più connettori HR per la propria organizzazione, la gestione dei rischi Insider tirerà automaticamente gli indicatori da tutti i connettori HR.
Il connettore Microsoft 365 HR è necessario quando si utilizzano i modelli di criteri seguenti:

- Furto dei dati degli utenti da parte dell'utente
- Violazioni dei criteri di sicurezza da parte degli utenti
- Violazioni dei criteri di sicurezza da parte di utenti scontenti
- Perdite di dati da parte di utenti scontenti

Vedere l'articolo [set up a Connector to Import HR data](import-hr-data.md) per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per la propria organizzazione. Dopo aver configurato il connettore HR, tornare a questi passaggi di configurazione.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurare i criteri di prevenzione della perdita di dati (DLP)

Gestione dei rischi Insider supporta l'utilizzo di criteri DLP per identificare l'esposizione intenzionale o accidentale di informazioni riservate a parti indesiderate per avvisi DLP a livello di gravità elevato. Quando si configura un criterio di gestione dei rischi Insider con qualsiasi modello di **perdita di dati** , è necessario assegnare un criterio DLP specifico al criterio.

I criteri DLP consentono di identificare gli utenti per attivare la valutazione dei rischi nella gestione dei rischi Insider per gli avvisi DLP di elevata gravità per informazioni riservate e sono una parte importante della configurazione della copertura di gestione a rischio completo nell'organizzazione. Per ulteriori informazioni sulla gestione dei rischi Insider e sull'integrazione e sulla pianificazione di criteri DLP, vedere [Insider Risk Management Policies](insider-risk-management-policies.md#general-data-leaks).

>[!IMPORTANT]
>Assicurarsi di aver completato le operazioni seguenti:
>
>- È possibile comprendere e configurare correttamente gli utenti in ambito sia nei criteri di gestione del rischio DLP che insider per produrre la copertura dei criteri prevista.
>- Verificare che l'impostazione dei **rapporti sugli incidenti** nei criteri DLP per la gestione dei rischi Insider utilizzati con questi modelli sia configurata per gli avvisi a livello di gravità *elevato* . Gli avvisi di gestione dei rischi insider non verranno generati da criteri DLP con il campo **rapporto eventi** non consentiti impostato su *basso* o *medio*.

Quando si utilizzano i seguenti modelli di criteri, è necessario un criterio DLP:

- Perdite di dati generali
- Perdite di dati da parte di utenti prioritari

Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'articolo [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) . Dopo aver configurato un criterio DLP, tornare a questi passaggi di configurazione.

### <a name="configure-priority-user-groups"></a>Configurare i gruppi di utenti prioritari

Gestione dei rischi Insider include il supporto per l'assegnazione di gruppi di utenti prioritari ai criteri che consentono di identificare le attività a rischio univoco per gli utenti con posizioni critiche, livelli elevati di dati e accesso alla rete o una cronologia del comportamento dei rischi. Creazione di un gruppo di utenti prioritari e assegnazione degli utenti ai criteri di ambito della Guida per i gruppi in base alle circostanze esclusive presentate da tali utenti.

Un gruppo di utenti prioritari è necessario quando si utilizzano i modelli di criteri seguenti:

- Violazioni dei criteri di sicurezza per gli utenti con priorità 
- Perdite di dati da parte di utenti prioritari

Per informazioni dettagliate su come creare un gruppo di utenti prioritari, vedere l'articolo [Introduzione alle impostazioni di gestione dei rischi Insider](insider-risk-management-settings.md#priority-user-groups-preview) . Dopo aver configurato un gruppo di utenti prioritari, tornare a questi passaggi di configurazione.

## <a name="step-4-configure-insider-risk-settings"></a>Passaggio 4: configurare le impostazioni dei rischi Insider

[Le impostazioni dei rischi Insider](insider-risk-management-settings.md) si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto quando si crea un criterio. Le impostazioni vengono configurate utilizzando il controllo **impostazioni di rischio Insider** nella parte superiore di tutte le schede gestione rischi Insider. Queste impostazioni controllano la privacy, gli indicatori, le finestre di monitoraggio e i rilevamenti intelligenti.

Prima di configurare un criterio, definire le seguenti impostazioni di rischio Insider:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), passare a **Insider Risk Management** e selezionare **impostazioni di rischio Insider** dall'angolo in alto a destra di qualsiasi pagina.
2. Nella pagina **privacy** , selezionare un'impostazione di privacy per la visualizzazione dei nomi utente per gli avvisi dei criteri.
3. Nella pagina **indicatori** selezionare gli indicatori di avviso che si desidera applicare a tutti i criteri di rischio Insider.

    >[!IMPORTANT]
    >Per ricevere gli avvisi per le attività a rischio definite nei criteri, è necessario selezionare uno o più indicatori.

4. Nella pagina **scadenze dei criteri** selezionare i [tempi](insider-risk-management-settings.md#policy-timeframes) di applicazione per l'esecuzione di un utente quando si attiva una corrispondenza per un criterio di rischio Insider.
5. Nella pagina **rilevamento intelligente** , configurare le seguenti impostazioni per i criteri di rischio Insider:
    - [Rilevamenti di anomalia](insider-risk-management-settings.md#anomaly-detections)
    - [Rilevamenti di lingua offensiva](insider-risk-management-settings.md#offensive-language-detections)
    - [Livello volume avvisi](insider-risk-management-settings.md#alert-volume)
    - [Stato avviso Microsoft 365 Defender Advanced Threat Protection](insider-risk-management-settings.md#microsoft-defender-advanced-threat-protection-preview)
    - [Impostazioni del dominio](insider-risk-management-settings.md#domains-preview)
6. Nella pagina **Esporta avvisi** , abilitare l'esportazione delle informazioni di avviso sui rischi Insider mediante le API di gestione di Office 365, se necessario.
7. Nella pagina **gruppi di utenti con priorità** creare un gruppo di utenti prioritari e aggiungere gli utenti se non sono stati creati nel **passaggio 3**.
8. Selezionare **Salva** per abilitare queste impostazioni per i criteri di rischio Insider.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Passaggio 5: creare un criterio di gestione dei rischi Insider

I criteri di gestione dei rischi Insider includono gli utenti assegnati e definiscono i tipi di indicatori di rischio configurati per gli avvisi. Prima che le attività possano attivare gli avvisi, è necessario configurare un criterio.

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nella pagina **nuovo criterio di rischio Insider** completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio.
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >La maggior parte dei modelli di criteri ha prerequisiti che devono essere configurati per il criterio per generare avvisi rilevanti. Se non sono stati configurati i prerequisiti per i criteri applicabili, vedere il **passaggio 3** sopra riportato.

4. Fare clic su **Avanti** per continuare.
5. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** oppure **scegliere gruppi** di utenti prioritari per definire quali utenti o gruppi di priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** , se applicabile (se non è stato selezionato un modello di priorità basato sull'utente). Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini alla priorità per i punteggi di rischio aumentati. Tuttavia, alcune attività non genereranno alcun avviso, a meno che il contenuto correlato contenga tipi di informazioni riservate incorporate o personalizzati o sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate**: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **Selezione indicatori di criteri** verranno visualizzati gli [indicatori](insider-risk-management-settings.md#indicators) definiti come disponibili nella pagina indicatori **impostazioni di rischio Insider**  >  **Indicators** . Se all'inizio della procedura guidata è stato selezionato un modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non utilizzare le impostazioni predefinite della soglia dei criteri per questi indicatori, disabilitare le **soglie di utilizzo predefinite consigliate da Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno un indicatore di *Office* o *dispositivo* , selezionare i **Booster del Punteggio di rischio** in base alle esigenze. I booster del Punteggio di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se non è possibile selezionare gli indicatori in questa pagina, è necessario scegliere gli indicatori che si desidera abilitare per tutti i criteri nella pagina indicatori dei criteri di **gestione dei rischi Insider Management**  >  **Settings**  >  **Policy indicators** .

9. Fare clic su **Avanti** per continuare.
10. Nella pagina **scadenze** dei criteri verranno visualizzate le condizioni per la [finestra di attivazione](insider-risk-management-settings.md#policy-timeframes) per il criterio che si trova nella pagina scadenze dei criteri di **rischio Insider**  >  **Policy timeframes** .
11. Fare clic su **Avanti** per continuare.
12. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per creare e attivare il criterio.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato questa procedura per creare il primo criterio di gestione dei rischi Insider, si inizierà a ricevere avvisi da indicatori di attività dopo circa 24 ore. Configurare ulteriori criteri in base alle esigenze utilizzando le indicazioni contenute nel passaggio 4 di questo articolo o la procedura descritta in [creare un nuovo criterio di rischio Insider](insider-risk-management-policies.md#create-a-new-policy).

Per ulteriori informazioni sull'analisi degli avvisi sui rischi Insider e sul **Dashboard avvisi**, vedere [Insider Risk Management Alerts](insider-risk-management-alerts.md).