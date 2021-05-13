---
title: Configurare il codice "Customer Key"
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Scopri come configurare il codice "Customer Key" per Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344675"
---
# <a name="set-up-customer-key"></a>Configurare il codice "Customer Key"

Con Customer Key puoi controllare le chiavi di crittografia dell'organizzazione e quindi configurare Microsoft 365 per usarle per crittografare i dati in pausa nei data center di Microsoft. In altre parole, Customer Key consente ai clienti di aggiungere un livello di crittografia che appartiene a loro, con le loro chiavi.

Configurare Azure prima di poter usare customer key per Office 365. In questo articolo vengono descritti i passaggi da eseguire per creare e configurare le risorse di Azure necessarie e vengono quindi illustrati i passaggi per la configurazione del codice "Customer Key" in Office 365. Dopo aver configurato Azure, è possibile determinare quali criteri e quindi quali chiavi assegnare per crittografare i dati in vari carichi di lavoro Microsoft 365 nell'organizzazione. Per ulteriori informazioni su Customer Key o per una panoramica generale, vedere [Service encryption with Customer Key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> È consigliabile seguire le procedure consigliate in questo articolo. Questi sono chiamati **TIP e** **IMPORTANT**. Customer Key consente di controllare le chiavi di crittografia radice il cui ambito può essere grande quanto l'intera organizzazione. Ciò significa che gli errori commersi con queste chiavi possono avere un impatto generale e possono causare interruzioni del servizio o perdita irrevocabile dei dati.
  
## <a name="before-you-set-up-customer-key"></a>Prima di configurare customer key

Prima di iniziare, assicurarsi di disporre delle sottoscrizioni e delle licenze di Azure appropriate per l'organizzazione. Usare sottoscrizioni di Azure a pagamento usando un Enterprise Agreement o un provider di servizi cloud. I pagamenti basati su carta di credito non vengono accettati. Approvare e configurare le esigenze dell'account per la fatturazione. Le sottoscrizioni che hai ottenuto tramite Gratuito, Versione di valutazione, Sponsorizzazioni, Abbonamenti MSDN e quelle con supporto legacy non sono idonee.

Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance e Microsoft 365 E5 Information Protection & Governance SKU offrono Customer Key. Office 365 Advanced Compliance SKU non è più disponibile per la procura di nuove licenze. Le Office 365 Advanced Compliance esistenti continueranno a essere supportate.

Per comprendere i concetti e le procedure descritti in questo articolo, consultare la documentazione relativa a [Azure Key Vault.](/azure/key-vault/) Inoltre, acquisire familiarità con i termini usati in Azure, ad esempio tenant [di Azure AD.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)
  
Se è necessario ulteriore supporto oltre alla documentazione, contattare Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o un partner Microsoft per assistenza. Per fornire commenti e suggerimenti sul codice "Customer Key", inclusa la documentazione, invia idee, suggerimenti e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Panoramica della procedura per configurare customer key

Per configurare customer key, completare queste attività nell'ordine indicato. Il resto di questo articolo fornisce istruzioni dettagliate per ogni attività o collegamenti a ulteriori informazioni per ogni passaggio del processo.
  
**In Azure e Microsoft FastTrack:**
  
La maggior parte di queste attività verrà completata connettendosi in remoto a Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.
  
