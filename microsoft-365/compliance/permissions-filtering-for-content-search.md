---
title: Configurare il filtro delle autorizzazioni per la ricerca di contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Utilizzare il filtro delle autorizzazioni ricerca contenuto per consentire a un responsabile di eDiscovery di cercare solo un sottoinsieme di cassette postali e siti nell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ac09b35a4487ad836b48ba0cf7fee765e758ec4
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780474"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurare il filtro delle autorizzazioni per Ricerca contenuto

È possibile utilizzare il filtro delle autorizzazioni di ricerca per consentire a un responsabile di eDiscovery di cercare solo un sottoinsieme di cassette postali e siti nell'organizzazione. È inoltre possibile filtrare le autorizzazioni per consentire allo stesso gestore di eDiscovery di eseguire le ricerche solo per i contenuti delle cassette postali e dei siti che rispondono a un criterio di ricerca specifico. Ad esempio, è possibile consentire un gestore di eDiscovery di effettuare la ricerca solo nelle cassette postali degli utenti in un determinato percorso o reparto. A tale scopo, creare un filtro che utilizza un filtro destinatario supportato per limitare le cassette postali in cui un utente o un gruppo di utenti specifico può eseguire ricerche. È inoltre possibile creare un filtro che specifica il contenuto della cassetta postale che un utente può cercare. Questa operazione viene eseguita creando un filtro che utilizza una proprietà dei messaggi disponibili per la ricerca. Analogamente, è possibile consentire a un responsabile di eDiscovery di cercare solo siti di SharePoint specifici nell'organizzazione. Questa operazione viene eseguita creando un filtro che consente di limitare il sito disponibile per la ricerca. È inoltre possibile creare un filtro che consente di specificare i contenuti dei siti che è possibile ricercare. Questa operazione viene eseguita creando un filtro che utilizza una proprietà dei siti disponibili per la ricerca.

È inoltre possibile utilizzare il filtro delle autorizzazioni di ricerca per creare limiti logici (denominati limiti di *conformità)* all'interno di un'organizzazione che controllano i percorsi dei contenuti degli utenti (ad esempio cassette postali, siti di SharePoint e account di OneDrive) che possono essere cercati da responsabili di eDiscovery specifici. Per ulteriori informazioni, vedere [Configurare i limiti di conformità per le indagini eDiscovery in Office 365.](tagging-and-assessment-in-advanced-ediscovery.md)
  
Il filtro delle autorizzazioni di ricerca è supportato dalla funzionalità Ricerca contenuto nel Centro sicurezza & conformità. Questi quattro cmdlet consentono di configurare e gestire i filtri delle autorizzazioni di ricerca:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Requisiti per configurare il filtro delle autorizzazioni

- Per eseguire i cmdlet del filtro di sicurezza di conformità, è necessario essere membri del gruppo di ruoli Gestione organizzazione nel Centro sicurezza & conformità. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Per utilizzare i cmdlet del filtro di sicurezza di conformità, è necessario connettersi a PowerShell & Centro sicurezza e sicurezza. Ciò è necessario perché questi cmdlet richiedono l'accesso alle proprietà delle cassette postali, motivo per cui è necessario connettersi a PowerShell di Exchange Online. Vedere la procedura descritta nella sezione successiva.

