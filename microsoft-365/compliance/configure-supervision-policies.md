---
title: Configurare criteri di supervisione per l'organizzazione
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
description: Impostare i criteri di revisione di supervisione per acquisire le comunicazioni dei dipendenti per la revisione.
ms.openlocfilehash: ccbc5897ef8c6fb6018793ff7e3fe7731ee14710
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083215"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurare criteri di supervisione per l'organizzazione

Utilizzare i criteri di supervisione per acquisire le comunicazioni dei dipendenti per l'esame da revisori interni o esterni. Per ulteriori informazioni su come i criteri di supervisione consentono di monitorare le comunicazioni nell'organizzazione, vedere [criteri di supervisione in Office 365](supervision-policies.md).

> [!NOTE]
> Gli utenti monitorati dai criteri di supervisione devono avere una licenza di conformità Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato o essere inclusi in un abbonamento a Office 365 Enterprise E5.
> Se non si dispone di un piano Enterprise E5 esistente e si vuole provare a eseguire la supervisione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Seguire questa procedura per configurare e usare la supervisione nell'organizzazione di Office 365:
  
- **Passaggio 1 (facoltativo)**: [configurare i gruppi per la supervisione](#step-1-set-up-groups-for-supervision-optional) 

    Prima di iniziare a utilizzare la supervisione, determinare gli utenti che devono esaminare le comunicazioni e che eseguono le recensioni. Se si desidera iniziare a usare solo alcuni utenti per vedere come funziona la supervisione, è possibile ignorare la configurazione dei gruppi per il momento.

- **Passaggio 2 (obbligatorio)**: [rendere disponibile la supervisione nell'organizzazione](#step-2-make-supervision-available-in-your-organization-required)

    Aggiungersi al gruppo di ruolo revisione di supervisione per impostare i criteri. Tutti gli utenti a cui è assegnato questo ruolo possono accedere alla pagina di **supervisione** nel centro conformità. Se il messaggio di posta elettronica rivisualizzabile è ospitato in Exchange Online, ogni revisore deve disporre dell' [accesso remoto a PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Passaggio 3 (facoltativo)**: [creare tipi di informazioni riservate personalizzate e dizionari per parole chiave personalizzate](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Se è necessario un tipo di informazioni riservate personalizzato o un dizionario di parole chiave personalizzato per i criteri di supervisione, è necessario crearlo prima di avviare la procedura guidata di supervisione.

- **Passaggio 4 (obbligatorio)**: [impostare un criterio di supervisione](#step-4-set-up-a-supervision-policy-required)

    È possibile creare criteri di supervisione nel centro conformità. Questi criteri definiscono le comunicazioni soggette a revisione nell'organizzazione e specifica chi esegue le revisioni. Le comunicazioni includono la posta elettronica e le comunicazioni di Microsoft teams e le comunicazioni della piattaforma di terze parti (come Facebook, Twitter e così via).

- **Passaggio 5 (facoltativo)**: [testare i criteri di supervisione](#step-5-test-your-supervision-policy-optional)

    Testare i criteri di supervisione per assicurarsi che funzioni come desiderato. È importante garantire che la strategia di conformità soddisfi gli standard.

- **Passaggio 6 (facoltativo)**: [configurare Outlook per i revisori che non desiderano utilizzare il dashboard di supervisione di Office 365 per esaminare le comunicazioni sorvegliate](#step-6-configure-outlook-for-reviewers-optional)

    Configurare Outlook per consentire agli utenti di accedere alla funzionalità di supervisione all'interno del client Outlook in modo che possano valutare e categorizzare ogni elemento.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Passaggio 1: configurare i gruppi per la supervisione (facoltativo)

 Quando si crea un criterio di supervisione, si definisce chi ha le proprie comunicazioni recensite e chi esegue le revisioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica per identificare singoli o gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per gli utenti che hanno la propria comunicazione riesaminata e i gruppi per gli utenti che esaminano tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà controllato.

Utilizzare il seguente grafico per facilitare la configurazione dei gruppi nell'organizzazione per i criteri di supervisione:

| **Membro del criterio** | **Gruppi supportati** | **Gruppi non supportati** |
|:-----|:-----|:-----|
|Utenti controllati <br> Utenti non controllati | Gruppi di distribuzione <br> Gruppi di Office 365 | Gruppi di distribuzione dinamici |
| Revisori | Gruppi di sicurezza abilitati alla posta elettronica  | Gruppi di distribuzione <br> Gruppi di distribuzione dinamici |
  
Quando si seleziona un gruppo di Office 365 per gli utenti controllati, il criterio monitora il contenuto della cassetta postale di Office 365 condivisa e dei canali Microsoft teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le singole cassette postali degli utenti.

Per gestire gli utenti controllati nelle organizzazioni aziendali di grandi dimensioni, potrebbe essere necessario monitorare tutti gli utenti in gruppi di grandi dimensioni. È possibile utilizzare PowerShell per configurare un gruppo di distribuzione per un criterio di supervisione globale per il gruppo assegnato. In questo modo è possibile monitorare migliaia di utenti con un singolo criterio e mantenere il criterio di supervisione aggiornato man mano che i nuovi dipendenti fanno parte dell'organizzazione.

1. Creare un [gruppo di distribuzione](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) dedicato per il criterio di supervisione globale con le proprietà seguenti: assicurarsi che questo gruppo di distribuzione non venga utilizzato per altri scopi o per altri servizi di Office 365.

    - **MemberDepartRestriction = chiuso**. Assicura che gli utenti non possano rimuoversi dal gruppo di distribuzione.
    - **MemberJoinRestriction = chiuso**. Assicura che gli utenti non possano aggiungersi al gruppo di distribuzione.
    - **ModerationEnabled = true**. Garantisce che tutti i messaggi inviati a questo gruppo siano soggetti all'approvazione e che il gruppo non venga utilizzato per comunicare al di fuori della configurazione dei criteri di supervisione.

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. Selezionare un [attributo personalizzato di Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) inutilizzato per registrare gli utenti aggiunti al criterio di supervisione nell'organizzazione.

3. Eseguire il seguente script di PowerShell su una pianificazione ricorrente per aggiungere gli utenti ai criteri di supervisione:

    ```
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

- [Creazione e gestione dei gruppi di distribuzione](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gestire i gruppi di protezione abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Panoramica dei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Passaggio 2: rendere disponibile la supervisione nell'organizzazione (obbligatorio)

Per rendere disponibile la **supervisione** come opzione di menu nel centro conformità, è necessario essere assegnati al ruolo amministratore revisione di supervisione.
  
A tale scopo, è possibile aggiungere se stessi come membro del gruppo di ruolo revisione di supervisione oppure creare un gruppo di ruoli.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Aggiungere membri al gruppo di ruoli revisione di supervisione

1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro conformità, accedere a **autorizzazioni**.

3. Selezionare il gruppo di ruoli **revisione di supervisione** e quindi fare clic sull'icona modifica.

4. Nella sezione **membri** aggiungere gli utenti che si desidera gestire la supervisione per l'organizzazione.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro conformità, accedere a **autorizzazioni** e quindi fare clic su Aggiungi**+**().

3. Nella sezione **ruoli** fare clic su Aggiungi (**+**) e scorrere verso il basso fino a **amministratore revisione di supervisione**. Aggiungere questo ruolo al gruppo di ruoli.

4. Nella sezione **membri** aggiungere gli utenti che si desidera gestire la supervisione per l'organizzazione.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Abilitare l'accesso remoto a PowerShell per i revisori (se la posta elettronica è ospitata su Exchange Online)

1. Seguire le istruzioni riportate in [abilitare o disabilitare l'accesso a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Passaggio 3: creare tipi di informazioni riservate personalizzate e dizionari di parole chiave personalizzati (facoltativo)

Per scegliere tra tipi di informazioni riservate personalizzate esistenti o dizionari di parole chiave personalizzati nella procedura guidata dei criteri di supervisione, è necessario prima di tutto creare questi elementi, se necessario.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Creare dizionario di parole chiave personalizzato/lessico (facoltativo)

Utilizzare un editor di testo, ad esempio il blocco note, per creare un file che includa i termini di parola chiave che si desidera monitorare in un criterio di supervisione. Assicurarsi che ogni termine sia su una riga distinta e salvare il file nel formato **Unicode/UTF-16 (Little endian)** .

### <a name="create-custom-sensitive-information-types"></a>Creare tipi di informazioni riservate personalizzate

1. Creare un nuovo tipo di informazioni riservate e aggiungere il dizionario personalizzato nel centro sicurezza & conformità di Office 365. Passare a **classificazione** \> **tipi di informazioni riservate** e seguire i passaggi descritti nella **procedura guidata nuovo tipo di informazioni riservate**. Di seguito viene indicato:

    - Definire un nome e una descrizione per il tipo di informazioni riservate
    - Definire gli elementi di prossimità, livello di confidenza e motivo primario
    - Importare il dizionario personalizzato come requisito per l'elemento corrispondente
    - Esaminare le selezioni e creare il tipo di informazioni riservate

    Per informazioni più dettagliate, vedere [creare un tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md) e [creare un dizionario di parole chiave](create-a-keyword-dictionary.md)

    Dopo la creazione del dizionario/lessico personalizzato, è possibile visualizzare le parole chiave configurate con il cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) oppure aggiungere e rimuovere termini utilizzando il cmdlet [set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) .

## <a name="step-4-set-up-a-supervision-policy-required"></a>Passaggio 4: configurare un criterio di supervisione (obbligatorio)
  
1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro conformità, selezionare **supervisione**.
  
3. Selezionare **Crea** e seguire la procedura guidata per configurare la configurazione dei criteri. Se si utilizza la procedura guidata, sarà necessario:

    - Assegnare al criterio un nome e una descrizione.
    - Scegliere gli utenti o i gruppi da controllare, inclusa la scelta degli utenti o dei gruppi che si desidera escludere.
    - Definire le [condizioni](supervision-policies.md#ConditionalSettings)dei criteri di supervisione. È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.
    - Scegliere se si desidera includere tipi di informazioni riservate. È possibile selezionare i tipi di informazioni riservate predefinite e personalizzate.
    - Scegliere se si desidera abilitare il modello di lingua offensivo. In questo modo viene rilevato il linguaggio inappropriato inviato o ricevuto nel corpo dei messaggi di posta elettronica.
    - Definire la percentuale di comunicazioni da esaminare.
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o [gruppi di sicurezza abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.
    - Esaminare le selezioni dei criteri e creare il criterio.

## <a name="step-5-test-your-supervision-policy-optional"></a>Passaggio 5: testare i criteri di supervisione (facoltativo)

Dopo aver creato un criterio di supervisione, è consigliabile verificare che le condizioni definite vengano applicate in modo corretto dal criterio. È inoltre possibile [testare i criteri di prevenzione della perdita di dati (DLP)](create-test-tune-dlp-policy.md) se i criteri di supervisione includono tipi di informazioni riservate. Eseguire la procedura seguente per verificare i criteri di supervisione:

1. Aprire un client di posta elettronica o Microsoft teams connesso come utente controllato definito nel criterio che si desidera sottoporre a test.
2. Inviare un messaggio di posta elettronica o Microsoft teams chat che soddisfi i criteri definiti nei criteri di supervisione. Può trattarsi di una parola chiave, dimensioni degli allegati, dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo indulgenti.

    > [!Note]
    > I messaggi di posta elettronica soggetti a criteri definiti vengono elaborati in tempo quasi reale e possono essere testati immediatamente dopo la configurazione del criterio. Le chat in Microsoft teams possono richiedere fino a 24 ore per il processo completo in un criterio. 

3. Accedere al tenant di Office 365 come un revisore designato nei criteri di supervisione. Passare alla **supervisione** > del*criterio* > personalizzato**aperto** per visualizzare il report per il criterio.

## <a name="step-6-configure-outlook-for-reviewers-optional"></a>Passaggio 6: configurare Outlook per i revisori (facoltativo)

I revisori che desiderano utilizzare Outlook invece del dashboard di supervisione in Office 365 per esaminare le comunicazioni devono configurare il client di Outlook.

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Passaggio 1: copiare l'indirizzo della cassetta postale di supervisione

Per configurare la revisione per Outlook desktop, è necessario l'indirizzo della cassetta postale di supervisione creata come parte del programma di installazione dei criteri di supervisione.
  
> [!NOTE]
> Se un altro utente ha creato il criterio, è necessario ottenere questo indirizzo da loro per installare il componente aggiuntivo.

**Per trovare l'indirizzo della cassetta postale di supervisione**
  
1. Accedere al [centro conformità](https://compliance.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.

2. Andare a **supervisione**.

3. Selezionare un criterio di supervisione per le comunicazioni che si desidera esaminare.

4. Nel riquadro a comparsa dei dettagli del criterio, in **cassetta postale di supervisione**, copiare l'indirizzo.<br/>![La sezione "cassetta postale di supervisione" del riquadro a comparsa dei dettagli del criterio di supervisione che mostra l'indirizzo della cassetta postale](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a>Passaggio 2: configurare la cassetta postale di supervisione per l'accesso di Outlook

Successivamente, i revisori devono eseguire un paio di comandi di PowerShell di Exchange online in modo che possano connettere Outlook alla cassetta postale di supervisione.
  
1. Connettersi a PowerShell per Exchange Online. [Come eseguire l'operazione](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. Eseguire i comandi seguenti, dove *SupervisoryReview {GUID} @domain. onmicrosoft.com* è l'indirizzo copiato nel passaggio 1 sopra e *User* è il nome del revisore che si collegherà alla cassetta postale di supervisione nel passaggio 3.

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. Attendere almeno un'ora prima di passare al passaggio 3.

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Passaggio 3: creare un profilo di Outlook per la connessione alla cassetta postale di supervisione

Per il passaggio finale, i revisori devono creare un profilo di Outlook per la connessione alla cassetta postale di supervisione.

> [!NOTE]
> Per creare un nuovo profilo di Outlook, è possibile utilizzare le impostazioni di posta elettronica nel pannello di controllo di Windows. Il percorso da eseguire per accedere a queste impostazioni può dipendere dal sistema operativo Windows (Windows 7, Windows 8 o Windows 10) in uso e dalla versione di Outlook installata.
  
1. Aprire il pannello di controllo. Nella casella di **ricerca** nella parte superiore della finestra digitare **mail**.<br/>(Non si è sicuri di come accedere al pannello di controllo? Vedere [dove si trova il pannello di controllo?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. Aprire l'app di **posta elettronica** .

3. In **configurazione posta elettronica-Outlook**, fare clic su **Mostra profili**.<br/>![La finestra di dialogo "configurazione della posta elettronica-Outlook" con il pulsante ' Mostra profili ' evidenziata](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. In **posta**, fare clic su **Aggiungi**. Quindi, in **nuovo profilo**, immettere un nome per la cassetta postale di supervisione, ad esempio la **supervisione**.<br/>![La finestra di dialogo ' nuovo profilo ' che mostra il nome ' supervisione ' nella casella ' nome profilo '](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. In **Connetti Outlook a Office 365**fare clic su **Connetti a un account diverso**.<br/>![Il messaggio ' Connect Outlook to Office 365' con il collegamento ' Connetti a un account diverso ' evidenziato](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. In **Configurazione account automatico**, scegliere **installazione manuale o tipi di server aggiuntivi**, quindi fare clic su **Avanti**.

7. In **Scegli il tipo di account**, scegli **Office 365**. Nella casella indirizzo di **posta elettronica** immettere quindi l'indirizzo della cassetta postale di supervisione copiata in precedenza.<br/>![La pagina ' Scegli il tipo di account ' della finestra di dialogo ' Aggiungi account ' in Outlook che mostra la casella ' indirizzo di posta elettronica ' evidenziata.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Quando richiesto, immettere le credenziali di Office 365.

9. Se l'operazione ha esito positivo, la cartella **nome \<\> criterio** è elencata nella visualizzazione elenco cartelle in Outlook.

## <a name="powershell-reference"></a>Informazioni di riferimento su PowerShell

Se necessario, è possibile creare e gestire i criteri di supervisione con i cmdlet di PowerShell seguenti:

- [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
