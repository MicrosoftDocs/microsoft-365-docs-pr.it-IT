---
title: Infrastruttura IT ed esigenze aziendali di contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo le esigenze aziendali dell'azienda sono soddisfatte da Microsoft 365 per Enterprise.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637176"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="fb68f-103">Infrastruttura IT ed esigenze aziendali di contoso</span><span class="sxs-lookup"><span data-stu-id="fb68f-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="fb68f-104">Contoso si sta spostando da un'infrastruttura IT centralizzata locale a una configurazione cloud-inclusive che incorpora carichi di lavoro e applicazioni per la produttività personale basati su cloud.</span><span class="sxs-lookup"><span data-stu-id="fb68f-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="fb68f-105">Infrastruttura IT esistente di contoso</span><span class="sxs-lookup"><span data-stu-id="fb68f-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="fb68f-106">Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="fb68f-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="fb68f-107">Nella figura 1 viene illustrata la sede centrale con i centri dati delle applicazioni, una DMZ e Internet.</span><span class="sxs-lookup"><span data-stu-id="fb68f-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infrastruttura IT esistente di contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="fb68f-109">**Figura 1: infrastruttura IT esistente di contoso**</span><span class="sxs-lookup"><span data-stu-id="fb68f-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="fb68f-110">I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="fb68f-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="fb68f-111">Applicazioni line-of-business personalizzate che utilizzano SQL Server e altri database di Linux.</span><span class="sxs-lookup"><span data-stu-id="fb68f-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="fb68f-112">Un set di server SharePoint legacy.</span><span class="sxs-lookup"><span data-stu-id="fb68f-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="fb68f-113">Server a livello di organizzazione e di team per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="fb68f-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="fb68f-114">Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo.</span><span class="sxs-lookup"><span data-stu-id="fb68f-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="fb68f-115">Questi server sono sotto il controllo dei reparti IT regionali.</span><span class="sxs-lookup"><span data-stu-id="fb68f-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="fb68f-116">La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.</span><span class="sxs-lookup"><span data-stu-id="fb68f-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="fb68f-117">Nella DMZ della sede centrale di Contoso, diversi set di server offrono:</span><span class="sxs-lookup"><span data-stu-id="fb68f-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="fb68f-118">Hosting per il sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, forniture e servizi.</span><span class="sxs-lookup"><span data-stu-id="fb68f-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="fb68f-119">Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.</span><span class="sxs-lookup"><span data-stu-id="fb68f-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="fb68f-120">Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="fb68f-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="fb68f-121">Esigenze aziendali di contoso</span><span class="sxs-lookup"><span data-stu-id="fb68f-121">Contoso business needs</span></span>

<span data-ttu-id="fb68f-122">Le esigenze aziendali di Contoso rientrano in cinque categorie principali:</span><span class="sxs-lookup"><span data-stu-id="fb68f-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="fb68f-123">**Produttività**</span><span class="sxs-lookup"><span data-stu-id="fb68f-123">**Productivity**</span></span>

- <span data-ttu-id="fb68f-124">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="fb68f-124">Make collaboration easier</span></span>

  <span data-ttu-id="fb68f-125">Sostituisci la collaborazione basata su condivisione file e la posta elettronica con un modello online che consente modifiche in tempo reale sui documenti, riunioni online più semplici e thread di conversazione acquisiti.</span><span class="sxs-lookup"><span data-stu-id="fb68f-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="fb68f-126">Migliorare la produttività per utenti remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="fb68f-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="fb68f-127">Con molti dipendenti che lavorano da casa o nel campo, sostituire la soluzione VPN con collo di bottiglia con accesso performante ai dati e alle risorse di Contoso nel cloud.</span><span class="sxs-lookup"><span data-stu-id="fb68f-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="fb68f-128">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="fb68f-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="fb68f-129">Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.</span><span class="sxs-lookup"><span data-stu-id="fb68f-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="fb68f-130">**Sicurezza**</span><span class="sxs-lookup"><span data-stu-id="fb68f-130">**Security**</span></span>

- <span data-ttu-id="fb68f-131">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="fb68f-131">Identity and access management</span></span>

  <span data-ttu-id="fb68f-132">Applicare più fattori e altre forme di autenticazione e proteggere le credenziali degli account utente e amministratore.</span><span class="sxs-lookup"><span data-stu-id="fb68f-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="fb68f-133">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="fb68f-133">Threat protection</span></span>

  <span data-ttu-id="fb68f-134">Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fb68f-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="fb68f-135">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="fb68f-135">Information protection</span></span>

  <span data-ttu-id="fb68f-136">Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="fb68f-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="fb68f-137">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb68f-137">Security management</span></span>

  <span data-ttu-id="fb68f-138">Monitorare la posizione di sicurezza e rilevare e rispondere alle minacce in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="fb68f-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="fb68f-139">**Accesso remoto e mobile e partner commerciali**</span><span class="sxs-lookup"><span data-stu-id="fb68f-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="fb68f-140">Migliorare la sicurezza per i lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="fb68f-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="fb68f-141">Implementare portare il proprio dispositivo (BYOD) e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto dell'applicazione e la protezione dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="fb68f-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="fb68f-142">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="fb68f-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="fb68f-143">Ridurre i costi di manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando le risorse comunemente accessibili nel cloud.</span><span class="sxs-lookup"><span data-stu-id="fb68f-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="fb68f-144">Fornire una migliore connettività e ridurre le spese per le transazioni business-to-Susi (B2B)</span><span class="sxs-lookup"><span data-stu-id="fb68f-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="fb68f-145">Sostituire un'Extranet di partner obsoleta e costosa con una soluzione basata sul cloud in cui viene utilizzata l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="fb68f-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="fb68f-146">**Conformità**</span><span class="sxs-lookup"><span data-stu-id="fb68f-146">**Compliance**</span></span>

