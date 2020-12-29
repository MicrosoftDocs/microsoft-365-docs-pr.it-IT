---
title: Configurare il codice "Customer Key" a livello di applicazione
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare la chiave del cliente per Microsoft 365 per Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file teams.
ms.openlocfilehash: a89b5cb4144de3b548c7ac328f0be775b4262cdc
ms.sourcegitcommit: 8a6540df9d63db1ffb69711381dc44fc2fdaf547
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2020
ms.locfileid: "49736065"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Configurare il codice "Customer Key" a livello di applicazione

Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Microsoft 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft. In altre parole, la chiave del cliente consente ai clienti di aggiungere un livello di crittografia che appartiene a loro, con le chiavi. Data at rest include i dati di Exchange Online e Skype for business archiviati nelle cassette postali e nei file archiviati in SharePoint Online e OneDrive for business.

È necessario configurare Azure prima di poter utilizzare la chiave del cliente per Office 365. In questo argomento vengono descritti i passaggi da seguire per creare e configurare le risorse di Azure necessarie, quindi vengono illustrati i passaggi per la configurazione della chiave del cliente in Office 365. Dopo aver completato l'installazione di Azure, è possibile stabilire quali criteri e quindi quali chiavi, per assegnare alle cassette postali e ai file nell'organizzazione. Le cassette postali e i file per cui non si assegna un criterio utilizzeranno i criteri di crittografia controllati e gestiti da Microsoft. Per ulteriori informazioni sulla chiave del cliente o per una panoramica generale, vedere [Service Encryption with Customer Key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> È consigliabile attenersi alle procedure consigliate riportate in questo argomento. Questi sono denominati **Suggerimento** e **importante**. La chiave Customer consente di controllare le chiavi di crittografia radice il cui ambito può essere grande come l'intera organizzazione. Questo significa che gli errori commessi con queste chiavi possono avere un impatto generale e possono causare interruzioni del servizio o perdita irrevocabile dei dati.
  
## <a name="before-you-set-up-customer-key"></a>Prima di configurare la chiave del cliente

Prima di iniziare, verificare di disporre delle licenze appropriate per l'organizzazione. Utilizzare una sottoscrizione a pagamento e fatturata di Azure utilizzando un contratto Enterprise o un provider di servizi cloud. Gli abbonamenti di Azure acquistati con pay as you go plans o con una carta di credito non sono supportati per la chiave del cliente. A partire dal 1 ° aprile 2020, la chiave del cliente in Office 365 è disponibile in Office 365 E5, M365 E5, M365 E5 compliance e M365 E5 Information Protection & SKU. Microsoft Office 365 Advanced Compliance SKU non è più disponibile per l'ottenimento di nuove licenze. Le licenze di conformità avanzate di Office 365 continueranno a essere supportate.

Per informazioni sui concetti e le procedure illustrate in questo argomento, vedere la documentazione di [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) . Inoltre, acquisire familiarità con i termini utilizzati in Azure, ad esempio, il [tenant di Azure ad](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).

FastTrack viene utilizzato solo per raccogliere le informazioni necessarie per la configurazione del tenant e del servizio utilizzate per la registrazione per la chiave del cliente. Le offerte chiave del cliente sono pubblicate tramite FastTrack in modo che sia opportuno che i partner inviino le informazioni richieste utilizzando lo stesso metodo. FastTrack consente inoltre di archiviare facilmente i dati forniti nell'offerta.
  
Se è necessario ulteriore supporto oltre la documentazione, contattare Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o un partner Microsoft per assistenza. Per fornire commenti e suggerimenti sulla chiave del cliente, inclusa la documentazione, inviare le proprie idee, consigli e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Panoramica della procedura per configurare la chiave del cliente

Per impostare la chiave del cliente, completare queste attività nell'ordine indicato. Nella parte restante di questo articolo vengono fornite istruzioni dettagliate per ogni attività o collegamenti a ulteriori informazioni per ogni passaggio del processo.
  
**In Azure e Microsoft FastTrack:**
  
La maggior parte delle attività verrà completata tramite la connessione remota a Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.
  
- [Creare due nuove sottoscrizioni di Azure](#create-two-new-azure-subscriptions)

- [Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  La registrazione può richiedere da uno a cinque giorni lavorativi.

- [Inviare una richiesta per attivare la chiave del cliente per Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Dopo aver creato le due nuove sottoscrizioni di Azure, è necessario inviare la richiesta di offerta chiave del cliente completando un modulo Web ospitato nel portale di Microsoft FastTrack. **Il team di FastTrack non fornisce assistenza per la chiave del cliente. Office utilizza semplicemente il portale FastTrack per consentire all'utente di inviare il modulo e di aiutarci a tenere conto delle offerte rilevanti per la chiave del cliente**.

- [Creare un Vault Key Azure Premium in ogni sottoscrizione](#create-a-premium-azure-key-vault-in-each-subscription)

- [Assegnare le autorizzazioni per ogni Vault chiave](#assign-permissions-to-each-key-vault)

- [Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Aggiungere una chiave a ogni Vault chiave creando o importando una chiave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Controllare il livello di ripristino delle chiavi](#check-the-recovery-level-of-your-keys)

- [Backup del Vault delle chiavi di Azure](#back-up-azure-key-vault)

- [Convalidare le impostazioni di configurazione di Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Ottenere l'URI per ogni chiave del Vault Key di Azure](#obtain-the-uri-for-each-azure-key-vault-key)

**In Office 365:**
  
Exchange Online e Skype for business:
  
- [Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Assegnare una DEP a una cassetta postale](#assign-a-dep-to-a-mailbox)

- [Convalidare la crittografia della cassetta postale](#validate-mailbox-encryption)

SharePoint Online e OneDrive for business:
  
- [Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Convalidare la crittografia dei file per i file di SharePoint Online, OneDrive for business e teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completare le attività in Azure Key Vault e Microsoft FastTrack per la chiave del cliente

Completare queste attività in Azure Key Vault. È necessario completare questi passaggi, indipendentemente dal fatto che si desideri impostare la chiave del cliente per Exchange Online e Skype for business o per SharePoint Online, OneDrive for business e per i file di teams o per tutti i servizi supportati in Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure

La chiave del cliente richiede due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di creare nuove sottoscrizioni di Azure per l'utilizzo con la chiave del cliente. Le chiavi del Vault Key di Azure possono essere autorizzate solo per le applicazioni nello stesso tenant di Azure Active Directory (Microsoft Azure Active Directory), è necessario creare le nuove sottoscrizioni utilizzando lo stesso tenant di Azure AD utilizzato per l'organizzazione in cui verrà assegnato il DEPs. Ad esempio, utilizzando l'account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione. Per la procedura dettagliata, vedere [iscriversi a Azure come organizzazione](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> La chiave del cliente richiede due chiavi per ogni criterio di crittografia dei dati. Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri distinti dell'organizzazione che configurano una chiave in ogni sottoscrizione. È consigliabile utilizzare queste sottoscrizioni di Azure solo per amministrare le chiavi di crittografia per Office 365. Questo consente di proteggere l'organizzazione nel caso in cui uno degli operatori involontariamente, intenzionalmente o elimini in modo doloso o meno le chiavi per le quali sono responsabili.
>

Non esiste alcun limite pratico per il numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguendo queste procedure consigliate si minimizza l'impatto dell'errore umano contribuendo a gestire le risorse utilizzate dalla chiave del cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Inviare una richiesta per attivare la chiave del cliente per Office 365

Dopo aver completato i passaggi di Azure, è necessario inviare una richiesta di offerta nel [portale Microsoft FastTrack](https://fasttrack.microsoft.com/). Dopo aver inoltrato una richiesta tramite il portale Web di FastTrack, Microsoft verifica i dati di configurazione del Vault Key di Azure e le informazioni di contatto fornite. Le selezioni che vengono apportate nel modulo di offerta per quanto riguarda i funzionari autorizzati dell'organizzazione sono critiche e necessarie per il completamento della registrazione a chiave del cliente. Gli agenti dell'organizzazione selezionati nel modulo saranno utilizzati per garantire l'autenticità di qualsiasi richiesta di revocare e distruggere tutte le chiavi utilizzate con un criterio di crittografia dei dati chiave del cliente. È necessario eseguire questo passaggio una volta per attivare il codice "Customer Key" per Exchange Online e Skype for business e una seconda volta per attivare la chiave del cliente per SharePoint Online e OneDrive for business.
  
Per inviare un'offerta per attivare il codice "Customer Key", eseguire la procedura seguente:
  
1. Utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, eseguire l'accesso al [portale di Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Dopo aver effettuato l'accesso, passare al **Dashboard**.

3. Fare clic su **Distribuisci** dalla barra di spostamento **o** su **Visualizza tutte le risorse di distribuzione** nella scheda informazioni **deploy** ed esaminare l'elenco delle offerte correnti.

4. Scegliere la scheda informazioni per l'offerta che si applica all'utente:

   - **Exchange Online e Skype for business:** Scegliere la **Guida alla chiave di crittografia delle richieste per l'offerta di Exchange Online** .

   - **File di SharePoint Online, OneDrive e teams:** Scegliere la **Guida per la chiave di crittografia delle richieste per SharePoint e OneDrive** .

5. Dopo aver esaminato i dettagli dell'offerta, scegliere **continue to Step 2**.

6. Compilare tutti i dettagli applicabili e le informazioni richieste nel modulo di offerta. Prestare particolare attenzione alle selezioni per i funzionari dell'organizzazione che si desidera autorizzare ad approvare la distruzione permanente e irreversibile delle chiavi di crittografia e dei dati. Dopo aver completato il modulo, scegliere **Submit**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio

La perdita temporanea o permanente delle chiavi di crittografia radice può essere molto dirompente o addirittura catastrofica per l'utilizzo del servizio e può causare una perdita di dati. Per questo motivo, le risorse utilizzate con la chiave del cliente richiedono una protezione sicura. Tutte le risorse di Azure utilizzate con la chiave del cliente offrono meccanismi di protezione oltre la configurazione predefinita. Le sottoscrizioni di Azure possono essere contrassegnate o registrate in un modo che impedirà l'annullamento immediato e irrevocabile. Si tratta della registrazione di un periodo di conservazione obbligatorio. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con il team di Microsoft 365. Questo processo può richiedere da uno a cinque giorni lavorativi. In precedenza, questo è stato talvolta definito come "non annullare".
  
Prima di contattare il team di Microsoft 365, è necessario eseguire i passaggi seguenti per ogni sottoscrizione di Azure utilizzata con la chiave del cliente. Prima di iniziare, assicurarsi di avere installato il modulo di [Azure PowerShell AZ](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) .
  
1. Accedere con PowerShell di Azure. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Register-AzProviderFeature per registrare gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio. Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contattare Microsoft per eseguire il processo di completamento. Per il team di SharePoint e OneDrive for business, contattare [Spock@microsoft.com](mailto:spock@microsoft.com). Per Exchange Online e Skype for business, contattare [exock@microsoft.com](mailto:exock@microsoft.com). Includere quanto segue nel messaggio di posta elettronica:

   **Oggetto**: chiave del cliente per \<*Your tenant's fully-qualified domain name*\>

   **Corpo**: ID di sottoscrizione per i quali si desidera che il periodo di conservazione obbligatorio sia stato completato.
   L'output di Get-AzProviderFeature per ogni sottoscrizione.

   Il contratto di servizio per il completamento di questo processo è di cinque giorni lavorativi una volta che Microsoft è stato informato (e verificato) di aver registrato gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio.

4. Dopo aver ricevuto la notifica da parte di Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il comando Get-AzProviderFeature come indicato di seguito. Se verificato, il comando Get-AzProviderFeature restituisce il valore **registrato** per la proprietà **state di registrazione** . Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Per completare il processo, eseguire il comando Register-AzResourceProvider. Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un Vault Key Azure Premium in ogni sottoscrizione

La procedura per creare un Vault chiave è documentata per [iniziare con Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), che illustra l'installazione e l'avvio di Azure PowerShell, la connessione all'abbonamento di Azure, la creazione di un gruppo di risorse e la creazione di un Vault Key in tale gruppo di risorse.
  
Quando si crea un Vault chiave, è necessario scegliere un SKU: standard o Premium. La SKU standard consente di proteggere i tasti del Vault Key di Azure con il software: non vi è alcuna protezione della chiave HSM (hardware Security Module) e la SKU Premium consente l'utilizzo di HSM per la protezione delle chiavi del Vault Key. La chiave Customer accetta i Vault chiave che utilizzano SKU, anche se Microsoft consiglia vivamente di utilizzare solo la SKU Premium. Il costo delle operazioni con chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo al mese per ogni chiave protetta da HSM. Per informazioni dettagliate, vedere [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) .
  
> [!IMPORTANT]
> Utilizzare i Vault chiave SKU Premium e le chiavi con protezione HSM per i dati di produzione e utilizzare solo i Vault e le chiavi standard SKU per il testing e la convalida.
  
Per ogni servizio Microsoft 365 con cui si utilizzerà la chiave del cliente, creare un Vault Key in ognuna delle due sottoscrizioni di Azure create. Ad esempio, per Exchange Online e Skype for business solo o SharePoint Online e OneDrive for business, si creerà solo una coppia di volte. Per abilitare la chiave del cliente per Exchange Online e SharePoint Online, è possibile creare due coppie di volte chiave.
  
Utilizzare una convenzione di denominazione per i Vault chiave che riflette l'utilizzo previsto dei criteri di crittografia dei dati con cui verranno associati i Vault. Vedere la sezione procedure consigliate di seguito per la denominazione dei consigli convenzioni.
  
Creare un set di volte separato e abbinato per ogni criterio di crittografia dei dati. Per Exchange Online, l'ambito di un criterio di crittografia dei dati viene scelto dall'utente quando si assegna il criterio alla cassetta postale. Una cassetta postale può avere un solo criterio assegnato ed è possibile creare fino a 50 criteri. Per SharePoint Online l'ambito di un criterio è costituito da tutti i dati all'interno di un'organizzazione in una posizione geografica o _Geo_.

La creazione di Vault chiave richiede anche la creazione di gruppi di risorse di Azure, poiché è necessario che la capacità di archiviazione (anche se molto piccola) e la registrazione Key Vault, se abilitata, generano anche dati archiviati. Come procedura consigliata, Microsoft consiglia di utilizzare amministratori distinti per gestire ogni gruppo di risorse, con l'amministrazione allineata al set di amministratori che gestirà tutte le risorse chiave dei clienti correlate.
  
> [!IMPORTANT]
> Per massimizzare la disponibilità, i Vault delle chiavi devono trovarsi nelle aree geografiche vicino al servizio Microsoft 365. Ad esempio, se l'organizzazione di Exchange Online è in Nord America, inserire i Vault chiave in Nord America. Se l'organizzazione di Exchange Online è in Europa, inserire i Vault chiave in Europa.
> 
> Utilizzare un prefisso comune per i Vault chiave e includere un'abbreviazione dell'utilizzo e dell'ambito del Vault Key e delle chiavi (ad esempio, per il servizio contoso SharePoint in cui si trovano i Vault in Nord America, una possibile coppia di nomi è contoso-O365SP-NA-VaultA1 e contoso-O365SP-NA-VaultA2. Il nome del Vault è una stringa univoca globale all'interno di Azure, quindi potrebbe essere necessario provare varianti dei nomi desiderati, nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. A luglio 2017 non è possibile modificare i nomi dei Vault, quindi è consigliabile disporre di un piano scritto per il programma di installazione e utilizzare una seconda persona per verificare che il piano sia stato eseguito correttamente.
> 
> Se possibile, creare i Vault in aree non accoppiate. Le aree di Azure con accoppiamento offrono disponibilità elevata tra i domini di errore del servizio. Di conseguenza, le coppie regionali possono essere pensate come area di backup dell'altro. Questo significa che una risorsa di Azure inserita in un'area geografica acquisisce automaticamente la tolleranza di errore tramite l'area associata. Per questo motivo, la scelta delle aree geografiche per due volte utilizzate in un criterio di crittografia dei dati in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle geografie ha solo due aree geografiche, quindi non è ancora possibile selezionare le aree non accoppiate. Se possibile, scegliere due aree non associate per i due Vault utilizzati con un criterio di crittografia dei dati. Questo beneficia di un totale di quattro aree di disponibilità. Per ulteriori informazioni, vedere [Business Continuity and Disaster Recovery (BCdR): aree con accoppiamento di Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente di coppie regionali.
  
### <a name="assign-permissions-to-each-key-vault"></a>Assegnare le autorizzazioni per ogni Vault chiave

Per ogni Vault chiave, sarà necessario definire tre Set distinti di autorizzazioni per la chiave del cliente, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori chiave del Vault** che eseguono la gestione quotidiana del Vault Key per l'organizzazione. Tali attività includono backup, creazione, recupero, importazione, elenco e ripristino.

  > [!IMPORTANT]
  > Il set di autorizzazioni assegnate agli amministratori delle chiavi del Vault non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una prassi intenzionale e importante. L'eliminazione delle chiavi di crittografia non è in genere completata, poiché tale operazione distrugge definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori delle chiavi del Vault per impostazione predefinita. Al contrario, è necessario riservare questo elemento ai collaboratori del Vault Key e assegnarlo solo a un amministratore a breve termine dopo aver compreso la comprensione delle conseguenze.
  
  Per assegnare queste autorizzazioni a un utente dell'organizzazione, eseguire l'accesso alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

- Eseguire il cmdlet Set-AzKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Ad esempio:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Key Vault Contributors** che possono modificare le autorizzazioni per il Vault Key di Azure stesso. È necessario modificare queste autorizzazioni quando i dipendenti lasciano o entrano in un team o in una situazione estremamente rara in cui gli amministratori delle Key Vault devono legittimamente disporre dell'autorizzazione per eliminare o ripristinare una chiave. Questo set di collaboratori chiave del Vault deve essere concesso al ruolo **collaboratore** nel Vault Key. È possibile assegnare questo ruolo tramite Gestione risorse di Azure. Per la procedura dettagliata, vedere [utilizzare Role-Based controllo di accesso per gestire l'accesso alle risorse di sottoscrizione di Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). L'amministratore che crea una sottoscrizione ha questo accesso in modo implicito, nonché la possibilità di assegnare altri amministratori al ruolo Collaboratore.

- Se si intende utilizzare la chiave del cliente con Exchange Online e Skype for business, è necessario concedere l'autorizzazione a Microsoft 365 per utilizzare il Vault Key per conto di Exchange Online e Skype for business. Analogamente, se si intende utilizzare Customer Key con SharePoint Online e OneDrive for business, è necessario aggiungere le autorizzazioni per Microsoft 365 per utilizzare il Vault Key per conto di SharePoint Online e OneDrive for business. Per concedere l'autorizzazione a Microsoft 365, eseguire il cmdlet **set-AzKeyVaultAccessPolicy** utilizzando la sintassi seguente: 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dove:

    - *nome del Vault* è il nome del Vault Key creato.

    - Per Exchange Online e Skype for business, Sostituisci  *Office 365 AppID* con `00000002-0000-0ff1-ce00-000000000000`

    - Per i file di SharePoint Online, OneDrive for business e teams, sostituire  *Office 365 AppID* con `00000003-0000-0ff1-ce00-000000000000`

  Esempio: impostazione delle autorizzazioni per Exchange Online e Skype for business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Esempio: impostazione delle autorizzazioni per i file di SharePoint Online, OneDrive for business e teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi

Quando è possibile recuperare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi accidentali o eliminate intenzionalmente. È necessario abilitare questa configurazione, denominata eliminazione temporanea, prima di poter utilizzare le chiavi con il codice "Customer Key". L'abilitazione dell'eliminazione temporanea consente di recuperare le chiavi o i Vault entro 90 giorni dall'eliminazione senza dover ripristinare il backup.
  
Per abilitare l'eliminazione temporanea nei Vault delle chiavi, eseguire la procedura seguente:
  
1. Accedere alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) . In questo esempio, il *nome del Vault* è il nome del Vault Key per il quale si desidera abilitare l'eliminazione morbida:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirm soft delete è configurato per il Vault Key tramite l'esecuzione del cmdlet **Get-AzKeyVault** . Se l'eliminazione morbida è configurata correttamente per il Vault chiave, la proprietà _soft delete Enabled_ restituisce il valore **true**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Aggiungere una chiave a ogni Vault chiave creando o importando una chiave

Esistono due modi per aggiungere chiavi a un Vault Key di Azure; è possibile creare una chiave direttamente in Key Vault oppure è possibile importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave fornisce il controllo totale sul modo in cui viene generata la chiave. È necessario utilizzare i tasti RSA. Il Vault Key di Azure non supporta il wrapping e lo scartamento con i tasti della curva ellittica.
  
Per creare una chiave direttamente nel Vault chiave, eseguire il cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) nel modo seguente:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dove:

- *nome del Vault* è il nome del Vault Key in cui si desidera creare la chiave.

- *nome chiave* è il nome che si desidera assegnare alla nuova chiave.

  > [!TIP]
  > Le chiavi dei nomi utilizzano una convenzione di denominazione simile, come descritto in alto per i Vault chiave. In questo modo, in strumenti che mostrano solo il nome della chiave, la stringa è autoesplicativa.
  
Se si intende proteggere la chiave con un HSM, accertarsi di specificare **HSM** come valore del parametro _Destination_ , in caso contrario, specificare il **software**.

Ad esempio,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Per importare una chiave direttamente nel Vault chiave, è necessario disporre di un modulo di sicurezza hardware di nCipher nShield.
  
Alcune organizzazioni preferiscono questo approccio per stabilire la provenienza delle chiavi e quindi questo metodo fornisce anche gli elementi seguenti:
  
- Il set di strumenti utilizzato per l'importazione include l'attestazione di nCipher che la chiave Key Exchange (KEK) utilizzata per crittografare la chiave che si genera non è esportabile e che viene generata all'interno di un HSM genuino prodotto da nCipher.

- Il set di strumenti include l'attestazione di nCipher che il World Key Vault di sicurezza di Azure è stato generato anche su un HSM genuino prodotto da nCipher. L'attestazione dimostra che Microsoft utilizza anche hardware nCipher genuino.

Verificare con il gruppo di sicurezza se sono necessarie le attestazioni sopra riportate. Per la procedura dettagliata per creare una chiave locale e importarla nel Vault chiave, vedere [How to generate and transfer HSM-protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Utilizzare le istruzioni di Azure per creare una chiave in ogni Vault Key.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi

Microsoft 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su non Annulla e che le chiavi utilizzate dal codice "Customer Key" siano abilitate per l'eliminazione temporanea. È possibile confermarlo esaminando il livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di una chiave, in Azure PowerShell, eseguire il cmdlet Get-AzKeyVaultKey come indicato di seguito:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se la proprietà del _livello di recupero_ restituisce un valore diverso da quello di **+ ProtectedSubscription**, sarà necessario esaminare questo articolo e assicurarsi di aver seguito tutti i passaggi necessari per inserire la sottoscrizione nell'elenco non annullare e di aver attivato l'eliminazione temporanea su ognuna delle volte chiave.
  
### <a name="back-up-azure-key-vault"></a>Backup del Vault delle chiavi di Azure

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Le copie offline non devono essere connesse a nessuna rete, ad esempio in una struttura di archiviazione sicura o commerciale fisica. Almeno una copia del backup deve essere archiviata in un percorso che sarà accessibile in caso di emergenza. Gli oggetti BLOB di backup sono gli unici strumenti per ripristinare il materiale chiave se una chiave del Vault Key deve essere definitivamente distrutta o altrimenti resa inutilizzabile. Le chiavi esterne all'archivio delle chiavi di Azure e sono state importate in Azure Key Vault non sono qualificate come backup poiché i metadati necessari per la chiave del cliente per l'utilizzo della chiave non sono presenti con la chiave esterna. È possibile utilizzare solo un backup da Vault Key di Azure per le operazioni di ripristino con il codice "Customer Key". Pertanto, è essenziale che un backup del Vault Key di Azure venga eseguito dopo il caricamento o la creazione di una chiave.
  
Per creare un backup di una chiave del Vault Key di Azure, eseguire il cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) come indicato di seguito:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verificare che il file di output utilizzi il suffisso `.backup` .
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno del Vault Key di Azure. Il backup può essere ripristinato solo per la sottoscrizione di Azure da cui è stato effettuato il backup.
  
> [!TIP]
> Per il file di output, scegliere una combinazione del nome del Vault e del nome della chiave. Questo renderà il nome di file autodescrittivo. Assicurerà inoltre che i nomi dei file di backup non entrino in collisione.
  
Ad esempio:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Convalidare le impostazioni di configurazione di Azure Key Vault

L'esecuzione della convalida prima di utilizzare le chiavi in una funzionalità DEP è facoltativa, ma è consigliabile. In particolare, se si utilizzano i passaggi necessari per configurare le chiavi e le volte diverse da quelle descritte in questo argomento, è consigliabile convalidare l'integrità delle risorse del Vault Key di Azure prima di configurare la chiave del cliente.
  
Per verificare che le chiavi dispongano delle operazioni get, wrapKey e unwrapKey attivate:
  
Eseguire il cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) nel modo seguente:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Nell'output, cercare il criterio di accesso e per l'identità di Exchange Online (GUID) o l'identità di SharePoint Online (GUID) in base alle esigenze. Tutte e tre le autorizzazioni sopra riportate devono essere visualizzate in autorizzazioni per le chiavi.
  
Se la configurazione del criterio di accesso non è corretta, eseguire il cmdlet Set-AzKeyVaultAccessPolicy come indicato di seguito:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Ad esempio, per Exchange Online e Skype for business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Ad esempio, per SharePoint Online e OneDrive for business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) come indicato di seguito:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Non è possibile utilizzare una chiave scaduta dalla chiave del cliente e le operazioni tentate con una chiave scaduta avranno esito negativo e, eventualmente, si verificherà un'interruzione del servizio. È consigliabile che i tasti utilizzati con la chiave del cliente non abbiano una data di scadenza. La data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con un set di date di scadenza, impostare il valore di scadenza su 12/31/9999. Le chiavi con una data di scadenza impostata su una data diversa da 12/31/9999 non superano la convalida di Microsoft 365.
  
Per modificare una data di scadenza impostata su un valore diverso da 12/31/9999, eseguire il cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) come indicato di seguito:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Non impostare le date di scadenza per le chiavi di crittografia utilizzate con la chiave del cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave del Vault Key di Azure

Dopo aver completato tutti i passaggi in Azure per configurare i Vault chiave e aver aggiunto le chiavi, eseguire il seguente comando per ottenere l'URI per la chiave in ogni Vault Key. Sarà necessario utilizzare questi URI quando si crea e si assegna ogni DEP in un secondo momento, quindi salvare queste informazioni in una posizione sicura. Ricordarsi di eseguire questo comando una volta per ogni Vault Key.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: impostazione della chiave del cliente per Exchange Online e Skype for business

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) .
  
Per impostare la chiave del cliente per Exchange Online e Skype for business, è necessario eseguire questa procedura per la connessione remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business

Un DEP è associato a un set di chiavi archiviate in Azure Key Vault. È possibile assegnare una DEP a una cassetta postale in Microsoft 365. Microsoft 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](#obtain-the-uri-for-each-azure-key-vault-key) .
  
Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare la funzionalità di protezione esecuzione programmi, eseguire la procedura seguente:
  
1. Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) in una finestra di Windows PowerShell.

2. Per creare una protezione esecuzione programmi, utilizzare il cmdlet New-DataEncryptionPolicy digitando il comando seguente.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dove:

   - *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.

   - *Descrizione dei criteri* è una descrizione facile da usare per i criteri che consentiranno di ricordare a cosa serve il criterio. È possibile includere spazi nella descrizione. Ad esempio, "chiave radice per le cassette postali negli Stati Uniti e nei suoi territori".

   - *KeyVaultURI1* è l'URI per la prima chiave del criterio. Ad esempio, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* è l'URI per la seconda chiave del criterio. Ad esempio, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separare i due URI da una virgola e uno spazio.

   Esempio:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Assegnare una DEP a una cassetta postale

Assegnare la funzionalità Protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Microsoft 365 è in grado di crittografare la cassetta postale con la chiave indicata nella DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailboxIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Per le [cassette postali locali che usano Outlook per iOS e Android con l'autenticazione moderna ibrida](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), i dati delle cassette postali locali sincronizzati nel tenant di Exchange Online possono essere assegnati tramite il cmdlet Set-MailUser.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailUserIdParameter* specifica un utente di posta elettronica (noto anche come utente abilitato alla posta elettronica). Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).
  
### <a name="validate-mailbox-encryption"></a>Convalidare la crittografia della cassetta postale

La crittografia di una cassetta postale può richiedere del tempo. Per l'assegnazione dei criteri per la prima volta, la cassetta postale deve anche passare completamente da un database all'altro prima che il servizio possa crittografare la cassetta postale. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.

Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui viene assegnata una DEP per la prima volta, oltre che dalle dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stata assegnata la funzionalità DEP, contattare Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: impostazione della chiave del cliente per i file di SharePoint Online, OneDrive for business e teams

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) .
  
Per impostare la chiave del cliente per i file di SharePoint Online, OneDrive for business e teams, è necessario eseguire questa procedura per la connessione remota a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business

È possibile associare una funzionalità DEP a un set di chiavi archiviate in Azure Key Vault. È possibile applicare una DEP a tutti i dati in una posizione geografica, denominata anche geo. Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo con la possibilità di utilizzare chiavi diverse per Geo. Se non si utilizza multi-Geo, è possibile creare una DEP nell'organizzazione per l'utilizzo con i file di SharePoint Online, OneDrive for business e teams. Microsoft 365 utilizza le chiavi identificate nella funzionalità DEP per crittografare i dati in tale Geo. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](#obtain-the-uri-for-each-azure-key-vault-key) .
  
Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare una funzionalità di protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online tramite Windows PowerShell.
  
1. Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true).

2. In Microsoft SharePoint Online Management Shell, eseguire il cmdlet Register-SPODataEncryptionPolicy come indicato di seguito:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Esempio:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Quando si registra la funzionalità DEP, la crittografia inizia sui dati del geografico. Questo può richiedere un certo tempo. Per ulteriori informazioni sull'utilizzo di questo parametro, vedere [Register-SPODataEncryptionPolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true).

### <a name="validate-file-encryption"></a>Convalidare la crittografia dei file

 Per convalidare la crittografia dei file di SharePoint Online, OneDrive for business e teams, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)e quindi utilizzare il cmdlet Get-SPODataEncryptionPolicy per controllare lo stato del tenant. La proprietà _state_ restituisce un valore **registrato** se la crittografia a chiave del cliente è abilitata e tutti i file in tutti i siti sono stati crittografati. Se la crittografia è ancora in corso, questo cmdlet fornisce informazioni su quale percentuale di siti è stata completata.

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Gestione della chiave del cliente](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Crittografia del servizio](office-365-service-encryption.md)
