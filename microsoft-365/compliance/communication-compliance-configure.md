---
title: Introduzione alla conformità delle comunicazioni
description: Impostare i criteri di conformità della comunicazione per configurare le comunicazioni dei dipendenti per la revisione.
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
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: b1ce2de627e7068124a1dfd15b84d40a2063d3a2
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210562"
---
# <a name="get-started-with-communication-compliance"></a>Introduzione alla conformità delle comunicazioni

Utilizzare i criteri di conformità della comunicazione per acquisire le comunicazioni dei dipendenti per l'esame da revisori interni o esterni. Per ulteriori informazioni su come i criteri di conformità della comunicazione consentono di monitorare le comunicazioni nell'organizzazione, vedere [Communication Compliance Policies in Microsoft 365](communication-compliance.md). Se si desidera esaminare in che modo Contoso ha configurato rapidamente un criterio di conformità della comunicazione per il monitoraggio per la lingua offensiva in Microsoft teams, Exchange Online e Yammer Communications, vedere questo [caso di studio](communication-compliance-case-study.md).

## <a name="before-you-begin"></a>Informazioni preliminari

Prima di iniziare a utilizzare la conformità alla comunicazione, è necessario confermare la [sottoscrizione Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e i componenti aggiuntivi. Per accedere e utilizzare la conformità di comunicazione, è necessario che l'organizzazione disponga di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 E3 + il componente aggiuntivo Microsoft 365 E5 Compliance
- Sottoscrizione Microsoft 365 E3 + componente aggiuntivo Microsoft 365 E5 Insider Risk Management
- Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Compliance
- Sottoscrizione Microsoft 365 a3 + componente aggiuntivo Microsoft 365 a5 Insider Risk Management
- Sottoscrizione Microsoft 365 G5 (a pagamento o versione di valutazione)
- Sottoscrizione Microsoft 365 G5 + componente aggiuntivo Microsoft 365 G5 Compliance
- Microsoft 365 G5 Subscription + Microsoft 365 G5 Insider Risk Management componente aggiuntivo
- Abbonamento a Office 365 Enterprise E5 (a pagamento o versione di valutazione)
- Abbonamento a Office 365 Enterprise E3 + il componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per le nuove sottoscrizioni, vedere note)

Gli utenti inclusi nei criteri di conformità della comunicazione devono essere assegnati a una delle licenze sopra riportate.

>[!IMPORTANT]
>La conformità avanzata di Office 365 non viene più venduta come sottoscrizione autonoma. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse funzionalità di conformità o aggiuntive.