- Consultare la sezione [More information](#more-information) per ulteriori informazioni sui filtri delle autorizzazioni di ricerca.

- Il filtro delle autorizzazioni di ricerca è applicabile alle cassette postali inattive, il che significa che è possibile utilizzare il filtro dei contenuti delle cassette postali e delle cassette postali per limitare gli utenti che possono eseguire ricerche in una cassetta postale inattiva. Per ulteriori [informazioni sul filtro](#more-information) delle autorizzazioni e sulle cassette postali inattive, vedere la sezione Ulteriori informazioni.

- Il filtro delle autorizzazioni di ricerca non può essere utilizzato per limitare gli utenti che possono eseguire ricerche nelle cartelle pubbliche in Exchange.

- Non esiste alcun limite al numero di filtri delle autorizzazioni di ricerca che è possibile creare in un'organizzazione. Tuttavia, le prestazioni della ricerca saranno influenzate quando sono presenti più di 100 filtri per le autorizzazioni di ricerca. Per mantenere il numero di filtri delle autorizzazioni di ricerca nell'organizzazione il più piccolo possibile, creare filtri che combinano le regole per Exchange, SharePoint e OneDrive in un unico filtro, se possibile.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Connettersi a PowerShell di Exchange Online & Centro sicurezza e conformità in una singola sessione

Prima di eseguire correttamente lo script in questa sezione, è necessario scaricare e installare il modulo PowerShell V2 di Exchange Online. Per informazioni, vedere [Informazioni sul modulo PowerShell V2 di Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

1. Salvare il testo seguente in un Windows PowerShell di script utilizzando il suffisso del nome file **ps1.** Ad esempio, è possibile salvarlo in un file **denominatoConnectEXO-SCC.ps1**.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente ed eseguire lo script; Per esempio:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Come verificare se l'operazione ha funzionato? Dopo aver eseguito lo script, i cmdlet da Exchange Online e Security & Compliance PowerShell vengono importati nella sessione Windows PowerShell locale. Se non vengono visualizzati errori, la connessione è stata eseguita correttamente. Un breve test è l'esecuzione di un cmdlet del Centro sicurezza e conformità & di Exchange Online. Ad esempio, è possibile eseguire **Get-Mailbox** e **Get-ComplianceSearch.**

Per la risoluzione degli errori di connessione di PowerShell, vedere:

- [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter viene** utilizzato per creare un filtro delle autorizzazioni di ricerca. Nella tabella seguente vengono descritti i parametri per questo cmdlet. Tutti i parametri sono necessari per creare un filtro di sicurezza di conformità.
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Azione_ <br/> | Il  _parametro Action_ consente di specificare il tipo di azione di ricerca a cui viene applicato il filtro. Le azioni di ricerca di contenuto possibili sono:  <br/><br/> **Esportare:** Il filtro viene applicato durante l'esportazione dei risultati della ricerca.  <br/> **Anteprima:** Il filtro viene applicato quando si visualizzano in anteprima i risultati della ricerca.  <br/> **Elimina:** Il filtro viene applicato durante l'eliminazione dei risultati della ricerca.  <br/> **Ricerca:** Il filtro viene applicato quando si esegue una ricerca.  <br/> **Tutti:** Il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _FilterName_ <br/> |Il  _parametro FilterName_ consente di specificare il nome del filtro delle autorizzazioni. Questo nome è utilizzato per identificare un filtro quando si utilizzano i cmdlet **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** e **Remove-ComplianceSecurityFilter**.  <br/> |
| _Filtri_ <br/> | Il  _parametro Filters_ consente di specificare i criteri di ricerca per il filtro di sicurezza di conformità. È possibile creare tre diverse tipologie di filtri:  <br/><br/> **Filtro delle cassette postali:** Questo tipo di filtro specifica le cassette postali in cui gli utenti assegnati (specificati dal parametro  _Users)_ possono eseguire ricerche. La sintassi per questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove  _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per l'ambito delle cassette postali in cui è possibile eseguire ricerche. Ad esempio, il filtro delle cassette postali consentirebbe all'utente assegnato a questo filtro di cercare solo le cassette postali con il valore  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" nella proprietà CustomAttribute10.  <br/>  Qualsiasi proprietà destinatario filtrabile supportata può essere utilizzata per la _proprietà MailboxPropertyName._ Per un elenco delle proprietà supportate, vedere [Proprietà filtrabili per il parametro -RecipientFilter.](https://go.microsoft.com/fwlink/p/?LinkId=784903)  <br/><br/> **Filtro contenuto delle cassette postali:** Questo tipo di filtro viene applicato al contenuto in cui è possibile eseguire ricerche. Specifica il contenuto della cassetta postale che gli utenti assegnati possono cercare. La sintassi per questo tipo di filtro è MailboxContent_ _SearchablePropertyName: value_, **dove** _SearchablePropertyName_ specifica una proprietà KQL (Keyword Query Language) che può essere specificata in una ricerca di contenuto. Ad esempio, il filtro contenuto delle cassette postali consente all'utente assegnato a questo filtro di cercare solo i messaggi inviati ai destinatari nel  `MailboxContent_recipients:contoso.com` contoso.com dominio.  <br/>  Per un elenco delle proprietà dei messaggi disponibili per la ricerca, vedere Query con parole chiave [e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md) <br/> <br/> **Importante:**  Un singolo filtro di ricerca non può contenere un filtro delle cassette postali e un filtro contenuto della cassetta postale. Per combinarle in un singolo filtro, è necessario utilizzare un [elenco di filtri.](#using-a-filters-list-to-combine-filter-types)  Un filtro può tuttavia contenere una query più complessa dello stesso tipo. Esempio:  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtro contenuto sito e sito:** Esistono due filtri correlati al sito di SharePoint e OneDrive for Business che è possibile utilizzare per specificare il contenuto del sito o del sito che gli utenti assegnati possono cercare:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Questi due filtri sono intercambiabili. Ad esempio,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` e restituire gli stessi  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` risultati. Per facilitare l'identificazione delle funzionalità di un filtro, è tuttavia possibile utilizzare per specificare le proprietà correlate al sito, ad esempio un URL del sito, e per specificare le proprietà correlate al contenuto, ad esempio i tipi  `Site_`  `SiteContent_` di documento. Ad esempio, il filtro consente all'utente assegnato a questo filtro di cercare solo  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` il contenuto nella raccolta https://contoso.sharepoint.com/sites/doctors siti. Il filtro consente all'utente assegnato a questo filtro di cercare solo i documenti di  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 e versioni successive).  <br/><br/>  Per un elenco delle proprietà dei siti disponibili per la ricerca, vedere Panoramica delle proprietà sottoposte a ricerca per [indicizzazione e gestite in SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) Le proprietà contrassegnate con **Sì** nella **colonna Queryable** possono essere utilizzate per creare un filtro contenuto sito o sito.  <br/><br/> **Importante:** È necessario creare un filtro delle autorizzazioni di ricerca per impedire esplicitamente agli utenti di eseguire ricerche nei percorsi dei contenuti in un servizio specifico, ad esempio per impedire a un utente di eseguire ricerche in qualsiasi cassetta postale di Exchange o in qualsiasi sito di SharePoint. In altre parole, la creazione di un filtro delle autorizzazioni di ricerca che consenta a un utente di eseguire ricerche in tutti i siti di SharePoint nell'organizzazione non impedisce a tale utente di eseguire ricerche nelle cassette postali. Ad esempio, per consentire agli amministratori di SharePoint di eseguire ricerche solo nei siti di SharePoint, è necessario creare un filtro che impedisca loro di eseguire ricerche nelle cassette postali. Analogamente, per consentire agli amministratori di Exchange di eseguire ricerche solo nelle cassette postali, è necessario creare un filtro che impedisca loro di eseguire ricerche nei siti.           |
| _Utenti_ <br/> |Il  _parametro Users_ consente di specificare gli utenti a cui viene applicato questo filtro alle ricerche di contenuto. Identificare gli utenti in base all'alias o all'indirizzo SMTP primario. È possibile specificare più valori separati da virgole oppure assegnare il filtro a tutti gli utenti utilizzando il valore **Tutto**.  <br/> È inoltre possibile utilizzare il  _parametro Users_ per specificare un gruppo di ruoli & centro conformità. Ciò consente di creare un gruppo di ruoli personalizzato e di assegnare a tale gruppo di ruoli un filtro delle autorizzazioni di ricerca. Si supponga, ad esempio, di disporre di un gruppo di ruoli personalizzato per i gestori di eDiscovery per la filiale americana di una multinazionale. È possibile utilizzare il parametro  _Users_ per specificare questo gruppo di ruoli (utilizzando la proprietà Name del gruppo di ruoli) e quindi utilizzare il parametro  _Filter_ per consentire la ricerca solo delle cassette postali negli Stati Uniti.  <br/> Non è possibile specificare gruppi di distribuzione con questo parametro.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Utilizzo di un elenco di filtri per combinare i tipi di filtro

Un *elenco di filtri* è un filtro che include un filtro delle cassette postali e un filtro sito separati da una virgola. L'utilizzo di un elenco di filtri è l'unico metodo supportato per combinare diversi tipi di filtri. Nell'esempio seguente, si noti che una virgola separa i filtri **Cassetta** postale **e** Sito:

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

Quando un filtro contenente un elenco di filtri viene elaborato durante l'esecuzione di una ricerca di contenuto, vengono creati due filtri delle autorizzazioni di ricerca dall'elenco dei filtri: uno per ogni filtro separato da una virgola. Nell'esempio precedente vengono pertanto creati un filtro delle autorizzazioni di ricerca delle cassette postali e un filtro delle autorizzazioni di ricerca del sito. 

Un'alternativa all'utilizzo di un elenco di filtri consiste nel creare due filtri separati per le autorizzazioni di ricerca. Pertanto, nell'esempio precedente, è necessario creare un filtro per l'attributo della cassetta postale e un filtro per l'attributo del sito. In entrambi i casi, i risultati sono gli stessi. L'uso di un elenco di filtri o la creazione di filtri separati per le autorizzazioni di ricerca è una questione di preferenza.

Tenere presente quanto segue sull'uso di un elenco di filtri:

- È necessario utilizzare un elenco di filtri per creare un filtro che include un filtro Cassette **postali** e un **filtro MailboxContent.** 

- Come suggerito in precedenza, non è necessario utilizzare un elenco di filtri per includere un filtro **Site** e **un filtro SiteContent** in un singolo filtro delle autorizzazioni di ricerca. Ad esempio, è possibile combinare **i filtri Site** e **SiteContent** utilizzando un **operatore -or.**

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- Ogni componente di un elenco di filtri può contenere una sintassi di filtro complessa. Ad esempio, i filtri della cassetta postale e del sito possono contenere più filtri separati da un **operatore -or:**

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Esempi di creazione di filtri per le autorizzazioni di ricerca

Di seguito sono riportati esempi di utilizzo del cmdlet **New-ComplianceSecurityFilter** per creare un filtro delle autorizzazioni di ricerca. 
  
In questo esempio l'utente annb@contoso.com di eseguire tutte le azioni di Ricerca contenuto solo per le cassette postali in Canada. Questo filtro contiene il codice numerico a tre cifre per il Canada fornito dall'ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In questo esempio, gli utenti donh e suzanf possono eseguire le ricerche solo nelle cassette postali che dispongono del valore "Marketing" per la proprietà delle cassette postali CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

In questo esempio, i membri del gruppo di ruoli "US Discovery Managers" possono effettuare tutte le azioni di ricerca di contenuto solo nelle cassette postali negli Stati Uniti. Questo filtro contiene il codice numerico a tre cifre per gli Stati Uniti fornito dall'ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

In questo esempio i membri del gruppo di ruoli Gestore di eDiscovery possono eseguire ricerche solo nelle cassette postali dei membri del gruppo di distribuzione Ottawa Users. Il Get-DistributionGroup cmdlet in PowerShell di Exchange Online viene utilizzato per trovare i membri del gruppo Ottawa Users.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

In questo esempio si impedisce agli utenti di eliminare il contenuto dalle cassette postali dei membri del gruppo di distribuzione Team esecutivo. Il Get-DistributionGroup cmdlet in PowerShell di Exchange Online viene utilizzato per trovare i membri del gruppo Executive Team.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

In questo esempio i membri del gruppo di ruoli personalizzato Manager eDiscovery di OneDrive possono cercare solo il contenuto nelle posizioni di OneDrive for Business nell'organizzazione.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> Per limitare gli utenti alla ricerca in siti specifici, utilizzare il filtro  `Site_Path` , come illustrato nell'esempio precedente. `Site_Site`L'utilizzo non funzionerà. 
  
In questo esempio, le azioni di ricerca di contenuto di un utente sono limitate solo ai messaggi di posta elettronica inviati durante il 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

Analogamente all'esempio precedente, in questo esempio le azioni di ricerca di contenuto di un utente sono limitate solo ai documenti modificati nel 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

In questo esempio si impedisce ai membri del gruppo di ruoli "OneDrive Discovery Managers" di eseguire azioni di ricerca contenuto su qualsiasi cassetta postale nell'organizzazione. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

In questo esempio si impedisce a chiunque nell'organizzazione di cercare i messaggi di posta elettronica inviati o ricevuti da janet o sarad.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

In questo esempio viene utilizzato un elenco di filtri per combinare i filtri delle cassette postali e dei siti.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter viene** utilizzato per restituire un elenco di filtri delle autorizzazioni di ricerca. Utilizzare il  _parametro FilterName_ per restituire informazioni per un filtro di ricerca specifico. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter viene** utilizzato per modificare un filtro delle autorizzazioni di ricerca esistente. L'unico parametro obbligatorio è _FilterName._ 
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Azione_| Il  _parametro Action_ consente di specificare il tipo di azione di ricerca a cui viene applicato il filtro. Le azioni di ricerca di contenuto possibili sono: <br/><br/> **Esportare:** Il filtro viene applicato durante l'esportazione dei risultati della ricerca.  <br/> **Anteprima:** Il filtro viene applicato quando si visualizzano in anteprima i risultati della ricerca.  <br/> **Elimina:** Il filtro viene applicato durante l'eliminazione dei risultati della ricerca.  <br/> **Ricerca:** Il filtro viene applicato quando si esegue una ricerca.  <br/> **Tutti:** Il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _FilterName_|Il  _parametro FilterName_ consente di specificare il nome del filtro delle autorizzazioni. |
| _Filtri_| Il  _parametro Filters_ consente di specificare i criteri di ricerca per il filtro di sicurezza di conformità. È possibile creare due diversi tipi di filtri: <br/><br/>**Filtro delle cassette postali:** Questo tipo di filtro specifica le cassette postali in cui gli utenti assegnati (specificati dal parametro  _Users)_ possono eseguire ricerche. La sintassi per questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove  _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per l'ambito delle cassette postali in cui è possibile eseguire ricerche. Ad esempio, il filtro delle cassette postali consentirebbe all'utente assegnato a questo filtro di cercare solo le cassette postali con il valore  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` "OttawaUsers" nella proprietà CustomAttribute10.  Qualsiasi proprietà destinatario filtrabile supportata può essere utilizzata per la _proprietà MailboxPropertyName._ Per un elenco delle proprietà supportate, vedere [Proprietà filtrabili per il parametro -RecipientFilter.](https://go.microsoft.com/fwlink/p/?LinkId=784903) <br/><br/>**Filtro contenuto delle cassette postali:** Questo tipo di filtro viene applicato al contenuto in cui è possibile eseguire ricerche. Specifica il contenuto della cassetta postale che gli utenti assegnati possono cercare. La sintassi per questo tipo di filtro è MailboxContent_ _SearchablePropertyName:value_, **dove** _SearchablePropertyName_ specifica una proprietà KQL (Keyword Query Language) che può essere specificata in una ricerca di contenuto. Ad esempio, il filtro contenuto delle cassette postali consente all'utente assegnato a questo filtro di cercare solo i messaggi inviati ai destinatari nel  `MailboxContent_recipients:contoso.com` contoso.com dominio.  Per un elenco delle proprietà dei messaggi disponibili per la ricerca, vedere [Query con parole chiave per Ricerca contenuto.](keyword-queries-and-search-conditions.md) <br/><br/>**Filtro contenuto sito e sito:** Esistono due filtri correlati al sito di SharePoint e OneDrive for Business che è possibile utilizzare per specificare il contenuto del sito o del sito che gli utenti assegnati possono cercare: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>Questi due filtri sono intercambiabili. Ad esempio,  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` e restituisce gli stessi  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` risultati. Per facilitare l'identificazione delle funzionalità di un filtro, è tuttavia possibile utilizzare per specificare le proprietà correlate al sito, ad esempio un URL del sito, e per specificare le proprietà correlate al contenuto, ad esempio i tipi  `Site_`  `SiteContent_` di documento. Ad esempio, il filtro consente all'utente assegnato a questo filtro di cercare solo  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` il contenuto nella raccolta https://contoso.spoppe.com/sites/doctors siti. Il filtro consente all'utente assegnato a questo filtro di cercare solo i documenti di  `"SiteContent_FileExtension -eq 'docx'"` Word (Word 2007 e versioni successive).  <br/><br/>Per un elenco delle proprietà dei siti disponibili per la ricerca, vedere Panoramica delle proprietà sottoposte a ricerca per [indicizzazione e gestite in SharePoint.](https://go.microsoft.com/fwlink/p/?LinkId=331599) Le proprietà contrassegnate con **Sì** nella **colonna Queryable** possono essere utilizzate per creare un filtro contenuto sito o sito. <br/><br/>          |
| _Utenti_|Il  _parametro Users_ consente di specificare gli utenti a cui viene applicato questo filtro alle ricerche di contenuto. Poiché si tratta di una proprietà multivalore, se si specifica un utente o un gruppo di utenti con questo parametro, l'elenco di utenti esistente verrà sovrascritto. Vedere gli esempi seguenti per la sintassi per aggiungere e rimuovere utenti selezionati. <br/><br/>È inoltre possibile utilizzare il  _parametro Users_ per specificare un gruppo di ruoli & centro conformità. Ciò consente di creare un gruppo di ruoli personalizzato e di assegnare a tale gruppo di ruoli un filtro delle autorizzazioni di ricerca. Si supponga, ad esempio, di disporre di un gruppo di ruoli personalizzato per i gestori di eDiscovery per la filiale americana di una multinazionale. È possibile utilizzare il parametro  _Users_ per specificare questo gruppo di ruoli (utilizzando la proprietà Name del gruppo di ruoli) e quindi utilizzare il parametro  _Filter_ per consentire la ricerca solo delle cassette postali negli Stati Uniti. <br/><br/>Non è possibile specificare gruppi di distribuzione con questo parametro. |

## <a name="examples-of-changing-search-permissions-filters"></a>Esempi di modifica dei filtri delle autorizzazioni di ricerca

In questi esempi viene illustrato come utilizzare i cmdlet **Get-ComplianceSecurityFilter** e **Set-ComplianceSecurityFilter** per aggiungere o rimuovere un utente all'elenco esistente di utenti a cui è assegnato il filtro. Quando si aggiungono o si rimuovono utenti da un filtro, specificare l'utente mediante l'indirizzo SMTP. 
  
In questo esempio viene aggiunto un utente al filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

In questo esempio viene rimosso un utente dal filtro.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter viene** utilizzato per eliminare un filtro di ricerca. Utilizzare il  _parametro FilterName_ per specificare il filtro che si desidera eliminare. 
  
## <a name="more-information"></a>Ulteriori informazioni

- **Come funziona il filtro delle autorizzazioni di ricerca?** Il filtro delle autorizzazioni viene aggiunto alla query di ricerca quando viene eseguita una ricerca di contenuto. Il filtro delle autorizzazioni viene aggiunto alla query di ricerca dall'operatore **booleano AND.** Ad esempio, si dispone di un filtro delle autorizzazioni che consente a Bob di eseguire tutte le azioni di ricerca sulle cassette postali dei membri del gruppo di distribuzione Workers. Bob esegue quindi una ricerca di contenuto in tutte le cassette postali dell'organizzazione con la query di  `sender:jerry@adatum.com` ricerca. Poiché il filtro delle autorizzazioni e la query di ricerca sono combinati logicamente da un operatore **AND,** la ricerca restituisce qualsiasi messaggio inviato da jerry@adatum.com a qualsiasi membro del gruppo di distribuzione Workers. 
    
- **Cosa accade se si dispone di più filtri delle autorizzazioni di ricerca?** In una query di ricerca di contenuto, più filtri delle autorizzazioni sono combinati tramite operatori booleani **OR**. Pertanto, verranno restituiti risultati che rispondono a tali filtri. In una ricerca di contenuto, tutti i filtri (combinati tramite operatori **OR**) vengono quindi combinati con la query di ricerca dall'operatore **AND**. Si consideri l'esempio precedente, in cui un filtro di ricerca consente a Bob di cercare solo le cassette postali dei membri del gruppo di distribuzione Workers. È possibile creare un altro filtro che impedisce a Bob di effettuare la ricerca nella cassetta postale di Phil ("Mailbox_Alias -ne 'Phil'"). Si supponga, inoltre, che Phil sia un membro del gruppo "Workers". Quando Bob esegue una ricerca di contenuto (dall'esempio precedente) in tutte le cassette postali dell'organizzazione, i risultati della ricerca vengono restituiti per la cassetta postale di Phil anche se è stato applicato un filtro per impedire a Bob di cercare nella cassetta postale di Phil. Questo perché il primo filtro, che consente a Bob di eseguire la ricerca nel gruppo Workers, è valido. E poiché Phil è un membro del gruppo Workers, Bob può eseguire la ricerca nella cassetta postale di Phil. 
    
- **Il filtro delle autorizzazioni di ricerca funziona per le cassette postali inattive?** Sì, è possibile utilizzare i filtri del contenuto delle cassette postali e delle cassette postali per limitare gli utenti che possono eseguire ricerche nelle cassette postali inattive nell'organizzazione. Come una normale cassetta postale, una cassetta postale inattiva deve essere configurata con la proprietà del destinatario utilizzata per creare un filtro delle autorizzazioni. Se necessario, è possibile utilizzare il **comando Get-Mailbox -InactiveMailboxOnly** per visualizzare le proprietà delle cassette postali inattive. Per ulteriori informazioni, vedere [Creare e gestire cassette postali inattive in Office 365.](create-and-manage-inactive-mailboxes.md)
    
- **Il filtro delle autorizzazioni di ricerca funziona per le cartelle pubbliche?** No. Come spiegato in precedenza, il filtro delle autorizzazioni di ricerca non può essere utilizzato per limitare gli utenti che possono eseguire ricerche nelle cartelle pubbliche in Exchange. Ad esempio, gli elementi nei percorsi delle cartelle pubbliche non possono essere esclusi dai risultati della ricerca da un filtro delle autorizzazioni. 
    
- **Consentire a un utente di eseguire ricerche in tutti i percorsi di contenuto in un servizio specifico impedisce inoltre di eseguire ricerche in percorsi di contenuto in un servizio diverso?** No. Come spiegato in precedenza, è necessario creare un filtro delle autorizzazioni di ricerca per impedire esplicitamente agli utenti di eseguire ricerche nei percorsi dei contenuti in un servizio specifico, ad esempio per impedire a un utente di eseguire ricerche in qualsiasi cassetta postale di Exchange o in qualsiasi sito di SharePoint. In altre parole, la creazione di un filtro delle autorizzazioni di ricerca che consenta a un utente di eseguire ricerche in tutti i siti di SharePoint nell'organizzazione non impedisce a tale utente di eseguire ricerche nelle cassette postali. Ad esempio, per consentire agli amministratori di SharePoint di eseguire ricerche solo nei siti di SharePoint, è necessario creare un filtro che impedisca loro di eseguire ricerche nelle cassette postali. Analogamente, per consentire agli amministratori di Exchange di eseguire ricerche solo nelle cassette postali, è necessario creare un filtro che impedisca loro di eseguire ricerche nei siti.
