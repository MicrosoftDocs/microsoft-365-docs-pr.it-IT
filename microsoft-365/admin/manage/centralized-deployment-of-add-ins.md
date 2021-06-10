---
title: Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione
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
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determinare se il tenant e gli utenti soddisfano i requisiti, in modo da poter utilizzare la distribuzione centralizzata per distribuire Office componenti aggiuntivi.
ms.openlocfilehash: 63775ed6bab2d595ae87085e1607be5818b355e2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782488"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="e15aa-103">Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e15aa-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="e15aa-104">La distribuzione centralizzata è il modo consigliato e più ricco di funzionalità per la maggior parte dei clienti per distribuire Office componenti aggiuntivi a utenti e gruppi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e15aa-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="e15aa-105">Se sei un amministratore, usa queste indicazioni per determinare se l'organizzazione e gli utenti soddisfano i requisiti in modo da poter usare la distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="e15aa-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="e15aa-106">La distribuzione centralizzata offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e15aa-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="e15aa-107">Un amministratore globale può assegnare un componente aggiuntivo direttamente a un utente, a più utenti tramite un gruppo o a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e15aa-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="e15aa-108">All'avvio dell Office appalto pertinente, il componente aggiuntivo viene scaricato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e15aa-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="e15aa-109">Se il componente aggiuntivo supporta i comandi del componente aggiuntivo, il componente aggiuntivo verrà visualizzato automaticamente nella barra multifunzione all'interno dell Office applizione.</span><span class="sxs-lookup"><span data-stu-id="e15aa-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="e15aa-110">I componenti aggiuntivi non vengono più visualizzati per gli utenti se l'amministratore disattiva o elimina il componente aggiuntivo o se l'utente viene rimosso da Azure Active Directory o da un gruppo a cui è assegnato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e15aa-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="e15aa-111">La distribuzione centralizzata supporta tre piattaforme desktop Windows, Mac e Online Office app.</span><span class="sxs-lookup"><span data-stu-id="e15aa-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="e15aa-112">La distribuzione centralizzata supporta anche iOS e Android (Outlook solo componenti aggiuntivi per dispositivi mobili).</span><span class="sxs-lookup"><span data-stu-id="e15aa-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="e15aa-113">La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="e15aa-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e15aa-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e15aa-114">Before you begin</span></span>

