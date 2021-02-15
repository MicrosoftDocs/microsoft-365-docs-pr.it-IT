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
description: Determinare se il tenant e gli utenti soddisfano i requisiti, in modo da poter utilizzare la distribuzione centralizzata per distribuire i componenti aggiuntivi di Office.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519366"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="05a3f-103">Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="05a3f-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="05a3f-104">La distribuzione centralizzata è il modo consigliato e più ricco di funzionalità per la maggior parte dei clienti di distribuire componenti aggiuntivi di Office a utenti e gruppi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05a3f-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="05a3f-105">Gli amministratori possono usare queste indicazioni per determinare se l'organizzazione e gli utenti soddisfano i requisiti in modo da poter usare la distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="05a3f-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="05a3f-106">La distribuzione centralizzata offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a3f-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="05a3f-107">Un amministratore globale può assegnare un componente aggiuntivo direttamente a un utente, a più utenti tramite un gruppo o a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05a3f-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="05a3f-108">All'avvio dell'applicazione di Office pertinente, il componente aggiuntivo viene scaricato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="05a3f-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="05a3f-109">Se il componente aggiuntivo supporta i comandi del componente aggiuntivo, il componente aggiuntivo verrà visualizzato automaticamente nella barra multifunzione all'interno dell'applicazione di Office.</span><span class="sxs-lookup"><span data-stu-id="05a3f-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="05a3f-110">I componenti aggiuntivi non vengono più visualizzati per gli utenti se l'amministratore disattiva o elimina il componente aggiuntivo oppure se l'utente viene rimosso da Azure Active Directory o da un gruppo a cui è assegnato il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="05a3f-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="05a3f-111">La distribuzione centralizzata supporta tre piattaforme desktop windows, Mac e app di Office online.</span><span class="sxs-lookup"><span data-stu-id="05a3f-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="05a3f-112">La distribuzione centralizzata supporta anche iOS e Android (solo componenti aggiuntivi per Outlook Mobile).</span><span class="sxs-lookup"><span data-stu-id="05a3f-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="05a3f-113">La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="05a3f-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="05a3f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05a3f-114">Requirements</span></span>

