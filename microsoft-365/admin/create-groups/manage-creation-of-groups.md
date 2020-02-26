---
title: Gestire chi può creare gruppi di Office 365
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Informazioni su come controllare gli utenti che possono creare gruppi di Office 365.
ms.openlocfilehash: a211cb3b69348a4d4a401a3c318fe019d8fd257f
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277193"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="7320b-103">Gestire chi può creare gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="7320b-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="7320b-104">Gli utenti possono creare gruppi di Office 365 con molta facilità, quindi gli amministratori non vengono inondati di richieste di crearli per conto di altre persone.</span><span class="sxs-lookup"><span data-stu-id="7320b-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="7320b-105">Tuttavia, a seconda dei requisiti aziendali, può essere opportuno controllare chi è autorizzato a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="7320b-106">Questo articolo spiega come impedire la creazione di gruppi **in tutti i servizi di Office 365 che usano i gruppi**:</span><span class="sxs-lookup"><span data-stu-id="7320b-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="7320b-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="7320b-107">Outlook</span></span>
    
- <span data-ttu-id="7320b-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7320b-108">SharePoint</span></span>
    
- <span data-ttu-id="7320b-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="7320b-109">Yammer</span></span>
    
- <span data-ttu-id="7320b-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7320b-110">Microsoft Teams</span></span>

- <span data-ttu-id="7320b-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7320b-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="7320b-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="7320b-112">StaffHub</span></span>
    
- <span data-ttu-id="7320b-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7320b-113">Planner</span></span>
    
- <span data-ttu-id="7320b-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="7320b-114">PowerBI</span></span>

- <span data-ttu-id="7320b-115">Roadmap</span><span class="sxs-lookup"><span data-stu-id="7320b-115">Roadmap</span></span>
    
<span data-ttu-id="7320b-116">È possibile limitare la creazione dei gruppi di Office 365 ai membri di un determinato gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7320b-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="7320b-117">Per configurarlo, è necessario utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7320b-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="7320b-118">In questo articolo vengono illustrati i passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="7320b-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="7320b-119">La procedura descritta in questo articolo non impedirà ai membri di determinati ruoli di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7320b-120">Gli amministratori globali di Office 365 possono creare gruppi tramite qualsiasi mezzo, ad esempio Microsoft 365 Admin Center, planner, teams, Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7320b-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7320b-121">Altri ruoli possono creare gruppi tramite mezzi limitati, elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7320b-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="7320b-122">Amministratore di Exchange: interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7320b-123">Supporto di partner Tier 1: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7320b-124">Supporto di partner Tier 2: interfaccia di amministrazione di Microsoft 365, interfaccia di amministrazione di Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7320b-125">Scrittori di directory: Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="7320b-126">Amministratore di SharePoint: interfaccia di amministrazione di SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7320b-127">Amministratore del servizio teams: interfaccia di amministrazione di teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7320b-128">Amministratore Gestione utenti: interfaccia di amministrazione di Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7320b-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="7320b-129">I membri di ognuno di questi ruoli possono creare Gruppi di Office 365 per utenti con restrizioni e quindi assegnare l'utente come proprietario del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7320b-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="7320b-130">Gli utenti che dispongono di questo ruolo sono in grado di creare gruppi connessi in Yammer, indipendentemente dalle impostazioni di PowerShell che potrebbero impedire la creazione.</span><span class="sxs-lookup"><span data-stu-id="7320b-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7320b-131">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="7320b-131">Licensing requirements</span></span>

