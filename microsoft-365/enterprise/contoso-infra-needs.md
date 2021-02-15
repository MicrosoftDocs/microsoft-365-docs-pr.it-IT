---
title: Infrastruttura IT e esigenze aziendali di Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo Microsoft 365 per le aziende deve soddisfare le esigenze aziendali dell'azienda.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558407"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="9e889-103">Infrastruttura IT e esigenze aziendali di Contoso</span><span class="sxs-lookup"><span data-stu-id="9e889-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="9e889-104">Contoso sta per passare da un'infrastruttura IT centralizzata locale a una configurazione inclusiva del cloud che incorpora i carichi di lavoro e le applicazioni di produttività personale basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="9e889-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="9e889-105">Infrastruttura IT di Contoso esistente</span><span class="sxs-lookup"><span data-stu-id="9e889-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="9e889-106">Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="9e889-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="9e889-107">Ecco l'ufficio della sede centrale con data center delle applicazioni, una rete perimetrale e Internet.</span><span class="sxs-lookup"><span data-stu-id="9e889-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infrastruttura IT di Contoso esistente](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="9e889-109">I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9e889-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="9e889-110">Applicazioni line-of-business personalizzate che usano SQL Server e altri database Linux.</span><span class="sxs-lookup"><span data-stu-id="9e889-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="9e889-111">Un set di server SharePoint legacy.</span><span class="sxs-lookup"><span data-stu-id="9e889-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="9e889-112">Server a livello di organizzazione e di team per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="9e889-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="9e889-113">Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo.</span><span class="sxs-lookup"><span data-stu-id="9e889-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="9e889-114">Questi server sono sotto il controllo dei reparti IT regionali.</span><span class="sxs-lookup"><span data-stu-id="9e889-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="9e889-115">La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.</span><span class="sxs-lookup"><span data-stu-id="9e889-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="9e889-116">Nella rete perimetrale della sede di Contoso, diversi set di server forniscono:</span><span class="sxs-lookup"><span data-stu-id="9e889-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="9e889-117">Hosting per il sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, forniture e servizi.</span><span class="sxs-lookup"><span data-stu-id="9e889-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="9e889-118">Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.</span><span class="sxs-lookup"><span data-stu-id="9e889-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="9e889-119">Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="9e889-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="9e889-120">Esigenze aziendali di Contoso</span><span class="sxs-lookup"><span data-stu-id="9e889-120">Contoso business needs</span></span>

<span data-ttu-id="9e889-121">Le esigenze aziendali di Contoso rientrano in cinque categorie principali:</span><span class="sxs-lookup"><span data-stu-id="9e889-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="9e889-122">**Produttività**</span><span class="sxs-lookup"><span data-stu-id="9e889-122">**Productivity**</span></span>

- <span data-ttu-id="9e889-123">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="9e889-123">Make collaboration easier</span></span>

  <span data-ttu-id="9e889-124">Sostituire la collaborazione basata su posta elettronica e condivisione file con un modello online che consente modifiche in tempo reale ai documenti, riunioni online più semplici e thread di conversazione acquisiti.</span><span class="sxs-lookup"><span data-stu-id="9e889-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="9e889-125">Migliorare la produttività per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="9e889-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="9e889-126">Con molti dipendenti che lavorano da casa o sul campo, sostituire la soluzione VPN con colli di bottiglia con un accesso efficace ai dati e alle risorse di Contoso nel cloud.</span><span class="sxs-lookup"><span data-stu-id="9e889-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="9e889-127">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="9e889-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="9e889-128">Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.</span><span class="sxs-lookup"><span data-stu-id="9e889-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="9e889-129">**Sicurezza**</span><span class="sxs-lookup"><span data-stu-id="9e889-129">**Security**</span></span>

- <span data-ttu-id="9e889-130">Gestione delle identità e degli accessi</span><span class="sxs-lookup"><span data-stu-id="9e889-130">Identity and access management</span></span>

  <span data-ttu-id="9e889-131">Applicare l'autenticazione a più fattori e altre forme di autenticazione e proteggere le credenziali degli account utente e amministratore.</span><span class="sxs-lookup"><span data-stu-id="9e889-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="9e889-132">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="9e889-132">Threat protection</span></span>

  <span data-ttu-id="9e889-133">Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9e889-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="9e889-134">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="9e889-134">Information protection</span></span>

  <span data-ttu-id="9e889-135">Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="9e889-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="9e889-136">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="9e889-136">Security management</span></span>

  <span data-ttu-id="9e889-137">Monitorare la sicurezza e rilevare e rispondere alle minacce in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9e889-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="9e889-138">**Accesso remoto e mobile e partner commerciali**</span><span class="sxs-lookup"><span data-stu-id="9e889-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="9e889-139">Migliorare la sicurezza per i lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="9e889-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="9e889-140">Implementare la gestione dei dispositivi Bring Your Own Device (BYOD) e di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto delle applicazioni e la protezione dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="9e889-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="9e889-141">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="9e889-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="9e889-142">Ridurre i costi di manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando le risorse a cui si accede comunemente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="9e889-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="9e889-143">Offrire una connettività migliore e ridurre il sovraccarico per le transazioni business-to-susiness (B2B)</span><span class="sxs-lookup"><span data-stu-id="9e889-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="9e889-144">Sostituire una extranet di partner obsoleta e costosa con una soluzione basata su cloud che utilizza l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="9e889-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="9e889-145">**Conformità**</span><span class="sxs-lookup"><span data-stu-id="9e889-145">**Compliance**</span></span>

- <span data-ttu-id="9e889-146">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="9e889-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="9e889-147">Garantire la conformità alle normative del settore e regionali per l'archiviazione dei dati, la crittografia, la privacy dei dati e le normative sui dati personali, come il Regolamento generale sulla protezione dei dati (GDPR) per l'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="9e889-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="9e889-148">**Gestione**</span><span class="sxs-lookup"><span data-stu-id="9e889-148">**Management**</span></span>

- <span data-ttu-id="9e889-149">Ridurre il sovraccarico IT per la gestione del software in esecuzione su PC e dispositivi client</span><span class="sxs-lookup"><span data-stu-id="9e889-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="9e889-150">Automatizzare l'installazione degli aggiornamenti per il sistema operativo Windows e Microsoft 365 Apps for enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e889-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="9e889-151">Mapping delle esigenze aziendali di Contoso a Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9e889-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="9e889-152">Il reparto IT di Contoso ha determinato la seguente mappatura delle esigenze aziendali con le funzionalità di Microsoft 365 E5 prima della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="9e889-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="9e889-153">Categoria</span><span class="sxs-lookup"><span data-stu-id="9e889-153">Category</span></span> | <span data-ttu-id="9e889-154">Esigenze aziendali</span><span class="sxs-lookup"><span data-stu-id="9e889-154">Business need</span></span> | <span data-ttu-id="9e889-155">Prodotti o funzionalità di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9e889-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="9e889-156">Produttività</span><span class="sxs-lookup"><span data-stu-id="9e889-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="9e889-157">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="9e889-157">Make collaboration easier</span></span> | <span data-ttu-id="9e889-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="9e889-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="9e889-159">Migliorare la produttività per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="9e889-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="9e889-160">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e889-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9e889-161">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="9e889-161">Increase creativity and innovation</span></span> | <span data-ttu-id="9e889-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9e889-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="9e889-163">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9e889-163">Security</span></span> |  |  |
|  | <span data-ttu-id="9e889-164">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="9e889-164">Identity & access management</span></span> | <span data-ttu-id="9e889-165">Account amministratore globale dedicati con Azure AD Multi-Factor Authentication (MFA) e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="9e889-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="9e889-166">MFA per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="9e889-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="9e889-167">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="9e889-167">Conditional Access</span></span> <BR> <span data-ttu-id="9e889-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="9e889-168">Windows Hello</span></span> <BR> <span data-ttu-id="9e889-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="9e889-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="9e889-170">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="9e889-170">Threat protection</span></span> | <span data-ttu-id="9e889-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="9e889-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="9e889-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9e889-172">Windows Defender</span></span> <BR> <span data-ttu-id="9e889-173">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="9e889-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="9e889-174">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="9e889-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="9e889-175">Analisi e risposta alle minacce di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e889-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="9e889-176">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="9e889-176">Information protection</span></span> | <span data-ttu-id="9e889-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="9e889-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="9e889-178">Prevenzione della perdita dei dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="9e889-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="9e889-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="9e889-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="9e889-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9e889-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="9e889-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9e889-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9e889-182">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="9e889-182">Security management</span></span> | <span data-ttu-id="9e889-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="9e889-183">Azure Defender</span></span>  <BR> <span data-ttu-id="9e889-184">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="9e889-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="9e889-185">Accesso remoto e mobile e partner commerciali</span><span class="sxs-lookup"><span data-stu-id="9e889-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="9e889-186">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="9e889-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="9e889-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9e889-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9e889-188">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="9e889-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="9e889-189">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e889-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9e889-190">Migliorare la connettività e ridurre il sovraccarico per le transazioni B2B</span><span class="sxs-lookup"><span data-stu-id="9e889-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="9e889-191">Autenticazione federata e risorse basate su cloud</span><span class="sxs-lookup"><span data-stu-id="9e889-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="9e889-192">Conformità</span><span class="sxs-lookup"><span data-stu-id="9e889-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="9e889-193">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="9e889-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="9e889-194">Funzionalità GDPR in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e889-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="9e889-195">Gestione</span><span class="sxs-lookup"><span data-stu-id="9e889-195">Management</span></span> |  |  |
|  | <span data-ttu-id="9e889-196">Ridurre il sovraccarico IT per l'installazione degli aggiornamenti client</span><span class="sxs-lookup"><span data-stu-id="9e889-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="9e889-197">Aggiornamenti di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e889-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="9e889-198">Aggiornamenti di App Microsoft 365 per grandi imprese</span><span class="sxs-lookup"><span data-stu-id="9e889-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="9e889-199">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9e889-199">Next step</span></span>

<span data-ttu-id="9e889-200">Informazioni sulla rete [locale](contoso-networking.md) di Contoso Corporation e su come è stata ottimizzata per l'accesso e la latenza alle risorse basate sul cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e889-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e889-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e889-201">See also</span></span>

[<span data-ttu-id="9e889-202">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9e889-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9e889-203">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="9e889-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