<span data-ttu-id="05a3f-115">La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino SKU Di Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium (e hanno effettuato l'accesso a Office con il proprio ID organizzazione) e che le cassette postali di Exchange Online e Di Exchange Online siano attive.</span><span class="sxs-lookup"><span data-stu-id="05a3f-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="05a3f-116">La directory di sottoscrizione deve essere in o federata in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05a3f-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="05a3f-117">È possibile visualizzare i requisiti specifici per Office ed Exchange di seguito oppure utilizzare Verifica compatibilità [distribuzione centralizzata.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="05a3f-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="05a3f-118">La distribuzione centralizzata non supporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="05a3f-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="05a3f-119">Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="05a3f-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="05a3f-120">Servizio di directory locale</span><span class="sxs-lookup"><span data-stu-id="05a3f-120">An on-premises directory service</span></span>
- <span data-ttu-id="05a3f-121">Distribuzione di componenti aggiuntivi in una cassetta postale locale di Exchange</span><span class="sxs-lookup"><span data-stu-id="05a3f-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="05a3f-122">Distribuzione di componenti aggiuntivi in SharePoint</span><span class="sxs-lookup"><span data-stu-id="05a3f-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="05a3f-123">App di Teams</span><span class="sxs-lookup"><span data-stu-id="05a3f-123">Teams apps</span></span>
- <span data-ttu-id="05a3f-124">Distribuzione di componenti aggiuntivi COM (Component Object Model) o Visual Studio Tools for Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="05a3f-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="05a3f-125">Distribuzioni di Microsoft 365 che non includono Exchange Online, ad esempio SKU: Microsoft 365 Apps for Business e Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="05a3f-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="05a3f-126">Requisiti di Office</span><span class="sxs-lookup"><span data-stu-id="05a3f-126">Office Requirements</span></span>

- <span data-ttu-id="05a3f-127">Per i componenti aggiuntivi di Word, Excel e PowerPoint, gli utenti devono utilizzare uno dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a3f-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="05a3f-128">In un dispositivo Windows, versione 1704 o successiva delle SKU di Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="05a3f-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="05a3f-129">In un Mac, versione 15.34 o successiva.</span><span class="sxs-lookup"><span data-stu-id="05a3f-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="05a3f-130">Per Outlook, gli utenti devono utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a3f-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="05a3f-131">Versione 1701 o successiva delle SKU di Microsoft 365 Enterprise: E3/E5/F3 o SKU aziendali: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="05a3f-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="05a3f-132">Versione 1808 o successiva di Office Professional Plus 2019 o Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="05a3f-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="05a3f-133">Versione 16.0.4494.1000 o successiva di Office Professional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="05a3f-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="05a3f-134">Versione 15.0.4937.1000 o successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="05a3f-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="05a3f-135">Versione 16.0.9318.1000 o successiva di Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="05a3f-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="05a3f-136">Versione 2.75.0 o successiva di Outlook Mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="05a3f-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="05a3f-137">Versione 2.2.145 o successiva di Outlook Mobile per Android</span><span class="sxs-lookup"><span data-stu-id="05a3f-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="05a3f-138">\*Le versioni MSI di Outlook mostrano i componenti aggiuntivi installati dall'amministratore nella barra multifunzione di Outlook appropriata, non nella sezione "Componenti aggiuntivi".</span><span class="sxs-lookup"><span data-stu-id="05a3f-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="05a3f-139">Requisiti di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05a3f-139">Exchange Online requirements</span></span>

<span data-ttu-id="05a3f-140">Microsoft Exchange archivia i manifesti dei componenti aggiuntivi all'interno del tenant dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05a3f-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="05a3f-141">L'amministratore che distribuisce i componenti aggiuntivi e gli utenti che ricevono tali componenti aggiuntivi devono essere in una versione di Exchange Online che supporta l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="05a3f-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="05a3f-p106">Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per ogni utente può essere verificata usando il cmdlet di PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="05a3f-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="05a3f-144">Verifica compatibilità distribuzione centralizzata</span><span class="sxs-lookup"><span data-stu-id="05a3f-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="05a3f-145">Con Verifica compatibilità distribuzione centralizzata è possibile verificare se gli utenti del tenant sono impostati per l'utilizzo della distribuzione centralizzata per Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="05a3f-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="05a3f-146">Verifica compatibilità non è necessario per il supporto di Outlook.</span><span class="sxs-lookup"><span data-stu-id="05a3f-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="05a3f-147">Scaricare Verifica compatibilità [qui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="05a3f-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="05a3f-148">Eseguire Verifica compatibilità</span><span class="sxs-lookup"><span data-stu-id="05a3f-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="05a3f-149">Avvia una finestra di PowerShell.exe con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="05a3f-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="05a3f-150">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="05a3f-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="05a3f-151">Eseguire il **comando Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="05a3f-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="05a3f-152">Questo comando richiede di specificare  *_TenantDomain_* (ad esempio, *TailspinToysIncorporated.onmicrosoft. </span> com*) e  *_le credenziali TenantAdmin_* (usare le credenziali di amministratore globale) e quindi richiede il consenso.</span><span class="sxs-lookup"><span data-stu-id="05a3f-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="05a3f-153">A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="05a3f-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="05a3f-154">Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola).</span><span class="sxs-lookup"><span data-stu-id="05a3f-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="05a3f-155">Il file viene salvato in **C:\windows\system32** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="05a3f-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="05a3f-156">Il file di output contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a3f-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="05a3f-157">Nome utente</span><span class="sxs-lookup"><span data-stu-id="05a3f-157">User Name</span></span>
    
