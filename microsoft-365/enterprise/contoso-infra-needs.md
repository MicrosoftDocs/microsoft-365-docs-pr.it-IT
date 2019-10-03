---
title: Infrastruttura IT ed esigenze di business di Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo Microsoft 365 Enterprise ha soddisfatto le sue esigenze di business.
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369587"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="ad010-103">Infrastruttura IT ed esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="ad010-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="ad010-104">**Riepilogo:** comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo Microsoft 365 Enterprise ha soddisfatto le sue esigenze di business.</span><span class="sxs-lookup"><span data-stu-id="ad010-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="ad010-105">Contoso sta cambiando la propria infrastruttura IT da un modello centralizzato locale a un'infrastruttura comprensiva di cloud che gestisce carichi di lavoro di produttività personale e applicazioni basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="ad010-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="ad010-106">Infrastruttura IT esistente di Contoso</span><span class="sxs-lookup"><span data-stu-id="ad010-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="ad010-107">Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="ad010-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="ad010-108">La Figura 1 mostra l'ufficio di una sede con centri dati delle applicazioni, una rete perimetrale e Internet.</span><span class="sxs-lookup"><span data-stu-id="ad010-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Infrastruttura IT esistente di Contoso](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="ad010-110">**Figura 1: Infrastruttura IT esistente di Contoso**</span><span class="sxs-lookup"><span data-stu-id="ad010-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="ad010-111">I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="ad010-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="ad010-112">Applicazioni line of business personalizzate che utilizzano SQL Server e altri database Linux.</span><span class="sxs-lookup"><span data-stu-id="ad010-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="ad010-113">Un set di server SharePoint legacy.</span><span class="sxs-lookup"><span data-stu-id="ad010-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="ad010-114">Server a livello di organizzazione e di team per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="ad010-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="ad010-115">Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo.</span><span class="sxs-lookup"><span data-stu-id="ad010-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="ad010-116">Questi server sono sotto il controllo dei reparti IT regionali.</span><span class="sxs-lookup"><span data-stu-id="ad010-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="ad010-117">La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.</span><span class="sxs-lookup"><span data-stu-id="ad010-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="ad010-118">Nella rete perimetrale degli uffici di Contoso, gruppi di server forniscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ad010-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="ad010-119">Hosting del sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, materiali o assistenza.</span><span class="sxs-lookup"><span data-stu-id="ad010-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="ad010-120">Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.</span><span class="sxs-lookup"><span data-stu-id="ad010-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="ad010-121">Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="ad010-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="ad010-122">Esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="ad010-122">Contoso's business needs</span></span>

<span data-ttu-id="ad010-123">Le esigenze di business di Contoso rientrano in cinque categorie principali.</span><span class="sxs-lookup"><span data-stu-id="ad010-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="ad010-124">Produttività:</span><span class="sxs-lookup"><span data-stu-id="ad010-124">Productivity:</span></span>

- <span data-ttu-id="ad010-125">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="ad010-125">Make collaboration easier</span></span>

  <span data-ttu-id="ad010-126">Sostituire il modello di collaborazione basato su posta elettronica e scambio di file con un modello online che consente di apportare modifiche in tempo reale ai documenti, partecipare a riunioni online e tenere traccia delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="ad010-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="ad010-127">Migliorare la produttività per utenti remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="ad010-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="ad010-128">Dato il numero elevato di utenti che lavorano da casa o sul campo, è preferibile sostituire la soluzione VPN caratterizzata da colli di bottiglia con un accesso ai dati e alle risorse di Contoso nel cloud che sia in grado di garantire prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="ad010-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="ad010-129">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="ad010-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="ad010-130">Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.</span><span class="sxs-lookup"><span data-stu-id="ad010-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="ad010-131">Sicurezza:</span><span class="sxs-lookup"><span data-stu-id="ad010-131">Security:</span></span>

- <span data-ttu-id="ad010-132">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="ad010-132">Identity and access management</span></span>

  <span data-ttu-id="ad010-133">Applicare l'autenticazione a più fattori e altre forme di autenticazione e proteggere le credenziali dell'account di utenti e amministratori.</span><span class="sxs-lookup"><span data-stu-id="ad010-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="ad010-134">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ad010-134">Threat protection</span></span>

  <span data-ttu-id="ad010-135">Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ad010-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="ad010-136">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="ad010-136">Information protection</span></span>

  <span data-ttu-id="ad010-137">Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ad010-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="ad010-138">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad010-138">Security management</span></span>

  <span data-ttu-id="ad010-139">Monitorare la postura di sicurezza ed essere in grado di rilevare le minacce in tempo reale ed intervenire tempestivamente.</span><span class="sxs-lookup"><span data-stu-id="ad010-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="ad010-140">Accesso remoto e mobile e partner commerciali:</span><span class="sxs-lookup"><span data-stu-id="ad010-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="ad010-141">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="ad010-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="ad010-142">Introdurre il BYOD e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto delle applicazioni e protezione dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="ad010-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="ad010-143">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="ad010-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="ad010-144">Ridurre i costi relativi a manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando sul cloud le risorse a cui si accede normalmente.</span><span class="sxs-lookup"><span data-stu-id="ad010-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="ad010-145">Fornire migliore connettività e ridurre le spese per le transazioni Business-to-Business (B2B)</span><span class="sxs-lookup"><span data-stu-id="ad010-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="ad010-146">Sostituire l’extranet per i partner obsoleta e costosa con una soluzione basata su cloud che utilizzi l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="ad010-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="ad010-147">Conformità:</span><span class="sxs-lookup"><span data-stu-id="ad010-147">Compliance:</span></span>

