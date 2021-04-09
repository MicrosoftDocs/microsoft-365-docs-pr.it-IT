---
title: Gestire chi può creare gruppi in Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Informazioni su come controllare quali utenti possono creare gruppi di Microsoft 365.
ms.openlocfilehash: 092ff821911ef0af2b7867e1b870b68b1b6355b3
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656986"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="e943d-103">Gestire chi può creare gruppi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e943d-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="e943d-104">Per impostazione predefinita, tutti gli utenti possono creare gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e943d-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="e943d-105">Questo è l'approccio consigliato perché consente agli utenti di iniziare a collaborare senza richiedere assistenza da parte dell'IT.</span><span class="sxs-lookup"><span data-stu-id="e943d-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="e943d-106">Se l'azienda richiede di limitare gli utenti che possono creare gruppi, è possibile limitare la creazione di gruppi di Microsoft 365 ai membri di un gruppo o di un gruppo di sicurezza di Microsoft 365 specifico.</span><span class="sxs-lookup"><span data-stu-id="e943d-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="e943d-107">Se si è preoccupati per la creazione di team o gruppi non conformi agli standard aziendali, è consigliabile richiedere agli utenti di completare un corso di formazione e quindi aggiungerli al gruppo di utenti consentiti.</span><span class="sxs-lookup"><span data-stu-id="e943d-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="e943d-108">Quando si limitano gli utenti autorizzati a creare un gruppo, questo influisce su tutti i servizi che si basano sui gruppi per l'accesso, tra cui:</span><span class="sxs-lookup"><span data-stu-id="e943d-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="e943d-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="e943d-109">Outlook</span></span>
- <span data-ttu-id="e943d-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e943d-110">SharePoint</span></span>
- <span data-ttu-id="e943d-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="e943d-111">Yammer</span></span>
- <span data-ttu-id="e943d-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e943d-112">Microsoft Teams</span></span>
- <span data-ttu-id="e943d-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="e943d-113">Microsoft Stream</span></span>
- <span data-ttu-id="e943d-114">Planner</span><span class="sxs-lookup"><span data-stu-id="e943d-114">Planner</span></span>
- <span data-ttu-id="e943d-115">Power BI (classico)</span><span class="sxs-lookup"><span data-stu-id="e943d-115">Power BI (classic)</span></span>
- <span data-ttu-id="e943d-116">Project for the web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="e943d-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="e943d-117">I passaggi descritti in questo articolo non impediscono ai membri di determinati ruoli di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="e943d-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="e943d-118">Gli amministratori globali di Office 365 possono creare gruppi tramite l'interfaccia di amministrazione di Microsoft 365, Planner, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e943d-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="e943d-119">Altri ruoli possono creare gruppi con mezzi limitati, elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e943d-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="e943d-120">Amministratore di Exchange: Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="e943d-121">Supporto di livello partner 1: Interfaccia di amministrazione di Microsoft 365, Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="e943d-122">Supporto di livello partner 2: Interfaccia di amministrazione di Microsoft 365, Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="e943d-123">Writer di directory: Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="e943d-124">Amministratore di SharePoint: Interfaccia di amministrazione di SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="e943d-125">Amministratore del servizio Teams: Interfaccia di amministrazione di Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="e943d-126">Amministratore utente: Interfaccia di amministrazione di Microsoft 365, Azure AD</span><span class="sxs-lookup"><span data-stu-id="e943d-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="e943d-127">Se si è membri di uno di questi ruoli, è possibile creare gruppi di Microsoft 365 per utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.</span><span class="sxs-lookup"><span data-stu-id="e943d-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="e943d-128">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="e943d-128">Licensing requirements</span></span>

