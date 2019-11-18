---
title: Configurare la conformità alla comunicazione per Microsoft 365 (anteprima)
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
description: Impostare i criteri di conformità della comunicazione per configurare le comunicazioni dei dipendenti per la revisione.
ms.openlocfilehash: 76b28443d2fa77967933ea61f2724a2a5ff072be
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "38686361"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a>Configurare la conformità alla comunicazione per Microsoft 365 (anteprima)

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

    Aggiungersi al ruolo **amministratore revisione di supervisione** per impostare i criteri. È inoltre necessario assegnare i ruoli di **gestione** e **Revisione** dei casi a persone o gruppi che avranno un'azione investigativa e di correzione dei messaggi con corrispondenze di criteri. Tutti gli utenti a cui è assegnato questo ruolo possono accedere alla pagina **conformità comunicazione** nel centro conformità di Microsoft 365. Se il messaggio di posta elettronica rivisualizzabile è ospitato in Exchange Online, ogni revisore deve disporre dell' [accesso remoto a PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Passaggio 3 (obbligatorio)**: [impostare un criterio di conformità della comunicazione](#step-3-create-a-communication-compliance-policy-required)

    È possibile creare criteri di conformità della comunicazione nel centro conformità di Microsoft 365. Questi criteri definiscono le comunicazioni soggette a revisione nell'organizzazione e specifica chi esegue le revisioni. Le comunicazioni includono la posta elettronica, Microsoft teams, Skype for business e le comunicazioni della piattaforma di terze parti (come Facebook, Twitter e così via).

- **Passaggio 4 (facoltativo)**: [creare modelli di avviso](#step-4-create-employee-notice-templates-optional) per i dipendenti

    Creare modelli di avviso personalizzati per inviare notifiche tramite posta elettronica ai dipendenti come opzione di correzione per le corrispondenze di criteri.

- **Passaggio 5 (facoltativo)**: [testare i criteri di conformità della comunicazione](#step-5-test-your-communication-compliance-policy-optional)

    Testare i criteri di conformità della comunicazione per assicurarsi che funzioni come desiderato. È importante garantire che la strategia di conformità soddisfi gli standard.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>Passaggio 1: configurare i gruppi per la conformità delle comunicazioni (facoltativo)

 Quando si crea un criterio di conformità della comunicazione, è possibile definire gli utenti che hanno esaminato le comunicazioni e che eseguono le revisioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica per identificare singoli o gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per gli utenti che hanno la propria comunicazione riesaminata e i gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà controllato.

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

Per rendere la **conformità di comunicazione** disponibile come opzione di menu in Microsoft 365 Compliance Center, è necessario essere assegnati al ruolo di amministratore revisione di supervisione. Per esaminare e correggere i messaggi con le corrispondenze di criteri, è necessario che i ruoli di gestione e **Revisione** dei **casi** siano assegnati.
  
A tale scopo, è possibile aggiungere se stessi come membro del gruppo di ruolo revisione di supervisione oppure creare un nuovo gruppo di ruoli.
  
### <a name="add-required-roles-to-the-supervisory-reviewer-role-group"></a>Aggiungere i ruoli necessari al gruppo di ruoli revisore di supervisione

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, andare a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli **revisione di supervisione** e quindi fare clic su **modifica** nella sezione **ruoli assegnati** della pagina dei dettagli.

4. Selezionare **modifica**, quindi fare clic su **Aggiungi**. Selezionare la casella di controllo per la gestione e la **Revisione**dei **casi** , quindi fare clic su **Aggiungi**.

5. Fare clic su **fine**e quindi su **Salva**.

6. Nella sezione **membri** selezionare **modifica** per aggiungere gli utenti a cui si desidera gestire la conformità di comunicazione per l'organizzazione.

7. Selezionare **modifica**, quindi fare clic su **Aggiungi**. Selezionare la casella di controllo per tutti gli utenti e i gruppi che si desidera gestire i messaggi con le corrispondenze di criteri, quindi selezionare **Aggiungi**.

8. Fare clic su **fine**e quindi su **Salva**.

9. Selezionare **Chiudi** per uscire dalla pagina dei dettagli del gruppo di ruoli.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro conformità di Microsoft 365, andare a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare **Crea**.

4. Nel campo **nome** assegnare un nome descrittivo al nuovo gruppo di ruoli.  Select **Next**. 

5. Selezionare **Scegli ruoli** e quindi **Aggiungi**. Selezionare la casella di controllo per l' **amministratore revisione di supervisione**, la **gestione dei casi**e la **Revisione**, quindi selezionare **Aggiungi** e **Chiudi**.  Select **Next**. 

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
    - Scegliere gli utenti o i gruppi da controllare, inclusa la scelta di tutti gli utenti dell'organizzazione, di utenti e gruppi specifici o di altri utenti e gruppi che si desidera escludere. -
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o [gruppi di sicurezza abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.
    - Scegliere i canali di comunicazione da analizzare, tra cui Exchange, Microsoft teams o Skype for business. È inoltre possibile scegliere di analizzare le origini di terze parti se è stato configurato un connettore in Microsoft 365.
    - Scegliere la direzione di comunicazione da monitorare, incluse le comunicazioni in ingresso, in uscita o interne.
    - Definire le [condizioni](communication-compliance-feature-reference.md#ConditionalSettings)dei criteri di conformità della comunicazione. È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.
    - Scegliere se si desidera includere tipi di informazioni riservate. È possibile selezionare i tipi di informazioni riservate predefinite e personalizzate. Scegliere tra tipi di informazioni riservate personalizzate esistenti o dizionari per parole chiave personalizzate nella procedura guidata criteri di conformità della comunicazione, è possibile creare questi elementi prima di eseguire la procedura guidata, se necessario. Se lo si desidera, è anche possibile creare nuovi tipi di informazioni riservate dall'interno della procedura guidata criteri di conformità della comunicazione.
    - Scegliere se si desidera abilitare il modello di lingua offensivo. In questo modo viene rilevato il linguaggio inappropriato inviato o ricevuto nel corpo dei messaggi di posta elettronica.
    - Definire la percentuale di comunicazioni da esaminare.
    - Esaminare le selezioni dei criteri e creare il criterio.

5. Selezionare **Crea criterio** quando si utilizzano i modelli o **Invia** quando si utilizza la procedura guidata per i criteri personalizzati.

6. La pagina **criteri è stata creata** viene visualizzata con linee guida su quando verranno attivati i criteri e le comunicazioni verranno acquisite.

## <a name="step-4-create-employee-notice-templates-optional"></a>Passaggio 4: creare modelli di avviso per i dipendenti (facoltativo)

Se si desidera avere la possibilità di rispondere a un avviso di criteri inviando un avviso di sollecito al dipendente associato, è necessario creare almeno un modello di avviso nell'organizzazione. I campi del modello di avviso sono modificabili prima dell'invio come parte del processo di correzione degli avvisi e la creazione di un modello di avviso personalizzato per ogni criterio di conformità della comunicazione è consigliata.

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

Dopo aver creato un criterio di conformità della comunicazione, è consigliabile verificare che le condizioni definite vengano applicate in modo corretto dal criterio. È inoltre possibile [testare i criteri di prevenzione della perdita di dati (DLP)](create-test-tune-dlp-policy.md) se i criteri di conformità della comunicazione includono tipi di informazioni riservate. Assicurarsi di fornire i criteri per l'attivazione in modo che le comunicazioni che si desidera testare vengano acquisite.

Eseguire la procedura seguente per testare i criteri di conformità della comunicazione:

1. Aprire un client di posta elettronica o Microsoft teams connesso come utente controllato definito nel criterio che si desidera sottoporre a test.
2. Inviare un messaggio di posta elettronica o Microsoft teams chat che soddisfi i criteri definiti nel criterio di conformità della comunicazione. Può trattarsi di una parola chiave, dimensioni degli allegati, dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo indulgenti.

    > [!NOTE]
    > Le comunicazioni in tutti i canali di origine possono richiedere fino a 24 ore per il processo completo in un criterio.

3. Accedere a Microsoft 365 come un revisore designato nei criteri di conformità della comunicazione. Passare a > **avvisi** **conformità comunicazione**per visualizzare gli avvisi per i criteri.

4. Correggere l'avviso utilizzando i controlli di correzione e verificare che l'avviso sia stato risolto correttamente.
