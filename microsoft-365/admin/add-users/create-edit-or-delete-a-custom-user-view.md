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
description: Informazioni su come usare i filtri per creare, modificare o eliminare una visualizzazione utente personalizzata in Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755573"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="ab122-103">Creazione, modifica o eliminazione di una visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="ab122-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="ab122-104">Se si è un amministratore globale o di gestione utenti di un abbonamento a Microsoft 365 per le aziende, è possibile creare visualizzazioni utente personalizzate per visualizzare un sottoinsieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="ab122-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="ab122-105">Queste visualizzazioni sono in aggiunta al set standard di visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ab122-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="ab122-106">È possibile creare, modificare o eliminare le visualizzazioni utente personalizzate e quelle create dall'utente sono disponibili per tutti gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="ab122-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="ab122-107">Visualizzazioni utente personalizzate nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="ab122-107">Custom user views in the admin center</span></span>

<span data-ttu-id="ab122-108">Quando si crea, si modifica o si elimina una visualizzazione  utente personalizzata, le modifiche verranno visualizzate nell'elenco Filtro visualizzato da tutti gli amministratori della società quando passano alla **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="ab122-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="ab122-109">È possibile creare al massimo 50 visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ab122-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="ab122-110">Per impostazione predefinita, le visualizzazioni utente standard vengono mostrate nell'elenco a discesa **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="ab122-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="ab122-111">I filtri standard includono Tutti gli utenti, Utenti con licenza, Utenti guest, Accesso consentito, Accesso bloccato, Utenti senza licenza, Utenti con  **errori,** Amministratori **fatturazione,** Amministratori **globali,** Amministratori   **helpdesk,** Amministratori del servizio e Amministratori gestione **utenti.**    </span><span class="sxs-lookup"><span data-stu-id="ab122-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="ab122-112">Non è possibile modificare o eliminare le visualizzazioni standard.</span><span class="sxs-lookup"><span data-stu-id="ab122-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="ab122-113">Alcune informazioni sulle visualizzazioni standard da tenere presente:</span><span class="sxs-lookup"><span data-stu-id="ab122-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="ab122-p104">Alcune visualizzazioni standard mostrano un elenco non ordinato se questo contiene più di 2000 utenti. Per individuare utenti specifici nell'elenco, usare la casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ab122-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="ab122-116">Se non hai acquistato Microsoft 365 da **Microsoft,** gli amministratori della fatturazione non vengono visualizzati nell'elenco delle visualizzazioni standard.</span><span class="sxs-lookup"><span data-stu-id="ab122-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="ab122-117">Per ulteriori informazioni, vedere [Assegnazione di ruoli di amministratore](assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ab122-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="ab122-118">Scegliere i filtri per la visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="ab122-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="ab122-119">È possibile creare e modificare le visualizzazioni personalizzate nel **riquadro Filtro** personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ab122-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="ab122-120">Se si selezionano più opzioni di filtro, nei risultati vengono inclusi gli utenti che corrispondono a tutti i criteri selezionati.</span><span class="sxs-lookup"><span data-stu-id="ab122-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="ab122-121">L'esempio seguente descrive come creare una visualizzazione personalizzata denominata "Utenti canadesi" che mostra tutti gli utenti di un dominio specifico che si trovano in Canada.</span><span class="sxs-lookup"><span data-stu-id="ab122-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="ab122-122">**A - Dominio** Se si dispone di più domini per l'organizzazione, è possibile scegliere tra un elenco a discesa di domini disponibili.</span><span class="sxs-lookup"><span data-stu-id="ab122-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="ab122-123">**B - Stato di accesso** Scegliere gli utenti consentiti o bloccati.</span><span class="sxs-lookup"><span data-stu-id="ab122-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="ab122-124">**C - Posizione** Scegliere una posizione da un elenco a discesa di paesi.</span><span class="sxs-lookup"><span data-stu-id="ab122-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="ab122-125">**D - Licenza del prodotto assegnata** Scegliere da un elenco a discesa di licenze disponibili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab122-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="ab122-126">Usare questo filtro per mostrare gli utenti a cui è assegnata la licenza selezionata.</span><span class="sxs-lookup"><span data-stu-id="ab122-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="ab122-127">Gli utenti possono avere anche altre licenze.</span><span class="sxs-lookup"><span data-stu-id="ab122-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="ab122-128">È anche possibile filtrare in base ad altri dettagli del profilo utente usati all'interno dell'organizzazione, ad esempio il reparto, la città, lo stato o la provincia, il paese o l'area geografica oppure la posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="ab122-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="ab122-129">**Altre condizioni:**</span><span class="sxs-lookup"><span data-stu-id="ab122-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="ab122-130">**Utenti sincronizzati:** selezionare questa casella per visualizzare tutti gli utenti sincronizzati con il servizio Active Directory locale, indipendentemente dallo stato di attivazione.</span><span class="sxs-lookup"><span data-stu-id="ab122-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="ab122-131">**Utenti con errori:** selezionare questa casella per visualizzare gli utenti con errori di provisioning.</span><span class="sxs-lookup"><span data-stu-id="ab122-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="ab122-p108">**Utenti senza licenza:** selezionare questa casella per trovare tutti gli utenti a cui non è stata assegnata una licenza. I risultati di questa visualizzazione possono anche includere utenti che hanno una cassetta postale di Exchange ma non una licenza. Per individuare tali utenti, usare il filtro **Utenti senza licenza con cassette postali o archivi di Exchange**. I risultati di questa visualizzazione possono includere anche utenti che hanno un archivio di Exchange, ma non una licenza.</span><span class="sxs-lookup"><span data-stu-id="ab122-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="ab122-136">**Utenti senza licenza con cassette postali o archivi di Exchange** Selezionare questa casella per visualizzare gli account utente creati in Exchange Online e con una cassetta postale di Exchange, ma a cui non è stata assegnata una licenza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab122-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="ab122-137">I risultati di questo filtro includono gli utenti a cui è stato assegnato o che dispongono di un Exchange archivio.</span><span class="sxs-lookup"><span data-stu-id="ab122-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab122-138">Il **filtro Utenti senza licenza con cassette postali di Exchange** funziona quando:</span><span class="sxs-lookup"><span data-stu-id="ab122-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="ab122-139">La cassetta postale è stata recentemente convertita **da condivisa** **a utente** e non dispone di licenza.</span><span class="sxs-lookup"><span data-stu-id="ab122-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="ab122-140">La cassetta postale è stata migrata di recente a Microsoft 365, ma non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="ab122-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="ab122-141">La cassetta postale è stata creata con PowerShell e non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="ab122-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="ab122-142">Viene eseguito il provisioning di una nuova cassetta postale creata in locale con New-RemoteMailbox cmdlet per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ab122-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="ab122-143">Se si crea una visualizzazione personalizzata che restituisce più di 2000 utenti, l'elenco utenti risultante non sarà ordinato.</span><span class="sxs-lookup"><span data-stu-id="ab122-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="ab122-144">In questo caso, utilizzare la casella di ricerca per trovare gli utenti o modificare la visualizzazione personalizzata per perfezionare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ab122-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="ab122-145">Creare una visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="ab122-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ab122-146">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="ab122-147">Nella pagina **Utenti attivi** selezionare **Filtri e** selezionare **Nuovo filtro.**</span><span class="sxs-lookup"><span data-stu-id="ab122-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="ab122-148">Nella pagina **Filtro personalizzato** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ab122-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="ab122-149">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="ab122-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ab122-150">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="ab122-151">Nella pagina **Utenti attivi** selezionare **Visualizzazioni** e **selezionare Aggiungi visualizzazione personalizzata.**</span><span class="sxs-lookup"><span data-stu-id="ab122-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="ab122-152">Nella pagina **Visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ab122-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="ab122-153">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="ab122-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="ab122-154">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="ab122-155">Nella pagina **Utenti attivi** selezionare **Visualizzazioni** e **selezionare Aggiungi visualizzazione personalizzata.**</span><span class="sxs-lookup"><span data-stu-id="ab122-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="ab122-156">Nella pagina **Visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ab122-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="ab122-157">La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.</span><span class="sxs-lookup"><span data-stu-id="ab122-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="ab122-158">Modificare o eliminare una visualizzazione utente personalizzata</span><span class="sxs-lookup"><span data-stu-id="ab122-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ab122-159">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="ab122-160">Nella pagina **Utenti attivi** selezionare **Filtro,** selezionare il filtro che si desidera modificare e quindi selezionare **Modifica filtro.**</span><span class="sxs-lookup"><span data-stu-id="ab122-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ab122-161">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ab122-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="ab122-162">Nella pagina **Filtro personalizzato** modificare le informazioni in base alle esigenze e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ab122-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="ab122-163">In caso contrario, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="ab122-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ab122-164">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="ab122-165">Nella pagina **Utenti attivi** selezionare **Visualizzazioni,** selezionare il filtro che si desidera modificare e quindi selezionare **Modifica visualizzazione.**</span><span class="sxs-lookup"><span data-stu-id="ab122-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ab122-166">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ab122-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="ab122-167">Nella pagina **Visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="ab122-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="ab122-168">In caso contrario, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata.**</span><span class="sxs-lookup"><span data-stu-id="ab122-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ab122-169">Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ab122-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="ab122-170">Nella pagina **Utenti attivi** selezionare **Visualizzazioni,** selezionare il filtro che si desidera modificare e quindi selezionare **Modifica visualizzazione.**</span><span class="sxs-lookup"><span data-stu-id="ab122-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ab122-171">È possibile modificare solo le visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ab122-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="ab122-172">Nella pagina **Visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="ab122-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="ab122-173">In caso contrario, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata.**</span><span class="sxs-lookup"><span data-stu-id="ab122-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     