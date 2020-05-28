---
title: Gestire gli utenti autorizzati a creare gruppi
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Informazioni su come controllare quali utenti possono creare gruppi di Microsoft 365.
ms.openlocfilehash: f3de4ac0856f1281151e6d1c686d90559a5e8544
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387994"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="a61df-103">Gestire gli utenti autorizzati a creare gruppi</span><span class="sxs-lookup"><span data-stu-id="a61df-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="a61df-104">Poiché è così semplice per gli utenti creare gruppi di Microsoft 365, non si è sommersi dalle richieste di crearle per conto di altre persone.</span><span class="sxs-lookup"><span data-stu-id="a61df-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="a61df-105">Tuttavia, a seconda dei requisiti aziendali, può essere opportuno controllare chi è autorizzato a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="a61df-106">In questo articolo viene illustrato come disabilitare la possibilità di creare gruppi in tutti i servizi di Microsoft 365 che utilizzano i gruppi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="a61df-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="a61df-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="a61df-107">Outlook</span></span>
    
- <span data-ttu-id="a61df-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a61df-108">SharePoint</span></span>
    
- <span data-ttu-id="a61df-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="a61df-109">Yammer</span></span>
    
- <span data-ttu-id="a61df-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a61df-110">Microsoft Teams</span></span>

- <span data-ttu-id="a61df-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a61df-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="a61df-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="a61df-112">StaffHub</span></span>
    
- <span data-ttu-id="a61df-113">Planner</span><span class="sxs-lookup"><span data-stu-id="a61df-113">Planner</span></span>
    
- <span data-ttu-id="a61df-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="a61df-114">PowerBI</span></span>

- <span data-ttu-id="a61df-115">Roadmap</span><span class="sxs-lookup"><span data-stu-id="a61df-115">Roadmap</span></span>
    
<span data-ttu-id="a61df-116">È possibile limitare la creazione di un gruppo di Microsoft 365 ai membri di un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="a61df-116">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="a61df-117">Per configurarlo, è necessario utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a61df-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="a61df-118">In questo articolo vengono illustrati i passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="a61df-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="a61df-119">La procedura descritta in questo articolo non impedirà ai membri di determinati ruoli di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="a61df-120">Gli amministratori globali possono creare gruppi tramite qualsiasi mezzo, ad esempio Microsoft 365 Admin Center, planner, teams, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a61df-120">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="a61df-121">Altri ruoli possono creare gruppi tramite mezzi limitati, elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="a61df-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="a61df-122">Amministratore di Exchange: interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a61df-123">Supporto di partner Tier 1: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a61df-124">Supporto di partner Tier 2: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a61df-125">Scrittori di directory: Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="a61df-126">Amministratore di SharePoint: interfaccia di amministrazione di SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="a61df-127">Amministratore del servizio teams: interfaccia di amministrazione di teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="a61df-128">Amministratore Gestione utenti: interfaccia di amministrazione di Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a61df-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="a61df-129">Se si è membri di uno di questi ruoli, è possibile creare gruppi Microsoft 365 per gli utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a61df-129">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="a61df-130">Gli utenti che dispongono di questo ruolo sono in grado di creare gruppi connessi in Yammer, indipendentemente dalle impostazioni di PowerShell che potrebbero impedire la creazione.</span><span class="sxs-lookup"><span data-stu-id="a61df-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a61df-131">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="a61df-131">Licensing requirements</span></span>

