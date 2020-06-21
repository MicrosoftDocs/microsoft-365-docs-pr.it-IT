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
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761675"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="4e90c-103">Gestire gli utenti autorizzati a creare gruppi</span><span class="sxs-lookup"><span data-stu-id="4e90c-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="4e90c-104">Poiché è così semplice per gli utenti creare gruppi di Microsoft 365, non si è sommersi dalle richieste di crearle per conto di altre persone.</span><span class="sxs-lookup"><span data-stu-id="4e90c-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="4e90c-105">Tuttavia, a seconda dei requisiti aziendali, può essere opportuno controllare chi è autorizzato a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="4e90c-106">In questo articolo viene illustrato come disabilitare la possibilità di creare gruppi in tutti i servizi di Microsoft 365 che utilizzano i gruppi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="4e90c-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="4e90c-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="4e90c-107">Outlook</span></span>
    
- <span data-ttu-id="4e90c-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e90c-108">SharePoint</span></span>
    
- <span data-ttu-id="4e90c-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="4e90c-109">Yammer</span></span>
    
- <span data-ttu-id="4e90c-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e90c-110">Microsoft Teams</span></span>

- <span data-ttu-id="4e90c-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4e90c-111">Microsoft Stream</span></span>

- <span data-ttu-id="4e90c-112">Planner</span><span class="sxs-lookup"><span data-stu-id="4e90c-112">Planner</span></span>
    
- <span data-ttu-id="4e90c-113">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4e90c-113">PowerBI</span></span>

- <span data-ttu-id="4e90c-114">Progetto per il Web e la Guida di orientamento</span><span class="sxs-lookup"><span data-stu-id="4e90c-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="4e90c-115">È possibile limitare la creazione di un gruppo di Microsoft 365 ai membri di un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="4e90c-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="4e90c-116">Per configurarlo, è necessario utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e90c-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="4e90c-117">In questo articolo vengono illustrati i passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="4e90c-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="4e90c-118">La procedura descritta in questo articolo non impedirà ai membri di determinati ruoli di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="4e90c-119">Gli amministratori globali possono creare gruppi tramite qualsiasi mezzo, ad esempio Microsoft 365 Admin Center, planner, teams, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e90c-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="4e90c-120">Altri ruoli possono creare gruppi tramite mezzi limitati, elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="4e90c-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="4e90c-121">Amministratore di Exchange: interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e90c-122">Supporto di partner Tier 1: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e90c-123">Supporto di partner Tier 2: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4e90c-124">Scrittori di directory: Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="4e90c-125">Amministratore di SharePoint: interfaccia di amministrazione di SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4e90c-126">Amministratore del servizio teams: interfaccia di amministrazione di teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4e90c-127">Amministratore Gestione utenti: interfaccia di amministrazione di Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e90c-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="4e90c-128">Se si è membri di uno di questi ruoli, è possibile creare gruppi Microsoft 365 per gli utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="4e90c-129">Gli utenti che dispongono di questo ruolo sono in grado di creare gruppi connessi in Yammer, indipendentemente dalle impostazioni di PowerShell che potrebbero impedire la creazione.</span><span class="sxs-lookup"><span data-stu-id="4e90c-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4e90c-130">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="4e90c-130">Licensing requirements</span></span>

