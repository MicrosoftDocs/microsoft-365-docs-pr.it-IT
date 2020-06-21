---
title: Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determinare se il tenant e gli utenti soddisfano i requisiti, in modo che sia possibile utilizzare la distribuzione centralizzata per distribuire i componenti aggiuntivi di Office.
ms.openlocfilehash: 4b9ca7213f36440114d39ef491fe934f13ca96ea
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717274"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="609cb-103">Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="609cb-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="609cb-104">La distribuzione centralizzata è il metodo consigliato e più ricco di funzionalità per la maggior parte dei clienti per distribuire i componenti aggiuntivi di Office agli utenti e ai gruppi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="609cb-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="609cb-105">Se si è un amministratore, utilizzare queste linee guida per determinare se il tenant e gli utenti soddisfano i requisiti affinché sia possibile utilizzare la distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="609cb-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="609cb-106">La distribuzione centralizzata supporta tre piattaforme desktop Windows, Mac e le app di Office Online.</span><span class="sxs-lookup"><span data-stu-id="609cb-106">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="609cb-107">La distribuzione centralizzata supporta anche iOS e Android (solo componenti aggiuntivi di Outlook Mobile).</span><span class="sxs-lookup"><span data-stu-id="609cb-107">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>
<span data-ttu-id="609cb-108">È possibile richiedere fino a 24 ore affinché un componente aggiuntivo venga visualizzato per il client per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="609cb-108">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="609cb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="609cb-109">Requirements</span></span>

