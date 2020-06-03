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
ms.openlocfilehash: e8c8783a570fe1b747ba8d2cf07f7d7f6f2fe39f
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515763"
---
# <a name="get-started-with-insider-risk-management"></a>Introduzione alla gestione dei rischi Insider

Usare i criteri di gestione dei rischi Insider per identificare attività rischiose e strumenti di gestione per intervenire sugli avvisi di rischio nell'organizzazione. Completare la procedura seguente per impostare i prerequisiti e configurare un criterio di gestione dei rischi Insider.

>[!IMPORTANT]
>La soluzione Microsoft 365 Insider Risk Management fornisce un'opzione tenant level per consentire ai clienti di facilitare la governance interna a livello di utente. Gli amministratori dei livelli tenant possono configurare le autorizzazioni per consentire l'accesso a questa soluzione per i membri dell'organizzazione e configurare i connettori dei dati nel centro conformità di Microsoft 365 per importare i dati rilevanti per supportare l'identificazione a livello di utente di attività potenzialmente rischiose. I clienti possono essere calcolati dall'amministratore e resi disponibili ad altri utenti dell'organizzazione, in base al comportamento, al carattere o alle prestazioni del singolo utente.

Per ulteriori informazioni su come i criteri di rischio Insider consentono di gestire i rischi nell'organizzazione, vedere [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare a utilizzare la gestione dei rischi Insider, è necessario confermare la [sottoscrizione Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi. Per accedere e utilizzare Gestione dei rischi Insider, è necessario che l'organizzazione disponga di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 E3 + il componente aggiuntivo Microsoft 365 E5 Compliance
- Sottoscrizione Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Compliance
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Insider Risk Management

Gli utenti inclusi nei criteri di gestione dei rischi Insider devono essere assegnati a una delle licenze sopra riportate.

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera tentare la gestione dei rischi Insider, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla sottoscrizione esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Passaggio 1 (obbligatorio): abilitare le autorizzazioni per la gestione dei rischi Insider

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

1. Accedere all' [https://protection.office.com/permissions](https://protection.office.com/permissions) utilizzo delle credenziali per un account di amministratore nell'organizzazione Microsoft 365. "" "" "" ""

2. Nel centro sicurezza &amp; e conformità, accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli Gestione dei rischi Insider a cui si desidera aggiungere gli utenti, quindi selezionare **modifica gruppo di ruoli**.

4. Selezionare **Scegli membri** nel riquadro di spostamento a sinistra, quindi selezionare **modifica**.

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi**, quindi fare clic su **fine**.

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.

## <a name="step-2-required-enable-the-audit-log"></a>Passaggio 2 (obbligatorio): abilitare il log di controllo

Insider Risk Management utilizza i registri di controllo per le informazioni e le attività dell'utente configurate nei criteri. I registri di controllo sono un riepilogo di tutte le attività associate a un criterio di gestione dei rischi insider o in qualsiasi momento modifiche di un criterio.

Per istruzioni dettagliate su come abilitare il controllo, vedere [attivazione o disattivazione della ricerca del registro di controllo](turn-audit-log-search-on-or-off.md). Dopo aver attivato il controllo, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. È sufficiente eseguire questa operazione una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-configure-prerequisites-for-templates"></a>Passaggio 3 (facoltativo): configurare i prerequisiti per i modelli

Alcuni modelli di gestione dei rischi Insider sono prerequisiti che devono essere configurati per gli indicatori dei criteri per generare avvisi attività rilevanti. Configurare i prerequisiti adeguati a seconda dei criteri che si intende configurare per l'organizzazione.

### <a name="configure-microsoft-365-hr-connector"></a>Configurare il connettore Microsoft 365 HR

Gestione dei rischi Insider supporta l'importazione di dati di utenti e log importati da piattaforme di gestione dei rischi di terze parti. Il connettore dati risorse umane (HR) di Microsoft 365 consente di inserire i dati delle risorse umane da file CSV, tra cui la terminazione degli utenti e le date dell'ultima occupazione. Questi dati consentono di indirizzare gli indicatori di avviso nei criteri di gestione dei rischi Insider ed è una parte importante della configurazione della copertura di gestione a rischio completo nell'organizzazione.

Vedere l'argomento [set up a Connector to Import HR data](import-hr-data.md) for Step-by-Step Guide to configure the Microsoft 365 HR Connector for Your Organization. Dopo aver configurato il connettore HR, tornare a questi passaggi di configurazione.

>[!IMPORTANT]
>Se si configura un criterio utilizzando il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri. Se si configurano più connettori HR per la propria organizzazione, la gestione dei rischi Insider tirerà automaticamente gli indicatori da tutti i connettori HR.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurare i criteri di prevenzione della perdita di dati (DLP)

Gestione dei rischi Insider supporta l'utilizzo di criteri DLP per identificare l'esposizione intenzionale o accidentale di informazioni riservate a parti indesiderate per avvisi DLP a livello di gravità elevato. Quando si configura un criterio di gestione dei rischi Insider con il modello di **perdita di dati** , è necessario assegnare un criterio DLP specifico al criterio.

