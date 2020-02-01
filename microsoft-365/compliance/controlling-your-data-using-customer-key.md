---
title: Controllare i dati in Office 365 con Customer Key
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni su come configurare Customer Key per Office 365 per Exchange Online, Skype for business, SharePoint Online e OneDrive for business. Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei datacenter di Microsoft.
ms.openlocfilehash: 6d8673443fd08edfbe6d9f8b320429a6424d2a30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595693"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Controllare i dati in Office 365 con Customer Key

Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft. In altre parole, la chiave del cliente consente ai clienti di aggiungere un livello di crittografia che appartiene a loro, con le chiavi. Data at rest include i dati di Exchange Online e Skype for business archiviati nelle cassette postali e nei file archiviati in SharePoint Online e OneDrive for business.

È necessario configurare Azure prima di poter utilizzare la chiave del cliente per Office 365. In questo argomento vengono descritti i passaggi da seguire per creare e configurare le risorse di Azure necessarie, quindi vengono illustrati i passaggi per la configurazione della chiave del cliente in Office 365. Dopo aver completato l'installazione di Azure, è possibile stabilire quali criteri e quindi quali chiavi, per assegnare alle cassette postali e ai file nell'organizzazione. Le cassette postali e i file per cui non si assegna un criterio utilizzeranno i criteri di crittografia controllati e gestiti da Microsoft. Per ulteriori informazioni sulla chiave del cliente o per una panoramica generale, vedere le [domande frequenti su Customer Key per Office 365](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> È consigliabile attenersi alle procedure consigliate riportate in questo argomento. Questi sono denominati **Suggerimento** e **importante**. La chiave Customer consente di controllare le chiavi di crittografia radice il cui ambito può essere grande come l'intera organizzazione. Questo significa che gli errori commessi con queste chiavi possono avere un impatto generale e possono causare interruzioni del servizio o perdita irrevocabile dei dati.
  
## <a name="before-you-begin-setting-up-customer-key"></a>Prima di iniziare a configurare la chiave del cliente
<a name="Beforeyoustart"> </a>

Prima di iniziare, assicurarsi di disporre della licenza appropriata per la propria organizzazione. La chiave del cliente in Office 365 è disponibile in Office 365 E5 o nella SKU di conformità avanzata.
  
Per comprendere i concetti e le procedure in questo argomento, è quindi necessario esaminare la documentazione relativa alla [chiave del Vault di Azure](https://azure.microsoft.com/documentation/services/key-vault/) . Inoltre, acquisire familiarità con i termini utilizzati in Azure, ad esempio [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Per fornire commenti e suggerimenti sulla chiave del cliente, inclusa la documentazione, inviare le proprie idee, consigli e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Panoramica della configurazione della chiave del cliente per Office 365
<a name="Overview"> </a>

Per impostare la chiave del cliente, è necessario completare queste attività. Il resto di questo argomento fornisce istruzioni dettagliate per ogni attività o collegamenti a ulteriori informazioni per ogni passaggio del processo.
  
**In Azure e Microsoft FastTrack:**
  
La maggior parte delle attività verrà completata tramite la connessione remota a Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.
  
- [Creare due nuove sottoscrizioni di Azure](controlling-your-data-using-customer-key.md#Create2newsubs)

- [Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)

    La registrazione può richiedere da uno a cinque giorni lavorativi.

- [Inviare una richiesta per attivare la chiave del cliente per Office 365](controlling-your-data-using-customer-key.md#FastTrack)

    Dopo aver creato le due nuove sottoscrizioni di Azure, è necessario inviare la richiesta di offerta chiave del cliente completando un modulo Web ospitato nel portale di Microsoft FastTrack. **Il team di FastTrack non fornisce assistenza per la chiave del cliente. Office utilizza semplicemente il portale FastTrack per consentire all'utente di inviare il modulo e di aiutarci a tenere conto delle offerte rilevanti per la chiave del cliente**.
  
Dopo aver inoltrato un'offerta per la chiave del cliente, Microsoft esamina la richiesta e notifica quando è possibile procedere con le altre attività di installazione. Questo processo può richiedere fino a cinque giorni lavorativi.

- [Creare un Vault Key Azure Premium in ogni sottoscrizione](controlling-your-data-using-customer-key.md#CreateKeyVault)

- [Assegnare le autorizzazioni per ogni Vault chiave](controlling-your-data-using-customer-key.md#KeyVaultPerms)

- [Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi](controlling-your-data-using-customer-key.md#SoftDelete)

- [Aggiungere una chiave a ogni Vault chiave creando o importando una chiave](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)

- [Controllare il livello di ripristino delle chiavi](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)

- [Backup della chiave del Vault di Azure](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)

- [Convalidare le impostazioni di configurazione di Azure Key Vault](controlling-your-data-using-customer-key.md#Validateconfiguration)

- [Ottenere l'URI per ogni chiave del Vault Key di Azure](controlling-your-data-using-customer-key.md#GetKeyURI)

**In Office 365:**
  
Exchange Online e Skype for business:
  
- [Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Assegnare una DEP a una cassetta postale](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Convalidare la crittografia della cassetta postale](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online e OneDrive for business:
  
- [Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Convalidare la crittografia di siti di gruppo, siti del team e OneDrive for business](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completare le attività in Azure Key Vault e Microsoft FastTrack per la chiave del cliente
<a name="AzureSteps"> </a>

Completare queste attività in Azure Key Vault per impostare la chiave del cliente per Office 365. Sarà necessario completare questi passaggi, indipendentemente dal fatto che si desideri configurare la chiave del cliente per Exchange Online e Skype for business o SharePoint Online e OneDrive for business o per tutti i servizi supportati in Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure
<a name="Create2newsubs"> </a>

Per la chiave del cliente sono necessarie due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di creare nuove sottoscrizioni di Azure per l'utilizzo con la chiave del cliente. Le chiavi del Vault Key di Azure possono essere autorizzate solo per le applicazioni nello stesso tenant di Azure Active Directory (AAD), è necessario creare le nuove sottoscrizioni usando lo stesso tenant di Azure AD utilizzato con l'organizzazione di Office 365 in cui verrà assegnato il DEPs. Ad esempio, utilizzando l'account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione di Office 365. Per la procedura dettagliata, vedere [iscriversi a Azure come organizzazione](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> La chiave del cliente richiede due chiavi per ogni criterio di crittografia dei dati. Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri distinti dell'organizzazione che configurano una chiave in ogni sottoscrizione. Inoltre, queste sottoscrizioni di Azure devono essere utilizzate solo per amministrare le chiavi di crittografia per Office 365. Questo consente di proteggere l'organizzazione nel caso in cui uno degli operatori involontariamente, intenzionalmente o elimini in modo doloso o meno le chiavi per le quali sono responsabili. <br/> È consigliabile impostare nuove sottoscrizioni di Azure che vengono utilizzate solo per la gestione delle risorse del Vault Key di Azure per l'utilizzo con la chiave del cliente. Non esiste alcun limite pratico per il numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguendo queste procedure consigliate si minimizza l'impatto dell'errore umano contribuendo a gestire le risorse utilizzate dalla chiave del cliente. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Inviare una richiesta per attivare la chiave del cliente per Office 365
<a name="FastTrack"> </a>

Dopo aver completato i passaggi di Azure, è necessario inviare una richiesta di offerta nel [portale Microsoft FastTrack](https://fasttrack.microsoft.com/). Dopo aver inoltrato una richiesta tramite il portale Web di FastTrack, Microsoft verifica i dati di configurazione del Vault Key di Azure e le informazioni di contatto fornite. Le selezioni che vengono apportate nel modulo di offerta per quanto riguarda i funzionari autorizzati dell'organizzazione sono critiche e necessarie per il completamento della registrazione a chiave del cliente. Gli agenti dell'organizzazione selezionati nel modulo saranno utilizzati per garantire l'autenticità di qualsiasi richiesta di revocare e distruggere tutte le chiavi utilizzate con un criterio di crittografia dei dati chiave del cliente. È necessario eseguire questo passaggio una volta per attivare il codice "Customer Key" per Exchange Online e Skype for business e una seconda volta per attivare la chiave del cliente per SharePoint Online e OneDrive for business.
  
Per inviare un'offerta per attivare il codice "Customer Key", eseguire la procedura seguente:
  
1. L'utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, accedere al [portale di Microsoft FastTrack](https://fasttrack.microsoft.com/).
    
2. Dopo aver effettuato l'accesso, passare al **Dashboard**.
    
3. Scegliere **offerte**ed esaminare l'elenco delle offerte correnti.
    
4. Scegliere **ulteriori informazioni** per l'offerta che si applica all'utente: 
    
  - **Exchange Online e Skype for business:** Scegliere **ulteriori informazioni** sulla **chiave del cliente per l'offerta di Exchange** . 
    
  - **SharePoint Online e OneDrive for business:** Scegliere **ulteriori informazioni** sulla chiave del cliente per l'offerta di **SharePoint e OneDrive for business** . 
    
5. Nella pagina **Dettagli offerta** scegliere **Crea richiesta**.
    
6. Compilare tutti i dettagli applicabili e le informazioni richieste nel modulo di offerta. Prestare particolare attenzione alle selezioni per i funzionari dell'organizzazione che si desidera autorizzare ad approvare la distruzione permanente e irreversibile delle chiavi di crittografia e dei dati. Dopo aver completato il modulo, scegliere **Submit**.
    
    Questo processo può richiedere fino a cinque giorni lavorativi una volta che Microsoft è stato informato della richiesta.
    
7. Passare alla sezione periodo di conservazione obbligatoria seguente.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio
<a name="RegisterSubsforMRP"> </a>

La perdita temporanea o permanente delle chiavi di crittografia radice può essere molto dirompente o addirittura catastrofica per l'utilizzo del servizio e può causare una perdita di dati. Per questo motivo, le risorse utilizzate con la chiave del cliente richiedono una protezione sicura. Tutte le risorse di Azure utilizzate con la chiave del cliente offrono meccanismi di protezione oltre la configurazione predefinita. Le sottoscrizioni di Azure possono essere contrassegnate o registrate in un modo che impedirà l'annullamento immediato e irrevocabile. Si tratta della registrazione di un periodo di conservazione obbligatorio. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con il team di Office 365. Questo processo può richiedere da uno a cinque giorni lavorativi. In precedenza, questo è stato talvolta definito come "non annullare".
  
Prima di contattare il team di Office 365, è necessario eseguire i passaggi seguenti per ogni sottoscrizione di Azure utilizzata con la chiave Customer:
  
1. Accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Eseguire il cmdlet Register-AzureRmProviderFeature per registrare gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio.
    
  ```powershell
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Contattare Microsoft per eseguire il processo di completamento. Per il team di SharePoint e OneDrive for business, contattare [Spock@microsoft.com](mailto:spock@microsoft.com). Per Exchange Online e Skype for business, contattare [exock@microsoft.com](mailto:exock@microsoft.com). Il contratto di servizio per il completamento di questo processo è di cinque giorni lavorativi una volta che Microsoft è stato informato (e verificato) di aver registrato gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio. Includere quanto segue nel messaggio di posta elettronica:
    
    **Oggetto**: chiave del cliente \<per *il nome di dominio* completo del tenant\> 
    
    **Corpo**: ID di sottoscrizione per i quali si desidera che il periodo di conservazione obbligatorio sia stato completato. 
    
4. Dopo aver ricevuto la notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il cmdlet Get-AzureRmProviderFeature come indicato di seguito:
    
  ```powershell
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Dopo aver verificato che la proprietà **state registrazione** del cmdlet Get-AzureRmProviderFeature restituisca il valore **registrato**, eseguire il comando seguente per completare il processo:
    
  ```powershell
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un Vault Key Azure Premium in ogni sottoscrizione
<a name="CreateKeyVault"> </a>

La procedura per creare un Vault chiave è documentata per [iniziare con Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), che illustra l'installazione e l'avvio di Azure PowerShell, la connessione all'abbonamento di Azure, la creazione di un gruppo di risorse e la creazione di un Vault Key in tale gruppo di risorse.
  
Quando si crea un Vault chiave, è necessario scegliere un SKU: standard o Premium. La SKU standard consente di proteggere i tasti del Vault Key di Azure con il software: non vi è alcuna protezione della chiave HSM (hardware Security Module) e la SKU Premium consente l'utilizzo di HSM per la protezione delle chiavi del Vault Key. La chiave Customer accetta i Vault chiave che utilizzano SKU, anche se Microsoft consiglia vivamente di utilizzare solo la SKU Premium. Il costo delle operazioni con chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo al mese per ogni chiave protetta da HSM. Per informazioni dettagliate, vedere [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) . 
  
> [!IMPORTANT]
> Utilizzare i Vault chiave SKU Premium e le chiavi con protezione HSM per i dati di produzione e utilizzare solo i Vault e le chiavi standard SKU per il testing e la convalida. 
  
Per ogni servizio di Office 365 con cui si utilizzerà la chiave del cliente, creare un Vault Key in ognuna delle due sottoscrizioni di Azure create. Ad esempio, per Exchange Online e Skype for business solo o SharePoint Online e OneDrive for business, si creerà solo una coppia di volte. Per abilitare la chiave del cliente per Exchange Online e SharePoint Online, è possibile creare due coppie di volte chiave.
  
Utilizzare una convenzione di denominazione per i Vault chiave che riflette l'utilizzo previsto della funzionalità di protezione dei nomi con cui verranno associati i Vault. Vedere la sezione procedure consigliate di seguito per la denominazione dei consigli convenzioni.
  
Creare un set di volte separato e abbinato per ogni criterio di crittografia dei dati. Per Exchange Online, l'ambito di un criterio di crittografia dei dati viene scelto dall'utente quando si assegna il criterio alla cassetta postale. Una cassetta postale può avere un solo criterio assegnato ed è possibile creare fino a 50 criteri. Per SharePoint Online l'ambito di un criterio è costituito da tutti i dati all'interno di un'organizzazione in una posizione geografica o Geo.
  
La creazione di Vault chiave richiede anche la creazione di gruppi di risorse di Azure, poiché è necessario che la capacità di archiviazione (anche se molto piccola) e la registrazione Key Vault, se abilitata, generano anche dati archiviati. Come procedura consigliata, Microsoft consiglia di utilizzare amministratori distinti per gestire ogni gruppo di risorse, con l'amministrazione allineata al set di amministratori che gestirà tutte le risorse chiave dei clienti correlate.
  
> [!IMPORTANT]
> Per massimizzare la disponibilità, i Vault delle chiavi devono trovarsi nelle aree geografiche vicino al servizio Office 365. Ad esempio, se l'organizzazione di Exchange Online è in Nord America, inserire i Vault chiave in Nord America. Se l'organizzazione di Exchange Online è in Europa, inserire i Vault chiave in Europa.<br/>Utilizzare un prefisso comune per i Vault chiave e includere un'abbreviazione dell'utilizzo e dell'ambito del Vault Key e delle chiavi (ad esempio, per il servizio contoso SharePoint in cui si trovano i Vault in Nord America, una possibile coppia di nomi è contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. Il nome del Vault è una stringa univoca globale all'interno di Azure, quindi potrebbe essere necessario provare varianti dei nomi desiderati, nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. A luglio 2017 non è possibile modificare i nomi dei Vault, quindi è consigliabile disporre di un piano scritto per il programma di installazione e utilizzare una seconda persona per verificare che il piano sia stato eseguito correttamente.<br/>Se possibile, creare i Vault in aree non accoppiate. Le aree di Azure con accoppiamento offrono disponibilità elevata tra i domini di errore del servizio. Di conseguenza, le coppie regionali possono essere pensate come area di backup dell'altro. Questo significa che una risorsa di Azure inserita in un'area geografica acquisisce automaticamente la tolleranza di errore tramite l'area associata. Per questo motivo, la scelta delle aree geografiche per due volte utilizzate in una DEP in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle geografie ha solo due aree geografiche, quindi non è ancora possibile selezionare le aree non accoppiate. Se possibile, scegliere due aree non associate per i due Vault utilizzati con una funzionalità di protezione esecuzione programmi. Questo beneficia di un totale di quattro aree di disponibilità. Per ulteriori informazioni, vedere [Business Continuity and Disaster Recovery (BCdR): aree con accoppiamento di Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente di coppie regionali. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Assegnare le autorizzazioni per ogni Vault chiave
<a name="KeyVaultPerms"> </a>

Per ogni Vault chiave, sarà necessario definire tre Set distinti di autorizzazioni per la chiave del cliente, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori chiave del Vault** che eseguono la gestione quotidiana del Vault Key per l'organizzazione. Tali attività includono backup, creazione, recupero, importazione, elenco e ripristino. 
    
    > [!IMPORTANT]
    > Il set di autorizzazioni assegnate agli amministratori delle chiavi del Vault non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una prassi intenzionale e importante. L'eliminazione delle chiavi di crittografia non è in genere completata, poiché tale operazione distrugge definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori delle chiavi del Vault per impostazione predefinita. Al contrario, è necessario riservare questo elemento ai collaboratori del Vault Key e assegnarlo solo a un amministratore a breve termine dopo aver compreso la comprensione delle conseguenze. 
  
    Per assegnare queste autorizzazioni a un utente nell'organizzazione di Office 365, eseguire l'accesso alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Ad esempio:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **Key Vault Contributors** che possono modificare le autorizzazioni per il Vault Key di Azure stesso. È necessario modificare queste autorizzazioni quando i dipendenti lasciano o entrano in un team o in una situazione estremamente rara in cui gli amministratori delle Key Vault devono legittimamente disporre dell'autorizzazione per eliminare o ripristinare una chiave. Questo set di collaboratori chiave del Vault deve essere concesso al ruolo **collaboratore** nel Vault Key. È possibile assegnare questo ruolo tramite Gestione risorse di Azure. Per la procedura dettagliata, vedere [utilizzare il controllo di accesso basato sui ruoli per gestire l'accesso alle risorse di sottoscrizione di Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). L'amministratore che crea una sottoscrizione ha questo accesso in modo implicito, nonché la possibilità di assegnare altri amministratori al ruolo Collaboratore.
    
- Se si intende utilizzare la chiave del cliente con Exchange Online e Skype for business, è necessario concedere l'autorizzazione a Office 365 per utilizzare il Vault Key per conto di Exchange Online e Skype for business. Analogamente, se si intende utilizzare Customer Key con SharePoint Online e OneDrive for business, è necessario aggiungere l'autorizzazione per Office 365 per utilizzare il Vault chiave per conto di SharePoint Online e OneDrive for business. Per concedere l'autorizzazione a Office 365, eseguire il cmdlet **set-AzureRmKeyVaultAccessPolicy** utilizzando la sintassi seguente: 
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Dove:
    
  - *VAULTNAME* è il nome del Vault Key creato. 
    
  - Per Exchange Online e Skype for business, Sostituisci *Office 365 AppID* con`00000002-0000-0ff1-ce00-000000000000`
    
  - Per SharePoint Online e OneDrive for business, sostituire *Office 365 AppID* con`00000003-0000-0ff1-ce00-000000000000`
    
  Esempio: impostazione delle autorizzazioni per Exchange Online e Skype for business:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Esempio: impostazione delle autorizzazioni per SharePoint Online e OneDrive for business

  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi
<a name="SoftDelete"> </a>

Quando è possibile recuperare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi accidentali o eliminate intenzionalmente. È necessario abilitare questa configurazione, denominata eliminazione temporanea, prima di poter utilizzare le chiavi con il codice "Customer Key". L'abilitazione dell'eliminazione temporanea consente di recuperare le chiavi o i Vault entro 90 giorni dall'eliminazione senza dover ripristinare il backup.
  
Per abilitare l'eliminazione temporanea nei Vault delle chiavi, eseguire la procedura seguente:
  
1. Accedere alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . In questo esempio, *VAULTNAME* è il nome del Vault Key per il quale si desidera abilitare l'eliminazione morbida: 

   ```powershell
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirm soft delete è configurato per il Vault Key tramite l'esecuzione del cmdlet **Get-AzureRmKeyVault** . Se l'eliminazione morbida è configurata correttamente per il Vault chiave, l'eliminazione temporanea è abilitata? la proprietà restituisce il valore **true**: 

   ```powershell
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Aggiungere una chiave a ogni Vault chiave creando o importando una chiave
<a name="AddKeystoKeyVault"> </a>

Esistono due modi per aggiungere chiavi a un Vault Key di Azure; è possibile creare una chiave direttamente in Key Vault oppure è possibile importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave fornisce il controllo totale sul modo in cui viene generata la chiave.
  
Per creare una chiave direttamente nel Vault chiave, eseguire il cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) nel modo seguente: 
  
```powershell
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dove:
  
- *VAULTNAME* è il nome del Vault chiave in cui si desidera creare la chiave.

- *nome del tasto è il* nome che si desidera assegnare alla nuova chiave.

    > [!TIP]
    > Le chiavi dei nomi utilizzano una convenzione di denominazione simile, come descritto in alto per i Vault chiave. In questo modo, in strumenti che mostrano solo il nome della chiave, la stringa è autoesplicativa. 
  
- Se si intende proteggere la chiave con un HSM, accertarsi di specificare **HSM** come valore del parametro _Destination_ , in caso contrario, specificare il **software**.

For example,
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Per importare una chiave direttamente nel Vault chiave, è necessario disporre di un modulo di sicurezza hardware di Thales nShield.
  
Alcune organizzazioni preferiscono questo approccio per stabilire la provenienza delle chiavi e questo metodo fornisce anche gli elementi seguenti:
  
- Il set di strumenti utilizzato per l'importazione include l'attestazione di Thales che la chiave Key Exchange (KEK) utilizzata per crittografare la chiave che si genera non è esportabile e che viene generata all'interno di un HSM genuino prodotto da Thales.

- Il set di strumenti include l'attestazione di Thales che la sicurezza di Azure Key Vault è stata generata anche su un HSM genuino prodotto da Thales. L'attestazione dimostra che Microsoft utilizza anche hardware reale Thales.

Verificare con il gruppo di sicurezza se sono necessarie le attestazioni sopra riportate. Per la procedura dettagliata per creare una chiave locale e importarla nel Vault chiave, vedere [How to generate and transfer HSM-protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Utilizzare le istruzioni di Azure per creare una chiave in ogni Vault Key.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su non Annulla e che le chiavi utilizzate dal codice "Customer Key" siano abilitate per l'eliminazione temporanea. È possibile confermarlo esaminando il livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di una chiave, in Azure PowerShell, eseguire il cmdlet Get-AzureKeyVaultKey come indicato di seguito:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes
```

Se la proprietà del _livello di recupero_ restituisce un valore diverso da quello di **+ ProtectedSubscription**, sarà necessario esaminare questo argomento e assicurarsi di aver seguito tutti i passaggi necessari per inserire la sottoscrizione nell'elenco non annullare e di aver attivato l'eliminazione temporanea su ognuna delle volte chiave.
  
### <a name="backup-azure-key-vault"></a>Backup della chiave del Vault di Azure
<a name="BackupAzureKeyVaultkeys"> </a>

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Le copie offline non devono essere connesse a nessuna rete, ad esempio in una struttura di archiviazione sicura o commerciale fisica. Almeno una copia del backup deve essere archiviata in un percorso che sarà accessibile in caso di emergenza. Gli oggetti BLOB di backup sono gli unici strumenti per ripristinare il materiale chiave se una chiave del Vault Key deve essere definitivamente distrutta o altrimenti resa inutilizzabile. Le chiavi esterne all'archivio delle chiavi di Azure e sono state importate in Azure Key Vault non sono qualificate come backup poiché i metadati necessari per la chiave del cliente per l'utilizzo della chiave non sono presenti con la chiave esterna. È possibile utilizzare solo un backup da Vault Key di Azure per le operazioni di ripristino con il codice "Customer Key". Pertanto, è essenziale che un backup del Vault Key di Azure venga eseguito dopo il caricamento o la creazione di una chiave.
  
Per creare un backup di una chiave del Vault Key di Azure, eseguire il cmdlet [backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) come indicato di seguito:

```powershell
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>
-OutputFile <filename .backup>
```

Verificare che il file di output utilizzi il `.backup`suffisso.
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno del Vault Key di Azure. Il backup può essere ripristinato solo per la sottoscrizione di Azure da cui è stato effettuato il backup.
  
> [!TIP]
> Per il file di output, scegliere una combinazione del nome del Vault e del nome della chiave. Questo renderà il nome di file autodescrittivo. Assicurerà inoltre che i nomi dei file di backup non entrino in collisione.
  
Ad esempio:
  
```powershell
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Convalidare le impostazioni di configurazione di Azure Key Vault
<a name="Validateconfiguration"> </a>

L'esecuzione della convalida prima di utilizzare le chiavi in una funzionalità DEP è facoltativa, ma è consigliabile. In particolare, se si utilizzano i passaggi necessari per configurare le chiavi e le volte diverse da quelle descritte in questo argomento, è consigliabile convalidare l'integrità delle risorse del Vault Key di Azure prima di configurare la chiave del cliente.
  
Per verificare che le chiavi dispongano delle operazioni get, wrapKey e unwrapKey attivate:
  
Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) nel modo seguente:
  
```powershell
Get-AzureRMKeyVault -VaultName <vaultname>
```

Nell'output, cercare il criterio di accesso e per l'identità di Exchange Online (GUID) o l'identità di SharePoint Online (GUID) in base alle esigenze. Tutte e tre le autorizzazioni sopra riportate devono essere visualizzate in autorizzazioni per le chiavi.
  
Se la configurazione del criterio di accesso non è corretta, eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy come indicato di seguito:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Ad esempio, per Exchange Online e Skype for business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Ad esempio, per SharePoint Online e OneDrive for business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) come indicato di seguito:
  
```powershell
Get-AzureKeyVaultKey -VaultName <vaultname>
```

Non è possibile utilizzare una chiave scaduta dalla chiave del cliente e le operazioni tentate con una chiave scaduta avranno esito negativo e, eventualmente, si verificherà un'interruzione del servizio. È consigliabile che i tasti utilizzati con la chiave del cliente non abbiano una data di scadenza. La data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con un set di date di scadenza, impostare il valore di scadenza su 12/31/9999. Le chiavi con una data di scadenza impostata su una data diversa da 12/31/9999 non supereranno la convalida di Office 365.
  
Per modificare una data di scadenza impostata su un valore diverso da 12/31/9999, eseguire il cmdlet [set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) come indicato di seguito:
  
```powershell
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Non impostare le date di scadenza per le chiavi di crittografia utilizzate con la chiave del cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave del Vault Key di Azure
<a name="GetKeyURI"> </a>

Dopo aver completato tutti i passaggi in Azure per configurare i Vault chiave e aver aggiunto le chiavi, eseguire il seguente comando per ottenere l'URI per la chiave in ogni Vault Key. Sarà necessario utilizzare questi URI quando si crea e si assegna ogni DEP in un secondo momento, quindi salvare queste informazioni in una posizione sicura. Ricordarsi di eseguire questo comando una volta per ogni Vault Key.
  
In Azure PowerShell:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: impostazione della chiave del cliente per Exchange Online e Skype for business
<a name="AzureSteps"> </a>

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Per impostare la chiave del cliente per Exchange Online e Skype for business, è necessario eseguire questa procedura per la connessione remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business
<a name="CreateDEP4EXOSkype"> </a>

Un DEP è associato a un set di chiavi archiviate in Azure Key Vault. È possibile assegnare una DEP a una cassetta postale in Office 365. Office 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .
  
Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare la funzionalità di protezione esecuzione programmi, eseguire la procedura seguente:
  
1. Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) aprendo Windows PowerShell ed eseguendo il comando riportato di seguito.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Nella finestra di dialogo richiesta credenziali di Windows PowerShell, immettere le informazioni dell'account aziendale o dell'Istituto di istruzione, fare clic su **OK**e quindi immettere il comando seguente.

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Eseguire il comando riportato di seguito.

   ```powershell
   Import-PSSession $Session
   ```

4. Per creare una funzionalità di protezione esecuzione programmi, utilizzare il cmdlet New-DataEncryptionPolicy digitando il comando seguente.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dove:

   -  *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.

   -  *PolicyDescription* è una descrizione facile da usare per i criteri che consentiranno di ricordare a cosa serve il criterio. È possibile includere spazi nella descrizione. Ad esempio, la chiave radice per le cassette postali negli Stati Uniti e nei suoi territori.

   -  *KeyVaultURI1* è l'URI per la prima chiave del criterio. Ad esempio, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   -  *KeyVaultURI2* è l'URI per la seconda chiave del criterio. Ad esempio, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separare i due URI da una virgola e uno spazio.

   Esempio:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Assegnare una DEP a una cassetta postale
<a name="assignDEPtomailbox"> </a>

Assegnare la funzionalità Protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Office 365 può crittografare la cassetta postale con la chiave indicata nella DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailboxIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Convalidare la crittografia della cassetta postale
<a name="validatemailboxencryption"> </a>

La crittografia di una cassetta postale può richiedere del tempo. Per l'assegnazione dei criteri per la prima volta, la cassetta postale deve anche completare lo spostamento da un database all'altro prima che il servizio possa crittografare la cassetta postale. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata. 

Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui viene assegnata una DEP per la prima volta, oltre che dalle dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stata assegnata la funzionalità DEP, avviare lo spostamento di una cassetta postale per le cassette postali non crittografate tramite il cmdlet New-MoveRequest.

```powershell
New-MoveRequest <mailbox alias>
```

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: impostazione della chiave del cliente per SharePoint Online e OneDrive for business
<a name="AzureSteps"> </a>

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) .
  
Per impostare la chiave del cliente per SharePoint Online e OneDrive for business, è necessario eseguire questa procedura per la connessione remota a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business
<a name="CreateDEP4SPOODfB"> </a>

Un DEP è associato a un set di chiavi archiviate in Azure Key Vault. È possibile applicare una DEP a tutti i dati in una posizione geografica, denominata anche geo. Se si utilizza la caratteristica multi-geo di Office 365, è possibile creare una DEP per Geo. Se non si utilizza multi-Geo, è possibile creare una DEP in Office 365 per l'utilizzo con SharePoint Online e OneDrive for business. Office 365 utilizzerà quindi le chiavi identificate nella funzionalità DEP per crittografare i dati in tale Geo. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare una funzionalità di protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online tramite Windows PowerShell.
  
1. Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx).

2. In Microsoft SharePoint Online Management Shell, eseguire il cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) come indicato di seguito:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Quando si registra la funzionalità DEP, la crittografia inizia sui dati del geografico. Questo può richiedere un certo tempo.

### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Convalidare la crittografia di siti di gruppo, siti del team e OneDrive for business
<a name="validateencryptionSPO"> </a>

È possibile controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

L'output di questo cmdlet include:
  
- URI della chiave primaria.

- URI del tasto secondario.

- Lo stato di crittografia per il Geo. Gli stati possibili includono:

  - Non **registrato:** La crittografia a chiave del cliente non è stata ancora applicata.

  - **Registrazione:** È stata applicata la crittografia a chiave del cliente e i file sono in fase di crittografazione. Se il geografico è in questo stato, verranno visualizzate anche informazioni su quale percentuale di siti nel Geo sono completi, in modo da poter monitorare lo stato della crittografia.

  - **Registrato:** È stata applicata la crittografia a chiave del cliente e tutti i file in tutti i siti sono stati crittografati.

  - **Rolling:** È in corso un roll Key. Se il geografico è in questo stato, verranno visualizzate anche informazioni su quale percentuale di siti è stata completata l'operazione di roll Key, in modo da poter monitorare lo stato di avanzamento.

## <a name="managing-customer-key-for-office-365"></a>Gestione della chiave del cliente per Office 365
<a name="ManageCustomerKey"> </a>

Dopo aver configurato Customer Key per Office 365, è possibile eseguire queste attività di gestione aggiuntive.
  
- [Ripristinare le chiavi del Vault Key di Azure](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)

- [Rotazione o rotazione di una chiave nel Vault Key di Azure utilizzata con la chiave del cliente](controlling-your-data-using-customer-key.md#RollCKkey)

- [Gestire le autorizzazioni del Vault Key](controlling-your-data-using-customer-key.md#Managekeyvaultperms)

- [Determinare la funzionalità DEP assegnata a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Ripristinare le chiavi del Vault Key di Azure
<a name="RestoreAzureKeyVaultKeys"> </a>

Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite da soft delete. Tutte le chiavi utilizzate con la chiave Customer devono essere abilitate per l'eliminazione temporanea. Delete Soft agisce come un cestino e consente il ripristino per un massimo di 90 giorni senza che sia necessario ripristinarlo. Il ripristino deve essere necessario solo in caso di circostanze estreme o inusuali, ad esempio se la chiave o la chiave del Vault è persa. Se è necessario ripristinare una chiave da utilizzare con la chiave Customer, in Azure PowerShell, eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:
  
```powershell
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Ad esempio:
  
```powershell
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se nel Vault della chiave è già presente un tasto con lo stesso nome, l'operazione di ripristino avrà esito negativo. Restore-AzureKeyVaultKey Ripristina tutte le versioni principali e tutti i metadati per la chiave, incluso il nome della chiave.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Rotazione o rotazione di una chiave nel Vault Key di Azure utilizzata con la chiave del cliente
<a name="RollCKkey"> </a>

I tasti di scorrimento non sono richiesti da un Vault di Azure Key o dal codice del cliente. Inoltre, le chiavi protette con un HSM sono virtualmente impossibili da compromettere. Anche se una chiave radice è in possesso di un attore malevolo, non è possibile utilizzarlo per decrittografare i dati, poiché solo il codice di Office 365 sa come usarlo. Tuttavia, l'implementazione di una chiave è supportata dal codice "Customer Key".
  
> [!CAUTION]
> Eseguire il rollback di una chiave di crittografia da utilizzare con il codice "Customer Key" se esiste un motivo tecnico chiaro oppure se un requisito di conformità richiede che è necessario eseguire il rollforward della chiave. Inoltre, non eliminare le chiavi che sono o sono state associate ai criteri. Quando si esegue il rollback delle chiavi, verranno crittografati i contenuti con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno crittografate di frequente, le cassette postali inattive, disconnesse e disabilitate potrebbero essere ancora crittografate con le chiavi precedenti. SharePoint Online esegue il backup del contenuto per scopi di ripristino e ripristino, per cui è possibile che il contenuto archiviato sia ancora utilizzato con i tasti precedenti. <br/> Per garantire la sicurezza dei dati, SharePoint Online non consentirà di eseguire più di un'operazione di rollforward della chiave alla volta. Se si desidera eseguire il rollback di entrambe le chiavi in un Vault chiave, è necessario attendere il completamento completo della prima operazione di rollforward. La nostra raccomandazione è quella di scaglionare le operazioni di rollio chiave a intervalli diversi, in modo che non si tratti di un problema.
  
Quando si esegue il rollforward di una chiave, si richiede una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, è necessario utilizzare lo stesso cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la stessa sintassi utilizzata per creare la chiave in primo luogo.
  
Ad esempio:
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

In questo esempio, poiché una chiave denominata **Contoso-O365EX-na-VaultA1-Key001** esiste già nel Vault **Contoso-O365EX-na-VaultA1** , verrà creata una nuova versione della chiave. L'operazione aggiunge una nuova versione della chiave. Questa operazione consente di conservare le versioni precedenti nella cronologia delle versioni della chiave, in modo che i dati precedentemente crittografati con tale chiave possano ancora essere decrittografati. Dopo aver completato il rollforward di qualsiasi tasto associato a una funzionalità di protezione esecuzione programmi, è necessario eseguire un ulteriore cmdlet per assicurarsi che la chiave del cliente inizi a utilizzare la nuova chiave.
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Abilitazione di Exchange Online e Skype for business per l'utilizzo di una nuova chiave dopo aver eseguito il rollforward o la rotazione delle chiavi in Azure Key Vault

Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una funzionalità di protezione dei comandi utilizzata con Exchange Online e Skype for business, è necessario eseguire il comando seguente per aggiornare la funzionalità DEP e abilitare Office 365 per iniziare a utilizzare la nuova chiave.
  
Per indicare alla chiave del cliente di utilizzare la nuova chiave per crittografare le cassette postali in Office 365, eseguire il cmdlet Set-DataEncryptionPolicy come indicato di seguito:
  
```powershell
Set-DataEncryptionPolicy <policyname> -Refresh
```

Entro 48 ore, le cassette postali attive crittografate con questo criterio diventeranno associate alla chiave aggiornata. Utilizzare la procedura descritta in [determinare la funzionalità DEP assegnata a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) per controllare il valore della proprietà DataEncryptionPolicyID per la cassetta postale. Il valore di questa proprietà verrà modificato dopo l'applicazione della chiave aggiornata.
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Abilitazione di SharePoint Online e OneDrive for business per l'utilizzo di una nuova chiave dopo aver eseguito il rollforward o la rotazione delle chiavi in Azure Key Vault

Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una funzionalità di protezione da utilizzare con SharePoint Online e OneDrive for business, è necessario eseguire il cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) per aggiornare la funzionalità DEP e abilitare Office 365 per iniziare a utilizzare la nuova chiave. 
  
```powershell
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Verrà avviata l'operazione di rollforward delle chiavi per SharePoint Online e OneDrive for business. Questa azione non è immediata. Per visualizzare lo stato dell'operazione di rollforward delle chiavi, eseguire il cmdlet Get-SPODataEncryptionPolicy nel modo riportato di seguito:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Gestire le autorizzazioni del Vault Key
<a name="Managekeyvaultperms"> </a>

Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, di rimuovere le autorizzazioni chiave del Vault. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.
  
Per visualizzare le autorizzazioni per il Vault chiave, eseguire il cmdlet Get-AzureRmKeyVault:
  
```powershell
Get-AzureRmKeyVault -VaultName <vaultname>
```

Ad esempio:
  
```powershell
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzureRmKeyVaultAccessPolicy:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname>
-UserPrincipalName <UPN of user>
```

Ad esempio:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinare la funzionalità DEP assegnata a una cassetta postale
<a name="DeterminemailboxDEP"> </a>

Per determinare la funzionalità DEP assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce un identificatore univoco (GUID).
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Utilizzare il GUID per individuare il nome descrittivo della funzionalità DEP a cui è assegnata la cassetta postale eseguendo il cmdlet seguente.
  
```powershell
Get-DataEncryptionPolicy <GUID>
```

Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.
