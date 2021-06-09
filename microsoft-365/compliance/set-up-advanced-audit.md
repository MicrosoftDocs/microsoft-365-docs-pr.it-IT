---
title: Configurare il controllo avanzato in Microsoft 365
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
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced Audit in modo da poter eseguire indagini forensi quando gli account utente vengono compromessi o per indagare altri incidenti correlati alla sicurezza.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314360"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="16931-103">Configurare il controllo avanzato in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16931-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="16931-104">Se l'organizzazione dispone di una sottoscrizione e di una licenza per gli utenti finali che supporta il controllo avanzato, eseguire la procedura seguente per configurare e utilizzare le funzionalità aggiuntive in Advanced Audit.</span><span class="sxs-lookup"><span data-stu-id="16931-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Flusso di lavoro per la configurazione di Audit avanzato](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="16931-106">Passaggio 1: Configurare il controllo avanzato per gli utenti</span><span class="sxs-lookup"><span data-stu-id="16931-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="16931-107">Le funzionalità di Audit avanzato, come la possibilità di registrare eventi cruciali come MailItemsAccessed e Send, richiedono una licenza E5 appropriata assegnata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="16931-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="16931-108">Inoltre, è necessario che per tali utenti siano abilitati l'app Controllo avanzato e/o il piano di servizio.</span><span class="sxs-lookup"><span data-stu-id="16931-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="16931-109">Per verificare che l'app Controllo avanzato sia assegnata agli utenti, eseguire la procedura seguente per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="16931-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="16931-110">Nell'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/Adminportal) passare a **Utenti** > **Utenti attivi** e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="16931-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="16931-111">Nel riquadro a comparsa delle proprietà utente fare clic su **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="16931-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="16931-112">Nella sezione **Licenze** verificare che all'utente sia assegnata una licenza E5 o a una licenza del componente aggiuntivo appropriata.</span><span class="sxs-lookup"><span data-stu-id="16931-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="16931-113">Per un elenco delle licenze che supportano Advanced Audit, vedere [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span><span class="sxs-lookup"><span data-stu-id="16931-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="16931-114">Espandere la sezione **App** e verificare che la casella di controllo **Controllo avanzato Microsoft 365** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="16931-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="16931-115">Se la casella di controllo non è selezionata, selezionarla e quindi fare clic su **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="16931-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="16931-116">La registrazione dei record di controllo per MailItemsAccessed e Send inizierà entro 24 ore.</span><span class="sxs-lookup"><span data-stu-id="16931-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="16931-117">È necessario eseguire il passaggio 3 per avviare la registrazione di altri due eventi cruciali di controllo avanzato: SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="16931-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="16931-118">Per le organizzazioni che assegnano licenze ai gruppi di utenti usando le licenze basate su gruppi, è necessario disabilitare l'assegnazione delle licenze per il controllo avanzato di Microsoft 365 per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="16931-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="16931-119">Dopo aver salvato le modifiche, verificare che il controllo avanzato di Microsoft 365 sia disabilitato per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="16931-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="16931-120">Quindi, riabilitare l'assegnazione delle licenze per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="16931-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="16931-121">Per istruzioni sulle licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="16931-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="16931-122">Inoltre, se sono state personalizzate le azioni delle cassette postali registrate nelle cassette postali degli utenti o nelle cassette postali condivise, eventuali nuovi eventi cruciali rilasciati da Microsoft non verranno controllati automaticamente in tali cassette postali.</span><span class="sxs-lookup"><span data-stu-id="16931-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="16931-123">Per informazioni sulla modifica delle azioni della cassetta postale controllate per ogni tipo di accesso, vedere la sezione "Modificare o ripristinare le azioni della cassetta postale registrate per impostazione predefinita" in [Gestire il controllo delle cassette postali](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="16931-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="16931-124">Passaggio 2: abilitare gli eventi cruciali</span><span class="sxs-lookup"><span data-stu-id="16931-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="16931-125">È necessario abilitare due eventi cruciali (SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint) per essere registrati quando gli utenti eseguono ricerche in Exchange Online e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="16931-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="16931-126">Per abilitare il controllo di questi due eventi per gli utenti, eseguire il comando seguente (per ogni utente) in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="16931-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="16931-127">In un ambiente multi-geografico, è necessario eseguire il comando **Set-Mailbox** precedente nella foresta in cui si trova la cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="16931-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="16931-128">Per identificare la posizione della cassetta postale dell'utente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="16931-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="16931-129">Se il comando per abilitare il controllo delle query di ricerca è stato eseguito in precedenza in una foresta diversa da quella in cui si trova la cassetta postale dell'utente, è necessario rimuovere il valore SearchQueryInitiated dalla cassetta postale dell'utente eseguendolo e quindi aggiungerlo alla cassetta postale dell'utente nella foresta in cui si trova la cassetta postale `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` dell'utente.</span><span class="sxs-lookup"><span data-stu-id="16931-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="16931-130">Passaggio 3: Configurare i criteri di conservazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="16931-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="16931-131">Oltre ai criteri predefiniti che conservano i record di controllo di Exchange, SharePoint e Azure AD per un anno, puoi creare altri criteri di conservazione del log di audit per soddisfare i requisiti delle operazioni di sicurezza, dell'IT e dei team di conformità dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="16931-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="16931-132">Per altre informazioni, vedere [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="16931-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="16931-133">Passaggio 4: ricerca di eventi cruciali</span><span class="sxs-lookup"><span data-stu-id="16931-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="16931-134">Dopo aver configurato il controllo avanzato per l'organizzazione, è possibile cercare eventi cruciali e altre attività durante l'esecuzione di indagini forensi.</span><span class="sxs-lookup"><span data-stu-id="16931-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="16931-135">Dopo aver completato i passaggi 1 e 2, è possibile cercare nel log di controllo eventi cruciali e altre attività durante indagini forensi su account compromessi e altri tipi di indagini di sicurezza o conformità.</span><span class="sxs-lookup"><span data-stu-id="16931-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="16931-136">Per ulteriori informazioni sull'esecuzione di un'indagine forense sugli account utente compromessi utilizzando l'evento cruciale MailItemsAccessed, vedere [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="16931-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
