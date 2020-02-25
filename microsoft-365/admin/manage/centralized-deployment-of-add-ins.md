---
title: Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determinare se il tenant e gli utenti di Office 365 soddisfano i requisiti, in modo che sia possibile utilizzare la distribuzione centralizzata per distribuire i componenti aggiuntivi di Office.
ms.openlocfilehash: 4351658f2637b86c9b3233f55916d8e0ac0f8cfb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252890"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="f0b2f-103">Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f0b2f-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="f0b2f-104">La distribuzione centralizzata è il metodo consigliato e più ricco di funzionalità per la maggior parte dei clienti per distribuire i componenti aggiuntivi per Office agli utenti e ai gruppi all'interno dell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization.</span></span> <span data-ttu-id="f0b2f-105">Se si è un amministratore, utilizzare queste linee guida per determinare se il tenant e gli utenti soddisfano i requisiti affinché sia possibile utilizzare la distribuzione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="f0b2f-106">La distribuzione centralizzata supporta le app di Office, Windows, Mac, iOS, Android e online.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="f0b2f-107">È possibile richiedere fino a 12 ore affinché un componente aggiuntivo venga visualizzato per il client per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-107">It can take up to 12 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f0b2f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0b2f-108">Requirements</span></span>

<span data-ttu-id="f0b2f-109">La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Office 365 ProPlus (e siano firmati in Office utilizzando l'ID dell'organizzazione) e dispongano di cassette postali di Exchange Online e Active Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-109">Centralized deployment of add-ins requires that the users are using Office 365 ProPlus (and are signed into Office using their Organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="f0b2f-110">È necessario che la directory di sottoscrizione sia in o federata in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-110">Your subscription'd directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="f0b2f-111">È possibile visualizzare i requisiti specifici per Office ed Exchange di seguito oppure utilizzare la [Verifica compatibilità della distribuzione centralizzata di office 365](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-111">You can view specific requirements for Office and Exchange below, or use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="f0b2f-112">La distribuzione centralizzata non supporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="f0b2f-113">Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0b2f-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="f0b2f-114">Servizio di directory locale</span><span class="sxs-lookup"><span data-stu-id="f0b2f-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="f0b2f-115">Distribuzione di componenti aggiuntivi in SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0b2f-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="f0b2f-116">App Teams</span><span class="sxs-lookup"><span data-stu-id="f0b2f-116">Teams apps</span></span>
   
- <span data-ttu-id="f0b2f-117">Distribuzione dei componenti aggiuntivi Component Object Model (COM) o Visual Studio Tools per Office (VSTO)</span><span class="sxs-lookup"><span data-stu-id="f0b2f-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="f0b2f-118">Distribuzioni di Office 365 che non includono Exchange, come Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="f0b2f-118">Deployments of Office 365 that do not include Exchange such as Office 365 Business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="f0b2f-119">Requisiti di Office</span><span class="sxs-lookup"><span data-stu-id="f0b2f-119">Office Requirements</span></span>

- <span data-ttu-id="f0b2f-120">Per i componenti aggiuntivi di Word, Excel e PowerPoint, è necessario che gli utenti utilizzino uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="f0b2f-121">In un dispositivo Windows, versione 1704 o successiva di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-121">On a Windows device, Version 1704 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="f0b2f-122">Su un Mac, versione 15,34 o successiva.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-122">On a Mac, Version 15.34 or later.</span></span>
      - <span data-ttu-id="f0b2f-123">Su iOS (solo iPad), Version 2.9.18010804 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-123">On iOS (iPad only), Version 2.9.18010804 or later.</span></span>
- <span data-ttu-id="f0b2f-124">Per Outlook, è necessario che gli utenti utilizzino una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-124">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="f0b2f-125">Versione 1701 o successiva di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-125">Version 1701 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="f0b2f-126">Versione 1808 o successiva di Office Professional Plus 2019 o Office standard 2019.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-126">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="f0b2f-127">Version 16.0.4494.1000 o versione successiva di Office Professional Plus 2016 (MSI) o Office standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="f0b2f-127">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="f0b2f-128">Version 15.0.4937.1000 o versione successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="f0b2f-128">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="f0b2f-129">Version 16.0.9318.1000 o versione successiva di Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="f0b2f-129">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="f0b2f-130">Version 2.75.0 o versione successiva di Outlook Mobile per iOS</span><span class="sxs-lookup"><span data-stu-id="f0b2f-130">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="f0b2f-131">Version 2.2.145 o versione successiva di Outlook Mobile per Android</span><span class="sxs-lookup"><span data-stu-id="f0b2f-131">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="f0b2f-132">\* Le versioni MSI di Outlook visualizzano i componenti aggiuntivi installati dall'amministratore nella barra multifunzione di Outlook appropriata e non nella sezione "componenti aggiuntivi".</span><span class="sxs-lookup"><span data-stu-id="f0b2f-132">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a><span data-ttu-id="f0b2f-133">Scoprire se Office 365 ProPlus è installato</span><span class="sxs-lookup"><span data-stu-id="f0b2f-133">Find out if Office 365 ProPlus is installed</span></span>

