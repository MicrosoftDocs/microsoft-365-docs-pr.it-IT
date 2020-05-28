---
title: Creazione, modifica o eliminazione di una visualizzazione utente personalizzata
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Informazioni su come utilizzare i filtri per creare, modificare o eliminare una visualizzazione utente personalizzata in Microsoft 365.
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387214"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="afa7e-103">Creare, modificare o eliminare una visualizzazione utente personalizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="afa7e-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="afa7e-p101">Se l'utente è un amministratore Gestione utenti o un amministratore globale di Office 365, è possibile creare visualizzazioni utente personalizzate per visualizzare un sottoinsieme specifico di utenti. Queste visualizzazioni si aggiungono all'insieme standard di visualizzazioni incluso in Office 365. È possibile creare, modificare o eliminare le visualizzazioni utente personalizzate e quelle create dall'utente sono disponibili per tutti gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="afa7e-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="afa7e-107">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="afa7e-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="afa7e-108">Visualizzazioni utente personalizzate nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="afa7e-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="afa7e-109">Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche verranno visualizzate nell'elenco dei **filtri** che tutti gli amministratori della società vedranno quando andranno alla pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="afa7e-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="afa7e-110">È possibile creare al massimo 50 visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="afa7e-111">Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche vengono visualizzate nell'elenco **visualizzazioni** che tutti gli amministratori della società visualizzano quando passano alla pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="afa7e-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="afa7e-112">È possibile creare al massimo 50 visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="afa7e-113">Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche vengono visualizzate nell'elenco **visualizzazioni** che tutti gli amministratori della società visualizzano quando passano alla pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="afa7e-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="afa7e-114">È possibile creare al massimo 50 visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="afa7e-115">Per impostazione predefinita, le visualizzazioni utente standard vengono mostrate nell'elenco a discesa **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="afa7e-116">I filtri standard includono **tutti gli**utenti, gli utenti con **licenza**, **gli utenti Guest**, l' **accesso consentito**, l' **accesso bloccato**, **gli utenti senza licenza**, **gli utenti con errori**, gli amministratori di **fatturazione**, gli **amministratori globali**, gli amministratori del **supporto tecnico**, gli amministratori dei **Servizi**e gli **amministratori di gestione degli**utenti.</span><span class="sxs-lookup"><span data-stu-id="afa7e-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="afa7e-117">Non è possibile modificare o eliminare le visualizzazioni standard.</span><span class="sxs-lookup"><span data-stu-id="afa7e-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="afa7e-118">Alcune informazioni sulle visualizzazioni standard da tenere presente:</span><span class="sxs-lookup"><span data-stu-id="afa7e-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="afa7e-p106">Alcune visualizzazioni standard mostrano un elenco non ordinato se questo contiene più di 2000 utenti. Per individuare utenti specifici nell'elenco, usare la casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="afa7e-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="afa7e-121">Se non è stato acquistato Microsoft 365 da Microsoft, gli **amministratori di fatturazione** non vengono visualizzati nell'elenco delle visualizzazioni standard.</span><span class="sxs-lookup"><span data-stu-id="afa7e-121">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="afa7e-122">Per ulteriori informazioni, vedere [Assegnazione di ruoli di amministratore](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="afa7e-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="afa7e-123">Scegliere i filtri per la visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="afa7e-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="afa7e-124">È possibile creare e modificare le visualizzazioni personalizzate nel riquadro **filtro personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="afa7e-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="afa7e-125">Se si selezionano più opzioni di filtro, nei risultati vengono inclusi gli utenti che corrispondono a tutti i criteri selezionati.</span><span class="sxs-lookup"><span data-stu-id="afa7e-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="afa7e-126">L'esempio seguente descrive come creare una visualizzazione personalizzata denominata "Utenti canadesi" che mostra tutti gli utenti di un dominio specifico che si trovano in Canada.</span><span class="sxs-lookup"><span data-stu-id="afa7e-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="afa7e-127">**A-Domain** Se si dispone di più domini per l'organizzazione, è possibile scegliere da un elenco a discesa dei domini disponibili.</span><span class="sxs-lookup"><span data-stu-id="afa7e-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="afa7e-128">**Stato di accesso B** Scegliere gli utenti che sono consentiti o bloccati.</span><span class="sxs-lookup"><span data-stu-id="afa7e-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="afa7e-129">**C-posizione** Scegliere un percorso da un elenco a discesa dei paesi.</span><span class="sxs-lookup"><span data-stu-id="afa7e-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="afa7e-130">**Licenza del prodotto D-assegnato** Scegliere da un elenco a discesa di licenze disponibili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afa7e-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="afa7e-131">Usare questo filtro per mostrare gli utenti a cui è assegnata la licenza selezionata.</span><span class="sxs-lookup"><span data-stu-id="afa7e-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="afa7e-132">Gli utenti possono avere anche altre licenze.</span><span class="sxs-lookup"><span data-stu-id="afa7e-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="afa7e-133">È anche possibile filtrare in base ad altri dettagli del profilo utente usati all'interno dell'organizzazione, ad esempio il reparto, la città, lo stato o la provincia, il paese o l'area geografica oppure la posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="afa7e-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="afa7e-134">**Altre condizioni:**</span><span class="sxs-lookup"><span data-stu-id="afa7e-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="afa7e-135">**Utenti sincronizzati:** selezionare questa casella per visualizzare tutti gli utenti sincronizzati con il servizio Active Directory locale, indipendentemente dallo stato di attivazione.</span><span class="sxs-lookup"><span data-stu-id="afa7e-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="afa7e-136">**Utenti con errori:** selezionare questa casella per visualizzare gli utenti con errori di provisioning.</span><span class="sxs-lookup"><span data-stu-id="afa7e-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="afa7e-p110">**Utenti senza licenza:** selezionare questa casella per trovare tutti gli utenti a cui non è stata assegnata una licenza. I risultati di questa visualizzazione possono anche includere utenti che hanno una cassetta postale di Exchange ma non una licenza. Per individuare tali utenti, usare il filtro **Utenti senza licenza con cassette postali o archivi di Exchange**. I risultati di questa visualizzazione possono includere anche utenti che hanno un archivio di Exchange, ma non una licenza.</span><span class="sxs-lookup"><span data-stu-id="afa7e-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="afa7e-141">**Utenti senza licenza con archivi o cassette postali di Exchange** Selezionare questa casella per visualizzare gli account utente creati in Exchange Online e avere una cassetta postale di Exchange, ma non è stata assegnata una licenza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afa7e-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="afa7e-142">I risultati di questo filtro includono gli utenti a cui è stato assegnato o che dispongono di un Exchange archivio.</span><span class="sxs-lookup"><span data-stu-id="afa7e-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="afa7e-143">Il filtro **utenti senza licenza con cassette postali di Exchange** funziona quando:</span><span class="sxs-lookup"><span data-stu-id="afa7e-143">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="afa7e-144">La cassetta postale è stata recentemente convertita da **Shared** a **User** e non ha alcuna licenza.</span><span class="sxs-lookup"><span data-stu-id="afa7e-144">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="afa7e-145">La cassetta postale è stata di recente migrata a Microsoft 365 ma non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="afa7e-145">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="afa7e-146">La cassetta postale è stata creata utilizzando PowerShell e non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="afa7e-146">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="afa7e-147">Viene effettuato il provisioning di una nuova cassetta postale creata in locale con un cmdlet New-RemoteMailbox per l'utente.</span><span class="sxs-lookup"><span data-stu-id="afa7e-147">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="afa7e-148">Se si crea una visualizzazione personalizzata che restituisce più di 2000 utenti, l'elenco utenti risultante non sarà ordinato.</span><span class="sxs-lookup"><span data-stu-id="afa7e-148">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="afa7e-149">In questo caso, utilizzare la casella di ricerca per trovare gli utenti o modificare la visualizzazione personalizzata per affinare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="afa7e-149">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="afa7e-150">Creare una visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="afa7e-150">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="afa7e-151">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="afa7e-152">Nella pagina **utenti attivi** selezionare **filtri** e selezionare **nuovo filtro**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-152">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="afa7e-153">Nella pagina **filtro personalizzato** , immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-153">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="afa7e-154">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="afa7e-154">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="afa7e-155">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="afa7e-156">Nella pagina **utenti attivi** selezionare **visualizzazioni** e quindi **Aggiungi visualizzazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-156">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="afa7e-157">Nella pagina **visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-157">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="afa7e-158">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="afa7e-158">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="afa7e-159">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="afa7e-160">Nella pagina **utenti attivi** selezionare **visualizzazioni** e quindi **Aggiungi visualizzazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-160">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="afa7e-161">Nella pagina **visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-161">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="afa7e-162">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="afa7e-162">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="afa7e-163">Modificare o eliminare una visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="afa7e-163">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="afa7e-164">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="afa7e-165">Nella pagina **utenti attivi** selezionare **filtro**, selezionare il filtro che si desidera modificare e quindi scegliere **Modifica filtro**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-165">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="afa7e-166">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="afa7e-167">Nella pagina **filtro personalizzato** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-167">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="afa7e-168">In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-168">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="afa7e-169">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="afa7e-170">Nella pagina **utenti attivi** selezionare **visualizzazioni**, selezionare il filtro che si desidera modificare, quindi selezionare **modifica questa visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="afa7e-171">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="afa7e-172">Nella pagina **visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="afa7e-173">In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="afa7e-174">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="afa7e-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="afa7e-175">Nella pagina **utenti attivi** selezionare **visualizzazioni**, selezionare il filtro che si desidera modificare, quindi selezionare **modifica questa visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-175">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="afa7e-176">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="afa7e-176">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="afa7e-177">Nella pagina **visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-177">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="afa7e-178">In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="afa7e-178">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     