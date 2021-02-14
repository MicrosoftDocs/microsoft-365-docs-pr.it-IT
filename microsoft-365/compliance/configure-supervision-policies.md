---
title: Configurare i criteri di supervisione
description: Configurare i criteri di supervisione delle comunicazioni in Office 365 per acquisire le comunicazioni dei dipendenti per l'esame da parte di revisori interni o esterni.
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
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74244b5288043a1d1bc62e0ae09ee8c25ff7d4e1
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546778"
---
# <a name="configure-supervision-policies-in-office-365"></a>Configurare i criteri di supervisione in Office 365

>[!IMPORTANT]
>Dopo il rilascio della conformità delle comunicazioni in Conformità Microsoft 365 a febbraio 2020, la supervisione in Office 365 viene ritirata. I criteri di supervisione non saranno più disponibili per la creazione e i criteri verranno rimossi dopo un lungo periodo di accesso in sola lettura.
>
>Se si utilizza supervisione, tenere presente che:
>
>- A partire dal 15 giugno 2020, i tenant non potranno creare nuovi criteri di supervisione.
>- A partire dal 31 agosto 2020, i criteri esistenti interromperanno l'acquisizione dei nuovi messaggi.
>- A partire dal 26 ottobre 2020, i criteri esistenti verranno eliminati.
>
>We actively encourage customers who are currently exploring or using Supervision in Office 365 to use the new [communication compliance](communication-compliance.md) solution to address your communications monitoring or regulatory requirements with a much richer set of intelligent capabilities.

Usare i criteri di supervisione per acquisire le comunicazioni dei dipendenti per l'esame da parte di revisori interni o esterni. Per ulteriori informazioni su come i criteri di supervisione consentono di monitorare le comunicazioni nell'organizzazione, vedere [Criteri di supervisione in Office 365.](supervision-policies.md)

>[!NOTE]
>Gli utenti monitorati dai criteri di supervisione devono disporre di una licenza Di conformità di Microsoft 365 E5, una licenza di Office 365 Enterprise E3 con il componente aggiuntivo Conformità avanzata o essere inclusi in un abbonamento a Office 365 Enterprise E5 o essere inclusi in un abbonamento a Microsoft 365 E5.
>Se non si dispone di un piano Enterprise E5 esistente e si vuole provare la supervisione, è possibile iscriversi per una versione di valutazione di [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)
  
Seguire questa procedura per configurare e usare la supervisione nell'organizzazione:
  
