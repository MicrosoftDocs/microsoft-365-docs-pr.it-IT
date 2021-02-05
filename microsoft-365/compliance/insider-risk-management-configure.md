---
title: Introduzione alla gestione dei rischi Insider
description: Configurare la gestione dei rischi Insider nell'organizzazione.
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 3a88c48e6915b03316b29d80d2a0f7550d4b5d32
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105163"
---
# <a name="get-started-with-insider-risk-management"></a>Introduzione alla gestione dei rischi Insider

Utilizzare i criteri di gestione dei rischi Insider per identificare le attività rischiose e gli strumenti di gestione per agire sugli avvisi di rischio nell'organizzazione. Completare la procedura seguente per impostare i prerequisiti e configurare un criterio di gestione dei rischi Insider.

>[!IMPORTANT]
>La soluzione di gestione dei rischi insider di Microsoft 365 offre un'opzione a livello di tenant per aiutare i clienti a facilitare la governance interna a livello di utente. Gli amministratori a livello di tenant possono configurare le autorizzazioni per fornire l'accesso a questa soluzione per i membri dell'organizzazione e configurare i connettori dati nel Centro conformità Microsoft 365 per importare dati rilevanti per supportare l'identificazione a livello utente di attività potenzialmente rischiose. I clienti riconoscono che le informazioni dettagliate relative al comportamento, al carattere o alle prestazioni del singolo utente materialmente correlate all'impiego possono essere calcolate dall'amministratore e rese disponibili agli altri utenti dell'organizzazione. Inoltre, i clienti riconoscono di doversi avvalere di un'indagine completa relativa al comportamento, al carattere o alle prestazioni del singolo utente in relazione al rapporto di lavoro e non solo alle informazioni dettagliate del servizio di gestione dei rischi insider. I clienti sono esclusivamente responsabili dell'uso del servizio di gestione dei rischi Insider di Microsoft 365 e di qualsiasi funzionalità o servizio associato in conformità a tutte le leggi applicabili, incluse le leggi relative all'identificazione dei singoli utenti e alle eventuali azioni correttive.

Per ulteriori informazioni su come i criteri di rischio Insider consentono di gestire i rischi nell'organizzazione, vedere Gestione dei rischi [Insider in Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Abbonamenti e licenze

Prima di iniziare a usare la gestione dei rischi Insider, è consigliabile confermare l'abbonamento a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi. Per accedere e usare la gestione dei rischi Insider, l'organizzazione deve disporre di uno dei seguenti abbonamenti o componenti aggiuntivi:

- Abbonamento a Microsoft 365 E5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Conformità Microsoft 365 E5
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Abbonamento a Microsoft 365 A5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Conformità Microsoft 365 A5
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Microsoft 365 A5 Insider Risk Management
- Abbonamento a Microsoft 365 G5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 G5 + componente aggiuntivo conformità Microsoft 365 G5
- Abbonamento a Microsoft 365 G5 + componente aggiuntivo Microsoft 365 G5 Insider Risk Management

Agli utenti inclusi nei criteri di gestione dei rischi Insider deve essere assegnata una delle licenze precedenti.

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si vuole provare la gestione dei rischi Insider, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Passaggio 1: abilitare le autorizzazioni per la gestione dei rischi Insider

>[!Important]
>Dopo aver configurato i gruppi di ruoli, potrebbero essere necessarie fino a 30 minuti prima che le autorizzazioni del gruppo di ruoli si appliino agli utenti assegnati all'interno dell'organizzazione.

Esistono quattro gruppi di ruoli utilizzati per configurare le autorizzazioni per gestire le funzionalità di gestione dei rischi Insider. Per continuare con questi passaggi di configurazione, gli amministratori tenant devono prima assegnarti al gruppo di ruoli **Insider Risk Management** o Insider Risk Management **Admin.** Per accedere e gestire le funzionalità di gestione dei rischi Insider dopo la configurazione iniziale, gli utenti devono essere membri di almeno un gruppo di ruoli di gestione dei rischi Insider.

