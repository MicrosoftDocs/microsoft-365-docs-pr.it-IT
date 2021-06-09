---
title: Gestire Microsoft 365 tenant con Windows PowerShell partner DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: In questo articolo viene illustrato come usare PowerShell per Microsoft 365 i tenaci dei clienti.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691081"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Gestire Microsoft 365 tenant con Windows PowerShell per i partner daP (Delegated Access Permissions)

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Windows PowerShell consente ai partner syndication e Cloud Solution Provider (CSP) di amministrare e segnalare facilmente le impostazioni di tenancy dei clienti non disponibili nell'interfaccia di amministrazione di Microsoft 365. Tenere presente che le autorizzazioni Amministra per conto terzi (AOBO, Administer On Behalf Of) sono necessarie all'account amministratore del partner per connettersi ai tenancy dei clienti.
  
I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP). Di solito, rappresentano fornitori di rete o telecomunicazioni di altre aziende. Aggregano Microsoft 365 sottoscrizioni nelle offerte di servizio ai clienti. Quando vendono una sottoscrizione Microsoft 365, vengono automaticamente concesse le autorizzazioni Amministra per conto di (AOBO) ai tenaaci dei clienti in modo che possano amministrare e segnalare i tenaaci dei clienti.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

Le procedure descritte in questo argomento richiedono la connessione a [Connessione a Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md)
  
Sono necessarie anche le credenziali di amministratore tenant del partner.
  
## <a name="what-do-you-want-to-do"></a>Operazione desiderata

### <a name="list-all-tenant-ids"></a>Elencare tutti gli ID tenant

> [!NOTE]
> Se si dispone di più di 500 tenant, definire l'ambito della sintassi del cmdlet con  _-All_ o _-MaxResultsParameter_. Questo è applicabile agli altri cmdlet che possono fornire un output di grandi dimensioni, come **Get-MsolUser**.
  
Per elencare tutti gli ID tenant dei clienti ai quali si ha accesso, eseguire questo comando.
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

In questo modo verrà visualizzato un elenco di tutti i tenant dei clienti tramite **TenantId**.

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Ottenere un ID tenant tramite il nome di dominio

Per ottenere il **TenantId** per il tenant di un cliente specifico per nome di dominio, eseguire questo comando. Sostituire _<nomedominio.onmicrosoft.com>_ con il nome di dominio effettivo del tenant del cliente desiderato.
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Elencare tutti i domini per un tenant

Per ottenere tutti i domini per il tenant di un cliente qualsiasi, eseguire questo comando. Sostituire  _<customer TenantId value>_ con il valore effettivo.
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

Se sono stati registrati ulteriori domini, verranno restituiti tutti i domini associati al **TenantId** del cliente.
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Ottenere un mapping di tutti i tenant e i domini registrati

I comandi di PowerShell per Microsoft 365 precedenti mostravano come recuperare id tenant o domini, ma non entrambi contemporaneamente e senza un mapping chiaro tra di essi. Questo comando consente di generare un elenco di tutti gli ID tenant dei clienti e i relativi domini.
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Ottenere tutti gli utenti per un tenant

Questo comando consente di visualizzare lo stato **UserPrincipalName**, **DisplayName** e **isLicensed** per tutti gli utenti di un tenant particolare. Sostituire _<customer TenantId value>_ con il valore effettivo.
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Ottenere tutti i dettagli di un utente

Se si desidera visualizzare tutte le proprietà per un utente particolare, eseguire questo comando. Sostituire _<customer TenantId value>_  e _<user principal name value>_ con i valori effettivi.
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Aggiungere utenti, impostare opzioni e assegnare licenze

La creazione in blocco, la configurazione e la gestione delle licenze Microsoft 365 utenti sono particolarmente efficienti utilizzando PowerShell per Microsoft 365. In questo processo in due passaggi, è necessario innanzitutto creare voci per tutti gli utenti che si desidera aggiungere in un file con valori delimitati da virgole (CSV) e quindi importare il file utilizzando PowerShell per Microsoft 365. 
  
#### <a name="create-a-csv-file"></a>Creare un file CSV

Creare un file CSV utilizzando questo formato:
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
dove:
  
- **UsageLocation**: questo valore è costituito dal codice paese ISO di due lettere dell'utente. I codici paese ISO sono disponibili nella piattaforma [Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). Il codice per gli Stati Uniti, ad esempio, è US e quello per il Brasile è BR. 
    
- **LicenseAssignment**: questo valore utilizza il seguente formato: `syndication-account:<PROVISIONING_ID>`. Ad esempio, se si assegnano licenze O365_Business_Premium agli utenti del tenant dei clienti, il valore **LicenseAssignment** sarà simile al seguente: **syndication-account:O365_Business_Premium**. I PROVISIONING_ID sono disponibili nel portale per i partner Syndication al quale è stato effettuato l'accesso come partner Syndication o CSP.
    
#### <a name="import-the-csv-file-and-create-the-users"></a>Importare il file CSV e creare gli utenti

In seguito alla creazione del file CSV, eseguire questo comando per creare account utente con password senza scadenza che l'utente deve modificare al primo accesso e con cui viene assegnata la licenza specificata. Sostituire il nome del file CSV corretto.
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Vedere anche

#### 

[Guida per partner](https://go.microsoft.com/fwlink/p/?LinkId=533477)

