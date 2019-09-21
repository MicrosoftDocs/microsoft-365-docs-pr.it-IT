---
title: Gestire un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Sintesi: gestire il sito del team di SharePoint Online isolato con queste procedure.'
ms.openlocfilehash: e6ed86421ec199ce785e2daff5e9c5447939e69b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084367"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="6543d-103">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="6543d-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="6543d-104">**Sintesi:** gestire il sito del team di SharePoint Online isolato con queste procedure.</span><span class="sxs-lookup"><span data-stu-id="6543d-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="6543d-105">In questo articolo vengono descritte le comuni operazioni di gestione per un sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="6543d-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="6543d-106">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="6543d-106">Add a new user</span></span>

<span data-ttu-id="6543d-107">Quando un nuovo utente accede al sito, è necessario decidere il livello di partecipazione di tale utente nel sito:</span><span class="sxs-lookup"><span data-stu-id="6543d-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="6543d-108">Amministrazione: aggiungere il nuovo account utente al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="6543d-109">Collaborazione attiva: aggiungere l'account utente al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="6543d-110">Visualizzazione: aggiungere l'account utente al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="6543d-111">Se si gestiscono account utente e gruppi tramite servizi di dominio Active Directory, aggiungere gli utenti adatti ai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di AD DS e attendere la sincronizzazione con Office 365 abbonamento.</span><span class="sxs-lookup"><span data-stu-id="6543d-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6543d-112">Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="6543d-113">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere gli utenti adatti ai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="6543d-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="6543d-114">Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6543d-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="6543d-115">Per aggiungere un account utente a un gruppo di accesso con il relativo nome dell'entità utente (UPN), utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="6543d-116">Per un file di testo che contiene tutti i comandi di PowerShell e un foglio di lavoro di configurazione di Excel che genera comandi di PowerShell in base ai nomi degli account utente e di gruppo, scaricare [Kit di distribuzione del sito di SharePoint Online Team isolato](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="6543d-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="6543d-117">Per aggiungere un account utente a un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="6543d-118">Aggiungere un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="6543d-118">Add a new group</span></span>

<span data-ttu-id="6543d-119">Per aggiungere l'accesso per un intero gruppo, è necessario decidere il livello di partecipazione di tutti i membri del gruppo nel sito:</span><span class="sxs-lookup"><span data-stu-id="6543d-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="6543d-120">Amministrazione: aggiungere il gruppo al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="6543d-121">Collaborazione attiva: aggiungere il gruppo al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="6543d-122">Visualizzazione: aggiungere il gruppo al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="6543d-123">Se si gestiscono account utente e gruppi tramite servizi di dominio Active Directory, aggiungere i gruppi adatti ai gruppi corretti utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6543d-123">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6543d-124">Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-124">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6543d-125">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere i gruppi adatti ai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="6543d-125">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="6543d-126">Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6543d-126">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="6543d-127">Successivamente, utilizzare i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="6543d-127">Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="6543d-128">Rimuovere un utente</span><span class="sxs-lookup"><span data-stu-id="6543d-128">Remove a user</span></span>

<span data-ttu-id="6543d-129">Quando è necessario rimuovere l'accesso di un utente dal sito, si rimuove tale utente dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:</span><span class="sxs-lookup"><span data-stu-id="6543d-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="6543d-130">Amministrazione: rimuovere l'account utente dal gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="6543d-131">Collaborazione attiva: rimuovere l'account utente dal gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="6543d-132">Visualizzazione: rimuovere l'account utente dal gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="6543d-133">Se si gestiscono account utente e gruppi tramite servizi di dominio Active Directory, rimuovere gli utenti idonei dai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="6543d-133">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6543d-134">Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-134">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6543d-135">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per rimuovere gli utenti idonei dai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="6543d-135">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="6543d-136">Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6543d-136">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="6543d-137">Per rimuovere un account utente da un gruppo di accesso con il relativo UPN, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-137">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="6543d-138">Per rimuovere un account utente da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="6543d-139">Rimuovere un gruppo</span><span class="sxs-lookup"><span data-stu-id="6543d-139">Remove a group</span></span>

