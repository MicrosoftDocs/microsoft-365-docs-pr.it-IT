---
title: Customer Key per Microsoft 365 a livello di tenant (anteprima pubblica)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
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
description: Informazioni su come configurare customer key per tutti i dati all'interno del tenant di Microsoft 365.
ms.openlocfilehash: 2fed4730e79f6e2ace827eab338bf9da8fe55260
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838241"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Panoramica del codice "Customer Key" per Microsoft 365 a livello di tenant (anteprima pubblica)

Usando le chiavi fornite, è possibile creare un criterio di crittografia dei dati e assegnarlo al tenant. Protezione esecuzione programmi crittografa i dati nel tenant per questi carichi di lavoro:

- Messaggi di chat di Teams (chat 1:1, chat di gruppo, chat di riunioni e conversazioni di canale)
- Messaggi multimediali di Teams (immagini, frammenti di codice, messaggi video, messaggi audio, immagini wiki)
- Registrazioni delle chiamate e delle riunioni di Teams archiviate nello spazio di archiviazione di Teams
- Notifiche chat di Teams
- Suggerimenti di chat di Teams da Cortana
- Messaggi di stato di Teams
- Informazioni su utenti e segnali per Exchange Online
- Cassette postali di Exchange Online che non sono già crittografate DEP chiave cliente a livello di applicazione

Per Microsoft Teams, customer key a livello di tenant crittografa i nuovi dati dal momento in cui la protezione esecuzione programmi viene assegnata al tenant. L'anteprima pubblica non supporta la crittografia dei dati passati. Per Exchange Online, customer key crittografa tutti i dati esistenti e nuovi.

È possibile creare più criteri di protezione esecuzione per tenant, ma è possibile assegnare una sola protezione esecuzione programmi in qualsiasi momento. Quando si assegna Protezione esecuzione programmi, la crittografia inizia automaticamente, ma può richiedere del tempo a seconda delle dimensioni del tenant.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>I criteri a livello di tenant aggiungono un controllo più ampio a Customer Key per Microsoft 365

Se è già stata impostata la chiave cliente per Exchange Online e Sharepoint Online, ecco come si inserisce la nuova anteprima pubblica a livello di tenant.

Il criterio di crittografia a livello di tenant creato crittografa tutti i dati per i carichi di lavoro di Microsoft Teams ed Exchange Online in Microsoft 365. Tuttavia, per Exchange Online, se sono già stati assegnati DEP chiave cliente a singole cassette postali, i criteri a livello di tenant non sovrascrivono tali CRITERI. Il criterio a livello di tenant crittograferà solo le cassette postali a cui non è già assegnata una protezione esecuzione programmi chiave cliente a livello di cassetta postale.

Ad esempio, i file di Microsoft Teams e alcune registrazioni di chiamate e riunioni di Teams salvate in OneDrive for Business e SharePoint vengono crittografate da una protezione esecuzione programmi di SharePoint Online. Una singola funzionalità Protezione esecuzione programmi di SharePoint Online crittografa il contenuto all'interno di un'unica area geografica.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurare customer key a livello di tenant (anteprima pubblica)