- **Passaggio 1 (facoltativo):** [Configurare i gruppi per la supervisione](#step-1-set-up-groups-for-supervision-optional)

    Prima di iniziare a usare i criteri di supervisione, determinare chi deve essere esaminato e chi esegue le revisioni. Se vuoi iniziare a usare solo alcuni utenti per vedere come funziona la supervisione, puoi ignorare la configurazione dei gruppi per il momento.

- **Passaggio 2 (obbligatorio):** [rendere disponibile la supervisione nell'organizzazione](#step-2-make-supervision-available-in-your-organization-required)

    Aggiungere se stessi al gruppo di ruoli Revisione di supervisione in modo da poter configurare i criteri. Tutti gli utenti a cui è assegnato questo ruolo possono accedere alla **pagina Supervisione** nel Centro sicurezza & conformità. Se la posta elettronica verificabile è ospitata su Exchange Online, ogni revisore deve disporre dell'accesso [remoto di PowerShell a Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- **Passaggio 3 (facoltativo):** [Creare tipi di informazioni sensibili personalizzati e dizionari](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional) di parole chiave personalizzati

    Se hai bisogno di un tipo di informazioni sensibili personalizzato o di un dizionario di parole chiave personalizzato per i criteri di supervisione, devi crearlo prima di avviare la procedura guidata di supervisione.

- **Passaggio 4 (obbligatorio):** [configurare un criterio di supervisione](#step-4-set-up-a-supervision-policy-required)

    I criteri di supervisione vengono creati nel Centro sicurezza & conformità. Questi criteri definiscono quali comunicazioni sono soggette a revisione nell'organizzazione e specificano chi esegue le revisioni. Le comunicazioni includono la posta elettronica e le comunicazioni di Microsoft Teams e le comunicazioni della piattaforma di terze parti (ad esempio Facebook, Twitter e così via). I criteri di supervisione creati nelle organizzazioni non sono supportati nella supervisione delle comunicazioni negli abbonamenti a Microsoft 365.

- **Passaggio 5 (facoltativo):** [testare i criteri di supervisione delle comunicazioni](#step-5-test-your-supervision-policy-optional)

    Testare i criteri di supervisione per verificare che funzionino come desiderato. È importante assicurarsi che la strategia di conformità sia conforme agli standard.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Passaggio 1: Configurare i gruppi per la supervisione (facoltativo)

 Quando si crea un criterio di supervisione, si definisce chi esegue l'analisi delle comunicazioni e chi esegue le revisioni. Nel criterio, si useranno gli indirizzi di posta elettronica per identificare singoli utenti o gruppi di persone. Per semplificare la configurazione, è possibile creare gruppi per le persone che analizzano le comunicazioni e gruppi per gli utenti che esaminano tali comunicazioni. Se si usano gruppi, potrebbero essere necessari diversi gruppi. Ad esempio, si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà supervisionato.

Utilizzare il grafico seguente per configurare i gruppi nell'organizzazione per i criteri di supervisione delle comunicazioni:

| **Membro del criterio** | **Gruppi supportati** | **Gruppi non supportati** |
|:-----|:-----|:-----|
|Utenti supervisionati <br> Utenti non supervisionati | Gruppi di distribuzione <br> Gruppi di Microsoft 365 | Gruppi di distribuzione dinamici |
| Revisori | Gruppi di sicurezza abilitati alla posta elettronica  | Gruppi di distribuzione <br> Gruppi di distribuzione dinamici |
  
Quando si seleziona un gruppo di Microsoft 365 per gli utenti supervisionati, il criterio monitora il contenuto della cassetta postale condivisa e i canali di Microsoft Teams associati al gruppo. Quando si seleziona una lista di distribuzione, il criterio monitora le cassette postali dei singoli utenti.

Per gestire gli utenti supervisionati nelle organizzazioni aziendali di grandi dimensioni, potrebbe essere necessario monitorare tutti gli utenti in gruppi di grandi dimensioni. È possibile utilizzare PowerShell per configurare un gruppo di distribuzione per un criterio di supervisione globale per il gruppo assegnato. In questo modo è possibile monitorare migliaia di utenti con un singolo criterio e mantenere aggiornati i criteri di supervisione quando i nuovi dipendenti aderiscono all'organizzazione.

1. Creare un [](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) gruppo di distribuzione dedicato per i criteri di supervisione globali con le proprietà seguenti: Assicurarsi che questo gruppo di distribuzione non sia utilizzato per altri scopi o altri servizi di Office 365.

    - **MemberDepartRestriction = Closed.** Garantisce che gli utenti non siano in grado di rimuoversi dal gruppo di distribuzione.
    - **MemberJoinRestriction = Closed**. Garantisce che gli utenti non possono aggiungersi al gruppo di distribuzione.
    - **ModerationEnabled = True.** Garantisce che tutti i messaggi inviati a questo gruppo siano soggetti all'approvazione e che il gruppo non venga utilizzato per comunicare al di fuori della configurazione dei criteri di supervisione.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selezionare un attributo personalizzato di [Exchange inutilizzato](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) per tenere traccia degli utenti aggiunti ai criteri di supervisione nell'organizzazione.

3. Eseguire il seguente script di PowerShell in base a una pianificazione ricorrente per aggiungere utenti ai criteri di supervisione:

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

- [Creazione e gestione dei gruppi di distribuzione](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gestire i gruppi di protezione abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Panoramica dei gruppi di Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Passaggio 2: rendere disponibile la supervisione nell'organizzazione (obbligatorio)

Per rendere **disponibile la** supervisione come opzione di menu nel Centro sicurezza & conformità, è necessario disporre del ruolo Di amministratore revisione di supervisione.
  
A tale scopo, è possibile aggiungersi come membro del gruppo di ruoli Revisione di supervisione oppure creare un gruppo di ruoli.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Aggiungere membri al gruppo di ruoli Revisione di supervisione

1. Accedere con [https://protection.office.com](https://protection.office.com) le credenziali di un account amministratore nell'organizzazione.

2. Nel Centro sicurezza & conformità passare a **Autorizzazioni.**

3. Selezionare il **gruppo di ruoli Revisione** di supervisione e quindi fare clic sull'icona Modifica.

4. Nella sezione **Membri** aggiungere le persone a cui si desidera gestire la supervisione delle comunicazioni per l'organizzazione.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere con [https://protection.office.com/permissions](https://protection.office.com/permissions) le credenziali di un account amministratore nell'organizzazione.

2. Nel Centro sicurezza & conformità passare a **Autorizzazioni** e quindi fare clic su Aggiungi ( **+** ).

3. Nella sezione **Ruoli** fare clic su Aggiungi ( ) e scorrere verso il basso fino **+** a **Supervisory Review Administrator.** Aggiungere questo ruolo al gruppo di ruoli.

4. Nella sezione **Membri** aggiungere le persone a cui si desidera gestire la supervisione delle comunicazioni per l'organizzazione.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Autorizzazioni nel Centro conformità.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Abilitare l'accesso remoto a PowerShell per i revisori (se la posta elettronica è ospitata in Exchange Online)

1. Seguire le istruzioni in [Abilitare o disabilitare l'accesso a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Passaggio 3: Creare tipi di informazioni sensibili personalizzati e dizionari di parole chiave personalizzati (facoltativo)

Per scegliere tra tipi di informazioni sensibili o dizionari di parole chiave personalizzati esistenti nella procedura guidata dei criteri di supervisione, devi prima creare questi elementi, se necessario.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Creare dizionario di parole chiave/lessico personalizzato (facoltativo)

Utilizzare un editor di testo (ad esempio Blocco note) per creare un file che includa i termini delle parole chiave che si desidera monitorare in un criterio di supervisione. Assicurati che ogni termine si trova su una riga separata e salva il file nel formato **Unicode/UTF-16 (Little Endian).**

### <a name="create-custom-sensitive-information-types"></a>Creare tipi di informazioni sensibili personalizzati

1. Creare un nuovo tipo di informazioni riservate e aggiungere il dizionario personalizzato nel Centro sicurezza & conformità. Passare a **Classificazioni tipi** di informazioni sensibili e seguire i passaggi della procedura guidata Nuovo tipo \>  di **informazioni sensibili.** Di seguito è possibile:

    - Definire un nome e una descrizione per il tipo di informazioni sensibili
    - Definire gli elementi di prossimità, livello di confidenza ed elementi del modello principale
    - Importare il dizionario personalizzato come requisito per l'elemento corrispondente
    - Rivedere le selezioni e creare il tipo di informazioni sensibili

    Per informazioni più dettagliate, vedere [Creare un tipo](create-a-custom-sensitive-information-type.md) di informazioni sensibili personalizzato e Creare un dizionario di parole [chiave](create-a-keyword-dictionary.md)

    Dopo aver creato il dizionario/lessico personalizzato, è possibile visualizzare le parole chiave configurate con il cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) o aggiungere e rimuovere termini utilizzando il cmdlet [Set-DlpKeywordDictionary.](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary)

## <a name="step-4-set-up-a-supervision-policy-required"></a>Passaggio 4: Configurare un criterio di supervisione (obbligatorio)
  
1. Accedere con [https://protection.office.com](https://protection.office.com) le credenziali di un account amministratore nell'organizzazione.

2. Nel Centro sicurezza & conformità selezionare **Supervisione.**
  
3. Selezionare **Crea** e seguire la procedura guidata per configurare la configurazione dei criteri. Utilizzando la procedura guidata, è possibile:

    - Assegnare un nome e una descrizione al criterio.
    - Scegliere gli utenti o i gruppi da supervisionare, inclusa la scelta di utenti o gruppi che si desidera escludere.
    - Definire le condizioni dei criteri [di supervisione.](supervision-policies.md#ConditionalSettings) È possibile scegliere tra l'indirizzo del messaggio, la parola chiave, i tipi di file e le condizioni di corrispondenza delle dimensioni.
    - Scegliere se si desidera includere i tipi di informazioni riservate. Qui è possibile selezionare i tipi di informazioni sensibili predefiniti e personalizzati.
    - Scegli se vuoi abilitare il modello di linguaggio offensivo. In questo modo viene rilevata una lingua inappropriata inviata o ricevuta nel corpo dei messaggi di posta elettronica.
    - Definire la percentuale di comunicazioni da rivedere.
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o gruppi [di sicurezza abilitati alla posta elettronica.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group) Tutti i revisori devono disporre di cassette postali ospitate in Exchange Online.
    - Esaminare le selezioni dei criteri e creare il criterio.

## <a name="step-5-test-your-supervision-policy-optional"></a>Passaggio 5: testare i criteri di supervisione (facoltativo)

Dopo aver creato un criterio di supervisione della comunicazione, è buona idea testare che le condizioni definite vengano applicate correttamente dal criterio. È inoltre possibile testare i criteri di prevenzione della perdita dei dati [(DLP)](create-test-tune-dlp-policy.md) se i criteri di supervisione includono tipi di informazioni riservate. Seguire questa procedura per testare i criteri di supervisione:

1. Aprire un client di posta elettronica o Microsoft Teams connesso come utente supervisionato definito nel criterio che si desidera testare.
2. Inviare un messaggio di posta elettronica o una chat di Microsoft Teams che soddisfi i criteri definiti nei criteri di supervisione. Può trattarsi di una parola chiave, dimensioni degli allegati, dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo lente.

    >[!NOTE]
    >I messaggi di posta elettronica soggetti a criteri definiti vengono elaborati quasi in tempo reale e possono essere testati subito dopo la configurazione del criterio. Le chat in Microsoft Teams possono richiedere fino a 24 ore per elaborare completamente i criteri. 

3. Accedere a Microsoft 365 come revisore designato nei criteri di supervisione delle comunicazioni. Passare a  >  *Supervisione l'apertura dei*  >   criteri personalizzati per visualizzare il report per il criterio.

