---
title: Attivare o disattivare il controllo
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
description: Come attivare o disattivare la funzionalità di ricerca dei log di controllo nel Centro conformità Microsoft 365 per abilitare o disabilitare la capacità degli amministratori di eseguire ricerche nel log di controllo.
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706665"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="d53d5-103">Attivare o disattivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-103">Turn auditing on or off</span></span>

<span data-ttu-id="d53d5-104">La registrazione di controllo è attivata per impostazione predefinita per le organizzazioni di Microsoft 365 e Office 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d53d5-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="d53d5-105">Ciò include le organizzazioni con abbonamenti E3 / G3 o E5 / G5.</span><span class="sxs-lookup"><span data-stu-id="d53d5-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="d53d5-106">Quando il controllo nel Centro conformità è attivato, le attività degli utenti e degli amministratori dell'organizzazione vengono registrate nel log di controllo e conservate per 90 giorni e fino a un anno a seconda della licenza assegnata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d53d5-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="d53d5-107">Tuttavia, l'organizzazione potrebbe avere motivi per non voler registrare e conservare i dati del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="d53d5-108">In questi casi, un amministratore globale può decidere di disattivare il controllo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d53d5-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d53d5-109">Se si disattiva il controllo in Microsoft 365, non è possibile usare l'API di attività di gestione di Office 365 o Azure Sentinel per accedere ai dati di controllo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="d53d5-110">Disattivare il controllo seguendo i passaggi descritti in questo articolo significa che non verrà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza e conformità di & o quando si esegue il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d53d5-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d53d5-111">Questo significa anche che i log di controllo non saranno disponibili tramite l'API Office 365 management o Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d53d5-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="d53d5-112">Prima di attivare o disattivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="d53d5-113">Per attivare o disattivare il controllo nell Exchange Online nell'organizzazione Microsoft 365 controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="d53d5-114">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi  di ruoli Gestione conformità e Gestione organizzazione nella pagina Autorizzazioni nell'Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d53d5-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="d53d5-115">Gli amministratori globali in Microsoft 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d53d5-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d53d5-116">Agli utenti devono essere assegnate le autorizzazioni Exchange Online attivare o disattivare il controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="d53d5-117">Se si assegna agli utenti  il ruolo Log di controllo nella pagina Autorizzazioni del Centro sicurezza & conformità, non potranno attivare o disattivare il controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="d53d5-118">Questo perché il cmdlet sottostante è un cmdlet Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d53d5-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="d53d5-119">Per istruzioni dettagliate sulla ricerca nel log di controllo, vedere [Search the audit log in the Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="d53d5-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="d53d5-120">Per altre informazioni sull'API di Microsoft 365 Management Activity, vedi Introduzione alle API di [Microsoft 365 Management.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="d53d5-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="d53d5-121">Per verificare che il controllo sia attivato, è possibile eseguire il comando seguente in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d53d5-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="d53d5-122">Il valore di  `True` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che il controllo è attivato.</span><span class="sxs-lookup"><span data-stu-id="d53d5-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="d53d5-123">Attivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-123">Turn on auditing</span></span>

<span data-ttu-id="d53d5-124">Se il controllo non è attivato per l'organizzazione, è possibile attivarlo nel Centro conformità o Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d53d5-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="d53d5-125">L'attivazione del controllo può richiedere diverse ore prima di poter restituire i risultati durante la ricerca nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="d53d5-126">Usare il Centro conformità per attivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="d53d5-127">Andare su <https://compliance.microsoft.com> ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d53d5-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="d53d5-128">Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic **su Mostra tutto** e quindi su **Controlla.**</span><span class="sxs-lookup"><span data-stu-id="d53d5-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="d53d5-129">Se il controllo non è attivato per l'organizzazione, viene visualizzato un banner in cui viene richiesto di avviare la registrazione delle attività degli utenti e degli amministratori.</span><span class="sxs-lookup"><span data-stu-id="d53d5-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner nella pagina di controllo](../media/AuditingBanner.png)

3. <span data-ttu-id="d53d5-131">Fai clic sul **banner Avvia registrazione attività utente e** amministratore.</span><span class="sxs-lookup"><span data-stu-id="d53d5-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="d53d5-132">L'applicazione della modifica potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="d53d5-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="d53d5-133">Usare PowerShell per attivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="d53d5-134">Connettersi a PowerShell di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d53d5-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="d53d5-135">Eseguire il comando di PowerShell seguente per attivare il controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d53d5-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="d53d5-136">Viene visualizzato un messaggio che indica che la modifica potrebbe richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="d53d5-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="d53d5-137">Disattivare il controllo</span><span class="sxs-lookup"><span data-stu-id="d53d5-137">Turn off auditing</span></span>

<span data-ttu-id="d53d5-138">È necessario utilizzare Exchange Online PowerShell per disattivare il controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="d53d5-139">Connettersi a PowerShell di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d53d5-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="d53d5-140">Eseguire il comando di PowerShell seguente per disattivare il controllo.</span><span class="sxs-lookup"><span data-stu-id="d53d5-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="d53d5-141">Dopo un po', verificare che il controllo sia disattivato (disabilitato).</span><span class="sxs-lookup"><span data-stu-id="d53d5-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="d53d5-142">È possibile eseguire questa operazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="d53d5-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="d53d5-143">In Exchange Online PowerShell, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d53d5-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="d53d5-144">Il valore di  `False` per la  _proprietà UnifiedAuditLogIngestionEnabled_ indica che il controllo è disattivato.</span><span class="sxs-lookup"><span data-stu-id="d53d5-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="d53d5-145">Passare alla pagina **Controllo** nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="d53d5-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="d53d5-146">Se il controllo non è attivato per l'organizzazione, viene visualizzato un banner in cui viene richiesto di avviare la registrazione delle attività degli utenti e degli amministratori.</span><span class="sxs-lookup"><span data-stu-id="d53d5-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