Questi passaggi sono simili ma non identici a quelli per la configurazione del codice "Customer Key" a livello di applicazione. È consigliabile usare questa anteprima pubblica solo con i dati di test nei tenant di test. Non usare questa versione con i dati di produzione o nell'ambiente di produzione. Se si dispone già di una distribuzione di produzione di Customer Key, eseguire questi passaggi per configurare customer key a livello di tenant in un ambiente di testing. Dopo aver assegnato una protezione esecuzione programmi a livello di tenant al tenant, è possibile avviare il processo di convalida e contattare m365ck@microsoft.com con domande o dubbi. È inoltre possibile trovare i passaggi di convalida documentati nell'anteprima pubblica di Istruzioni di convalida per la crittografia in stato di [in-rest per Microsoft 365.](https://aka.ms/CustomerKey/PublicPreviewValidation)

La maggior parte di queste attività verrà completata connettendosi in remoto ad Azure PowerShell. Per ottenere risultati ottimali, usare la versione 4.4.0 o successiva di Azure PowerShell.

Prima di iniziare, verificare quanto segue:

- Dovrai usare un account aziendale o dell'istituto di istruzione con il ruolo di amministratore della conformità per configurare il codice "Customer Key" a livello di tenant.
- Assicurarsi di disporre delle licenze appropriate per l'organizzazione. Usa una sottoscrizione di Azure a pagamento e fatturata usando un Contratto Enterprise o un provider di servizi cloud. Le sottoscrizioni di Azure acquistate con i piani Pay As You Go o con una carta di credito non sono supportate per customer key. A partire dal 1° aprile 2020, customer key in Office 365 è disponibile in Office 365 E5, M365 E5, M365 E5 Compliance e M365 E5 Information Protection & Governance SKU. Office 365 Advanced Compliance SKU non è più disponibile per la procura di nuove licenze. Le licenze esistenti di Office 365 Advanced Compliance continueranno a essere supportate. Anche se il servizio può essere abilitato con almeno una licenza nel tenant con la licenza appropriata, è comunque consigliabile assicurarsi che tutti gli utenti che beneficiano del servizio siano in grado di disporre di licenze appropriate.

### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure

Customer Key richiede due chiavi per ogni criterio di crittografia dei dati (DEP). A tale scopo, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri separati dell'organizzazione per configurare una chiave in ogni sottoscrizione. Usare queste sottoscrizioni di Azure solo per amministrare le chiavi di crittografia per Microsoft 365. Questo protegge l'organizzazione nel caso in cui uno degli operatori elimini accidentalmente, intenzionalmente o in modo dannoso o in altro modo maneggio le chiavi di cui sono responsabili.

Non esiste un limite pratico al numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguire questa procedura consigliata consente di ridurre al minimo l'impatto dell'errore umano e allo stesso tempo di gestire le risorse utilizzate da Customer Key.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per usare un periodo di conservazione obbligatorio

La perdita temporanea o permanente delle chiavi di crittografia radice può essere dannosa o addirittura catastrofica per il funzionamento del servizio e può causare la perdita di dati. Per questo motivo, le risorse utilizzate con Customer Key richiedono una protezione avanzata. Tutte le risorse di Azure usate con Customer Key offrono meccanismi di protezione oltre la configurazione predefinita. Le sottoscrizioni di Azure possono essere contrassegnate o registrate in modo da impedire l'annullamento immediato e irrevocabile. Questa operazione viene definita registrazione per un periodo di conservazione obbligatorio. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con Microsoft. Questo processo può richiedere fino a cinque giorni lavorativi. In precedenza, a volte questo è stato definito "Non annullare".
  
Prima di contattare il team di Microsoft 365, è necessario eseguire la procedura seguente per ogni sottoscrizione di Azure che si usa con customer key. Prima di iniziare, assicurati di avere installato il modulo Az di [Azure PowerShell.](https://docs.microsoft.com/powershell/azure/new-azureps-module-az)

1. Accedi con Azure PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Register-AzProviderFeature per registrare le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio. Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contattare Microsoft per completare il processo [m365ck@microsoft.com](mailto:m365ck@microsoft.com). Includere quanto segue nel messaggio di posta elettronica:

   **Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\>

   **Corpo**: ID sottoscrizione per cui si desidera finalizzare il periodo di conservazione obbligatorio.
   Output del Get-AzProviderFeature per ogni sottoscrizione.

   Il Contratto di servizio (SLA) per il completamento di questo processo è di cinque giorni lavorativi dopo che Microsoft ha notificato (e verificato) di aver registrato le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio.

4. Una volta ricevuta la notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il comando Get-AzProviderFeature come indicato di seguito. Se verificato, il comando Get-AzProviderFeature restituisce il valore **Registered** per la **proprietà Registration State.** Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Per completare il processo, eseguire il Register-AzResourceProvider comando. Eseguire questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un azure key vault premium in ogni sottoscrizione

I passaggi per creare un insieme di credenziali delle chiavi sono documentati in Introduzione a [Azure Key Vault,](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)che consente di installare e avviare Azure PowerShell, connettersi alla sottoscrizione di Azure, creare un gruppo di risorse e creare un insieme di credenziali delle chiavi in tale gruppo di risorse.
  
Quando si crea un insieme di credenziali delle chiavi, è necessario scegliere una SKU: Standard o Premium. Lo SKU standard consente di proteggere le chiavi dell'insieme di credenziali delle chiavi di Azure con il software - non esiste alcuna protezione delle chiavi HSM (Hardware Security Module) - e lo SKU Premium consente l'uso di HMS per la protezione delle chiavi dell'insieme di credenziali delle chiavi. Customer Key accetta gli insiemi di credenziali delle chiavi che usano una delle due SKU, anche se Microsoft consiglia vivamente di usare solo la SKU Premium. Il costo delle operazioni con chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo mensile per ogni chiave protetta da HSM. Per [informazioni dettagliate, vedere Key Vault pricing.](https://azure.microsoft.com/pricing/details/key-vault/)
  
> [!IMPORTANT]
> Usa gli insiemi di credenziali delle chiavi SKU Premium e le chiavi protette con HSM per i dati di produzione e usa solo gli insiemi di credenziali e le chiavi SKU standard a scopo di test e convalida.

Usa un prefisso comune per gli insiemi di credenziali delle chiavi e includi un'abbreviazione dell'uso e dell'ambito dell'insieme di credenziali delle chiavi e delle chiavi. Ad esempio, per il servizio Contoso in cui si trovano gli insiemi di credenziali in Nord America, una possibile coppia di nomi è Contoso-O365-NA-VaultA1 e Contoso-O365-NA-VaultA2. I nomi degli insiemi di credenziali sono stringhe univoche a livello globale in Azure, quindi potrebbe essere necessario provare le varianti dei nomi desiderati nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. Una volta configurati, i nomi dell'insieme di credenziali non possono essere modificati, quindi la procedura consigliata consiste nell'avere un piano scritto per la configurazione e utilizzare una seconda persona per verificare che il piano venga eseguito correttamente.

Se possibile, creare gli insiemi di credenziali in aree non abbinate. Le aree di Azure abbinate offrono disponibilità elevata tra i domini di errore del servizio. Pertanto, le coppie regionali possono essere ritenute come l'area di backup reciproca. Ciò significa che una risorsa di Azure posizionata in un'area ottiene automaticamente la tolleranza di errore attraverso l'area associata. Per questo motivo, la scelta delle aree per due insiemi di credenziali utilizzati in un criterio di crittografia dei dati in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle aree geografiche ha solo due aree, quindi non è ancora possibile selezionare aree non abbinate. Se possibile, scegliere due aree non associate per i due insiemi di credenziali utilizzati con un criterio di crittografia dei dati. Ciò trae vantaggio da un totale di quattro aree di disponibilità. Per altre informazioni, vedere Continuità aziendale e ripristino di emergenza [(BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) Azure Paired Regions per un elenco corrente di coppie regionali.

### <a name="assign-permissions-to-each-key-vault"></a>Assegnare autorizzazioni a ogni insieme di credenziali delle chiavi

Per ogni insieme di credenziali delle chiavi, dovrai definire tre set separati di autorizzazioni per Customer Key, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori dell'insieme di** credenziali delle chiavi che eseguiranno la gestione quotidiana dell'insieme di credenziali delle chiavi per l'organizzazione. Queste attività includono il backup, la creazione, il ripristino, l'importazione, l'elenco e il ripristino.

  > [!IMPORTANT]
  > Il set di autorizzazioni assegnate agli amministratori dell'insieme di credenziali delle chiavi non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una pratica intenzionale e importante. L'eliminazione delle chiavi di crittografia in genere non viene eseguita, poiché in questo modo vengono eliminati definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori dell'insieme di credenziali delle chiavi per impostazione predefinita. Al contrario, riservare questo valore ai collaboratori dell'insieme di credenziali chiave e assegnarlo a un amministratore solo a breve termine, una volta compresa una chiara comprensione delle conseguenze.
  
  Per assegnare queste autorizzazioni a un utente dell'organizzazione, accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Eseguire il cmdlet Set-AzKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Ad esempio:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Collaboratori dell'insieme di** credenziali delle chiavi che possono modificare le autorizzazioni nell'insieme di credenziali delle chiavi di Azure stesso. È necessario modificare queste autorizzazioni quando i dipendenti lasciano o si uniscono al team o nella rara situazione in cui gli amministratori dell'insieme di credenziali delle chiavi hanno legittimamente bisogno dell'autorizzazione per eliminare o ripristinare una chiave. A questo set di collaboratori dell'insieme di credenziali chiave deve essere concesso il ruolo Collaboratore nell'insieme di credenziali delle chiavi. Puoi assegnare questo ruolo usando Azure Resource Manager. Per la procedura dettagliata, vedere [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources. L'amministratore che crea una sottoscrizione ha questo accesso per impostazione predefinita e la possibilità di assegnare altri amministratori al ruolo Collaboratore.

- Servizio di crittografia dei dati in pausa di **Microsoft 365** che esegue il lavoro del codice "Customer Key" a livello di tenant. Per concedere l'autorizzazione a Microsoft 365, eseguire il cmdlet **Set-AzKeyVaultAccessPolicy** utilizzando la sintassi seguente:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Dove:

  - *nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi creato.

  Esempio: per il servizio Di crittografia dati in pausa di Microsoft 365, sostituire  *AppID di Microsoft 365* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare e quindi confermare l'eliminazione recidiva degli insiemi di credenziali delle chiavi

Quando è possibile ripristinare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi eliminate accidentalmente o in modo dannoso. Abilita questa configurazione, definita eliminazione soft, prima di poter usare le chiavi con Customer Key. L'abilitazione dell'eliminazione soft consente di ripristinare chiavi o insiemi di credenziali entro 90 giorni dall'eliminazione senza doverle ripristinare dal backup.
  
Per abilitare l'eliminazione soft nei vault delle chiavi, completare la procedura seguente:
  
1. Accedi alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet [Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) In questo esempio, *il nome dell'insieme di* credenziali è il nome dell'insieme di credenziali delle chiavi per cui si sta abilitando l'eliminazione recidiva:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Verificare che l'eliminazione soft sia configurata per l'insieme di credenziali delle chiavi eseguendo il cmdlet **Get-AzKeyVault.** Se l'eliminazione soft è configurata correttamente per l'insieme di credenziali delle chiavi, la proprietà _Soft Delete Enabled_ restituisce il valore **True**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Aggiungere una chiave a ogni insieme di credenziali delle chiavi creando o importando una chiave

Esistono due modi per aggiungere chiavi a un insieme di credenziali delle chiavi di Azure; è possibile creare una chiave direttamente in Key Vault oppure importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave offre un controllo totale sulla modalità di generazione della chiave. Usa le chiavi RSA. Azure Key Vault non supporta il ritorno a capo e l'annullamento del wrapping con chiavi di curva ellittiche.
  
Per creare una chiave direttamente nell'insieme di credenziali delle chiavi, eseguire il cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) come segue:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dove:

- *nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi in cui si desidera creare la chiave.

- *key name* è il nome che si desidera assegnare alla nuova chiave.

  > [!TIP]
  > Assegnare nomi alle chiavi usando una convenzione di denominazione simile a quella descritta in precedenza per gli insiemi di credenziali delle chiavi. In questo modo, negli strumenti che mostrano solo il nome della chiave, la stringa è autodescrittura.
  
Se si intende proteggere la chiave con un HSM, assicurarsi di specificare **HSM** come valore del _parametro Destination,_ altrimenti specificare **Software**.

Ad esempio,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi

Microsoft 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su Do Not Cancel e che le chiavi usate da Customer Key hanno l'eliminazione soft abilitata. Puoi confermarlo esaminando il livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di una chiave, in Azure PowerShell eseguire il cmdlet Get-AzKeyVaultKey come indicato di seguito:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se la proprietà _Recovery Level_ restituisce un valore diverso da **Recoverable+ProtectedSubscription,** sarà necessario leggere questo articolo e assicurarsi di aver seguito tutti i passaggi per inserire la sottoscrizione nell'elenco Non annullare e di aver abilitato l'eliminazione reversibile in ognuno degli insiemi di credenziali delle chiavi. Successivamente, inviare uno screenshot dell'output `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` di nella posta elettronica a m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Eseguire il backup di Azure Key Vault

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Non connettere copie offline ad alcuna rete. Archiviarli invece in una struttura di archiviazione fisica sicura o commerciale. Almeno una copia del backup deve essere archiviata in un percorso accessibile in caso di emergenza. I BLOB di backup sono l'unico mezzo per ripristinare il materiale delle chiavi nel caso in cui una chiave dell'insieme di credenziali delle chiavi sia definitivamente distrutta o altrimenti resa inoperabile. Le chiavi esterne all'insieme di credenziali delle chiavi di Azure e che sono state importate in Azure Key Vault non sono idonee come backup perché i metadati necessari per l'uso della chiave da parte del cliente non esistono con la chiave esterna. Solo un backup eseguito da Azure Key Vault può essere usato per le operazioni di ripristino con Customer Key. Pertanto, è essenziale eseguire un backup di Azure Key Vault dopo aver caricato o creato una chiave.
  
Per creare un backup di una chiave di Azure Key Vault, eseguire il cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) come segue:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verificare che il file di output utilizzi il suffisso `.backup` .
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno di Azure Key Vault. Il backup può essere ripristinato solo nella sottoscrizione di Azure da cui è stato eseguito il backup.
  
Ad esempio:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Convalidare le impostazioni di configurazione di Azure Key Vault

L'esecuzione della convalida prima di utilizzare le chiavi in una protezione esecuzione programmi è facoltativa, ma è consigliabile. In particolare, se usi la procedura per configurare le chiavi e gli insiemi di credenziali diversi da quelli descritti in questo argomento, devi convalidare l'integrità delle risorse di Azure Key Vault prima di configurare Customer Key.
  
Per verificare che le chiavi siano abilitate per le operazioni get, wrapKey e unwrapKey:
  
Eseguire il cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) come segue:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Nell'output cercare i criteri di accesso e l'ID app (GUID) di Microsoft 365 in base alle esigenze. Tutte e tre le operazioni, get, wrapKey e unwrapKey, devono essere visualizzate in Autorizzazioni per le chiavi.
  
