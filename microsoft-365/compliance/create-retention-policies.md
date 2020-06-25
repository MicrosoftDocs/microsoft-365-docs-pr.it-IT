---
title: Creare e configurare criteri di conservazione per conservare o eliminare automaticamente il contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usare i criteri di conservazione per decidere in modo proattivo se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente, se applicare un singolo criterio all'intera organizzazione o a posizioni o utenti specifici e se applicare un criterio a tutti i contenuti o al contenuto che soddisfa determinate condizioni.
ms.openlocfilehash: 12b0c15186a27a1583403214a657367c1dd3b1a9
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844752"
---
# <a name="create-and-configure-retention-policies"></a>Creare e configurare criteri di conservazione

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Usare un criterio di conservazione per decidere proattivamente se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente. 

Per informazioni sul funzionamento dei criteri di conservazione, vedere [Informazioni sui criteri di conservazione](retention-policies.md).

## <a name="before-you-begin"></a>Prima di iniziare

Ai membri del team di conformità che creeranno e gestiranno i criteri di conservazione è necessario assegnare autorizzazioni per il [Centro conformità Microsoft 365](https://compliance.microsoft.com/). Per impostazione predefinita, l'amministratore del tenant (amministratore globale) ha accesso a questa posizione e può fornire l'accesso ai responsabili della conformità e ad altre persone senza concedere loro tutte le autorizzazioni di un amministratore del tenant. Per concedere le autorizzazioni per questa amministrazione limitata, è consigliabile aggiungere gli utenti al gruppo di ruoli di amministratore **Amministratore di conformità**. Per le istruzioni, vedere [Fornire agli utenti l'accesso al Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Queste autorizzazioni sono necessarie solo per creare e applicare criteri di conservazione. La persona che configura i criteri di conservazione non ha bisogno di accedere al contenuto.

## <a name="create-and-configure-a-retention-policy"></a>Creare e configurare un criterio di conservazione

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) selezionare **Criteri** > **Conservazione**.

2. Selezionare **Nuovo criterio di conservazione** o modificare un criterio esistente.

