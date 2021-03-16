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
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819703"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="68b9c-103">Gestire chi può creare gruppi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68b9c-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="68b9c-104">Per impostazione predefinita, tutti gli utenti possono creare gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68b9c-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="68b9c-105">Questo è l'approccio consigliato perché consente agli utenti di iniziare a collaborare senza richiedere assistenza da parte dell'IT.</span><span class="sxs-lookup"><span data-stu-id="68b9c-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="68b9c-106">Se l'azienda richiede di limitare gli utenti che possono creare gruppi, è possibile farlo seguendo le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="68b9c-107">Quando si limitano gli utenti autorizzati a creare un gruppo, questo influisce su tutti i servizi che si basano sui gruppi per l'accesso, tra cui:</span><span class="sxs-lookup"><span data-stu-id="68b9c-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="68b9c-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="68b9c-108">Outlook</span></span>
- <span data-ttu-id="68b9c-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="68b9c-109">SharePoint</span></span>
- <span data-ttu-id="68b9c-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="68b9c-110">Yammer</span></span>
- <span data-ttu-id="68b9c-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68b9c-111">Microsoft Teams</span></span>
- <span data-ttu-id="68b9c-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="68b9c-112">Microsoft Stream</span></span>
- <span data-ttu-id="68b9c-113">Planner</span><span class="sxs-lookup"><span data-stu-id="68b9c-113">Planner</span></span>
- <span data-ttu-id="68b9c-114">Power BI (classico)</span><span class="sxs-lookup"><span data-stu-id="68b9c-114">Power BI (classic)</span></span>
- <span data-ttu-id="68b9c-115">Project for the web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="68b9c-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="68b9c-116">È possibile limitare la creazione del gruppo di Microsoft 365 ai membri di un gruppo o di un gruppo di sicurezza specifico di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68b9c-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="68b9c-117">Per configurare questo valore, utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68b9c-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="68b9c-118">In questo articolo vengono descritti i passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="68b9c-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="68b9c-119">I passaggi descritti in questo articolo non impediscono ai membri di determinati ruoli di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="68b9c-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="68b9c-120">Gli amministratori globali di Office 365 possono creare gruppi con qualsiasi mezzo, ad esempio l'interfaccia di amministrazione di Microsoft 365, Planner, Teams, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68b9c-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="68b9c-121">Altri ruoli possono creare gruppi con mezzi limitati, elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="68b9c-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="68b9c-122">Amministratore di Exchange: Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="68b9c-123">Supporto di livello partner 1: Interfaccia di amministrazione di Microsoft 365, Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="68b9c-124">Supporto di livello partner 2: Interfaccia di amministrazione di Microsoft 365, Interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="68b9c-125">Writer di directory: Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="68b9c-126">Amministratore di SharePoint: Interfaccia di amministrazione di SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="68b9c-127">Amministratore del servizio Teams: Interfaccia di amministrazione di Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="68b9c-128">Amministratore utente: Interfaccia di amministrazione di Microsoft 365, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68b9c-128">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="68b9c-129">Se si è membri di uno di questi ruoli, è possibile creare gruppi di Microsoft 365 per utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="68b9c-130">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="68b9c-130">Licensing requirements</span></span>

<span data-ttu-id="68b9c-131">Per gestire chi crea i gruppi, le persone seguenti hanno bisogno di licenze di Azure AD Premium o licenze EDU di base di Azure AD assegnate:</span><span class="sxs-lookup"><span data-stu-id="68b9c-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="68b9c-132">L'amministratore che configura queste impostazioni di creazione del gruppo</span><span class="sxs-lookup"><span data-stu-id="68b9c-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="68b9c-133">Membri del gruppo a cui è consentito creare gruppi</span><span class="sxs-lookup"><span data-stu-id="68b9c-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="68b9c-134">Per [ulteriori informazioni su come assegnare licenze di Azure,](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) vedere Assegnare o rimuovere licenze nel portale di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68b9c-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="68b9c-135">Le persone seguenti non hanno bisogno di licenze EDU di Azure AD Premium o Azure AD Basic EDU assegnate:</span><span class="sxs-lookup"><span data-stu-id="68b9c-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="68b9c-136">Persone che sono membri dei gruppi di Microsoft 365 e che non hanno la possibilità di creare altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="68b9c-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="68b9c-137">Passaggio 1: Creare un gruppo per gli utenti che devono creare gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68b9c-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="68b9c-138">È possibile utilizzare un solo gruppo dell'organizzazione per controllare chi è in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="68b9c-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="68b9c-139">Tuttavia, è possibile annidare altri gruppi come membri di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="68b9c-140">Gli amministratori dei ruoli sopra elencati non devono essere membri di questo gruppo: mantengono la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="68b9c-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="68b9c-141">Nell'interfaccia di amministrazione passare alla [pagina Gruppi](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="68b9c-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="68b9c-142">Fare clic **su Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="68b9c-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="68b9c-143">Scegliere il tipo di gruppo desiderato.</span><span class="sxs-lookup"><span data-stu-id="68b9c-143">Choose the group type you want.</span></span> <span data-ttu-id="68b9c-144">Ricordare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-144">Remember the name of the group!</span></span> <span data-ttu-id="68b9c-145">Questo nome sarà necessario in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="68b9c-145">You'll need it later.</span></span>

