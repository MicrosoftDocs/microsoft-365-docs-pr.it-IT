---
title: Chiave del cliente per Microsoft 365 a livello di tenant (anteprima pubblica)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Informazioni su come configurare la chiave del cliente per tutti i dati all'interno del tenant di Microsoft 365.
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712527"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Panoramica della chiave del cliente per Microsoft 365 a livello di tenant (anteprima pubblica)

Utilizzando i tasti forniti, è possibile creare un criterio di crittografia dei dati (DEP) e assegnarlo al tenant. La funzionalità DEP crittografa i dati nel tenant per i carichi di lavoro seguenti:

- Messaggi chat di Teams (1:1 chat, chat di gruppo, chat di riunioni e conversazioni di canale)
- Messaggi multimediali dei team (immagini, frammenti di codice, video, immagini wiki)
- Registrazioni di chiamate e riunioni di Team memorizzate nell'archivio di Teams
- Notifiche chat di Teams
- Suggerimenti per la chat in teams di Cortana
- Messaggi di stato dei team
- Informazioni sull'utente e sui segnali per Exchange Online

Per Microsoft teams, la chiave del cliente a livello di tenant crittografa i nuovi dati dal momento in cui la DEP è assegnata al tenant. L'anteprima pubblica non supporta la crittografia dei dati precedenti. Per Exchange Online, la chiave del cliente crittografa tutti i dati esistenti e nuovi.

È possibile creare più DEPs per tenant, ma può solo assegnare una DEP in qualsiasi momento. Quando si assegna la funzionalità DEP, la crittografia inizia automaticamente, ma può richiedere del tempo per il completamento, a seconda delle dimensioni del tenant.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>I criteri di livello tenant aggiungono un controllo più ampio alla chiave del cliente per Microsoft 365

Se è già stata configurata la chiave del cliente per Exchange Online e SharePoint Online, ecco come si inserisce la nuova anteprima pubblica a livello di tenant.

Il criterio di crittografia a livello di tenant creato consente di crittografare tutti i dati per i carichi di lavoro di Microsoft teams e Exchange online in Microsoft 365. Questo criterio non interferisce con il DEPs finemente sintonizzato che è stato già creato nella chiave del cliente.

Esempi:

I file di Microsoft teams e alcune registrazioni di chiamata e riunione di teams salvati in OneDrive for business e SharePoint vengono crittografati da una funzionalità di protezione dei dati di SharePoint Online. Una singola protezione esecuzione programmi di SharePoint Online crittografa i contenuti all'interno di un singolo Geo. La funzionalità DEP a livello di tenant eseguirà di nuovo la crittografia dei dati crittografati con il nuovo criterio.

Per Exchange Online, è possibile creare una DEP che crittografa una o più cassette postali utente con la chiave del cliente. Quando si crea un criterio a livello di tenant, tale criterio non crittografa le cassette postali crittografate. Tuttavia, la chiave a livello di tenant eseguirà la crittografia delle cassette postali che non sono già state intaccate da una DEP.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurare il codice "Customer Key" a livello di tenant (anteprima pubblica)

Questi passaggi sono simili ma non identici ai passaggi per l'impostazione della chiave del cliente a livello di applicazione. È consigliabile utilizzare questa anteprima pubblica solo con i dati dei test nei tenant di test. Non utilizzare questa versione con i dati di produzione o nell'ambiente di produzione. Se si dispone già di una distribuzione di Product Key per la produzione, attenersi alla procedura seguente per configurare il codice "Customer Key" a livello di tenant in un ambiente di testing.

La maggior parte di queste attività verrà completata tramite la connessione remota a Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.

Prima di iniziare, verificare quanto segue:

- È necessario utilizzare un account aziendale o dell'Istituto di istruzione che disponga del ruolo di amministratore della conformità per impostare la chiave del cliente a livello di tenant.
- Verificare di disporre delle licenze appropriate per l'organizzazione. Utilizzare una sottoscrizione a pagamento e fatturata di Azure utilizzando un contratto Enterprise o un provider di servizi cloud. Gli abbonamenti di Azure acquistati con pay as you go plans o con una carta di credito non sono supportati per la chiave del cliente. A partire dal 1 ° aprile 2020, la chiave del cliente in Office 365 è disponibile in Office 365 E5, M365 E5, M365 E5 compliance e M365 E5 Information Protection & SKU. Microsoft Office 365 Advanced Compliance SKU non è più disponibile per l'ottenimento di nuove licenze. Le licenze di conformità avanzate di Office 365 continueranno a essere supportate. Anche se il servizio può essere abilitato con un minimo di una licenza sotto il tenant avente la licenza appropriata, è comunque necessario verificare che tutti gli utenti che usufruiscono del servizio dispongano di licenze appropriate. È necessaria una delle licenze seguenti:

### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure

La chiave del cliente richiede due chiavi per ogni criterio di crittografia dei dati. Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri distinti dell'organizzazione che configurano una chiave in ogni sottoscrizione. Utilizzare solo queste sottoscrizioni di Azure per amministrare le chiavi di crittografia per Microsoft 365. Questo consente di proteggere l'organizzazione nel caso in cui uno degli operatori involontariamente, intenzionalmente o elimini in modo doloso o meno le chiavi per le quali sono responsabili.

Non esiste alcun limite pratico per il numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. La procedura consigliata consente di ridurre al minimo l'impatto dell'errore umano contribuendo alla gestione delle risorse utilizzate dalla chiave del cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio

La perdita temporanea o permanente delle chiavi di crittografia radice può essere un'operazione di disturbo o addirittura catastrofica per il servizio e può provocare la perdita di dati. Per questo motivo, le risorse utilizzate con la chiave del cliente richiedono una protezione sicura. Tutte le risorse di Azure utilizzate con la chiave del cliente offrono meccanismi di protezione oltre la configurazione predefinita. Le sottoscrizioni di Azure possono essere contrassegnate o registrate in un modo che impedirà l'annullamento immediato e irrevocabile. Si tratta della registrazione di un periodo di conservazione obbligatorio. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con Microsoft. Questo processo può richiedere fino a cinque giorni lavorativi. In precedenza, questo è stato talvolta definito come "non annullare".
  
Prima di contattare il team di Microsoft 365, è necessario eseguire i passaggi seguenti per ogni sottoscrizione di Azure utilizzata con la chiave del cliente. Prima di iniziare, assicurarsi di avere installato il modulo di [Azure PowerShell AZ](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) .

1. Accedere con PowerShell di Azure. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Register-AzProviderFeature per registrare gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio. Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contattare Microsoft per eseguire il processo di completamento in [m365ck@microsoft.com](mailto:m365ck@microsoft.com). Includere quanto segue nel messaggio di posta elettronica:

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

Utilizzare un prefisso comune per i Vault chiave e includere un'abbreviazione dell'utilizzo e dell'ambito del Vault chiave e delle chiavi. Ad esempio, per il servizio Contoso in cui si trovano i Vault in Nord America, una possibile coppia di nomi è contoso-O365-NA-VaultA1 e contoso-O365-NA-VaultA2. Il nome del Vault è una stringa univoca globale all'interno di Azure, quindi potrebbe essere necessario provare varianti dei nomi desiderati, nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. Una volta configurati, i nomi dei Vault non possono essere modificati, quindi la procedura consigliata consiste nell'avere un piano scritto per l'installazione e utilizzare una seconda persona per verificare che il piano sia stato eseguito correttamente.

Se possibile, creare i Vault in aree non accoppiate. Le aree di Azure con accoppiamento offrono disponibilità elevata tra i domini di errore del servizio. Di conseguenza, le coppie regionali possono essere pensate come area di backup dell'altro. Questo significa che una risorsa di Azure inserita in un'area geografica acquisisce automaticamente la tolleranza di errore tramite l'area associata. Per questo motivo, la scelta delle aree geografiche per due volte utilizzate in un criterio di crittografia dei dati in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle geografie ha solo due aree geografiche, quindi non è ancora possibile selezionare le aree non accoppiate. Se possibile, scegliere due aree non associate per i due Vault utilizzati con un criterio di crittografia dei dati. Questo beneficia di un totale di quattro aree di disponibilità. Per ulteriori informazioni, vedere [Business Continuity and Disaster Recovery (BCdR): aree con accoppiamento di Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente di coppie regionali.

### <a name="assign-permissions-to-each-key-vault"></a>Assegnare le autorizzazioni per ogni Vault chiave

