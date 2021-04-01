---
title: Introduzione alla gestione dei rischi Insider
description: Configurare la gestione dei rischi insider nell'organizzazione.
keywords: Microsoft 365, gestione dei rischi insider, gestione dei rischi, conformità
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
ms.openlocfilehash: 9e1b7a18bea09d10cb133ce9106df45533a72172
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445230"
---
# <a name="get-started-with-insider-risk-management"></a>Introduzione alla gestione dei rischi Insider

Utilizzare i criteri di gestione dei rischi insider per identificare le attività rischiose e gli strumenti di gestione per agire sugli avvisi di rischio nell'organizzazione. Completare la procedura seguente per configurare i prerequisiti e configurare un criterio di gestione dei rischi insider.

>[!IMPORTANT]
>La soluzione di gestione dei rischi insider di Microsoft 365 offre un'opzione a livello di tenant per aiutare i clienti a facilitare la governance interna a livello utente. Gli amministratori a livello di tenant possono configurare le autorizzazioni per fornire l'accesso a questa soluzione ai membri dell'organizzazione e configurare i connettori dati nel Centro conformità Microsoft 365 per importare dati rilevanti per supportare l'identificazione a livello utente di attività potenzialmente rischiose. I clienti riconoscono che le informazioni dettagliate relative al comportamento, al carattere o alle prestazioni del singolo utente materialmente correlate all'impiego possono essere calcolate dall'amministratore e rese disponibili agli altri utenti dell'organizzazione. Inoltre, i clienti riconoscono che devono condurre una propria indagine completa relativa al comportamento, al carattere o alle prestazioni del singolo utente in modo materiale correlato all'impiego e non si basano solo sulle informazioni del servizio di gestione dei rischi insider. I clienti sono responsabili esclusivamente dell'utilizzo del servizio di gestione dei rischi insider di Microsoft 365 e di qualsiasi funzionalità o servizio associato in conformità a tutte le leggi applicabili, incluse le leggi relative all'identificazione dei singoli utenti e alle eventuali azioni di correzione.

Per ulteriori informazioni su come i criteri di rischio insider possono aiutare a gestire i rischi nell'organizzazione, vedere [Insider risk management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Abbonamenti e licenze

Prima di iniziare a usare la gestione dei rischi insider, è consigliabile confermare l'abbonamento [a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e tutti i componenti aggiuntivi. Per accedere e usare la gestione dei rischi insider, l'organizzazione deve disporre di uno dei seguenti abbonamenti o componenti aggiuntivi:

- Abbonamento a Microsoft 365 E5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Conformità Microsoft 365 E5
- Abbonamento a Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Abbonamento a Microsoft 365 A5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Conformità microsoft 365 A5
- Abbonamento a Microsoft 365 A3 + componente aggiuntivo Microsoft 365 A5 Insider Risk Management
- Abbonamento a Microsoft 365 G5 (versione di valutazione o a pagamento)
- Abbonamento a Microsoft 365 G3 + componente aggiuntivo Conformità Microsoft 365 G5
- Abbonamento a Microsoft 365 G3 + componente aggiuntivo Microsoft 365 G5 Insider Risk Management
- Abbonamento a Office 365 E3 + Enterprise Mobility and Security E3 + componente aggiuntivo Conformità Microsoft 365 E5

