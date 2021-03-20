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
description: Informazioni sull'utilizzo di componenti aggiuntivi centralizzati per distribuire componenti aggiuntivi a utenti e gruppi dell'organizzazione.
ms.openlocfilehash: 0750b6c9b91bc5cbd67d227fadb304bfc6cf7537
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915399"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="2c124-103">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="2c124-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2c124-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="2c124-104">The admin center is changing.</span></span> <span data-ttu-id="2c124-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="2c124-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="2c124-106">I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a usare il componente aggiuntivo [di Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="2c124-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="2c124-107">Dopo che un amministratore distribuisce componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o attivare, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2c124-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="2c124-108">Per ulteriori informazioni sull'installazione di componenti aggiuntivi dall'interfaccia di amministrazione, vedere [Distribuire componenti aggiuntivi nell'interfaccia di amministrazione.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="2c124-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="2c124-109">Stati dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="2c124-109">Add-in states</span></span>

<span data-ttu-id="2c124-110">Un componente aggiuntivo può essere nello stato **Attivo** **o Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="2c124-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="2c124-111">**Stato**</span><span class="sxs-lookup"><span data-stu-id="2c124-111">**State**</span></span>|<span data-ttu-id="2c124-112">**Quando si verifica lo stato**</span><span class="sxs-lookup"><span data-stu-id="2c124-112">**How the state occurs**</span></span>|<span data-ttu-id="2c124-113">**Impatto**</span><span class="sxs-lookup"><span data-stu-id="2c124-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c124-114">**Attivo**</span><span class="sxs-lookup"><span data-stu-id="2c124-114">**Active**</span></span>  <br/> |<span data-ttu-id="2c124-115">L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="2c124-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="2c124-116">Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.</span><span class="sxs-lookup"><span data-stu-id="2c124-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="2c124-117">**Disattivato**</span><span class="sxs-lookup"><span data-stu-id="2c124-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="2c124-118">L'amministratore ha disattivato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2c124-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="2c124-119">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="2c124-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="2c124-120">Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2c124-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="2c124-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="2c124-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="2c124-122">L'amministratore ha eliminato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2c124-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="2c124-123">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="2c124-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="2c124-124">Prendere in considerazione l'eliminazione di un componente aggiuntivo se non viene più utilizzato da nessuno.</span><span class="sxs-lookup"><span data-stu-id="2c124-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="2c124-125">Ad esempio, la disattivazione di un componente aggiuntivo potrebbe avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno.</span><span class="sxs-lookup"><span data-stu-id="2c124-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="2c124-126">Eliminare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="2c124-126">Delete an add-in</span></span>

<span data-ttu-id="2c124-127">È inoltre possibile eliminare un componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="2c124-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="2c124-128">Nell'interfaccia di amministrazione passare alla pagina  >  **Servizi & componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="2c124-129">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="2c124-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="2c124-130">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.**</span><span class="sxs-lookup"><span data-stu-id="2c124-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="2c124-131">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="2c124-132">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="2c124-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="2c124-133">Fare clic **su Elimina componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="2c124-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="2c124-134">Rimuovi il pulsante Componente aggiuntivo nell'angolo in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="2c124-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="2c124-135">Convalidare le selezioni e scegliere **Rimuovi componente aggiuntivo.**</span><span class="sxs-lookup"><span data-stu-id="2c124-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="2c124-136">Modificare l'accesso ai componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="2c124-136">Edit add-in access</span></span>

<span data-ttu-id="2c124-137">Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="2c124-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="2c124-138">Nell'interfaccia di amministrazione passare alla pagina  >  **Servizi & componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="2c124-139">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="2c124-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="2c124-140">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.**</span><span class="sxs-lookup"><span data-stu-id="2c124-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="2c124-141">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="2c124-142">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="2c124-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="2c124-143">Fare clic **su Modifica** in Chi **ha accesso**.</span><span class="sxs-lookup"><span data-stu-id="2c124-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="2c124-144">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2c124-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="2c124-145">Impedire i download di componenti aggiuntivi disattivando Office Store in tutti i client (ad eccezione di Outlook)</span><span class="sxs-lookup"><span data-stu-id="2c124-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="2c124-146">L'installazione del componente aggiuntivo di Outlook è gestita da [un processo diverso.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="2c124-146">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="2c124-147">In quanto organizzazione è possibile impedire il download di nuovi componenti aggiuntivi di Office da Office Store.</span><span class="sxs-lookup"><span data-stu-id="2c124-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="2c124-148">Può essere utilizzato insieme alla distribuzione centralizzata per garantire che solo i componenti aggiuntivi approvati dall'organizzazione siano distribuiti agli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c124-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="2c124-149">**Per disattivare l'acquisizione di componenti aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="2c124-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="2c124-150">Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="2c124-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="2c124-151">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="2c124-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="2c124-152">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.**</span><span class="sxs-lookup"><span data-stu-id="2c124-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="2c124-153">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="2c124-154">Selezionare **App e servizi di proprietà dell'utente.**</span><span class="sxs-lookup"><span data-stu-id="2c124-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="2c124-155">Deselezionare l'opzione per consentire agli utenti di accedere a Office Store.</span><span class="sxs-lookup"><span data-stu-id="2c124-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="2c124-156">Questo impedirà a tutti gli utenti di acquisire i componenti aggiuntivi seguenti dallo Store.</span><span class="sxs-lookup"><span data-stu-id="2c124-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="2c124-157">Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:</span><span class="sxs-lookup"><span data-stu-id="2c124-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="2c124-158">Windows</span><span class="sxs-lookup"><span data-stu-id="2c124-158">Windows</span></span>
    
  - <span data-ttu-id="2c124-159">Mac</span><span class="sxs-lookup"><span data-stu-id="2c124-159">Mac</span></span>
    
  - <span data-ttu-id="2c124-160">Ufficio</span><span class="sxs-lookup"><span data-stu-id="2c124-160">Office</span></span>
    
    
- <span data-ttu-id="2c124-161">Acquisizioni a partire da **AppSource**</span><span class="sxs-lookup"><span data-stu-id="2c124-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="2c124-162">Componenti aggiuntivi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c124-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="2c124-163">Un utente che tenta di accedere all'archivio visualizza il messaggio seguente: **Spiacenti, Microsoft 365 è** stato configurato per impedire l'acquisizione individuale di componenti aggiuntivi di Office Store.</span><span class="sxs-lookup"><span data-stu-id="2c124-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="2c124-164">Il supporto per la disattivazione di Office Store è disponibile nelle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c124-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="2c124-165">Windows: 16.0.9001 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c124-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="2c124-166">Mac: 16.10.18011401 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c124-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="2c124-167">iOS: 2.9.18010804 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c124-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="2c124-168">Web - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c124-168">The web - Currently available.</span></span>
    
<span data-ttu-id="2c124-169">Ciò non impedisce a un amministratore di utilizzare la distribuzione centralizzata per assegnare un componente aggiuntivo da Office Store.</span><span class="sxs-lookup"><span data-stu-id="2c124-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="2c124-170">Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso in modo che utilizzi solo l'account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c124-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="2c124-171">Per ulteriori informazioni, vedere [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span><span class="sxs-lookup"><span data-stu-id="2c124-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="2c124-172">Impedire agli utenti di accedere all'Office Store impedirà anche loro di eseguire il sideload dei componenti aggiuntivi di Office per [il testing.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="2c124-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="2c124-173">Altre informazioni sull'esperienza dell'utente finale con i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="2c124-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="2c124-174">Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a usarlo nelle applicazioni di Office (vedere Iniziare a [usare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="2c124-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="2c124-175">Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="2c124-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="2c124-p110">Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="2c124-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Barra multifunzione di Office con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="2c124-179">Se il componente aggiuntivo distribuito non supporta i comandi dei componenti aggiuntivi o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite I **miei componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="2c124-180">In Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="2c124-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="2c124-181">Selezionare **Inserisci \> componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="2c124-182">Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office.</span><span class="sxs-lookup"><span data-stu-id="2c124-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="2c124-183">Fare doppio clic sul componente aggiuntivo distribuito in precedenza, in questo esempio **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="2c124-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="2c124-184">![Scheda Gestito dall'amministratore della pagina Componenti aggiuntivi di Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="2c124-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="2c124-185">In Outlook</span><span class="sxs-lookup"><span data-stu-id="2c124-185">In Outlook</span></span>

1. <span data-ttu-id="2c124-186">Sulla barra **multifunzione Home** selezionare Ottieni **componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="2c124-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="2c124-187">![Pulsante Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="2c124-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="2c124-188">Seleziona **Gestito dall'amministratore** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="2c124-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="2c124-189">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="2c124-189">Learn more</span></span>

[<span data-ttu-id="2c124-190">Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="2c124-190">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="2c124-191">Altre informazioni sulla creazione e sulla compilazione dei [componenti aggiuntivi per Office](/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="2c124-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="2c124-192">[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti aggiuntivi.](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="2c124-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="2c124-193">Risoluzione dei problemi: l'utente non vede i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="2c124-193">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="2c124-194">Minori e acquisizione di componenti aggiuntivi da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="2c124-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)