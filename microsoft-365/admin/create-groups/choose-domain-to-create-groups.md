---
title: Scegliere il dominio da usare durante la creazione di Gruppi di Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Informazioni su come scegliere il dominio da utilizzare per la creazione di gruppi di Office 365 mediante la configurazione dei criteri degli indirizzi di posta elettronica tramite PowerShell. '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241408"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="7bd8e-103">Scegliere il dominio da usare durante la creazione di Gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="7bd8e-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="7bd8e-p101">Alcune organizzazioni usano domini di posta elettronica separati per segmentare le diverse parti dell'azienda. È possibile specificare il dominio da usare quando gli utenti creano i gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="7bd8e-106">Se l'organizzazione richiede agli utenti di creare i propri gruppi in domini diversi dal dominio accettato predefinito per la propria azienda, è possibile configurarli tramite la configurazione dei criteri degli indirizzi di posta elettronica (criteri EAP) tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="7bd8e-107">Prima di poter eseguire i cmdlet di PowerShell, scaricare e installare un modulo che consentirà di parlare con l'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization.</span></span> <span data-ttu-id="7bd8e-108">Vedere [Connettersi a Exchange Online usando una sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="7bd8e-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="7bd8e-109">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="7bd8e-109">Example scenarios</span></span>

<span data-ttu-id="7bd8e-110">Si supponga che il dominio principale dell'azienda sia Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="7bd8e-111">Tuttavia, il dominio accettato predefinito dell'organizzazione è service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="7bd8e-112">Questo significa che i gruppi verranno creati in service.contoso.com (ad esempio, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7bd8e-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="7bd8e-113">Si supponga di disporre anche di sottodomini configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="7bd8e-114">Si desidera che i gruppi vengano creati anche in questi domini:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="7bd8e-115">students.contoso.com per gli studenti</span><span class="sxs-lookup"><span data-stu-id="7bd8e-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="7bd8e-116">faculty.contoso.com per membri dell'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="7bd8e-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="7bd8e-117">I due scenari seguenti illustrano come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7bd8e-118">Quando si dispone di più criteri EAP, vengono valutati in base all'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="7bd8e-119">Un valore pari a 1 indica la massima priorità.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="7bd8e-120">Una volta che un EAP corrisponde, non viene valutato un ulteriore EAP e gli indirizzi che vengono timbrati sul gruppo sono secondo il protocollo EAP corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="7bd8e-121">> se non criteri EAP soddisfano i criteri specificati, il gruppo viene sottoposto a provisioning nel dominio accettato predefinito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="7bd8e-122">Per informazioni dettagliate su come aggiungere un dominio accettato, vedere [Gestire i domini accettati in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).</span><span class="sxs-lookup"><span data-stu-id="7bd8e-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="7bd8e-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="7bd8e-123">Scenario 1</span></span>

<span data-ttu-id="7bd8e-124">L'esempio seguente illustra come effettuare il provisioning di tutti i gruppi di Office 365 nell'organizzazione nel dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="7bd8e-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="7bd8e-125">Scenario 2</span></span>

<span data-ttu-id="7bd8e-126">Si supponga di voler controllare quali domini secondari vengono creati in gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="7bd8e-127">Si vuole che:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-127">You want:</span></span>
  
- <span data-ttu-id="7bd8e-128">Gruppi creati dagli studenti (gli utenti che hanno un **reparto** impostato su **studenti**) nel dominio students.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="7bd8e-129">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="7bd8e-130">I gruppi creati dai membri della facoltà (gli utenti che hanno un **reparto** impostato su **docenti o indirizzo di posta elettronica contiene Faculty.contoso.com)**) nel dominio Faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="7bd8e-131">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="7bd8e-132">Tutti gli altri utenti del dominio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="7bd8e-133">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="7bd8e-134">Cambiare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7bd8e-134">Change email address policies</span></span>

<span data-ttu-id="7bd8e-135">Per modificare la priorità o i modelli dell'indirizzo di posta elettronica per un criterio EAP esistente, usare il cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="7bd8e-136">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="7bd8e-137">Eliminare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7bd8e-137">Delete email address policies</span></span>

<span data-ttu-id="7bd8e-138">Per eliminare un criterio EAP, usare il cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="7bd8e-139">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="7bd8e-140">Requisiti ibridi</span><span class="sxs-lookup"><span data-stu-id="7bd8e-140">Hybrid requirements</span></span>

<span data-ttu-id="7bd8e-141">Se l'organizzazione è configurata in uno scenario ibrido, vedere [Configurare i gruppi di Office 365 con una distribuzione ibrida di Exchange locale](https://go.microsoft.com/fwlink/p/?LinkId=785430) per assicurarsi che l'organizzazione soddisfi i requisiti per la creazione di gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="7bd8e-142">Ulteriori informazioni sull'utilizzo dei gruppi di criteri degli indirizzi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="7bd8e-143">Sono disponibili alcune altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="7bd8e-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="7bd8e-144">La velocità con cui vengono creati i gruppi dipendono dal numero di criteri EAP configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="7bd8e-145">Gli amministratori e gli utenti possono modificare i domini anche quando creano gruppi.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="7bd8e-146">Il gruppo di utenti viene determinato usando le query standard (proprietà utente) già disponibili.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="7bd8e-147">Estrarre [le proprietà filtrabili per il parametro-RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) per pProperties filtrabili supportate.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="7bd8e-148">Se si configurano criteri EAP per i gruppi, viene selezionato il dominio accettato predefinito per la creazione di gruppi.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="7bd8e-149">Se si rimuove un dominio accettato, è necessario aggiornare prima i criteri EAP, altrimenti ci saranno conseguenze sul provisioning dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="7bd8e-150">È possibile configurare un limite massimo di 100 criteri per gli indirizzi di posta elettronica per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bd8e-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="7bd8e-151">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="7bd8e-151">Related articles</span></span>

[<span data-ttu-id="7bd8e-152">Creare un gruppo di Office 365 nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="7bd8e-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