- [Creare due nuove sottoscrizioni di Azure](#create-two-new-azure-subscriptions)

- [Inviare una richiesta per attivare il codice "Customer Key" per Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [Registrare le sottoscrizioni di Azure per usare un periodo di conservazione obbligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  La registrazione può richiedere da uno a cinque giorni lavorativi.

- [Creare un azure key vault premium in ogni sottoscrizione](#create-a-premium-azure-key-vault-in-each-subscription)

- [Assegnare autorizzazioni a ogni insieme di credenziali delle chiavi](#assign-permissions-to-each-key-vault)

- [Assicurarsi che l'eliminazione soft sia abilitata nei vault delle chiavi](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Aggiungere una chiave a ogni insieme di credenziali delle chiavi creando o importando una chiave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Controllare il livello di ripristino delle chiavi](#check-the-recovery-level-of-your-keys)

- [Eseguire il backup di Azure Key Vault](#back-up-azure-key-vault)

- [Convalidare le impostazioni di configurazione di Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Ottenere l'URI per ogni chiave di Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completare le attività in Azure Key Vault e Microsoft FastTrack for Customer Key

Completare queste attività in Azure Key Vault. Dovrai completare questi passaggi per tutti i dep che usi con Customer Key.
  
### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure

Customer Key richiede due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di creare nuove sottoscrizioni di Azure da usare con customer key. Le chiavi dell'insieme di credenziali delle chiavi di Azure possono essere autorizzate solo per le applicazioni nello stesso tenant di Azure Active Directory (Microsoft Azure Active Directory), è necessario creare le nuove sottoscrizioni usando lo stesso tenant di Azure AD usato con l'organizzazione a cui verranno assegnati i criteri di configurazione. Ad esempio, utilizzando l'account aziendale o dell'istituto di istruzione con privilegi di amministratore globale nell'organizzazione. Per la procedura dettagliata, vedere [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).
  
> [!IMPORTANT]
> Customer Key richiede due chiavi per ogni criterio di crittografia dei dati (DEP). Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri separati dell'organizzazione per configurare una chiave in ogni sottoscrizione. È consigliabile usare queste sottoscrizioni di Azure solo per amministrare le chiavi di crittografia per Office 365. Questo protegge l'organizzazione nel caso in cui uno degli operatori elimini accidentalmente, intenzionalmente o in modo dannoso o in altro modo maneggio le chiavi di cui sono responsabili.

Non esiste un limite pratico al numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguire queste procedure consigliate ridurrà al minimo l'impatto dell'errore umano, contribuendo al contempo a gestire le risorse utilizzate da Customer Key.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Inviare una richiesta per attivare il codice "Customer Key" per Office 365

Dopo aver creato le due nuove sottoscrizioni di Azure, dovrai inviare la richiesta di offerta codice cliente appropriata nel portale [Microsoft FastTrack.](https://fasttrack.microsoft.com/) Le selezioni apportate nel modulo dell'offerta relative alle designazioni autorizzate all'interno dell'organizzazione sono fondamentali e necessarie per il completamento della registrazione del codice Cliente. I responsabili dei ruoli selezionati all'interno dell'organizzazione garantiscono l'autenticità di qualsiasi richiesta di revocare ed eliminare tutte le chiavi utilizzate con un criterio di crittografia dei dati chiave cliente. È necessario eseguire questo passaggio una volta per ogni tipo di protezione esecuzione programmi customer key che si intende utilizzare per l'organizzazione.

**Il team di FastTrack non fornisce assistenza con Customer Key. Office 365 usa semplicemente il portale FastTrack per consentire l'invio del modulo e per consentirci di tenere traccia delle offerte pertinenti per customer key. Dopo aver inviato la richiesta FastTrack, contatta il team di onboarding customer key corrispondente per avviare il processo di onboarding.**
  
Per inviare un'offerta per attivare il codice "Customer Key", completare la procedura seguente:
  
1. Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, accedere al portale [Microsoft FastTrack.](https://fasttrack.microsoft.com/)

2. Dopo aver effettuato l'accesso, selezionare il dominio appropriato.

3. Per il dominio selezionato, scegliere **Richiedi servizi** dalla barra di spostamento superiore ed esaminare l'elenco delle offerte disponibili.

4. Scegli la scheda informazioni per l'offerta che ti si applica:

   - **Più Microsoft 365 di lavoro:** Scegliere richiedi **assistenza per la chiave di crittografia Microsoft 365** offerta.

   - **Exchange Online e Skype for Business:** Scegliere richiedi **assistenza per la chiave di crittografia per Exchange** offerta.

   - **SharePoint online, OneDrive e Teams file:** Scegliere richiedi **assistenza per la chiave di crittografia SharePoint e OneDrive for Business** offerta.

5. Dopo aver esaminato i dettagli dell'offerta, scegliere **Continua al passaggio 2.**

6. Compila tutti i dettagli applicabili e le informazioni richieste nel modulo dell'offerta. Prestare particolare attenzione alle selezioni per i responsabili dell'organizzazione che si desidera autorizzare ad approvare la distruzione permanente e irreversibile delle chiavi di crittografia e dei dati. Dopo aver completato il modulo, scegliere **Invia**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni di Azure per usare un periodo di conservazione obbligatorio

La perdita temporanea o permanente delle chiavi di crittografia radice può essere dannosa o addirittura catastrofica per il funzionamento del servizio e può causare la perdita di dati. Per questo motivo, le risorse utilizzate con Customer Key richiedono una protezione avanzata. Tutte le risorse di Azure usate con Customer Key offrono meccanismi di protezione oltre la configurazione predefinita. È possibile contrassegnare o registrare le sottoscrizioni di Azure per un *periodo di conservazione obbligatorio.* Un periodo di conservazione obbligatorio impedisce l'annullamento immediato e irrevocabile della sottoscrizione di Azure. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con Microsoft 365 team. Questo processo può richiedere da uno a cinque giorni lavorativi. In precedenza, il periodo di conservazione obbligatorio era talvolta definito "Non annullare".
  
Prima di contattare il team Microsoft 365, è necessario eseguire la procedura seguente per ogni sottoscrizione di Azure che si usa con Customer Key. Assicurati di avere installato il [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) prima di iniziare.
  
1. Accedi con Azure PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Register-AzProviderFeature per registrare le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio. Completare questa azione per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contattare Microsoft per completare il processo.

   - Per abilitare customer key per l'assegnazione di Protezione esecuzione programmi a singole cassette postali Exchange Online, [contattare exock@microsoft.com](mailto:exock@microsoft.com).

   - Per abilitare customer key per l'assegnazione di dep per crittografare il contenuto di SharePoint Online e OneDrive for Business (inclusi i file Teams) per tutti gli utenti tenant, [contattare spock@microsoft.com](mailto:spock@microsoft.com).

   - Per abilitare customer key per l'assegnazione dei criteri di configurazione per crittografare il contenuto in più carichi di lavoro di Microsoft 365 (Exchange Online, Teams, MIP EDM) per tutti gli utenti tenant, contattare [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).

- Includere le informazioni seguenti nel messaggio di posta elettronica:

   **Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\>

   **Corpo:** includere gli ID sottoscrizione per i quali si desidera completare il periodo di conservazione obbligatorio e l'output Get-AzProviderFeature per ogni sottoscrizione.

   Il Contratto di servizio (SLA) per il completamento di questo processo è di cinque giorni lavorativi dopo che Microsoft ha notificato (e verificato) di aver registrato le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatorio.

4. Una volta ricevuta la notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il comando Get-AzProviderFeature come indicato di seguito. Se verificato, il comando Get-AzProviderFeature restituisce il valore **Registered** per la **proprietà Registration State.** Completare questo passaggio per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Per completare il processo, eseguire il Register-AzResourceProvider comando. Completare questo passaggio per ogni sottoscrizione.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un azure key vault premium in ogni sottoscrizione

I passaggi per creare un insieme di credenziali delle chiavi sono documentati in Introduzione a [Azure Key Vault,](/azure/key-vault/general/overview)che illustra l'installazione e l'avvio di Azure PowerShell, la connessione alla sottoscrizione di Azure, la creazione di un gruppo di risorse e la creazione di un insieme di credenziali chiave in tale gruppo di risorse.
  
Quando si crea un insieme di credenziali delle chiavi, è necessario scegliere una SKU: Standard o Premium. Lo SKU standard consente di proteggere le chiavi dell'insieme di credenziali delle chiavi di Azure con il software ( non esiste alcuna protezione delle chiavi HSM (Hardware Security Module) e la SKU di Premium consente l'uso di HSM per la protezione delle chiavi dell'insieme di credenziali delle chiavi. Customer Key accetta gli insiemi di credenziali delle chiavi che usano una delle due SKU, anche se Microsoft consiglia vivamente di usare solo la chiave Premium SKU. Il costo delle operazioni con chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo mensile per ogni chiave protetta da HSM. Per [informazioni dettagliate, vedere Key Vault pricing.](https://azure.microsoft.com/pricing/details/key-vault/)
  
> [!IMPORTANT]
> Usa gli insiemi Premium chiave SKU e le chiavi protette con HSM per i dati di produzione e usa solo le chiavi e gli insiemi di credenziali delle chiavi SKU standard a scopo di test e convalida.
  
Per ogni Microsoft 365 servizio con cui verrà utilizzato il codice Cliente, creare un insieme di credenziali delle chiavi in ognuna delle due sottoscrizioni di Azure create. Ad esempio, per consentire a Customer Key di utilizzare ISP per gli scenari di Exchange Online, SharePoint Online e multi-carico di lavoro, creerai tre coppie di insiemi di credenziali chiave.
  
Utilizzare una convenzione di denominazione per gli insiemi di credenziali delle chiavi che rifletta l'utilizzo previsto della protezione esecuzione programmi a cui verranno associati gli insiemi di credenziali. Per suggerimenti sulle convenzioni di denominazione, vedere la sezione Procedure consigliate di seguito.
  
Creare un set separato di insiemi di credenziali associati per ogni criterio di crittografia dei dati. Ad Exchange Online, l'ambito di un criterio di crittografia dei dati viene scelto dall'utente quando si assegna il criterio alla cassetta postale. A una cassetta postale può essere assegnato un solo criterio ed è possibile creare fino a 50 criteri. L'ambito di un SharePoint Online include tutti i dati all'interno di un'organizzazione in una posizione geografica o _geografica._ L'ambito di un criterio multi-carico di lavoro include tutti i dati nei carichi di lavoro supportati per tutti gli utenti.

La creazione degli insiemi di credenziali delle chiavi richiede anche la creazione di gruppi di risorse di Azure, poiché gli insiemi di credenziali delle chiavi necessitano di capacità di archiviazione (anche se di piccole dimensioni) e la registrazione dell'insieme di credenziali delle chiavi, se abilitata, genera anche i dati archiviati. Come procedura consigliata, Microsoft consiglia di utilizzare amministratori separati per gestire ogni gruppo di risorse, con l'amministrazione allineata al set di amministratori che gestiranno tutte le risorse chiave del cliente correlate.
  
> [!IMPORTANT]
> Per ottimizzare la disponibilità, posizionare gli insiemi di credenziali delle chiavi in aree geografiche vicine al servizio Microsoft 365 Ad esempio, se l'organizzazione di Exchange Online si trova in Nord America, posizionare gli insiemi di credenziali delle chiavi in Nord America. Se l'Exchange Online è in Europa, posizionare gli insiemi di credenziali delle chiavi in Europa.
>
> Utilizzare un prefisso comune per gli insiemi di credenziali delle chiavi e includere un'abbreviazione dell'utilizzo e dell'ambito dell'insieme di credenziali e delle chiavi (ad esempio, per il servizio Contoso SharePoint in cui si trovano gli insiemi di credenziali in Nord America, una possibile coppia di nomi è Contoso-CK-SP-NA-VaultA1 e Contoso-CK-SP-NA-VaultA2. I nomi degli insiemi di credenziali sono stringhe univoche a livello globale in Azure, quindi potrebbe essere necessario provare le varianti dei nomi desiderati nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. A partire da luglio 2017 i nomi degli insiemi di credenziali non possono essere modificati, quindi è consigliabile disporre di un piano scritto per la configurazione e utilizzare una seconda persona per verificare che il piano venga eseguito correttamente.
>
> Se possibile, creare gli insiemi di credenziali in aree non abbinate. Le aree di Azure abbinate offrono disponibilità elevata tra i domini di errore del servizio. Pertanto, le coppie regionali possono essere ritenute come l'area di backup reciproca. Ciò significa che una risorsa di Azure posizionata in un'area ottiene automaticamente la tolleranza di errore attraverso l'area associata. Per questo motivo, la scelta delle aree per due insiemi di credenziali utilizzati in un criterio di crittografia dei dati in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle aree geografiche ha solo due aree, quindi non è ancora possibile selezionare aree non abbinate. Se possibile, scegliere due aree non associate per i due insiemi di credenziali utilizzati con un criterio di crittografia dei dati. Ciò trae vantaggio da un totale di quattro aree di disponibilità. Per altre informazioni, vedere Continuità aziendale e ripristino di emergenza [(BCDR):](/azure/best-practices-availability-paired-regions) Azure Paired Regions per un elenco corrente di coppie regionali.
  
### <a name="assign-permissions-to-each-key-vault"></a>Assegnare autorizzazioni a ogni insieme di credenziali delle chiavi

Dovrai definire tre set separati di autorizzazioni per ogni insieme di credenziali delle chiavi, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:
  
- **Amministratori dell'insieme di** credenziali delle chiavi che eseauno la gestione quotidiana dell'insieme di credenziali delle chiavi per l'organizzazione. Queste attività includono il backup, la creazione, il ripristino, l'importazione, l'elenco e il ripristino.

  > [!IMPORTANT]
  > Il set di autorizzazioni assegnate agli amministratori dell'insieme di credenziali delle chiavi non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una pratica intenzionale e importante. L'eliminazione delle chiavi di crittografia in genere non viene eseguita, poiché in questo modo vengono eliminati definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori dell'insieme di credenziali delle chiavi per impostazione predefinita. Al contrario, riservare questo valore ai collaboratori dell'insieme di credenziali chiave e assegnarlo a un amministratore solo a breve termine, una volta compresa una chiara comprensione delle conseguenze.
  
  Per assegnare queste autorizzazioni a un utente dell'organizzazione, accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

- Eseguire il cmdlet Set-AzKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Ad esempio:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Collaboratori dell'insieme di** credenziali delle chiavi che possono modificare le autorizzazioni nell'insieme di credenziali delle chiavi di Azure stesso. Sarà necessario modificare queste autorizzazioni quando i dipendenti lasciano o si uniscono al team. Nella rara situazione in cui gli amministratori dell'insieme di credenziali delle chiavi necessitano legittimamente dell'autorizzazione per eliminare o ripristinare una chiave, dovrai anche modificare le autorizzazioni. A questo set di collaboratori dell'insieme di credenziali chiave deve essere concesso il **ruolo Collaboratore** nell'insieme di credenziali delle chiavi. Puoi assegnare questo ruolo usando Azure Resource Manager. Per la procedura dettagliata, vedere [Use Role-Based Access Control to manage access to your Azure subscription resources.](/azure/active-directory/role-based-access-control-configure) L'amministratore che crea una sottoscrizione dispone implicitamente di questo accesso e della possibilità di assegnare altri amministratori al ruolo Collaboratore.

- **Autorizzazioni per Microsoft 365** applicazioni per ogni insieme di credenziali delle chiavi utilizzato per customer key, è necessario assegnare wrapKey, unwrapKey e ottenere le autorizzazioni per l'entità servizio Microsoft 365 corrispondente. 

Per concedere l'autorizzazione Microsoft 365'entità servizio, eseguire il cmdlet **Set-AzKeyVaultAccessPolicy** utilizzando la sintassi seguente:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Dove:

   - *nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi creato.
   - Per Exchange Online e Skype for Business, sostituire *Office 365 appID* con`00000002-0000-0ff1-ce00-000000000000`
   - Per SharePoint online, OneDrive for Business e Teams file, sostituire Office 365 *appID* con`00000003-0000-0ff1-ce00-000000000000`
   - Per i criteri multi-carico di lavoro (Exchange, Teams, MIP EDM) che si applicano a tutti gli utenti tenant, sostituire Office 365 *appID* con`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Esempio: Impostazione delle autorizzazioni per Exchange Online e Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Esempio: Impostazione delle autorizzazioni per SharePoint online, OneDrive for Business e Teams file:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Assicurarsi che l'eliminazione soft sia abilitata nei vault delle chiavi

Quando è possibile ripristinare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi eliminate accidentalmente o in modo dannoso. Abilita questa configurazione, definita eliminazione soft, prima di poter usare le chiavi con Customer Key. L'abilitazione dell'eliminazione soft consente di ripristinare chiavi o insiemi di credenziali entro 90 giorni dall'eliminazione senza doverle ripristinare dal backup.
  
Per abilitare l'eliminazione soft nei vault delle chiavi, completare la procedura seguente:
  
1. Accedi alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet [Get-AzKeyVault.](/powershell/module/az.keyvault/get-azkeyvault) In questo esempio, *il nome dell'insieme* di credenziali è il nome dell'insieme di credenziali delle chiavi per cui si sta abilitando l'eliminazione recidiva:

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

Esistono due modi per aggiungere chiavi a un insieme di credenziali delle chiavi di Azure; è possibile creare una chiave direttamente in Key Vault oppure importare una chiave. La creazione di una chiave direttamente in Key Vault è meno complicata, ma l'importazione di una chiave offre un controllo totale sulla modalità di generazione della chiave. Usa le chiavi RSA. Azure Key Vault non supporta il ritorno a capo e l'annullamento del wrapping con chiavi di curva ellittiche.
  
Per creare una chiave direttamente nell'insieme di credenziali delle chiavi, eseguire il cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) come segue:
  
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
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Per importare una chiave direttamente nell'insieme di credenziali delle chiavi, è necessario disporre di un modulo di sicurezza hardware nCipher nShield.
  
Alcune organizzazioni preferiscono questo approccio per stabilire la provenienza delle chiavi, quindi questo metodo fornisce anche le attestazioni seguenti:
  
- Il set di strumenti utilizzato per l'importazione include l'attestazione da nCipher che la chiave chiave Exchange (KEK) utilizzata per crittografare la chiave generata non è esportabile e viene generata all'interno di un HSM originale prodotto da nCipher.

- Il set di strumenti include l'attestazione da nCipher che il mondo della sicurezza di Azure Key Vault è stato generato anche su un HSM originale prodotto da nCipher. Questa attestazione dimostra che Microsoft usa anche hardware nCipher originale.

Rivolgersi al gruppo di sicurezza per determinare se sono necessarie le attestazioni precedenti. Per la procedura dettagliata per creare una chiave locale e importarla nell'insieme di credenziali delle chiavi, vedere Come generare e trasferire chiavi protette con [HSM per Azure Key Vault.](/azure/key-vault/keys/hsm-protected-keys) Usa le istruzioni di Azure per creare una chiave in ogni insieme di credenziali delle chiavi.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Controllare il livello di ripristino delle chiavi

Microsoft 365 è necessario che la sottoscrizione di Azure Key Vault sia impostata su Do Not Cancel e che le chiavi usate da Customer Key hanno l'eliminazione soft abilitata. Puoi confermare le impostazioni delle sottoscrizioni esaminando il livello di ripristino delle chiavi.
  
Per verificare il livello di ripristino di una chiave, in Azure PowerShell eseguire il cmdlet Get-AzKeyVaultKey seguente:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se la proprietà _Recovery Level_ restituisce un valore diverso da **Recoverable+ProtectedSubscription,** verificare di aver inserito la sottoscrizione nell'elenco Non annullare e di avere abilitato l'eliminazione reversibile in ognuno degli insiemi di credenziali delle chiavi.
  
### <a name="back-up-azure-key-vault"></a>Eseguire il backup di Azure Key Vault

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Non connettere copie offline ad alcuna rete. Archiviarli invece in una posizione offline, ad esempio in una struttura di archiviazione fisica sicura o commerciale. Almeno una copia del backup deve essere archiviata in un percorso accessibile in caso di emergenza. I BLOB di backup sono l'unico mezzo per ripristinare il materiale delle chiavi nel caso in cui una chiave dell'insieme di credenziali delle chiavi sia definitivamente distrutta o altrimenti resa inoperabile. Le chiavi esterne all'insieme di credenziali delle chiavi di Azure e importate in Azure Key Vault non sono idonee come backup perché i metadati necessari per customer key per usare la chiave non esistono con la chiave esterna. Solo un backup eseguito da Azure Key Vault può essere usato per le operazioni di ripristino con Customer Key. Pertanto, è necessario creare un backup di Azure Key Vault dopo aver caricato o creato una chiave.
  
Per creare un backup di una chiave di Azure Key Vault, eseguire il cmdlet [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) come segue:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verificare che il file di output utilizzi il suffisso `.backup` .
  
Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno di Azure Key Vault. Il backup può essere ripristinato solo nella sottoscrizione di Azure da cui è stato eseguito il backup.
  
> [!TIP]
> Per il file di output, scegliere una combinazione del nome dell'insieme di credenziali e del nome della chiave. In questo modo il nome del file verrà autodescritto. Garantisce inoltre che i nomi dei file di backup non si scontrano.
  
Ad esempio:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Convalidare le impostazioni di configurazione di Azure Key Vault

La convalida prima di usare le chiavi in protezione esecuzione programmi è facoltativa, ma è consigliabile. Se si usa la procedura per configurare le chiavi e gli insiemi di credenziali diversi da quelli descritti in questo articolo, convalidare l'integrità delle risorse di Azure Key Vault prima di configurare customer key.
  
Per verificare che le chiavi siano `get` `wrapKey` abilitate, e le `unwrapKey` operazioni:
  
Eseguire il cmdlet [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) come segue:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Nell'output cercare i criteri di accesso e l'identità Exchange Online (GUID) o l'identità SharePoint Online (GUID) in base alle esigenze. Tutte e tre le autorizzazioni precedenti devono essere visualizzate in Autorizzazioni per le chiavi.
  
Se la configurazione dei criteri di accesso non è corretta, eseguire il cmdlet Set-AzKeyVaultAccessPolicy seguente:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Ad esempio, per Exchange Online e Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Ad esempio, per SharePoint Online e OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) come segue:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Customer Key non può usare una chiave scaduta. Le operazioni tentate con una chiave scaduta avranno esito negativo e potrebbero causare un'interruzione del servizio. Ti consigliamo vivamente che le chiavi usate con customer key non abbia una data di scadenza. Una data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con una data di scadenza impostata, modificare il valore di scadenza in 31/12/9999. Le chiavi con una data di scadenza impostata su una data diversa dal 31/12/9999 non Microsoft 365 convalida.
  
Per modificare una data di scadenza impostata su un valore diverso dal 31/12/9999, eseguire il cmdlet [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) come segue:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Non impostare date di scadenza per le chiavi di crittografia usate con Customer Key.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni chiave di Azure Key Vault

Dopo aver configurato gli insiemi di credenziali delle chiavi e aver aggiunto le chiavi, eseguire il comando seguente per ottenere l'URI per la chiave in ogni insieme di credenziali delle chiavi. Questi URI verranno utilizzati quando si crea e si assegna ogni protezione esecuzione programmi in un secondo momento, quindi salvare queste informazioni in un luogo sicuro. Eseguire questo comando una volta per ogni insieme di credenziali delle chiavi.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato i passaggi descritti in questo articolo, è possibile creare e assegnare criteri di dep. Per istruzioni, vedere [Manage Customer Key.](customer-key-manage.md)

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Gestire il codice Cliente](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Crittografia del servizio](office-365-service-encryption.md)