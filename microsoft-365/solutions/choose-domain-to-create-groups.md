---
title: Scegliere il dominio da utilizzare per la creazione Microsoft 365 gruppi
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: Informazioni su come scegliere il dominio da usare per la creazione di Microsoft 365 di posta elettronica configurando i criteri degli indirizzi di posta elettronica tramite PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583149"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="ae083-103">Scegliere il dominio da utilizzare per la creazione Microsoft 365 gruppi</span><span class="sxs-lookup"><span data-stu-id="ae083-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="ae083-104">Alcune organizzazioni usano domini di posta elettronica separati per segmentare le diverse parti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="ae083-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="ae083-105">È possibile specificare il dominio da utilizzare quando gli utenti creano Microsoft 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="ae083-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="ae083-106">Se l'organizzazione necessita che gli utenti creino i propri gruppi in domini diversi dal dominio accettato predefinito dell'azienda, è possibile consentire questa operazione configurando i criteri degli indirizzi di posta elettronica tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae083-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="ae083-107">Prima di poter eseguire i cmdlet di PowerShell, scaricare e installare un modulo che consente di parlare con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae083-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="ae083-108">Vedere [Connettersi a Exchange Online usando una sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae083-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="ae083-109">Scenari di esempio</span><span class="sxs-lookup"><span data-stu-id="ae083-109">Example scenarios</span></span>

<span data-ttu-id="ae083-110">Supponiamo che il dominio principale dell'azienda sia Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ae083-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="ae083-111">Tuttavia, il dominio accettato predefinito dell'organizzazione è service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ae083-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="ae083-112">Ciò significa che i gruppi verranno creati in service.contoso.com (ad esempio, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ae083-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="ae083-113">Supponiamo che nell'organizzazione siano configurati anche sottodomini.</span><span class="sxs-lookup"><span data-stu-id="ae083-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="ae083-114">Si desidera che i gruppi siano creati anche in questi domini:</span><span class="sxs-lookup"><span data-stu-id="ae083-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="ae083-115">students.contoso.com per gli studenti</span><span class="sxs-lookup"><span data-stu-id="ae083-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="ae083-116">faculty.contoso.com per membri dell'istituto di istruzione</span><span class="sxs-lookup"><span data-stu-id="ae083-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="ae083-117">I due scenari seguenti illustrano come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ae083-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="ae083-118">Quando si dispone di EAP mulitple, questi vengono valutati nell'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="ae083-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="ae083-119">Un valore pari a 1 indica la massima priorità.</span><span class="sxs-lookup"><span data-stu-id="ae083-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="ae083-120">Una volta che un EAP corrisponde, non viene valutato alcun altro EAP e gli indirizzi che vengono contrassegnati sul gruppo sono come in base al EAP corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ae083-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="ae083-121">> Se nessun criterio EAP corrisponde ai criteri specificati, il provisioning del gruppo viene eseguito nel dominio accettato predefinito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae083-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="ae083-122">Per informazioni dettagliate su come aggiungere un dominio accettato, vedere [Gestire i domini accettati in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="ae083-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="ae083-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="ae083-123">Scenario 1</span></span>

<span data-ttu-id="ae083-124">Nell'esempio seguente viene illustrato come eseguire il provisioning di Microsoft 365 gruppi nell'organizzazione nel groups.contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="ae083-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="ae083-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="ae083-125">Scenario 2</span></span>

<span data-ttu-id="ae083-126">Supponiamo che tu voglia controllare in quali sottodomini Microsoft 365 gruppi vengono creati.</span><span class="sxs-lookup"><span data-stu-id="ae083-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="ae083-127">Si vuole che:</span><span class="sxs-lookup"><span data-stu-id="ae083-127">You want:</span></span>
  
- <span data-ttu-id="ae083-128">Gruppi creati dagli studenti (utenti con **Reparto** impostato su **Studenti)** nel students.groups.contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="ae083-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="ae083-129">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="ae083-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="ae083-130">Gruppi creati dai membri dell'istituto di docente (gli utenti che hanno department impostato su Faculty o l'indirizzo di posta elettronica **contiene faculty.contoso.com)** nel faculty.groups.contoso.com dominio. </span><span class="sxs-lookup"><span data-stu-id="ae083-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="ae083-131">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="ae083-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="ae083-132">I gruppi creati da chiunque altro vengono creati nel groups.contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="ae083-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="ae083-133">Utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="ae083-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="ae083-134">Cambiare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae083-134">Change email address policies</span></span>

<span data-ttu-id="ae083-135">Per modificare la priorità o i modelli dell'indirizzo di posta elettronica per un criterio EAP esistente, usare il cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="ae083-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="ae083-136">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="ae083-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="ae083-137">Eliminare i criteri per gli indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ae083-137">Delete email address policies</span></span>

<span data-ttu-id="ae083-138">Per eliminare un criterio EAP, usare il cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="ae083-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="ae083-139">La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="ae083-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="ae083-140">Requisiti ibridi</span><span class="sxs-lookup"><span data-stu-id="ae083-140">Hybrid requirements</span></span>

<span data-ttu-id="ae083-141">Se l'organizzazione è configurata in uno scenario ibrido, vedere [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) per assicurarsi che l'organizzazione soddisfi i requisiti per la creazione di Microsoft 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="ae083-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="ae083-142">Informazioni aggiuntive sull'uso dei gruppi di criteri degli indirizzi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="ae083-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="ae083-143">Ci sono alcune altre cose da sapere:</span><span class="sxs-lookup"><span data-stu-id="ae083-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="ae083-144">La velocità di creazione dei gruppi dipende dal numero di EAP configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae083-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="ae083-145">Gli amministratori e gli utenti possono anche modificare i domini quando creano gruppi.</span><span class="sxs-lookup"><span data-stu-id="ae083-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="ae083-p110">Il gruppo di utenti viene determinato usando le query standard (proprietà utente) già disponibili. Per informazioni sulle proprietà filtrabili supportate, vedere [Proprietà filtrabili per il parametro - RecipientFilter](/powershell/exchange/recipientfilter-properties).</span><span class="sxs-lookup"><span data-stu-id="ae083-p110">Group of users is determined using the standard queries (User properties) that are already available. Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="ae083-148">Se si configurano criteri EAP per i gruppi, viene selezionato il dominio accettato predefinito per la creazione di gruppi.</span><span class="sxs-lookup"><span data-stu-id="ae083-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="ae083-149">Se si rimuove un dominio accettato, è necessario aggiornare prima i criteri EAP, altrimenti ci saranno conseguenze sul provisioning dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="ae083-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="ae083-150">È possibile configurare un limite massimo di 100 criteri per gli indirizzi di posta elettronica per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae083-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="ae083-151">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="ae083-151">Related content</span></span>

<span data-ttu-id="ae083-152">[Pianificazione dettagliata della governance della](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) collaborazione (articolo)</span><span class="sxs-lookup"><span data-stu-id="ae083-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="ae083-153">[Creare il piano di governance della collaborazione](collaboration-governance-first.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="ae083-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="ae083-154">[Creare un Microsoft 365 nell'interfaccia di amministrazione](../admin/create-groups/create-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="ae083-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>