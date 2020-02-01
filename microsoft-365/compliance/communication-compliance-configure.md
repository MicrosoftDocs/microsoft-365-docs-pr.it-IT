---
title: Configurare la conformità delle comunicazioni (anteprima)
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
ms.openlocfilehash: 24c87b8244b2dc53f58a07784c07231fb1588121
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595843"
---
# <a name="configure-communication-compliance-in-microsoft-365-preview"></a>Configurare la conformità delle comunicazioni in Microsoft 365 (anteprima)

> [!IMPORTANT]
> Questo argomento si applica alla configurazione della conformità di comunicazione in un abbonamento a Microsoft 365. Se si desidera configurare i criteri di supervisione per una sottoscrizione a Office 365, vedere [Configure supervisioning for office 365](supervision-policies.md).

Utilizzare i criteri di conformità della comunicazione per acquisire le comunicazioni dei dipendenti per l'esame da revisori interni o esterni. Per ulteriori informazioni su come i criteri di conformità della comunicazione consentono di monitorare le comunicazioni nell'organizzazione, vedere [Communication Compliance Policies in Microsoft 365](communication-compliance.md).

> [!NOTE]
> Gli utenti monitorati dai criteri di conformità della comunicazione devono avere una licenza di conformità Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato oppure essere inclusi in un abbonamento a Office 365 Enterprise E5.
> Se non si dispone di un piano Enterprise E5 esistente e si vuole provare la conformità alla comunicazione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Seguire questa procedura per configurare e usare la conformità della comunicazione nell'organizzazione Microsoft 365:
  
