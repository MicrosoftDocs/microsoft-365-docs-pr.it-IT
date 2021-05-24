---
title: Introduzione alla conformità delle comunicazioni
description: Configurare i criteri di conformità delle comunicazioni per configurare le comunicazioni utente per la revisione.
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: eed486120673abc513490f4892069ee8fd9bba21
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636159"
---
# <a name="get-started-with-communication-compliance"></a>Introduzione alla conformità delle comunicazioni

Utilizzare i criteri di conformità delle comunicazioni per identificare le comunicazioni degli utenti per l'esame da parte di revisori interni o esterni. Per ulteriori informazioni sul modo in cui i criteri di conformità delle comunicazioni consentono di monitorare le comunicazioni [nell'organizzazione,](communication-compliance.md)vedere Criteri di conformità delle comunicazioni in Microsoft 365 . Se si desidera esaminare il modo in cui Contoso ha configurato rapidamente un criterio di conformità delle comunicazioni per monitorare il linguaggio offensivo nelle comunicazioni Microsoft Teams, Exchange Online e Yammer, vedere questo [case study.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Abbonamenti e licenze

Prima di iniziare a usare la conformità alle comunicazioni, è consigliabile confermare l'abbonamento [Microsoft 365 ed](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) eventuali componenti aggiuntivi. Per accedere e usare la conformità delle comunicazioni, l'organizzazione deve disporre di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:

- Microsoft 365 E5 (versione di valutazione o a pagamento)
- Microsoft 365 E3 abbonamento + Microsoft 365 E5 Compliance componente aggiuntivo
- Microsoft 365 E3 e il Microsoft 365 E5 Insider Risk Management
- Microsoft 365 Sottoscrizione A5 (versione di valutazione o a pagamento)
- Microsoft 365 Sottoscrizione A3 + componente aggiuntivo Microsoft 365 conformità A5
- Microsoft 365 Sottoscrizione A3 + il Microsoft 365 A5 Insider Risk Management
- Microsoft 365 Abbonamento G5 (versione di valutazione o a pagamento)
- Microsoft 365 Sottoscrizione G5 + componente aggiuntivo Microsoft 365 conformità G5
- Microsoft 365 Sottoscrizione G5 + il Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise Abbonamento E5 (versione di valutazione o a pagamento)
- Office 365 A5 abbonamento (versione di valutazione o a pagamento)
- Office 365 Enterprise Sottoscrizione E3 + Office 365 Advanced Compliance componente aggiuntivo (non più disponibile per le nuove sottoscrizioni, vedere nota)

Agli utenti inclusi nei criteri di conformità delle comunicazioni deve essere assegnata una delle licenze precedenti.

>[!IMPORTANT]
>Office 365 Advanced Compliance non viene più venduto come abbonamento autonomo. Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse o ulteriori funzionalità di conformità.

Se non si dispone di un piano Office 365 Enterprise E5 esistente e si desidera provare la conformità delle comunicazioni, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Passaggio 1 (obbligatorio): abilitare le autorizzazioni per la conformità delle comunicazioni

>[!Important]
>Per impostazione predefinita, gli amministratori globali non hanno accesso alle funzionalità di conformità delle comunicazioni. I ruoli assegnati in questo passaggio sono necessari prima che le funzionalità di conformità della comunicazione siano accessibili. Dopo aver configurato i gruppi di ruoli, potrebbero essere necessarie fino a 30 minuti per applicare le autorizzazioni del gruppo di ruoli agli utenti assegnati all'interno dell'organizzazione.

Esistono cinque gruppi di ruoli utilizzati per configurare le autorizzazioni per gestire le funzionalità di conformità delle comunicazioni. Per rendere **disponibile la** conformità delle comunicazioni come opzione di menu nel Centro conformità di Microsoft 365 e per continuare con questi passaggi di configurazione, è necessario essere assegnati ai gruppi di ruoli Communication *Compliance* o Communication *Compliance Admin.* Per accedere e gestire le funzionalità di conformità delle comunicazioni dopo la configurazione iniziale, gli utenti devono essere membri di almeno un gruppo di ruoli di conformità delle comunicazioni.

A seconda di come si desidera gestire i criteri di comunicazione e gli avvisi, è necessario assegnare gli utenti a gruppi di ruoli specifici. È possibile assegnare utenti con responsabilità di conformità diverse a gruppi di ruoli specifici per gestire diverse aree di funzionalità di conformità delle comunicazioni. In caso contrario, è possibile decidere di assegnare tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati al gruppo di ruoli *Conformità* comunicazioni. Utilizzare uno o più gruppi di ruoli per soddisfare al meglio i requisiti di gestione della conformità.

Scegliere tra queste opzioni del gruppo di ruoli per la configurazione della conformità delle comunicazioni:

| Ruolo | Autorizzazioni del ruolo |
|:-----|:-----|
| **Conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per gestire la conformità delle comunicazioni per l'organizzazione in un singolo gruppo. Aggiungendo tutti gli account utente per amministratori, analisti, investigatori e visualizzatori designati, è possibile configurare le autorizzazioni di conformità delle comunicazioni in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di conformità delle comunicazioni. Questa configurazione è il modo più semplice per iniziare rapidamente a utilizzare la conformità delle comunicazioni ed è adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti distinti. |
| **Amministratore per la conformità delle comunicazioni** | Utilizzare questo gruppo di ruoli per configurare inizialmente la conformità delle comunicazioni e successivamente per separare gli amministratori di conformità delle comunicazioni in un gruppo definito. Gli utenti assegnati a questo gruppo di ruoli possono creare, leggere, aggiornare ed eliminare criteri di conformità delle comunicazioni, impostazioni globali e assegnazioni di gruppi di ruoli. Gli utenti assegnati a questo gruppo di ruoli non possono visualizzare gli avvisi dei messaggi. |
| **Communication Compliance Analyst** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che fungeranno da analisti della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i criteri in cui sono assegnati come revisori, visualizzare i metadati dei messaggi (non il contenuto del messaggio), inoltrare ad altri revisori o inviare notifiche agli utenti. Gli analisti non possono risolvere gli avvisi in sospeso. |
| **Communication Compliance Investigator** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che agiranno come investigatori della conformità delle comunicazioni. Gli utenti assegnati a questo gruppo di ruoli possono visualizzare i metadati e il contenuto dei messaggi, inoltrare a revisori aggiuntivi, inoltrare a un caso di Advanced eDiscovery, inviare notifiche agli utenti e risolvere l'avviso. |
| **Visualizzatore della conformità delle comunicazioni** | Utilizzare questo gruppo per assegnare autorizzazioni agli utenti che gestiranno i report di comunicazione. Gli utenti assegnati a questo gruppo di ruoli possono accedere a tutti i widget di report nella home page di conformità delle comunicazioni e possono visualizzare tutti i report di conformità delle comunicazioni. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opzione 1: assegnare tutti gli utenti di conformità al gruppo di ruoli Conformità comunicazione

1. Accedere usando [https://protection.office.com/permissions](https://protection.office.com/permissions) le credenziali per un account amministratore nell'Microsoft 365 aziendale.

2. Nel Centro &amp; sicurezza e conformità passare a **Autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il *gruppo di ruoli Conformità* comunicazione, quindi selezionare Modifica gruppo di **ruoli.**

4. Selezionare **Scegli membri** nel riquadro di spostamento sinistro, quindi selezionare **Modifica.**

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al *gruppo di* ruoli Conformità comunicazioni.

6. Selezionare **Aggiungi**, quindi **Fine**.

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opzione 2: assegnare utenti a gruppi di ruoli di conformità delle comunicazioni specifici

Utilizzare questa opzione per assegnare utenti a gruppi di ruoli specifici per segmentare l'accesso e le responsabilità di conformità delle comunicazioni tra i diversi utenti dell'organizzazione.

1. Accedere usando [https://protection.office.com/permissions](https://protection.office.com/permissions) le credenziali per un account amministratore nell'Microsoft 365 aziendale.

2. Nel Centro &amp; sicurezza e conformità passare a **Autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare uno dei gruppi di ruoli di conformità delle comunicazioni, quindi **selezionare Modifica gruppo di ruoli.**

4. Selezionare **Scegli membri** nel riquadro di spostamento sinistro, quindi selezionare **Modifica.**

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi**, quindi **Fine**.

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli.

8. Selezionare il gruppo di ruoli di conformità alle comunicazioni successivo, quindi ripetere i passaggi da 4 a 7 per ogni gruppo di ruoli necessario.

9. Selezionare **Chiudi** per completare la procedura.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Autorizzazioni nel Centro conformità.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Passaggio 2 (obbligatorio): abilitare il log di controllo

Conformità delle comunicazioni richiede log di audit per visualizzare gli avvisi e tenere traccia delle azioni di correzione intraprese dai revisori. I log di audit sono un riepilogo di tutte le attività associate a un criterio aziendale definito o delle modifiche apportate ai criteri di conformità delle comunicazioni.

Per istruzioni dettagliate su come attivare o disattivare il controllo, vedere Attivare o [disattivare la ricerca nel log di controllo.](turn-audit-log-search-on-or-off.md) Dopo l'abilitazione, verrà visualizzato un messaggio che indica che è in corso la preparazione del log di controllo e che sarà possibile eseguire una ricerca in un paio d'ore, dopo il completamento della preparazione. Questa procedura deve essere eseguita una sola volta. Per ulteriori informazioni sull'utilizzo del log di controllo, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Passaggio 3 (facoltativo): configurare i gruppi per la conformità delle comunicazioni

 Quando si crea un criterio di conformità delle comunicazioni, si definisce chi ha esaminato le comunicazioni e chi esegue le revisioni. Nel criterio verranno utilizzati gli indirizzi di posta elettronica per identificare gli utenti o i gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per le persone che hanno esaminato le comunicazioni e gruppi per le persone che rivede le comunicazioni. Se si usano gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà supervisionato.

Utilizzare il grafico seguente per configurare i gruppi nell'organizzazione per i criteri di conformità delle comunicazioni:

| **Membro del criterio** | **Gruppi supportati** | **Gruppi non supportati** |
|:-----|:-----|:-----|
|Utenti con supervisione <br> Utenti esclusi | Gruppi di distribuzione <br> Gruppi di Microsoft 365 | Gruppi di distribuzione dinamici <br> Gruppi di distribuzione annidati <br> Gruppi di sicurezza abilitati alla posta elettronica <br> Microsoft 365 gruppi con appartenenza dinamica |
| Revisori | Nessuno | Gruppi di distribuzione <br> Gruppi di distribuzione dinamici <br> Gruppi di distribuzione annidati <br> Gruppi di sicurezza abilitati alla posta elettronica |
  
Quando si assegna un gruppo di distribuzione nel criterio, il criterio monitora tutti i messaggi di posta elettronica Teams chat di ogni utente nel gruppo di distribuzione. Quando si assegna un gruppo di Microsoft 365 nel criterio, il criterio monitora tutti i messaggi di posta elettronica e le chat di Teams inviate a tale gruppo, non i singoli messaggi di posta elettronica e chat ricevuti da ogni membro del gruppo.

Se si è un'organizzazione con una distribuzione locale di Exchange o un provider di posta elettronica esterno e si desidera monitorare le chat di Microsoft Teams per gli utenti, è necessario creare un gruppo di distribuzione per gli utenti con cassette postali locali o esterne da monitorare. Più avanti in questi passaggi, questo gruppo  di distribuzione verrà assegnato come selezione Di utenti e gruppi supervisionati nella procedura guidata dei criteri.

Per gestire gli utenti supervisionati nelle organizzazioni aziendali di grandi dimensioni, potrebbe essere necessario monitorare tutti gli utenti in gruppi di grandi dimensioni. È possibile utilizzare PowerShell per configurare un gruppo di distribuzione per un criterio di conformità delle comunicazioni globale per il gruppo assegnato. In questo modo è possibile monitorare migliaia di utenti con un singolo criterio e mantenere aggiornati i criteri di conformità delle comunicazioni quando i nuovi dipendenti aderiscono all'organizzazione.

1. Creare un [](/powershell/module/exchange/new-distributiongroup) gruppo di distribuzione dedicato per i criteri di conformità delle comunicazioni globali con le proprietà seguenti: Assicurarsi che questo gruppo di distribuzione non sia utilizzato per altri scopi o altri servizi Office 365.

    - **MemberDepartRestriction = Closed**. Garantisce che gli utenti non siano in grado di rimuoversi dal gruppo di distribuzione.
    - **MemberJoinRestriction = Closed**. Garantisce che gli utenti non possono aggiungersi al gruppo di distribuzione.
    - **ModerationEnabled = True.** Garantisce che tutti i messaggi inviati a questo gruppo siano soggetti all'approvazione e che il gruppo non venga utilizzato per comunicare al di fuori della configurazione dei criteri di conformità delle comunicazioni.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selezionare un attributo [personalizzato Exchange utilizzato per](/Exchange/recipients/mailbox-custom-attributes) tenere traccia degli utenti aggiunti ai criteri di conformità delle comunicazioni nell'organizzazione.

3. Eseguire lo script di PowerShell seguente in una pianificazione ricorrente per aggiungere utenti ai criteri di conformità delle comunicazioni:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Per ulteriori informazioni sulla configurazione dei gruppi, vedere:

- [Creazione e gestione dei gruppi di distribuzione](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Panoramica di Microsoft 365 gruppi](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Passaggio 4 (facoltativo): verificare che il tenant Yammer sia in modalità nativa

In modalità nativa, tutti Yammer utenti sono in Azure Active Directory (Azure AD), tutti i gruppi sono Office 365 Gruppi e tutti i file vengono archiviati in SharePoint Online. Il tenant Yammer deve essere in modalità nativa per i criteri di conformità delle comunicazioni per analizzare e identificare conversazioni rischiose in messaggi privati e conversazioni della community in Yammer.

Per altre informazioni sulla configurazione di Yammer in modalità nativa, vedi:

- [Panoramica della Yammer nativa in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurare la rete Yammer per la modalità nativa per Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Passaggio 5 (obbligatorio): creare un criterio di conformità delle comunicazioni
  
>[!Important]
>L'utilizzo di PowerShell per creare e gestire i criteri di conformità delle comunicazioni non è supportato. Per creare e gestire questi criteri, è necessario utilizzare i controlli di gestione dei criteri nella soluzione di conformità Microsoft 365 [comunicazione.](https://compliance.microsoft.com/supervisoryreview)

1. Accedere usando [https://compliance.microsoft.com](https://compliance.microsoft.com) le credenziali per un account amministratore nell'Microsoft 365 aziendale.

2. Nel Centro Microsoft 365 conformità selezionare **Conformità comunicazioni**.
  
3. Selezionare la scheda **Criteri**.

4. Selezionare **Crea criterio** per creare e configurare un nuovo criterio da un modello o per creare e configurare un criterio personalizzato.

    Se si sceglie un modello di criteri per creare un criterio, sarà necessario:

    - Confermare o aggiornare il nome del criterio. I nomi dei criteri non possono essere modificati dopo la creazione del criterio.

    - Scegliere gli utenti o i gruppi da supervisionare, inclusa la scelta di utenti o gruppi che si desidera escludere. Quando si utilizza il modello di conflitto di interesse, è necessario selezionare due gruppi o due utenti da monitorare per le comunicazioni interne.

    - Scegliere i revisori per il criterio. I revisori sono singoli utenti e tutti i revisori devono disporre di cassette postali ospitate Exchange Online. I revisori aggiunti qui sono i revisori tra cui è possibile scegliere quando si esegue l'escalation di un avviso nel flusso di lavoro di analisi e correzione. Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che li informa dell'assegnazione al criterio e fornisce collegamenti a informazioni sul processo di revisione.

    - Scegli un campo condizione limitato, in genere un tipo di informazioni riservate o un dizionario parole chiave da applicare al criterio.

    >[!NOTE]
    >Se si desidera abilitare il riconoscimento ottico dei caratteri [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) per analizzare le immagini incorporate o allegate nei messaggi per il testo stampato o scritto a mano che soddisfa le condizioni dei criteri, selezionare Personalizza condizioni e percentuale dei criteri e abilitare Estrai testo stampato o scritto a mano dalle immagini per la  >   valutazione. 

    Se si sceglie di utilizzare la procedura guidata dei criteri per creare un criterio personalizzato, sarà necessario:

    - Assegnare un nome e una descrizione al criterio. Non è possibile modificare i nomi dei criteri dopo la loro creazione.

    - Scegliere gli utenti o i gruppi da supervisionare, inclusi tutti gli utenti dell'organizzazione, utenti e gruppi specifici o altri utenti e gruppi che si desidera escludere.

    - Scegliere i revisori per il criterio. I revisori sono singoli utenti e tutti i revisori devono disporre di cassette postali ospitate Exchange Online. I revisori aggiunti qui sono i revisori tra cui è possibile scegliere quando si esegue l'escalation di un avviso nel flusso di lavoro di analisi e correzione. Quando i revisori vengono aggiunti a un criterio, ricevono automaticamente un messaggio di posta elettronica che li informa dell'assegnazione al criterio e fornisce collegamenti a informazioni sul processo di revisione.

    - Scegliere i canali di comunicazione da analizzare, inclusi Exchange, Microsoft Teams, Yammer o Skype for Business. Si può anche scegliere di analizzare le origini di terze parti se è stato configurato un connettore in Microsoft 365.

    - Scegliere la direzione di comunicazione da monitorare, incluse le comunicazioni in ingresso, in uscita o interne.

    - Definire le condizioni dei criteri di [conformità delle comunicazioni](communication-compliance-feature-reference.md#ConditionalSettings). È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.

    - Scegliere se si desidera includere tipi di informazioni riservate. Questo passaggio consente di selezionare i tipi di informazioni riservate predefiniti e personalizzati. Scegli tra tipi di informazioni riservate o dizionari parole chiave personalizzati esistenti nella procedura guidata dei criteri di conformità delle comunicazioni. È possibile creare questi elementi prima di eseguire la procedura guidata, se necessario. È inoltre possibile creare nuovi tipi di informazioni riservate dall'interno della procedura guidata dei criteri di conformità delle comunicazioni.

    - Scegli se vuoi abilitare i classificatori. I classificatori possono rilevare la lingua e le immagini inappropriati inviate o ricevute nel corpo dei messaggi di posta elettronica o di altri tipi di testo. È possibile scegliere i classificatori predefiniti seguenti: *Threat,* *Profanity,* *Targeted harassment,* *Adult images,* *Racy images* e *Gory images.*

    - Abilita il riconoscimento ottico dei caratteri [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) per analizzare le immagini incorporate o allegate nei messaggi per trovare testo stampato o scritto a mano che corrisponda alle condizioni dei criteri. Per i criteri personalizzati, una o più impostazioni condizionali associate a testo, parole chiave, classificatori o tipi di informazioni riservate devono essere configurate nel criterio per abilitare la selezione dell'analisi del riconoscimento ottico dei caratteri.

    - Definire la percentuale di comunicazioni da rivedere.

    - Esaminare le selezioni dei criteri e creare il criterio.

5. Selezionare **Crea criterio quando** si usano i modelli o **Invia** quando si usa la procedura guidata per i criteri personalizzati.

6. Viene visualizzata la pagina **Il criterio è stato creato** con una guida sulla data di attivazione del criterio e sulle comunicazioni che verranno acquisite.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Passaggio 6 (facoltativo): creare modelli di avviso e configurare l'anonimizzazione degli utenti

Se si desidera avere la possibilità di rispondere a un avviso dei criteri inviando un avviso di promemoria all'utente associato, è necessario creare almeno un modello di avviso nell'organizzazione. I campi del modello di avviso sono modificabili prima di essere inviati come parte del processo di correzione degli avvisi e si consiglia di creare un modello di avviso personalizzato per ogni criterio di conformità delle comunicazioni.

Puoi anche scegliere di abilitare l'anonimizzazione per i nomi utente visualizzati durante l'analisi delle corrispondenze dei criteri e l'azione sui messaggi.

1. Accedere usando [https://compliance.microsoft.com](https://compliance.microsoft.com) le credenziali per un account amministratore nell'Microsoft 365 aziendale.

2. Nel Centro Microsoft 365 conformità passare a **Conformità delle comunicazioni**.

3. Per configurare l'anonimizzazione per i nomi utente, selezionare la **scheda** Privacy.

4. Per abilitare l'anonimizzazione, selezionare **Mostra versioni anonime dei nomi utente.**

5. Selezionare **Salva**.

6. Passare alla scheda **Modelli di avviso** e quindi selezionare Crea modello di **avviso.**

7. Nella pagina **Modifica modello di avviso** completare i campi seguenti:

    - Nome modello (obbligatorio)
    - Invia da (obbligatorio)
    - Cc e Ccn (facoltativo)
    - Oggetto (obbligatorio)
    - Corpo del messaggio (obbligatorio)

8. Selezionare **Salva** per creare e salvare il modello di avviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Passaggio 7 (facoltativo): testare i criteri di conformità delle comunicazioni

Dopo aver creato un criterio di conformità delle comunicazioni, è buona idea testarlo per assicurarsi che le condizioni definite vengano applicate correttamente dal criterio. È inoltre possibile testare i criteri di prevenzione della perdita dei dati [(DLP)](create-test-tune-dlp-policy.md) se i criteri di conformità delle comunicazioni includono tipi di informazioni riservate. Assicurati di concedere ai criteri il tempo necessario per l'attivazione in modo che le comunicazioni che vuoi testare siano acquisite.

Seguire questi passaggi per testare i criteri di conformità delle comunicazioni:

1. Aprire un client di posta elettronica, Microsoft Teams o Yammer mentre è stato eseguito l'accesso come utente supervisionato definito nel criterio che si desidera testare.

2. Inviare un messaggio di Microsoft Teams, una chat o Yammer che soddisfi i criteri definiti nei criteri di conformità delle comunicazioni. Questo test può essere una parola chiave, dimensioni degli allegati, dominio e così via. Assicurati di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo restrittive.

    > [!NOTE]
    > L'elaborazione completa dei messaggi di posta elettronica in un criterio può richiedere fino a 24 ore. Le comunicazioni Microsoft Teams, Yammer e le piattaforme di terze parti possono richiedere fino a 48 ore per elaborare completamente i criteri.

3. Accedi a Microsoft 365 come revisore designato nei criteri di conformità delle comunicazioni. Passare a **Avvisi di conformità**  >  **delle** comunicazioni per visualizzare gli avvisi per i criteri.

4. Correggere l'avviso usando i controlli di correzione e verificare che l'avviso sia stato risolto correttamente.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato questi passaggi per creare il primo criterio di conformità delle comunicazioni, inizierai a ricevere avvisi dagli indicatori di attività dopo 24-48 ore. Configurare criteri aggiuntivi in base alle esigenze usando le indicazioni del passaggio 5 di questo articolo.

Per ulteriori informazioni sull'analisi degli avvisi di conformità delle comunicazioni, vedere [Investigate and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).