<span data-ttu-id="609cb-110">La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Microsoft 365 Apps for Enterprise (e che siano firmati in Office utilizzando l'ID dell'organizzazione) e dispongano di cassette postali di Exchange Online e Active Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="609cb-110">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="609cb-111">È necessario che la directory di sottoscrizione sia in o federata in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="609cb-111">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="609cb-112">È possibile visualizzare i requisiti specifici per Office ed Exchange di seguito oppure utilizzare la [Verifica compatibilità della distribuzione centralizzata](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="609cb-112">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="609cb-113">La distribuzione centralizzata non supporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="609cb-113">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="609cb-114">Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="609cb-114">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="609cb-115">Servizio di directory locale</span><span class="sxs-lookup"><span data-stu-id="609cb-115">An on-premises directory service</span></span>
    
- <span data-ttu-id="609cb-116">Distribuzione di componenti aggiuntivi in SharePoint</span><span class="sxs-lookup"><span data-stu-id="609cb-116">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="609cb-117">App Teams</span><span class="sxs-lookup"><span data-stu-id="609cb-117">Teams apps</span></span>
   
- <span data-ttu-id="609cb-118">Distribuzione dei componenti aggiuntivi Component Object Model (COM) o Visual Studio Tools per Office (VSTO)</span><span class="sxs-lookup"><span data-stu-id="609cb-118">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="609cb-119">Distribuzioni di Microsoft 365 che non includono Exchange, ad esempio Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="609cb-119">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="609cb-120">Requisiti di Office</span><span class="sxs-lookup"><span data-stu-id="609cb-120">Office Requirements</span></span>

- <span data-ttu-id="609cb-121">Per i componenti aggiuntivi di Word, Excel e PowerPoint, è necessario che gli utenti utilizzino uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="609cb-121">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="609cb-122">Su un dispositivo Windows, versione 1704 o successiva di Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="609cb-122">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="609cb-123">Su un Mac, versione 15,34 o successiva.</span><span class="sxs-lookup"><span data-stu-id="609cb-123">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="609cb-124">Per Outlook, è necessario che gli utenti utilizzino una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="609cb-124">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="609cb-125">Versione 1701 o successiva di Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="609cb-125">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="609cb-126">Versione 1808 o successiva di Office Professional Plus 2019 o Office standard 2019.</span><span class="sxs-lookup"><span data-stu-id="609cb-126">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="609cb-127">Version 16.0.4494.1000 o versione successiva di Office Professional Plus 2016 (MSI) o Office standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="609cb-127">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="609cb-128">Version 15.0.4937.1000 o versione successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="609cb-128">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="609cb-129">Version 16.0.9318.1000 o versione successiva di Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="609cb-129">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="609cb-130">Version 2.75.0 o versione successiva di Outlook Mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="609cb-130">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="609cb-131">Version 2.2.145 o versione successiva di Outlook Mobile per Android</span><span class="sxs-lookup"><span data-stu-id="609cb-131">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="609cb-132">\* Le versioni MSI di Outlook visualizzano i componenti aggiuntivi installati dall'amministratore nella barra multifunzione di Outlook appropriata e non nella sezione "componenti aggiuntivi".</span><span class="sxs-lookup"><span data-stu-id="609cb-132">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="609cb-133">Scoprire se Microsoft 365 Apps for Enterprise è installato</span><span class="sxs-lookup"><span data-stu-id="609cb-133">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="609cb-134">Per utilizzare Microsoft 365 Apps for Enterprise, un utente deve disporre di un account Microsoft 365 e deve disporre di una licenza.</span><span class="sxs-lookup"><span data-stu-id="609cb-134">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="609cb-135">Per ulteriori informazioni, vedere [Overview of Microsoft 365 Apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="609cb-135">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="609cb-136">Il modo più semplice per rilevare se un utente ha installato Microsoft 365 Apps for Enterprise e lo ha utilizzato di recente consiste nell'utilizzare il rapporto attivazioni di Microsoft Office, disponibile nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="609cb-136">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="609cb-137">Il rapporto fornisce un elenco di tutti gli utenti che hanno attivato Microsoft 365 Apps for Enterprise negli ultimi 7 giorni, 30 giorni, 90 o 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="609cb-137">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="609cb-138">Ai fini della distribuzione centralizzata, le attivazioni desktop per Windows o Mac rappresentano le colonne più importanti del report.</span><span class="sxs-lookup"><span data-stu-id="609cb-138">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="609cb-139">È possibile esportare il report in Excel.</span><span class="sxs-lookup"><span data-stu-id="609cb-139">You can export the report to Excel.</span></span> <span data-ttu-id="609cb-140">Per ulteriori informazioni sul report, vedere [rapporti microsoft 365 nell'interfaccia di amministrazione-attivazioni di Microsoft Office](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="609cb-140">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="609cb-141">Se non si desidera utilizzare il rapporto attivazioni, è possibile chiedere a un utente di aprire un'applicazione di Office come Word nel computer in uso e quindi scegliere **File** \> **account**file.</span><span class="sxs-lookup"><span data-stu-id="609cb-141">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="609cb-142">In **informazioni sui prodotti**, dovrebbe essere visualizzato il **prodotto di sottoscrizione** e **Microsoft 365 per Enterprise**, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="609cb-142">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Informazioni sul prodotto in un'applicazione di Office](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="609cb-144">Per informazioni su Microsoft 365 Apps for Enterprise, vedere [Troubleshooting Tips for microsoft 365 Apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="609cb-144">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="609cb-145">Requisiti di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="609cb-145">Exchange Online requirements</span></span>

<span data-ttu-id="609cb-146">Microsoft Exchange archivia i manifesti del componente aggiuntivo all'interno del tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="609cb-146">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="609cb-147">Gli amministratori che distribuiscono i componenti aggiuntivi e gli utenti che ricevono i componenti aggiuntivi devono trovarsi in una versione di Exchange Online che supporta l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="609cb-147">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="609cb-148">Check with your organization's Exchange admin to find out which configuration is in use.</span><span class="sxs-lookup"><span data-stu-id="609cb-148">Check with your organization's Exchange admin to find out which configuration is in use.</span></span> <span data-ttu-id="609cb-149">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="609cb-149">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="609cb-150">Verifica compatibilità della distribuzione centralizzata</span><span class="sxs-lookup"><span data-stu-id="609cb-150">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="609cb-151">Tramite Verifica compatibilità della distribuzione centralizzata, è possibile verificare se gli utenti del tenant sono configurati per l'utilizzo della distribuzione centralizzata per Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="609cb-151">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="609cb-152">Verifica compatibilità non è necessario per il supporto di Outlook.</span><span class="sxs-lookup"><span data-stu-id="609cb-152">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="609cb-153">Scaricare Verifica compatibilità [qui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="609cb-153">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="609cb-154">Esecuzione di verifica compatibilità</span><span class="sxs-lookup"><span data-stu-id="609cb-154">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="609cb-155">Avviare una finestra di PowerShell.exe con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="609cb-155">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="609cb-156">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="609cb-156">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="609cb-157">Eseguire il comando **Invoke-CompatabilityCheck** :</span><span class="sxs-lookup"><span data-stu-id="609cb-157">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="609cb-158">in cui viene richiesto di *_TenantDomain_* (ad esempio, *TailspinToysIncorporated. onmicrosoft. </span> com*) e le credenziali di *_TenantAdmin_* (utilizzare le credenziali di amministratore globale) e quindi richiede il consenso.</span><span class="sxs-lookup"><span data-stu-id="609cb-158">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="609cb-159">A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="609cb-159">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="609cb-160">Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola).</span><span class="sxs-lookup"><span data-stu-id="609cb-160">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="609cb-161">Il file viene salvato in **C:\Windows\System32** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="609cb-161">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="609cb-162">Il file di output contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="609cb-162">The output file contains the following information:</span></span>
  
- <span data-ttu-id="609cb-163">Nome utente</span><span class="sxs-lookup"><span data-stu-id="609cb-163">User Name</span></span>
    
- <span data-ttu-id="609cb-164">ID utente (indirizzo di posta elettronica dell'utente)</span><span class="sxs-lookup"><span data-stu-id="609cb-164">User ID (User's email address)</span></span>
    
- <span data-ttu-id="609cb-165">Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri</span><span class="sxs-lookup"><span data-stu-id="609cb-165">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="609cb-166">Piano di Office: il piano di Office in cui sono concessi in licenza</span><span class="sxs-lookup"><span data-stu-id="609cb-166">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="609cb-167">Office attivato: se Office è stato attivato</span><span class="sxs-lookup"><span data-stu-id="609cb-167">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="609cb-168">Cassetta postale supportata: se la cassetta postale è abilitata per OAuth</span><span class="sxs-lookup"><span data-stu-id="609cb-168">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="609cb-169">Assegnazioni di utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="609cb-169">User and group assignments</span></span>

<span data-ttu-id="609cb-170">La funzionalità di distribuzione centralizzata supporta attualmente la maggior parte dei gruppi supportati da Azure Active Directory, inclusi i gruppi di Microsoft 365, le liste di distribuzione e i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="609cb-170">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="609cb-171">I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="609cb-171">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="609cb-172">La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e tutti i clienti del tenant.</span><span class="sxs-lookup"><span data-stu-id="609cb-172">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="609cb-173">La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.</span><span class="sxs-lookup"><span data-stu-id="609cb-173">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="609cb-174">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="609cb-174">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span></span> <span data-ttu-id="609cb-175">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="609cb-175">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="609cb-177">Scoprire se un gruppo contiene gruppi annidati</span><span class="sxs-lookup"><span data-stu-id="609cb-177">Find out if a group contains nested groups</span></span>

<span data-ttu-id="609cb-178">Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="609cb-178">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="609cb-179">Se si immette il nome del gruppo all'interno del campo **a** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi nidificati.</span><span class="sxs-lookup"><span data-stu-id="609cb-179">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="609cb-180">Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi.</span><span class="sxs-lookup"><span data-stu-id="609cb-180">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Scheda membri della scheda contatto di Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="609cb-182">You can do the opposite query by resolving the group to see if it's a member of any group.</span><span class="sxs-lookup"><span data-stu-id="609cb-182">You can do the opposite query by resolving the group to see if it's a member of any group.</span></span> <span data-ttu-id="609cb-183">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="609cb-183">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Scheda appartenenza della scheda contatto di Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="609cb-185">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span><span class="sxs-lookup"><span data-stu-id="609cb-185">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span></span> <span data-ttu-id="609cb-186">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="609cb-186">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="609cb-187">Contattare Microsoft per assistenza</span><span class="sxs-lookup"><span data-stu-id="609cb-187">Contacting Microsoft for support</span></span>

<span data-ttu-id="609cb-188">Se l'utente o gli utenti riscontrano problemi durante il caricamento del componente aggiuntivo utilizzando le app di Office per il Web (Word, Excel e così via), che sono state distribuite in modo centralizzato, potrebbe essere necessario contattare il supporto tecnico Microsoft ([informazioni su come](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="609cb-188">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="609cb-189">Fornire le seguenti informazioni sull'ambiente Microsoft 365 nel ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="609cb-189">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="609cb-190">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="609cb-190">**Platform**</span></span>|<span data-ttu-id="609cb-191">**Informazioni di debug**</span><span class="sxs-lookup"><span data-stu-id="609cb-191">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="609cb-192">Ufficio</span><span class="sxs-lookup"><span data-stu-id="609cb-192">Office</span></span>  <br/> | <span data-ttu-id="609cb-193">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="609cb-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="609cb-194">ID tenant ( [informazioni](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="609cb-194">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="609cb-195">CorrelationId.</span><span class="sxs-lookup"><span data-stu-id="609cb-195">CorrelationID.</span></span> <span data-ttu-id="609cb-196">Visualizzare l'origine di una delle pagine di Office e cercare il valore dell'ID correlazione e inviarlo al supporto:</span><span class="sxs-lookup"><span data-stu-id="609cb-196">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="609cb-197">Rich client (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="609cb-197">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="609cb-198">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="609cb-198">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="609cb-199">Creare numeri dell'app client (preferibilmente come schermata da **file/account**)</span><span class="sxs-lookup"><span data-stu-id="609cb-199">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