Agli utenti inclusi nei criteri di gestione dei rischi insider deve essere assegnata una delle licenze precedenti.

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera provare la gestione dei rischi insider, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [a](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Passaggio 1: Abilitare le autorizzazioni per la gestione dei rischi insider

>[!Important]
>Dopo aver configurato i gruppi di ruoli, potrebbero essere necessarie fino a 30 minuti per applicare le autorizzazioni del gruppo di ruoli agli utenti assegnati all'interno dell'organizzazione.

Esistono quattro gruppi di ruoli utilizzati per configurare le autorizzazioni per gestire le funzionalità di gestione dei rischi insider. Per continuare con questi passaggi di configurazione, gli amministratori tenant devono prima assegnarti al gruppo di ruoli **Insider Risk Management** o Insider Risk Management **Admin.** Per accedere e gestire le funzionalità di gestione dei rischi insider dopo la configurazione iniziale, gli utenti devono essere membri di almeno un gruppo di ruoli di gestione dei rischi insider.

A seconda della struttura del team di gestione della conformità, è possibile assegnare utenti a specifici gruppi di ruolo per gestire diversi insiemi di funzionalità della gestione dei rischi Insider. Per visualizzare  la scheda Autorizzazioni nel Centro sicurezza & e conformità di Office 365  e gestire i gruppi di ruoli, è necessario essere assegnati al gruppo di ruoli Gestione organizzazione o assegnare il ruolo Gestione *ruoli.* Scegliere tra queste opzioni del gruppo di ruoli durante la configurazione della gestione dei rischi insider:

| **Gruppo di ruolo** | **Autorizzazioni di ruolo** |
| :------------- | :------------------- |
| **Insider Risk Management** | Usare questo gruppo di ruoli per la gestione dei rischi Insider per la propria organizzazione in un unico gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e revisori designati, è possibile configurare le autorizzazioni di gestione dei rischi insider in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione per la gestione dei rischi insider e le autorizzazioni associate. Questa configurazione è il modo più semplice per iniziare rapidamente a usare la gestione dei rischi insider ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi distinti di utenti. |
| **Insider Risk Management Admin** | Utilizzare questo gruppo di ruoli per configurare inizialmente la gestione dei rischi insider e successivamente per separare gli amministratori dei rischi insider in un gruppo definito. Gli utenti di questo gruppo di ruoli possono abilitare e visualizzare informazioni analitiche e creare, leggere, aggiornare ed eliminare criteri di gestione dei rischi insider, impostazioni globali e assegnazioni di gruppi di ruoli. |
| **Analisti gestione dei rischi Insider** | Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da analisti di casi di rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere e visualizzare tutti gli avvisi, i casi, le informazioni analitiche e i modelli di avvisi per la gestione dei rischi insider. Non possono accedere a Esplora contenuto a rischio insider. |
| **Investigatori gestione dei rischi Insider** | Usare questo gruppo per assegnare le autorizzazioni agli utenti che fungeranno da investigatori dei dati relativi al rischio Insider. Gli utenti di questo gruppo di ruoli possono accedere a tutti gli avvisi di gestione dei rischi insider, i casi, i modelli di avviso e Esplora contenuto per tutti i casi. |
| **Revisori della gestione dei rischi insider** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che controllano le attività di gestione dei rischi insider. Gli utenti di questo gruppo di ruoli possono accedere al log di controllo dei rischi insider. |

> [!NOTE]
> Questi gruppi di ruoli non sono attualmente supportati in Privileged Identity Management (PIM). Per altre informazioni su PIM, vedere [Assegnare ruoli di Azure AD in Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Aggiungere utenti a un gruppo di ruoli di gestione dei rischi insider

Completare i passaggi seguenti per aggiungere utenti a un gruppo di ruoli di gestione dei rischi insider:

1. Accedere usando [https://protection.office.com/permissions](https://protection.office.com/permissions) le credenziali per un account amministratore nell'organizzazione di Microsoft 365.

2. Nel Centro &amp; sicurezza e conformità passare a **Autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli di gestione dei rischi insider a cui si desidera aggiungere utenti, quindi selezionare **Modifica gruppo di ruoli.**

4. Selezionare **Scegli membri** nel riquadro di spostamento sinistro, quindi selezionare **Modifica.**

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi** e quindi **Fare clic su Fine.**

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Passaggio 2: Abilitare il log di controllo di Microsoft 365

La gestione dei rischi insider usa i log di controllo di Microsoft 365 per le informazioni dettagliate e le attività degli utenti identificate nei criteri e nelle analisi analitiche. I log di controllo di Microsoft 365 sono un riepilogo di tutte le attività all'interno dell'organizzazione e i criteri di gestione dei rischi insider possono utilizzare queste attività per generare informazioni dettagliate sui criteri.

Per istruzioni dettagliate su come attivare o disattivare il controllo, vedere Attivare o [disattivare la ricerca nel log di controllo.](turn-audit-log-search-on-or-off.md) Dopo l'abilitazione, verrà visualizzato un messaggio che indica che è in corso la preparazione del log di controllo e che sarà possibile eseguire una ricerca in un paio d'ore, dopo il completamento della preparazione. È necessario eseguire questa azione una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo di Microsoft 365, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Passaggio 3: Abilitare e visualizzare informazioni dettagliate sull'analisi dei rischi insider (facoltativo)

L'analisi dei rischi insider consente di eseguire una valutazione dei potenziali rischi insider nell'organizzazione senza configurare criteri di rischio insider. Questa valutazione può aiutare l'organizzazione a identificare le potenziali aree con un rischio maggiore per gli utenti e a determinare il tipo e l'ambito dei criteri di gestione dei rischi insider che è possibile configurare. Questa valutazione può anche aiutare a determinare le esigenze di ulteriori licenze o l'ottimizzazione futura dei criteri esistenti. I risultati dell'analisi dell'analisi possono richiedere fino a 48 ore prima che i dati analitici siano disponibili come report per la revisione. Per altre informazioni sui dati analitici, vedi Impostazioni di gestione dei rischi [Insider: Analisi (anteprima)](insider-risk-management-settings.md#analytics-preview) e guarda il [video insider Risk Management Analytics](https://www.youtube.com/watch?v=5c0P5MCXNXk) per comprendere in che modo l'analisi può aiutare ad accelerare l'identificazione dei potenziali rischi insider e ad agire rapidamente.

Per abilitare Insider Risk Analytics, è necessario essere membri del gruppo di ruoli *Insider Risk Management,* *Insider Risk Management Admin* o Microsoft 365 Global *admin.*

Completare la procedura seguente per abilitare l'analisi dei rischi insider:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider.**
2. Selezionare **Esegui analisi** nella scheda Analisi per i rischi insider **nella** scheda Panoramica della gestione dei rischi **insider.** Questa azione attiva l'analisi dell'analisi per l'organizzazione. Puoi anche attivare   >  **l'analisi nell'organizzazione** accedendo a Impostazioni rischio Insider **Analisi (anteprima)** e abilitando Analizza l'attività utente del tenant per identificare potenziali rischi insider.
3. Nel riquadro **Dei dettagli di** Analisi selezionare Esegui analisi per avviare **l'analisi per l'organizzazione.** I risultati dell'analisi analitica possono richiedere fino a 24 ore prima che i dati analitici siano disponibili come report per la revisione.

Dopo aver esaminato le informazioni analitiche, scegliere i criteri di rischio insider e configurare i prerequisiti associati che meglio soddisfano la strategia di mitigazione dei rischi insider dell'organizzazione.

## <a name="step-4-configure-prerequisites-for-policies"></a>Passaggio 4: Configurare i prerequisiti per i criteri

La maggior parte dei criteri di gestione dei rischi insider dispone di prerequisiti che devono essere configurati per gli indicatori dei criteri per generare avvisi di attività rilevanti. Configurare i prerequisiti appropriati in base ai criteri che si prevede di configurare per l'organizzazione.

### <a name="configure-microsoft-365-hr-connector"></a>Configurare il connettore risorse umane di Microsoft 365

La gestione dei rischi insider supporta l'importazione dei dati degli utenti e dei log importati da piattaforme di gestione dei rischi e risorse umane di terze parti. Il connettore dati risorse umane di Microsoft 365 consente di estrarre i dati delle risorse umane dai file CSV, incluse le date di fine utente, le date dell'ultimo impiego, le notifiche del piano di miglioramento delle prestazioni, le azioni di revisione delle prestazioni e lo stato di modifica a livello di processo. Tali dati aiutano a guidare gli indicatori di avviso nei criteri di gestione dei rischi Insider e costituiscono una parte importante della configurazione della copertura completa relativa alla gestione dei rischi nell’organizzazione. Se si configurano più connettori HR per l'organizzazione, la gestione dei rischi insider estrarrà automaticamente gli indicatori da tutti i connettori HR.

Il connettore risorse umane di Microsoft 365 è necessario quando si utilizzano i modelli di criteri seguenti:

- Furto di dati utente in partenza
- Violazioni dei criteri di sicurezza da parte degli utenti in partenza
- Violazioni dei criteri di sicurezza da parte di utenti scontenti
- Perdite di dati da parte di utenti scontenti

Vedere [l'articolo Configurare un connettore](import-hr-data.md) per importare i dati delle risorse umane per istruzioni dettagliate per configurare il connettore risorse umane di Microsoft 365 per l'organizzazione. Dopo aver configurato il connettore HR, tornare a questi passaggi di configurazione.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurare i criteri di prevenzione della perdita dei dati (DLP)

La gestione dei rischi insider supporta l'utilizzo dei criteri DLP per identificare l'esposizione intenzionale o accidentale di informazioni riservate a parti indesiderate per avvisi DLP di livello di gravità elevato. Quando si configura un criterio di  gestione dei rischi insider con uno qualsiasi dei modelli perdite di dati, è necessario assegnare un criterio DLP specifico al criterio.

I criteri DLP consentono di identificare gli utenti per attivare il punteggio di rischio nella gestione dei rischi insider per gli avvisi DLP di alta gravità per le informazioni riservate e sono una parte importante della configurazione della copertura completa per la gestione dei rischi nell'organizzazione. Per ulteriori informazioni sulla gestione dei rischi insider e sull'integrazione e sulla pianificazione dei criteri DLP, vedere [Insider risk management policies](insider-risk-management-policies.md#general-data-leaks).

>[!IMPORTANT]
>Assicurarsi di aver completato le operazioni seguenti:
>
>- È possibile comprendere e configurare correttamente gli utenti nell'ambito dei criteri di gestione dei rischi DLP e insider per produrre la copertura dei criteri prevista.
>- Verificare che **l'impostazione Rapporti** eventi imprevisti nel criterio DLP per la gestione dei rischi insider utilizzata con questi modelli sia configurata per gli *avvisi* a livello di gravità elevato. Gli avvisi per la gestione dei rischi insider non verranno generati dai criteri DLP con il campo **Report** operazioni non consentite impostato su *Basso* o *Medio.*

Quando si utilizzano i modelli di criteri seguenti, è necessario un criterio DLP:

- Perdite di dati generali
- Perdite di dati per utenti con priorità

Per istruzioni dettagliate sulla configurazione dei criteri DLP per l'organizzazione, vedere l'articolo [Creare, testare](create-test-tune-dlp-policy.md) e ottimizzare un criterio DLP. Dopo aver configurato un criterio DLP, tornare a questi passaggi di configurazione.

### <a name="configure-priority-user-groups"></a>Configurare i gruppi di utenti con priorità

La gestione dei rischi Insider include il supporto per l'assegnazione di gruppi di utenti prioritari ai criteri per aiutare le attività di rischio univoche dell'identità per gli utenti con posizioni critiche, livelli elevati di dati e accesso alla rete o una cronologia del comportamento dei rischi passata. La creazione di un gruppo di utenti con priorità e l'assegnazione degli utenti ai criteri di ambito della Guida di gruppo alle circostanze univoche presentate da questi utenti.

Quando si utilizzano i modelli di criteri seguenti, è necessario un gruppo di utenti con priorità:

- Violazioni dei criteri di sicurezza per utenti con priorità
- Perdite di dati per utenti con priorità

Vedi [l'articolo Introduzione alle impostazioni di gestione](insider-risk-management-settings.md#priority-user-groups-preview) dei rischi insider per istruzioni dettagliate per creare un gruppo di utenti con priorità. Dopo aver configurato un gruppo di utenti con priorità, tornare a questi passaggi di configurazione.

### <a name="configure-physical-badging-connector-optional"></a>Configurare il connettore di badging fisico (facoltativo)

La gestione dei rischi Insider supporta l'importazione dei dati degli utenti e dei log dalle piattaforme di accesso e controllo fisico. Il connettore di badging fisico consente di estrarre i dati di accesso dai file JSON, inclusi ID utente, ID punto di accesso, data e ora di accesso e stato di accesso. Tali dati aiutano a guidare gli indicatori di avviso nei criteri di gestione dei rischi Insider e costituiscono una parte importante della configurazione della copertura completa relativa alla gestione dei rischi nell’organizzazione. Se si configurano più connettori di badging fisico per l'organizzazione, la gestione dei rischi insider estrae automaticamente gli indicatori da tutti i connettori di badging fisici. Le informazioni del connettore di badging fisico integrano altri segnali di rischio insider quando si utilizzano tutti i modelli di criteri di rischio insider.

>[!IMPORTANT]
>Per consentire ai criteri di gestione dei rischi insider di usare e correlare i dati del segnale relativi agli utenti in uscita e terminati con i dati degli eventi dalle piattaforme di controllo fisico e accesso, è necessario configurare anche il connettore HR di Microsoft 365. Se si abilita il connettore di badging fisico senza abilitare il connettore HR di Microsoft 365, i criteri di gestione dei rischi insider eelaborareranno solo gli eventi per l'accesso fisico non autorizzato per gli utenti dell'organizzazione.

Per istruzioni dettagliate sulla configurazione del connettore di badging fisico per l'organizzazione, vedere l'articolo Set [up a connector to import physical badging data.](import-physical-badging-data.md) Dopo aver configurato il connettore, tornare a questi passaggi di configurazione.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Configurare Microsoft Defender per Endpoint (facoltativo)

[Microsoft Defender for Endpoint è](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) una piattaforma di sicurezza degli endpoint aziendale progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate. Per avere una migliore visibilità delle violazioni della sicurezza nell'organizzazione, puoi importare e filtrare Defender per gli avvisi endpoint per le attività utilizzate nei criteri creati dai modelli di criteri di violazione della sicurezza per la gestione dei rischi insider.

Se crei criteri di violazione della sicurezza, dovrai configurare Microsoft Defender for Endpoint nell'organizzazione e abilitare Defender for Endpoint per l'integrazione della gestione dei rischi insider nel Defender Security Center per importare gli avvisi di violazione della sicurezza. Per altre informazioni sui requisiti, vedi [l'articolo Requisiti minimi per Microsoft Defender per endpoint.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Vedi [l'articolo Configurare le funzionalità avanzate in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) per istruzioni dettagliate per configurare Defender per Endpoint per l'integrazione della gestione dei rischi insider. Dopo aver configurato Microsoft Defender per Endpoint, torna a questi passaggi di configurazione.

## <a name="step-5-configure-insider-risk-settings"></a>Passaggio 5: Configurare le impostazioni dei rischi insider

[Le impostazioni dei rischi](insider-risk-management-settings.md) insider si applicano a tutti i criteri di gestione dei rischi insider, indipendentemente dal modello scelto durante la creazione di un criterio. Le impostazioni vengono configurate usando il controllo **Impostazioni rischi dei dipendenti** posto nella parte superiore di tutte le schede per la gestione dei rischi Insider. Queste impostazioni controllano la privacy, gli indicatori, le finestre di monitoraggio e i rilevamenti intelligenti.

Prima di configurare un criterio, definire le impostazioni di rischio insider seguenti:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a Gestione dei rischi **Insider** e selezionare Impostazioni rischio **Insider** nell'angolo in alto a destra di qualsiasi pagina.
2. Nella pagina **Privacy** seleziona un'impostazione di privacy per la visualizzazione dei nomi utente per gli avvisi dei criteri.
3. Nella pagina **Indicatori** selezionare gli indicatori di avviso che si desidera applicare a tutti i criteri di rischio insider.

    >[!IMPORTANT]
    >Per ricevere avvisi per attività rischiose definite nei criteri, è necessario selezionare uno o più indicatori. Se gli indicatori non sono configurati in Impostazioni, gli indicatori non saranno selezionabili nei criteri di rischio insider.

4. Nella pagina Intervallo di tempo [](insider-risk-management-settings.md#policy-timeframes) dei **criteri** selezionare gli intervallo di tempo dei criteri da attivare per un utente quando attivano una corrispondenza per un criterio di rischio insider.
5. Nella pagina **Rilevamenti intelligenti** configurare le impostazioni seguenti per i criteri di rischio insider:
    - [Esclusioni di tipi di file](insider-risk-management-settings.md#file-type-exclusions)
    - [Soglie per attività insolite nei file](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Livello volume avviso](insider-risk-management-settings.md#alert-volume)
    - [Stato dell'avviso di Microsoft Defender for Endpoint](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Impostazioni di dominio](insider-risk-management-settings.md#domains-preview)
6. Nella pagina **Esporta avvisi** abilitare l'esportazione delle informazioni sugli avvisi per i rischi insider utilizzando le API di gestione di Office 365, se necessario.
7. Nella pagina **Priorità gruppi di utenti** creare un gruppo di utenti con priorità e aggiungere utenti se non creati nel passaggio **3.**
8. Nella pagina **Power Automate flows** configurare un flusso da modelli di flusso di rischio insider o creare un nuovo flusso. Per istruzioni [dettagliate,](insider-risk-management-settings.md#power-automate-flows-preview) vedere l'articolo Introduzione alle impostazioni di gestione dei rischi insider.
9. Nella pagina **Asset di priorità** configurare le risorse prioritarie per l'utilizzo dei dati della piattaforma di controllo e accesso fisico importata dal connettore di badging fisico. Per istruzioni [dettagliate,](insider-risk-management-settings.md#priority-physical-assets-preview) vedere l'articolo Introduzione alle impostazioni di gestione dei rischi insider.
10. Nella pagina **Microsoft Teams,** abilitare l'integrazione di Microsoft Teams con la gestione dei rischi insider per creare automaticamente un team per la collaborazione di casi o utenti. Per istruzioni [dettagliate,](insider-risk-management-settings.md#microsoft-teams-preview) vedere l'articolo Introduzione alle impostazioni di gestione dei rischi insider.
11. Selezionare **Salva per** abilitare queste impostazioni per i criteri di rischio insider.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Passaggio 6: Creare un criterio di gestione dei rischi insider

I criteri di gestione dei rischi Insider includono gli utenti assegnati e definiscono quali tipi di indicatori di rischio sono configurati per gli avvisi. Prima che le attività possano attivare gli avvisi, è necessario configurare un criterio. Utilizzare la procedura guidata dei criteri per creare nuovi criteri di gestione dei rischi insider.

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Criteri.
2. Selezionare **Crea criterio** per aprire la procedura guidata dei criteri.
3. Nella pagina **Modello di** criterio scegliere una categoria di criteri e quindi selezionare il modello per il nuovo criterio. Questi modelli sono costituito da condizioni e indicatori che definiscono le attività di rischio che si desidera rilevare e analizzare. Esaminare i prerequisiti del modello, l'attivazione di eventi e le attività rilevate per verificare che questo modello di criteri sia adatto alle proprie esigenze.

    >[!IMPORTANT]
    >Alcuni modelli di criteri dispongono di prerequisiti che devono essere configurati per il criterio per generare avvisi pertinenti. Se non sono stati configurati i prerequisiti dei criteri applicabili, vedere **passaggio 4** precedente.

4. Selezionare **Avanti** per continuare.
5. Nella pagina **Nome e descrizione** compilare i campi seguenti:
    - **Nome (obbligatorio):** immettere un nome descrittivo per il criterio. Questo nome non può essere modificato dopo la creazione del criterio.
    - **Descrizione (facoltativo):** immettere una descrizione per il criterio.

6. Selezionare **Avanti** per continuare.
7. Nella pagina **Utenti** e  gruppi selezionare Includi  tutti gli utenti e i gruppi oppure Includi utenti e gruppi specifici per definire quali utenti o gruppi sono inclusi nel criterio o se è stato scelto un modello basato su utenti prioritario. selezionare **Aggiungi o modifica gruppi di utenti con priorità**. Se **si seleziona Includi tutti gli utenti** e i gruppi, verranno cercati eventi di attivazione per tutti gli utenti e i gruppi dell'organizzazione per iniziare ad assegnare i punteggi di rischio per il criterio. Selezionando **Includi utenti e gruppi** specifici è possibile definire gli utenti e i gruppi da assegnare al criterio.
8. Selezionare **Avanti** per continuare.
9. Nella pagina **Contenuto per la** definizione delle priorità, è possibile assegnare (se necessario) le origini a cui assegnare la priorità, in modo da aumentare le probabilità di generare un avviso di gravità elevata per tali origini. Selezionare una delle opzioni seguenti:

    - **Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario.** Selezionando questa opzione, verranno abilitate le pagine di dettaglio della procedura guidata per configurare questi canali.
    - **Non voglio specificare il contenuto** prioritario in questo momento (sarà possibile farlo dopo la creazione del criterio). Se si seleziona questa opzione, le pagine dei dettagli del canale verranno ignorate nella procedura guidata.

10. Selezionare **Avanti** per continuare.

11. Se è stato selezionato Si desidera specificare i siti di SharePoint, le etichette di riservatezza e/o i tipi di informazioni riservate come contenuto prioritario nel passaggio precedente, verranno visualizzate le pagine dei dettagli per i siti di **SharePoint,** i tipi di informazioni riservate e le etichette di  *riservatezza.* Usare queste pagine di dettaglio per definire SharePoint, i tipi di informazioni riservate e le etichette di riservatezza per definire la priorità nel criterio.

    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare i siti di SharePoint a cui si ha accesso e si desidera definire le priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate:** seleziona **Aggiungi tipo di informazioni** riservate e seleziona i tipi di riservatezza di cui vuoi definire la priorità. Ad esempio, *"U.S. Bank Account Number"* e *"Credit Card Number"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette di cui si desidera definire la priorità. Ad esempio, *"Confidential"* e *"Secret"*.

12. Selezionare **Avanti** per continuare.
13. Nella pagina **Indicatori ed** eventi di attivazione [](insider-risk-management-settings.md#indicators) vedrai gli indicatori definiti come disponibili nella pagina Indicatori delle impostazioni di rischio   >  **Insider.** Se è stato selezionato un modello Perdite di dati all'inizio della procedura guidata, è necessario selezionare un criterio DLP nell'elenco *a* discesa dei criteri **DLP** per abilitare gli indicatori di attivazione per il criterio o selezionare l'evento di attivazione predefinito.

    >[!IMPORTANT]
    >Se gli indicatori in questa pagina non possono essere selezionati, è necessario selezionare gli indicatori che si desidera abilitare per tutti i criteri. Puoi usare il **pulsante Attiva indicatori nella** procedura guidata o selezionare gli indicatori nella pagina **Impostazioni** di gestione dei rischi Insider  >    >  **Indicatori di** criteri.

    Selezionare gli indicatori che si desidera applicare al criterio. Se si preferisce non usare le impostazioni di soglia dei criteri predefiniti per questi indicatori, disabilitare l'opzione Usa soglie predefinite consigliate da **Microsoft** e immettere i valori di soglia per ogni indicatore selezionato.

    - Se è stato selezionato almeno un indicatore di *Office* o *dispositivo,* selezionare i ripetitori del **punteggio di rischio in** base alle esigenze. I ripetitori del punteggio di rischio sono applicabili solo per gli indicatori selezionati.
    - Se è stato  selezionato un  modello di criteri Furto di  dati o Perdite di dati, selezionare uno o più metodi di rilevamento della sequenza e un metodo di rilevamento **dell'esfiltrazione** cumulativa da applicare al criterio.

14. Selezionare **Avanti** per continuare.
15. Nella pagina **Soglie indicatore** selezionare l'opzione per l'utilizzo delle soglie degli indicatori predefinite o per specificare soglie personalizzate per singoli indicatori. Per ogni indicatore, scegliere il livello appropriato per generare il livello desiderato di avvisi di attività.
16. Selezionare **Avanti** per continuare.
17. Nella pagina **Revisione** esaminare le impostazioni scelte per il criterio e gli eventuali suggerimenti o avvisi per le selezioni. Selezionare **Modifica** per modificare i valori dei criteri oppure selezionare **Invia** per creare e attivare il criterio.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato questi passaggi per creare il primo criterio di gestione dei rischi insider, inizierai a ricevere avvisi dagli indicatori di attività dopo circa 24 ore. Configurare criteri aggiuntivi in base alle esigenze usando le indicazioni del passaggio 4 di questo articolo o la procedura descritta in [Creare un nuovo criterio di rischio insider.](insider-risk-management-policies.md#create-a-new-policy)

Per ulteriori informazioni sull'analisi degli avvisi per i rischi insider e sul **dashboard degli** avvisi, vedere Avvisi per la gestione dei [rischi Insider.](insider-risk-management-alerts.md)