Questo criterio consente di instradare gli indicatori di gestione dei rischi Insider per gli avvisi High Severity DLP per informazioni riservate ed è una parte importante della configurazione della copertura di gestione dei rischi nell'organizzazione. Per ulteriori informazioni sulla gestione dei rischi Insider e sull'integrazione e sulla pianificazione di criteri DLP, vedere [Insider Risk Management Policies](insider-risk-management-policies.md#data-leaks).

>[!IMPORTANT]
>Assicurarsi di aver completato le operazioni seguenti:
>
>- È possibile comprendere e configurare correttamente gli utenti in ambito sia nei criteri di gestione del rischio DLP che insider per produrre la copertura dei criteri prevista.
>- Verificare che l'impostazione dei **rapporti sugli incidenti** nei criteri DLP per la gestione dei rischi Insider utilizzati con questo modello sia configurata per gli avvisi a livello di gravità *elevato* . Gli avvisi di gestione dei rischi insider non verranno generati da criteri DLP con il campo **rapporto eventi** non consentiti impostato su *basso* o *medio*.

Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'argomento [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) . Dopo aver configurato un criterio DLP, tornare a questi passaggi di configurazione.

## <a name="step-4-required-configure-insider-risk-settings"></a>Passaggio 4 (obbligatorio): configurare le impostazioni dei rischi Insider

[Le impostazioni dei rischi Insider](insider-risk-management-policies.md#policy-settings) si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto quando si crea un criterio. Le impostazioni vengono configurate utilizzando il controllo **impostazioni di rischio Insider** nella parte superiore di tutte le schede gestione rischi Insider. Queste impostazioni controllano la privacy, gli indicatori, le finestre di monitoraggio e i rilevamenti intelligenti.

Prima di configurare un criterio, definire le seguenti impostazioni di rischio Insider:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com), passare a **Insider Risk Management** e selezionare **impostazioni di rischio Insider** dall'angolo in alto a destra di qualsiasi pagina.
2. Nella pagina **privacy** , selezionare un'impostazione di privacy per la visualizzazione dei nomi utente per gli avvisi dei criteri.
3. Nella pagina **indicatori** selezionare gli indicatori di avviso che si desidera applicare a tutti i criteri di rischio Insider.

    >[!IMPORTANT]
    >Per ricevere gli avvisi per le attività a rischio definite nei criteri, è necessario selezionare uno o più indicatori.

4. Nella pagina **scadenze dei criteri** selezionare i [tempi](insider-risk-management-policies.md#policy-timeframes) di applicazione per l'esecuzione di un utente quando si attiva una corrispondenza per un criterio di rischio Insider.
5. Nella pagina **rilevamento intelligente** , configurare il rilevamento di [anomalie, il rilevamento di lingua offensiva e il livello di volume degli avvisi](insider-risk-management-policies.md#intelligent-detections) per i criteri di rischio Insider.
6. Selezionare **Salva** per abilitare queste impostazioni per i criteri di rischio Insider.

## <a name="step-5-required-create-an-insider-risk-management-policy"></a>Passaggio 5 (obbligatorio): creare un criterio di gestione dei rischi Insider

I criteri di gestione dei rischi Insider includono gli utenti assegnati e definiscono i tipi di indicatori di rischio configurati per gli avvisi. Prima che le attività possano attivare gli avvisi, è necessario configurare un criterio.

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nella pagina **nuovo criterio di rischio Insider** completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio.
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >Se si seleziona il modello per le *perdite di dati* , sarà necessario configurare almeno un criterio DLP che verrà assegnato in un secondo momento nella procedura guidata. Se si seleziona il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri.

4. Fare clic su **Avanti** per continuare.
5. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** per definire quali utenti sono inclusi nel criterio oppure selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini a priorità per le attività degli utenti a rischio:
    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate**: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **indicatori di avviso** , verranno visualizzati gli indicatori definiti nella pagina indicatori **impostazioni di rischio Insider**  >  **Indicators** . Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
9. Nella pagina **selezione finestra di monitoraggio** , verranno visualizzate le [condizioni della finestra di monitoraggio](insider-risk-management-policies.md#policy-timeframes) per il criterio che si trova nella pagina scadenze dei criteri di **rischio Insider**  >  **Policy timeframes** . Se è stato selezionato il modello dei criteri per il *furto dei dati* per i dipendenti in uscita, è possibile selezionare la casella di *controllo Controlla la terminazione del post attività* per rilevare l'attività dopo la data di fine importata dal connettore Microsoft 365 HR.
10. Fare clic su **Avanti** per continuare.
11. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per creare e attivare il criterio.

Dopo aver completato questa procedura per creare il primo criterio di gestione dei rischi Insider, si inizierà a ricevere avvisi da indicatori di attività dopo circa 24 ore. Configurare ulteriori criteri in base alle istruzioni fornite nel passaggio 4 di questo argomento o la procedura descritta in [creare un nuovo criterio di rischio Insider](insider-risk-management-policies.md#create-a-new-policy).