Se la configurazione dei criteri di accesso non è corretta, eseguire il cmdlet Set-AzKeyVaultAccessPolicy seguente:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Esempio: per il servizio Di crittografia dati in pausa di Microsoft 365, sostituire  *AppID di Microsoft 365* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) come indicato di seguito:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Una chiave scaduta non può essere utilizzata da Customer Key e le operazioni tentate con una chiave scaduta avranno esito negativo e potrebbero causare un'interruzione del servizio. È consigliabile che le chiavi utilizzate con customer key non abbia una data di scadenza. Una data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con una data di scadenza impostata, modificare il valore di scadenza in 31/12/9999. Le chiavi con una data di scadenza impostata su una data diversa dal 31/12/9999 non supereranno la convalida di Microsoft 365.
  
Per modificare una data di scadenza impostata su un valore diverso dal 31/12/9999, eseguire il cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) come segue:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave di Azure Key Vault

Dopo aver completato tutti i passaggi in Azure per configurare gli insiemi di credenziali delle chiavi e aver aggiunto le chiavi, eseguire il comando seguente per ottenere l'URI per la chiave in ogni insieme di credenziali delle chiavi. Dovrai usare questi URI quando crei e assegni ogni protezione esecuzione programmi in un secondo momento, quindi salva queste informazioni in un luogo sicuro. Ricordarsi di eseguire questo comando una volta per ogni insieme di credenziali delle chiavi.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurare il criterio di crittografia customer key per il tenant