Se non si dispone di un piano di Office 365 Enterprise E5 esistente e si desidera tentare la gestione dei rischi Insider, è possibile [aggiungere Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla sottoscrizione esistente oppure [iscriversi a una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Passaggio 1 (obbligatorio): abilitare le autorizzazioni per la conformità della comunicazione

>[!Important]
>Per impostazione predefinita, gli amministratori globali non possono accedere alle funzionalità di conformità della comunicazione. I ruoli assegnati a questo passaggio sono necessari prima che vengano accessibili tutte le funzionalità di conformità della comunicazione.

Per rendere la **conformità di comunicazione** disponibile come opzione di menu in Microsoft 365 Compliance Center, è necessario essere assegnati al ruolo di **amministratore revisione di supervisione** . È necessario creare un nuovo gruppo di ruoli per i revisori con l' **amministratore revisione di supervisione**, la **gestione dei casi**, l' **amministratore della conformità**e i ruoli di **Revisione** per esaminare e correggere i messaggi con le corrispondenze di criteri.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere [https://protection.office.com/permissions](https://protection.office.com/permissions) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro sicurezza &amp; e conformità, accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare **Crea**.

4. Nel campo **nome** assegnare un nome descrittivo al nuovo gruppo di ruoli. Selezionare **Avanti**.

5. Selezionare **Scegli ruoli** e quindi **Aggiungi**. Selezionare la casella di controllo per l' **amministratore della revisione di supervisione**, la **gestione dei casi**, l' **amministratore della conformità**e la **Revisione**, quindi selezionare **Aggiungi** e **Chiudi**. Selezionare **Avanti**.

    ![Gruppi di ruoli necessari per la conformità della comunicazione](../media/communication-compliance-role-groups-1.png)

6. Selezionare **Scegli membri** e quindi **Aggiungi**. Selezionare la casella di controllo per tutti gli utenti e i gruppi che si desidera creare criteri e gestire i messaggi con le corrispondenze di criteri, quindi fare clic su **Aggiungi** e **Chiudi**. Selezionare **Avanti**.

7. Selezionare **Crea gruppo di ruoli** per terminare.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Passaggio 2 (obbligatorio): abilitare il log di controllo

La conformità alla comunicazione richiede i registri di controllo per visualizzare gli avvisi e tenere presenti le azioni di correzione eseguite dai revisori. I registri di controllo sono un riepilogo di tutte le attività associate a un criterio organizzativo definito o in qualsiasi momento di un criterio di conformità comunicazione modifiche.

Per istruzioni dettagliate su come abilitare il controllo, vedere [attivazione o disattivazione della ricerca del registro di controllo](turn-audit-log-search-on-or-off.md). Dopo aver attivato il controllo, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. È sufficiente eseguire questa operazione una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Passaggio 3 (facoltativo): configurare i gruppi per la conformità della comunicazione

 Quando si crea un criterio di conformità della comunicazione, è possibile definire gli utenti che hanno esaminato le comunicazioni e che eseguono le revisioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica per identificare singoli o gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per gli utenti che hanno la propria comunicazione riesaminata e i gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà controllato.

Utilizzare il seguente grafico per facilitare la configurazione dei gruppi nell'organizzazione per i criteri di conformità della comunicazione:

| **Membro del criterio** | **Gruppi supportati** | **Gruppi non supportati** |
|:-----|:-----|:-----|
|Utenti controllati <br> Utenti non controllati | Gruppi di distribuzione <br> Gruppi di Microsoft 365 | Gruppi di distribuzione dinamici |
| Revisori | Nessuno | Gruppi di distribuzione <br> Gruppi di distribuzione dinamici <br> Gruppi di sicurezza abilitati alla posta elettronica |
  
Quando si seleziona un gruppo di Microsoft 365 per gli utenti controllati, il criterio monitora il contenuto della cassetta postale condivisa e dei canali Microsoft teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le singole cassette postali degli utenti.

Per ulteriori informazioni sulla configurazione dei gruppi, vedere:

- [Creazione e gestione dei gruppi di distribuzione](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Panoramica dei gruppi di Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Passaggio 4 (facoltativo): verificare che il tenant di Yammer sia in modalità nativa

In modalità nativa, tutti gli utenti di Yammer sono in Azure Active Directory (AAD), tutti i gruppi sono gruppi di Office 365 e tutti i file vengono archiviati in SharePoint Online. Il tenant di Yammer deve essere in modalità nativa per i criteri di conformità della comunicazione per analizzare e identificare le conversazioni rischiose nei messaggi privati e nelle conversazioni della community in Yammer.

Per ulteriori informazioni sulla configurazione di Yammer in modalità nativa, vedere:

- [Panoramica della modalità nativa di Yammer in Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurare la rete Yammer per la modalità nativa per Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Passaggio 5 (obbligatorio): creare un criterio di conformità della comunicazione
  
>[!Important]
>L'utilizzo di PowerShell per la creazione e la gestione di criteri di conformità della comunicazione non è supportato. Per creare e gestire questi criteri, è necessario utilizzare i controlli di gestione dei criteri nella [soluzione Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365 selezionare **conformità comunicazione**.
  
3. Selezionare la scheda **criteri** .

4. Selezionare **create Policy** per creare e configurare un nuovo criterio da un modello o per creare e configurare un criterio personalizzato.

    Se si sceglie un modello di criteri per creare un criterio, sarà necessario:

    - Confermare o aggiornare il nome del criterio. Non è possibile modificare i nomi dei criteri dopo la creazione del criterio.
    - Scegliere gli utenti o i gruppi da controllare, inclusa la scelta degli utenti o dei gruppi che si desidera escludere.
    - Scegliere i revisori per il criterio. I revisori sono utenti singoli e tutti i revisori devono disporre di cassette postali ospitate in Exchange Online. Revisori aggiunti qui sono i revisori che è possibile scegliere quando si effettua l'escalation di un avviso nel flusso di lavoro di analisi e correzione. Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che informa gli utenti dell'assegnazione ai criteri e fornisce collegamenti alle informazioni sul processo di revisione.
    - Scegliere un campo di condizioni limitate, in genere un tipo di informazioni riservate o un dizionario di parole chiave da applicare al criterio.

    Se si sceglie di utilizzare la procedura guidata dei criteri per creare un criterio personalizzato, sarà necessario:

    - Assegnare al criterio un nome e una descrizione. Non è possibile modificare i nomi dei criteri dopo la creazione del criterio.
    - Scegliere gli utenti o i gruppi da controllare, inclusi tutti gli utenti dell'organizzazione, utenti e gruppi specifici o altri utenti e gruppi che si desidera escludere.
    - Scegliere i revisori per il criterio. I revisori sono utenti singoli e tutti i revisori devono disporre di cassette postali ospitate in Exchange Online. Revisori aggiunti qui sono i revisori che è possibile scegliere quando si effettua l'escalation di un avviso nel flusso di lavoro di analisi e correzione. Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che informa gli utenti dell'assegnazione ai criteri e fornisce collegamenti alle informazioni sul processo di revisione.
    - Scegliere i canali di comunicazione da analizzare, tra cui Exchange, Microsoft teams, Yammer o Skype for business. Se si è configurato un connettore in Microsoft 365, è inoltre possibile scegliere di eseguire l'analisi delle origini di terze parti.
    - Scegliere la direzione di comunicazione da monitorare, incluse le comunicazioni in ingresso, in uscita o interne.
    - Definire le [condizioni](communication-compliance-feature-reference.md#ConditionalSettings)dei criteri di conformità della comunicazione. È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.
    - Scegliere se si desidera includere tipi di informazioni riservate. In questo passaggio è possibile selezionare i tipi di informazioni riservate predefinite e personalizzate. Scegliere tra tipi di informazioni riservate personalizzate esistenti o dizionari di parole chiave personalizzati nella procedura guidata criteri di conformità della comunicazione. È possibile creare questi elementi prima di eseguire la procedura guidata, se necessario. È inoltre possibile creare nuovi tipi di informazioni riservate dall'interno della procedura guidata criteri di conformità della comunicazione.
    - Scegliere se si desidera abilitare i classificatori. I classificatori possono rilevare la lingua inappropriata inviata o ricevuta nel corpo dei messaggi di posta elettronica o di altri tipi di testo.

    >[!CAUTION]
    >Il classificatore incorporato del **linguaggio offensivo** è obsoleto perché produce un numero elevato di falsi positivi. Non utilizzarlo e, se lo si sta attualmente utilizzando, è consigliabile spostarne i processi aziendali. È consigliabile utilizzare invece i classificatori incorporati per la **minaccia**, la **profanità**e la **molestia** .

    - Definire la percentuale di comunicazioni da esaminare.
    - Esaminare le selezioni dei criteri e creare il criterio.

5. Selezionare **Crea criterio** quando si utilizzano i modelli o **Invia** quando si utilizza la procedura guidata per i criteri personalizzati.

6. La pagina **criteri è stata creata** viene visualizzata con linee guida su quando verranno attivati i criteri e quali comunicazioni verranno acquisite.

## <a name="step-6-optional-create-employee-notice-templates"></a>Passaggio 6 (facoltativo): creare modelli di avviso per i dipendenti

Se si desidera avere la possibilità di rispondere a un avviso di criteri inviando un avviso di sollecito al dipendente associato, è necessario creare almeno un modello di avviso nell'organizzazione. I campi del modello di avviso sono modificabili prima di essere inviati come parte del processo di correzione degli avvisi e la creazione di un modello di avviso personalizzato per ogni criterio di conformità della comunicazione è consigliata.

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **conformità comunicazione**.

3. Selezionare la scheda **modelli di avviso** e quindi fare clic su **Crea modello di avviso**.

4. Nella pagina **modifica modello di avviso** completare i seguenti campi:

    - Nome del modello di avviso (obbligatorio)
    - Invia da (obbligatorio)
    - CC e Ccn (facoltativo)
    - Subject (obbligatorio)
    - Corpo del messaggio (obbligatorio)

5. Selezionare **Salva** per creare e salvare il modello di avviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Passaggio 7 (facoltativo): testare i criteri di conformità della comunicazione

Dopo aver creato un criterio di conformità della comunicazione, è consigliabile testarlo per assicurarsi che le condizioni definite vengano applicate correttamente dal criterio. È inoltre possibile [testare i criteri di prevenzione della perdita di dati (DLP)](create-test-tune-dlp-policy.md) se i criteri di conformità della comunicazione includono tipi di informazioni riservate. Assicurarsi di fornire i criteri per l'attivazione in modo che le comunicazioni che si desidera testare vengano acquisite.

Eseguire la procedura seguente per testare i criteri di conformità della comunicazione:

1. Aprire un client di posta elettronica, Microsoft teams o Yammer mentre è stato eseguito l'accesso come utente controllato definito nel criterio che si desidera sottoporre a test.
2. Inviare un messaggio di posta elettronica, Microsoft teams chat o Yammer che soddisfi i criteri definiti nel criterio di conformità della comunicazione. Questo test può essere una parola chiave, le dimensioni degli allegati, il dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo indulgenti.

    > [!NOTE]
    > Le comunicazioni in tutti i canali di origine possono richiedere fino a 24 ore per il processo completo in un criterio.

3. Accedere a Microsoft 365 come un revisore designato nei criteri di conformità della comunicazione. Passare a **avvisi conformità comunicazione**  >  **Alerts** per visualizzare gli avvisi per i criteri.

4. Correggere l'avviso utilizzando i controlli di correzione e verificare che l'avviso sia stato risolto correttamente.