Per ogni Vault chiave, sarà necessario definire tre Set distinti di autorizzazioni per la chiave del cliente, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori chiave del Vault** che eseguono la gestione quotidiana del Vault Key per l'organizzazione. Tali attività includono backup, creazione, recupero, importazione, elenco e ripristino.

  > [!IMPORTANT]
  > Il set di autorizzazioni assegnate agli amministratori delle chiavi del Vault non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una prassi intenzionale e importante. L'eliminazione delle chiavi di crittografia non è in genere completata, poiché tale operazione distrugge definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori delle chiavi del Vault per impostazione predefinita. Al contrario, è necessario riservare questo elemento ai collaboratori del Vault Key e assegnarlo solo a un amministratore a breve termine dopo aver compreso la comprensione delle conseguenze.
  
  Per assegnare queste autorizzazioni a un utente dell'organizzazione, eseguire l'accesso alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Eseguire il cmdlet Set-AzKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Ad esempio:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Key Vault Contributors** che possono modificare le autorizzazioni per il Vault Key di Azure stesso. È necessario modificare queste autorizzazioni quando i dipendenti lasciano o entrano in un team o in una situazione rara in cui gli amministratori delle Key Vault devono legittimamente disporre dell'autorizzazione necessaria per eliminare o ripristinare una chiave. Questo set di collaboratori chiave del Vault deve essere concesso al ruolo Collaboratore nel Vault Key. È possibile assegnare questo ruolo tramite Gestione risorse di Azure. Per la procedura dettagliata, vedere [utilizzare Role-Based controllo di accesso](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) per gestire l'accesso alle risorse di sottoscrizione di Azure. L'amministratore che crea una sottoscrizione ha questo accesso per impostazione predefinita e la possibilità di assegnare altri amministratori al ruolo Collaboratore.

- **Microsoft 365 data at rest Encryption Service** che esegue il lavoro della chiave del cliente a livello di tenant. Per concedere l'autorizzazione a Microsoft 365, eseguire il cmdlet **set-AzKeyVaultAccessPolicy** utilizzando la sintassi seguente:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Dove:

  - *nome del Vault* è il nome del Vault Key creato.

  Esempio: per il servizio Microsoft 365 data at rest Encryption, sostituire  *microsoft 365 AppID* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi

Quando è possibile recuperare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi accidentali o eliminate intenzionalmente. Abilitare questa configurazione, denominata eliminazione temporanea, prima di poter utilizzare le chiavi con il codice "Customer Key". L'abilitazione dell'eliminazione temporanea consente di recuperare le chiavi o i Vault entro 90 giorni dall'eliminazione senza dover ripristinare il backup.
  
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

Esistono due modi per aggiungere chiavi a un Vault Key di Azure; è possibile creare una chiave direttamente in Key Vault oppure è possibile importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave fornisce il controllo totale sul modo in cui viene generata la chiave. Utilizzare le chiavi RSA. Il Vault Key di Azure non supporta il wrapping e lo scartamento con i tasti della curva ellittica.
  
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

### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi

Microsoft 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su non Annulla e che le chiavi utilizzate dal codice "Customer Key" siano abilitate per l'eliminazione temporanea. È possibile confermarlo esaminando il livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di una chiave, in Azure PowerShell, eseguire il cmdlet Get-AzKeyVaultKey come indicato di seguito:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se la proprietà del _livello di recupero_ restituisce un valore diverso da quello di **+ ProtectedSubscription**, sarà necessario esaminare questo articolo e assicurarsi di aver seguito tutti i passaggi per inserire la sottoscrizione nell'elenco non annullare e che sia stata abilitata "eliminazione temporanea" in ciascuna delle volte chiave. Successivamente, inviare una schermata dell'output di `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` nella posta elettronica a m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Backup del Vault delle chiavi di Azure

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Non connettere le copie offline a qualsiasi rete. In alternativa, archiviarli in una struttura di archiviazione sicura o commerciale fisica. Almeno una copia del backup deve essere archiviata in una posizione che sarà accessibile se si verifica un errore. Gli oggetti BLOB di backup sono gli unici strumenti per ripristinare il materiale chiave se una chiave del Vault Key deve essere definitivamente distrutta o altrimenti resa inutilizzabile. Le chiavi esterne all'archivio delle chiavi di Azure e sono state importate in Azure Key Vault non sono qualificate come backup poiché i metadati necessari per la chiave del cliente per l'utilizzo della chiave non sono presenti con la chiave esterna. È possibile utilizzare solo un backup da Vault Key di Azure per le operazioni di ripristino con il codice "Customer Key". Pertanto, è essenziale creare una copia di backup del Vault Key di Azure dopo che un tasto è stato caricato o creato.
  