<span data-ttu-id="a61df-132">Per gestire gli utenti che creano gruppi, le seguenti persone devono avere licenze Azure AD Premium o licenze di Azure AD Basic EDU ad essi assegnate:</span><span class="sxs-lookup"><span data-stu-id="a61df-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="a61df-133">L'amministratore che configura queste impostazioni per la creazione di un gruppo</span><span class="sxs-lookup"><span data-stu-id="a61df-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="a61df-134">I membri del gruppo di sicurezza a cui è consentito creare i gruppi</span><span class="sxs-lookup"><span data-stu-id="a61df-134">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="a61df-135">Per ulteriori informazioni su come assegnare le licenze di Azure, vedere [assegnare o rimuovere licenze nel portale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .</span><span class="sxs-lookup"><span data-stu-id="a61df-135">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="a61df-136">Gli utenti seguenti non hanno la necessità di assegnare loro le licenze Azure ad Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="a61df-136">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="a61df-137">Utenti che sono membri di gruppi di Microsoft 365 e che non hanno la possibilità di creare altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-137">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="a61df-138">Passaggio 1: creare un gruppo di sicurezza per gli utenti che hanno la necessità di creare gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a61df-138">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="a61df-139">È possibile utilizzare un solo gruppo di sicurezza nell'organizzazione per controllare chi è in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-139">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="a61df-140">Tuttavia, è possibile annidare altri gruppi di sicurezza come membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a61df-140">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="a61df-141">Ad esempio, il gruppo denominato Consenti creazione gruppi è il gruppo di sicurezza designato e i gruppi Utenti di Microsoft Planner e Utenti di Exchange Online sono membri di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="a61df-141">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="a61df-142">Gli amministratori nei ruoli sopra elencati non devono necessariamente essere membri di questo gruppo: mantengono la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-142">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a61df-143">Assicurarsi di utilizzare un **gruppo di sicurezza** per limitare gli utenti autorizzati a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-143">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="a61df-144">Se si tenta di utilizzare un gruppo di Microsoft 365, i membri non saranno in grado di creare un gruppo da SharePoint perché verifica la ricerca di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a61df-144">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="a61df-145">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="a61df-145">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="a61df-146">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a61df-146">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="a61df-147">Scegliere **sicurezza** come tipo di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a61df-147">Choose **Security** as the group type.</span></span> <span data-ttu-id="a61df-148">Ricordare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a61df-148">Remember the name of the group!</span></span> <span data-ttu-id="a61df-149">Questo nome sarà necessario in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a61df-149">You'll need it later.</span></span>
  
4. <span data-ttu-id="a61df-150">Completare la configurazione del gruppo di sicurezza, aggiungendo persone o altri gruppi di sicurezza che si desidera siano in grado di creare gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a61df-150">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="a61df-151">Per istruzioni dettagliate, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="a61df-151">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="a61df-152">Passaggio 2: Eseguire i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a61df-152">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="a61df-153">Per modificare l'impostazione di accesso Guest a livello di gruppo, è necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="a61df-153">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="a61df-154">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="a61df-154">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="a61df-155">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="a61df-155">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="a61df-156">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a61df-156">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="a61df-157">Copiare lo script riportato di seguito in un editor di testo, ad esempio Blocco note, o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="a61df-157">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="a61df-158">Sostituire *\<SecurityGroupName\>* con il nome del gruppo di sicurezza creato.</span><span class="sxs-lookup"><span data-stu-id="a61df-158">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="a61df-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a61df-159">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="a61df-160">Salvare il file come GroupCreators. ps1.</span><span class="sxs-lookup"><span data-stu-id="a61df-160">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="a61df-161">Nella finestra di PowerShell, passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="a61df-161">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="a61df-162">Eseguire lo script digitando:</span><span class="sxs-lookup"><span data-stu-id="a61df-162">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="a61df-163">e [Accedi con l'account di amministratore](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="a61df-163">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="a61df-164">L'ultima riga dello script visualizzerà le impostazioni aggiornate:</span><span class="sxs-lookup"><span data-stu-id="a61df-164">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="a61df-166">Se in futuro si desidera modificare il gruppo di sicurezza utilizzato, è possibile rieseguire lo script con il nome del nuovo gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a61df-166">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="a61df-167">Se si desidera disattivare la restrizione per la creazione di un gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "true" ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="a61df-167">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="a61df-168">Passaggio 4: verificare che funzioni</span><span class="sxs-lookup"><span data-stu-id="a61df-168">Step 4: Verify that it works</span></span>

<span data-ttu-id="a61df-169">Per rendere effettive le modifiche possono essere necessari 30 minuti o più.</span><span class="sxs-lookup"><span data-stu-id="a61df-169">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="a61df-170">È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a61df-170">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="a61df-171">Accedere con un account utente di utenti che non devono avere la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="a61df-171">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="a61df-172">Ovvero, non sono membri del gruppo di sicurezza creato o di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="a61df-172">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="a61df-173">Selezionare il riquadro **pianificatore** .</span><span class="sxs-lookup"><span data-stu-id="a61df-173">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="a61df-174">In pianificazione selezionare **nuovo piano** nella barra di spostamento a sinistra per creare un piano.</span><span class="sxs-lookup"><span data-stu-id="a61df-174">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="a61df-175">Si dovrebbe ottenere un messaggio che prevede che la creazione di piani e gruppi sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="a61df-175">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="a61df-176">Provare di nuovo la stessa procedura con un membro del gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a61df-176">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="a61df-177">Se i membri del gruppo di sicurezza non sono in grado di creare gruppi, verificare che non siano bloccati tramite il [criterio cassetta postale OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="a61df-177">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="a61df-178">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a61df-178">Related articles</span></span>

[<span data-ttu-id="a61df-179">Guida introduttiva a PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="a61df-179">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="a61df-180">Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a61df-180">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="a61df-181">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a61df-181">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="a61df-182">Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="a61df-182">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