- <span data-ttu-id="05a3f-158">ID utente (indirizzo di posta elettronica dell'utente)</span><span class="sxs-lookup"><span data-stu-id="05a3f-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="05a3f-159">Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri</span><span class="sxs-lookup"><span data-stu-id="05a3f-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="05a3f-160">Piano di Office - Piano di Office per cui sono concessi in licenza</span><span class="sxs-lookup"><span data-stu-id="05a3f-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="05a3f-161">Office attivato: se Office è stato attivato</span><span class="sxs-lookup"><span data-stu-id="05a3f-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="05a3f-162">Cassetta postale supportata: se la cassetta postale è abilitata per OAuth</span><span class="sxs-lookup"><span data-stu-id="05a3f-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="05a3f-163">L'autenticazione a più fattori non è supportata quando si utilizza il modulo PowerShell per la distribuzione centrale.</span><span class="sxs-lookup"><span data-stu-id="05a3f-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="05a3f-164">Assegnazioni di utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="05a3f-164">User and group assignments</span></span>

<span data-ttu-id="05a3f-165">La funzionalità di distribuzione centralizzata attualmente supporta la maggior parte dei gruppi supportati da Azure Active Directory, inclusi i gruppi di Microsoft 365, le liste di distribuzione e i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="05a3f-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05a3f-166">I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="05a3f-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="05a3f-167">La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e tutti gli utenti del tenant.</span><span class="sxs-lookup"><span data-stu-id="05a3f-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="05a3f-168">La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.</span><span class="sxs-lookup"><span data-stu-id="05a3f-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="05a3f-p110">Esaminare l'esempio seguente, in cui Valeria, Pupetta e il gruppo Reparto vendite vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="05a3f-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="05a3f-172">Scoprire se un gruppo contiene gruppi annidati</span><span class="sxs-lookup"><span data-stu-id="05a3f-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="05a3f-173">Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="05a3f-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="05a3f-174">Se si immette il nome del gruppo nel campo **A** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi annidati.</span><span class="sxs-lookup"><span data-stu-id="05a3f-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="05a3f-175">Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi.</span><span class="sxs-lookup"><span data-stu-id="05a3f-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Scheda Membri della scheda contatto di Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="05a3f-p112">È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente nella scheda **Appartenenza** della scheda contatto di Outlook si vede che il sottogruppo 1 è un membro del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="05a3f-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Scheda Appartenenza della scheda contatto di Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="05a3f-p113">In alternativa, è possibile usare l'API di Azure Active Directory Graph per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per altre informazioni, vedere [Operazioni su gruppi | Riferimento API Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="05a3f-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="05a3f-182">Contattare Microsoft per assistenza</span><span class="sxs-lookup"><span data-stu-id="05a3f-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="05a3f-183">Se si verificano problemi durante il caricamento del componente aggiuntivo durante l'uso delle app di Office per il Web (Word, Excel e così via), distribuite centralmente, potrebbe essere necessario contattare il supporto tecnico Microsoft[(](../contact-support-for-business-products.md)informazioni su come ).</span><span class="sxs-lookup"><span data-stu-id="05a3f-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="05a3f-184">Fornire le informazioni seguenti sull'ambiente Microsoft 365 nel ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="05a3f-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="05a3f-185">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="05a3f-185">**Platform**</span></span>|<span data-ttu-id="05a3f-186">**Informazioni di debug**</span><span class="sxs-lookup"><span data-stu-id="05a3f-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="05a3f-187">Ufficio</span><span class="sxs-lookup"><span data-stu-id="05a3f-187">Office</span></span>  <br/> | <span data-ttu-id="05a3f-188">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="05a3f-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="05a3f-189">ID tenant ( [informazioni](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="05a3f-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="05a3f-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="05a3f-190">CorrelationID.</span></span> <span data-ttu-id="05a3f-191">Visualizzare l'origine di una delle pagine di Office e cercare il valore dell'ID correlazione e inviarlo al supporto:</span><span class="sxs-lookup"><span data-stu-id="05a3f-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="05a3f-192">Rich client (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="05a3f-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="05a3f-193">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="05a3f-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="05a3f-194">Numeri di build dell'app client (preferibilmente come screenshot da **File/Account)**</span><span class="sxs-lookup"><span data-stu-id="05a3f-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
