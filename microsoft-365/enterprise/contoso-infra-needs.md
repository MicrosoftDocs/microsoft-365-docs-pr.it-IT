---
title: Infrastruttura IT ed esigenze di business di Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3cee0f3e6cd20b0d93038595cdab9270c8eb30aa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068388"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="74514-103">Infrastruttura IT ed esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="74514-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="74514-104">Contoso sta cambiando la propria infrastruttura IT da un modello centralizzato locale a un'infrastruttura comprensiva di cloud che gestisce carichi di lavoro di produttività personale e applicazioni basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="74514-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="74514-105">Infrastruttura IT esistente di Contoso</span><span class="sxs-lookup"><span data-stu-id="74514-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="74514-106">Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="74514-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="74514-107">La Figura 1 mostra l'ufficio di una sede con centri dati delle applicazioni, una rete perimetrale e Internet.</span><span class="sxs-lookup"><span data-stu-id="74514-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Infrastruttura IT esistente di Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="74514-109">**Figura 1: Infrastruttura IT esistente di Contoso**</span><span class="sxs-lookup"><span data-stu-id="74514-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="74514-110">I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="74514-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="74514-111">Applicazioni line of business personalizzate che utilizzano SQL Server e altri database Linux.</span><span class="sxs-lookup"><span data-stu-id="74514-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="74514-112">Un set di server SharePoint legacy.</span><span class="sxs-lookup"><span data-stu-id="74514-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="74514-113">Server a livello di organizzazione e di team per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="74514-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="74514-114">Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo.</span><span class="sxs-lookup"><span data-stu-id="74514-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="74514-115">Questi server sono sotto il controllo dei reparti IT regionali.</span><span class="sxs-lookup"><span data-stu-id="74514-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="74514-116">La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.</span><span class="sxs-lookup"><span data-stu-id="74514-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="74514-117">Nella rete perimetrale degli uffici di Contoso, gruppi di server forniscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74514-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="74514-118">Hosting del sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, materiali o assistenza.</span><span class="sxs-lookup"><span data-stu-id="74514-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="74514-119">Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.</span><span class="sxs-lookup"><span data-stu-id="74514-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="74514-120">Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="74514-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="74514-121">Esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="74514-121">Contoso's business needs</span></span>

<span data-ttu-id="74514-122">Le esigenze di business di Contoso rientrano in cinque categorie principali.</span><span class="sxs-lookup"><span data-stu-id="74514-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="74514-123">Produttività:</span><span class="sxs-lookup"><span data-stu-id="74514-123">Productivity:</span></span>

- <span data-ttu-id="74514-124">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="74514-124">Make collaboration easier</span></span>

  <span data-ttu-id="74514-125">Sostituire il modello di collaborazione basato su posta elettronica e scambio di file con un modello online che consente di apportare modifiche in tempo reale ai documenti, partecipare a riunioni online e tenere traccia delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="74514-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="74514-126">Migliorare la produttività per utenti remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="74514-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="74514-127">Dato il numero elevato di utenti che lavorano da casa o sul campo, è preferibile sostituire la soluzione VPN caratterizzata da colli di bottiglia con un accesso ai dati e alle risorse di Contoso nel cloud che sia in grado di garantire prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="74514-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="74514-128">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="74514-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="74514-129">Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.</span><span class="sxs-lookup"><span data-stu-id="74514-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="74514-130">Sicurezza:</span><span class="sxs-lookup"><span data-stu-id="74514-130">Security:</span></span>

- <span data-ttu-id="74514-131">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="74514-131">Identity and access management</span></span>

  <span data-ttu-id="74514-132">Applicare l'autenticazione a più fattori e altre forme di autenticazione e proteggere le credenziali dell'account di utenti e amministratori.</span><span class="sxs-lookup"><span data-stu-id="74514-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="74514-133">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="74514-133">Threat protection</span></span>

  <span data-ttu-id="74514-134">Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="74514-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="74514-135">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="74514-135">Information protection</span></span>

  <span data-ttu-id="74514-136">Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="74514-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="74514-137">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="74514-137">Security management</span></span>

  <span data-ttu-id="74514-138">Monitorare la postura di sicurezza ed essere in grado di rilevare le minacce in tempo reale ed intervenire tempestivamente.</span><span class="sxs-lookup"><span data-stu-id="74514-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="74514-139">Accesso remoto e mobile e partner commerciali:</span><span class="sxs-lookup"><span data-stu-id="74514-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="74514-140">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="74514-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="74514-141">Introdurre il BYOD e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto delle applicazioni e protezione dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="74514-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="74514-142">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="74514-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="74514-143">Ridurre i costi relativi a manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando sul cloud le risorse a cui si accede normalmente.</span><span class="sxs-lookup"><span data-stu-id="74514-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="74514-144">Fornire migliore connettività e ridurre le spese per le transazioni Business-to-Business (B2B)</span><span class="sxs-lookup"><span data-stu-id="74514-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="74514-145">Sostituire l’extranet per i partner obsoleta e costosa con una soluzione basata su cloud che utilizzi l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="74514-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="74514-146">Conformità:</span><span class="sxs-lookup"><span data-stu-id="74514-146">Compliance:</span></span>