- <span data-ttu-id="fb68f-147">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="fb68f-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="fb68f-148">Garantire la conformità con le normative industriali e regionali per l'archiviazione dei dati, la crittografia, la privacy dei dati e le normative sui dati personali, come il regolamento generale sulla protezione dei dati (GDPR) per l'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="fb68f-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="fb68f-149">**Gestione**</span><span class="sxs-lookup"><span data-stu-id="fb68f-149">**Management**</span></span>

- <span data-ttu-id="fb68f-150">Riduzione del sovraccarico per la gestione del software in esecuzione su computer e dispositivi client</span><span class="sxs-lookup"><span data-stu-id="fb68f-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="fb68f-151">Automatizzare l'installazione degli aggiornamenti nel sistema operativo Windows e nelle app Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fb68f-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="fb68f-152">Mapping delle esigenze aziendali di Contoso a Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb68f-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="fb68f-153">Il reparto IT di Contoso ha determinato la seguente mappatura delle esigenze aziendali alle caratteristiche di Microsoft 365 E5 prima della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="fb68f-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="fb68f-154">Categoria</span><span class="sxs-lookup"><span data-stu-id="fb68f-154">Category</span></span> | <span data-ttu-id="fb68f-155">Esigenze aziendali</span><span class="sxs-lookup"><span data-stu-id="fb68f-155">Business need</span></span> | <span data-ttu-id="fb68f-156">Microsoft 365 per prodotti o funzionalità aziendali</span><span class="sxs-lookup"><span data-stu-id="fb68f-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="fb68f-157">Produttività</span><span class="sxs-lookup"><span data-stu-id="fb68f-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="fb68f-158">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="fb68f-158">Make collaboration easier</span></span> | <span data-ttu-id="fb68f-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="fb68f-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="fb68f-160">Migliorare la produttività per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="fb68f-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="fb68f-161">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb68f-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="fb68f-162">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="fb68f-162">Increase creativity and innovation</span></span> | <span data-ttu-id="fb68f-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="fb68f-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="fb68f-164">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb68f-164">Security</span></span> |  |  |
|  | <span data-ttu-id="fb68f-165">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="fb68f-165">Identity & access management</span></span> | <span data-ttu-id="fb68f-166">Account di amministratore globale dedicati con l'autenticazione a più fattori di Azure (AMF) e Azure Active Directory Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="fb68f-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="fb68f-167">MFA per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="fb68f-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="fb68f-168">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="fb68f-168">Conditional Access</span></span> <BR> <span data-ttu-id="fb68f-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="fb68f-169">Windows Hello</span></span> <BR> <span data-ttu-id="fb68f-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="fb68f-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="fb68f-171">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="fb68f-171">Threat protection</span></span> | <span data-ttu-id="fb68f-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="fb68f-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="fb68f-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="fb68f-173">Windows Defender</span></span> <BR> <span data-ttu-id="fb68f-174">Protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="fb68f-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="fb68f-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fb68f-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="fb68f-176">Analisi e risposta alle minacce di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb68f-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="fb68f-177">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="fb68f-177">Information protection</span></span> | <span data-ttu-id="fb68f-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="fb68f-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="fb68f-179">Prevenzione della perdita dei dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="fb68f-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="fb68f-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="fb68f-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="fb68f-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fb68f-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="fb68f-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fb68f-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="fb68f-183">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="fb68f-183">Security management</span></span> | <span data-ttu-id="fb68f-184">Centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="fb68f-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="fb68f-185">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="fb68f-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="fb68f-186">Accesso remoto e mobile e partner commerciali</span><span class="sxs-lookup"><span data-stu-id="fb68f-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="fb68f-187">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="fb68f-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="fb68f-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fb68f-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="fb68f-189">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="fb68f-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="fb68f-190">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb68f-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="fb68f-191">Migliorare la connettività e ridurre le spese per le transazioni B2B</span><span class="sxs-lookup"><span data-stu-id="fb68f-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="fb68f-192">Autenticazione federata e risorse basate su cloud</span><span class="sxs-lookup"><span data-stu-id="fb68f-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="fb68f-193">Conformità</span><span class="sxs-lookup"><span data-stu-id="fb68f-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="fb68f-194">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="fb68f-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="fb68f-195">Funzionalità di GDPR in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb68f-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="fb68f-196">Gestione</span><span class="sxs-lookup"><span data-stu-id="fb68f-196">Management</span></span> |  |  |
|  | <span data-ttu-id="fb68f-197">Riduzione del sovraccarico per l'installazione degli aggiornamenti client</span><span class="sxs-lookup"><span data-stu-id="fb68f-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="fb68f-198">Anelli di distribuzione</span><span class="sxs-lookup"><span data-stu-id="fb68f-198">Deployment rings</span></span> <BR> <span data-ttu-id="fb68f-199">Aggiornamenti di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb68f-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="fb68f-200">Aggiornamenti di App Microsoft 365 per grandi imprese</span><span class="sxs-lookup"><span data-stu-id="fb68f-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="fb68f-201">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="fb68f-201">Next step</span></span>

<span data-ttu-id="fb68f-202">Informazioni [sulla rete](contoso-networking.md) Contoso Corporation in locale e su come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb68f-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb68f-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb68f-203">See also</span></span>

[<span data-ttu-id="fb68f-204">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="fb68f-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fb68f-205">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="fb68f-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
