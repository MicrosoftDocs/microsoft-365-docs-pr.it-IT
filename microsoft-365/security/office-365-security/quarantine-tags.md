---
title: Tag di quarantena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gli amministratori possono imparare a usare i tag di quarantena per controllare quali utenti sono in grado di eseguire nei messaggi in quarantena.
ms.openlocfilehash: 557a6832807c1768f482e76c76c0e92b027e49a7
ms.sourcegitcommit: 2810d1347e5016412074b2dd18e654aee7e593de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2020
ms.locfileid: "48819230"
---
# <a name="quarantine-tags"></a>Tag di quarantena

> [!NOTE]
> Le funzionalità descritte in questo articolo sono attualmente in anteprima, non sono disponibili per tutti gli utenti e sono soggette a modifiche.

I tag di quarantena in Exchange Online Protection (EOP) consentono agli amministratori di controllare quali utenti sono in grado di eseguire nei messaggi in quarantena in base al modo in cui il messaggio è arrivato in quarantena.

EOP ha tradizionalmente consentito o impedito alcuni livelli di interattività per i messaggi in [quarantena](find-and-release-quarantined-messages-as-a-user.md) e nelle [notifiche di posta indesiderata dell'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md). Ad esempio, gli utenti finali possono visualizzare e rilasciare i messaggi che sono stati messi in quarantena dal filtro antispam come posta indesiderata o in blocco, ma non possono visualizzare o rilasciare messaggi che sono stati messi in quarantena come phishing ad alta sicurezza.

Per le [funzionalità di protezione supportate](#step-2-assign-a-quarantine-tag-to-supported-features), i tag Quarantine specificano quali utenti sono autorizzati a eseguire nei messaggi di notifica di posta indesiderata dell'utente finale e nei messaggi in quarantena (messaggi in cui l'utente è destinatario). I tag di quarantena predefiniti vengono assegnati automaticamente per applicare le funzionalità storiche per gli utenti finali nei messaggi in quarantena. In alternativa, è possibile creare e assegnare tag di quarantena personalizzati per consentire o impedire agli utenti finali di eseguire azioni specifiche sui messaggi in quarantena.

Le singole autorizzazioni vengono combinate nei seguenti gruppi di autorizzazioni preimpostati:

- Nessun diritto di accesso
- Accesso limitato
- Accesso completo

Nella tabella seguente sono descritte le autorizzazioni individuali disponibili e quelle incluse o non incluse nei gruppi di autorizzazioni preimpostati:

|Autorizzazione|Nessun diritto di accesso|Accesso limitato|Accesso completo|
|---|:---:|:---:|:---:|
|**Consenti mittente** ( _PermissionToAllowSender_ )|||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Blocca mittente** ( _PermissionToBlockSender_ )||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Delete** ( _PermissionToDelete_ )||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Anteprima** ( _PermissionToPreview_ )||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Consenti ai destinatari di rilasciare un messaggio dalla quarantena** ( _PermissionToRelease_ )|||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena** ( _PermissionToRequestRelease_ )||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

Se non si desiderano le autorizzazioni predefinite nei gruppi di autorizzazioni preimpostati, è possibile utilizzare le autorizzazioni personalizzate quando si creano o si modificano i tag di quarantena personalizzati. Per ulteriori informazioni sulle operazioni eseguite da ogni autorizzazione, vedere la sezione relativa alle autorizzazioni per i [tag di quarantena](#quarantine-tag-permission-details) più avanti in questo articolo.

È possibile creare e assegnare tag di quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali di Exchange Online; standalone EOP PowerShell nelle organizzazioni di EOP senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina dei **tag di quarantena** , Apri <https://protection.office.com/quarantineTags> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per visualizzare, creare, modificare o rimuovere i tag di quarantena, è necessario essere membri di uno dei gruppi di ruoli seguenti:
  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Passaggio 1: creare tag di quarantena nel centro sicurezza & Compliance

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** e quindi selezionare i **tag di quarantena** .

2. Nella pagina dei **tag di quarantena** , selezionare **Aggiungi tag personalizzato** .

3. Verrà visualizzata la procedura guidata **nuovo tag** . Nella pagina **nome tag** immettere un nome breve ma univoco nel campo **nome tag** . È necessario identificare e selezionare il tag per nome nei passaggi imminenti. Al termine dell'operazione, fare clic su **Avanti** .

4. Nella pagina **accesso ai messaggi destinatario** selezionare uno dei valori seguenti:
   - **Nessun accesso**
   - **Accesso limitato**
   - **Accesso completo**

   Le singole autorizzazioni incluse in questi gruppi di autorizzazioni sono descritte in precedenza in questo articolo.

   Per specificare le autorizzazioni personalizzate, selezionare **Imposta accesso specifico (avanzato)** e configurare le impostazioni seguenti:

     - **Selezionare la preferenza azione di rilascio** : selezionare uno dei valori seguenti:
       - **Nessuna azione di rilascio** : questo è il valore predefinito.
       - **Consenti ai destinatari di rilasciare un messaggio dalla quarantena**
       - **Consenti ai destinatari di richiedere il rilascio di un messaggio dalla quarantena**

     - **Selezionare ulteriori azioni che i destinatari possono intraprendere nei messaggi in quarantena** : selezionare alcuni, tutti o nessuno dei valori seguenti:
       - **Elimina**
       - **Anteprima**
       - **Consenti mittente**
       - **Blocca mittente**

   Queste autorizzazioni e il loro effetto sui messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale sono descritte nella sezione [informazioni sulle autorizzazioni dei tag di quarantena](#quarantine-tag-permission-details) più avanti in questo articolo.

   Al termine dell'operazione, fare clic su **Avanti** .

5. Nella pagina **Riepilogo** visualizzata, esaminare le impostazioni. È possibile fare clic su **modifica** su ogni impostazione per modificarla.

   Al termine, fare clic su **Invia** .

6. Fare clic su **fine** nella pagina di conferma che viene visualizzata.

A questo punto si è pronti per assegnare il tag Quarantine a una funzionalità di quarantena, come descritto nella sezione [passaggio 2](#step-2-assign-a-quarantine-tag-to-supported-features) .

### <a name="create-quarantine-tags-in-powershell"></a>Creare tag di quarantena in PowerShell

Se si preferisce utilizzare PowerShell per creare tag di quarantena, connettersi a PowerShell di Exchange Online o Exchange Online Protection PowerShell e utilizzare il cmdlet **New-QuarantineTag** . Sono disponibili due metodi diversi tra cui scegliere:

- Utilizzare il parametro _EndUserQuarantinePermissionsValue_ .
- Utilizzare il parametro _EndUserQuarantinePermissions_ .

Questi metodi sono descritti nelle sezioni seguenti.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Utilizzare il parametro EndUserQuarantinePermissionsValue

Per creare un tag di quarantena utilizzando il parametro _EndUserQuarantinePermissionsValue_ , utilizzare la sintassi seguente:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

Il parametro _EndUserQuarantinePermissionsValue_ utilizza un valore decimale convertito da un valore binario. Il valore binario corrisponde alle autorizzazioni di quarantena dell'utente finale disponibili in un ordine specifico. Per ogni autorizzazione, il valore 1 è uguale a true e il valore 0 è uguale a false.

Nella tabella seguente sono descritti l'ordine e i valori richiesti per ogni singola autorizzazione in gruppi di autorizzazioni preimpostati:

****

|Autorizzazione|Nessun diritto di accesso|Accesso limitato|Accesso completo|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1 |
|PermissionToBlockSender|0|1 |1 |
|PermissionToDelete|0|1 |1 |
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1 |1 |
|PermissionToRelease<sup>\*\*</sup>|0|0|1 |
|PermissionToRequestRelease<sup>\*\*</sup>|0|1 |0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|Valore binario|00000000|01101010|11101100|
|Valore Decimal da utilizzare|0|106|236|

<sup>\*</sup> Attualmente, questo valore è sempre 0. Per PermissionToViewHeader, il valore 0 non nasconde il pulsante **Visualizza intestazione del messaggio** nei dettagli del messaggio in quarantena (il pulsante è sempre disponibile).

<sup>\*\*</sup> Non impostare entrambi i valori su 1. Impostare uno su 1 e l'altro su 0 o impostare entrambi su 0.

In questo esempio viene creato un nuovo nome di tag di quarantena NoAccess che assegna le autorizzazioni No Access come descritto nella tabella precedente.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Per le autorizzazioni di accesso limitate, utilizzare il valore 106. Per le autorizzazioni di accesso completo, utilizzare il valore 236.

Per le autorizzazioni personalizzate, utilizzare la tabella precedente per ottenere il valore binario corrispondente alle autorizzazioni desiderate. Convertire il valore binario in un valore decimale e utilizzare il valore decimale per il parametro _EndUserQuarantinePermissionsValue_ .

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Utilizzare il parametro EndUserQuarantinePermissions

Per creare un tag di quarantena utilizzando il parametro _EndUserQuarantinePermissionsValue_ , eseguire le operazioni seguenti:

R. Archiviare un oggetto autorizzazioni per la quarantena in una variabile utilizzando il cmdlet **New-QuarantinePermissions** .
<br/>
B. Utilizzare la variabile come valore _EndUserQuarantinePermissions_ nel comando **New-QuarantineTag** .

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Passaggio A: archiviare un oggetto autorizzazioni per la quarantena in una variabile

Utilizzare la sintassi seguente:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

Il valore predefinito per tutti i parametri inutilizzati è `$false` , quindi è necessario solo utilizzare i parametri in cui si desidera impostare il valore su `$true` .

Negli esempi seguenti viene illustrato come creare oggetti Permission che corrispondono ai gruppi di autorizzazioni preimpostati:

- **Nessun accesso** :

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Accesso limitato** :

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Accesso completo** :

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Per visualizzare i valori impostati, eseguire il nome della variabile come comando (ad esempio, eseguire il comando `$NoAccess` ).

Per le autorizzazioni personalizzate, non impostare entrambi i parametri _PermissionToRelease_ e _PermissionToRequestRelease_ su `$true` . Impostare uno su `$true` e lasciare l'altro come `$false` , o lasciare entrambi come `$false` .

È inoltre possibile modificare una variabile dell'oggetto Permissions esistente dopo aver creato, ma prima di utilizzarla utilizzando il cmdlet **set-QuarantinePermissions** .

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) e [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Passaggio B: utilizzare la variabile nel comando New-QuarantineTag

Dopo aver creato e archiviato l'oggetto Permissions in una variabile, utilizzare la variabile per il valore del parametro _EndUserQuarantinePermission_ nel comando **New-QuarantineTag** seguente:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

In questo esempio viene creato un nuovo tag di quarantena denominato LimitedAccess utilizzando l' `$LimitedAccess` oggetto Permissions descritto e creato nel passaggio precedente.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Passaggio 2: assegnare un tag di quarantena alle funzionalità supportate

Nelle funzionalità di protezione _supportate_ che consentono di mettere in quarantena i messaggi o i file (azione automatica o configurabile), è possibile assegnare un tag di quarantena alle azioni di quarantena disponibili. Nella tabella seguente sono descritte le funzionalità per la quarantena dei messaggi e la disponibilità di tag di quarantena:

****

|Funzionalità|I tag di quarantena sono supportati?|Tag di quarantena predefiniti utilizzati|
|---|:---:|---|
|[Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md): <ul><li>**Posta indesiderata** ( _SpamAction_ )</li><li>**Posta indesiderata con elevata sicurezza** ( _HighConfidenceSpamAction_ )</li><li>**Messaggi di posta elettronica di phishing** ( _PhishSpamAction_ )</li><li>**Posta elettronica di phishing con elevata sicurezza** ( _HighConfidencePhishAction_ )</li><li>**Messaggi di posta elettronica in blocco** ( _BulkSpamAction_ )</li></ul>|Sì|<ul><li>DefaultSpamTag (accesso completo)</li><li>DefaultHighConfSpamTag (accesso completo)</li><li>DefaultPhishTag (accesso completo)</li><li>DefaultHighConfPhishTag (nessun accesso)</li><li>DefaultBulkTag (accesso completo)</li></ul>
|Criteri di anti-phishing: <ul><li>[Protezione di intelligence spoof](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</li><li>[Protezione della rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies):<sup>\*</sup> <ul><li>**Se il messaggio di posta elettronica viene inviato da un utente rappresentato** ( _TargetedUserProtectionAction_ )</li><li>**Se il messaggio di posta elettronica viene inviato da un dominio rappresentato** ( _TargetedDomainProtectionAction_ )</li><li>Intelligence delle cassette **postali** \> **Se il messaggio di posta elettronica viene inviato da un utente rappresentato** ( _MailboxIntelligenceProtectionAction_ )</li></ul></li></ul></ul>|No|n/d|
|[Criteri anti-malware](configure-anti-malware-policies.md): tutti i messaggi rilevati vengono sempre messi in quarantena.|No|n/d|
|[ATP per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)|No|n/d|
|[Regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (note anche come regole di trasporto) con l'azione: **recapitare il messaggio alla quarantena ospitata** ( _Quarantine_ ).|No|n/d|
|

<sup>\*</sup> Le impostazioni di protezione della rappresentazione sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.

Se si è soddisfatti delle autorizzazioni dell'utente finale fornite dai tag di quarantena predefiniti, non è necessario eseguire alcuna operazione. Se si desidera personalizzare le funzionalità degli utenti finali (pulsanti disponibili) nelle notifiche di posta indesiderata dell'utente finale o nei dettagli dei messaggi in quarantena, è possibile assegnare un tag di quarantena personalizzato.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Assegnare i tag di quarantena nei criteri di protezione da posta indesiderata nel centro sicurezza & conformità

Le istruzioni complete per la creazione e la modifica dei criteri di protezione da posta indesiderata sono descritte in [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> e quindi selezionare **protezione da posta indesiderata** . In alternativa, aprire <https://protection.office.com/antispam> .

2. Individuare e selezionare un criterio di protezione da posta indesiderata esistente da modificare o creare un nuovo criterio di protezione dalla posta indesiderata.

3. Nel riquadro a comparsa dettagli criteri espandere la sezione **posta indesiderata e azioni in blocco** .
  
4. Se è stato selezionato **messaggio in quarantena** per l'azione di un verdetto di filtraggio della posta indesiderata, è disponibile la casella di **tag Applica criterio di quarantena** che consente di selezionare il tag di quarantena per tale verdetto.

   **Nota** : quando si crea un nuovo criterio, un valore del tag di quarantena vuoto per un verdetto del filtro della posta indesiderata indica che viene utilizzato il tag di quarantena predefinito per il verdetto. Quando si modifica il criterio in un secondo momento, i valori vuoti vengono sostituiti dai nomi dei tag di quarantena predefiniti effettivi come descritto nella tabella precedente.
  
   ![Selezioni dei tag di quarantena in un criterio di protezione da posta indesiderata](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Al termine, scegliere **Salva** .

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Assegnare i tag di quarantena nei criteri di protezione da posta indesiderata in PowerShell

Se si preferisce utilizzare PowerShell per assegnare i tag di quarantena nei criteri di protezione da posta indesiderata, connettersi a PowerShell di Exchange Online o Exchange Online Protection PowerShell e utilizzare la sintassi seguente:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Note** :

- Il valore predefinito per il parametro _HighConfidencePhishAction_ è Quarantine, quindi non è necessario impostare l'azione di quarantena per i rilevamenti di phishing ad alta confidenza nei nuovi criteri di protezione da posta indesiderata. Per tutti gli altri verdetti di filtraggio della posta indesiderata nei criteri di protezione da posta indesiderata nuovi o esistenti, il tag Quarantine è efficace solo se il valore dell'azione è Quarantine. Per visualizzare i valori di azione nei criteri di protezione da posta indesiderata esistenti, eseguire il seguente comando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Per informazioni sui valori di azione predefiniti e sui valori di azione consigliati per standard e Strict, vedere Impostazioni dei criteri di protezione da [posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

- Un verdetto di filtraggio della posta indesiderata senza un parametro di tag di quarantena corrispondente indica che viene utilizzato il [tag di quarantena predefinito](#step-2-assign-a-quarantine-tag-to-supported-features) .

  Se si desidera modificare le funzionalità predefinite degli utenti finali nei messaggi in quarantena, è necessario sostituire un tag di quarantena predefinito con un tag di quarantena personalizzato.

- Un nuovo criterio di protezione dalla posta indesiderata in PowerShell richiede un criterio di filtro della posta indesiderata (impostazioni) utilizzando il cmdlet **New-HostedContentFilterPolicy** e una nuova regola di filtro posta indesiderata (filtri destinatario) utilizzando il cmdlet **New-HostedContentFilterRule** . Per istruzioni, vedere [utilizzare PowerShell per creare criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).

In questo esempio viene creato un nuovo criterio di filtro posta indesiderata denominato Research Department con le seguenti impostazioni:

- L'azione per tutti i verdetti del filtro della posta indesiderata è impostata su Quarantine.
- Il tag di quarantena personalizzato denominato NoAccess che non assegna autorizzazioni di **accesso** sostituisce tutti i tag di quarantena predefiniti che non assegnano le autorizzazioni di **accesso** per impostazione predefinita.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

In questo esempio viene modificato il criterio di filtro posta indesiderata esistente denominato risorse umane. L'azione relativa al verdetto per la quarantena della posta indesiderata è impostata su Quarantine e viene assegnato il tag di quarantena personalizzato denominato NoAccess.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Configurare le impostazioni di notifica per la quarantena globale nel centro sicurezza & conformità

Le impostazioni globali per i tag Quarantine consentono di personalizzare le notifiche di posta indesiderata dell'utente finale inviate ai destinatari dei messaggi in quarantena. Per ulteriori informazioni su queste notifiche, vedere [notifiche di posta indesiderata dell'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** e quindi selezionare i **tag di quarantena** .

2. Nella pagina **tag di quarantena** selezionare **Impostazioni globali** .

3. Nel riquadro a comparsa **delle impostazioni di notifica per la quarantena** che si apre, configurare alcune o tutte le impostazioni seguenti:

   - **Utilizzare il logo della società** : selezionare questa opzione per sostituire il logo Microsoft predefinito che viene utilizzato all'inizio delle notifiche di posta indesiderata dell'utente finale. Prima di eseguire questa operazione, è necessario seguire le istruzioni riportate in [Customize the Microsoft 365 Theme for Your Organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your Custom logo.

     Nella schermata seguente viene mostrato un logo personalizzato in una notifica di posta indesiderata dell'utente finale:

     ![Un logo personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-logo.png)

   - **Scegliere la lingua** : le notifiche di posta indesiderata dell'utente finale sono già localizzate in base alle impostazioni della lingua del destinatario. È possibile specificare testo personalizzato in lingue diverse per il **nome visualizzato** e i valori di dichiarazione di non **responsabilità** .

     Selezionare almeno una lingua nella prima casella della lingua e quindi fare clic su **Aggiungi** . È possibile selezionare più lingue facendo clic su **Aggiungi** dopo ogni. Una casella della lingua della sezione Visualizza tutte le lingue selezionate:

     ![Lingue selezionate nella seconda lingua nelle impostazioni di notifica della quarantena globale dei tag di quarantena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Nome visualizzato** : personalizzare il nome visualizzato del mittente utilizzato nelle notifiche di posta indesiderata dell'utente finale.

     Per ogni lingua aggiunta, selezionare la lingua nella seconda casella di lingua (non fare clic sulla X) e immettere il valore di testo desiderato nella casella **nome visualizzato** .

     Nella schermata seguente viene mostrato il nome visualizzato personalizzato in una notifica di posta indesiderata dell'utente finale:

     ![Un nome visualizzato del mittente personalizzato in una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Dichiarazione** di non responsabilità: aggiungere una dichiarazione di non responsabilità personalizzata alla fine delle notifiche di posta indesiderata dell'utente finale Il testo localizzato, **una dichiarazione di non responsabilità dell'organizzazione:** è sempre incluso per primo, seguito dal testo specificato.

     Per ogni lingua aggiunta, selezionare la lingua nella seconda casella di lingua (non fare clic sulla X) e immettere il valore del testo desiderato nella casella Dichiarazione di non **responsabilità** .

     Nella schermata seguente viene visualizzata la dichiarazione di non responsabilità personalizzata in una notifica di posta indesiderata dell'utente finale:

     ![Una dichiarazione di non responsabilità personalizzata nella parte inferiore di una notifica di posta indesiderata dell'utente finale](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Visualizzare i tag per la quarantena nel centro sicurezza & Compliance

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** e quindi selezionare i **tag di quarantena** .

- Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, selezionare il tag Quarantine nell'elenco (non selezionare la casella di controllo).

- Per visualizzare le impostazioni globali, selezionare **Impostazioni globali**

### <a name="view-quarantine-tags-in-powershell"></a>Visualizzare i tag di quarantena in PowerShell

Se si preferisce utilizzare PowerShell per visualizzare i tag di quarantena, eseguire una delle operazioni seguenti:

- Per visualizzare un elenco riepilogativo di tutti i tag incorporati o personalizzati, eseguire il comando riportato di seguito:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Per visualizzare le impostazioni dei tag di quarantena incorporati o personalizzati, sostituire \<TagName\> con il nome del tag Quarantine ed eseguire il comando riportato di seguito:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Per visualizzare le impostazioni globali, eseguire il comando riportato di seguito:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Rimuovere i tag di quarantena nel centro sicurezza & conformità

**Note** :

- Non è possibile rimuovere i tag di quarantena incorporati.

- Prima di rimuovere un tag di quarantena personalizzato, verificare che non sia in uso. Ad esempio, eseguire il comando seguente in PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Se viene utilizzato il tag Quarantine, [sostituire il tag di quarantena assegnato prima di](#step-2-assign-a-quarantine-tag-to-supported-features) rimuoverlo.

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** e quindi selezionare i **tag di quarantena** .

2. Nella pagina dei **tag di quarantena** selezionare il tag di quarantena personalizzato che si desidera rimuovere e il tag fare clic su **Elimina** .

3. Fare clic su **Rimuovi tag** nella finestra di dialogo di conferma che viene visualizzata.

### <a name="remove-quarantine-tags-in-powershell"></a>Rimuovere i tag di quarantena in PowerShell

Se si preferisce utilizzare PowerShell per rimuovere un tag di quarantena personalizzato, sostituire \<TagName\> con il nome del tag Quarantine ed eseguire il comando riportato di seguito:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).

## <a name="quarantine-tag-permission-details"></a>Dettagli sull'autorizzazione dei tag per la quarantena

Nelle sezioni seguenti vengono descritti gli effetti dei gruppi di autorizzazioni preimpostati e delle autorizzazioni individuali nei dettagli dei messaggi in quarantena e nelle notifiche di posta indesiderata dell'utente finale.

### <a name="preset-permissions-groups"></a>Gruppi di autorizzazioni preimpostati

Nella tabella all'inizio di questo articolo vengono elencate le singole autorizzazioni incluse nei gruppi di autorizzazioni preimpostati.

#### <a name="no-access"></a>Nessun diritto di accesso

Se il tag Quarantine assegna le autorizzazioni di **accesso no** (nessuna autorizzazione), gli utenti possono ancora ottenere alcune funzionalità di base:

- **Dettagli del messaggio in quarantena** : il pulsante **Visualizza intestazione del messaggio** è sempre disponibile.

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce all'utente nessuna autorizzazione di accesso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Notifiche di posta indesiderata dell'utente finale** : il pulsante **Revisione** che porta l'utente al messaggio in quarantena è sempre disponibile.

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce all'utente nessuna autorizzazione di accesso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Accesso limitato

Se il tag Quarantine assegna le autorizzazioni di **accesso limitate** , gli utenti riceveranno le seguenti funzionalità:

- **Dettagli del messaggio in quarantena** : sono disponibili i seguenti pulsanti:
  - **Rilascio delle richieste**
  - **Visualizzazione delle intestazioni del messaggio**
  - **Messaggio di anteprima**
  - **Blocca mittente**
  - **Rimuovi dalla quarantena**

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce le autorizzazioni di accesso limitate all'utente](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Notifiche di posta indesiderata dell'utente finale** : sono disponibili i seguenti pulsanti:
  - **Blocca mittente**
  - **Verifica**

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce le autorizzazioni di accesso limitate all'utente](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Accesso completo

Se il tag Quarantine assegna le autorizzazioni di **accesso completo** (tutte le autorizzazioni disponibili), gli utenti ottengono le seguenti funzionalità:

- **Dettagli del messaggio in quarantena** : sono disponibili i seguenti pulsanti:
  - **Rilascia il messaggio**
  - **Visualizzazione delle intestazioni del messaggio**
  - **Messaggio di anteprima**
  - **Blocca mittente**
  - **Consenti mittente**
  - **Rimuovi dalla quarantena**

  ![Pulsanti disponibili nei dettagli del messaggio in quarantena se il tag Quarantine fornisce all'utente le autorizzazioni di accesso completo](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Notifiche di posta indesiderata dell'utente finale** : sono disponibili i seguenti pulsanti:
  - **Blocca mittente**
  - **Rilascio**
  - **Verifica**

  ![Pulsanti disponibili nella notifica di posta indesiderata dell'utente finale se il tag Quarantine fornisce le autorizzazioni di accesso completo dell'utente](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Autorizzazioni individuali

> [!NOTE]
> Tenere presente che gli utenti ottengono sempre i pulsanti descritti nella sezione [No Access](#no-access) . Questi pulsanti non sono inclusi nelle singole descrizioni delle autorizzazioni.

#### <a name="allow-sender-permission"></a>Consenti autorizzazione mittente

L'autorizzazione **Consenti mittente** ( _PermissionToAllowSender_ ) consente di controllare l'accesso al pulsante per consentire agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco dei mittenti attendibili.

- **Dettagli del messaggio in quarantena** :
  - **Consenti autorizzazione mittente** attivata: il pulsante **Consenti mittente** è disponibile.
  - **Consenti autorizzazioni mittente** disabilitate: il pulsante **Consenti mittente** non è disponibile.

- **Notifiche di posta indesiderata dell'utente finale** : nessun effetto.

Per ulteriori informazioni sull'elenco dei mittenti attendibili, vedere [Impedisci](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) l'esecuzione del blocco dei mittenti trusted e [utilizzo di PowerShell di Exchange Online per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

### <a name="block-sender-permission"></a>Autorizzazione Blocca mittente

L'autorizzazione **Blocca mittente** ( _PermissionToBlockSender_ ) consente di controllare l'accesso al pulsante per consentire agli utenti di aggiungere comodamente il mittente del messaggio in quarantena all'elenco dei mittenti bloccati.

- **Dettagli del messaggio in quarantena** :
  - **Blocca autorizzazione mittente** attivata: il pulsante **Blocca mittente** è disponibile.
  - **Blocca autorizzazioni mittente** disabilitate: il pulsante **Blocca mittente** non è disponibile.

- **Notifiche di posta indesiderata dell'utente finale** :
  - **Blocca autorizzazioni mittente** disabilitate: il pulsante **Blocca mittente** non è disponibile.
  - **Blocca autorizzazione mittente** attivata: il pulsante **Blocca mittente** è disponibile.

Per ulteriori informazioni sull'elenco dei mittenti bloccati, vedere [blocco dei messaggi da](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) parte di [un utente e utilizzo di PowerShell di Exchange Online per configurare la raccolta degli elenchi indirizzi attendibili in una cassetta postale](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

### <a name="delete-permission"></a>Autorizzazione di eliminazione

L'autorizzazione di **eliminazione** ( _PermissionToDelete_ ) consente di controllare la possibilità per gli utenti di eliminare i propri messaggi (messaggi in cui l'utente è destinatario) dalla quarantena.

- **Dettagli del messaggio in quarantena** :
  - Autorizzazioni di **eliminazione** abilitate: il pulsante **Rimuovi da Quarantine** è disponibile.
  - Autorizzazioni di **eliminazione** disabilitate: il pulsante **Rimuovi dalla quarantena** non è disponibile.

- **Notifiche di posta indesiderata dell'utente finale** : nessun effetto.

### <a name="preview-permission"></a>Autorizzazione anteprima

L'autorizzazione **Preview** ( _PermissionToPreview_ ) consente di controllare la possibilità per gli utenti di visualizzare in anteprima i propri messaggi in quarantena.

- **Dettagli del messaggio in quarantena** :
  - Autorizzazioni di **Anteprima** abilitate: il pulsante **Anteprima messaggio** è disponibile.
  - Autorizzazioni di **Anteprima** disabilitate: il pulsante **Anteprima messaggio** non è disponibile.

- **Notifiche di posta indesiderata dell'utente finale** : nessun effetto.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Consenti ai destinatari di rilasciare un messaggio dall'autorizzazione per la quarantena

L'autorizzazione **Consenti ai destinatari di rilasciare un messaggio dalla quarantena** ( _PermissionToRelease_ ) consente di controllare la possibilità per gli utenti di rilasciare i messaggi in quarantena direttamente e senza l'approvazione di un amministratore.

- **Dettagli del messaggio in quarantena** :
  - Autorizzazione abilitata: il pulsante **rilascia messaggio** è disponibile.
  - Autorizzazioni disabilitate: il pulsante **rilascia messaggio** non è disponibile.
  
- **Notifiche di posta indesiderata dell'utente finale** :
  - Autorizzazione abilitata: il pulsante **rilascia** è disponibile.
  - Autorizzazioni disabilitate: il pulsante **rilascia** non è disponibile.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Consenti ai destinatari di richiedere il rilascio di un messaggio dall'autorizzazione per la quarantena

L'opzione **Consenti ai destinatari di richiedere un messaggio da rilasciare dall'autorizzazione di quarantena** ( _PermissionToRequestRelease_ ) controlla la possibilità per gli utenti di _richiedere_ il rilascio dei messaggi in quarantena. Il messaggio viene rilasciato solo dopo che un amministratore approva la richiesta.

- **Dettagli del messaggio in quarantena** :
  - Autorizzazione abilitata: il pulsante **rilascia richiesta** è disponibile.
  - Autorizzazioni disabilitate: il pulsante **rilascia richiesta** non è disponibile.

- **Notifiche di posta indesiderata dell'utente finale** : il pulsante **rilascia** non è disponibile.