<span data-ttu-id="e943d-129">Per gestire chi crea i gruppi, le persone seguenti hanno bisogno di licenze di Azure AD Premium o licenze EDU di base di Azure AD assegnate:</span><span class="sxs-lookup"><span data-stu-id="e943d-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="e943d-130">L'amministratore che configura queste impostazioni di creazione del gruppo</span><span class="sxs-lookup"><span data-stu-id="e943d-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="e943d-131">Membri del gruppo a cui è consentito creare gruppi</span><span class="sxs-lookup"><span data-stu-id="e943d-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="e943d-132">Per [ulteriori informazioni su come assegnare licenze di Azure,](/azure/active-directory/fundamentals/license-users-groups) vedere Assegnare o rimuovere licenze nel portale di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e943d-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="e943d-133">Le persone seguenti non hanno bisogno di licenze EDU di Azure AD Premium o Azure AD Basic EDU assegnate:</span><span class="sxs-lookup"><span data-stu-id="e943d-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="e943d-134">Persone che sono membri dei gruppi di Microsoft 365 e che non hanno la possibilità di creare altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="e943d-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="e943d-135">Passaggio 1: Creare un gruppo per gli utenti che devono creare gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e943d-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="e943d-136">È possibile utilizzare un solo gruppo dell'organizzazione per controllare chi è in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="e943d-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="e943d-137">Tuttavia, è possibile annidare altri gruppi come membri di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="e943d-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="e943d-138">Gli amministratori dei ruoli sopra elencati non devono essere membri di questo gruppo: mantengono la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="e943d-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="e943d-139">Nell'interfaccia di amministrazione passare alla [pagina Gruppi](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="e943d-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="e943d-140">Fare clic **su Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e943d-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="e943d-141">Scegliere il tipo di gruppo desiderato.</span><span class="sxs-lookup"><span data-stu-id="e943d-141">Choose the group type you want.</span></span> <span data-ttu-id="e943d-142">Ricordare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="e943d-142">Remember the name of the group!</span></span> <span data-ttu-id="e943d-143">Questo nome sarà necessario in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e943d-143">You'll need it later.</span></span>

4. <span data-ttu-id="e943d-144">Completare la configurazione del gruppo, aggiungere persone o altri gruppi che si desidera possano creare gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e943d-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="e943d-145">Per istruzioni dettagliate, vedere Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di [Microsoft 365.](../admin/email/create-edit-or-delete-a-security-group.md)</span><span class="sxs-lookup"><span data-stu-id="e943d-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="e943d-146">Passaggio 2: Eseguire i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e943d-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="e943d-147">È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell for Graph (AzureAD) (nome](/powershell/azure/active-directory/install-adv2) modulo **AzureADPreview)** per modificare l'impostazione di accesso guest a livello di gruppo:</span><span class="sxs-lookup"><span data-stu-id="e943d-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="e943d-148">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="e943d-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="e943d-149">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="e943d-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="e943d-150">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="e943d-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="e943d-151">Copiare lo script seguente in un editor di testo, ad esempio Blocco note, [o Windows PowerShell ISE.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="e943d-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="e943d-152">Sostituire *\<GroupName\>* con il nome del gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="e943d-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="e943d-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e943d-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="e943d-154">Salvare il file come GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="e943d-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="e943d-155">Nella finestra di PowerShell passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="e943d-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="e943d-156">Eseguire lo script digitando:</span><span class="sxs-lookup"><span data-stu-id="e943d-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="e943d-157">e [accedere con l'account amministratore](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="e943d-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="e943d-158">L'ultima riga dello script visualizza le impostazioni aggiornate:</span><span class="sxs-lookup"><span data-stu-id="e943d-158">The last line of the script will display the updated settings:</span></span>

![Screenshot dell'output dello script di PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="e943d-160">Se in futuro si desidera modificare il gruppo utilizzato, è possibile eseguire di nuovo lo script con il nome del nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="e943d-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="e943d-161">Se si desidera disattivare la restrizione di creazione del gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "True" ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="e943d-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="e943d-162">Passaggio 3: Verificare il funzionamento del comando</span><span class="sxs-lookup"><span data-stu-id="e943d-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="e943d-163">L'applicazione delle modifiche può richiedere 30 minuti o più.</span><span class="sxs-lookup"><span data-stu-id="e943d-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="e943d-164">È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e943d-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="e943d-165">Accedere a Microsoft 365 con un account utente di un utente che NON dovrebbe avere la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="e943d-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="e943d-166">Ciò significa che non sono membri del gruppo creato o di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="e943d-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="e943d-167">Seleziona il **riquadro Planner.**</span><span class="sxs-lookup"><span data-stu-id="e943d-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="e943d-168">In Planner seleziona **Nuovo piano nel** riquadro di spostamento sinistro per creare un piano.</span><span class="sxs-lookup"><span data-stu-id="e943d-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="e943d-169">Dovrebbe essere visualizzato un messaggio che indica che la creazione del piano e del gruppo è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e943d-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="e943d-170">Ripetere la stessa procedura con un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="e943d-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="e943d-171">Se i membri del gruppo non sono in grado di creare gruppi, verificare che non siano bloccati tramite il criterio OWA [cassetta postale](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="e943d-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e943d-172">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e943d-172">Related topics</span></span>

[<span data-ttu-id="e943d-173">Pianificazione dettagliata della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="e943d-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="e943d-174">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="e943d-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="e943d-175">Guida introduttiva a PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="e943d-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="e943d-176">Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e943d-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="e943d-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="e943d-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="e943d-178">Cmdlet di Azure Active Directory per la configurazione delle impostazioni dei gruppi</span><span class="sxs-lookup"><span data-stu-id="e943d-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
