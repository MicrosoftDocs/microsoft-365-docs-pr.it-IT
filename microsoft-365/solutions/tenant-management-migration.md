---
title: Passaggio 4. Migrazione per i Microsoft 365 per i tenant aziendali
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Eseguire la migrazione Windows dispositivi, Office client e Office server per i tenant Microsoft 365 aziendali.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929145"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="51fa9-104">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="51fa9-104">Step 4.</span></span> <span data-ttu-id="51fa9-105">Migrazione per i Microsoft 365 per i tenant aziendali</span><span class="sxs-lookup"><span data-stu-id="51fa9-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="51fa9-106">La maggior parte delle organizzazioni aziendali dispone di un ambiente eterogeneo che include più versioni di sistemi operativi, software client e software server.</span><span class="sxs-lookup"><span data-stu-id="51fa9-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="51fa9-107">Microsoft 365 per le aziende include le versioni più sicure dei componenti chiave dell'infrastruttura IT.</span><span class="sxs-lookup"><span data-stu-id="51fa9-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="51fa9-108">Include inoltre funzionalità di produttività progettate per sfruttare le tecnologie cloud.</span><span class="sxs-lookup"><span data-stu-id="51fa9-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="51fa9-109">Per ottimizzare il valore aziendale del Microsoft 365 di prodotti integrati per le aziende, iniziare a pianificare e implementare una strategia per la migrazione di queste versioni:</span><span class="sxs-lookup"><span data-stu-id="51fa9-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="51fa9-110">Da</span><span class="sxs-lookup"><span data-stu-id="51fa9-110">From</span></span> | <span data-ttu-id="51fa9-111">A</span><span class="sxs-lookup"><span data-stu-id="51fa9-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="51fa9-112">Windows 7 e Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="51fa9-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="51fa9-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="51fa9-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="51fa9-114">Office prodotti client installati nei dispositivi del lavoratore</span><span class="sxs-lookup"><span data-stu-id="51fa9-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="51fa9-115">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="51fa9-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="51fa9-116">Office server installati nei server locali</span><span class="sxs-lookup"><span data-stu-id="51fa9-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="51fa9-117">I servizi basati su cloud equivalenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51fa9-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="51fa9-118">Migrazione a Windows 10</span><span class="sxs-lookup"><span data-stu-id="51fa9-118">Migrating to Windows 10</span></span>

