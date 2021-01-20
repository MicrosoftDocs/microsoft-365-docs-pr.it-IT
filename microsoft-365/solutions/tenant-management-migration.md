---
title: Passaggio 4. Migrazione per i tenant di Microsoft 365 per Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Migrare i dispositivi Windows, le app client di Office e i server di Office per i tenant Microsoft 365.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908627"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e03e6-104">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e03e6-104">Step 4.</span></span> <span data-ttu-id="e03e6-105">Migrazione per i tenant di Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="e03e6-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e03e6-106">La maggior parte delle organizzazioni dell'organizzazione dispone di un ambiente eterogeneo che include più versioni di sistemi operativi, software client e server.</span><span class="sxs-lookup"><span data-stu-id="e03e6-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="e03e6-107">Microsoft 365 per Enterprise include le versioni più sicure dei componenti chiave dell'infrastruttura IT.</span><span class="sxs-lookup"><span data-stu-id="e03e6-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="e03e6-108">Include anche funzionalità di produttività progettate per sfruttare le tecnologie cloud.</span><span class="sxs-lookup"><span data-stu-id="e03e6-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="e03e6-109">Per massimizzare il valore aziendale della famiglia di prodotti integrata Microsoft 365 for Enterprise, iniziare la pianificazione e l'implementazione di una strategia per la migrazione delle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e03e6-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="e03e6-110">Da</span><span class="sxs-lookup"><span data-stu-id="e03e6-110">From</span></span> | <span data-ttu-id="e03e6-111">A</span><span class="sxs-lookup"><span data-stu-id="e03e6-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="e03e6-112">Windows 7 e Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="e03e6-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="e03e6-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e03e6-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="e03e6-114">Prodotti client di Office installati nei dispositivi del lavoratore</span><span class="sxs-lookup"><span data-stu-id="e03e6-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="e03e6-115">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="e03e6-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="e03e6-116">Prodotti di Office Server installati nei server locali</span><span class="sxs-lookup"><span data-stu-id="e03e6-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="e03e6-117">Servizi basati su cloud equivalenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e03e6-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="e03e6-118">Migrazione a Windows 10</span><span class="sxs-lookup"><span data-stu-id="e03e6-118">Migrating to Windows 10</span></span>