3. Per **Impostazioni** specificare prima di tutto le opzioni di configurazione per la conservazione e l'eliminazione del contenuto. È possibile creare un criterio che si limita a conservare il contenuto senza eliminarlo, lo conserva e quindi lo elimina dopo un periodo di tempo specificato oppure semplicemente elimina il contenuto dopo un periodo di tempo specificato. Per altre informazioni, vedere [Impostazioni per la conservazione e l'eliminazione del contenuto](#settings-for-retaining-and-deleting-content) in questa pagina:
    
    Quindi, decidere se il criterio di conservazione va applicato a tutto il contenuto o al contenuto che soddisfa determinate condizioni. Per altre informazioni su queste impostazioni avanzate di conservazione, vedere [Impostazioni avanzate per identificare il contenuto che soddisfa condizioni specifiche](#advanced-settings-to-identify-content-that-meets-specific-conditions) in questa pagina. 

4. Per la pagina **Seleziona posizioni**, selezionare se il criterio di conservazione va applicato a tutte le posizioni supportate nell'organizzazione o se si vogliono specificare. Se si scelgono posizioni specifiche, è anche possibile specificare cosa includere o escludere. 
    
    Per Microsoft Teams: 
    - È necessario selezionare l'opzione per scegliere posizioni specifiche se si vogliono eliminare o conservare i messaggi dei canali di Teams o le chat di Teams. Selezionando una di queste opzioni, le altre posizioni vengono escluse automaticamente perché un criterio di conservazione che include questi dati di Teams non può includere altre posizioni. 
    - Si noti che per **Messaggi del canale di Teams** sono inclusi i messaggi provenienti da canali standard ma non dai [canali privati](https://docs.microsoft.com/microsoftteams/private-channels). I messaggi dei canali privati vengono inclusi per gli utenti come chat di gruppo selezionando la posizione **Chat di Teams**.
    
    Per altre informazioni sulla scelta tra criteri di conservazione per l'organizzazione o per posizioni specifiche, vedere [Applicazione di criteri di conservazione a un'intera organizzazione o a posizioni specifiche](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) in questa pagina.
    
    Per informazioni specifiche su **gruppi di Office 365** e **Skype for Business**, vedere le successive sezioni [Informazioni di configurazione per i gruppi di Microsoft 365](#configuration-information-for-microsoft-365-groups) e [Informazioni di configurazione per Skype for Business](#configuration-information-for-skype-for-business).

5. Completare la procedura guidata per salvare le impostazioni.

Se sono presenti più criteri di conservazione, vedere [Principi di conservazione: cosa ha la precedenza?](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)

### <a name="configuration-information-for-microsoft-365-groups"></a>Informazioni di configurazione per i gruppi di Microsoft 365

Per conservare o eliminare il contenuto di un gruppo di Microsoft 365 (in precedenza gruppo di Office 365), selezionare **Gruppi di Office 365** quando si scelgono le posizioni per il criterio di conservazione. Anche se un gruppo di Microsoft 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso **Posta elettronica di Exchange** non includerà il contenuto nelle cassette postali del gruppo di Microsoft 365. Inoltre, anche se il percorso **Posta elettronica di Exchange** consente inizialmente di selezionare una cassetta postale del gruppo da includere o escludere, provando a salvare il criterio di conservazione si riceverà un messaggio di errore che segnala che "RemoteGroupMailbox" non è una selezione valida per il percorso di Exchange.

I criteri di conservazione applicati a un gruppo di Microsoft 365 includono sia la cassetta postale del gruppo che il sito. Un criterio di conservazione applicato a un gruppo di Microsoft 365 protegge le risorse create da un gruppo di Microsoft 365, che include Microsoft Teams.

### <a name="configuration-information-for-skype-for-business"></a>Informazioni di configurazione per Skype for Business

A differenza della posta elettronica di Exchange, non è possibile attivare lo stato della posizione Skype per includere tutti gli utenti ma quando si attiva la posizione, sarà possibile scegliere manualmente gli utenti di cui si desidera conservare le conversazioni:

![Scegliere il percorso Skype per i criteri di conservazione](../media/skype-location-retention-policies.png)
  
Quando si seleziona **Scegli utenti **, è possibile includere rapidamente tutti gli utenti selezionando la casella **Nome ** nell'intestazione di colonna. È necessario considerare, però, che ciascun utente viene conteggiato come specifica inclusione nei criteri. Di conseguenza, se si includono più di 1.000 utenti, si applicano i limiti indicati nella sezione precedente. La selezione di tutti gli utenti di Skype da questa posizione non coincide con la procedura che prevede l'inclusione predefinita di tutti gli utenti di Skype con i criteri a livello di organizzazione. 
  
![Pagina di scelta utenti Skype](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.


## <a name="settings-for-retaining-and-deleting-content"></a>Impostazioni per la conservazione e l'eliminazione del contenuto

Scegliendo le impostazioni per la conservazione e l'eliminazione del contenuto, il criterio di conservazione avrà una delle configurazioni seguenti per un periodo di tempo specificato:

- Conserva solo
- Conserva ed elimina
- Elimina solo

### <a name="retaining-content-for-a-specific-period-of-time"></a>Conservazione del contenuto per un periodo di tempo specifico

Quando si configura un criterio di conservazione, si sceglie di conservare il contenuto per un periodo di tempo indefinito o per un numero specifico di giorni, mesi o anni. Il calcolo relativo al periodo di conservazione del contenuto è basato sulla data di modifica del contenuto e non sulla data di applicazione dei criteri di conservazione. È possibile scegliere se calcolare questo periodo a partire dalla creazione del contenuto o, per OneDrive e SharePoint, dalla data dell'ultima modifica.

Esempi:
  
- SharePoint: se si vuole conservare il contenuto di una raccolta siti per sette anni dopo l'ultima modifica e un documento presente nella raccolta siti non è stato modificato per sei anni, il documento verrà conservato solo per un altro anno se non viene modificato. Se il documento viene nuovamente modificato, la durata viene ricalcolata in base alla nuova data di modifica e il documento verrà conservato per altri sette anni.
  
- Exchange: se si vuole conservare il contenuto di una cassetta postale per sette anni e un messaggio è stato inviato sei anni fa, il messaggio verrà conservato solo per un altro anno. Per il contenuto di Exchange, l'età dipende dalla data di ricezione per la posta in arrivo o dalla data di invio per la posta in uscita. La conservazione del contenuto in base all'ultima modifica si applica solo al contenuto del sito di OneDrive e SharePoint.
  
Al termine del periodo di conservazione, si sceglie se si vuole eliminare definitivamente il contenuto:
  
![Pagina delle impostazioni di conservazione](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminazione di contenuto antecedente a una data specifica

I criteri di conservazione possono conservare e quindi eliminare il contenuto successivamente o eliminare il contenuto obsoleto senza conservarlo.
  
Se i criteri di conservazione eliminano il contenuto, è importante tenere presente che il periodo di tempo specificato per i criteri di conservazione viene calcolato dal momento in cui il contenuto è stato creato o modificato, non dal momento dell'assegnazione dei criteri.
  
![Impostazioni di eliminazione](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
Ad esempio, si supponga di creare criteri di conservazione che eliminano il contenuto dopo tre anni e quindi di assegnarli a tutti gli account di OneDrive, che includono grandi quantità di contenuti creati quattro o cinque anni fa. In questo caso, molti contenuti verranno eliminati subito dopo la prima assegnazione dei criteri di conservazione. Per questo motivo, è importante comprendere che i criteri di conservazione che eliminano il contenuto possono avere un impatto notevole. 
  
Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.
  
![Avviso riguardante l'eliminazione del contenuto](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>Impostazioni avanzate per identificare il contenuto che soddisfa condizioni specifiche

I criteri di conservazione possono essere applicati a tutto il contenuto nelle posizioni incluse oppure solo al contenuto che contiene parole chiave specifiche o [tipi specifici di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
![Opzioni avanzate di conservazione](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>Identificare il contenuto che include parole chiave specifiche

È possibile applicare i criteri di conservazione solo al contenuto che soddisfa specifiche condizioni e quindi eseguire azioni di conservazione solo su tale contenuto. Le condizioni disponibili supportano l'applicazione di criteri di conservazione al contenuto che include parole o frasi specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT. Per altre informazioni sugli operatori, vedere [Query con parola chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).
  
Il supporto delle proprietà disponibili per le ricerche (ad esempio, **subject:**) sarà disponibile a breve.
  
I criteri di conservazione basati su query usano l'indice di ricerca per identificare il contenuto.
  
![Editor di query](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>Identificare il contenuto che include informazioni riservate

You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.
  
![Pagina riguardante i tipi di informazioni riservate](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
Note:
  
- I criteri di conservazione avanzati per le informazioni riservate non si applicano alle cartelle pubbliche di Exchange o a Skype for Business perché queste posizioni non supportano i tipi di informazioni riservate.
    
- Exchange Online usa regole del flusso di posta, note anche come regole di trasporto, per identificare le informazioni riservate, quindi funziona solo per i messaggi in transito, non per tutti gli elementi già archiviati in una cassetta postale. Per Exchange Online, questo significa che i criteri di conservazione possono identificare le informazioni riservate e possono eseguire azioni di conservazione solo nei messaggi ricevuti **dopo** l'applicazione dei criteri alla cassetta postale. I criteri di conservazione basati su query descritti nella sezione precedente non hanno questa limitazione perché usano l'indice di ricerca per identificare il contenuto. 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>Applicazione di criteri di conservazione a un'intera organizzazione o a posizioni specifiche

È possibile applicare facilmente i criteri di conservazione a un'intera organizzazione, a intere posizioni oppure a posizioni o utenti specifici.
  
### <a name="org-wide-policy"></a>Criteri a livello di organizzazione

Una delle caratteristiche più efficaci dei criteri di conservazione riguarda la possibilità di applicare i criteri alle posizioni in Microsoft 365, tra cui:
  
- Posta elettronica di Exchange
    
- Raccolte siti di SharePoint
    
- Account di OneDrive
    
- Gruppi di Microsoft 365 (si applica al contenuto della cassetta postale del gruppo e del sito di SharePoint associato).
    
- Cartelle pubbliche di Exchange
    

![Opzione Tutte le posizioni](../media/retention-policies-all-locations.png)

Altre caratteristiche importanti di un criterio di conservazione a livello di organizzazione includono:
  
- Non sono previsti limiti al numero di cassette postali o di siti inclusi nel criterio.
    
- Per Exchange, le nuove cassette postali create dopo l'applicazione del criterio ereditano automaticamente il criterio.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>Criteri validi per intere posizioni

Quando si scelgono le posizioni, è possibile includere o escludere facilmente un'intera posizione, ad esempio la posta elettronica di Exchange o gli account di OneDrive. A questo scopo, attivare o disattivare lo **Stato** di tale posizione. 
  
Come per i criteri a livello di organizzazione, un criterio applicabile a una qualsiasi combinazione di posizioni complete può includere un numero illimitato di cassette postali o siti. 

Ad esempio, se un criterio include tutta la posta elettronica di Exchange e tutti i siti di SharePoint, verranno inclusi tutti i siti e tutte le cassette postali, indipendentemente dal numero. Per Exchange, le nuove cassette postali create dopo l'applicazione del criterio ereditano automaticamente il criterio.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Criteri con specifiche inclusioni o esclusioni

È anche possibile applicare un criterio di conservazione a specifici utenti, gruppi di Microsoft 365 o siti. A questo scopo, attivare lo **Stato** di tale posizione e quindi usare i collegamenti per includere o escludere determinati utenti, gruppi di Microsoft 365 o siti. 
  
Questa configurazione, tuttavia, prevede dei limiti se i criteri di conservazione includono o escludono più di 1.000 posizioni specifiche:
  
- Valori massimi per i criteri di conservazione:
    - 1.000 cassette postali
    - 1.000 gruppi di Microsoft 365
    - 1.000 utenti per le chat private di Teams
    - 100 siti (OneDrive o SharePoint)

Il un numero massimo di criteri supportati per un tenant è di 10.000. Questi elementi includono criteri di conservazione, criteri per le etichette di conservazione e criteri di conservazione applicati automaticamente.

Se è probabile che i propri criteri di conservazione siano soggetti a queste limitazioni, scegliere le opzioni di configurazione che prevedono l'applicazione a intere posizioni oppure usare un criterio a livello di organizzazione.

## <a name="updating-retention-policies"></a>Aggiornamento dei criteri di conservazione

Se si modifica un criterio di conservazione ed esiste già contenuto soggetto alle impostazioni originali del criterio, le impostazioni aggiornate verranno applicate automaticamente al tale contenuto oltre che ai nuovi contenuti identificati.

In genere l'aggiornamento è piuttosto rapido, ma può richiedere alcuni giorni. Una volta completata la replica del criterio nelle diverse posizioni di Microsoft 365, il suo stato nel Centro conformità Microsoft 365 passerà da **Attivato (in sospeso)** ad **Attivato (operazione riuscita)**.

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>Trovare i cmdlet di PowerShell per i criteri di conservazione

Per usare i cmdlet dei criteri di conservazione:
  
1. [Connettersi a PowerShell in Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Usare questi cmdlet del Centro sicurezza e conformità di Office 365:
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a>Bloccare i criteri di conservazione con PowerShell

Se è necessario usare la [protezione dell'archiviazione](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) per soddisfare i requisiti normativi, occorre usare PowerShell.

1. [Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Visualizzare un elenco dei criteri di conservazione e trovare il nome del criterio da bloccare eseguendo `Get-RetentionCompliancePolicy`.
    
    ![Elenco dei criteri di conservazione in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. Per applicare la protezione dell'archiviazione su un criterio di conservazione, eseguire `Set-RetentionCompliancePolicy` con il parametro `RestrictiveRetention` impostato su true. Ad esempio:
    
        Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
    
    ![Parametro RestrictiveRetention in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    Dopo aver eseguito il cmdlet, scegliere **Sì a tutti**:
    
    ![Richiesta di conferma del blocco dei criteri di conservazione in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

La protezione dell'archiviazione è ora inserita nei criteri di conservazione. Se si esegue `Get-RetentionCompliancePolicy`, il parametro `RestrictiveRetention` viene impostato su true. Ad esempio:

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![Criteri bloccati con tutti i parametri visualizzati in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

