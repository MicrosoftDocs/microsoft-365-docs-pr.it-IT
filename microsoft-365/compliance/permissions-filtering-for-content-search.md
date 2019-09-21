---
title: Configurare il filtro delle autorizzazioni per la ricerca di contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Utilizzare il filtro delle autorizzazioni per la ricerca del contenuto per consentire a un responsabile di eDiscovery di cercare solo un sottoinsieme di cassette postali e siti nell'organizzazione di Office 365.
ms.openlocfilehash: a5dcdd450a974cab476a1b31fc82c78bdda84b2b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084157"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurare il filtro delle autorizzazioni per Ricerca contenuto

È possibile utilizzare il filtro delle autorizzazioni di ricerca per consentire a un responsabile di eDiscovery di ricercare solo un sottoinsieme di cassette postali e siti nell'organizzazione di Office 365. È inoltre possibile filtrare le autorizzazioni per consentire allo stesso gestore di eDiscovery di eseguire le ricerche solo per i contenuti delle cassette postali e dei siti che rispondono a un criterio di ricerca specifico. Ad esempio, è possibile consentire un gestore di eDiscovery di effettuare la ricerca solo nelle cassette postali degli utenti in un determinato percorso o reparto. A tale scopo, è possibile creare un filtro che utilizza un filtro destinatario supportato per limitare le cassette postali che un utente o un gruppo di utenti specifico può eseguire la ricerca. È inoltre possibile creare un filtro che consente di specificare i contenuti delle cassette postali che è possibile ricercare. Questa operazione viene eseguita creando un filtro che utilizza una proprietà dei messaggi disponibili per la ricerca. Analogamente, è possibile consentire a un Manager di eDiscovery di ricercare solo i siti di SharePoint specifici nell'organizzazione. Questa operazione viene eseguita creando un filtro che consente di limitare il sito disponibile per la ricerca. È inoltre possibile creare un filtro che consente di specificare i contenuti dei siti che è possibile ricercare. Questa operazione viene eseguita creando un filtro che utilizza una proprietà dei siti disponibili per la ricerca.

È inoltre possibile utilizzare il filtro delle autorizzazioni di ricerca per creare confini logici (denominati *limiti di conformità*) all'interno di un'organizzazione di Office 365 che controllano le posizioni di contenuto dell'utente (ad esempio, cassette postali, siti di SharePoint e account OneDrive) è possibile eseguire ricerche nei Manager di eDiscovery specifici. Per ulteriori informazioni, vedere [configurare i limiti di conformità per le indagini di eDiscovery in Office 365](tagging-and-assessment-in-advanced-ediscovery.md).
  
Il filtro delle autorizzazioni di ricerca è supportato dalla funzionalità di ricerca contenuto nel centro sicurezza & conformità. Questi quattro cmdlet consentono di configurare e gestire i filtri delle autorizzazioni di ricerca:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire i cmdlet del filtro di sicurezza per la conformità, è necessario essere membri del gruppo di ruoli Gestione organizzazione nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](/security/office-365-security/protect-against-threats.md).
    
- È necessario connettere Windows PowerShell al centro sicurezza & conformità e all'organizzazione di Exchange Online per utilizzare i cmdlet per il filtro di sicurezza di conformità. Questa operazione è necessaria perché questi cmdlet richiedono l'accesso alle proprietà della cassetta postale, che è il motivo per cui è necessario connettersi a Exchange Online. Vedere la procedura descritta nella sezione successiva. 
    
