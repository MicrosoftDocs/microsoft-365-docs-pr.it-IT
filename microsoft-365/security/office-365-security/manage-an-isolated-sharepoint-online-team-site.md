---
title: Gestire un sito del team di SharePoint Online isolato
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Gestire un sito del team di SharePoint Online isolato, aggiungere nuovi utenti e gruppi, rimuovere utenti e gruppi e creare una sottocartella di documenti con autorizzazioni personalizzate.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289522"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ec4ba-103">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="ec4ba-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec4ba-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ec4ba-104">**Applies to**</span></span>
- [<span data-ttu-id="ec4ba-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec4ba-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ec4ba-106">Microsoft Defender per Office 365 piano 1</span><span class="sxs-lookup"><span data-stu-id="ec4ba-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="ec4ba-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ec4ba-107">SharePoint Online</span></span> 

 <span data-ttu-id="ec4ba-108">**Sintesi:** gestire il sito del team di SharePoint Online isolato con queste procedure.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="ec4ba-109">In questo articolo vengono descritte le comuni operazioni di gestione per un sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="ec4ba-110">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="ec4ba-110">Add a new user</span></span>

<span data-ttu-id="ec4ba-111">Quando un nuovo utente accede al sito, è necessario decidere il livello di partecipazione di tale utente nel sito:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="ec4ba-112">Amministrazione: aggiungere il nuovo account utente al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="ec4ba-113">Collaborazione attiva: aggiungere l'account utente al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="ec4ba-114">Visualizzazione: aggiungere l'account utente al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="ec4ba-115">Se si gestiscono account utente e gruppi tramite Servizi di dominio Active Directory, aggiungere gli utenti appropriati ai gruppi di accesso appropriati utilizzando le normali procedure di gestione degli utenti e dei gruppi di Servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ec4ba-116">Se si gestiscono account utente e gruppi tramite Microsoft 365, è possibile usare l'interfaccia di amministrazione di Microsoft 365 o Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="ec4ba-117">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato il ruolo Amministratore account utente o Amministratore società e usare Gruppi per aggiungere gli utenti appropriati ai gruppi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="ec4ba-118">Per PowerShell, [connettersi innanzitutto con il modulo Azure Active Directory PowerShell per Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ec4ba-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="ec4ba-119">Per aggiungere un account utente a un gruppo di accesso con il relativo nome dell'entità utente (UPN), utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ec4ba-120">Per aggiungere un account utente a un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="ec4ba-121">Aggiungere un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="ec4ba-121">Add a new group</span></span>

<span data-ttu-id="ec4ba-122">Per aggiungere l'accesso per un intero gruppo, è necessario decidere il livello di partecipazione di tutti i membri del gruppo nel sito:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="ec4ba-123">Amministrazione: aggiungere il gruppo al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="ec4ba-124">Collaborazione attiva: aggiungere il gruppo al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="ec4ba-125">Visualizzazione: aggiungere il gruppo al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="ec4ba-126">Se si gestiscono account utente e gruppi tramite Servizi di dominio Active Directory, aggiungere i gruppi appropriati ai gruppi appropriati utilizzando le normali procedure di gestione di utenti e gruppi di Servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ec4ba-127">Se si gestiscono account utente e gruppi tramite Office 365, è possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ec4ba-128">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato il ruolo Amministratore account utente o Amministratore società e usare Gruppi per aggiungere i gruppi appropriati ai gruppi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="ec4ba-129">Per PowerShell, [connettersi innanzitutto con il modulo Azure Active Directory PowerShell per Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ec4ba-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="ec4ba-130">Successivamente, utilizzare i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="ec4ba-131">Rimuovere un utente</span><span class="sxs-lookup"><span data-stu-id="ec4ba-131">Remove a user</span></span>

<span data-ttu-id="ec4ba-132">Quando è necessario rimuovere l'accesso di un utente dal sito, si rimuove tale utente dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="ec4ba-133">Amministrazione: rimuovere l'account utente dal gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="ec4ba-134">Collaborazione attiva: rimuovere l'account utente dal gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="ec4ba-135">Visualizzazione: rimuovere l'account utente dal gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="ec4ba-136">Se si gestiscono account utente e gruppi tramite Servizi di dominio Active Directory, rimuovere gli utenti appropriati dai gruppi di accesso appropriati utilizzando le normali procedure di gestione di utenti e gruppi di Servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ec4ba-137">Se si gestiscono account utente e gruppi tramite Office 365, è possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ec4ba-138">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato il ruolo Amministratore account utente o Amministratore società e usare Gruppi per rimuovere gli utenti appropriati dai gruppi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="ec4ba-139">Per PowerShell, [connettersi innanzitutto con il modulo Azure Active Directory PowerShell per Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ec4ba-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="ec4ba-140">Per rimuovere un account utente da un gruppo di accesso con il relativo UPN, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ec4ba-141">Per rimuovere un account utente da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="ec4ba-142">Rimuovere un gruppo</span><span class="sxs-lookup"><span data-stu-id="ec4ba-142">Remove a group</span></span>

<span data-ttu-id="ec4ba-143">Per rimuovere l'accesso per un intero gruppo, si rimuove tale gruppo dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="ec4ba-144">Amministrazione: rimuovere il gruppo dal gruppo di acceso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="ec4ba-145">Collaborazione attiva: rimuovere il gruppo dal gruppo di acceso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="ec4ba-146">Visualizzazione: rimuovere il gruppo dal gruppo di acceso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="ec4ba-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="ec4ba-147">Se si gestiscono account utente e gruppi tramite Windows Server Active Directory, rimuovere i gruppi appropriati dai gruppi di accesso appropriati utilizzando le normali procedure di gestione di utenti e gruppi di Servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ec4ba-148">Se si gestiscono account utente e gruppi tramite Office 365, è possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ec4ba-149">Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato il ruolo Amministratore account utente o Amministratore società e usare Gruppi per rimuovere i gruppi appropriati dai gruppi di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="ec4ba-150">Per PowerShell, [connettersi innanzitutto con il modulo Azure Active Directory PowerShell per Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ec4ba-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="ec4ba-151">Per rimuovere un gruppo da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="ec4ba-152">Creare una sottocartella di documenti con autorizzazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ec4ba-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="ec4ba-p105">In alcuni casi, un sottoinsieme di utenti che lavorano all'interno del sito isolato necessitano di una posizione più privata per la collaborazione. Per i siti di SharePoint Online, è possibile creare una sottocartella nella cartella Documenti del sito e assegnare autorizzazioni personalizzate. Gli utenti privi di autorizzazioni non saranno in grado di visualizzare la sottocartella.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-p105">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="ec4ba-156">Per creare una sottocartella di documenti con autorizzazioni personalizzate, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec4ba-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="ec4ba-157">Accedere a un account membro del gruppo di accesso degli amministratori per il sito.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="ec4ba-158">Per informazioni, vedere [Dove accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="ec4ba-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ec4ba-159">Accedere al sito del team isolato e fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="ec4ba-160">Passare alla cartella dei documenti contenente la sottocartella con autorizzazioni personalizzate, creare la cartella e quindi aprirla.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="ec4ba-161">Fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-161">Click **Share**.</span></span>

5. <span data-ttu-id="ec4ba-162">Fare clic su **Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="ec4ba-163">Fare clic su **Interrompi ereditarietà autorizzazioni**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="ec4ba-164">Fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-164">Click **Share**.</span></span>

8. <span data-ttu-id="ec4ba-165">Fare clic su **Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="ec4ba-166">Fare clic su **Concedi autorizzazioni > Condiviso con > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="ec4ba-167">Nella pagina relativa alle autorizzazioni, fare clic su **Membri di \<site name> nell'elenco**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="ec4ba-168">Nella pagina **Membri di \<site name>**, selezionare la casella di controllo accanto al gruppo di accesso dei membri del sito, fare clic su **Azioni**, fare clic su **Rimuovi utenti dal gruppo** e infine su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="ec4ba-169">Per aggiungere membri specifici a questa sottocartella, fare clic su **Nuovo > Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="ec4ba-170">Nella finestra di dialogo **Condividi**, digitare i nomi degli account utente che possono collaborare sui file nella sottocartella, quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="ec4ba-171">Aggiornare la pagina Web per visualizzare i nuovi risultati.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="ec4ba-172">In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **Visitatori di \<site name>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di visualizzare i file nella sottocartella (in base alle esigenze).</span><span class="sxs-lookup"><span data-stu-id="ec4ba-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="ec4ba-173">In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **Proprietari di \<site name>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di amministrare le autorizzazioni nella sottocartella (in base alle esigenze).</span><span class="sxs-lookup"><span data-stu-id="ec4ba-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="ec4ba-174">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser.</span><span class="sxs-lookup"><span data-stu-id="ec4ba-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec4ba-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec4ba-175">See Also</span></span>

[<span data-ttu-id="ec4ba-176">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="ec4ba-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="ec4ba-177">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="ec4ba-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ec4ba-178">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="ec4ba-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
