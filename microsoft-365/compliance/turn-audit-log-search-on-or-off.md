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
ms.custom: seo-marvel-apr2020
description: Come attivare o disattivare la funzionalità di ricerca dei log di controllo nel Centro sicurezza & conformità per abilitare o disabilitare la possibilità degli amministratori di eseguire ricerche nel log di controllo.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919282"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="e3992-103">Abilitare o disabilitare la ricerca dei log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-103">Turn audit log search on or off</span></span>

<span data-ttu-id="e3992-104">La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e3992-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="e3992-105">Ciò include le organizzazioni con abbonamenti E3 / G3 o E5 / G5.</span><span class="sxs-lookup"><span data-stu-id="e3992-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="e3992-106">Quando la ricerca nei log di controllo nel Centro conformità è attivata, le attività dell'utente e dell'amministratore dell'organizzazione vengono registrate nel log di controllo e conservate per 90 giorni e fino a un anno a seconda della licenza assegnata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e3992-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="e3992-107">Tuttavia, l'organizzazione potrebbe avere motivi per non voler registrare e conservare i dati del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="e3992-108">In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3992-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3992-109">Se si disattiva la ricerca nei log di controllo in Microsoft 365, non è possibile usare l'API di attività di gestione di Office 365 o Azure Sentinel per accedere ai dati di controllo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3992-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="e3992-110">Disattivando la ricerca nei log di controllo seguendo i passaggi descritti in questo articolo, non verrà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza e conformità di & o quando si esegue il cmdlet **Search-UnifiedAuditLog** in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3992-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="e3992-111">Questo significa anche che i log di controllo non saranno disponibili tramite l'API di attività di gestione di Office 365 o Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="e3992-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="e3992-112">Prima di attivare o disattivare la ricerca nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="e3992-113">Per attivare o disattivare la ricerca nei registri di controllo nell'organizzazione di Microsoft 365, è necessario disporre del ruolo Registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3992-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="e3992-114">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella **pagina Autorizzazioni** nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3992-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="e3992-115">Gli amministratori globali in Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3992-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e3992-116">Gli utenti devono disporre delle autorizzazioni in Exchange Online per attivare o disattivare la ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="e3992-117">Se si assegna agli utenti  il ruolo Log di controllo nella pagina Autorizzazioni nel Centro sicurezza & conformità, non potranno attivare o disattivare la ricerca nei log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="e3992-118">Questo perché il cmdlet sottostante è un cmdlet di PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3992-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="e3992-119">Per istruzioni dettagliate sulla ricerca nel log di controllo, vedere [Search the audit log in the Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="e3992-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="e3992-120">Per altre informazioni sull'API di attività di gestione di Microsoft 365, vedi Introduzione alle API di gestione di [Microsoft 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="e3992-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="e3992-121">Per verificare che la ricerca nel registro di controllo sia attivata, è possibile eseguire il comando seguente in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e3992-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="e3992-122">Il valore di  `True` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è attivata.</span><span class="sxs-lookup"><span data-stu-id="e3992-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="e3992-123">Attivare la ricerca nei log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-123">Turn on audit log search</span></span>

<span data-ttu-id="e3992-124">Se la ricerca nel log di controllo non è attivata per l'organizzazione, è possibile attivarla nel Centro conformità o tramite PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e3992-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="e3992-125">L'attivazione della ricerca nel log di controllo può richiedere diverse ore prima di poter restituire i risultati durante la ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="e3992-126">Usare il Centro conformità per attivare la ricerca nei log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="e3992-127">[Passare al Centro conformità ed](https://protection.office.com) eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e3992-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="e3992-128">Nel Centro conformità passare a Ricerca **log**  >  **di controllo**.</span><span class="sxs-lookup"><span data-stu-id="e3992-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="e3992-129">Se la ricerca nel log di controllo non è attivata per l'organizzazione, viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività di utenti e amministratori.</span><span class="sxs-lookup"><span data-stu-id="e3992-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="e3992-130">Fare **clic su Attiva controllo.**</span><span class="sxs-lookup"><span data-stu-id="e3992-130">Click **Turn on auditing**.</span></span>

    ![Fare clic su Attiva controllo](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="e3992-132">Il banner viene aggiornato per dire che il log di controllo è in fase di preparazione e che è possibile cercare attività di utenti e amministratori in poche ore.</span><span class="sxs-lookup"><span data-stu-id="e3992-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="e3992-133">Usare PowerShell per attivare la ricerca nei log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="e3992-134">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e3992-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="e3992-135">Eseguire il comando di PowerShell seguente per attivare la ricerca nei log di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3992-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="e3992-136">Viene visualizzato un messaggio che indica che la modifica potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="e3992-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="e3992-137">Disattivare la ricerca nei log di controllo</span><span class="sxs-lookup"><span data-stu-id="e3992-137">Turn off audit log search</span></span>

<span data-ttu-id="e3992-138">È necessario utilizzare PowerShell di Exchange Online per disattivare la ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="e3992-139">Connettersi a PowerShell per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e3992-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="e3992-140">Eseguire il comando di PowerShell seguente per disattivare la ricerca nei log di controllo.</span><span class="sxs-lookup"><span data-stu-id="e3992-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="e3992-141">Dopo un po', verificare che la ricerca nel log di controllo sia disattivata (disabilitata).</span><span class="sxs-lookup"><span data-stu-id="e3992-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="e3992-142">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="e3992-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="e3992-143">In PowerShell di Exchange Online, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e3992-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="e3992-144">Il valore di  `False` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che la ricerca nel log di controllo è disattivata.</span><span class="sxs-lookup"><span data-stu-id="e3992-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="e3992-145">Nel Centro [conformità](https://protection.office.com)passare a Ricerca **log** \> **di controllo**.</span><span class="sxs-lookup"><span data-stu-id="e3992-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="e3992-146">Viene visualizzato un banner che indica che il controllo deve essere attivato per registrare le attività degli utenti e degli amministratori.</span><span class="sxs-lookup"><span data-stu-id="e3992-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>