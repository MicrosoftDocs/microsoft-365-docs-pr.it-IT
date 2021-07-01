---
title: Aggiungere un dominio a una tenancy client con Windows PowerShell partner DAP
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
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Riepilogo: utilizzare PowerShell per Microsoft 365 aggiungere un nome di dominio alternativo a un tenant del cliente esistente.'
ms.openlocfilehash: 3bcdb40e2c72e5aac8103b0b55ff6fccfe6a9fcc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229084"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Aggiungere un dominio a un tenancy client con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile creare e associare nuovi domini alla tenancy del cliente con PowerShell per Microsoft 365 più velocemente rispetto all'interfaccia di amministrazione di Microsoft 365.

I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP). Di solito, rappresentano fornitori di rete o telecomunicazioni di altre aziende. Aggregano Microsoft 365 sottoscrizioni nelle offerte di servizio ai clienti. Quando vendono una sottoscrizione Microsoft 365, vengono automaticamente concesse le autorizzazioni Amministra per conto di (AOBO) ai tenaaci dei clienti in modo che possano amministrare e segnalare i tenaaci dei clienti.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

Le procedure descritte in questo argomento richiedono la connessione a [Connessione a Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md)

Sono necessarie anche le credenziali di amministratore tenant del partner.

Sono necessarie anche le informazioni seguenti:

- È necessario il nome di dominio completo (FQDN) che desidera il cliente.

- È necessario il **TenantId** del cliente.

- Il nome di dominio completo deve essere registrato con un registrar di DNS (Domain Name Service), come GoDaddy. Per ulteriori informazioni su come registrare pubblicamente un nome di dominio, vedere [Come acquistare un nome di dominio](../admin/get-help-with-domains/buy-a-domain-name.md).

- È necessario conoscere la procedura per aggiungere un record TXT alla zona DNS registrata per il proprio registrar. Per ulteriori informazioni su come aggiungere un record TXT, vedere [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Se queste procedure non funzionano, è necessario trovare quelle adatte al proprio registrar.

## <a name="create-domains"></a>Creare domini

 Probabilmente i propri clienti richiederanno la creazione di domini aggiuntivi da associare ai loro tenancy perché non vogliono che il dominio principale per rappresentare le loro identità aziendali a livello mondiale sia quello predefinito, vale a dire <domain>.onmicrosoft.com sia quello principale che rappresenta le identità aziendali al mondo. La procedura seguente illustra i passaggi per creare un nuovo dominio associato alla tenancy del cliente.

> [!NOTE]
> Per eseguire alcune di queste operazioni, l'account di  amministratore del  partner con cui accedi deve essere impostato su Amministrazione completa per l'impostazione Assegna accesso amministrativo alle società supportate nei dettagli dell'account amministratore nella interfaccia di amministrazione di Microsoft 365. Per ulteriori informazioni sulla gestione dei ruoli di amministratore del partner, vedere [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).

### <a name="create-the-domain-in-azure-active-directory"></a>Creare il dominio in Azure Active Directory

Questo comando consente di creare il dominio in Azure Active Directory ma non di associarlo al dominio registrato pubblicamente. Ciò si verifica quando si dimostra di essere proprietari del dominio registrato pubblicamente a Microsoft Microsoft 365 per le aziende.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Recuperare i dati per il record di verifica TXT DNS

 Microsoft 365 genererà i dati specifici da inserire nel record di verifica TXT DNS. Per ottenere i dati, eseguire questo comando.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Si otterrà quanto segue:

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> Questo testo sarà necessario per creare il record TXT nella zona DNS registrata pubblicamente. Copiarlo e salvarlo.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Aggiungere un record TXT per l'area DNS registrata pubblicamente

Prima Microsoft 365 il traffico diretto al nome di dominio registrato pubblicamente, è necessario dimostrare di essere proprietari e di disporre delle autorizzazioni di amministratore per il dominio. È possibile dimostrare di essere il proprietario del dominio creando un record TXT nel dominio. Un record TXT non produce alcun effetto sul dominio e può essere eliminato dopo aver confermato la proprietà del dominio. Per creare i record TXT, seguire le procedure descritte in [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). Se queste procedure non funzionano, è necessario trovare quelle adatte al proprio registrar DNS.

Confermare la creazione del record TXT tramite nslookup. Seguire questa sintassi:

```console
nslookup -type=TXT <FQDN of registered domain>
```

Si otterrà quanto segue:

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Convalidare la proprietà del dominio in Microsoft 365

In questo ultimo passaggio viene convalidato Microsoft 365 che si è proprietari del dominio registrato pubblicamente. Dopo questo passaggio, Microsoft 365 inizierà ad accettare il traffico instradato al nuovo nome di dominio. Per completare la procedura di registrazione e creazione del dominio, eseguire questo comando.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Questo comando non restituisce alcun output, pertanto, per confermare che ha avuto esito positivo, eseguire il comando riportato di seguito.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Si otterrà un risultato simile al seguente

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```


## <a name="see-also"></a>Vedere anche

####

[Guida per partner](https://go.microsoft.com/fwlink/p/?LinkID=533477)