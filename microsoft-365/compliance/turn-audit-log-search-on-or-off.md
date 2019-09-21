---
title: Abilitare o disabilitare la ricerca nel log di controllo di Office 365
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
description: È possibile abilitare la funzionalità di ricerca del registro di controllo nel centro sicurezza & Compliance. Se si cambia idea, è possibile attivarlo in qualsiasi momento. Quando la ricerca del registro di controllo è disattivata, gli amministratori non possono eseguire ricerche nel log di controllo di Office 365 per l'attività dell'utente e dell'amministratore nell'organizzazione.
ms.openlocfilehash: c5e1106617aa4828ec2db5afcc44ac55e91f2383
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084749"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="fb45c-105">Abilitare o disabilitare la ricerca nel log di controllo di Office 365</span><span class="sxs-lookup"><span data-stu-id="fb45c-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="fb45c-106">L'utente (o un altro amministratore) deve attivare la registrazione di controllo prima di iniziare la ricerca nel registro di controllo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="fb45c-107">Quando la ricerca del registro di controllo nel centro sicurezza & conformità è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="fb45c-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="fb45c-108">Tuttavia, è possibile che l'organizzazione non desideri registrare e conservare i dati del log di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="fb45c-109">In alternativa, è possibile utilizzare un'applicazione di sicurezza di terze parti e la gestione eventi (SIEM) per accedere ai dati di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="fb45c-110">In questi casi, un amministratore globale può disattivare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="fb45c-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="fb45c-111">Before you begin</span></span>

- <span data-ttu-id="fb45c-112">È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="fb45c-113">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="fb45c-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="fb45c-114">Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb45c-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fb45c-115">Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="fb45c-116">Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel centro sicurezza & Compliance, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="fb45c-117">Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb45c-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="fb45c-118">Se si disattiva la ricerca del registro di controllo in Office 365, non sarà possibile utilizzare l'API di attività di gestione di Office 365 per accedere ai dati di controllo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb45c-118">If you turn off audit log search in Office 365, you won't be able to use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="fb45c-119">La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & conformità o quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell .</span><span class="sxs-lookup"><span data-stu-id="fb45c-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="fb45c-120">Questo significa anche che i registri di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="fb45c-121">Per istruzioni dettagliate sulla ricerca nel registro di controllo di Office 365, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="fb45c-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="fb45c-122">Attiva ricerca log di controllo</span><span class="sxs-lookup"><span data-stu-id="fb45c-122">Turn on audit log search</span></span>

<span data-ttu-id="fb45c-123">È possibile utilizzare il Centro sicurezza & conformità o PowerShell per abilitare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="fb45c-124">Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="fb45c-125">Per abilitare la ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb45c-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="fb45c-126">Utilizzare il Centro sicurezza & conformità per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="fb45c-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="fb45c-127">Nel centro sicurezza & conformità, andare alla **ricerca del registro di controllo**della **ricerca** \> .</span><span class="sxs-lookup"><span data-stu-id="fb45c-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="fb45c-128">Fare clic su **Avvia registrazione attività utente e amministratore**.</span><span class="sxs-lookup"><span data-stu-id="fb45c-128">Click **Start recording user and admin activities**.</span></span>
    
    ![Fare clic su Avvia registrazione attività utente e amministratore per attivare il controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="fb45c-130">Viene visualizzata una finestra di dialogo in cui viene indicato che l'attività dell'utente e dell'amministratore nell'organizzazione verrà registrata nel log di controllo di Office 365 e disponibile per la visualizzazione in un report.</span><span class="sxs-lookup"><span data-stu-id="fb45c-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="fb45c-131">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="fb45c-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="fb45c-132">Viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio di ore dopo il completamento della preparazione.</span><span class="sxs-lookup"><span data-stu-id="fb45c-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="fb45c-133">Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="fb45c-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="fb45c-134">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fb45c-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="fb45c-135">Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="fb45c-136">Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fb45c-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="fb45c-137">Disattiva la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="fb45c-137">Turn off audit log search</span></span>

<span data-ttu-id="fb45c-138">Per disattivare la ricerca del registro di controllo, è necessario utilizzare Remote PowerShell connesso all'organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fb45c-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="fb45c-139">Analogamente all'attivazione della ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online per disattivare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="fb45c-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="fb45c-140">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fb45c-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="fb45c-141">Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="fb45c-142">Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata).</span><span class="sxs-lookup"><span data-stu-id="fb45c-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="fb45c-143">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="fb45c-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="fb45c-144">In PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fb45c-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="fb45c-145">Il valore della `False` proprietà _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata.</span><span class="sxs-lookup"><span data-stu-id="fb45c-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="fb45c-146">Nel centro sicurezza & conformità, andare alla **ricerca nel registro di controllo**di **ricerca** \> e quindi fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="fb45c-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="fb45c-147">Viene visualizzato un messaggio in cui viene indicato che la ricerca del registro di controllo non è attivata.</span><span class="sxs-lookup"><span data-stu-id="fb45c-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![Se il controllo è disattivato, viene visualizzato un messaggio.](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