- Consultare la sezione [More information](#more-information) per ulteriori informazioni sui filtri delle autorizzazioni di ricerca. 
    
- Il filtro delle autorizzazioni di ricerca è applicabile alle cassette postali inattive, il che significa che è possibile utilizzare il filtro contenuto cassetta postale e cassette postali per limitare chi può cercare una cassetta postale inattiva. Per ulteriori informazioni sul filtro delle autorizzazioni e sulle cassette postali inattive, vedere la sezione [ulteriori informazioni](#more-information) . 
    
-  Non è possibile utilizzare il filtro delle autorizzazioni di ricerca per limitare gli utenti che possono eseguire ricerche nelle cartelle pubbliche in Exchange. 
    
- Non esiste alcun limite al numero di filtri per le autorizzazioni di ricerca che è possibile creare in un'organizzazione. Tuttavia, le prestazioni di ricerca avranno un impatto se sono presenti più di 100 filtri delle autorizzazioni di ricerca. Per mantenere il minor numero possibile di filtri per le autorizzazioni di ricerca nell'organizzazione, creare filtri che consentano di combinare le regole per Exchange, SharePoint e OneDrive in un unico filtro quando possibile.
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Connettersi al centro sicurezza & compliance e a Exchange online in una singola sessione di PowerShell remota

1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di **. ps1**. Ad esempio, è possibile salvarlo in un file denominato **ConnectEXO-CC. ps1**.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente, quindi eseguire lo script. Per esempio:
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
Come si può verificare se l'operazione ha avuto esito positivo? Dopo aver eseguito lo script, i cmdlet del Centro sicurezza & compliance e di Exchange Online vengono importati nella sessione locale di Windows PowerShell. Se non vengono visualizzati errori, la connessione è stata eseguita correttamente. Un test rapido consiste nell'eseguire un cmdlet del Centro sicurezza & compliance e un cmdlet di Exchange Online. Ad esempio, è possibile eseguire **Install-UnifiedCompliancePrerequisite** e **Get-Mailbox**. 
  
Se non vengono visualizzati errori, controllare i requisiti seguenti:
  
- Un problema comune è rappresentato da una password errata. Eseguire di nuovo questi due passaggi e prestare particolare attenzione al nome utente e alla password del passaggio 1.
    
- Verificare che l'account disponga dell'autorizzazione necessaria per accedere al centro sicurezza & conformità. Per informazioni dettagliate, vedere [fornire agli utenti l'accesso al centro sicurezza & Compliance](/security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Per evitare attacchi DoS (Denial of Service), è possibile aprire solo tre connessioni remote di PowerShell al centro sicurezza & conformità.
    
- Windows PowerShell deve essere configurato per l'esecuzione di script. Questa operazione deve essere eseguita solo una volta, non ogni volta che si effettua la connessione. Per abilitare Windows PowerShell affinché esegua script firmati, eseguire il seguente comando in una finestra di Windows PowerShell elevata (una finestra di Windows PowerShell aperta selezionando **Esegui come amministratore**).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- Il traffico sulla porta TCP 80 deve essere aperto tra il computer locale e Office 365. È probabile che sia aperto, ma è bene verificare se l'organizzazione dispone di criteri restrittivi relativi all'accesso a Internet.

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

Il **nuovo-ComplianceSecurityFilter** viene utilizzato per creare un filtro delle autorizzazioni di ricerca. Nella tabella seguente vengono descritti i parametri per questo cmdlet. Tutti i parametri sono necessari per creare un filtro di sicurezza di conformità. 
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Action_ <br/> | Il parametro _Action_ consente di specificare il tipo di azione di ricerca a cui è applicato il filtro. Le azioni di ricerca di contenuto possibili sono:  <br/><br/> **Esporta:** Il filtro viene applicato quando si esportano i risultati della ricerca.  <br/> **Anteprima:** Il filtro viene applicato quando si visualizzano in anteprima i risultati della ricerca.  <br/> **Purge:** Il filtro viene applicato durante l'eliminazione dei risultati della ricerca.  <br/> **Ricerca:** Il filtro viene applicato durante l'esecuzione di una ricerca.  <br/> **All:** Il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _NomeFiltro_ <br/> |Il parametro _FilterName_ consente di specificare il nome del filtro delle autorizzazioni. Questo nome è utilizzato per identificare un filtro quando si utilizzano i cmdlet **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** e **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filtri_ <br/> | Il parametro _Filters_ consente di specificare i criteri di ricerca per il filtro di sicurezza di conformità. È possibile creare tre diverse tipologie di filtri:  <br/><br/> **Filtro delle cassette postali:** Questo tipo di filtro consente di specificare le cassette postali a cui possono eseguire ricerche gli utenti assegnati (specificati dal parametro _Users_ ). La sintassi per questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per l'ambito delle cassette postali di cui è possibile eseguire la ricerca. Ad esempio, il filtro `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` delle cassette postali consentirebbe all'utente assegnato a questo filtro di cercare solo le cassette postali con il valore "OttawaUsers" nella proprietà CustomAttribute10.  <br/>  Per la proprietà _MailboxPropertyName_ è possibile utilizzare tutte le proprietà dei destinatari filtrabili supportate. Per un elenco delle proprietà supportate, vedere [filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903).  <br/><br/> **Filtro contenuto delle cassette postali:** Questo tipo di filtro viene applicato al contenuto di cui è possibile eseguire la ricerca. Specifica il contenuto delle cassette postali a cui gli utenti assegnati possono eseguire ricerche. La sintassi per questo tipo di filtro è **MailboxContent_** _SearchablePropertyName: valore_, dove _SearchablePropertyName_ specifica una proprietà KQL (Keyword Query Language) che può essere specificata in una ricerca di contenuto. Ad esempio, il filtro `MailboxContent_recipients:contoso.com` contenuto della cassetta postale consentirebbe all'utente assegnato a questo filtro di cercare solo i messaggi inviati ai destinatari nel dominio contoso.com.  <br/>  Per un elenco delle proprietà dei messaggi disponibili per la ricerca, vedere [keyword query and Search Conditions for content search](keyword-queries-and-search-conditions.md). <br/> <br/> **Importante:**  Un singolo filtro di ricerca non può contenere un filtro per le cassette postali e un filtro contenuto della cassetta postale. Per combinarli in un unico filtro, è necessario utilizzare un [elenco di filtri](#using-a-filters-list-to-combine-filter-types).  Tuttavia, un filtro può contenere una query più complessa dello stesso tipo. Esempio:  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtro contenuto del sito e del sito:** Sono disponibili due filtri per il sito di SharePoint e OneDrive for business che è possibile utilizzare per specificare il contenuto del sito o del sito a cui gli utenti assegnati possono eseguire ricerche:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Questi due filtri sono interscambiabili. Ad esempio, `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` restituire gli stessi risultati. Tuttavia, per identificare la funzionalità di un filtro, è possibile utilizzare `Site_` questa impostazione per specificare le proprietà relative al sito, ad esempio l'URL `SiteContent_` di un sito, e per specificare le proprietà relative al contenuto, ad esempio i tipi di documento. Ad esempio, il filtro `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` consentirebbe all'utente assegnato a questo filtro di cercare solo il contenuto https://contoso.sharepoint.com/sites/doctors della raccolta siti. Il filtro `"SiteContent_FileExtension -eq 'docx'"` consentirebbe all'utente assegnato a questo filtro di cercare solo i documenti di Word (Word 2007 e versioni successive).  <br/><br/>  Per un elenco delle proprietà dei siti disponibili per la ricerca, vedere [Panoramica delle proprietà gestite e sottoposte a indicizzazione in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Le proprietà contrassegnate con un **Sì** nella colonna **Queryable** possono essere utilizzate per creare un sito o un filtro contenuto del sito.  <br/><br/> **Importante:** È necessario creare un filtro delle autorizzazioni di ricerca per impedire esplicitamente agli utenti di eseguire ricerche nei percorsi di contenuto in uno specifico servizio di Office 365, ad esempio impedendo a un utente di eseguire ricerche in qualsiasi cassetta postale di Exchange o in qualsiasi sito di SharePoint. In altre parole, la creazione di un filtro delle autorizzazioni di ricerca che consente a un utente di eseguire la ricerca in tutti i siti di SharePoint nell'organizzazione non impedisce all'utente di cercare le cassette postali. Ad esempio, per consentire agli amministratori di SharePoint di cercare solo i siti di SharePoint, è necessario creare un filtro che impedisca loro di effettuare ricerche nelle cassette postali. Analogamente, per consentire agli amministratori di Exchange di eseguire ricerche solo nelle cassette postali, è necessario creare un filtro che impedisca loro di effettuare ricerche nei siti.           |
| _Utenti_ <br/> |Il parametro _Users_ consente di specificare gli utenti a cui viene applicato il filtro per le ricerche di contenuto. Identificare gli utenti in base all'alias o all'indirizzo SMTP primario. È possibile specificare più valori separati da virgole oppure assegnare il filtro a tutti gli utenti utilizzando il valore **Tutto**.  <br/> È inoltre possibile utilizzare il parametro _Users_ per specificare un gruppo di ruoli centro sicurezza & conformità. Ciò consente di creare un gruppo di ruoli personalizzato e di assegnare a tale gruppo di ruoli un filtro delle autorizzazioni di ricerca. Si supponga, ad esempio, di disporre di un gruppo di ruoli personalizzato per i gestori di eDiscovery per la filiale americana di una multinazionale. È possibile utilizzare il parametro _Users_ per specificare questo gruppo di ruoli, utilizzando la proprietà Name del gruppo di ruoli, e quindi utilizzare il parametro _Filter_ per consentire la ricerca solo nelle cassette postali degli Stati Uniti.  <br/> Non è possibile specificare gruppi di distribuzione con questo parametro.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Utilizzo di un elenco di filtri per combinare i tipi di filtro

Un *elenco di filtri* è un filtro che include un filtro per le cassette postali e un filtro sito separato da una virgola. L'utilizzo di un elenco filtri è l'unico metodo supportato per la combinazione di diversi tipi di filtri. Nell'esempio seguente, si noti che la virgola separa la **cassetta postale** e i filtri del **sito** :

```
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Quando un filtro contenente un elenco filtri viene elaborato durante l'esecuzione di una ricerca di contenuto, vengono creati due filtri delle autorizzazioni di ricerca dall'elenco filtri: uno per ogni filtro separato da una virgola. Nell'esempio precedente viene creato un filtro delle autorizzazioni per la ricerca delle cassette postali e un filtro delle autorizzazioni per la ricerca di un sito. 

Un'alternativa all'utilizzo di un elenco di filtri consiste nel creare due filtri di autorizzazioni di ricerca distinti. Nell'esempio precedente, è necessario creare un filtro per l'attributo Mailbox e un filtro per l'attributo site. In entrambi i casi, i risultati sono gli stessi. L'utilizzo di un elenco filtri o la creazione di filtri di autorizzazioni di ricerca distinti è una questione di preferenza.

Tenere presenti le considerazioni seguenti sull'utilizzo di un elenco di filtri:

- È necessario utilizzare un elenco di filtri per creare un filtro che includa un filtro per le **cassette postali** e un filtro **MailboxContent** . 

- Come indicato in precedenza, non è necessario utilizzare un elenco di filtri per includere un **sito** e un filtro **sitecontent** in un unico filtro delle autorizzazioni di ricerca. Ad esempio, è possibile combinare i filtri **sito** e **sitecontent** utilizzando un operatore **-or** .

   ```
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Ogni componente di un elenco di filtri può contenere una sintassi del filtro complessa. Ad esempio, i filtri della cassetta postale e del sito possono contenere più filtri separati da un operatore **or** :

   ```
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Esempi di creazione di filtri per le autorizzazioni di ricerca

Di seguito sono riportati esempi di utilizzo del cmdlet **New-ComplianceSecurityFilter** per creare un filtro delle autorizzazioni di ricerca. 
  
In questo esempio viene consentito all'utente annb@contoso.com di eseguire tutte le azioni di ricerca di contenuto solo per le cassette postali in Canada. Questo filtro contiene il codice numerico a tre cifre per il Canada fornito dall'ISO 3166-1.

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In questo esempio viene consentito agli utenti di DonH e suzanf di cercare solo le cassette postali con il valore "marketing" per la proprietà della cassetta postale di CustomAttribute1.

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
In questo esempio, i membri del gruppo di ruoli "US Discovery Managers" possono effettuare tutte le azioni di ricerca di contenuto solo nelle cassette postali negli Stati Uniti. Questo filtro contiene il codice numerico a tre cifre per gli Stati Uniti fornito dall'ISO 3166-1.
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

Questo esempio consente ai membri del gruppo di ruoli eDiscovery Manager di eseguire ricerche solo nelle cassette postali dei membri del gruppo di distribuzione Ottawa Users. 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
In questo esempio si impedisce agli utenti di eliminare il contenuto dalle cassette postali dei membri del gruppo di distribuzione Team esecutivo.

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
Questo esempio consente ai membri del gruppo di ruoli personalizzato OneDrive eDiscovery Manager di cercare solo il contenuto nelle posizioni di OneDrive for business nell'organizzazione.

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> Per limitare gli utenti alla ricerca di siti specifici, utilizzare `Site_Path`il filtro, come illustrato nell'esempio precedente. L' `Site_Site` utilizzo non funzionerà. 
  
In questo esempio, le azioni di ricerca di contenuto di un utente sono limitate solo ai messaggi di posta elettronica inviati durante il 2015.

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
Analogamente all'esempio precedente, in questo esempio le azioni di ricerca di contenuto di un utente sono limitate solo ai documenti modificati nel 2015.

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
In questo esempio viene impedito ai membri del gruppo di ruoli "OneDrive Discovery managers" di eseguire azioni di ricerca di contenuto su qualsiasi cassetta postale dell'organizzazione. 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In questo esempio viene impedito a tutti gli utenti dell'organizzazione di cercare i messaggi di posta elettronica inviati o ricevuti da Janet o Sarad.

```
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In questo esempio viene utilizzato un elenco di filtri per combinare i filtri per cassette postali e siti.

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

Il **Get-ComplianceSecurityFilter** viene utilizzato per restituire un elenco dei filtri delle autorizzazioni di ricerca. Utilizzare il parametro _FilterName_ per restituire le informazioni relative a un filtro di ricerca specifico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

Il **set-ComplianceSecurityFilter** viene utilizzato per modificare un filtro delle autorizzazioni di ricerca esistente. L'unico parametro obbligatorio è _FilterName_. 
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Action_| Il parametro _Action_ consente di specificare il tipo di azione di ricerca a cui è applicato il filtro. Le azioni di ricerca di contenuto possibili sono: <br/><br/> **Esporta:** Il filtro viene applicato quando si esportano i risultati della ricerca.  <br/> **Anteprima:** Il filtro viene applicato quando si visualizzano in anteprima i risultati della ricerca.  <br/> **Purge:** Il filtro viene applicato durante l'eliminazione dei risultati della ricerca.  <br/> **Ricerca:** Il filtro viene applicato durante l'esecuzione di una ricerca.  <br/> **All:** Il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _NomeFiltro_|Il parametro _FilterName_ consente di specificare il nome del filtro delle autorizzazioni. |
| _Filtri_| Il parametro _Filters_ consente di specificare i criteri di ricerca per il filtro di sicurezza di conformità. È possibile creare due tipi diversi di filtri: <br/><br/>**Filtro delle cassette postali:** Questo tipo di filtro consente di specificare le cassette postali a cui possono eseguire ricerche gli utenti assegnati (specificati dal parametro _Users_ ). La sintassi per questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per l'ambito delle cassette postali di cui è possibile eseguire la ricerca. Ad esempio, il filtro `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` delle cassette postali consentirebbe all'utente assegnato a questo filtro di cercare solo le cassette postali con il valore "OttawaUsers" nella proprietà CustomAttribute10.  Per la proprietà _MailboxPropertyName_ è possibile utilizzare tutte le proprietà dei destinatari filtrabili supportate. Per un elenco delle proprietà supportate, vedere [filterable Properties for the-RecipientFilter Parameter](https://go.microsoft.com/fwlink/p/?LinkId=784903). <br/><br/>**Filtro contenuto delle cassette postali:** Questo tipo di filtro viene applicato al contenuto di cui è possibile eseguire la ricerca. Specifica il contenuto delle cassette postali a cui gli utenti assegnati possono eseguire ricerche. La sintassi per questo tipo di filtro è **MailboxContent_** _SearchablePropertyName: valore_, dove _SearchablePropertyName_ specifica una proprietà KQL (Keyword Query Language) che può essere specificata in una ricerca di contenuto. Ad esempio, il filtro `MailboxContent_recipients:contoso.com` contenuto della cassetta postale consentirebbe all'utente assegnato a questo filtro di cercare solo i messaggi inviati ai destinatari nel dominio contoso.com.  Per un elenco delle proprietà dei messaggi disponibili per la ricerca, vedere [keyword queries for content search](keyword-queries-and-search-conditions.md). <br/><br/>**Filtro contenuto del sito e del sito:** Sono disponibili due filtri per il sito di SharePoint e OneDrive for business che è possibile utilizzare per specificare il contenuto del sito o del sito a cui gli utenti assegnati possono eseguire ricerche: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **Sitecontent**_*SearchableSiteProperty*<br/><br/>Questi due filtri sono interscambiabili. Ad esempio, `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` restituisce gli stessi risultati. Tuttavia, per identificare la funzionalità di un filtro, è possibile utilizzare `Site_` questa impostazione per specificare le proprietà relative al sito, ad esempio l'URL `SiteContent_` di un sito, e per specificare le proprietà relative al contenuto, ad esempio i tipi di documento. Ad esempio, il filtro `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` consentirebbe all'utente assegnato a questo filtro di cercare solo il contenuto https://contoso.spoppe.com/sites/doctors della raccolta siti. Il filtro `"SiteContent_FileExtension -eq 'docx'"` consentirebbe all'utente assegnato a questo filtro di cercare solo i documenti di Word (Word 2007 e versioni successive).  <br/><br/>Per un elenco delle proprietà dei siti disponibili per la ricerca, vedere [Panoramica delle proprietà gestite e sottoposte a indicizzazione in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Le proprietà contrassegnate con un **Sì** nella colonna **Queryable** possono essere utilizzate per creare un sito o un filtro contenuto del sito. <br/><br/>          |
| _Utenti_|Il parametro _Users_ consente di specificare gli utenti a cui viene applicato il filtro per le ricerche di contenuto. Poiché si tratta di una proprietà multivalore, la specifica di un utente o di un gruppo di utenti con questo parametro sovrascrive l'elenco esistente di utenti. Per la sintassi da aggiungere e rimuovere gli utenti selezionati, vedere gli esempi seguenti. <br/><br/>È inoltre possibile utilizzare il parametro _Users_ per specificare un gruppo di ruoli centro sicurezza & conformità. Ciò consente di creare un gruppo di ruoli personalizzato e di assegnare a tale gruppo di ruoli un filtro delle autorizzazioni di ricerca. Si supponga, ad esempio, di disporre di un gruppo di ruoli personalizzato per i gestori di eDiscovery per la filiale americana di una multinazionale. È possibile utilizzare il parametro _Users_ per specificare questo gruppo di ruoli, utilizzando la proprietà Name del gruppo di ruoli, e quindi utilizzare il parametro _Filter_ per consentire la ricerca solo nelle cassette postali degli Stati Uniti. <br/><br/>Non è possibile specificare gruppi di distribuzione con questo parametro. |

## <a name="examples-of-changing-search-permissions-filters"></a>Esempi di modifica dei filtri delle autorizzazioni di ricerca

In questi esempi viene illustrato come utilizzare i cmdlet **Get-ComplianceSecurityFilter** e **set-ComplianceSecurityFilter** per aggiungere o rimuovere un utente nell'elenco esistente di utenti a cui è assegnato il filtro. Quando si aggiungono o si rimuovono utenti da un filtro, specificare l'utente mediante l'indirizzo SMTP. 
  
In questo esempio viene aggiunto un utente al filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
In questo esempio viene rimosso un utente dal filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

Il parametro **Remove-ComplianceSecurityFilter** viene utilizzato per eliminare un filtro di ricerca. Utilizzare il parametro _FilterName_ per specificare il filtro che si desidera eliminare. 
  
## <a name="more-information"></a>Ulteriori informazioni

- **Come funziona il filtro delle autorizzazioni di ricerca?** Il filtro delle autorizzazioni viene aggiunto alla query di ricerca quando viene eseguita una ricerca di contenuto. Il filtro delle autorizzazioni viene aggiunto alla query di ricerca in base all'operatore booleano **and** . Ad esempio, si dispone di un filtro autorizzazioni che consente a Bob di eseguire tutte le azioni di ricerca nelle cassette postali dei membri del gruppo di distribuzione workers. Successivamente, Bob esegue una ricerca contenuto in tutte le cassette postali dell'organizzazione con `sender:jerry@adatum.com`la query di ricerca. Poiché il filtro delle autorizzazioni e la query di ricerca sono combinati logicamente da un operatore **and** , la ricerca restituisce tutti i messaggi inviati da Jerry@adatum.com a qualsiasi membro del gruppo di distribuzione workers. 
    
- **Cosa accade se si dispone di più filtri delle autorizzazioni di ricerca?** In una query di ricerca di contenuto, più filtri delle autorizzazioni sono combinati tramite operatori booleani **OR**. Pertanto, verranno restituiti risultati che rispondono a tali filtri. In una ricerca di contenuto, tutti i filtri (combinati tramite operatori **OR**) vengono quindi combinati con la query di ricerca dall'operatore **AND**. È possibile eseguire l'esempio precedente, in cui un filtro di ricerca consente a Bob di cercare solo le cassette postali dei membri del gruppo di distribuzione workers. È possibile creare un altro filtro che impedisce a Bob di effettuare la ricerca nella cassetta postale di Phil ("Mailbox_Alias -ne 'Phil'"). Si supponga, inoltre, che Phil sia un membro del gruppo "Workers". Quando Bob esegue una ricerca contenuto (nell'esempio precedente) in tutte le cassette postali dell'organizzazione, i risultati della ricerca vengono restituiti alla cassetta postale di Phil anche se il filtro è stato applicato per impedire a Bob di cercare la cassetta postale di Phil. Questo perché il primo filtro, che consente a Bob di eseguire la ricerca nel gruppo Workers, è valido. E poiché Phil è un membro del gruppo Workers, Bob può eseguire la ricerca nella cassetta postale di Phil. 
    
- **Il filtro delle autorizzazioni di ricerca funziona per le cassette postali inattive?** Sì, è possibile utilizzare filtri contenuto cassetta postale e cassette postali per limitare gli utenti che possono eseguire ricerche nelle cassette postali inattive nell'organizzazione. Analogamente a una cassetta postale normale, una cassetta postale inattiva deve essere configurata con la proprietà Recipient utilizzata per creare un filtro delle autorizzazioni. Se necessario, è possibile utilizzare il comando **Get-Mailbox-InactiveMailboxOnly** per visualizzare le proprietà delle cassette postali inattive. Per ulteriori informazioni, vedere [creare e gestire le cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md).
    
- **Il filtro delle autorizzazioni di ricerca funziona per le cartelle pubbliche?** No. Come spiegato in precedenza, non è possibile utilizzare il filtro delle autorizzazioni di ricerca per limitare gli utenti che possono eseguire ricerche nelle cartelle pubbliche in Exchange. Ad esempio, gli elementi in percorsi di cartelle pubbliche non possono essere esclusi dai risultati della ricerca da un filtro autorizzazioni. 
    
- **È possibile impedire a un utente di eseguire ricerche in tutti i percorsi di contenuto di un servizio specifico anche per cercare percorsi di contenuto in un altro servizio?** No. Come spiegato in precedenza, è necessario creare un filtro delle autorizzazioni di ricerca per impedire esplicitamente agli utenti di eseguire ricerche nei percorsi di contenuto in uno specifico servizio di Office 365, ad esempio impedendo a un utente di eseguire ricerche in qualsiasi cassetta postale di Exchange o in qualsiasi sito di SharePoint. In altre parole, la creazione di un filtro delle autorizzazioni di ricerca che consente a un utente di eseguire la ricerca in tutti i siti di SharePoint nell'organizzazione non impedisce all'utente di cercare le cassette postali. Ad esempio, per consentire agli amministratori di SharePoint di cercare solo i siti di SharePoint, è necessario creare un filtro che impedisca loro di effettuare ricerche nelle cassette postali. Analogamente, per consentire agli amministratori di Exchange di eseguire ricerche solo nelle cassette postali, è necessario creare un filtro che impedisca loro di effettuare ricerche nei siti.
