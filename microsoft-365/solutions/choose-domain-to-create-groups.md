---
title: Scegliere il dominio da utilizzare per la creazione dei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Informazioni su come scegliere il dominio da utilizzare per la creazione di gruppi di Microsoft 365 configurando i criteri degli indirizzi di posta elettronica tramite PowerShell.
ms.openlocfilehash: a4bc5bd499652109586c30462d484a12a6cbe876
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662666"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="3e2a0-103">Scegliere il dominio da utilizzare per la creazione dei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e2a0-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="3e2a0-104">Alcune organizzazioni usano domini di posta elettronica separati per segmentare le diverse parti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="3e2a0-105">È possibile specificare il dominio da usare quando gli utenti creano gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="3e2a0-106">Se l'organizzazione richiede agli utenti di creare i propri gruppi in domini diversi dal dominio accettato predefinito per la propria azienda, è possibile configurarli tramite la configurazione dei criteri degli indirizzi di posta elettronica (criteri EAP) tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="3e2a0-107">Prima di poter eseguire i cmdlet di PowerShell, scaricare e installare un modulo che consentirà di parlare con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="3e2a0-108">Vedere [Connettersi a Exchange Online usando una sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="3e2a0-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="3e2a0-109">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="3e2a0-109">Example scenarios</span></span>

<span data-ttu-id="3e2a0-110">Si supponga che il dominio principale dell'azienda sia Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="3e2a0-111">Tuttavia, il dominio accettato predefinito dell'organizzazione è service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="3e2a0-112">Questo significa che i gruppi verranno creati in service.contoso.com (ad esempio, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3e2a0-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="3e2a0-113">Si supponga di disporre anche di sottodomini configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="3e2a0-114">Si desidera che i gruppi vengano creati anche in questi domini:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="3e2a0-115">students.contoso.com per gli studenti</span><span class="sxs-lookup"><span data-stu-id="3e2a0-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="3e2a0-116">faculty.contoso.com per membri dell'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="3e2a0-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="3e2a0-117">I due scenari seguenti illustrano come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2a0-118">Quando si dispone di più criteri EAP, vengono valutati in base all'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="3e2a0-119">Un valore pari a 1 indica la massima priorità.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="3e2a0-120">Una volta che un EAP corrisponde, non viene valutato un ulteriore EAP e gli indirizzi che vengono timbrati sul gruppo sono secondo il protocollo EAP corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="3e2a0-121">> se non criteri EAP soddisfano i criteri specificati, il gruppo viene sottoposto a provisioning nel dominio accettato predefinito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="3e2a0-122">Per informazioni dettagliate su come aggiungere un dominio accettato, vedere [Gestire i domini accettati in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).</span><span class="sxs-lookup"><span data-stu-id="3e2a0-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="3e2a0-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="3e2a0-123">Scenario 1</span></span>

<span data-ttu-id="3e2a0-124">Nell'esempio seguente viene illustrato come eseguire il provisioning di tutti i gruppi di Microsoft 365 nell'organizzazione nel dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="3e2a0-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="3e2a0-125">Scenario 2</span></span>

<span data-ttu-id="3e2a0-126">Si supponga di voler controllare quali gruppi di sottodomini vengono creati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="3e2a0-127">Si vuole che:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-127">You want:</span></span>
  
- <span data-ttu-id="3e2a0-128">Gruppi creati dagli studenti (gli utenti che hanno un **reparto** impostato su **studenti**) nel dominio students.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="3e2a0-129">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="3e2a0-130">I gruppi creati dai membri della facoltà (gli utenti che hanno un **reparto** impostato su **docenti o indirizzo di posta elettronica contiene Faculty.contoso.com)**) nel dominio Faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="3e2a0-131">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="3e2a0-132">Tutti gli altri utenti del dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="3e2a0-133">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="3e2a0-134">Cambiare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3e2a0-134">Change email address policies</span></span>

<span data-ttu-id="3e2a0-135">Per modificare la priorità o i modelli dell'indirizzo di posta elettronica per un criterio EAP esistente, usare il cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="3e2a0-136">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="3e2a0-137">Eliminare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3e2a0-137">Delete email address policies</span></span>

<span data-ttu-id="3e2a0-138">Per eliminare un criterio EAP, usare il cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="3e2a0-139">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="3e2a0-140">Requisiti ibridi</span><span class="sxs-lookup"><span data-stu-id="3e2a0-140">Hybrid requirements</span></span>

<span data-ttu-id="3e2a0-141">Se l'organizzazione è configurata in uno scenario ibrido, vedere [Configure microsoft 365 groups with on-premises Exchange Hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) per assicurarsi che l'organizzazione soddisfi i requisiti per la creazione di gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="3e2a0-142">Ulteriori informazioni sull'utilizzo dei gruppi di criteri degli indirizzi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="3e2a0-143">Sono disponibili alcune altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="3e2a0-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="3e2a0-144">La velocità con cui vengono creati i gruppi dipendono dal numero di criteri EAP configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="3e2a0-145">Gli amministratori e gli utenti possono modificare i domini anche quando creano gruppi.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="3e2a0-p110">Il gruppo di utenti viene determinato usando le query standard (proprietà utente) già disponibili. Per informazioni sulle proprietà filtrabili supportate, vedere [Proprietà filtrabili per il parametro - RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties).</span><span class="sxs-lookup"><span data-stu-id="3e2a0-p110">Group of users is determined using the standard queries (User properties) that are already available. Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="3e2a0-148">Se si configurano criteri EAP per i gruppi, viene selezionato il dominio accettato predefinito per la creazione di gruppi.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="3e2a0-149">Se si rimuove un dominio accettato, è necessario aggiornare prima i criteri EAP, altrimenti ci saranno conseguenze sul provisioning dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="3e2a0-150">È possibile configurare un limite massimo di 100 criteri per gli indirizzi di posta elettronica per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e2a0-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3e2a0-151">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="3e2a0-151">Related articles</span></span>

[<span data-ttu-id="3e2a0-152">Creare un gruppo di Microsoft 365 nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e2a0-152">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