4. <span data-ttu-id="68b9c-146">Completare la configurazione del gruppo, aggiungere persone o altri gruppi che si desidera possano creare gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="68b9c-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="68b9c-147">Per istruzioni dettagliate, vedere Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di [Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="68b9c-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="68b9c-148">Passaggio 2: Eseguire i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="68b9c-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="68b9c-149">È necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell for Graph (AzureAD) (nome](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) modulo **AzureADPreview)** per modificare l'impostazione di accesso guest a livello di gruppo:</span><span class="sxs-lookup"><span data-stu-id="68b9c-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="68b9c-150">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="68b9c-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="68b9c-151">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="68b9c-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="68b9c-152">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="68b9c-153">Copiare lo script seguente in un editor di testo, ad esempio Blocco note, [o Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="68b9c-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="68b9c-154">Sostituire *\<GroupName\>* con il nome del gruppo creato.</span><span class="sxs-lookup"><span data-stu-id="68b9c-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="68b9c-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="68b9c-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="68b9c-156">Salvare il file come GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="68b9c-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="68b9c-157">Nella finestra di PowerShell passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="68b9c-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="68b9c-158">Eseguire lo script digitando:</span><span class="sxs-lookup"><span data-stu-id="68b9c-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="68b9c-159">e [accedere con l'account amministratore](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="68b9c-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="68b9c-160">L'ultima riga dello script visualizza le impostazioni aggiornate:</span><span class="sxs-lookup"><span data-stu-id="68b9c-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="68b9c-162">Se in futuro si desidera modificare il gruppo utilizzato, è possibile eseguire di nuovo lo script con il nome del nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="68b9c-163">Se si desidera disattivare la restrizione di creazione del gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "True" ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="68b9c-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="68b9c-164">Passaggio 3: Verificare il funzionamento del comando</span><span class="sxs-lookup"><span data-stu-id="68b9c-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="68b9c-165">L'applicazione delle modifiche può richiedere 30 minuti o più.</span><span class="sxs-lookup"><span data-stu-id="68b9c-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="68b9c-166">È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68b9c-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="68b9c-167">Accedere a Microsoft 365 con un account utente di un utente che NON dovrebbe avere la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="68b9c-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="68b9c-168">Ciò significa che non sono membri del gruppo creato o di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="68b9c-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="68b9c-169">Seleziona il **riquadro Planner.**</span><span class="sxs-lookup"><span data-stu-id="68b9c-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="68b9c-170">In Planner seleziona **Nuovo piano nel** riquadro di spostamento sinistro per creare un piano.</span><span class="sxs-lookup"><span data-stu-id="68b9c-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="68b9c-171">Dovrebbe essere visualizzato un messaggio che indica che la creazione del piano e del gruppo è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="68b9c-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="68b9c-172">Ripetere la stessa procedura con un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="68b9c-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="68b9c-173">Se i membri del gruppo non sono in grado di creare gruppi, verificare che non siano bloccati tramite il criterio OWA [cassetta postale](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="68b9c-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="68b9c-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="68b9c-174">Related topics</span></span>

[<span data-ttu-id="68b9c-175">Pianificazione dettagliata della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="68b9c-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="68b9c-176">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="68b9c-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="68b9c-177">Guida introduttiva a PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="68b9c-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="68b9c-178">Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="68b9c-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="68b9c-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="68b9c-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="68b9c-180">Cmdlet di Azure Active Directory per la configurazione delle impostazioni dei gruppi</span><span class="sxs-lookup"><span data-stu-id="68b9c-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
