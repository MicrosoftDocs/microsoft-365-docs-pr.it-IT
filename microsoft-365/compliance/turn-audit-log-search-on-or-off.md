---
title: Abilitare o disabilitare la ricerca dei log di controllo
f1.keywords:
- NOCSH
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
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: È possibile abilitare la funzionalità di ricerca del registro di controllo nel centro sicurezza & Compliance. Se si cambia idea, è possibile attivarlo in qualsiasi momento. Quando la ricerca del registro di controllo è disattivata, gli amministratori non possono eseguire ricerche nel log di controllo di Microsoft 365 per l'attività dell'utente e dell'amministratore nell'organizzazione.
ms.openlocfilehash: 6b5ea41ff9f40291e54f8cc9f6660d0f86367994
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633421"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="251a3-105">Abilitare o disabilitare la ricerca dei log di controllo</span><span class="sxs-lookup"><span data-stu-id="251a3-105">Turn audit log search on or off</span></span>

<span data-ttu-id="251a3-106">L'utente (o un altro amministratore) deve attivare la registrazione di controllo prima di iniziare a eseguire la ricerca nel registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-106">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="251a3-107">Quando la ricerca del registro di controllo nel centro sicurezza & conformità è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni e fino a un anno, a seconda della licenza assegnata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="251a3-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="251a3-108">Tuttavia, è possibile che l'organizzazione abbia motivi per non voler registrare e conservare i dati del log di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="251a3-109">In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="251a3-109">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="251a3-110">Se si disattiva la ricerca del registro di controllo in Microsoft 365, non è possibile utilizzare l'API di attività di gestione di Office 365 o la sentinella di Azure per accedere ai dati di controllo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="251a3-110">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="251a3-111">La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & conformità o quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="251a3-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="251a3-112">Questo significa anche che i registri di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365 o la sentinella di Azure.</span><span class="sxs-lookup"><span data-stu-id="251a3-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="251a3-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="251a3-113">Before you begin</span></span>

- <span data-ttu-id="251a3-114">È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="251a3-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="251a3-115">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="251a3-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="251a3-116">Gli amministratori globali di Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="251a3-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="251a3-117">Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="251a3-118">Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel centro sicurezza & Compliance, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="251a3-119">Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="251a3-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="251a3-120">Per istruzioni dettagliate sulla ricerca nel registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="251a3-120">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="251a3-121">Per ulteriori informazioni sull'API Microsoft 365 Management Activity, vedere [Introduzione a microsoft 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="251a3-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="251a3-122">Attiva ricerca log di controllo</span><span class="sxs-lookup"><span data-stu-id="251a3-122">Turn on audit log search</span></span>

<span data-ttu-id="251a3-123">È possibile utilizzare il Centro sicurezza & conformità o PowerShell per abilitare la ricerca nel registro di controllo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="251a3-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="251a3-124">Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="251a3-125">Per abilitare la ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="251a3-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="251a3-126">Utilizzare il Centro sicurezza & conformità per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="251a3-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="251a3-127">Nel centro sicurezza & conformità, andare alla **ricerca del registro di controllo**della **ricerca** \> .</span><span class="sxs-lookup"><span data-stu-id="251a3-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="251a3-128">Viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="251a3-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="251a3-129">Fare clic **su Attiva controllo**.</span><span class="sxs-lookup"><span data-stu-id="251a3-129">Click **Turn on auditing**.</span></span>
    
    ![Fare clic su Attiva controllo](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="251a3-131">Il banner viene aggiornato per indicare che il registro di controllo è in fase di preparazione e che è possibile cercare l'attività dell'utente e dell'amministratore in poche ore.</span><span class="sxs-lookup"><span data-stu-id="251a3-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="251a3-132">Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="251a3-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="251a3-133">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="251a3-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="251a3-134">Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="251a3-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="251a3-135">Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="251a3-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="251a3-136">Disattiva la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="251a3-136">Turn off audit log search</span></span>

<span data-ttu-id="251a3-137">Per disattivare la ricerca del registro di controllo, è necessario utilizzare Remote PowerShell connesso all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="251a3-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="251a3-138">Analogamente all'attivazione della ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online per disattivare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="251a3-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="251a3-139">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="251a3-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="251a3-140">Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="251a3-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="251a3-141">Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata).</span><span class="sxs-lookup"><span data-stu-id="251a3-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="251a3-142">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="251a3-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="251a3-143">In PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="251a3-143">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="251a3-144">Il valore della `False` proprietà _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata.</span><span class="sxs-lookup"><span data-stu-id="251a3-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="251a3-145">Nel centro sicurezza & conformità, andare alla **ricerca del registro di controllo**della **ricerca** \> .</span><span class="sxs-lookup"><span data-stu-id="251a3-145">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
      <span data-ttu-id="251a3-146">Viene visualizzato un banner che indica che è necessario che il controllo sia attivato per registrare l'attività dell'utente e dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="251a3-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>