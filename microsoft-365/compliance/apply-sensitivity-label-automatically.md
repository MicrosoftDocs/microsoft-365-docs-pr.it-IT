---
title: Applicare automaticamente un'etichetta di riservatezza al contenuto in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Quando si crea un'etichetta di riservatezza, è possibile assegnare automaticamente un'etichetta a file e messaggi di posta elettronica oppure chiedere agli utenti di selezionare l'etichetta consigliata.
ms.openlocfilehash: 2f873482dc351050a87993420e718f6de87ac218
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227532"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Applicare automaticamente un'etichetta di riservatezza al contenuto

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Per informazioni su come classificare ed etichettare i dati in Azure Purview, attualmente in anteprima, vedere [Etichettare automaticamente contenuti in Azure Purview](/azure/purview/create-sensitivity-label).

Quando si crea un'etichetta di riservatezza, è possibile assegnarla automaticamente a file e messaggi di posta elettronica quando soddisfano le condizioni specificate.

La possibilità di applicare automaticamente etichette di riservatezza al contenuto è importante perché:

- Non è necessario spiegare agli utenti quando usare le singole classificazioni.

- Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.

- Gli utenti non hanno più bisogno di conoscere i criteri e possono concentrarsi sul loro lavoro.

Quando il contenuto è stato etichettato manualmente, quell'etichetta non verrà mai sostituita dall'etichettatura automatica. Tuttavia, l'etichettatura automatica può sostituire un'[etichetta con livello di priorità inferiore](sensitivity-labels.md#label-priority-order-matters) applicata automaticamente.

Esistono due metodi diversi per applicare automaticamente un'etichetta di riservatezza al contenuto in Microsoft 365:

- **Etichettatura lato client quando gli utenti modificano documenti o compongono (e rispondono o inoltrano) messaggi di posta elettronica**: usare un'etichetta configurata per l'applicazione automatica di etichette per file e messaggi di posta elettronica (include Word, Excel, PowerPoint e Outlook).

    Questo metodo supporta la raccomandazione di un'etichetta agli utenti, nonché l'applicazione automatica di un'etichetta. In entrambi i casi, comunque, l'utente decide se accettarla o rifiutarla, per garantire la corretta etichettatura del contenuto. Questa etichettatura lato client ha un ritardo minimo per i documenti perché l'etichetta può essere applicata anche prima di salvare il documento. Tuttavia, non tutte le app client supportano l'etichettatura automatica. Questa funzionalità è supportata dal client di etichettatura unificata di Azure Information Protection e da [alcune versioni di Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

    Per le istruzioni di configurazione, vedere [Come configurare l'applicazione automatica di etichette per le app di Office](#how-to-configure-auto-labeling-for-office-apps) in questa pagina.

- **Etichettatura lato servizio quando il contenuto è già salvato (in SharePoint o OneDrive) o inviato tramite posta elettronica (elaborato da Exchange Online)**: usare un criterio di applicazione automatica di etichette.

    Questo metodo potrebbe essere indicato anche come applicazione automatica di etichette per i dati inattivi (documenti in SharePoint e OneDrive) e per i dati in transito (messaggi di posta elettronica inviati o ricevuti da Exchange). Per Exchange, non include i messaggi di posta elettronica inattivi (cassette postali).

    Dato che questa etichettatura viene applicata dai servizi e non dalle applicazioni, non è necessario preoccuparsi delle app e delle versioni usate dagli utenti. Di conseguenza, questa funzionalità è immediatamente disponibile nell'intera organizzazione ed è adatta per l'applicazione di etichette su vasta scala. I criteri di applicazione automatica di etichette non supportano l'applicazione di etichette consigliate perché l'utente non interagisce con il processo di etichettatura. L'amministratore esegue invece i criteri in modalità di simulazione per garantire la corretta etichettatura del contenuto prima dell'applicazione effettiva dell'etichetta.

    Per istruzioni sulla configurazione, vedere [Come configurare i criteri di applicazione automatica di etichette per SharePoint, OneDrive e Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) in questa pagina.

    Caratteristiche specifiche dell'etichettatura automatica per SharePoint e OneDrive:
    - Sono supportati i file di Office per Word, PowerPoint ed Excel. È supportato il formato Open XML, ad esempio le estensioni .docx e .xlsx, ma non il formato di Microsoft Office 97-2003, ad esempio le estensioni .doc e .xls.
        - Questi file inattivi possono essere etichettati automaticamente prima o dopo la creazione dei criteri di etichettatura automatica. I file non possono essere etichettati automaticamente se fanno parte di una sessione aperta (il file è aperto).
        - Al momento gli allegati agli elementi dell'elenco non sono supportati e non verranno etichettati automaticamente.
    - Massimo 25.000 file etichettati automaticamente nel tenant al giorno.
    - Massimo di 10 criteri di etichettatura automatica per tenant, ognuno dei quali ha un massimo di 10 siti (SharePoint o OneDrive).
    - I valori esistenti per "Modificato", "Modificato da" e la data non vengono cambiati dai criteri di etichettatura automatica, sia per la modalità di simulazione che per l'applicazione delle etichette.
    - Quando si applica la crittografia all'etichetta, [l'emittente di Rights Management e il proprietario di Rights Management](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) è il conto che ha modificato per ultimo il file.

    Caratteristiche specifiche dell'etichettatura automatica per Exchange:
    - A differenza dell'etichettatura manuale o dell'etichettatura automatica per le app di Office, negli allegati di Office (file Word, Excel e PowerPoint) e PDF vengono ricercate anche le condizioni specificate nei criteri di etichettatura automatica. Quando viene rilevata una corrispondenza, viene applicata un'etichetta al messaggio di posta elettronica ma non all'allegato.
        - Per i file PDF, se l'etichetta applica la crittografia, questi file vengono crittografati quando il tenant [abilitati per gli allegati PDF](ome-faq.yml#are-pdf-file-attachments-supported-).
        - Per questi file di Office, è supportato il formato Open XML, ad esempio le estensioni .docx e .xlsx, ma non il formato di Microsoft Office 97-2003, ad esempio le estensioni .doc e .xls. Se l'etichetta applica la crittografia, questi file vengono crittografati.
    - Se sono presenti regole per il flusso di posta di Exchange o criteri di prevenzione della perdita dei dati che applicano la crittografia IRM: quando il contenuto viene identificato da queste regole o criteri e da un criterio di applicazione automatica di etichette, l'etichetta viene applicata. Se quell'etichetta applica la crittografia, le impostazioni IRM delle regole per il flusso di posta di Exchange o dei criteri di prevenzione della perdita dei dati vengono ignorate. Se invece quella etichetta non applica la crittografia, in aggiunta all'etichetta vengono applicate le impostazioni IRM delle regole per il flusso di posta di Exchange o dei criteri di prevenzione della perdita dei dati.
    - I messaggi di posta elettronica con crittografia IRM senza etichetta verranno sostituiti da un'etichetta con qualsiasi impostazione di crittografia se esiste una corrispondenza usando l'etichettatura automatica.
    - La posta in arrivo viene etichettata quando esiste una corrispondenza con le condizioni di etichettatura automatica:
        - Se l'etichetta è configurata per la [crittografia](encryption-sensitivity-labels.md), la crittografia non viene applicata.
        - Se l'etichetta è configurata per l'applicazione di [contrassegni dinamici](sensitivity-labels-office-apps.md#dynamic-markings-with-variables), tenere presente che questo può risultare in nomi di persone esterne all'organizzazione.
    - Quando si applica la crittografia all'etichetta, [l'emittente di Rights Management e il proprietario di Rights Management](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) è la persona che invia il messaggio di posta elettronica. Al momento non è possibile impostare un proprietario di Rights Manager per tutte le e-mail in arrivo che vengono crittografate automaticamente.


## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Confronto tra l'applicazione automatica di etichette per le app di Office e i criteri di applicazione automatica di etichette

Nella tabella seguente sono riportate le differenze di comportamento tra i due metodi complementari di etichettatura automatica:

|Funzionalità o comportamento|Impostazione di etichettatura: Applicazione automatica delle etichette per file e messaggi di posta elettronica  |Criterio: Etichettatura automatica|
|:-----|:-----|:-----|
|Dipendenza dall'app|[Sì](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |No \* |
|Limitazione in base alla posizione|No |Sì |
|Condizioni: Classificatori sottoponibili a training|Sì |No |
|Condizioni: Opzioni di condivisione e opzioni aggiuntive per la posta elettronica|No |Sì |
|Condizioni: Eccezioni|No |Sì (solo posta elettronica) |
|Consigli, suggerimento criteri e criteri ignorati dagli utenti|Sì |No |
|Modalità di simulazione|No |Sì |
|Verifica delle condizioni negli allegati di Exchange|No | Sì|
|Applicazione di contrassegni visivi |Sì |Sì (solo posta elettronica) |
|Override della crittografia IRM applicata senza etichetta|Sì, se l'utente dispone del diritto minimo di utilizzo per l'esportazione |Sì (solo posta elettronica) |
|Etichettatura della posta in arrivo|No |Sì|

\* L'applicazione automatica di etichette non è attualmente disponibile in tutte le aree geografiche. Se il tenant non supporta questa funzionalità, la scheda di applicazione automatica delle etichette non è visibile nell'interfaccia di amministrazione relativa all’applicazione delle etichette.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Modalità di valutazione di più condizioni quando si applicano a più etichette

Le etichette sono ordinate per la valutazione in base alla posizione specificata nei criteri: la prima etichetta ha la posizione più bassa (meno riservata) mentre l'ultima etichetta ha la posizione più alta (più riservata). Per altre informazioni sulla priorità, vedere [Priorità dell’etichetta (l’ordine è importante)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Non configurare un'etichetta padre in modo che venga applicata automaticamente o consigliata

Tenere presente che non è possibile applicare al contenuto un'etichetta padre (un'etichetta con sottoetichette). Verificare che non sia stata configurata un'etichetta padre per essere applicata automaticamente o consigliata nelle app di Office e non selezionare un'etichetta padre per un criterio di applicazione automatica di etichette, altrimenti l'etichetta padre non verrà applicata al contenuto.

Per usare l'etichettatura automatica con le sottoetichette, assicurarsi di pubblicare sia l'etichetta padre che la sottoetichetta.

Per ulteriori informazioni sulle etichette padre e sulle sottoetichette, vedere [Sottoetichette (raggruppamento etichette)](sensitivity-labels.md#sublabels-grouping-labels).

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Come configurare l'applicazione automatica di etichette per le app di Office

L'assegnazione automatica di etichette nelle app Office per Windows è supportata dal client di etichettatura unificata di Azure Information Protection. Per l’etichettatura predefinita delle app di Office, questa funzionalità [prevede fasi di disponibilità diverse per app differenti](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Le impostazioni di applicazione automatica delle etichette per le app di Office sono disponibili quando si [crea o modifica un'etichetta di riservatezza](create-sensitivity-labels.md). Assicurarsi che **File e messaggi di posta elettronica** sia selezionato per l'ambito dell'etichetta:

![Opzioni relative all'ambito dell'etichetta di riservatezza per file e messaggi di posta elettronica](../media/filesandemails-scope-options-sensitivity-label.png)

Mentre ci si sposta attraverso la procedura guidata, viene visualizzata la pagina **Applicazione automatica delle etichette per file e messaggi di posta elettronica**, in cui è possibile scegliere da un elenco di tipi di informazioni sensibili o di classificatori sottoponibili a training:

![Condizioni delle etichette per l'applicazione automatica di etichette nelle app di Office](../media/sensitivity-labels-conditions.png)

Quando questa etichetta di riservatezza viene applicata automaticamente, l'utente riceve una notifica nella propria app Office. Ad esempio:

![Notifica di applicazione automatica di un'etichetta a un documento](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>Configurazione dei tipi di informazioni sensibili per un'etichetta

Quando si seleziona l'opzione **Tipi di informazioni sensibili**, viene visualizzato lo stesso elenco di tipi di informazioni sensibili mostrato durante la creazione di un criterio di prevenzione della perdita dei dati (DLP). Ad esempio, è possibile applicare automaticamente un'etichetta Estremamente riservato a qualsiasi contenuto che include informazioni personali dei clienti, ad esempio numeri di carte di credito, codici fiscali o numeri di passaporto:

![Tipi di informazioni sensibili per l'assegnazione automatica di etichette nelle app Office](../media/sensitivity-labels-sensitive-info-types.png)

Analogamente a quando si configurano i criteri sulla prevenzione della perdita dei dati, è possibile perfezionare la condizione cambiando il numero delle istanze e l’accuratezza della corrispondenza. Ad esempio:

![Opzioni per l'accuratezza della corrispondenza e numero di istanze](../media/sit-confidence-level.png)

Per altre informazioni su queste opzioni di configurazione, vedere la documentazione sulla prevenzione della perdita dei dati: [Modificare le regole per rendere più facili o difficili le corrispondenze](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Inoltre, analogamente alla configurazione dei criteri di prevenzione della perdita dei dati, è possibile scegliere se una condizione deve rilevare tutti i tipi di informazioni sensibili o solo una di esse. Per rendere le condizioni più flessibili o complesse, è possibile aggiungere [gruppi e usare operatori logici tra i gruppi](data-loss-prevention-policies.md#grouping-and-logical-operators).

> [!NOTE]
> I criteri di etichettatura automatica basati su tipi di informazioni sensibili personalizzati si applicano solo al contenuto appena creato o modificato in OneDrive e SharePoint, non al contenuto esistente.

### <a name="configuring-trainable-classifiers-for-a-label"></a>Configurazione di classificatori sottoponibili a training per un'etichetta

Al momento questa opzione è disponibile in anteprima. Se si usa questa opzione, assicurare di avere pubblicato nel tenant almeno un'altra etichetta di riservatezza che sia configurata per l'assegnazione automatica delle etichette e l'opzione [tipi di informazioni sensibili](#configuring-sensitive-info-types-for-a-label).

Quando si seleziona l'opzione **Classificatori sottoponibili a training**, scegliere uno o più dei classificatori sottoponibili a training predefiniti di Microsoft. Se sono stati creati classificatori sottoponibili a training personalizzati, saranno anch'essi disponibili per la selezione:

![Opzioni per i classificatori sottoponibili a training e le etichette di riservatezza](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> Il classificatore predefinito **Linguaggio offensivo** è stato deprecato perché generava un numero elevato di falsi positivi. Non usare questo classificatore predefinito e, se è in uso, è consigliabile spostare i processi aziendali da esso. Usare invece i classificatori predefiniti per **molestie**, **volgarità** e **minacce**.

Per altre informazioni su questi classificatori, vedere [Informazioni sui classificatori sottoponibili a training](classifier-learn-about.md).

Durante il periodo di anteprima dell'opzione, le app seguenti supportano i classificatori sottoponibili a training per le etichette di riservatezza:

- Microsoft 365 Apps for enterprise ([in precedenza Office 365 ProPlus](/deployoffice/name-change)) per Windows, ora in distribuzione nel [Canale corrente](/deployoffice/overview-update-channels#current-channel-overview) nella versione 2006 e successive:
    - Word
    - Excel
    - PowerPoint

- Office per le app Web, se le [etichette di riservatezza sono abilitate per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):
    - Word
    - Excel
    - PowerPoint
    - Outlook

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a>Consigliare all'utente di applicare un'etichetta di riservatezza

Se si preferisce, si può consigliare agli utenti di applicare l'etichetta. Con questa opzione, gli utenti possono accettare la classificazione e l'eventuale protezione associata oppure chiudere il suggerimento, se l'etichetta non è adatta al contenuto.

![Opzione per consigliare un'etichetta di riservatezza agli utenti](../media/Sensitivity-labels-Recommended-label-option.png)

Ecco un esempio di un avviso del client di etichettatura unificata di Azure Information Protection quando si configura una condizione per applicare un'etichetta come azione consigliata, con un suggerimento per i criteri personalizzati. È possibile scegliere quale testo visualizzare nel suggerimento per i criteri.

![Richiesta di applicazione di un'etichetta consigliata](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a>Quando vengono applicate le etichette automatiche o consigliate

L'implementazione dell'etichettatura automatica e consigliata nelle app di Office varia a seconda che si usi l'etichettatura integrata in Office o il client di etichettatura unificata di Azure Information Protection. In entrambi i casi, tuttavia:

- Non è possibile usare l'assegnazione automatica di etichette per le e-mail e i documenti in precedenza etichettati manualmente o associati automaticamente a un grado maggiore di riservatezza. È possibile applicare una singola etichetta di riservatezza a un documento o un messaggio di posta elettronica (oltre a una singola etichetta di conservazione).

- Non è possibile usare la classificazione consigliata per i documenti etichettati in precedenza con un grado maggiore di riservatezza. Quando il contenuto è già stato etichettato con una riservatezza superiore, l'utente non visualizzerà l'avviso con il consiglio e il suggerimento per i criteri.

Caratteristiche specifiche dell'etichettatura predefinita:

- Non tutte le app di Office supportano l'etichettatura automatica (e consigliata). Per altre informazioni, vedere [Supporto per le funzionalità di riservatezza nelle app](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

- Per le etichette consigliate nelle versioni desktop di Word, il contenuto sensibile che ha generato il suggerimento viene contrassegnato in modo che gli utenti possano rivedere e rimuovere tale contenuto anziché applicare l'etichetta di riservatezza consigliata.

- Per informazioni su come vengono applicate tali etichette nelle app di Office, screenshot di esempio e dettagli su come vengono rilevate le informazioni sensibili, vedere [Applicare automaticamente o consigliare l'applicazione di etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.office.com/it-IT/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).

Caratteristiche specifiche del client di etichettatura unificata di Azure Information Protection:

-  L'assegnazione automatica e consigliata delle etichette si applica a Word, Excel e PowerPoint al salvataggio dei documenti e in Outlook all'invio di messaggi di posta elettronica.

- Affinché Outlook sia in grado di supportare l'etichettatura consigliata, è prima necessario configurare un'[impostazione dei criteri avanzata](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).

- Le informazioni sensibili possono essere rilevate nel corpo del testo nei documenti e nei messaggi di posta elettronica e nelle intestazioni a piè di pagina, ma non nella riga dell'oggetto o negli allegati di posta elettronica.

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>Come configurare i criteri di applicazione automatica di etichette per SharePoint, OneDrive e Exchange

Assicurarsi di conoscere i prerequisiti prima di configurare i criteri di etichetta automatica.

### <a name="prerequisites-for-auto-labeling-policies"></a>Prerequisiti per i criteri di applicazione automatica di etichette

- Modalità di simulazione:
    - È necessario abilitare il controllo per Microsoft 365. Per abilitare il controllo o verificare se è già attivato, vedere [Abilitare o disabilitare la ricerca nel log di audit](turn-audit-log-search-on-or-off.md).
    - Per visualizzare il contenuto del file e del messaggio di posta elettronica nella visualizzazione origine, è necessario avere il ruolo di **Visualizzatore contenuto di Esplora contenuto**. Per impostazione predefinita, gli amministratori globali non hanno questo ruolo. Se non si dispone di questa autorizzazione, non viene visualizzato il riquadro di anteprima quando si seleziona un elemento dalla scheda **Elementi corrispondenti**.

- Per assegnare automaticamente un'etichetta ai file in SharePoint e OneDrive:
    - Sono state [abilitate le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).
    - Nel momento in cui vengono eseguiti i criteri di applicazione automatica di etichette, il file non deve essere aperto da un altro processo o utente. Un file estratto per la modifica rientra in questa categoria.

- Se si prevede di usare [tipi di informazioni sensibili personalizzati](sensitive-information-type-learn-about.md) anziché quelli predefiniti:
    - I tipi di informazioni di sensibili personalizzati riguardano solo il contenuto aggiunto o modificato in SharePoint o a OneDrive successivamente alla loro applicazione.
    - Per testare nuovi tipi di informazioni sensibili personalizzati, crearli prima di creare i criteri di applicazione automatica di etichette e quindi creare nuovi documenti con i dati di esempio per il test.

- Una o più etichette di riservatezza [create e pubblicate](create-sensitivity-labels.md) (per almeno un utente) che è possibile selezionare per i criteri di applicazione automatica di etichette. Per queste etichette:
    - Non è rilevante se l'opzione di etichettatura automatica nelle app di Office sia attivata o disattivata perché, come spiegato nell'introduzione, quella impostazione delle etichette integra i criteri di applicazione automatica di etichette.
    - Se le etichette che si vogliono usare per l'applicazione automatica di etichette sono configurate per l'uso di contrassegni visivi (intestazioni, piè di pagina e filigrane), tenere presente che non questi non vengono applicati ai documenti.
    - Se le etichette applicano la [crittografia](encryption-sensitivity-labels.md):
        - Quando il criterio di applicazione automatica delle etichette include posizioni per SharePoint o OneDrive, l'etichetta deve essere configurata per l'impostazione **Assegnare le autorizzazioni adesso**.
        - Quando il criterio di applicazione automatica delle etichette è solo per Exchange, l'etichetta può essere configurata sia per **Assegnare le autorizzazioni adesso** o **Consentire agli utenti di assegnare le autorizzazioni** (per le opzioni Non inoltrare o Solo crittografia).

### <a name="learn-about-simulation-mode"></a>Informazioni sulla modalità di simulazione

La modalità di simulazione è specifica dei criteri di applicazione automatica di etichette ed è integrata nel flusso di lavoro. Non è possibile applicare automaticamente etichette ai documenti e ai messaggi di posta elettronica prima che il criterio abbia eseguito almeno una simulazione.

Flusso di lavoro per un criterio di applicazione automatica di etichette:

1. Creare e configurare un criterio di applicazione automatica di etichette.

2. Eseguire il criterio in modalità di simulazione. Il completamento può richiedere fino a 48 ore.

3. Rivedere i risultati e, se necessario, perfezionare il criterio. Rieseguire la modalità di simulazione e attendere che la procedura sia completata di nuovo.

4. Ripetere il passaggio 3 in base alle esigenze.

5. Distribuire in produzione.

La distribuzione simulata viene eseguita come il parametro WhatIf per PowerShell. Vengono riportati i risultati come se il criterio di applicazione automatica di etichette avesse applicato l'etichetta selezionata, usando le regole definite. È possibile perfezionare le regole, se necessario, ed eseguire di nuovo la simulazione. Tuttavia, dato che l'etichettatura automatica per Exchange si applica ai messaggi di posta elettronica inviati e ricevuti e non ai messaggi archiviati nelle cassette postali, i risultati relativi alla posta in una simulazione non saranno coerenti, a meno che non si riesca a inviare e ricevere gli stessi identici messaggi.

La modalità di simulazione consente anche di aumentare gradualmente l'ambito del criterio di applicazione automatica di etichette prima della distribuzione. Ad esempio, è possibile iniziare con una singola posizione, come un sito di SharePoint site, con una singola raccolta documenti. Quindi, con le modifiche iterative, estendere l'ambito a più siti e quindi a un'altra posizione, ad esempio OneDrive.

Infine, è possibile usare la modalità di simulazione per ottenere un'approssimazione del tempo necessario per eseguire il criterio di applicazione automatica di etichette, per agevolare la pianificazione e la programmazione della sua esecuzione senza la modalità di simulazione.

### <a name="creating-an-auto-labeling-policy"></a>Creazione di un criterio di applicazione automatica di etichette

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare alle etichette di riservatezza:

    - **Soluzioni** > **Information Protection)**

    Se questa opzione non è immediatamente visibile, selezionare prima **Mostra tutto**.

2. Selezionare la scheda **Etichettatura automatica**:

    ![Scheda Etichettatura automatica](../media/auto-labeling-tab.png)

    > [!NOTE]
    > Se non viene visualizzata la scheda di **Applicazione automatica di etichette**, questa funzionalità non è attualmente disponibile nella propria area geografica.

3. Selezionare **+ Crea criterio di applicazione automatica di etichette**. Verrà avviata la creazione guidata del nuovo criterio:

    ![Creazione guidata del nuovo criterio per l’applicazione automatica di etichette](../media/auto-labeling-wizard.png)

4. Per la pagina **Scegliere le informazioni a cui applicare questa etichetta**: selezionare uno dei modelli, ad esempio **Finanziari** o **Privacy**. È possibile perfezionare la ricerca usando l'elenco a discesa **Mostra le opzioni per**. In alternativa, selezionare **Criterio personalizzato** se i modelli non soddisfano i propri requisiti. Selezionare **Avanti**.

5. Per la pagina **Assegnare un nome al criterio di applicazione automatica delle etichette**: specificare un nome univoco e, facoltativamente, una descrizione per l'etichetta applicata automaticamente, le posizioni e le condizioni che identificano il contenuto da etichettare.

6. Per la pagina **Scegliere le posizioni in cui si desidera applicare l'etichetta**: selezionare e specificare le posizioni per Exchange, siti di SharePoint e OneDrive. Quindi, scegliere **Avanti**.

    ![Scegliere la procedura guidata per l’applicazione automatica di etichette alla pagina delle posizioni ](../media/locations-auto-labeling-wizard.png)

    È necessario specificare singoli siti di SharePoint e account di OneDrive. Per OneDrive, l'URL dell'account di OneDrive di un utente ha il seguente formato: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

    Ad esempio, per un utente nel tenant Contoso con il nome utente "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

    Per verificare la sintassi del tenant e identificare gli URL per gli utenti, vedere [Ottenere un elenco di tutti gli URL di OneDrive dell'utente nell'organizzazione](/onedrive/list-onedrive-urls).

7. Per la pagina **Configurare regole comuni o avanzate**: mantenere l'impostazione predefinita di **Regole comuni** per definire le regole che identificano il contenuto da etichettare in tutte le posizioni selezionate. Se sono necessarie regole diverse per ogni posizione, selezionare **Regole avanzate**. Quindi, scegliere **Avanti**.

    Le regole usano condizioni che includono i tipi di informazioni sensibili e le opzioni di condivisione:
    - Per i tipi di informazioni sensibili, è possibile selezionare tipi predefiniti e personalizzati.
    - Per le opzioni di condivisione, è possibile scegliere **Solo con persone interne all'organizzazione** o **Con persone esterne all'organizzazione**.

    Se l'unica posizione è **Exchange** o se si seleziona **Regole avanzate**, è possibile selezionare altre condizioni:
    - L'indirizzo IP del mittente è
    - Il dominio del destinatario è
    - Il destinatario è
    - L'estensione del file allegato è
    - L'allegato è protetto da password
    - Non è stato possibile analizzare il contenuto degli allegati di posta elettronica
    - L'analisi del contenuto degli allegati di posta elettronica non è stata completata
    - L'intestazione corrisponde ai criteri
    - Il soggetto corrisponde ai criteri
    - L'indirizzo del destinatario contiene parole
    - L'indirizzo del destinatario corrisponde ai criteri
    - L'indirizzo del mittente corrisponde ai criteri
    - Il dominio del mittente è
    - Il destinatario è un membro di
    - Il mittente è

    Per ognuna di queste condizioni, è quindi possibile specificare le eccezioni.

8. A seconda delle scelte effettuate in precedenza, è possibile creare regole nuove usando condizioni ed eccezioni.

    Le opzioni di configurazione per i tipi di informazioni sensibili sono identiche a quelle selezionate per l'applicazione automatica di etichette per le app di Office. Per altre informazioni, vedere [Configurazione dei tipi di informazioni sensibili per un'etichetta](#configuring-sensitive-info-types-for-a-label).

    Dopo avere definito tutte le regole necessarie e avere verificato che il relativo stato è attivato, selezionare **Avanti** per scegliere l’etichetta da applicare automaticamente.

11. Per la pagina **Scegliere un'etichetta da applicare automaticamente**: selezionare **+ Scegli un'etichetta**, selezionare un'etichetta nel riquadro **Choose a sensitivity label**, quindi scegliere **Avanti**.

12. Per la pagina **Decidere se si vuole eseguire il test dei criteri ora o in un secondo momento**: selezionare **Esegui criteri in modalità di simulazione** se si è pronti per eseguire il criterio di applicazione automatica di etichette in modalità di simulazione. In caso contrario, selezionare **Mantieni il criterio disabilitato**. Selezionare **Avanti**:

    ![Testare la procedura guidata per l’applicazione automatica delle etichette dei criteri](../media/simulation-mode-auto-labeling-wizard.png)

13. Per la pagina **Riepilogo**: esaminare la configurazione del criterio di applicazione automatica di etichette e apportare le modifiche necessarie, quindi completare la procedura guidata.

Andando alla pagina **Protezione delle informazioni** > **Applicazione automatica di etichette**, ora è possibile visualizzare i criteri di applicazione automatica di etichette nella sezione **Simulazione** o **Disattivato**, a seconda che si sia scelto di eseguirlo in modalità di simulazione o meno. Selezionare il criterio per visualizzare i dettagli della configurazione e dello stato, ad esempio **Simulazione del criterio ancora in corso**. Per i criteri in modalità di simulazione, selezionare la scheda **Elementi corrispondenti** per vedere quali e-mail o documenti corrispondono alle regole specificate.

È possibile modificare i criteri direttamente dall'interfaccia:

- Per un criterio nella sezione **Disattivato**, selezionare il pulsante **Modifica criterio**.

- Per i criteri nella sezione **Simulazione**, selezionare l'opzione **Modifica criteri** nella parte superiore della pagina, da entrambe le schede:

    ![Modificare l'opzione del criterio di applicazione automatica di etichette](../media/auto-labeling-edit.png)

    Quando si è pronti per eseguire il criterio senza simulazione, selezionare l'opzione **Abilita criterio**.

I criteri automatici vengono eseguiti continuativamente finché non vengono eliminati. Ad esempio, i documenti nuovi e modificati verranno inclusi nelle impostazioni dei criteri correnti.

Per visualizzare i risultati del criterio di applicazione automatica di etichette è possibile anche usare [Esplora contenuto](data-classification-content-explorer.md) quando si hanno le [autorizzazioni](data-classification-content-explorer.md#permissions) appropriate:
- **Visualizzatore elenco di Esplora contenuto** consente di vedere l'etichetta di un file ma non il contenuto del file.
- **Visualizzatore contenuto di Esplora contenuto** consente di vedere il contenuto del file.

> [!TIP]
> È anche possibile usare Esplora contenuto per identificare le posizioni in cui sono presenti documenti con informazioni sensibili, ma senza etichetta. Usando queste informazioni, è possibile aggiungere queste posizioni ai criteri di applicazione automatica di etichette e includere come regole i tipi di informazioni sensibili identificati.

### <a name="use-powershell-for-auto-labeling-policies"></a>Usare PowerShell per i criteri di applicazione automatica di etichette.

È possibile usare il [ Centro conformità e conformità di PowerShell](/powershell/exchange/scc-powershell) per creare e configurare criteri di applicazione automatica di etichette. Questo significa che è possibile creare script per la creazione e la manutenzione dei criteri di applicazione automatica di etichette, che forniscono anche un metodo più efficiente per specificare multipli URL per OneDrive e percorsi di SharePoint.

Per poter eseguire i comandi di PowerShell, è prima necessario [connettersi al Centro sicurezza e conformità di PowerShell](/powershell/exchange/connect-to-scc-powershell).

Per creare un nuovo criterio di applicazione automatica di etichette:

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
Questo comando crea un criterio di applicazione automatica di etichette per un sito di SharePoint che viene specificato. Per una posizione di OneDrive, usare invece il parametro *OneDriveLocation*.

Per aggiungere altri siti a criteri di applicazione automatica di etichette esistenti:

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

Questo comando specifica gli URL di SharePoint aggiuntivi in una variabile che viene quindi aggiunta a un criterio di applicazione automatica di etichette esistente. Per aggiungere percorsi di OneDrive, usare il parametro *AddOneDriveLocation* con una variabile diversa, ad esempio *$OneDriveLocations*.

Per creare una nuova regola per i criteri di applicazione automatica di etichette:

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

Per i criteri di applicazione automatica di etichette esistenti, questo comando crea una nuova regola per i criteri per rilevare informazioni riservate, del tipo **Numero di previdenza sociale (SSN, Stati Uniti)**, che ha un ID entità di a44669fe-0d48-453d-a9b1-2cc83f2cba77. Per trovare gli ID entità per altri tipi di informazioni sensibili, vedere [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md).

Per altre informazioni sui cmdlet di PowerShell che supportano i criteri di applicazione automatica di etichette, sui parametri disponibili e su alcuni esempi, vedere la guida ai cmdlet seguente:

- [Get-AutoSensitivityLabelPolicy](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelPolicy](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelRule](/powershell/module/exchange/new-autosensitivitylabelrule)
- [Remove-AutoSensitivityLabelPolicy](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [Remove-AutoSensitivityLabelRule](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [Set-AutoSensitivityLabelPolicy](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [Set-AutoSensitivityLabelRule](/powershell/module/exchange/set-autosensitivitylabelrule)

## <a name="tips-to-increase-labeling-reach"></a>Suggerimenti per aumentare la portata dell'etichettatura

Anche se l'etichettatura automatica è uno dei modi più efficienti per classificare, etichettare e proteggere i file di Office di proprietà dell'organizzazione, verificare se è possibile integrarla con uno dei metodi aggiuntivi per aumentarne la portata:

- Quando si usa il [client di etichettatura unificata di Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2):

    - Per i file in archivi dati locali, ad esempio condivisioni di rete e raccolte di SharePoint Server: usare lo [scanner](/azure/information-protection/deploy-aip-scanner) per individuare le informazioni sensibili in questi file ed etichettarli in modo appropriato. Se si prevede di eseguire la migrazione o caricare questi file in SharePoint in Microsoft 365, usare lo scanner per etichettare i file prima di spostarli nel cloud.

    - Se è stata usata un'altra soluzione di etichettatura prima di usare le etichette di riservatezza: usare PowerShell e [un'impostazione avanzata per riutilizzare le etichette](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#migrate-labels-from-secure-islands-and-other-labeling-solutions) da queste soluzioni.

- Incoraggiare l'uso dell'[etichettatura manuale](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) dopo aver formato gli utenti su quali etichette di riservatezza applicare. Quando si è certi che gli utenti comprendano quale etichetta applicare, valutare la possibilità di configurare un'etichetta predefinita e l'etichettatura obbligatoria come [impostazioni dei criteri](sensitivity-labels.md#what-label-policies-can-do).

È inoltre consigliabile [contrassegnare i nuovi file come sensibili per impostazione predefinita](/sharepoint/sensitive-by-default) in SharePoint per impedire che gli utenti guest possano accedere ai nuovi file aggiunti prima che almeno un criterio DLP abbia ne analizzato il contenuto.