<span data-ttu-id="e15aa-115">La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino SKU Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium (e hanno eseguito l'accesso a Office usando l'ID dell'organizzazione) e disporre di cassette postali Exchange Online e Exchange Online attive.</span><span class="sxs-lookup"><span data-stu-id="e15aa-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="e15aa-116">La directory di sottoscrizione deve essere in o federata per Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e15aa-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="e15aa-117">È possibile visualizzare i requisiti specifici per Office e Exchange di seguito oppure usare Verifica compatibilità [distribuzione centralizzata.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="e15aa-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="e15aa-118">La distribuzione centralizzata non supporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e15aa-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="e15aa-119">Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="e15aa-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="e15aa-120">Servizio di directory locale</span><span class="sxs-lookup"><span data-stu-id="e15aa-120">An on-premises directory service</span></span>
- <span data-ttu-id="e15aa-121">Distribuzione di componenti aggiuntivi in una Exchange locale</span><span class="sxs-lookup"><span data-stu-id="e15aa-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="e15aa-122">Distribuzione di componenti aggiuntivi in SharePoint</span><span class="sxs-lookup"><span data-stu-id="e15aa-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="e15aa-123">Teams app</span><span class="sxs-lookup"><span data-stu-id="e15aa-123">Teams apps</span></span>
- <span data-ttu-id="e15aa-124">Distribuzione di componenti aggiuntivi COM (Component Object Model) o Visual Studio Tools per Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="e15aa-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="e15aa-125">Distribuzioni di Microsoft 365 che non includono Exchange Online ad esempio SKU: Microsoft 365 Apps for Business e Microsoft 365 Apps per Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e15aa-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="e15aa-126">Office Requisiti</span><span class="sxs-lookup"><span data-stu-id="e15aa-126">Office Requirements</span></span>

- <span data-ttu-id="e15aa-127">Per Word, Excel e PowerPoint componenti aggiuntivi, gli utenti devono utilizzare uno dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e15aa-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="e15aa-128">In un dispositivo Windows versione 1704 o successiva delle SKU di Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e15aa-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="e15aa-129">In un Mac, versione 15.34 o successiva.</span><span class="sxs-lookup"><span data-stu-id="e15aa-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="e15aa-130">Per Outlook, gli utenti devono utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e15aa-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="e15aa-131">Versione 1701 o successiva delle SKU Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e15aa-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="e15aa-132">Versione 1808 o successiva di Office Professional Plus 2019 o Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="e15aa-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="e15aa-133">Versione 16.0.4494.1000 o successiva di Office Professional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="e15aa-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="e15aa-134">Versione 15.0.4937.1000 o successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="e15aa-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="e15aa-135">Versione 16.0.9318.1000 o successiva di Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e15aa-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="e15aa-136">Versione 2.75.0 o successiva di Outlook mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="e15aa-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="e15aa-137">Versione 2.2.145 o successiva di Outlook mobile per Android</span><span class="sxs-lookup"><span data-stu-id="e15aa-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="e15aa-138">\*Le versioni MSI Outlook i componenti aggiuntivi installati dall'amministratore nella barra multifunzione Outlook appropriata, non nella sezione "Componenti aggiuntivi".</span><span class="sxs-lookup"><span data-stu-id="e15aa-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="e15aa-139">Exchange Online requisiti</span><span class="sxs-lookup"><span data-stu-id="e15aa-139">Exchange Online requirements</span></span>

<span data-ttu-id="e15aa-140">Microsoft Exchange i manifesti dei componenti aggiuntivi all'interno del tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e15aa-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="e15aa-141">L'amministratore che distribuisce i componenti aggiuntivi e gli utenti che ricevono tali componenti aggiuntivi devono essere in una versione di Exchange Online che supporti l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="e15aa-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="e15aa-p106">Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per ogni utente può essere verificata usando il cmdlet di PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity).</span><span class="sxs-lookup"><span data-stu-id="e15aa-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="e15aa-144">Verifica compatibilità distribuzione centralizzata</span><span class="sxs-lookup"><span data-stu-id="e15aa-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="e15aa-145">Utilizzando Verifica compatibilità distribuzione centralizzata, è possibile verificare se gli utenti del tenant sono impostati per l'utilizzo della distribuzione centralizzata per Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e15aa-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="e15aa-146">Verifica compatibilità non è necessario per il supporto di Outlook.</span><span class="sxs-lookup"><span data-stu-id="e15aa-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="e15aa-147">Scarica verifica [compatibilità](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="e15aa-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="e15aa-148">Eseguire Verifica compatibilità</span><span class="sxs-lookup"><span data-stu-id="e15aa-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="e15aa-149">Avviare una finestra PowerShell.exe elevata.</span><span class="sxs-lookup"><span data-stu-id="e15aa-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="e15aa-150">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e15aa-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="e15aa-151">Eseguire il **comando Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="e15aa-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="e15aa-152">Questo comando richiede di specificare  *_TenantDomain,_* ad esempio *TailspinToysIncorporated.onmicrosoft. </span> com*)  *_e Le credenziali TenantAdmin_* (usare le credenziali di amministratore globale) e quindi richiede il consenso.</span><span class="sxs-lookup"><span data-stu-id="e15aa-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="e15aa-153">A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="e15aa-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="e15aa-154">Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola).</span><span class="sxs-lookup"><span data-stu-id="e15aa-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="e15aa-155">Il file viene salvato in **C:\windows\system32** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e15aa-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="e15aa-156">Il file di output contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e15aa-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="e15aa-157">Nome utente</span><span class="sxs-lookup"><span data-stu-id="e15aa-157">User Name</span></span>
    