<span data-ttu-id="f0b2f-134">Per utilizzare Office 365 ProPlus, un utente deve disporre di un account di Office 365 e deve disporre di una licenza.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-134">To use Office 365 ProPlus, a user must have an Office 365 account and must have been assigned a license.</span></span> <span data-ttu-id="f0b2f-135">Per altre informazioni, vedere [Panoramica di Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-135">For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="f0b2f-136">Il modo più semplice per rilevare se un utente dispone di Office 365 ProPlus installato e lo ha utilizzato di recente consiste nell'utilizzare il rapporto attivazioni di Microsoft Office, disponibile nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-136">The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f0b2f-137">Il report fornisce un elenco di tutti gli utenti che hanno attivato Office 365 ProPlus negli ultimi 7, 30, 90 o 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-137">The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="f0b2f-138">Ai fini della distribuzione centralizzata, le attivazioni desktop per Windows o Mac rappresentano le colonne più importanti del report.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-138">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="f0b2f-139">È possibile esportare il report in Excel.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-139">You can export the report to Excel.</span></span> <span data-ttu-id="f0b2f-140">Per altre informazioni sul report, vedere [Report di Office 365 nell'interfaccia di amministrazione - Attivazioni di Microsoft Office](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-140">For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="f0b2f-141">Se non si desidera utilizzare il rapporto attivazioni, è possibile chiedere a un utente di aprire un'applicazione di Office come Word nel computer in uso e quindi scegliere \*\*\*\* \> **account**file.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-141">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="f0b2f-142">In **informazioni sui prodotti** dovrebbe essere visualizzato **Prodotto a sottoscrizione** e **Microsoft Office 365 ProPlus**, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-142">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span></span>

![Informazioni sul prodotto in un'applicazione di Office](../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
<span data-ttu-id="f0b2f-144">Per assistenza con Office 365 ProPlus, vedere [Suggerimenti per la risoluzione dei problemi per Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-144">For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-requirements"></a><span data-ttu-id="f0b2f-145">Requisiti di Exchange</span><span class="sxs-lookup"><span data-stu-id="f0b2f-145">Exchange requirements</span></span>

<span data-ttu-id="f0b2f-p106">Microsoft Exchange archivia i manifesti del componente aggiuntivo all'interno del tenant dell'organizzazione. L'amministratore che distribuisce i componenti aggiuntivi e gli utenti che li ricevono devono avere una versione di Exchange Server che supporta l'autenticazione OAuth. Per impostazione predefinita, le distribuzioni multi-tenant o vNext dedicato di Exchange supportano OAuth. Le distribuzioni legacy dedicate e locali ibride di Exchange possono essere configurate per supportare OAuth. Tuttavia, non è la configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p106">Microsoft Exchange stores the add-in manifests within your organization's tenant. The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Server that supports OAuth authentication. By default, Exchange Multi-Tenant and Dedicated VNext deployments support OAuth. Exchange Dedicated Legacy and hybrid on-premises deployments can be configured to support OAuth; however, it isn't the default configuration.</span></span>
  
<span data-ttu-id="f0b2f-p107">Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per ogni utente può essere verificata usando il cmdlet di PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="office-365-centralized-deployment-compatibility-checker"></a><span data-ttu-id="f0b2f-152">Verifica compatibilità della distribuzione centralizzata di Office 365</span><span class="sxs-lookup"><span data-stu-id="f0b2f-152">Office 365 Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="f0b2f-p108">Con Verifica compatibilità della distribuzione centralizzata di Office 365, è possibile verificare se gli utenti del tenant sono configurati per l'uso della distribuzione centralizzata per Word, Excel e PowerPoint. Verifica compatibilità non è necessario per il supporto di Outlook. Scaricare Verifica compatibilità [qui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p108">Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="f0b2f-156">Esecuzione di verifica compatibilità</span><span class="sxs-lookup"><span data-stu-id="f0b2f-156">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="f0b2f-157">Avviare una finestra di PowerShell. exe con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-157">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="f0b2f-158">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-158">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="f0b2f-159">Eseguire il comando **Invoke-CompatabilityCheck** :</span><span class="sxs-lookup"><span data-stu-id="f0b2f-159">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="f0b2f-160">in cui viene richiesto di *_TenantDomain_* (ad esempio, *TailspinToysIncorporated. onmicrosoft.</span> com*) e le credenziali di *_TenantAdmin_* (utilizzare le credenziali di amministratore globale) e quindi richiede il consenso.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-160">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f0b2f-161">A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-161">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="f0b2f-162">Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-162">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="f0b2f-163">Il file viene salvato in **C:\Windows\System32** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-163">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="f0b2f-164">Il file di output contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-164">The output file contains the following information:</span></span>
  
- <span data-ttu-id="f0b2f-165">Nome utente</span><span class="sxs-lookup"><span data-stu-id="f0b2f-165">User Name</span></span>
    
- <span data-ttu-id="f0b2f-166">ID utente (indirizzo di posta elettronica dell'utente)</span><span class="sxs-lookup"><span data-stu-id="f0b2f-166">User ID (User's email address)</span></span>
    
- <span data-ttu-id="f0b2f-167">Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri</span><span class="sxs-lookup"><span data-stu-id="f0b2f-167">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="f0b2f-168">Piano di Office: il piano di Office in cui sono concessi in licenza</span><span class="sxs-lookup"><span data-stu-id="f0b2f-168">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="f0b2f-169">Office attivato: se Office è stato attivato</span><span class="sxs-lookup"><span data-stu-id="f0b2f-169">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="f0b2f-170">Cassetta postale supportata: se la cassetta postale è abilitata per OAuth</span><span class="sxs-lookup"><span data-stu-id="f0b2f-170">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="f0b2f-171">Assegnazioni di utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="f0b2f-171">User and group assignments</span></span>

<span data-ttu-id="f0b2f-172">La funzionalità Distribuzione centralizzata attualmente supporta la maggior parte dei gruppi supportati da Azure Active Directory, tra cui Gruppi di Office 365, le liste di distribuzione e i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-172">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0b2f-173">I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-173">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="f0b2f-174">La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e tutti i clienti del tenant.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-174">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="f0b2f-175">La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-175">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="f0b2f-p111">Esaminare l'esempio seguente, in cui Valeria, Pupetta e il gruppo Reparto vendite vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramma del reparto vendite](../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="f0b2f-179">Scoprire se un gruppo contiene gruppi annidati</span><span class="sxs-lookup"><span data-stu-id="f0b2f-179">Find out if a group contains nested groups</span></span>

<span data-ttu-id="f0b2f-180">Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-180">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="f0b2f-181">Se si immette il nome del gruppo all'interno del campo **a** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi nidificati.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-181">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="f0b2f-182">Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-182">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Scheda membri della scheda contatto di Outlook](../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="f0b2f-p113">È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente nella scheda **Appartenenza** della scheda contatto di Outlook si vede che il sottogruppo 1 è un membro del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Scheda appartenenza della scheda contatto di Outlook](../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="f0b2f-p114">In alternativa, è possibile usare l'API di Azure Active Directory Graph per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per altre informazioni, vedere [Operazioni su gruppi | Riferimento API Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="f0b2f-189">Contattare Microsoft per assistenza</span><span class="sxs-lookup"><span data-stu-id="f0b2f-189">Contacting Microsoft for support</span></span>

<span data-ttu-id="f0b2f-190">Se l'utente o gli utenti riscontrano problemi durante il caricamento del componente aggiuntivo utilizzando le app di Office per il Web (Word, Excel e così via), che sono state distribuite in modo centralizzato, potrebbe essere necessario contattare il supporto tecnico Microsoft ([informazioni su come](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="f0b2f-190">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="f0b2f-191">Specificare le informazioni seguenti sull'ambiente di Office 365 nel ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-191">Provide the following information about your Office 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="f0b2f-192">**Piattaforma**</span><span class="sxs-lookup"><span data-stu-id="f0b2f-192">**Platform**</span></span>|<span data-ttu-id="f0b2f-193">**Informazioni di debug**</span><span class="sxs-lookup"><span data-stu-id="f0b2f-193">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0b2f-194">Ufficio</span><span class="sxs-lookup"><span data-stu-id="f0b2f-194">Office</span></span>  <br/> | <span data-ttu-id="f0b2f-195">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="f0b2f-195">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="f0b2f-196">ID tenant ( [informazioni](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span><span class="sxs-lookup"><span data-stu-id="f0b2f-196">Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span></span>  <br/>  <span data-ttu-id="f0b2f-197">CorrelationId.</span><span class="sxs-lookup"><span data-stu-id="f0b2f-197">CorrelationID.</span></span> <span data-ttu-id="f0b2f-198">Visualizzare l'origine di una delle pagine di Office e cercare il valore dell'ID correlazione e inviarlo al supporto:</span><span class="sxs-lookup"><span data-stu-id="f0b2f-198">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="f0b2f-199">Rich client (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="f0b2f-199">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="f0b2f-200">Log di Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="f0b2f-200">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="f0b2f-201">Creare numeri dell'app client (preferibilmente come schermata da **file/account**)</span><span class="sxs-lookup"><span data-stu-id="f0b2f-201">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