<span data-ttu-id="4e90c-131">Per gestire gli utenti che creano gruppi, le seguenti persone devono avere licenze Azure AD Premium o licenze di Azure AD Basic EDU ad essi assegnate:</span><span class="sxs-lookup"><span data-stu-id="4e90c-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4e90c-132">L'amministratore che configura queste impostazioni per la creazione di un gruppo</span><span class="sxs-lookup"><span data-stu-id="4e90c-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="4e90c-133">I membri del gruppo di sicurezza a cui è consentito creare i gruppi</span><span class="sxs-lookup"><span data-stu-id="4e90c-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="4e90c-134">Per ulteriori informazioni su come assegnare le licenze di Azure, vedere [assegnare o rimuovere licenze nel portale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .</span><span class="sxs-lookup"><span data-stu-id="4e90c-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="4e90c-135">Gli utenti seguenti non hanno la necessità di assegnare loro le licenze Azure ad Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="4e90c-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4e90c-136">Utenti che sono membri di gruppi di Microsoft 365 e che non hanno la possibilità di creare altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="4e90c-137">Passaggio 1: creare un gruppo di sicurezza per gli utenti che hanno la necessità di creare gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e90c-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="4e90c-138">È possibile utilizzare un solo gruppo di sicurezza nell'organizzazione per controllare chi è in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="4e90c-139">Tuttavia, è possibile annidare altri gruppi di sicurezza come membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="4e90c-140">Ad esempio, il gruppo denominato Consenti creazione gruppi è il gruppo di sicurezza designato e i gruppi Utenti di Microsoft Planner e Utenti di Exchange Online sono membri di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="4e90c-141">Gli amministratori nei ruoli sopra elencati non devono necessariamente essere membri di questo gruppo: mantengono la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e90c-142">Assicurarsi di utilizzare un **gruppo di sicurezza** per limitare gli utenti autorizzati a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="4e90c-143">Se si tenta di utilizzare un gruppo di Microsoft 365, i membri non saranno in grado di creare un gruppo da SharePoint perché verifica la ricerca di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4e90c-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="4e90c-144">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="4e90c-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="4e90c-145">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4e90c-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="4e90c-146">Scegliere **sicurezza** come tipo di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="4e90c-147">Ricordare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-147">Remember the name of the group!</span></span> <span data-ttu-id="4e90c-148">Questo nome sarà necessario in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="4e90c-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="4e90c-149">Completare la configurazione del gruppo di sicurezza, aggiungendo persone o altri gruppi di sicurezza che si desidera siano in grado di creare gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4e90c-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="4e90c-150">Per istruzioni dettagliate, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="4e90c-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="4e90c-151">Passaggio 2: Eseguire i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e90c-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="4e90c-152">Per modificare l'impostazione di accesso Guest a livello di gruppo, è necessario utilizzare la versione di anteprima di [Azure Active Directory PowerShell per Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module Name **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="4e90c-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="4e90c-153">Se non è ancora stata installata una versione del modulo PowerShell di Azure AD, vedere [installare il modulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e seguire le istruzioni per installare la versione di anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="4e90c-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="4e90c-154">Se è installata la versione 2.0 disponibile a livello generale del modulo PowerShell di Azure AD (AzureAD), è necessario disinstallarlo eseguendo `Uninstall-Module AzureAD` nella sessione di PowerShell e quindi installare la versione di anteprima eseguendo `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="4e90c-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="4e90c-155">Se è già stata installata la versione Preview, eseguire `Install-Module AzureADPreview` per verificare che sia la versione più recente di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="4e90c-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="4e90c-156">Copiare lo script riportato di seguito in un editor di testo, ad esempio Blocco note, o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="4e90c-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="4e90c-157">Sostituire *\<SecurityGroupName\>* con il nome del gruppo di sicurezza creato.</span><span class="sxs-lookup"><span data-stu-id="4e90c-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="4e90c-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4e90c-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="4e90c-159">Salvare il file come GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="4e90c-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="4e90c-160">Nella finestra di PowerShell, passare al percorso in cui è stato salvato il file (digitare "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="4e90c-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="4e90c-161">Eseguire lo script digitando:</span><span class="sxs-lookup"><span data-stu-id="4e90c-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="4e90c-162">e [Accedi con l'account di amministratore](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="4e90c-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="4e90c-163">L'ultima riga dello script visualizzerà le impostazioni aggiornate:</span><span class="sxs-lookup"><span data-stu-id="4e90c-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="4e90c-165">Se in futuro si desidera modificare il gruppo di sicurezza utilizzato, è possibile rieseguire lo script con il nome del nuovo gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4e90c-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="4e90c-166">Se si desidera disattivare la restrizione per la creazione di un gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "true" ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="4e90c-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="4e90c-167">Passaggio 3: Verificare il funzionamento del comando</span><span class="sxs-lookup"><span data-stu-id="4e90c-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="4e90c-168">Per rendere effettive le modifiche possono essere necessari 30 minuti o più.</span><span class="sxs-lookup"><span data-stu-id="4e90c-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="4e90c-169">È possibile verificare le nuove impostazioni eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e90c-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="4e90c-170">Accedere con un account utente di utenti che non devono avere la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="4e90c-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="4e90c-171">Ovvero, non sono membri del gruppo di sicurezza creato o di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="4e90c-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="4e90c-172">Selezionare il riquadro **pianificatore** .</span><span class="sxs-lookup"><span data-stu-id="4e90c-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="4e90c-173">In pianificazione selezionare **nuovo piano** nella barra di spostamento a sinistra per creare un piano.</span><span class="sxs-lookup"><span data-stu-id="4e90c-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="4e90c-174">Si dovrebbe ottenere un messaggio che prevede che la creazione di piani e gruppi sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="4e90c-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="4e90c-175">Provare di nuovo la stessa procedura con un membro del gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4e90c-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="4e90c-176">Se i membri del gruppo di sicurezza non sono in grado di creare gruppi, verificare che non siano bloccati tramite il [criterio cassetta postale OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="4e90c-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="4e90c-177">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4e90c-177">Related articles</span></span>

[<span data-ttu-id="4e90c-178">Guida introduttiva a PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="4e90c-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="4e90c-179">Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e90c-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="4e90c-180">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4e90c-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="4e90c-181">Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="4e90c-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
