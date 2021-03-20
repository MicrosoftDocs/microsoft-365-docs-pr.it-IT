---
title: Aggiungere un dominio a una tenancy client con Windows PowerShell per i partner DAP
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
description: 'Riepilogo: utilizzare PowerShell per Microsoft 365 per aggiungere un nome di dominio alternativo a un tenant del cliente esistente.'
ms.openlocfilehash: b6a40f387f9fc7e513137cda4253a62be2455aad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905573"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="4f2df-103">Aggiungere un dominio a un tenancy client con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)</span><span class="sxs-lookup"><span data-stu-id="4f2df-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="4f2df-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4f2df-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4f2df-105">È possibile creare e associare nuovi domini alla tenancy del cliente con PowerShell per Microsoft 365 più velocemente rispetto all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f2df-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="4f2df-106">I partner di autorizzazione accesso delegato (DAP, Delegated Access Permission) sono partner di Syndication e Cloud Solution Provider (CSP).</span><span class="sxs-lookup"><span data-stu-id="4f2df-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="4f2df-107">Di solito, rappresentano fornitori di rete o telecomunicazioni di altre aziende.</span><span class="sxs-lookup"><span data-stu-id="4f2df-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="4f2df-108">Aggregano le sottoscrizioni di Microsoft 365 nelle offerte di servizio ai clienti.</span><span class="sxs-lookup"><span data-stu-id="4f2df-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="4f2df-109">Quando vendono un abbonamento a Microsoft 365, vengono automaticamente concesse le autorizzazioni Amministra per conto di (AOBO) ai tenaci dei clienti in modo che possano amministrare e segnalare i tenaaci dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4f2df-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f2df-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4f2df-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="4f2df-111">Le procedure descritte in questo argomento richiedono la connessione a [Connettersi a Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="4f2df-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="4f2df-112">Sono necessarie anche le credenziali di amministratore tenant del partner.</span><span class="sxs-lookup"><span data-stu-id="4f2df-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="4f2df-113">Sono necessarie anche le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f2df-113">You also need the following information:</span></span>
  
- <span data-ttu-id="4f2df-114">È necessario il nome di dominio completo (FQDN) che desidera il cliente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="4f2df-115">È necessario il **TenantId** del cliente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="4f2df-p102">Il nome di dominio completo deve essere registrato con un registrar di DNS (Domain Name Service), come GoDaddy. Per ulteriori informazioni su come registrare pubblicamente un nome di dominio, vedere [Come acquistare un nome di dominio](../admin/get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="4f2df-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>
    
- <span data-ttu-id="4f2df-118">È necessario conoscere la procedura per aggiungere un record TXT alla zona DNS registrata per il proprio registrar.</span><span class="sxs-lookup"><span data-stu-id="4f2df-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="4f2df-119">Per ulteriori informazioni su come aggiungere un record TXT, vedere [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f2df-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="4f2df-120">Se queste procedure non funzionano, è necessario trovare quelle adatte al proprio registrar.</span><span class="sxs-lookup"><span data-stu-id="4f2df-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="4f2df-121">Creare domini</span><span class="sxs-lookup"><span data-stu-id="4f2df-121">Create domains</span></span>

 <span data-ttu-id="4f2df-p104">Probabilmente i propri clienti richiederanno la creazione di domini aggiuntivi da associare ai loro tenancy perché non vogliono che il dominio principale per rappresentare le loro identità aziendali a livello mondiale sia quello predefinito, vale a dire <domain>.onmicrosoft.com sia quello principale che rappresenta le identità aziendali al mondo. La procedura seguente illustra i passaggi per creare un nuovo dominio associato alla tenancy del cliente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f2df-124">Per eseguire alcune di queste operazioni, l'account amministratore  del partner  con cui si accede deve essere impostato su Amministrazione completa per l'impostazione Assegna accesso amministrativo alle società supportate nei dettagli dell'account amministratore nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f2df-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4f2df-125">Per ulteriori informazioni sulla gestione dei ruoli di amministratore del partner, vedere [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span><span class="sxs-lookup"><span data-stu-id="4f2df-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="4f2df-126">Creare il dominio in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4f2df-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="4f2df-127">Questo comando consente di creare il dominio in Azure Active Directory ma non di associarlo al dominio registrato pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="4f2df-128">Ciò si verifica quando si dimostra di essere proprietari del dominio registrato pubblicamente in Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="4f2df-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="4f2df-129">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="4f2df-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4f2df-130">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f2df-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="4f2df-131">Recuperare i dati per il record di verifica TXT DNS</span><span class="sxs-lookup"><span data-stu-id="4f2df-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="4f2df-132">Microsoft 365 genererà i dati specifici che è necessario inserire nel record di verifica TXT DNS.</span><span class="sxs-lookup"><span data-stu-id="4f2df-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="4f2df-133">Per ottenere i dati, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="4f2df-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="4f2df-134">Si otterrà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4f2df-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="4f2df-135">Questo testo sarà necessario per creare il record TXT nella zona DNS registrata pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="4f2df-136">Copiarlo e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="4f2df-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="4f2df-137">Aggiungere un record TXT per l'area DNS registrata pubblicamente</span><span class="sxs-lookup"><span data-stu-id="4f2df-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="4f2df-138">Prima che Microsoft 365 inizi ad accettare il traffico diretto al nome di dominio registrato pubblicamente, è necessario dimostrare di essere proprietari e di disporre delle autorizzazioni di amministratore per il dominio.</span><span class="sxs-lookup"><span data-stu-id="4f2df-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="4f2df-139">È possibile dimostrare di essere il proprietario del dominio creando un record TXT nel dominio.</span><span class="sxs-lookup"><span data-stu-id="4f2df-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="4f2df-140">Un record TXT non produce alcun effetto sul dominio e può essere eliminato dopo aver confermato la proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="4f2df-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="4f2df-141">Per creare i record TXT, seguire le procedure descritte in [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f2df-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="4f2df-142">Se queste procedure non funzionano, è necessario trovare quelle adatte al proprio registrar DNS.</span><span class="sxs-lookup"><span data-stu-id="4f2df-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="4f2df-p111">Confermare la creazione del record TXT tramite nslookup. Seguire questa sintassi:</span><span class="sxs-lookup"><span data-stu-id="4f2df-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="4f2df-145">Si otterrà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4f2df-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="4f2df-146">Convalidare la proprietà del dominio in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f2df-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="4f2df-147">In questo ultimo passaggio, si convalida a Microsoft 365 che si è proprietari del dominio registrato pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="4f2df-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="4f2df-148">Dopo questo passaggio, Microsoft 365 inizierà ad accettare il traffico instradato al nuovo nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="4f2df-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="4f2df-149">Per completare la procedura di registrazione e creazione del dominio, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="4f2df-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="4f2df-150">Questo comando non restituisce alcun output, pertanto, per confermare che ha avuto esito positivo, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4f2df-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="4f2df-151">Si otterrà un risultato simile al seguente</span><span class="sxs-lookup"><span data-stu-id="4f2df-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="4f2df-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f2df-152">See also</span></span>

#### 

[<span data-ttu-id="4f2df-153">Guida per partner</span><span class="sxs-lookup"><span data-stu-id="4f2df-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)