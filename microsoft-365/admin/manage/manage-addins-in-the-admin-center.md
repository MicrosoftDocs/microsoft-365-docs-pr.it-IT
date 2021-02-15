---
title: Gestire i componenti aggiuntivi nell'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sull'uso dei componenti aggiuntivi centralizzati per distribuire i componenti aggiuntivi a utenti e gruppi dell'organizzazione.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114202"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="cb945-103">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="cb945-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cb945-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="cb945-104">The admin center is changing.</span></span> <span data-ttu-id="cb945-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="cb945-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="cb945-106">I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a [usare il componente aggiuntivo di Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="cb945-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="cb945-107">Dopo che un amministratore distribuisce i componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o attivare, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cb945-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="cb945-108">Per ulteriori informazioni sull'installazione dei componenti aggiuntivi dall'interfaccia di amministrazione, vedere [Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="cb945-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="cb945-109">Stati dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="cb945-109">Add-in states</span></span>

<span data-ttu-id="cb945-110">Un componente aggiuntivo può essere nello stato **Attivo** **o Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="cb945-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="cb945-111">**Stato**</span><span class="sxs-lookup"><span data-stu-id="cb945-111">**State**</span></span>|<span data-ttu-id="cb945-112">**Quando si verifica lo stato**</span><span class="sxs-lookup"><span data-stu-id="cb945-112">**How the state occurs**</span></span>|<span data-ttu-id="cb945-113">**Impatto**</span><span class="sxs-lookup"><span data-stu-id="cb945-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb945-114">**Attivazione**</span><span class="sxs-lookup"><span data-stu-id="cb945-114">**Active**</span></span>  <br/> |<span data-ttu-id="cb945-115">L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="cb945-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="cb945-116">Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.</span><span class="sxs-lookup"><span data-stu-id="cb945-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="cb945-117">**Disattivato**</span><span class="sxs-lookup"><span data-stu-id="cb945-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="cb945-118">L'amministratore ha disattivato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cb945-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="cb945-119">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="cb945-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="cb945-120">Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="cb945-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="cb945-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="cb945-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="cb945-122">L'amministratore ha eliminato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cb945-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="cb945-123">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="cb945-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="cb945-124">È consigliabile eliminare un componente aggiuntivo se non viene più utilizzato da nessuno.</span><span class="sxs-lookup"><span data-stu-id="cb945-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="cb945-125">Ad esempio, la disattivazione di un componente aggiuntivo potrebbe avere senso se un componente aggiuntivo viene usato solo in determinati periodi dell'anno.</span><span class="sxs-lookup"><span data-stu-id="cb945-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="cb945-126">Eliminare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="cb945-126">Delete an add-in</span></span>

<span data-ttu-id="cb945-127">È inoltre possibile eliminare un componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="cb945-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="cb945-128">Nell'interfaccia di amministrazione passare **alla** pagina Servizi & componenti  >  **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="cb945-129">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="cb945-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="cb945-130">Se i passaggi precedenti non sono visualizzati, passare alla sezione Distribuzione centralizzata andando su **Impostazioni**  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="cb945-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="cb945-131">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="cb945-132">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="cb945-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="cb945-133">Fare clic **su Elimina componente aggiuntivo.**</span><span class="sxs-lookup"><span data-stu-id="cb945-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="cb945-134">Rimuovi il pulsante Del componente aggiuntivo nell'angolo in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="cb945-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="cb945-135">Convalidare le selezioni e scegliere **Rimuovi componente aggiuntivo.**</span><span class="sxs-lookup"><span data-stu-id="cb945-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="cb945-136">Modificare l'accesso ai componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="cb945-136">Edit add-in access</span></span>