- <span data-ttu-id="ad010-148">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="ad010-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="ad010-149">Essere conformi alle normative applicabili per la conservazione dei dati, la crittografia, la tutela della privacy dei dati e alle normative relative al trattamento dei dati personali, ad esempio il Regolamento generale sulla protezione dei dati (GDPR) per l'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="ad010-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="ad010-150">Gestione:</span><span class="sxs-lookup"><span data-stu-id="ad010-150">Management:</span></span>

- <span data-ttu-id="ad010-151">Ridurre la spesa IT per la gestione del software dei computer e dei dispositivi client</span><span class="sxs-lookup"><span data-stu-id="ad010-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="ad010-152">Automatizzare l'installazione degli aggiornamenti del sistema operativo Windows e Microsoft Office ProPlus nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad010-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="ad010-153">Tabella delle esigenze di business di Contoso rispetto alle funzionalità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ad010-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ad010-154">Il reparto IT di Contoso ha associato le esigenze di business alle funzionalità di Microsoft 365 Enterprise E5 prima dell'implementazione in questa tabella:</span><span class="sxs-lookup"><span data-stu-id="ad010-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="ad010-155">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="ad010-155">**Category**</span></span> | <span data-ttu-id="ad010-156">**Esigenza di business**</span><span class="sxs-lookup"><span data-stu-id="ad010-156">**Business need**</span></span> | <span data-ttu-id="ad010-157">**Prodotti o funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="ad010-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="ad010-158">Produttività</span><span class="sxs-lookup"><span data-stu-id="ad010-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="ad010-159">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="ad010-159">Make collaboration easier</span></span> | <span data-ttu-id="ad010-160">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="ad010-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="ad010-161">Migliorare la produttività per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="ad010-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="ad010-162">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad010-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ad010-163">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="ad010-163">Increase creativity and innovation</span></span> | <span data-ttu-id="ad010-164">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ad010-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="ad010-165">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad010-165">Security</span></span> |  |  |
|  | <span data-ttu-id="ad010-166">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="ad010-166">Identity & access management</span></span> | <span data-ttu-id="ad010-167">Account di amministratore globali dedicati con Azure Multi-Factor Authentication (MFA) e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="ad010-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="ad010-168">MFA per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="ad010-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="ad010-169">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="ad010-169">Conditional access</span></span> <BR> <span data-ttu-id="ad010-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="ad010-170">Windows Hello</span></span> <BR> <span data-ttu-id="ad010-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="ad010-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="ad010-172">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ad010-172">Threat protection</span></span> | <span data-ttu-id="ad010-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="ad010-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="ad010-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ad010-174">Windows Defender</span></span> <BR> <span data-ttu-id="ad010-175">Protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ad010-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="ad010-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ad010-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="ad010-177">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="ad010-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="ad010-178">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="ad010-178">Information protection</span></span> | <span data-ttu-id="ad010-179">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ad010-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="ad010-180">Prevenzione perdita di dati (DLP) di Office 365</span><span class="sxs-lookup"><span data-stu-id="ad010-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="ad010-181">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="ad010-181">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="ad010-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad010-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="ad010-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ad010-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ad010-184">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ad010-184">Security management</span></span> | <span data-ttu-id="ad010-185">Centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="ad010-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="ad010-186">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="ad010-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="ad010-187">Accesso remoto e mobile e partner commerciali</span><span class="sxs-lookup"><span data-stu-id="ad010-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="ad010-188">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="ad010-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="ad010-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ad010-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ad010-190">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="ad010-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="ad010-191">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad010-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ad010-192">Fornire migliore connettività e ridurre le spese per le transazioni B2B</span><span class="sxs-lookup"><span data-stu-id="ad010-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="ad010-193">Autenticazione federata e risorse basate su cloud</span><span class="sxs-lookup"><span data-stu-id="ad010-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="ad010-194">Conformità</span><span class="sxs-lookup"><span data-stu-id="ad010-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="ad010-195">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="ad010-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="ad010-196">Funzionalità per il GDPR in Office 365</span><span class="sxs-lookup"><span data-stu-id="ad010-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="ad010-197">Gestione</span><span class="sxs-lookup"><span data-stu-id="ad010-197">Management</span></span> |  |  |
|  | <span data-ttu-id="ad010-198">Ridurre la spesa IT per installare gli aggiornamenti del client</span><span class="sxs-lookup"><span data-stu-id="ad010-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="ad010-199">Anelli di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ad010-199">Deployment rings</span></span> <BR> <span data-ttu-id="ad010-200">Aggiornamenti di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ad010-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="ad010-201">Aggiornamenti di Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="ad010-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="ad010-202">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ad010-202">Next step</span></span>

<span data-ttu-id="ad010-203">[Informazioni](contoso-networking.md) sulla rete locale dell'azienda Contoso e come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad010-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad010-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad010-204">See also</span></span>

[<span data-ttu-id="ad010-205">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="ad010-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ad010-206">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="ad010-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