- **Passaggio 1 (facoltativo)**: [configurare i gruppi per la conformità della comunicazione](#step-1-set-up-groups-for-communication-compliance-optional) 

    Prima di iniziare a utilizzare la conformità alla comunicazione, determinare gli utenti che devono esaminare le comunicazioni e che eseguono le revisioni. Se si desidera iniziare a usare solo alcuni utenti per vedere come funziona la conformità di comunicazione, è possibile ignorare la configurazione dei gruppi per il momento.

- **Passaggio 2 (obbligatorio)**: [rendere la conformità della comunicazione disponibile nell'organizzazione](#step-2-make-communication-compliance-available-in-your-organization-required)

    Aggiungersi al ruolo **amministratore revisione di supervisione** per impostare i criteri. È inoltre necessario creare un nuovo gruppo con l' **amministratore revisione di supervisione**, la **gestione dei casi**e i ruoli di **Revisione** per persone o gruppi che avranno un'azione di verifica e correzione nei messaggi con corrispondenze di criteri. Tutti gli utenti a cui è assegnato questo ruolo possono accedere alla pagina **conformità comunicazione** nel centro conformità di Microsoft 365. Se il messaggio di posta elettronica rivisualizzabile è ospitato in Exchange Online, ogni revisore deve disporre dell' [accesso remoto a PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Passaggio 3 (obbligatorio)**: [impostare un criterio di conformità della comunicazione](#step-3-create-a-communication-compliance-policy-required)

    È possibile creare criteri di conformità della comunicazione nel centro conformità di Microsoft 365. Questi criteri definiscono le comunicazioni soggette a revisione nell'organizzazione e specifica chi esegue le revisioni. Le comunicazioni includono la posta elettronica, Microsoft teams, Skype for business e le comunicazioni della piattaforma di terze parti (come Facebook, Twitter e così via).

- **Passaggio 4 (facoltativo)**: [creare modelli di avviso](#step-4-create-employee-notice-templates-optional) per i dipendenti

    Creare modelli di avviso personalizzati per inviare notifiche tramite posta elettronica ai dipendenti come opzione di correzione per le corrispondenze di criteri.

- **Passaggio 5 (facoltativo)**: [testare i criteri di conformità della comunicazione](#step-5-test-your-communication-compliance-policy-optional)

    Testare i criteri di conformità della comunicazione per assicurarsi che funzioni come desiderato. È importante garantire che la strategia di conformità soddisfi gli standard.

- **Passaggio 6 (facoltativo)**: [abilitare il controllo per i criteri di conformità della comunicazione](#step-6-enable-auditing-for-your-communication-compliance-policies-optional)

    Abilitare il controllo per l'organizzazione per registrare le attività di gestione per i criteri di conformità della comunicazione.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>Passaggio 1: configurare i gruppi per la conformità delle comunicazioni (facoltativo)

 Quando si crea un criterio di conformità della comunicazione, è possibile definire gli utenti che hanno esaminato le comunicazioni e che eseguono le revisioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica per identificare singoli o gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per gli utenti che hanno la propria comunicazione riesaminata e i gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà controllato.

Utilizzare il seguente grafico per facilitare la configurazione dei gruppi nell'organizzazione per i criteri di conformità della comunicazione:

| **Membro del criterio** | **Gruppi supportati** | **Gruppi non supportati** |
|:-----|:-----|:-----|
|Utenti controllati <br> Utenti non controllati | Gruppi di distribuzione <br> Gruppi di Office 365 | Gruppi di distribuzione dinamici |
| Revisori | Gruppi di sicurezza abilitati alla posta elettronica  | Gruppi di distribuzione <br> Gruppi di distribuzione dinamici |
  
Quando si seleziona un gruppo di Office 365 per gli utenti controllati, il criterio monitora il contenuto della cassetta postale di Office 365 condivisa e dei canali Microsoft teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le singole cassette postali degli utenti.

Per ulteriori informazioni sulla configurazione dei gruppi, vedere:

- [Creazione e gestione dei gruppi di distribuzione](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gestire i gruppi di protezione abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Panoramica dei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a>Passaggio 2: rendere la conformità della comunicazione disponibile nell'organizzazione (obbligatorio)

> [!Important]
> Per impostazione predefinita, gli amministratori globali non possono accedere alle funzionalità di conformità della comunicazione. I ruoli assegnati a questo passaggio sono necessari prima che vengano accessibili tutte le funzionalità di conformità della comunicazione.

Per rendere la **conformità di comunicazione** disponibile come opzione di menu in Microsoft 365 Compliance Center, è necessario essere assegnati al ruolo di **amministratore revisione di supervisione** . Inoltre, per esaminare e correggere i messaggi con le corrispondenze di criteri, è necessario creare un gruppo per i revisori con l' **amministratore revisione di supervisione**, la **gestione dei casi**e i ruoli di **Revisione** .

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere [https://protection.office.com/permissions](https://protection.office.com/permissions) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro sicurezza e conformità di Microsoft Office 365 accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare **Crea**.

4. Nel campo **nome** assegnare un nome descrittivo al nuovo gruppo di ruoli.  Select **Next**. 

5. Selezionare **Scegli ruoli** e quindi **Aggiungi**. Selezionare la casella di controllo per l' **amministratore revisione di supervisione**, la **gestione dei casi**e la **Revisione**, quindi selezionare **Aggiungi** e **Chiudi**.  Select **Next**. 

    ![Gruppi di ruoli necessari per la conformità della comunicazione](media/communication-compliance-role-groups.png)

6. Selezionare **Scegli membri** e quindi **Aggiungi**. Selezionare la casella di controllo per tutti gli utenti e i gruppi che si desidera creare criteri e gestire i messaggi con le corrispondenze di criteri, quindi fare clic su **Aggiungi** e **Chiudi**.  Select **Next**. 

7. Selezionare **Crea gruppo di ruoli** per terminare.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-3-create-a-communication-compliance-policy-required"></a>Passaggio 3: creare un criterio di conformità della comunicazione (obbligatorio)
  
1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365 selezionare **conformità comunicazione**.
  
3. Selezionare la scheda **criteri** .

4. Selezionare **create Policy** per creare e configurare un nuovo criterio da un modello o per creare e configurare un criterio personalizzato.

    Se si sceglie un modello di criteri per creare un criterio, sarà necessario:

    - Confermare o aggiornare il nome del criterio. Non è possibile modificare i nomi dei criteri dopo la creazione del criterio.
    - Scegliere gli utenti o i gruppi da controllare, inclusa la scelta degli utenti o dei gruppi che si desidera escludere.
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o [gruppi di sicurezza abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.
    - Scegliere un campo di condizioni limitate, in genere un tipo di informazioni riservate o un dizionario di parole chiave da applicare al criterio.

    Se si sceglie di utilizzare la procedura guidata dei criteri per creare un criterio personalizzato, sarà necessario:

    - Assegnare al criterio un nome e una descrizione. Non è possibile modificare i nomi dei criteri dopo la creazione del criterio.
    - Scegliere gli utenti o i gruppi da controllare, inclusi tutti gli utenti dell'organizzazione, utenti e gruppi specifici o altri utenti e gruppi che si desidera escludere. -
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o [gruppi di sicurezza abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.
    - Scegliere i canali di comunicazione da analizzare, tra cui Exchange, Microsoft teams o Skype for business. Se si è configurato un connettore in Microsoft 365, è inoltre possibile scegliere di eseguire l'analisi delle origini di terze parti.
    - Scegliere la direzione di comunicazione da monitorare, incluse le comunicazioni in ingresso, in uscita o interne.
    - Definire le [condizioni](communication-compliance-feature-reference.md#ConditionalSettings)dei criteri di conformità della comunicazione. È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.
    - Scegliere se si desidera includere tipi di informazioni riservate. In questo passaggio è possibile selezionare i tipi di informazioni riservate predefinite e personalizzate. Scegliere tra tipi di informazioni riservate personalizzate esistenti o dizionari di parole chiave personalizzati nella procedura guidata criteri di conformità della comunicazione. È possibile creare questi elementi prima di eseguire la procedura guidata, se necessario. È inoltre possibile creare nuovi tipi di informazioni riservate dall'interno della procedura guidata criteri di conformità della comunicazione.
    - Scegliere se si desidera abilitare il classificatore di lingua offensivo. Questo classificatore rileva la lingua inappropriata inviata o ricevuta nel corpo dei messaggi di posta elettronica.
    - Definire la percentuale di comunicazioni da esaminare.
    - Esaminare le selezioni dei criteri e creare il criterio.

5. Selezionare **Crea criterio** quando si utilizzano i modelli o **Invia** quando si utilizza la procedura guidata per i criteri personalizzati.

6. La pagina **criteri è stata creata** viene visualizzata con linee guida su quando verranno attivati i criteri e quali comunicazioni verranno acquisite.

## <a name="step-4-create-employee-notice-templates-optional"></a>Passaggio 4: creare modelli di avviso per i dipendenti (facoltativo)

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

## <a name="step-5-test-your-communication-compliance-policy-optional"></a>Passaggio 5: testare i criteri di conformità della comunicazione (facoltativo)

Dopo aver creato un criterio di conformità della comunicazione, è consigliabile testarlo per assicurarsi che le condizioni definite vengano applicate correttamente dal criterio. È inoltre possibile [testare i criteri di prevenzione della perdita di dati (DLP)](create-test-tune-dlp-policy.md) se i criteri di conformità della comunicazione includono tipi di informazioni riservate. Assicurarsi di fornire i criteri per l'attivazione in modo che le comunicazioni che si desidera testare vengano acquisite.

Eseguire la procedura seguente per testare i criteri di conformità della comunicazione:

1. Aprire un client di posta elettronica o Microsoft teams mentre è stato eseguito l'accesso come utente controllato definito nel criterio che si desidera sottoporre a test.
2. Inviare un messaggio di posta elettronica o Microsoft teams chat che soddisfi i criteri definiti nel criterio di conformità della comunicazione. Questo test può essere una parola chiave, le dimensioni degli allegati, il dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo indulgenti.

    > [!NOTE]
    > Le comunicazioni in tutti i canali di origine possono richiedere fino a 24 ore per il processo completo in un criterio.

3. Accedere a Microsoft 365 come un revisore designato nei criteri di conformità della comunicazione. Passare a > **avvisi** **conformità comunicazione**per visualizzare gli avvisi per i criteri.

4. Correggere l'avviso utilizzando i controlli di correzione e verificare che l'avviso sia stato risolto correttamente.

## <a name="step-6-enable-auditing-for-your-communication-compliance-policies-optional"></a>Passaggio 6: abilitare il controllo per i criteri di conformità della comunicazione (facoltativo)

Dopo aver testato i criteri, è possibile abilitare il controllo in modo che le attività associate alla gestione della conformità della comunicazione vengano registrate. Può trattarsi di un riepilogo di tutte le attività associate a un criterio organizzativo definito o in qualsiasi momento in cui cambia il criterio di conformità della comunicazione.

Quando il controllo è abilitato, i criteri di conformità della comunicazione hanno percorsi di controllo incorporati per una completa preparazione per i controlli interni o esterni. È possibile utilizzare il controllo **Esporta attività di revisione** nella pagina principale per qualsiasi criterio per generare un file di controllo o per visualizzare le attività di controllo nel log di controllo unificato se il controllo è abilitato.

Per attivare il controllo, fare clic su **Avvia registrazione attività utente e amministratore** nella pagina di **ricerca del registro di controllo** nel centro sicurezza & conformità di Office 365. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. Dopo aver attivato il controllo, viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio d'ore dopo il completamento della preparazione. Questa procedura deve essere eseguita una sola volta. Per ulteriori informazioni sul log di controllo, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