<span data-ttu-id="7320b-132">Per gestire gli utenti che creano gruppi, le seguenti persone devono avere licenze Azure AD Premium o licenze di Azure AD Basic EDU ad essi assegnate:</span><span class="sxs-lookup"><span data-stu-id="7320b-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7320b-133">L'amministratore che configura queste impostazioni per la creazione di un gruppo</span><span class="sxs-lookup"><span data-stu-id="7320b-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7320b-134">I membri del gruppo di sicurezza a cui è consentito creare i gruppi</span><span class="sxs-lookup"><span data-stu-id="7320b-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="7320b-135">Gli utenti seguenti non hanno la necessità di assegnare loro le licenze Azure ad Premium o Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="7320b-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7320b-136">Utenti che sono membri di gruppi di Office 365 e che non hanno la possibilità di creare altri gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="7320b-137">Passaggio 1: Creare un gruppo di sicurezza per gli utenti che devono creare Gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="7320b-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="7320b-138">È possibile utilizzare un solo gruppo di sicurezza nell'organizzazione per controllare chi è in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7320b-139">Tuttavia, è possibile annidare altri gruppi di sicurezza come membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7320b-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="7320b-140">Ad esempio, il gruppo denominato Consenti creazione gruppi è il gruppo di sicurezza designato e i gruppi Utenti di Microsoft Planner e Utenti di Exchange Online sono membri di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="7320b-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="7320b-141">Gli amministratori nei ruoli sopra elencati non devono necessariamente essere membri di questo gruppo: mantengono la possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7320b-142">Assicurarsi di utilizzare un **gruppo di sicurezza** per limitare gli utenti autorizzati a creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="7320b-143">Se si prova a usare un gruppo di Office 365, i membri non saranno in grado di creare un gruppo da SharePoint, che verificherà infatti che il gruppo sia un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7320b-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="7320b-144">Nell'interfaccia di amministrazione, andare alla <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> \> pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="7320b-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="7320b-145">Fare clic su **Aggiungi gruppo**.</span><span class="sxs-lookup"><span data-stu-id="7320b-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7320b-146">Scegliere **sicurezza** come tipo di gruppo.</span><span class="sxs-lookup"><span data-stu-id="7320b-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="7320b-147">Ricordare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7320b-147">Remember the name of the group!</span></span> <span data-ttu-id="7320b-148">Questo nome sarà necessario in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7320b-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="7320b-149">Completare la configurazione del gruppo di sicurezza, aggiungendo persone o altri gruppi di sicurezza che si desidera siano in grado di creare gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7320b-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="7320b-150">Per istruzioni dettagliate, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="7320b-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="7320b-151">Passaggio 2: installare la versione di anteprima di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="7320b-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="7320b-152">Queste procedure richiedono la versione di anteprima di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="7320b-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="7320b-153">La versione GA non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="7320b-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7320b-154">Non è possibile installare contemporaneamente entrambe le versioni di anteprima e di GA nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="7320b-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="7320b-155">È possibile installare il modulo in Windows 10, Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="7320b-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="7320b-156">È consigliabile avere  *sempre*  la versione più aggiornata: disinstallare la versione precedente di AzureADPreview o AzureAD e ottenere quella più recente.</span><span class="sxs-lookup"><span data-stu-id="7320b-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="7320b-157">Nella barra di ricerca digitare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7320b-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="7320b-158">Fare clic con il pulsante destro del mouse su **Windows PowerShell** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="7320b-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![Aprire PowerShell con "Esegui come amministratore".](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="7320b-160">Impostare il criterio su RemoteSigned utilizzando [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="7320b-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="7320b-161">Controllare il modulo installato:</span><span class="sxs-lookup"><span data-stu-id="7320b-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="7320b-162">Per disinstallare una versione precedente di AzureADPreview o AzureAD, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="7320b-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="7320b-163">oppure</span><span class="sxs-lookup"><span data-stu-id="7320b-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="7320b-164">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="7320b-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="7320b-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="7320b-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="7320b-166">Lasciare aperta la finestra di PowerShell per il passaggio 3, in basso.</span><span class="sxs-lookup"><span data-stu-id="7320b-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="7320b-167">Passaggio 3: eseguire i comandi di PowerShell</span><span class="sxs-lookup"><span data-stu-id="7320b-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="7320b-168">Copiare lo script riportato di seguito in un editor di testo, ad esempio Blocco note, o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="7320b-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7320b-169">Sostituire \* \<SecurityGroupName\> \* con il nome del gruppo di sicurezza creato.</span><span class="sxs-lookup"><span data-stu-id="7320b-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="7320b-170">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7320b-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7320b-171">Salvare il file come GroupCreators. ps1.</span><span class="sxs-lookup"><span data-stu-id="7320b-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="7320b-172">Nella finestra di PowerShell, passare al percorso in cui è stato salvato il file (digitare " <FileLocation>CD").</span><span class="sxs-lookup"><span data-stu-id="7320b-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7320b-173">Eseguire lo script digitando:</span><span class="sxs-lookup"><span data-stu-id="7320b-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7320b-174">e [Accedi con l'account di amministratore](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="7320b-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="7320b-175">L'ultima riga dello script visualizzerà le impostazioni aggiornate:</span><span class="sxs-lookup"><span data-stu-id="7320b-175">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7320b-177">Se in futuro si desidera modificare il gruppo di sicurezza utilizzato, è possibile rieseguire lo script con il nome del nuovo gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7320b-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="7320b-178">Se si desidera disattivare la restrizione per la creazione di un gruppo e consentire nuovamente a tutti gli utenti di creare gruppi, impostare $GroupName su "" e $AllowGroupCreation su "true" ed eseguire di nuovo lo script.</span><span class="sxs-lookup"><span data-stu-id="7320b-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="7320b-179">Passaggio 4: verificare che funzioni</span><span class="sxs-lookup"><span data-stu-id="7320b-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="7320b-180">Accedere a Office 365 con un account utente che non disponga della possibilità di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="7320b-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7320b-181">Ovvero, non sono membri del gruppo di sicurezza creato o di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="7320b-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="7320b-182">Selezionare il riquadro **pianificatore** .</span><span class="sxs-lookup"><span data-stu-id="7320b-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="7320b-183">In pianificazione selezionare **nuovo piano** nella barra di spostamento a sinistra per creare un piano.</span><span class="sxs-lookup"><span data-stu-id="7320b-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="7320b-184">Si dovrebbe ottenere un messaggio che prevede che la creazione di piani e gruppi sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="7320b-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7320b-185">Provare di nuovo la stessa procedura con un membro del gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7320b-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="7320b-186">Se i membri del gruppo di sicurezza non sono in grado di creare gruppi, verificare che non siano bloccati tramite il [criterio cassetta postale OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="7320b-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="7320b-187">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="7320b-187">Related articles</span></span>

[<span data-ttu-id="7320b-188">Guida introduttiva a PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="7320b-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7320b-189">Configurare la gestione dei gruppi in modalità self-service in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7320b-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7320b-190">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7320b-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7320b-191">Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="7320b-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
