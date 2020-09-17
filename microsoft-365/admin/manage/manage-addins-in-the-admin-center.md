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
description: Informazioni su come distribuire i componenti aggiuntivi per gli utenti e i gruppi dell'organizzazione tramite la distribuzione centralizzata nell'interfaccia di amministrazione.
ms.openlocfilehash: 10bca6776173c07a28b097f44c641c3e65a0cf6c
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948701"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="e8936-103">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e8936-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e8936-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="e8936-104">The admin center is changing.</span></span> <span data-ttu-id="e8936-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e8936-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e8936-106">I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare la modalità di accesso alle informazioni sul Web (vedere [iniziare a utilizzare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="e8936-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="e8936-107">Dopo che un amministratore ha distribuito i componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o disabilitare i componenti aggiuntivi, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="e8936-108">Per ulteriori informazioni sull'installazione dei componenti aggiuntivi dall'interfaccia di amministrazione, vedere [deploy Add-ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="e8936-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="e8936-109">Stati dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="e8936-109">Add-in states</span></span>

<span data-ttu-id="e8936-110">Un componente aggiuntivo può **essere in uno stato attivato o** **disattivato** .</span><span class="sxs-lookup"><span data-stu-id="e8936-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="e8936-111">**Stato**</span><span class="sxs-lookup"><span data-stu-id="e8936-111">**State**</span></span>|<span data-ttu-id="e8936-112">**Quando si verifica lo stato**</span><span class="sxs-lookup"><span data-stu-id="e8936-112">**How the state occurs**</span></span>|<span data-ttu-id="e8936-113">**Impatto**</span><span class="sxs-lookup"><span data-stu-id="e8936-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8936-114">**Attivazione**</span><span class="sxs-lookup"><span data-stu-id="e8936-114">**Active**</span></span>  <br/> |<span data-ttu-id="e8936-115">L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="e8936-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="e8936-116">Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.</span><span class="sxs-lookup"><span data-stu-id="e8936-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="e8936-117">**Disattivato**</span><span class="sxs-lookup"><span data-stu-id="e8936-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="e8936-118">L'amministratore ha disattivato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e8936-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="e8936-119">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="e8936-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="e8936-120">Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e8936-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="e8936-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="e8936-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="e8936-122">L'amministratore ha eliminato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e8936-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="e8936-123">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="e8936-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="e8936-124">Se non è più in uso, è consigliabile eliminare un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e8936-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="e8936-125">La disattivazione di un componente aggiuntivo, ad esempio, può avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno.</span><span class="sxs-lookup"><span data-stu-id="e8936-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="e8936-126">Eliminare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e8936-126">Delete an add-in</span></span>

<span data-ttu-id="e8936-127">È inoltre possibile eliminare un componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="e8936-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="e8936-128">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni**  >  **& componenti** aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="e8936-129">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="e8936-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="e8936-130">Fare clic su **Elimina componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="e8936-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="e8936-131">Rimuovere il pulsante del componente aggiuntivo nell'angolo in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="e8936-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="e8936-132">Convalidare le selezioni e scegliere **Rimuovi componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="e8936-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="e8936-133">Modificare l'accesso del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e8936-133">Edit add-in access</span></span>

<span data-ttu-id="e8936-134">Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="e8936-135">Nell'interfaccia di amministrazione passare alla pagina **Impostazioni**  >  **& componenti** aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="e8936-136">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="e8936-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="e8936-137">Fare clic su **modifica** in **chi ha accesso**.</span><span class="sxs-lookup"><span data-stu-id="e8936-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="e8936-138">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e8936-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="e8936-139">Impedisci download del componente aggiuntivo disattivando l'archivio di Office in tutti i client (eccetto Outlook)</span><span class="sxs-lookup"><span data-stu-id="e8936-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="e8936-140">L'installazione del componente aggiuntivo di Outlook è gestita da un [processo diverso](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8936-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="e8936-141">Come organizzazione, è possibile che si desideri impedire il download di nuovi componenti aggiuntivi di Office dall'Office Store.</span><span class="sxs-lookup"><span data-stu-id="e8936-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="e8936-142">Questo può essere utilizzato insieme alla distribuzione centralizzata per garantire che vengano distribuiti solo i componenti aggiuntivi approvati dall'organizzazione per gli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8936-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="e8936-143">**Per disattivare l'acquisizione del componente aggiuntivo**</span><span class="sxs-lookup"><span data-stu-id="e8936-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="e8936-144">Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="e8936-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="e8936-145">Selezionare **le app e i servizi posseduti dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="e8936-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="e8936-146">Cancellare l'opzione per consentire agli utenti di accedere a Office Store.</span><span class="sxs-lookup"><span data-stu-id="e8936-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="e8936-147">In questo modo tutti gli utenti potranno acquistare i componenti aggiuntivi seguenti dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="e8936-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="e8936-148">Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:</span><span class="sxs-lookup"><span data-stu-id="e8936-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="e8936-149">Windows</span><span class="sxs-lookup"><span data-stu-id="e8936-149">Windows</span></span>
    
  - <span data-ttu-id="e8936-150">Mac</span><span class="sxs-lookup"><span data-stu-id="e8936-150">Mac</span></span>
    
  - <span data-ttu-id="e8936-151">Ufficio</span><span class="sxs-lookup"><span data-stu-id="e8936-151">Office</span></span>
    
    
- <span data-ttu-id="e8936-152">Acquisizioni che iniziano all'interno di **AppSource**</span><span class="sxs-lookup"><span data-stu-id="e8936-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="e8936-153">Componenti aggiuntivi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8936-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="e8936-154">Un utente che cerca di accedere all'archivio vedrà il messaggio seguente: **Microsoft 365 è stato configurato per impedire l'acquisizione individuale dei componenti aggiuntivi di Office Store.**</span><span class="sxs-lookup"><span data-stu-id="e8936-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="e8936-155">Il supporto per la disattivazione di Office Store è disponibile nelle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8936-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="e8936-156">Windows: 16.0.9001-attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="e8936-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="e8936-157">Mac: 16.10.18011401-attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="e8936-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="e8936-158">iOS: 2.9.18010804-attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="e8936-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="e8936-159">Il Web-attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="e8936-159">The web - Currently available.</span></span>
    
<span data-ttu-id="e8936-160">Questo non impedisce a un amministratore di utilizzare la distribuzione centralizzata per assegnare un componente aggiuntivo da Office Store.</span><span class="sxs-lookup"><span data-stu-id="e8936-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="e8936-161">Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso per utilizzare solo l'account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8936-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="e8936-162">Per ulteriori informazioni, vedere [identità, autenticazione e autorizzazione in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8936-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="e8936-163">Ulteriori informazioni sull'esperienza degli utenti finali con i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="e8936-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="e8936-164">Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a utilizzarlo nelle proprie applicazioni di Office (vedere [iniziare a usare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="e8936-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="e8936-165">Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e8936-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="e8936-p107">Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="e8936-p107">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Barra multifunzione di Office con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="e8936-169">Se il componente aggiuntivo distribuito non supporta i comandi del componente aggiuntivo o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite i **componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="e8936-170">In Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="e8936-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="e8936-171">Selezionare **Inserisci \> i componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="e8936-172">Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office.</span><span class="sxs-lookup"><span data-stu-id="e8936-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="e8936-173">Fare doppio clic sul componente aggiuntivo distribuito in precedenza, in questo esempio **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="e8936-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="e8936-174">![Scheda gestita dall'amministratore della pagina dei componenti aggiuntivi di Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="e8936-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="e8936-175">In Outlook</span><span class="sxs-lookup"><span data-stu-id="e8936-175">In Outlook</span></span>

1. <span data-ttu-id="e8936-176">Nella barra multifunzione **Home** selezionare **Ricevi componenti**aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="e8936-177">![Pulsante Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="e8936-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="e8936-178">Selezionare **gestito dall'amministratore** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="e8936-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="e8936-179">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="e8936-179">Learn more</span></span>

[<span data-ttu-id="e8936-180">Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e8936-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="e8936-181">Altre informazioni sulla creazione e sulla compilazione dei [componenti aggiuntivi per Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="e8936-181">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="e8936-182">[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8936-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="e8936-183">Risoluzione dei problemi: utenti che non vedono componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="e8936-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="e8936-184">Minorenni e acquisizione di componenti aggiuntivi da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e8936-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)