<span data-ttu-id="6543d-140">Per rimuovere l'accesso per un intero gruppo, si rimuove tale gruppo dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:</span><span class="sxs-lookup"><span data-stu-id="6543d-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="6543d-141">Amministrazione: rimuovere il gruppo dal gruppo di acceso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="6543d-142">Collaborazione attiva: rimuovere il gruppo dal gruppo di acceso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="6543d-143">Visualizzazione: rimuovere il gruppo dal gruppo di acceso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="6543d-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="6543d-144">Se si gestiscono gli account utente e i gruppi tramite Windows Server Active Directory, rimuovere i gruppi corretti dai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con Office 365 abbonamento.</span><span class="sxs-lookup"><span data-stu-id="6543d-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="6543d-145">Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-145">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="6543d-146">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per rimuovere i gruppi corretti dai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="6543d-146">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="6543d-147">Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6543d-147">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="6543d-148">Per rimuovere un gruppo da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6543d-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="6543d-149">Creare una sottocartella di documenti con autorizzazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="6543d-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="6543d-p104">In alcuni casi, un sottoinsieme di utenti che lavorano all'interno del sito isolato necessitano di una posizione più privata per la collaborazione. Per i siti di SharePoint Online, è possibile creare una sottocartella nella cartella Documenti del sito e assegnare autorizzazioni personalizzate. Gli utenti privi di autorizzazioni non saranno in grado di visualizzare la sottocartella.</span><span class="sxs-lookup"><span data-stu-id="6543d-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="6543d-153">Per creare una sottocartella di documenti con autorizzazioni personalizzate, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6543d-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="6543d-p105">Accedere a Office 365 con un account che è membro del gruppo di accesso degli amministratori del sito. Per informazioni, vedere [Dove accedere a Office 365 per le aziende](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6543d-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6543d-156">Accedere al sito del team isolato e fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="6543d-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="6543d-157">Passare alla cartella dei documenti contenente la sottocartella con autorizzazioni personalizzate, creare la cartella e quindi aprirla.</span><span class="sxs-lookup"><span data-stu-id="6543d-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="6543d-158">Fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="6543d-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="6543d-159">Fare clic su **Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6543d-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="6543d-160">Fare clic su **Interrompi ereditarietà autorizzazioni**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6543d-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="6543d-161">Fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="6543d-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="6543d-162">Fare clic su **Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6543d-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="6543d-163">Fare clic su **Concedi autorizzazioni > Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6543d-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="6543d-164">Nella pagina relativa alle autorizzazioni, fare clic su **\<Membri di <nome sito> nell'elenco**.</span><span class="sxs-lookup"><span data-stu-id="6543d-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="6543d-165">Nella pagina **\<Membri di <nome sito>**, selezionare la casella di controllo accanto al gruppo di accesso dei membri del sito, fare clic su **Azioni**, fare clic su **Rimuovi utenti dal gruppo** e infine su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6543d-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="6543d-166">Per aggiungere membri specifici a questa sottocartella, fare clic su **Nuovo > Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="6543d-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="6543d-167">Nella finestra di dialogo **Condividi**, digitare i nomi degli account utente che possono collaborare sui file nella sottocartella, quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="6543d-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="6543d-168">Aggiornare la pagina Web per visualizzare i nuovi risultati.</span><span class="sxs-lookup"><span data-stu-id="6543d-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="6543d-169">In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **\<Visitatori di <nome sito>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di visualizzare i file nella sottocartella (in base alle esigenze).</span><span class="sxs-lookup"><span data-stu-id="6543d-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="6543d-170">In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **\<Proprietari di <nome sito>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di amministrare le autorizzazioni nella sottocartella (in base alle esigenze).</span><span class="sxs-lookup"><span data-stu-id="6543d-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="6543d-171">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser.</span><span class="sxs-lookup"><span data-stu-id="6543d-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6543d-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6543d-172">See Also</span></span>

[<span data-ttu-id="6543d-173">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="6543d-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="6543d-174">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="6543d-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6543d-175">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="6543d-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