Per creare un backup di una chiave del Vault Key di Azure, eseguire il cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) come indicato di seguito:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verificare che il file di output utilizzi il suffisso `.backup` .
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno del Vault Key di Azure. Il backup può essere ripristinato solo per la sottoscrizione di Azure da cui è stato effettuato il backup.
  
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

Nell'output, cercare il criterio di accesso e per l'ID app Microsoft 365 (GUID) in base alle esigenze. Tutte e tre le operazioni, Get, wrapKey e unwrapKey, devono essere visualizzate in autorizzazioni per le chiavi.
  
Se la configurazione del criterio di accesso non è corretta, eseguire il cmdlet Set-AzKeyVaultAccessPolicy come indicato di seguito:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Esempio: per il servizio Microsoft 365 data at rest Encryption, sostituire  *microsoft 365 AppID* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) come indicato di seguito:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Non è possibile utilizzare una chiave scaduta dalla chiave del cliente e le operazioni tentate con una chiave scaduta avranno esito negativo e potrebbero provocare un'interruzione del servizio. È consigliabile che i tasti utilizzati con la chiave del cliente non abbiano una data di scadenza. La data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con un set di date di scadenza, impostare il valore di scadenza su 12/31/9999. Le chiavi con una data di scadenza impostata su una data diversa da 12/31/9999 non superano la convalida di Microsoft 365.
  
Per modificare una data di scadenza impostata su un valore diverso da 12/31/9999, eseguire il cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) come indicato di seguito:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave del Vault Key di Azure

Dopo aver completato tutti i passaggi in Azure per configurare i Vault chiave e aver aggiunto le chiavi, eseguire il seguente comando per ottenere l'URI per la chiave in ogni Vault Key. Sarà necessario utilizzare questi URI quando si crea e si assegna ogni DEP in un secondo momento, quindi salvare queste informazioni in una posizione sicura. Ricordarsi di eseguire questo comando una volta per ogni Vault Key.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Impostare i criteri di crittografia per il proprietario del tenant