<span data-ttu-id="cb945-137">Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="cb945-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="cb945-138">Nell'interfaccia di amministrazione passare **alla** pagina Servizi & componenti  >  **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="cb945-139">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="cb945-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="cb945-140">Se i passaggi precedenti non sono visualizzati, passare alla sezione Distribuzione centralizzata andando su **Impostazioni**  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="cb945-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="cb945-141">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="cb945-142">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="cb945-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="cb945-143">Fare clic **su Modifica** in Chi **ha accesso.**</span><span class="sxs-lookup"><span data-stu-id="cb945-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="cb945-144">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cb945-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="cb945-145">Impedire i download dei componenti aggiuntivi disattivando Office Store in tutti i client (ad eccezione di Outlook)</span><span class="sxs-lookup"><span data-stu-id="cb945-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="cb945-146">L'installazione del componente aggiuntivo di Outlook è gestita da [un processo diverso.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb945-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="cb945-147">In quanto organizzazione, è possibile impedire il download di nuovi componenti aggiuntivi di Office dall'Office Store.</span><span class="sxs-lookup"><span data-stu-id="cb945-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="cb945-148">Può essere usato insieme alla distribuzione centralizzata per garantire che solo i componenti aggiuntivi approvati dall'organizzazione siano distribuiti agli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb945-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="cb945-149">**Per disattivare l'acquisizione di componenti aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="cb945-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="cb945-150">Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="cb945-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="cb945-151">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="cb945-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="cb945-152">Se i passaggi precedenti non sono visualizzati, passare alla sezione Distribuzione centralizzata andando su **Impostazioni**  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="cb945-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="cb945-153">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="cb945-154">Selezionare **App e servizi di proprietà dell'utente.**</span><span class="sxs-lookup"><span data-stu-id="cb945-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="cb945-155">Deselezionare l'opzione per consentire agli utenti di accedere all'Office Store.</span><span class="sxs-lookup"><span data-stu-id="cb945-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="cb945-156">Questo impedirà a tutti gli utenti di acquisire i componenti aggiuntivi seguenti dallo Store.</span><span class="sxs-lookup"><span data-stu-id="cb945-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="cb945-157">Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:</span><span class="sxs-lookup"><span data-stu-id="cb945-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="cb945-158">Windows</span><span class="sxs-lookup"><span data-stu-id="cb945-158">Windows</span></span>
    
  - <span data-ttu-id="cb945-159">Mac</span><span class="sxs-lookup"><span data-stu-id="cb945-159">Mac</span></span>
    
  - <span data-ttu-id="cb945-160">Ufficio</span><span class="sxs-lookup"><span data-stu-id="cb945-160">Office</span></span>
    
    
- <span data-ttu-id="cb945-161">Acquisizioni a partire da **AppSource**</span><span class="sxs-lookup"><span data-stu-id="cb945-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="cb945-162">Componenti aggiuntivi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb945-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="cb945-163">Un utente che tenta di accedere all'archivio visualizza il messaggio seguente: **Spiacenti, Microsoft 365** è stato configurato per impedire l'acquisizione individuale di componenti aggiuntivi di Office Store.</span><span class="sxs-lookup"><span data-stu-id="cb945-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="cb945-164">Il supporto per la disattivazione di Office Store è disponibile nelle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb945-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="cb945-165">Windows: 16.0.9001 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb945-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="cb945-166">Mac: 16.10.18011401 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb945-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="cb945-167">iOS: 2.9.18010804 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb945-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="cb945-168">Web - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb945-168">The web - Currently available.</span></span>
    
<span data-ttu-id="cb945-169">Ciò non impedisce a un amministratore di utilizzare la distribuzione centralizzata per assegnare un componente aggiuntivo da Office Store.</span><span class="sxs-lookup"><span data-stu-id="cb945-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="cb945-170">Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso all'uso solo dell'account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb945-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="cb945-171">Per ulteriori informazioni, vedere [Identità, autenticazione e autorizzazione in Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb945-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="cb945-172">Se si impedisce agli utenti di accedere all'Office Store, non sarà possibile eseguire il sideload dei componenti aggiuntivi [di Office per i test.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="cb945-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="cb945-173">Ulteriori informazioni sull'esperienza utente finale con i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="cb945-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="cb945-174">Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a usarlo nelle proprie applicazioni di Office (vedere Iniziare a [usare il componente aggiuntivo di Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="cb945-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="cb945-175">Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="cb945-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="cb945-p110">Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="cb945-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Barra multifunzione di Office con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="cb945-179">Se il componente aggiuntivo distribuito non supporta i comandi dei componenti aggiuntivi o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite I miei **componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="cb945-180">In Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="cb945-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="cb945-181">Selezionare **Inserisci \> componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="cb945-182">Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office.</span><span class="sxs-lookup"><span data-stu-id="cb945-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="cb945-183">Fare doppio clic sul componente aggiuntivo distribuito in precedenza, in questo esempio **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="cb945-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="cb945-184">![Scheda Admin Managed della pagina Componenti aggiuntivi di Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="cb945-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="cb945-185">In Outlook</span><span class="sxs-lookup"><span data-stu-id="cb945-185">In Outlook</span></span>

1. <span data-ttu-id="cb945-186">Sulla barra **multifunzione Home** selezionare Ottieni **componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="cb945-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="cb945-187">![Pulsante Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="cb945-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="cb945-188">Seleziona **Admin-managed** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="cb945-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="cb945-189">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="cb945-189">Learn more</span></span>

[<span data-ttu-id="cb945-190">Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="cb945-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="cb945-191">Altre informazioni sulla creazione e sulla compilazione dei [componenti aggiuntivi per Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="cb945-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="cb945-192">[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti aggiuntivi.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="cb945-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="cb945-193">Risoluzione dei problemi: i componenti aggiuntivi non vengono visualizzati dall'utente</span><span class="sxs-lookup"><span data-stu-id="cb945-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="cb945-194">Minorenni e acquisizione di componenti aggiuntivi da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cb945-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
