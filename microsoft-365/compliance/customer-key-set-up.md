---
title: Configurare Customer Key a livello di applicazione
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
description: Informazioni su come configurare Customer Key per i file di Microsoft 365 per Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams.
ms.openlocfilehash: 057f20005e64a15ef18d076206394159d2690818
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058479"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Configurare Customer Key a livello di applicazione

Con Customer Key, è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Microsoft 365 per usarle per crittografare i dati in stato di inquieto nei data center di Microsoft. In altre parole, Customer Key consente ai clienti di aggiungere un livello di crittografia che appartiene a loro, con le loro chiavi. I dati in pausa includono i dati di Exchange Online e Skype for Business archiviati nelle cassette postali e nei file archiviati in SharePoint Online e OneDrive for Business.

È necessario configurare Azure prima di poter usare Customer Key per Office 365. Questo articolo descrive i passaggi da seguire per creare e configurare le risorse di Azure necessarie e quindi fornisce i passaggi per configurare Customer Key in Office 365. Dopo aver completato l'installazione di Azure, è possibile determinare quale criterio, e quindi quali chiavi, assegnare alle cassette postali e ai file nell'organizzazione. Le cassette postali e i file per i quali non si assegna un criterio utilizzeranno i criteri di crittografia controllati e gestiti da Microsoft. Per ulteriori informazioni su Customer Key o per una panoramica generale, vedere Crittografia del servizio [con Customer Key in Office 365.](customer-key-overview.md)
  
> [!IMPORTANT]
> È consigliabile attenersi alle procedure consigliate in questo articolo. Questi sono denominati **TIP** e **IMPORTANT.** Customer Key offre il controllo sulle chiavi di crittografia radice il cui ambito può essere grande quanto l'intera organizzazione. Ciò significa che gli errori commersi con queste chiavi possono avere un forte impatto e possono causare interruzioni del servizio o perdita irrevocabile dei dati.
  
## <a name="before-you-set-up-customer-key"></a>Prima di configurare Customer Key

Prima di iniziare, verificare di disporre delle licenze appropriate per l'organizzazione. Usare una sottoscrizione di Azure a pagamento e fatturata usando un Contratto Enterprise o un provider di servizi cloud. Le sottoscrizioni di Azure acquistate con i piani Pay As You Go o con una carta di credito non sono supportate per Customer Key. A partire dal 1° aprile 2020, Customer Key in Office 365 è disponibile in Office 365 E5, M365 E5, M365 E5 Compliance e M365 E5 Information Protection & Governance SKU. Office 365 Advanced Compliance SKU non è più disponibile per la distribuzione di nuove licenze. Le licenze di Office 365 Advanced Compliance esistenti continueranno a essere supportate.

Per comprendere i concetti e le procedure descritti in questo articolo, consultare la documentazione [di Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/) Inoltre, acquisire familiarità con i termini usati in Azure, ad esempio, [tenant di Azure AD.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)

FastTrack viene usato solo per raccogliere le informazioni di configurazione del tenant e del servizio necessarie per la registrazione per Customer Key. Le offerte customer key vengono pubblicate tramite FastTrack in modo che sia comodo per l'utente e i partner inviare le informazioni necessarie con lo stesso metodo. FastTrack semplifica inoltre l'archiviazione dei dati forniti nell'offerta.
  
Se è necessario ulteriore supporto oltre alla documentazione, contattare Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o un partner Microsoft per assistenza. Per fornire feedback su Customer Key, inclusa la documentazione, invia idee, suggerimenti e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Panoramica della procedura per configurare Customer Key

Per configurare Customer Key, completa queste attività nell'ordine indicato. Il resto di questo articolo fornisce istruzioni dettagliate per ogni attività o collegamenti a ulteriori informazioni per ogni passaggio del processo.
  
**In Azure e Microsoft FastTrack:**
  
La maggior parte di queste attività verrà completata connettendosi in remoto ad Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.
  