- <span data-ttu-id="74514-147">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="74514-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="74514-148">Essere conformi alle normative applicabili per la conservazione dei dati, la crittografia, la tutela della privacy dei dati e alle normative relative al trattamento dei dati personali, ad esempio il Regolamento generale sulla protezione dei dati (GDPR) per l'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="74514-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="74514-149">Gestione:</span><span class="sxs-lookup"><span data-stu-id="74514-149">Management:</span></span>

- <span data-ttu-id="74514-150">Ridurre la spesa IT per la gestione del software dei computer e dei dispositivi client</span><span class="sxs-lookup"><span data-stu-id="74514-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="74514-151">Automatizzare l'installazione degli aggiornamenti del sistema operativo Windows e Microsoft Office ProPlus nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="74514-151">Automate the installation of updates to the Windows operating system and Microsoft Office ProPlus across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="74514-152">Tabella delle esigenze di business di Contoso rispetto alle funzionalità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74514-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="74514-153">Il reparto IT di Contoso ha associato le esigenze di business alle funzionalità di Microsoft 365 E5 prima dell'implementazione in questa tabella:</span><span class="sxs-lookup"><span data-stu-id="74514-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="74514-154">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="74514-154">**Category**</span></span> | <span data-ttu-id="74514-155">**Esigenza di business**</span><span class="sxs-lookup"><span data-stu-id="74514-155">**Business need**</span></span> | <span data-ttu-id="74514-156">**Prodotti o funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="74514-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="74514-157">Produttività</span><span class="sxs-lookup"><span data-stu-id="74514-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="74514-158">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="74514-158">Make collaboration easier</span></span> | <span data-ttu-id="74514-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="74514-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="74514-160">Migliorare la produttività per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="74514-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="74514-161">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74514-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="74514-162">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="74514-162">Increase creativity and innovation</span></span> | <span data-ttu-id="74514-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="74514-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="74514-164">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="74514-164">Security</span></span> |  |  |
|  | <span data-ttu-id="74514-165">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="74514-165">Identity & access management</span></span> | <span data-ttu-id="74514-166">Account di amministratore globali dedicati con Azure Multi-Factor Authentication (MFA) e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="74514-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="74514-167">MFA per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="74514-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="74514-168">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="74514-168">Conditional Access</span></span> <BR> <span data-ttu-id="74514-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="74514-169">Windows Hello</span></span> <BR> <span data-ttu-id="74514-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="74514-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="74514-171">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="74514-171">Threat protection</span></span> | <span data-ttu-id="74514-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="74514-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="74514-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="74514-173">Windows Defender</span></span> <BR> <span data-ttu-id="74514-174">Protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="74514-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="74514-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="74514-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="74514-176">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="74514-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="74514-177">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="74514-177">Information protection</span></span> | <span data-ttu-id="74514-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="74514-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="74514-179">Prevenzione perdita di dati (DLP) di Office 365</span><span class="sxs-lookup"><span data-stu-id="74514-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="74514-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="74514-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="74514-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74514-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="74514-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="74514-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="74514-183">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="74514-183">Security management</span></span> | <span data-ttu-id="74514-184">Centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="74514-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="74514-185">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="74514-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="74514-186">Accesso remoto e mobile e partner commerciali</span><span class="sxs-lookup"><span data-stu-id="74514-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="74514-187">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="74514-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="74514-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="74514-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="74514-189">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="74514-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="74514-190">Carichi di lavoro e dati basati sul cloud di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74514-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="74514-191">Fornire migliore connettività e ridurre le spese per le transazioni B2B</span><span class="sxs-lookup"><span data-stu-id="74514-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="74514-192">Autenticazione federata e risorse basate su cloud</span><span class="sxs-lookup"><span data-stu-id="74514-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="74514-193">Conformità</span><span class="sxs-lookup"><span data-stu-id="74514-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="74514-194">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="74514-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="74514-195">Funzionalità per il GDPR in Office 365</span><span class="sxs-lookup"><span data-stu-id="74514-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="74514-196">Gestione</span><span class="sxs-lookup"><span data-stu-id="74514-196">Management</span></span> |  |  |
|  | <span data-ttu-id="74514-197">Ridurre la spesa IT per installare gli aggiornamenti del client</span><span class="sxs-lookup"><span data-stu-id="74514-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="74514-198">Anelli di distribuzione</span><span class="sxs-lookup"><span data-stu-id="74514-198">Deployment rings</span></span> <BR> <span data-ttu-id="74514-199">Aggiornamenti di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74514-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="74514-200">Aggiornamenti di Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="74514-200">Office 365 ProPlus updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="74514-201">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="74514-201">Next step</span></span>

<span data-ttu-id="74514-202">[Informazioni](contoso-networking.md) sulla rete locale dell'azienda Contoso e come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74514-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="74514-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74514-203">See also</span></span>

[<span data-ttu-id="74514-204">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="74514-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="74514-205">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="74514-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