Per poter eseguire questi cmdlet, è necessario disporre delle autorizzazioni appropriate. Sebbene in questo articolo siano elencati tutti i parametri per i cmdlet, è possibile che non si abbia accesso ad alcuni parametri se non sono inclusi nelle autorizzazioni assegnate. Per individuare le autorizzazioni necessarie per eseguire cmdlet o parametri nell'organizzazione, vedere [Trovare le autorizzazioni necessarie per eseguire i cmdlet di Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Creare criteri

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

Descrizione: abilitare l'amministratore della conformità per creare un nuovo criterio di crittografia dei dati utilizzando due chiavi radice AKV. Una volta creato, è possibile assegnare un criterio utilizzando Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Alla prima assegnazione dei tasti o dopo aver ruotato i tasti, possono essere necessario fino a 24 ore per l'applicazione dei nuovi tasti. Se la nuova protezione esecuzione programmi richiede più di 24 ore, contattare Microsoft.

Esempio:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parametri:

| Nome | Descrizione | Facoltativo (Y/N) |
|----------|----------|---------|
|Nome|Nome descrittivo del criterio di crittografia dei dati|N|
|AzureKeyIDs|Specifica due valori URI delle chiavi dell'insieme di credenziali delle chiavi di Azure, separati da una virgola, da associare al criterio di crittografia dei dati|N|
|Descrizione|Descrizione del criterio di crittografia dei dati|N|