- [Creare due nuove sottoscrizioni di Azure](#create-two-new-azure-subscriptions)

- [Registrare le sottoscrizioni di Azure per usare un periodo di conservazione obbligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  La registrazione può richiedere da uno a cinque giorni lavorativi.

- [Inviare una richiesta per attivare customer key per Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Dopo aver creato le due nuove sottoscrizioni di Azure, è necessario inviare la richiesta di offerta customer key appropriata compilando un modulo Web ospitato nel portale di Microsoft FastTrack. **Il team di FastTrack non fornisce assistenza con Customer Key. Office usa semplicemente il portale FastTrack per** consentire l'invio del modulo e per consentirci di tenere traccia delle offerte rilevanti per Customer Key.

- [Creare un Azure Key Vault premium in ogni sottoscrizione](#create-a-premium-azure-key-vault-in-each-subscription)

- [Assegnare autorizzazioni a ogni insieme di credenziali delle chiavi](#assign-permissions-to-each-key-vault)

- [Abilitare e quindi confermare l'eliminazione rescisa nei key vault](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Aggiungere una chiave a ogni insieme di credenziali delle chiavi creando o importando una chiave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Controllare il livello di ripristino delle chiavi](#check-the-recovery-level-of-your-keys)

- [Eseguire il backup di Azure Key Vault](#back-up-azure-key-vault)

- [Convalidare le impostazioni di configurazione di Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Ottenere l'URI per ogni chiave di Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)

**In Office 365:**
  
Exchange Online e Skype for Business:
  
- [Creare un criterio di crittografia dei dati da utilizzare con Exchange Online e Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Assegnare protezione esecuzione programmi a una cassetta postale](#assign-a-dep-to-a-mailbox)

- [Convalidare la crittografia delle cassette postali](#validate-mailbox-encryption)

SharePoint Online e OneDrive for Business:
  
- [Creare un criterio di crittografia dei dati per ogni area geografica di SharePoint Online e OneDrive for Business](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Convalidare la crittografia dei file di SharePoint Online, OneDrive for Business e Teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completare le attività in Azure Key Vault e Microsoft FastTrack per Customer Key

Completare queste attività in Azure Key Vault. You'll need to complete these steps regard of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure

Customer Key richiede due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di creare nuove sottoscrizioni di Azure da usare con Customer Key. Le chiavi di Azure Key Vault possono essere autorizzate solo per le applicazioni nello stesso tenant di Azure Active Directory (Microsoft Azure Active Directory), è necessario creare le nuove sottoscrizioni usando lo stesso tenant di Azure AD usato con l'organizzazione a cui verranno assegnati i criteri di configurazione. Ad esempio, usando l'account aziendale o dell'istituto di istruzione con privilegi di amministratore globale nell'organizzazione. Per la procedura dettagliata, vedere [Iscriversi ad Azure come organizzazione.](https://azure.microsoft.com/documentation/articles/sign-up-organization/)
  
> [!IMPORTANT]
> Customer Key richiede due chiavi per ogni criterio di crittografia dei dati. Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di avere membri separati dell'organizzazione per configurare una chiave in ogni abbonamento. È consigliabile usare queste sottoscrizioni di Azure solo per amministrare le chiavi di crittografia per Office 365. Ciò protegge l'organizzazione nel caso in cui uno degli operatori elimini accidentalmente, intenzionalmente o in modo dannoso o in altro modo le chiavi di cui sono responsabili.
>

Non esiste un limite pratico al numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguendo queste procedure consigliate è possibile ridurre al minimo l'impatto dell'errore umano e allo stesso tempo gestire le risorse usate da Customer Key.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Inviare una richiesta per attivare customer key per Office 365

Dopo aver completato i passaggi di Azure, è necessario inviare una richiesta di offerta nel portale [di Microsoft FastTrack.](https://fasttrack.microsoft.com/) Dopo aver inviato una richiesta tramite il portale Web di FastTrack, Microsoft verifica i dati di configurazione di Azure Key Vault e le informazioni di contatto fornite. Le selezioni che si effettuano nel modulo dell'offerta relative ai responsabili autorizzati dell'organizzazione sono fondamentali e necessarie per il completamento della registrazione del codice Cliente. I responsabili dell'organizzazione garantiscono l'autenticità di qualsiasi richiesta di revoca e di eliminazione di tutte le chiavi usate con un criterio di crittografia dei dati customer key. È necessario eseguire questo passaggio una volta per attivare la copertura Customer Key per Exchange Online e Skype for Business e una seconda volta per attivare Customer Key per SharePoint Online e OneDrive for Business.
  
Per inviare un'offerta per attivare customer key, completa questi passaggi:
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, accedere al portale [di Microsoft FastTrack.](https://fasttrack.microsoft.com/)

2. Dopo aver eseguito l'accesso, passare al **dashboard.**

3. Choose **Deploy** from the navigation bar **OR** select View all **deployment resources** on the **Deploy** information card, and review the list of current offers.

4. Scegli la scheda informazioni per l'offerta che ti si applica:

   - **Exchange Online e Skype for Business:** Scegliere la **Guida per richiedere la chiave di crittografia per l'offerta Exchange Online.**

   - **File di SharePoint Online, OneDrive e Teams:** Scegliere **l'offerta Richiedi chiave di crittografia per Sharepoint e OneDrive.**

5. Dopo aver esaminato i dettagli dell'offerta, scegliere **Continua al passaggio 2.**

6. Compila tutti i dettagli applicabili e le informazioni richieste nel modulo dell'offerta. Prestare particolare attenzione alle selezioni dei responsabili dell'organizzazione che si desidera autorizzare ad approvare la distruzione permanente e irreversibile di chiavi e dati di crittografia. Dopo aver completato il modulo, scegliere **Invia.**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per usare un periodo di conservazione obbligatorio

La perdita temporanea o permanente delle chiavi di crittografia radice può essere dannosa o addirittura catastrofica per il funzionamento del servizio e può causare la perdita di dati. Per questo motivo, le risorse usate con Customer Key richiedono una protezione avanzata. Tutte le risorse di Azure usate con Customer Key offrono meccanismi di protezione oltre la configurazione predefinita. È possibile contrassegnare o registrare le sottoscrizioni di Azure per un *periodo di conservazione obbligatorio.* Un periodo di conservazione obbligatorio impedisce l'annullamento immediato e irrevocabile della sottoscrizione di Azure. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con il team di Microsoft 365. Questo processo può richiedere da uno a cinque giorni lavorativi. In precedenza, il periodo di conservazione obbligatorio era talvolta denominato "Non annullare".
  
Prima di contattare il team di Microsoft 365, è necessario eseguire la procedura seguente per ogni sottoscrizione di Azure utilizzata con Customer Key. Assicurarsi di aver installato il [modulo Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) prima di iniziare.
  
1. Accedere con Azure PowerShell. Per istruzioni, vedere [Accedere con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Eseguire il cmdlet Register-AzProviderFeature per registrare le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio. Completare questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contattare Microsoft per completare il processo. Per il team di SharePoint e OneDrive for Business, contattare [spock@microsoft.com.](mailto:spock@microsoft.com) Per Exchange Online e Skype for Business, contattare [exock@microsoft.com.](mailto:exock@microsoft.com) Includere le informazioni seguenti nel messaggio di posta elettronica:

   **Oggetto**: Codice Cliente per \<*Your tenant's fully qualified domain name*\>

   **Corpo:** includere gli ID sottoscrizione per i quali si desidera completare il periodo di conservazione obbligatorio e l'output Get-AzProviderFeature per ogni sottoscrizione.

   Il contratto di servizio per il completamento di questo processo è di cinque giorni lavorativi dopo che Microsoft ha notificato (e verificato) di aver registrato le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio.

4. Una volta ricevuta la notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il Get-AzProviderFeature seguente. Se verificato, il Get-AzProviderFeature restituisce il valore **Registered** per la **proprietà Registration State.** Completare questo passaggio per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Per completare il processo, eseguire il Register-AzResourceProvider seguente. Completare questo passaggio per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un Azure Key Vault premium in ogni sottoscrizione

I passaggi per creare un insieme di credenziali delle chiavi sono documentati in Introduzione a [Azure Key Vault,](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)che guida l'utente nell'installazione e nell'avvio di Azure PowerShell, nella connessione alla sottoscrizione di Azure, nella creazione di un gruppo di risorse e nella creazione di un insieme di credenziali delle chiavi in tale gruppo di risorse.
  
Quando si crea un insieme di credenziali delle chiavi, è necessario scegliere uno SKU: Standard o Premium. Lo SKU standard consente di proteggere le chiavi dell'insieme di credenziali delle chiavi di Azure con il software ( non esiste alcuna protezione delle chiavi HSM (Hardware Security Module) e lo SKU Premium consente l'uso di HMS per la protezione delle chiavi key vault. Customer Key accetta gli insiemi di credenziali delle chiavi che usano uno degli SKU, anche se Microsoft consiglia vivamente di usare solo lo SKU Premium. Il costo delle operazioni con le chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo mensile per ogni chiave protetta da HSM. Per informazioni [dettagliate, vedi](https://azure.microsoft.com/pricing/details/key-vault/) i prezzi di Key Vault.
  
> [!IMPORTANT]
> Usa gli insiemi di credenziali delle chiavi SKU Premium e le chiavi protette con HSM per i dati di produzione e usa le chiavi e gli insiemi di credenziali delle chiavi SKU standard solo a scopo di test e convalida.
  
Per ogni servizio di Microsoft 365 con cui si userà Customer Key, creare un insieme di credenziali delle chiavi in ognuna delle due sottoscrizioni di Azure create. Ad esempio, solo per Exchange Online e Skype for Business o Solo SharePoint Online e OneDrive for Business, si creerà una sola coppia di insiemi di credenziali. Per abilitare Customer Key sia per Exchange Online che per SharePoint Online, verranno create due coppie di insiemi di credenziali delle chiavi.
  
Utilizzare una convenzione di denominazione per gli insiemi di credenziali delle chiavi che rifletta l'utilizzo previsto di Protezione esecuzione programmi a cui verranno associati gli insiemi di credenziali. Per suggerimenti sulle convenzioni di denominazione, vedere la sezione Procedure consigliate di seguito.
  
Creare un set separato di insiemi di credenziali associati per ogni criterio di crittografia dei dati. Per Exchange Online, l'ambito di un criterio di crittografia dei dati viene scelto dall'utente quando si assegna il criterio alla cassetta postale. A una cassetta postale può essere assegnato un solo criterio ed è possibile creare fino a 50 criteri. L'ambito di un criterio di SharePoint Online include tutti i dati all'interno di un'organizzazione in una posizione geografica o _geografica._

La creazione di insiemi di credenziali delle chiavi richiede anche la creazione di gruppi di risorse di Azure, poiché gli insiemi di credenziali delle chiavi necessitano di capacità di archiviazione (anche se di piccole dimensioni) e la registrazione key vault, se abilitata, genera anche dati archiviati. Come procedura consigliata, Microsoft consiglia di utilizzare amministratori separati per gestire ogni gruppo di risorse, con l'amministrazione allineata al set di amministratori che gestirà tutte le risorse chiave del cliente correlate.
  
> [!IMPORTANT]
> Per ottimizzare la disponibilità, gli insiemi di credenziali delle chiavi devono essere in aree geografiche vicine al servizio Microsoft 365. Ad esempio, se l'organizzazione di Exchange Online si trova in Nord America, posizionare gli insiemi di credenziali delle chiavi in Nord America. Se l'organizzazione di Exchange Online si trova in Europa, posizionare gli insiemi di credenziali delle chiavi in Europa.
> 
> Utilizzare un prefisso comune per gli insiemi di credenziali delle chiavi e includere un'abbreviazione dell'utilizzo e dell'ambito dell'insieme di credenziali e delle chiavi (ad esempio, per il servizio Di Contoso SharePoint in cui si trovano gli insiemi di credenziali in Nord America, una possibile coppia di nomi è Contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. I nomi dell'insieme di credenziali sono stringhe univoche globali all'interno di Azure, quindi potrebbe essere necessario provare le varianti dei nomi desiderati nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. A partire da luglio 2017 i nomi degli insiemi di credenziali non possono essere modificati, quindi è consigliabile disporre di un piano scritto per la configurazione e utilizzare una seconda persona per verificare che il piano venga eseguito correttamente.
> 
> Se possibile, creare gli insiemi di credenziali in aree non abbinate. Le aree di Azure abbinate offrono disponibilità elevata tra i domini di errore del servizio. Pertanto, le coppie regionali possono essere ritenute come l'area di backup reciproca. Ciò significa che una risorsa di Azure posizionata in un'area ottiene automaticamente la tolleranza di errore attraverso l'area associata. Per questo motivo, la scelta delle aree per due insiemi di credenziali utilizzati in un criterio di crittografia dei dati in cui le aree sono accoppiate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle aree geografiche ha solo due aree, quindi non è ancora possibile selezionare aree non abbinate. Se possibile, scegliere due aree non associate per i due insiemi di credenziali utilizzati con un criterio di crittografia dei dati. Questo vantaggio deriva da un totale di quattro aree di disponibilità. Per altre informazioni, vedere Continuità aziendale e ripristino di emergenza [(BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) aree associate di Azure per un elenco corrente di coppie regionali.
  
### <a name="assign-permissions-to-each-key-vault"></a>Assegnare autorizzazioni a ogni insieme di credenziali delle chiavi

Dovrai definire tre set separati di autorizzazioni per ogni insieme di credenziali delle chiavi, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori dell'insieme di** credenziali chiave che eseauno la gestione quotidiana dell'insieme di credenziali delle chiavi per l'organizzazione. Queste attività includono il backup, la creazione, il ripristino, l'importazione, l'elenco e il ripristino.

  > [!IMPORTANT]
  > Il set di autorizzazioni assegnate agli amministratori dell'insieme di credenziali delle chiavi non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una pratica intenzionale e importante. L'eliminazione delle chiavi di crittografia in genere non viene eseguita, poiché in questo modo vengono eliminati definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori dell'insieme di credenziali chiave per impostazione predefinita. Al contrario, riservarlo ai collaboratori chiave dell'insieme di credenziali e assegnarlo a un amministratore solo a breve termine una volta compreso chiaramente le conseguenze.
  
  Per assegnare queste autorizzazioni a un utente dell'organizzazione, accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [Accedere con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- Eseguire il cmdlet Set-AzKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Ad esempio:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Collaboratori dell'insieme di credenziali** chiave che possono modificare le autorizzazioni nell'Insieme di credenziali chiavi di Azure stesso. Sarà necessario modificare queste autorizzazioni quando i dipendenti lasciano o si uniscono al team. Nella rara situazione in cui gli amministratori dell'insieme di credenziali delle chiavi necessitano legittimamente dell'autorizzazione per eliminare o ripristinare una chiave, sarà necessario modificare anche le autorizzazioni. A questo set di collaboratori dell'insieme di credenziali chiave deve essere concesso il **ruolo Collaboratore** nell'insieme di credenziali delle chiavi. È possibile assegnare questo ruolo usando Azure Resource Manager. Per la procedura dettagliata, vedere Usare il Role-Based di accesso [per gestire l'accesso alle risorse di sottoscrizione di Azure.](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) L'amministratore che crea una sottoscrizione dispone implicitamente di questo accesso e della possibilità di assegnare altri amministratori al ruolo Collaboratore.

- Se si intende usare Customer Key con Exchange Online e Skype for Business, è necessario concedere l'autorizzazione a Microsoft 365 per usare l'insieme di credenziali delle chiavi per conto di Exchange Online e Skype for Business. Analogamente, se si intende usare Customer Key con SharePoint Online e OneDrive for Business, è necessario aggiungere l'autorizzazione per Microsoft 365 per usare l'insieme di credenziali delle chiavi per conto di SharePoint Online e OneDrive for Business. Per concedere l'autorizzazione a Microsoft 365, eseguire il cmdlet **Set-AzKeyVaultAccessPolicy** utilizzando la sintassi seguente:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dove:

    - *il nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi creato.

    - Per Exchange Online e Skype for Business, sostituire  *l'APPID di Office 365* con `00000002-0000-0ff1-ce00-000000000000`

    - Per i file di SharePoint Online, OneDrive for Business e Teams, sostituire  *l'APPID di Office 365* con `00000003-0000-0ff1-ce00-000000000000`

  Esempio: Impostazione delle autorizzazioni per Exchange Online e Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Esempio: Impostazione delle autorizzazioni per i file di SharePoint Online, OneDrive for Business e Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare e quindi confermare l'eliminazione rescisa nei key vault

Quando è possibile ripristinare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi eliminate accidentalmente o in modo dannoso. Devi abilitare questa configurazione, definita eliminazione recisa, prima di poter usare le chiavi con Customer Key. L'abilitazione dell'eliminazione soft consente di recuperare chiavi o insiemi di credenziali entro 90 giorni dall'eliminazione senza doverle ripristinare dal backup.
  
Per abilitare l'eliminazione recisa nei key vault, eseguire la procedura seguente:
  
1. Accedere alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [Accedere con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Eseguire il cmdlet [Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) In questo esempio, *il nome dell'insieme di* credenziali è il nome dell'insieme di credenziali delle chiavi per cui si abilita l'eliminazione rescisa:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Verificare che l'eliminazione soft sia configurata per l'insieme di credenziali delle chiavi eseguendo il cmdlet **Get-AzKeyVault.** Se l'eliminazione soft è configurata correttamente per l'insieme di credenziali delle chiavi, la proprietà _Soft Delete Enabled_ restituisce il valore **True:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Aggiungere una chiave a ogni insieme di credenziali delle chiavi creando o importando una chiave

Esistono due modi per aggiungere chiavi a un insieme di credenziali delle chiavi di Azure; è possibile creare una chiave direttamente in Key Vault oppure importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave offre il controllo totale sulla modalità di generazione della chiave. Utilizzare le chiavi RSA. Azure Key Vault non supporta il wrapping e l'annullamento del wrapping con chiavi curva ellittiche.
  
Per creare una chiave direttamente nell'insieme di credenziali delle chiavi, eseguire il cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) nel modo seguente:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dove:

- *il nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi in cui si desidera creare la chiave.

- *key name* è il nome che si desidera assegnare alla nuova chiave.

  > [!TIP]
  > Assegnare un nome alle chiavi usando una convenzione di denominazione simile a quella descritta in precedenza per gli insiemi di credenziali delle chiavi. In questo modo, negli strumenti che mostrano solo il nome della chiave, la stringa è autodescrittura.
  
Se intendi proteggere la chiave con un HSM, assicurati di specificare **HSM** come valore del parametro _Destination,_ altrimenti specifica **Software.**

Ad esempio,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Per importare una chiave direttamente nell'insieme di credenziali delle chiavi, è necessario disporre di un modulo di sicurezza hardware nCipher nShield.
  
Alcune organizzazioni preferiscono questo approccio per stabilire la provenienza delle chiavi, quindi questo metodo fornisce anche le attestazioni seguenti:
  
- Il set di strumenti utilizzato per l'importazione include l'attestazione da nCipher che la chiave di scambio delle chiavi (KEK) utilizzata per crittografare la chiave generata non è esportabile e viene generata all'interno di un HSM originale prodotto da nCipher.

- Il set di strumenti include l'attestazione da nCipher che il mondo della sicurezza di Azure Key Vault è stato generato anche su un HSM originale prodotto da nCipher. Questa attestazione dimostra che Microsoft usa anche hardware nCipher originale.

Rivolgersi al gruppo di sicurezza per determinare se sono necessarie le attestazioni precedenti. Per la procedura dettagliata per creare una chiave locale e importarla nell'insieme di credenziali delle chiavi, vedere Come generare e trasferire chiavi protette con HSM per [Azure Key Vault.](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) Usa le istruzioni di Azure per creare una chiave in ogni insieme di credenziali delle chiavi.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi

Microsoft 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su Non annullare e che le chiavi usate da Customer Key sia abilitata l'eliminazione rescisa. Puoi confermare le impostazioni delle sottoscrizioni esaminando il livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di una chiave, in Azure PowerShell, eseguire il cmdlet Get-AzKeyVaultKey seguente:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se la proprietà _Recovery Level_ restituisce un valore diverso dal valore **Recoverable+ProtectedSubscription,** verificare di aver inserito la sottoscrizione nell'elenco Do Not Cancel e di aver abilitato l'eliminazione reversibile in ognuno degli insiemi di credenziali delle chiavi.
  
### <a name="back-up-azure-key-vault"></a>Eseguire il backup di Azure Key Vault

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Le copie offline non devono essere connesse ad alcuna rete, ad esempio in una struttura di archiviazione fisica sicura o commerciale. Almeno una copia del backup deve essere archiviata in un percorso accessibile in caso di emergenza. I BLOB di backup sono l'unico mezzo per ripristinare il materiale delle chiavi nel caso in cui una chiave dell'insieme di credenziali delle chiavi sia definitivamente distrutta o altrimenti resa inoperabile. Le chiavi esterne a Azure Key Vault e importate in Azure Key Vault non sono qualificate come backup perché i metadati necessari per l'uso della chiave da parte di Customer Key non esistono con la chiave esterna. Solo un backup eseguito da Azure Key Vault può essere usato per le operazioni di ripristino con Customer Key. Pertanto, è necessario creare un backup di Azure Key Vault dopo aver caricato o creato una chiave.
  
Per creare un backup di una chiave di Azure Key Vault, eseguire il cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) nel modo seguente:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verificare che il file di output utilizzi il suffisso `.backup` .
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno di Azure Key Vault. Il backup può essere ripristinato solo nella sottoscrizione di Azure da cui è stato eseguito il backup.
  
> [!TIP]
> Per il file di output, scegli una combinazione del nome dell'insieme di credenziali e del nome della chiave. In questo modo il nome del file verrà autodescritto. Garantisce inoltre che i nomi dei file di backup non collidono.
  
Ad esempio:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Convalidare le impostazioni di configurazione di Azure Key Vault

La convalida prima di usare le chiavi in Protezione esecuzione programmi è facoltativa, ma è consigliabile. Se usi la procedura per configurare le chiavi e gli insiemi di credenziali diversi da quelli descritti in questo articolo, convalida l'integrità delle risorse di Azure Key Vault prima di configurare Customer Key.
  
Per verificare che le chiavi siano `get` `wrapKey` abilitate, e le `unwrapKey` operazioni:
  
Eseguire il cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) nel modo seguente:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Nell'output, cercare i criteri di accesso e l'identità (GUID) di Exchange Online o l'identità di SharePoint Online (GUID) in base alle esigenze. Tutte e tre le autorizzazioni precedenti devono essere visualizzate in Autorizzazioni per le chiavi.
  
Se la configurazione dei criteri di accesso non è corretta, eseguire il cmdlet Set-AzKeyVaultAccessPolicy seguente:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Ad esempio, per Exchange Online e Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Ad esempio, per SharePoint Online e OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) nel modo seguente:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Customer Key non può usare un codice scaduto. Le operazioni tentate con una chiave scaduta avranno esito negativo e potrebbero causare un'interruzione del servizio. Ti consigliamo vivamente che le chiavi usate con Customer Key non abbia una data di scadenza. Una data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con una data di scadenza impostata, modificare il valore di scadenza in 31/12/9999. Le chiavi con una data di scadenza impostata su una data diversa dal 31/12/9999 non supereranno la convalida di Microsoft 365.
  
Per modificare una data di scadenza impostata su un valore diverso dal 31/12/9999, eseguire il cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) nel modo seguente:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Non impostare date di scadenza per le chiavi di crittografia usate con Customer Key.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave di Azure Key Vault

Dopo aver configurato gli insiemi di credenziali delle chiavi e aver aggiunto le chiavi, eseguire il comando seguente per ottenere l'URI per la chiave in ogni insieme di credenziali delle chiavi. Dovrai usare questi URI quando crei e assegni ogni protezione esecuzione programmi in un secondo momento, quindi salva queste informazioni in un luogo sicuro. Eseguire questo comando una volta per ogni insieme di credenziali delle chiavi.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Configurazione di Customer Key per Exchange Online e Skype for Business

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare Azure Key Vault. Per informazioni, vedere Completare [le attività in Azure Key Vault e Microsoft FastTrack per Customer Key.](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)
  
Per configurare Customer Key per Exchange Online e Skype for Business, completare questi passaggi connettendosi in remoto a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Creare un criterio di crittografia dei dati da utilizzare con Exchange Online e Skype for Business

Protezione esecuzione programmi è associato a un set di chiavi archiviate in Azure Key Vault. È possibile assegnare protezione esecuzione programmi a una cassetta postale in Microsoft 365. Microsoft 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare Protezione esecuzione programmi, sono necessari gli URI key vault ottenuti in precedenza. Per istruzioni, vedere Ottenere [l'URI per ogni chiave di Azure Key Vault.](#obtain-the-uri-for-each-azure-key-vault-key)
  
Ricordati! Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi Insiemi di credenziali delle chiavi di Azure. Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare Protezione esecuzione programmi, attenersi alla seguente procedura:
  
1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) di Exchange Online in una Windows PowerShell predefinita.

2. Per creare una protezione esecuzione programmi, utilizzare New-DataEncryptionPolicy cmdlet digitando il comando seguente.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dove:

   - *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.

   - *Descrizione* criterio è una descrizione descrittiva del criterio che consente di ricordare a cosa è fatto il criterio. È possibile includere spazi nella descrizione. Ad esempio, "Chiave radice per le cassette postali negli Stati Uniti e nei relativi territori".

   - *KeyVaultURI1* è l'URI per la prima chiave nel criterio. Ad esempio, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* è l'URI della seconda chiave nel criterio. Ad esempio, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separare i due URI con una virgola e uno spazio.

   Esempio:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-DataEncryptionPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>Assegnare protezione esecuzione programmi a una cassetta postale

Assegnare Protezione esecuzione programmi a una cassetta postale utilizzando Set-Mailbox cmdlet. Dopo aver assegnato il criterio, Microsoft 365 può crittografare la cassetta postale con la chiave identificata in Protezione esecuzione programmi.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailboxIdParameter specifica* una cassetta postale utente. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)

Negli ambienti ibridi, è possibile assegnare protezione esecuzione programmi ai dati delle cassette postali locali sincronizzati nel tenant di Exchange Online. Per assegnare protezione esecuzione programmi ai dati sincronizzati della cassetta postale, utilizzare il cmdlet Set-MailUser. Per ulteriori informazioni sui dati delle cassette postali nell'ambiente ibrido, vedere cassette postali locali che utilizzano Outlook per iOS e [Android con l'autenticazione moderna ibrida.](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailUserIdParameter* specifica un utente di posta (noto anche come utente abilitato alla posta). Per ulteriori informazioni sul cmdlet Set-MailUser, vedere [Set-MailUser.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)
  
### <a name="validate-mailbox-encryption"></a>Convalidare la crittografia delle cassette postali

La crittografia di una cassetta postale può richiedere del tempo. Per la prima assegnazione dei criteri, la cassetta postale deve inoltre spostarsi completamente da un database a un altro prima che il servizio possa crittografare la cassetta postale. Si consiglia di attendere 72 ore prima di tentare di convalidare la crittografia dopo la modifica di Protezione esecuzione programmi o la prima volta che si assegna protezione esecuzione programmi a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata. Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui si assegna protezione esecuzione programmi per la prima volta e dalle dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stato assegnato Protezione esecuzione programmi, contattare Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: Configurazione di Customer Key per i file di SharePoint Online, OneDrive for Business e Teams

Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare Azure Key Vault. Per informazioni, vedere Completare [le attività in Azure Key Vault e Microsoft FastTrack per Customer Key.](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)
  
Per configurare Customer Key per i file di SharePoint Online, OneDrive for Business e Teams, completare questi passaggi connettendosi in remoto a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Creare un criterio di crittografia dei dati per ogni area geografica di SharePoint Online e OneDrive for Business

È possibile associare protezione esecuzione programmi a un set di chiavi archiviate in Azure Key Vault. È possibile applicare protezione esecuzione programmi a tutti i dati in una posizione geografica, detta anche geo. Se si usa la funzionalità multi-geo di Office 365, è possibile creare una protezione esecuzione programmi per ogni area geografica con la possibilità di usare chiavi diverse per ogni area geografica. Se non si usa multi-geo, è possibile creare una protezione esecuzione programmi nell'organizzazione per l'uso con i file di SharePoint Online, OneDrive for Business e Teams. Microsoft 365 usa le chiavi identificate in Protezione esecuzione programmi per crittografare i dati in tale area geografica. Per creare Protezione esecuzione programmi, sono necessari gli URI key vault ottenuti in precedenza. Per istruzioni, vedere Ottenere [l'URI per ogni chiave di Azure Key Vault.](#obtain-the-uri-for-each-azure-key-vault-key)
  
Ricordati! Quando si crea una protezione esecuzione programmi, si specificano due chiavi in due diversi Insiemi di credenziali delle chiavi di Azure. Creare queste chiavi in due aree di Azure separate per garantire la ridondanza geografica.
  
Per creare una protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online usando Windows PowerShell.
  
1. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [PowerShell di SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)

2. In Microsoft SharePoint Online Management Shell eseguire il cmdlet Register-SPODataEncryptionPolicy seguente:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Esempio:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Quando si registra Protezione esecuzione programmi, la crittografia inizia sui dati nella posizione geografica. La crittografia può richiedere del tempo. Per ulteriori informazioni sull'utilizzo di questo parametro, [vedere Register-SPODataEncryptionPolicy.](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true)

### <a name="validate-file-encryption"></a>Convalidare la crittografia dei file

 Per convalidare la crittografia dei file di SharePoint Online, OneDrive for Business e Teams, connettersi a PowerShell di [SharePoint Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)e quindi utilizzare il cmdlet Get-SPODataEncryptionPolicy per controllare lo stato del tenant. La _proprietà State_ restituisce un valore registrato **se** la crittografia Customer Key è abilitata e tutti i file in tutti i siti sono stati crittografati. Se la crittografia è ancora in corso, questo cmdlet restituisce il valore **di registrazione**.

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Gestire Customer Key](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Crittografia del servizio](office-365-service-encryption.md)