Prima di poter eseguire questi cmdlet, è necessario disporre delle autorizzazioni assegnate. Anche se in questo articolo vengono elencati tutti i parametri per i cmdlet, potrebbe non essere possibile accedere ad alcuni parametri se non sono inclusi nelle autorizzazioni assegnate all'utente. Per individuare le autorizzazioni necessarie per eseguire cmdlet o parametri nell'organizzazione, vedere [Trovare le autorizzazioni necessarie per eseguire i cmdlet di Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Creare criteri

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Descrizione: abilitare l'amministratore della conformità per creare un nuovo criterio di crittografia dei dati (DEP, Data Encryption Policy) utilizzando due chiavi radice di AKV. Una volta creato, è possibile assegnare un criterio utilizzando Set-M365DataAtRestEncryptionPolicy cmdlet. Dopo aver eseguito la prima assegnazione delle chiavi o dopo aver ruotato le chiavi, possono essere necessarie fino a 24 ore per rendere effettive le nuove chiavi. Se il nuovo DEP impiega più di 24 ore per rendere effettive le proprie funzionalità, contattare Microsoft.

Esempio:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parametri

| Nome | Descrizione | Facoltativo (s/N) |
|--|--|--|
|Nome|Nome descrittivo dei criteri di crittografia dei dati|N|
|AzureKeyIDs|Specifica due valori URI delle chiavi del Vault Key di Azure, separate da una virgola, da associare al criterio di crittografia dei dati|N|
|Descrizione|Descrizione dei criteri di crittografia dei dati|N|

### <a name="assign-policy"></a>Assegnare un criterio

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Descrizione: questo cmdlet viene utilizzato per configurare i criteri di crittografia dei dati predefiniti. Questo criterio verrà utilizzato per crittografare i dati in tutti i carichi di lavoro di supporto. 

Esempio:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parametri
| Nome | Descrizione | Facoltativo (s/N) |
|--|--|--|
-Policy|Specifica il criterio di crittografia dei dati che deve essere assegnato; specificare il nome del criterio o l'ID del criterio.|N|

### <a name="modify-or-refresh-policy"></a>Modificare o aggiornare i criteri

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descrizione: il cmdlet può essere utilizzato per modificare o aggiornare un criterio esistente. Può anche essere utilizzato per abilitare o disabilitare un criterio. Dopo aver eseguito la prima assegnazione delle chiavi o dopo aver ruotato le chiavi, possono essere necessarie fino a 24 ore per rendere effettive le nuove chiavi. Se il nuovo DEP impiega più di 24 ore per rendere effettive le proprie funzionalità, contattare Microsoft.

Esempi:

Disabilitare un criterio di crittografia dei dati.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Aggiornare un criterio di crittografia dei dati.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parametri
| Nome | Descrizione | Facoltativo (s/N) |
|--|--|--|
|-Identity|Specifica il criterio di crittografia dei dati che si desidera modificare.|N|
|-Aggiorna|Utilizzare l'opzione Aggiorna per aggiornare i criteri di crittografia dei dati dopo aver ruotato una delle chiavi associate nel Vault Key di Azure. Con questa opzione non è necessario specificare alcun valore.|Y|
|-Enabled|Il parametro Enabled consente di abilitare o disabilitare il criterio di crittografia dei dati. Prima di disabilitare un criterio, è necessario annullare l'assegnazione dal tenant. I valori validi sono:</br > $true: il criterio è abilitato</br > $true: il criterio è abilitato. Questo è il valore predefinito.
|Y|
|-Nome|Il parametro Name specifica il nome univoco del criterio di crittografia dei dati.|Y
|-Descrizione|Il parametro Description specifica una descrizione facoltativa del criterio di crittografia dei dati.|Y|

### <a name="get-policy-details"></a>Ottenere informazioni dettagliate sui criteri

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descrizione: questo cmdlet elenca tutti i criteri di crittografia di M365DataAtRest creati per il tenant o i dettagli relativi a un criterio specifico.

Esempi:

In questo esempio viene restituito un elenco riepilogativo dei criteri di crittografia di M365DatAtRest nell'organizzazione.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

In questo esempio vengono restituite informazioni dettagliate per il criterio di crittografia dei dati denominato "NAM Policy".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parametri

| Nome | Descrizione | Facoltativo (s/N) |
|--|--|--|
|-Identity|Specifica il criterio di crittografia dei dati per cui si desidera elencare i dettagli.|Y|

### <a name="get-policy-assignment-info"></a>Ottenere informazioni sull'assegnazione dei criteri

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descrizione: questo cmdlet elenca il criterio attualmente assegnato al tenant.

## <a name="offboarding-from-customer-key"></a>Offboarding dalla chiave del cliente

Se è necessario ripristinare le chiavi gestite da Microsoft, è possibile. Quando si trasferisce, i dati vengono crittografati di nuovo utilizzando la crittografia predefinita supportata da ogni singolo carico di lavoro. Ad esempio, Exchange Online supporta la crittografia predefinita utilizzando le chiavi gestite da Microsoft.

Se si decide di trasferisce il tenant dalla chiave del cliente a livello di tenant, contattare Microsoft con una richiesta tramite posta elettronica per disabilitare il servizio per il tenant di [m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> Offboarding non è lo stesso di un'eliminazione dei dati. Un data Purge permanentemente Crypto-Elimina i dati dell'organizzazione da Microsoft 365, offboarding. Non è possibile eseguire un'eliminazione dei dati per un criterio a livello di tenant. Per informazioni sul percorso di eliminazione dei dati, vedere [revocare le chiavi e avviare il processo di percorso di eliminazione dei dati](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

## <a name="about-the-availability-key"></a>Informazioni sul tasto disponibilità

Per informazioni sulla chiave di disponibilità, vedere [Learn about the availability Key](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Rotazione tasti

Per informazioni sulle chiavi rotanti o rotolanti utilizzate con la chiave del cliente, vedere [Roll or rotate a Customer Key o a availability Key](customer-key-availability-key-roll.md). Quando si aggiorna la funzionalità DEP per utilizzare la nuova versione delle chiavi, è possibile eseguire il cmdlet Set-M365DataAtRestEncryptionPolicy come descritto in precedenza in questo articolo.

## <a name="related-articles"></a>Articoli correlati:

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Crittografia del servizio](office-365-service-encryption.md)