- <span data-ttu-id="e15aa-158">ID utente (indirizzo di posta elettronica dell'utente)</span><span class="sxs-lookup"><span data-stu-id="e15aa-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="e15aa-159">Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri</span><span class="sxs-lookup"><span data-stu-id="e15aa-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="e15aa-160">Office piano - Piano di Office per cui sono concessi in licenza</span><span class="sxs-lookup"><span data-stu-id="e15aa-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="e15aa-161">Office attivato: se Office è stato attivato</span><span class="sxs-lookup"><span data-stu-id="e15aa-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="e15aa-162">Cassetta postale supportata: se la cassetta postale è abilitata per OAuth</span><span class="sxs-lookup"><span data-stu-id="e15aa-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="e15aa-163">L'autenticazione a più fattori non è supportata quando si utilizza il modulo PowerShell per la distribuzione centrale.</span><span class="sxs-lookup"><span data-stu-id="e15aa-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="e15aa-164">Il modulo funziona solo con l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e15aa-164">The module only works with Basic authentication.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="e15aa-165">Assegnazioni di utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="e15aa-165">User and group assignments</span></span>

<span data-ttu-id="e15aa-166">La funzionalità distribuzione centralizzata attualmente supporta la maggior parte dei gruppi supportati da Azure Active Directory, inclusi Microsoft 365, liste di distribuzione e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e15aa-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e15aa-167">I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="e15aa-167">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="e15aa-168">La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e a tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="e15aa-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="e15aa-169">La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.</span><span class="sxs-lookup"><span data-stu-id="e15aa-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="e15aa-p111">Esaminare l'esempio seguente, in cui Valeria, Pupetta e il gruppo Reparto vendite vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e15aa-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="e15aa-173">Scoprire se un gruppo contiene gruppi annidati</span><span class="sxs-lookup"><span data-stu-id="e15aa-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="e15aa-174">Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e15aa-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="e15aa-175">Se si immette il nome del gruppo nel campo **A** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi annidati.</span><span class="sxs-lookup"><span data-stu-id="e15aa-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="e15aa-176">Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi.</span><span class="sxs-lookup"><span data-stu-id="e15aa-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Scheda Membri della Outlook contatto](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="e15aa-p113">È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente nella scheda **Appartenenza** della scheda contatto di Outlook si vede che il sottogruppo 1 è un membro del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="e15aa-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Scheda Appartenenza della scheda Outlook contatto](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="e15aa-p114">In alternativa, è possibile usare l'API di Azure Active Directory Graph per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per altre informazioni, vedere [Operazioni su gruppi | Riferimento API Graph](/previous-versions/azure/ad/graph/api/groups-operations).</span><span class="sxs-lookup"><span data-stu-id="e15aa-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="e15aa-183">Contattare Microsoft per assistenza</span><span class="sxs-lookup"><span data-stu-id="e15aa-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="e15aa-184">Se l'utente o gli utenti riscontrano problemi durante il caricamento del componente aggiuntivo durante l'utilizzo di app Office per il Web (Word, Excel e così via), distribuite centralmente, potrebbe essere necessario contattare il supporto Tecnico Microsoft ([informazioni](../../business-video/get-help-support.md)su come ).</span><span class="sxs-lookup"><span data-stu-id="e15aa-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="e15aa-185">Fornire le informazioni seguenti sull'ambiente Microsoft 365 nel ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="e15aa-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="e15aa-186">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="e15aa-186">**Platform**</span></span>|<span data-ttu-id="e15aa-187">**Informazioni di debug**</span><span class="sxs-lookup"><span data-stu-id="e15aa-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e15aa-188">Office</span><span class="sxs-lookup"><span data-stu-id="e15aa-188">Office</span></span>  <br/> | <span data-ttu-id="e15aa-189">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="e15aa-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="e15aa-190">ID tenant ( [informazioni](/onedrive/find-your-office-365-tenant-id))</span><span class="sxs-lookup"><span data-stu-id="e15aa-190">Tenant ID ( [learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="e15aa-191">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="e15aa-191">CorrelationID.</span></span> <span data-ttu-id="e15aa-192">Visualizzare l'origine di una delle pagine di Office e cercare il valore id correlazione e inviarlo al supporto:</span><span class="sxs-lookup"><span data-stu-id="e15aa-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="e15aa-193">Rich client (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="e15aa-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="e15aa-194">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="e15aa-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="e15aa-195">Numeri di build dell'app client (preferibilmente come screenshot da **File/Account)**</span><span class="sxs-lookup"><span data-stu-id="e15aa-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="e15aa-196">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="e15aa-196">Related content</span></span>

<span data-ttu-id="e15aa-197">[Distribuire componenti aggiuntivi nell'interfaccia di amministrazione](../manage/manage-deployment-of-add-ins.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e15aa-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="e15aa-198">[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e15aa-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="e15aa-199">[Domande frequenti sulla distribuzione centralizzata](../manage/centralized-deployment-faq.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="e15aa-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="e15aa-200">[Aggiornare il Microsoft 365 per gli utenti aziendali al client Office](../setup/upgrade-users-to-latest-office-client.md) più recente (articolo)</span><span class="sxs-lookup"><span data-stu-id="e15aa-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 