<span data-ttu-id="e03e6-119">Ogni licenza di Microsoft 365 per Enterprise include una licenza per Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e03e6-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="e03e6-120">Per eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8,1, è possibile eseguire un aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="e03e6-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="e03e6-121">Supporto finito per Windows 7 *gennaio 14 2020*.</span><span class="sxs-lookup"><span data-stu-id="e03e6-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="e03e6-122">Per ulteriori metodi di installazione di Windows 10 Enterprise oltre a un aggiornamento sul posto, vedere [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="e03e6-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="e03e6-123">È anche possibile [pianificare la distribuzione di Windows 10](https://aka.ms/planforwin10deployment) autonomamente.</span><span class="sxs-lookup"><span data-stu-id="e03e6-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="e03e6-124">Migrazione a Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e03e6-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="e03e6-125">Microsoft 365 per Enterprise include Microsoft 365 Apps for Enterprise, una versione dei prodotti client di Office (Word, PowerPoint, Excel e Outlook) installata e aggiornata da Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="e03e6-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="e03e6-126">Per ulteriori informazioni, vedere [About Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="e03e6-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="e03e6-127">Anziché mantenere aggiornati i computer per le versioni di Office 2019 o versione precedente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e03e6-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="e03e6-128">Ottenere e assegnare una licenza Microsoft 365 per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e03e6-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="e03e6-129">Disinstallare Office 2013 o Office 2016 nei propri computer.</span><span class="sxs-lookup"><span data-stu-id="e03e6-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="e03e6-130">Installare le app Microsoft 365 per Enterprise, individualmente o durante un'implementazione IT.</span><span class="sxs-lookup"><span data-stu-id="e03e6-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="e03e6-131">Per ulteriori informazioni, vedere [Deployment Guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="e03e6-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="e03e6-132">Microsoft 365 Apps for Enterprise installa automaticamente sia gli aggiornamenti della sicurezza che i nuovi aggiornamenti delle funzionalità e può avvalersi dei servizi basati su cloud in Microsoft 365 per garantire una maggiore sicurezza e produttività.</span><span class="sxs-lookup"><span data-stu-id="e03e6-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="e03e6-133">Migrazione di dati e server locali a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e03e6-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="e03e6-134">Microsoft 365 per Enterprise include versioni basate su cloud dei servizi di Office Server che utilizzano alcuni degli stessi strumenti delle versioni locali del software di Office Server, ad esempio i Web browser e il client di Outlook.</span><span class="sxs-lookup"><span data-stu-id="e03e6-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="e03e6-135">Questi servizi basati sul cloud vengono aggiornati automaticamente per la sicurezza e le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e03e6-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="e03e6-136">Dopo la migrazione, il reparto IT può salvare il tempo necessario per gestire e aggiornare i server locali.</span><span class="sxs-lookup"><span data-stu-id="e03e6-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="e03e6-137">Utilizzare le risorse seguenti per informazioni sulla migrazione di utenti e dati per carichi di lavoro specifici di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e03e6-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="e03e6-138">Spostare le cassette postali dal server Exchange locale a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e03e6-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="e03e6-139">Eseguire la migrazione dei dati di SharePoint da SharePoint Server a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e03e6-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="e03e6-140">Eseguire la migrazione di Skype for business online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e03e6-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="e03e6-141">Transizione dell'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="e03e6-141">Transition your entire organization</span></span>

<span data-ttu-id="e03e6-142">Per ottenere un'immagine migliore di come spostare l'intera organizzazione ai prodotti e ai servizi in Microsoft 365 for Enterprise, scaricare questo poster di transizione:</span><span class="sxs-lookup"><span data-stu-id="e03e6-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="e03e6-143">[![Immagine che mostra la transizione al poster di Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="e03e6-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="e03e6-144">Questo poster di due pagine è modo rapido per inventariare l'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="e03e6-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="e03e6-145">Utilizzarlo per ottenere indicazioni per il passaggio a un prodotto o a un servizio in Microsoft 365 per Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e03e6-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="e03e6-146">Vengono visualizzati i prodotti Windows e Office e altri elementi di infrastruttura e sicurezza, quali gestione dei dispositivi, identità e protezione delle minacce e protezione delle informazioni e conformità.</span><span class="sxs-lookup"><span data-stu-id="e03e6-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="e03e6-147">Risultati del Passaggio 4</span><span class="sxs-lookup"><span data-stu-id="e03e6-147">Results of Step 4</span></span>

<span data-ttu-id="e03e6-148">Per la migrazione per il tenant di Microsoft 365, sono state determinate le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="e03e6-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="e03e6-149">Quali dispositivi eseguono Windows 7 o Windows 8,1 e il piano per aggiornarli a Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e03e6-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="e03e6-150">Quali dispositivi eseguono le app client di Office e il piano di aggiornamento a Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e03e6-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="e03e6-151">Quali servizi di Office Server locali devono essere migrati nell'equivalente Microsoft 365 e il piano per la migrazione e i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="e03e6-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="e03e6-152">Di seguito è riportato un esempio di un tenant con una migrazione completata dei server locali.</span><span class="sxs-lookup"><span data-stu-id="e03e6-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Esempio di un tenant con una migrazione completata dei server locali](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="e03e6-154">In questa figura, l'organizzazione dispone di:</span><span class="sxs-lookup"><span data-stu-id="e03e6-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="e03e6-155">È stata eseguita la migrazione delle cassette postali di Exchange Server locali a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e03e6-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="e03e6-156">Sono stati migrati i siti e i dati di SharePoint Server locali in SharePoint in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e03e6-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="e03e6-157">Manutenzione continua per la migrazione</span><span class="sxs-lookup"><span data-stu-id="e03e6-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="e03e6-158">Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e03e6-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="e03e6-159">A seconda dello stato della migrazione delle cassette postali di Exchange, continuare a eseguire il passaggio a Exchange Online all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e03e6-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="e03e6-160">A seconda dello stato della migrazione del sito di SharePoint locale, continuare a eseguire il passaggio a SharePoint in Microsoft 365 all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e03e6-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="e03e6-161">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e03e6-161">Next step</span></span>

<span data-ttu-id="e03e6-162">[![Passaggio 5. Distribuire la gestione di dispositivi e app](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="e03e6-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="e03e6-163">Continuare con la [gestione di dispositivi e app](tenant-management-device-management.md) per distribuire la gestione di dispositivi e app.</span><span class="sxs-lookup"><span data-stu-id="e03e6-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