### <a name="assign-policy"></a>Assegnare criteri

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

Descrizione: questo cmdlet viene utilizzato per configurare i criteri di crittografia dei dati predefiniti. Questo criterio verrà usato per crittografare i dati in tutti i carichi di lavoro di supporto. 

Esempio:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

Parametri:

| Nome | Descrizione | Facoltativo (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|Specifica il criterio di crittografia dei dati che deve essere assegnato. specificare il nome del criterio o l'ID criterio.|N|

### <a name="modify-or-refresh-policy"></a>Modificare o aggiornare i criteri

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descrizione: il cmdlet può essere utilizzato per modificare o aggiornare un criterio esistente. Può essere utilizzato anche per abilitare o disabilitare un criterio. Alla prima assegnazione dei tasti o dopo aver ruotato i tasti, possono essere necessario fino a 24 ore per l'applicazione dei nuovi tasti. Se la nuova protezione esecuzione programmi richiede più di 24 ore, contattare Microsoft.

Esempi:

Disabilitare un criterio di crittografia dei dati.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Aggiornare un criterio di crittografia dei dati.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

Parametri:

| Nome | Descrizione | Facoltativo (Y/N) |
|----------|----------|---------|
|-Identity|Specifica il criterio di crittografia dei dati che si desidera modificare.|N|
|-Refresh|Utilizzare l'opzione Aggiorna per aggiornare i criteri di crittografia dei dati dopo aver ruotato una delle chiavi associate nell'insieme di credenziali delle chiavi di Azure. Con questa opzione non è necessario specificare alcun valore.|Y|
|-Enabled|Il parametro Enabled consente di abilitare o disabilitare il criterio di crittografia dei dati. Prima di disabilitare un criterio, è necessario annullarne l'assegnazione dal tenant. I valori validi sono:</br > $true: il criterio è abilitato</br > $true: il criterio è abilitato. Questo è il valore predefinito.
|Y|
|-Name|Il parametro Name specifica il nome univoco del criterio di crittografia dei dati.|Y|
|-Description|Il parametro Description specifica una descrizione facoltativa del criterio di crittografia dei dati.|Y|

### <a name="get-policy-details"></a>Ottenere i dettagli dei criteri

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descrizione: questo cmdlet elenca tutti i criteri di crittografia M365DataAtRest creati per il tenant o i dettagli su un criterio specifico.

Esempi:

In questo esempio viene restituito un elenco riepilogativo dei criteri di crittografia M365DatAtRest nell'organizzazione.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

In questo esempio vengono restituite informazioni dettagliate per il criterio di crittografia dei dati denominato "NAM Policy".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parametri:

| Nome | Descrizione | Facoltativo (Y/N) |
|----------|----------|---------|
|-Identity|Specifica il criterio di crittografia dei dati per cui si desidera elencare i dettagli.|Y|

### <a name="get-policy-assignment-info"></a>Ottenere informazioni sull'assegnazione dei criteri

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descrizione: questo cmdlet elenca i criteri attualmente assegnati al tenant.

## <a name="offboarding-from-customer-key"></a>Offboarding da Customer Key

Se è necessario ripristinare le chiavi gestite da Microsoft, è possibile. Quando si esegue l'offboard, i dati vengono crittografati di nuovo utilizzando la crittografia predefinita supportata da ogni singolo carico di lavoro. Ad esempio, Exchange Online supporta la crittografia predefinita utilizzando le chiavi gestite da Microsoft.

Se si è deciso di eseguire l'offboard del tenant da Customer Key a livello di tenant, contattare Microsoft con una richiesta tramite posta elettronica per "disabilitare" il servizio per il tenant [a m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> L'offboarding non corrisponde a un'eliminazione di dati. Un'eliminazione dei dati elimina definitivamente i dati dell'organizzazione da Microsoft 365, l'offboarding no. Non è possibile eseguire un'eliminazione dei dati per un criterio a livello di tenant. Per informazioni sul percorso di eliminazione dei dati, vedere [Revocare le chiavi e avviare il processo del percorso di](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)eliminazione dei dati.

## <a name="about-the-availability-key"></a>Informazioni sulla chiave di disponibilità

Per informazioni sulla chiave di disponibilità, vedere [Informazioni sulla chiave di disponibilità.](customer-key-availability-key-understand.md)

## <a name="key-rotation"></a>Rotazione dei tasti

Per informazioni sulla rotazione o la rotazione dei tasti utilizzati con Customer Key, vedere [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md). Quando si aggiorna Protezione esecuzione programmi per l'utilizzo della nuova versione delle chiavi, si eseguirà il cmdlet Set-M365DataAtRestEncryptionPolicy come descritto in precedenza in questo articolo.

## <a name="related-articles"></a>Articoli correlati:

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Crittografia del servizio](office-365-service-encryption.md)
