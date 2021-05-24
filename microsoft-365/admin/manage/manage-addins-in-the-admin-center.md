---
title: Gestire i componenti aggiuntivi nell'interfaccia di amministrazione
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sull'utilizzo di componenti aggiuntivi centralizzati per distribuire componenti aggiuntivi a utenti e gruppi dell'organizzazione.
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636059"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="bf7cd-103">Gestire i componenti aggiuntivi nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="bf7cd-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="bf7cd-104">Office componenti aggiuntivi consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a usare il Office [aggiuntivo).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="bf7cd-105">Dopo che un amministratore distribuisce componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o attivare, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="bf7cd-106">Per ulteriori informazioni sull'installazione di componenti aggiuntivi dall'interfaccia di amministrazione, vedere [Distribuire componenti aggiuntivi nell'interfaccia di amministrazione.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="bf7cd-107">Stati dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="bf7cd-107">Add-in states</span></span>

<span data-ttu-id="bf7cd-108">Un componente aggiuntivo può essere nello stato **Attivo** **o Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="bf7cd-109">Stato</span><span class="sxs-lookup"><span data-stu-id="bf7cd-109">State</span></span> | <span data-ttu-id="bf7cd-110">Quando si verifica lo stato</span><span class="sxs-lookup"><span data-stu-id="bf7cd-110">How the state occurs</span></span> | <span data-ttu-id="bf7cd-111">Impatto</span><span class="sxs-lookup"><span data-stu-id="bf7cd-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="bf7cd-112">**Attivo**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-112">**Active**</span></span>  <br/> |<span data-ttu-id="bf7cd-113">L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="bf7cd-114">Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="bf7cd-115">**Disattivato**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="bf7cd-116">L'amministratore ha disattivato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="bf7cd-117">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="bf7cd-118">Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="bf7cd-119">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="bf7cd-120">L'amministratore ha eliminato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="bf7cd-121">Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="bf7cd-122">Prendere in considerazione l'eliminazione di un componente aggiuntivo se non viene più utilizzato da nessuno.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="bf7cd-123">Ad esempio, la disattivazione di un componente aggiuntivo potrebbe avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="bf7cd-124">Eliminare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="bf7cd-124">Delete an add-in</span></span>

<span data-ttu-id="bf7cd-125">È inoltre possibile eliminare un componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="bf7cd-126">Nell'interfaccia di amministrazione passare alla **Impostazioni**  >  **Servizi & componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf7cd-127">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="bf7cd-128">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a Impostazioni  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="bf7cd-129">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="bf7cd-130">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="bf7cd-131">Fare clic **su Elimina componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="bf7cd-132">Rimuovi il pulsante Componente aggiuntivo nell'angolo in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="bf7cd-133">Confermare le selezioni e scegliere **Rimuovi componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="bf7cd-134">Modificare l'accesso ai componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="bf7cd-134">Edit add-in access</span></span>

<span data-ttu-id="bf7cd-135">Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="bf7cd-136">Nell'interfaccia di amministrazione passare alla **Impostazioni**  >  **Servizi & componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf7cd-137">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="bf7cd-138">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a Impostazioni  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="bf7cd-139">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="bf7cd-140">Selezionare il componente aggiuntivo distribuito.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="bf7cd-141">Fare clic **su Modifica** in **Who accesso**.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="bf7cd-142">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="bf7cd-143">Impedisci download di componenti aggiuntivi disattivando Office Store in tutti i client (ad Outlook)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="bf7cd-144">Outlook'installazione del componente aggiuntivo è gestita da [un processo diverso.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="bf7cd-145">In quanto organizzazione, potresti voler impedire il download di nuovi Office componenti aggiuntivi dal Office Store.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="bf7cd-146">Può essere utilizzato insieme alla distribuzione centralizzata per garantire che solo i componenti aggiuntivi approvati dall'organizzazione siano distribuiti agli utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="bf7cd-147">**Per disattivare l'acquisizione di componenti aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="bf7cd-148">Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="bf7cd-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf7cd-149">L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="bf7cd-150">Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a Impostazioni  >  **app integrate.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="bf7cd-151">Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="bf7cd-152">Selezionare **App e servizi di proprietà dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="bf7cd-153">Deselezionare l'opzione per consentire agli utenti di accedere a Office Store.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="bf7cd-154">Questo impedirà a tutti gli utenti di acquisire i componenti aggiuntivi seguenti dallo Store.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="bf7cd-155">Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:</span><span class="sxs-lookup"><span data-stu-id="bf7cd-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="bf7cd-156">Windows</span><span class="sxs-lookup"><span data-stu-id="bf7cd-156">Windows</span></span>
      - <span data-ttu-id="bf7cd-157">Mac</span><span class="sxs-lookup"><span data-stu-id="bf7cd-157">Mac</span></span>
      - <span data-ttu-id="bf7cd-158">Office</span><span class="sxs-lookup"><span data-stu-id="bf7cd-158">Office</span></span>
        
        
    - <span data-ttu-id="bf7cd-159">Acquisizioni a partire da **AppSource**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="bf7cd-160">Componenti aggiuntivi all'interno di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf7cd-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="bf7cd-161">Un utente che tenta di accedere all'archivio visualizza il messaggio seguente: Spiacenti, Microsoft 365 è stato configurato per impedire l'acquisizione di singoli componenti aggiuntivi Office **Store.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="bf7cd-162">Il supporto per la disattivazione Office Store è disponibile nelle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf7cd-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="bf7cd-163">Windows: 16.0.9001 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="bf7cd-164">Mac: 16.10.18011401 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="bf7cd-165">iOS: 2.9.18010804 - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="bf7cd-166">Web - Attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-166">The web - Currently available.</span></span>
    
<span data-ttu-id="bf7cd-167">Ciò non impedisce a un amministratore di usare la distribuzione centralizzata per assegnare un componente aggiuntivo dal Office Store.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="bf7cd-168">Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso in modo che utilizzi solo l'account dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="bf7cd-169">Per ulteriori informazioni, vedere [Identity, authentication, and authorization in Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="bf7cd-170">Impedire agli utenti di accedere all'Office Store impedirà anche loro di eseguire il sideload Office componenti aggiuntivi per il test da [una condivisione di rete.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="bf7cd-171">Altre informazioni sull'esperienza dell'utente finale con i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="bf7cd-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="bf7cd-172">Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a usarlo nelle applicazioni Office (vedere Iniziare a usare il [Office componente aggiuntivo](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="bf7cd-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="bf7cd-173">Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="bf7cd-p109">Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office barra multifunzione con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="bf7cd-177">Se il componente aggiuntivo distribuito non supporta i comandi dei componenti aggiuntivi o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite I **miei componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="bf7cd-178">In Word 2016, Excel 2016 o PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="bf7cd-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="bf7cd-179">Selezionare **Inserisci \> componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="bf7cd-180">Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="bf7cd-181">Fare doppio clic sul componente aggiuntivo distribuito in precedenza (in questo esempio **Citations**).</span><span class="sxs-lookup"><span data-stu-id="bf7cd-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Scheda Gestito dall'amministratore della Office componenti aggiuntivi](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="bf7cd-183">In Outlook</span><span class="sxs-lookup"><span data-stu-id="bf7cd-183">In Outlook</span></span>

1. <span data-ttu-id="bf7cd-184">Sulla barra **multifunzione Home** selezionare Ottieni **componenti aggiuntivi.**</span><span class="sxs-lookup"><span data-stu-id="bf7cd-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Pulsante Store in Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="bf7cd-186">Selezionare **Gestiti dall'amministratore** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="bf7cd-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="bf7cd-187">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="bf7cd-187">Related content</span></span>

<span data-ttu-id="bf7cd-188">[Distribuire componenti aggiuntivi nell'interfaccia di amministrazione](./manage-deployment-of-add-ins.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="bf7cd-189">Ulteriori informazioni sulla creazione e la [Office componenti aggiuntivi](/office/dev/add-ins/overview/office-add-ins) (articolo)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="bf7cd-190">[Utilizzare i cmdlet di PowerShell per](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) la distribuzione centralizzata per gestire i componenti aggiuntivi (articolo)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="bf7cd-191">[Risoluzione dei problemi: l'utente non vede i componenti aggiuntivi](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (articolo)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="bf7cd-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span><span class="sxs-lookup"><span data-stu-id="bf7cd-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>