A seconda della struttura del team di gestione della conformità, sono disponibili opzioni per assegnare utenti a gruppi di ruoli specifici per gestire diversi set di funzionalità di gestione dei rischi Insider. Scegliere tra queste opzioni del gruppo di ruoli quando si configura la gestione dei rischi Insider:

| **Gruppo di ruolo** | **Autorizzazioni di ruolo** |
| :---- | :---------------- |
| **Gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti e investigatori designati, è possibile configurare le autorizzazioni di gestione dei rischi Insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi Insider. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la gestione dei rischi Insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.|
| **Amministratore gestione dei rischi Insider** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi Insider e successivamente per separare gli amministratori dei rischi Insider in un gruppo definito.  Gli utenti di questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider, le impostazioni globali e le assegnazioni dei gruppi di ruoli. |
| **Analisti gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti dei casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti i modelli di avvisi, casi e avvisi per la gestione dei rischi Insider. Non possono accedere a Esplora contenuto con rischio Insider. |
| **Investigatori gestione dei rischi Insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori dei dati di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi Insider, i casi, i modelli di avviso e Esplora contenuto. |

> [!NOTE]
> Questi gruppi di ruoli non sono attualmente supportati in Privileged Identity Management (PIM). Per altre informazioni su PIM, vedere [Assegnare ruoli di Azure AD in Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Aggiungere utenti a un gruppo di ruoli di gestione dei rischi Insider

Completare la procedura seguente per aggiungere utenti a un gruppo di ruoli di gestione dei rischi Insider:

1. Accedere con [https://protection.office.com/permissions](https://protection.office.com/permissions) le credenziali di un account amministratore nell'organizzazione di Microsoft 365.

2. Nel Centro &amp; sicurezza e conformità passare a **Autorizzazioni.** Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli di gestione dei rischi Insider a cui si desidera aggiungere gli utenti, quindi **selezionare Modifica gruppo di ruoli.**

4. Selezionare **Scegli membri** dal riquadro di spostamento a sinistra, quindi selezionare **Modifica.**

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi,** quindi **Fare clic su Fine.**

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare i passaggi.

## <a name="step-2-enable-the-audit-log"></a>Passaggio 2: abilitare il log di controllo

La gestione dei rischi Insider usa i log di controllo per le informazioni dettagliate degli utenti e le attività configurate nei criteri. I log di controllo sono un riepilogo di tutte le attività associate a un criterio di gestione dei rischi Insider o ogni volta che un criterio viene modificato.

Per istruzioni dettagliate su come attivare o disattivare il controllo, vedere Attivare o [disattivare la ricerca nei log di controllo.](turn-audit-log-search-on-or-off.md) Dopo aver attivare il controllo, viene visualizzato un messaggio che indica che il log di controllo è in fase di preparazione e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. È necessario eseguire questa azione una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo, vedere [Search the audit log.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-configure-prerequisites-for-templates"></a>Passaggio 3: Configurare i prerequisiti per i modelli

La maggior parte dei modelli di gestione dei rischi Insider dispone di prerequisiti che devono essere configurati per gli indicatori dei criteri per generare avvisi di attività pertinenti. Configurare i prerequisiti appropriati in base ai criteri che si intende configurare per l'organizzazione.

### <a name="configure-microsoft-365-hr-connector"></a>Configurare il connettore risorse umane di Microsoft 365

La gestione dei rischi Insider supporta l'importazione di dati di utenti e log importati da piattaforme di gestione dei rischi di terze parti e risorse umane. Il connettore dati delle risorse umane di Microsoft 365 consente di estrarre i dati delle risorse umane dai file CSV, incluse le date di fine dell'utente, le date dell'ultimo impiego, le notifiche del piano di miglioramento delle prestazioni, le azioni di revisione delle prestazioni e lo stato di modifica del livello di lavoro. Questi dati consentono di guidare gli indicatori di avviso nei criteri di gestione dei rischi Insider ed è una parte importante della configurazione della copertura completa per la gestione dei rischi nell'organizzazione. Se si configurano più connettori hr per l'organizzazione, la gestione dei rischi Insider estrarrà automaticamente gli indicatori da tutti i connettori hr.

Il connettore risorse umane di Microsoft 365 è necessario quando si utilizzano i modelli di criteri seguenti:

- Rimozione del furto di dati dell'utente
- Violazioni dei criteri di sicurezza da parte degli utenti
- Violazioni dei criteri di sicurezza da parte di utenti scontenti
- Perdite di dati da parte di utenti scontenti

Vedere [l'articolo configurare un connettore](import-hr-data.md) per importare i dati sulle risorse umane per istruzioni dettagliate per configurare il connettore risorse umane di Microsoft 365 per l'organizzazione. Dopo aver configurato il connettore hr, tornare a questi passaggi di configurazione.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurare i criteri di prevenzione della perdita di dati (DLP)

La gestione dei rischi Insider supporta l'utilizzo dei criteri DLP per identificare l'esposizione intenzionale o accidentale di informazioni riservate a parti indesiderate per avvisi DLP di livello elevato di gravità. Quando si configura un criterio di  gestione dei rischi Insider con uno qualsiasi dei modelli di perdita di dati, è necessario assegnare un criterio DLP specifico al criterio.

I criteri DLP consentono di identificare gli utenti per attivare il punteggio dei rischi nella gestione dei rischi Insider per avvisi DLP di gravità elevata per le informazioni riservate e sono una parte importante della configurazione della copertura completa per la gestione dei rischi nell'organizzazione. Per ulteriori informazioni sulla gestione dei rischi Insider e sulle considerazioni sulla pianificazione e sull'integrazione dei criteri DLP, vedere [Criteri di gestione dei rischi Insider.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Assicurarsi di aver completato le operazioni seguenti:
>
>- Si comprende e si configurano correttamente gli utenti nell'ambito sia nei criteri di gestione dei rischi DLP che insider per produrre la copertura dei criteri prevista.
>- Verificare che **l'impostazione dei rapporti** operazioni non consentite nel criterio DLP per la gestione dei rischi Insider utilizzata con questi modelli sia configurata per gli *avvisi* di livello di gravità elevato. Gli avvisi di gestione dei rischi Insider non verranno generati dai criteri DLP con il campo **Rapporti** operazioni non consentite impostato su *Basso* o *Medio.*

È necessario un criterio DLP quando si utilizzano i modelli di criteri seguenti:

- Perdite di dati generali
- Perdite di dati per utenti con priorità

Vedere [l'articolo creare, testare e](create-test-tune-dlp-policy.md) ottimizzare un criterio DLP per istruzioni dettagliate per configurare i criteri DLP per l'organizzazione. Dopo aver configurato un criterio DLP, tornare a questi passaggi di configurazione.

### <a name="configure-priority-user-groups"></a>Configurare i gruppi di utenti con priorità

La gestione dei rischi Insider include il supporto per l'assegnazione di gruppi di utenti prioritari ai criteri per aiutare le attività di rischio univoche dell'identità per gli utenti con posizioni critiche, livelli elevati di dati e accesso alla rete o una cronologia passata del comportamento dei rischi. La creazione di un gruppo di utenti con priorità e l'assegnazione di utenti al gruppo consentono di assegnare criteri di ambito alle circostanze univoche presentate da tali utenti.

Quando si utilizzano i modelli di criteri seguenti, è necessario un gruppo di utenti con priorità:

- Violazioni dei criteri di sicurezza da parte degli utenti con priorità
- Perdite di dati per utenti con priorità

Per istruzioni [dettagliate sulla creazione di un gruppo di](insider-risk-management-settings.md#priority-user-groups-preview) utenti con priorità, vedere l'articolo Introduttivo alle impostazioni di gestione dei rischi Insider. Dopo aver configurato un gruppo di utenti con priorità, tornare a questi passaggi di configurazione.

### <a name="configure-physical-badging-connector-optional"></a>Configurare il connettore di badging fisico (facoltativo)

La gestione dei rischi Insider supporta l'importazione dei dati degli utenti e dei log importati dalle piattaforme di accesso e controllo fisico. Il connettore di badging fisico consente di estrarre i dati di accesso dai file JSON, inclusi ID utente, ID punto di accesso, data e ora di accesso e stato di accesso. Questi dati consentono di guidare gli indicatori di avviso nei criteri di gestione dei rischi Insider ed è una parte importante della configurazione della copertura completa per la gestione dei rischi nell'organizzazione. Se si configurano più connettori di badging fisico per l'organizzazione, la gestione dei rischi Insider estrae automaticamente gli indicatori da tutti i connettori di badging fisico. Le informazioni del connettore di badging fisico integrano altri segnali di rischio Insider quando si utilizzano tutti i modelli di criteri di rischio Insider.

>[!IMPORTANT]
>Per consentire ai criteri di gestione dei rischi Insider di usare e correlare i dati del segnale relativi agli utenti in uscita e terminati con i dati degli eventi dalle piattaforme di accesso e controllo fisico, è necessario configurare anche il connettore risorse umane di Microsoft 365. Se si abilita il connettore di badging fisico senza abilitare il connettore hr di Microsoft 365, i criteri di gestione dei rischi Insider eelaborare solo gli eventi per l'accesso fisico non autorizzato per gli utenti dell'organizzazione.

Per istruzioni dettagliate su come configurare il connettore di badging fisico per l'organizzazione, vedere l'articolo configurare un connettore per importare dati di [badging](import-physical-badging-data.md) fisici. Dopo aver configurato il connettore, tornare a questi passaggi di configurazione.

## <a name="step-4-configure-insider-risk-settings"></a>Passaggio 4: Configurare le impostazioni dei rischi Insider

[Le impostazioni dei rischi](insider-risk-management-settings.md) Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto durante la creazione di un criterio. Le impostazioni vengono configurate usando il **controllo delle** impostazioni dei rischi Insider che si trova nella parte superiore di tutte le schede di gestione dei rischi Insider. Queste impostazioni controllano la privacy, gli indicatori, le finestre di monitoraggio e i rilevamenti intelligenti.

Prima di configurare un criterio, definire le impostazioni di rischio Insider seguenti:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare le impostazioni dei rischi **Insider** nell'angolo in alto a destra di qualsiasi pagina.
2. Nella pagina **Privacy seleziona** un'impostazione di privacy per la visualizzazione dei nomi utente per gli avvisi dei criteri.
3. Nella pagina **Indicatori selezionare** gli indicatori di avviso che si desidera applicare a tutti i criteri di rischio Insider.

    >[!IMPORTANT]
    >Per ricevere avvisi per attività rischiose definite nei criteri, è necessario selezionare uno o più indicatori.

4. Nella pagina Intervallo di tempo [](insider-risk-management-settings.md#policy-timeframes) **dei criteri,** selezionare l'intervallo di tempo per l'applicazione dei criteri per un utente quando attiva una corrispondenza per un criterio di rischio Insider.
5. Nella pagina **Rilevamenti intelligenti configurare le** impostazioni seguenti per i criteri di rischio Insider:
    - [Rilevamenti di anomalie](insider-risk-management-settings.md#anomaly-detections)
    - [Livello volume avviso](insider-risk-management-settings.md#alert-volume)
    - [Stato dell'avviso di Microsoft Defender per endpoint](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Impostazioni del dominio](insider-risk-management-settings.md#domains-preview)
6. Nella pagina **Esporta avvisi** abilitare l'esportazione delle informazioni sugli avvisi per i rischi Insider utilizzando le API di gestione di Office 365, se necessario.
7. Nella pagina **Gruppi di utenti con** priorità creare un gruppo di utenti con priorità e aggiungere gli utenti se non vengono creati nel passaggio **3.**
8. Nella pagina **Flussi di Power Automate** configurare un flusso da modelli di flusso di rischio Insider o creare un nuovo flusso. Per istruzioni [dettagliate,](insider-risk-management-settings.md#power-automate-flows-preview) vedere l'articolo Introduttivo alle impostazioni di gestione dei rischi Insider.
9. Nella pagina **Asset con priorità configurare** le risorse prioritarie per l'utilizzo dei dati della piattaforma di accesso e controllo fisico importati dal connettore di badging fisico. Per istruzioni [dettagliate,](insider-risk-management-settings.md#priority-physical-assets-preview) vedere l'articolo Introduttivo alle impostazioni di gestione dei rischi Insider.
10. Nella pagina **Microsoft Teams** abilitare l'integrazione di Microsoft Teams con la gestione dei rischi Insider per creare automaticamente un team per la collaborazione di utenti o casi. Per istruzioni [dettagliate,](insider-risk-management-settings.md#microsoft-teams-preview) vedere l'articolo Introduttivo alle impostazioni di gestione dei rischi Insider.
11. Selezionare **Salva** per abilitare queste impostazioni per i criteri di rischio Insider.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Passaggio 5: Creare un criterio di gestione dei rischi Insider

I criteri di gestione dei rischi Insider includono gli utenti assegnati e definiscono i tipi di indicatori di rischio configurati per gli avvisi. Prima che le attività possano attivare avvisi, è necessario configurare un criterio.

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Criteri.
2. Selezionare **Crea criterio** per aprire la procedura guidata dei criteri.
3. Nella pagina **Nuovi criteri di rischio Insider,** completare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il criterio.
    - **Descrizione (facoltativo):** immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio):** selezionare uno dei modelli di [criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio monitorati dal criterio.

    >[!IMPORTANT]
    >La maggior parte dei modelli di criteri dispone di prerequisiti che devono essere configurati per il criterio per generare avvisi pertinenti. Se non sono stati configurati i prerequisiti dei criteri applicabili, vedere **il passaggio 3** precedente.

4. Selezionare **Avanti** per continuare.
5. Nella pagina **Utenti**  selezionare Aggiungi utente  o gruppo o Scegli gruppi di utenti con priorità per definire quali utenti o gruppi di utenti con priorità sono inclusi nel criterio, a seconda del modello di criteri selezionato. Selezionare la casella di controllo Tutti gli utenti e i gruppi **abilitati** alla posta elettronica, se applicabile (se non è stato selezionato un modello basato sull'utente con priorità). Selezionare **Avanti** per continuare.
6. Nella pagina Specificare il contenuto di cui definire la priorità **(facoltativo)** è possibile assegnare le origini per definire la priorità per un aumento dei punteggi di rischio. Tuttavia, alcune attività non genereranno un avviso a meno che il contenuto correlato non contenga tipi di informazioni sensibili predefiniti o personalizzati o non sia stato specificato come priorità in questa pagina:
    - **Siti di SharePoint:** selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint di cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni sensibili:** seleziona **Aggiungi tipo di informazioni sensibili** e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza:** selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Riservato"* *e "Segreto".*
7. Selezionare **Avanti** per continuare.
8. Nella pagina **Seleziona indicatori di** criteri [](insider-risk-management-settings.md#indicators) verranno visualizzati gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato *un* modello di perdita di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP nell'elenco a discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio. Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare le soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato. Se è stato selezionato almeno  un indicatore di *Office* o dispositivo, selezionare gli indicatori del punteggio **di rischio in base** alle esigenze. I punteggi di rischio sono applicabili solo per gli indicatori selezionati.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri nella pagina Indicatori dei criteri delle impostazioni di gestione dei rischi  >    >   Insider.

9. Selezionare **Avanti** per continuare.
10. Nella pagina **Intervallo di tempo dei** criteri, vedrai le condizioni della finestra di attivazione per il criterio nella pagina Impostazioni dei rischi **Insider** Intervallo di tempo [](insider-risk-management-settings.md#policy-timeframes)  >  **dei** criteri.
11. Selezionare **Avanti** per continuare.
12. Nella pagina **Revisione** esaminare le impostazioni scelte per il criterio. Selezionare **Modifica** per modificare uno qualsiasi dei valori dei criteri oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato questi passaggi per creare il primo criterio di gestione dei rischi Insider, inizierai a ricevere avvisi dagli indicatori di attività dopo circa 24 ore. Configurare criteri aggiuntivi in base alle esigenze usando le indicazioni del passaggio 4 di questo articolo o i passaggi descritti in [Creare un nuovo criterio di rischio Insider.](insider-risk-management-policies.md#create-a-new-policy)

Per ulteriori informazioni sull'analisi degli avvisi per i rischi Insider e sul **dashboard degli** avvisi, vedere Avvisi per la gestione dei [rischi Insider.](insider-risk-management-alerts.md)