<span data-ttu-id="51fa9-119">Ogni Microsoft 365 per le aziende include una licenza per Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="51fa9-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="51fa9-120">Per eseguire la migrazione dei dispositivi che Windows 7 o Windows 8.1, è possibile eseguire un aggiornamento sul posto.</span><span class="sxs-lookup"><span data-stu-id="51fa9-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="51fa9-121">Il supporto è terminato Windows 7 il *14 gennaio 2020.*</span><span class="sxs-lookup"><span data-stu-id="51fa9-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="51fa9-122">Per ulteriori metodi di installazione Windows 10 Enterprise un aggiornamento sul posto, vedere Windows 10 [di distribuzione.](/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="51fa9-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="51fa9-123">È anche possibile [pianificare la distribuzione di Windows 10](/windows/deployment/planning/) autonomamente.</span><span class="sxs-lookup"><span data-stu-id="51fa9-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="51fa9-124">Migrazione a Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="51fa9-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="51fa9-125">Microsoft 365 per le aziende include Microsoft 365 Apps for enterprise, una versione dei prodotti client Office (Word, PowerPoint, Excel e Outlook) che viene installata e aggiornata dal cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51fa9-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="51fa9-126">Per ulteriori informazioni, vedere [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="51fa9-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="51fa9-127">Anziché mantenere i computer correnti per Office 2019 o versioni precedenti, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="51fa9-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="51fa9-128">Ottenere e assegnare una Microsoft 365 per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="51fa9-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="51fa9-129">Disinstallare Office 2013 o Office 2016 nei propri computer.</span><span class="sxs-lookup"><span data-stu-id="51fa9-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="51fa9-130">Installare Microsoft 365 Apps for enterprise, singolarmente o durante un'implementazione IT.</span><span class="sxs-lookup"><span data-stu-id="51fa9-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="51fa9-131">Per altre informazioni, consulta la [Guida alla distribuzione di Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="51fa9-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="51fa9-132">Microsoft 365 Apps for enterprise gli aggiornamenti della sicurezza e i nuovi aggiornamenti delle funzionalità vengono installati automaticamente e possono sfruttare i servizi basati su cloud in Microsoft 365 per migliorare la sicurezza e la produttività.</span><span class="sxs-lookup"><span data-stu-id="51fa9-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="51fa9-133">Migrazione di dati e server locali a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51fa9-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="51fa9-134">Microsoft 365 per le aziende include versioni basate su cloud dei servizi server di Office che utilizzano alcuni degli stessi strumenti delle versioni locali del software server Office, ad esempio i Web browser e il client Outlook.</span><span class="sxs-lookup"><span data-stu-id="51fa9-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="51fa9-135">Questi servizi basati sul cloud vengono aggiornati automaticamente per la sicurezza e le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="51fa9-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="51fa9-136">Dopo la migrazione, il reparto IT può risparmiare il tempo necessario per la manutenzione e l'aggiornamento dei server locali.</span><span class="sxs-lookup"><span data-stu-id="51fa9-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="51fa9-137">Utilizzare le risorse seguenti per informazioni sulla migrazione di utenti e dati per carichi di Microsoft 365 specifici:</span><span class="sxs-lookup"><span data-stu-id="51fa9-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="51fa9-138">Spostare le cassette postali da un Exchange Server locale a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51fa9-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="51fa9-139">Eseguire SharePoint dati da SharePoint Server a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="51fa9-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="51fa9-140">Eseguire la Skype for Business online a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51fa9-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="51fa9-141">Transizione dell'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="51fa9-141">Transition your entire organization</span></span>

<span data-ttu-id="51fa9-142">Per ottenere un'immagine migliore di come spostare l'intera organizzazione nei prodotti e servizi di Microsoft 365 per le aziende, scaricare questo poster di transizione:</span><span class="sxs-lookup"><span data-stu-id="51fa9-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="51fa9-143">[![Immagine che mostra il poster transizione a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="51fa9-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="51fa9-144">Questo poster di due pagine è modo rapido per inventariare l'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="51fa9-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="51fa9-145">Usalo per ottenere indicazioni per il passaggio a un prodotto o un servizio in Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="51fa9-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="51fa9-146">Mostra i Windows e Office e altri elementi dell'infrastruttura e della sicurezza, come la gestione dei dispositivi, la protezione delle identità e delle minacce, la protezione delle informazioni e la conformità.</span><span class="sxs-lookup"><span data-stu-id="51fa9-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="51fa9-147">Risultati del Passaggio 4</span><span class="sxs-lookup"><span data-stu-id="51fa9-147">Results of Step 4</span></span>

<span data-ttu-id="51fa9-148">Per la migrazione per Microsoft 365 tenant, è stato determinato:</span><span class="sxs-lookup"><span data-stu-id="51fa9-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="51fa9-149">Quali dispositivi eseguono Windows 7 o Windows 8.1 e il piano per aggiornarli Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="51fa9-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="51fa9-150">Quali dispositivi eseguono le app client Office e il piano per aggiornarle alle app Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="51fa9-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="51fa9-151">Quali servizi server Office locali devono essere migrati nel Microsoft 365 equivalente e il piano per eseguirne la migrazione e i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="51fa9-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="51fa9-152">Ecco un esempio di tenant con una migrazione completata di server locali.</span><span class="sxs-lookup"><span data-stu-id="51fa9-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Esempio di tenant con migrazione completata di server locali](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="51fa9-154">In questa figura, l'organizzazione dispone di:</span><span class="sxs-lookup"><span data-stu-id="51fa9-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="51fa9-155">È stata eseguita la migrazione delle cassette postali Exchange Server locali a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="51fa9-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="51fa9-156">È stata eseguita la migrazione dei siti e dei dati di SharePoint Server locali in SharePoint in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51fa9-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="51fa9-157">Manutenzione continua per la migrazione</span><span class="sxs-lookup"><span data-stu-id="51fa9-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="51fa9-158">Su base continuativa, potrebbe essere necessario:</span><span class="sxs-lookup"><span data-stu-id="51fa9-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="51fa9-159">A seconda dello stato della migrazione Exchange cassetta postale, continuare a eseguire la transizione Exchange Online'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51fa9-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="51fa9-160">A seconda dello stato della migrazione del sito SharePoint locale, continuare a eseguire la transizione a SharePoint in Microsoft 365 all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51fa9-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="51fa9-161">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="51fa9-161">Next step</span></span>

<span data-ttu-id="51fa9-162">[![Passaggio 5. Distribuire la gestione di dispositivi e app](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="51fa9-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="51fa9-163">Continua con [la gestione di dispositivi e app](tenant-management-device-management.md) per distribuire la gestione di dispositivi e app.</span><span class="sxs-lookup"><span data-stu-id="51fa9-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>