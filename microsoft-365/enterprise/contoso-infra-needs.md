---
title: Infrastruttura IT ed esigenze di business di Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo Microsoft 365 Enterprise può soddisfarne le esigenze di business.
ms.openlocfilehash: a4a86c56f956361e58730f328ef940a627370ea6
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353132"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="b600d-103">Infrastruttura IT ed esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="b600d-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="b600d-104">**Riepilogo:** comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo Microsoft 365 Enterprise può soddisfarne le esigenze di business.</span><span class="sxs-lookup"><span data-stu-id="b600d-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="b600d-105">Contoso sta cambiando la propria infrastruttura IT da un modello centralizzato locale a un'infrastruttura comprensiva di cloud che gestisce carichi di lavoro di produttività personale e applicazioni basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="b600d-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="b600d-106">Infrastruttura IT esistente di Contoso</span><span class="sxs-lookup"><span data-stu-id="b600d-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="b600d-107">Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="b600d-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="b600d-108">La Figura 1 mostra l'ufficio di una sede con centri dati delle applicazioni, una rete perimetrale e Internet.</span><span class="sxs-lookup"><span data-stu-id="b600d-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="b600d-109">**Figura 1: Infrastruttura IT esistente di Contoso**</span><span class="sxs-lookup"><span data-stu-id="b600d-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="b600d-110">I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b600d-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="b600d-111">Applicazioni line of business personalizzate che utilizzano SQL Server e altri database Linux.</span><span class="sxs-lookup"><span data-stu-id="b600d-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="b600d-112">Un set di server SharePoint legacy.</span><span class="sxs-lookup"><span data-stu-id="b600d-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="b600d-113">Server a livello di organizzazione e di team per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="b600d-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="b600d-p101">Inoltre, ogni sede centrale (hub) regionale che supporta un gruppo di server con un insieme di applicazioni simile. Questi server vengono controllati dai dipartimenti IT regionali.</span><span class="sxs-lookup"><span data-stu-id="b600d-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="b600d-116">La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.</span><span class="sxs-lookup"><span data-stu-id="b600d-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="b600d-117">Nella rete perimetrale degli uffici di Contoso, gruppi di server forniscono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b600d-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="b600d-118">Accesso remoto basato su VPN all’intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="b600d-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="b600d-119">Hosting del sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, materiali o assistenza.</span><span class="sxs-lookup"><span data-stu-id="b600d-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="b600d-120">Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.</span><span class="sxs-lookup"><span data-stu-id="b600d-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="b600d-121">Esigenze di business di Contoso</span><span class="sxs-lookup"><span data-stu-id="b600d-121">Contoso's business needs</span></span>

<span data-ttu-id="b600d-122">Le esigenze di business di Contoso rientrano in cinque categorie principali.</span><span class="sxs-lookup"><span data-stu-id="b600d-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="b600d-123">Produttività:</span><span class="sxs-lookup"><span data-stu-id="b600d-123">Productivity:</span></span>

- <span data-ttu-id="b600d-124">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="b600d-124">Make collaboration easier</span></span>

  <span data-ttu-id="b600d-125">Sostituire il modello di collaborazione basato su posta elettronica e scambio di file con un modello online che consente di apportare modifiche in tempo reale ai documenti, partecipare a riunioni online e tenere traccia delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="b600d-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="b600d-126">Migliorare la produttività per utenti remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="b600d-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="b600d-127">Dato il numero elevato di utenti che lavorano da casa o sul campo, è preferibile sostituire la soluzione VPN caratterizzata da colli di bottiglia con un accesso ai dati e alle risorse di Contoso nel cloud che sia in grado di garantire prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="b600d-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="b600d-128">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="b600d-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="b600d-129">Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.</span><span class="sxs-lookup"><span data-stu-id="b600d-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="b600d-130">Sicurezza:</span><span class="sxs-lookup"><span data-stu-id="b600d-130">Security:</span></span>

- <span data-ttu-id="b600d-131">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="b600d-131">Identity and access management</span></span>

  <span data-ttu-id="b600d-132">Applicare l'autenticazione a più fattori e altre forme di autenticazione e proteggere le credenziali dell'account di utenti e amministratori.</span><span class="sxs-lookup"><span data-stu-id="b600d-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="b600d-133">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="b600d-133">Threat protection</span></span>

  <span data-ttu-id="b600d-134">Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b600d-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="b600d-135">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="b600d-135">Information protection</span></span>

  <span data-ttu-id="b600d-136">Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="b600d-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="b600d-137">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="b600d-137">Security management</span></span>

  <span data-ttu-id="b600d-138">Monitorare la postura di sicurezza ed essere in grado di rilevare le minacce in tempo reale ed intervenire tempestivamente.</span><span class="sxs-lookup"><span data-stu-id="b600d-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="b600d-139">Accesso remoto e mobile e partner commerciali:</span><span class="sxs-lookup"><span data-stu-id="b600d-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="b600d-140">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="b600d-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="b600d-141">Introdurre il BYOD e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto delle applicazioni e protezione dei dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="b600d-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="b600d-142">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="b600d-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="b600d-143">Ridurre i costi relativi a manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando sul cloud le risorse a cui si accede normalmente.</span><span class="sxs-lookup"><span data-stu-id="b600d-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="b600d-144">Fornire migliore connettività e ridurre le spese per le transazioni Business-to-Business (B2B)</span><span class="sxs-lookup"><span data-stu-id="b600d-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="b600d-145">Sostituire l’extranet per i partner obsoleta e costosa con una soluzione basata su cloud che utilizzi l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="b600d-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="b600d-146">Conformità:</span><span class="sxs-lookup"><span data-stu-id="b600d-146">Compliance:</span></span>

- <span data-ttu-id="b600d-147">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="b600d-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="b600d-148">Essere conformi alle normative applicabili per la conservazione dei dati, la crittografia, la tutela della privacy dei dati e alle normative relative al trattamento dei dati personali, ad esempio il Regolamento generale sulla protezione dei dati (GDPR) per l'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="b600d-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="b600d-149">Gestione:</span><span class="sxs-lookup"><span data-stu-id="b600d-149">Management:</span></span>

- <span data-ttu-id="b600d-150">Ridurre la spesa IT per la gestione del software dei computer e dei dispositivi client</span><span class="sxs-lookup"><span data-stu-id="b600d-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="b600d-151">Automatizzare l'installazione degli aggiornamenti del sistema operativo Windows e Microsoft Office nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b600d-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="b600d-152">Tabella delle esigenze di business di Contoso rispetto alle funzionalità di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b600d-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b600d-153">Il reparto IT di Contoso ha associato le esigenze di business alle funzionalità di Microsoft 365 Enterprise E5 prima dell'implementazione in questa tabella:</span><span class="sxs-lookup"><span data-stu-id="b600d-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="b600d-154">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="b600d-154">**Category**</span></span> | <span data-ttu-id="b600d-155">**Esigenza di business**</span><span class="sxs-lookup"><span data-stu-id="b600d-155">**Business need**</span></span> | <span data-ttu-id="b600d-156">**Prodotti o funzionalità di Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="b600d-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="b600d-157">Produttività</span><span class="sxs-lookup"><span data-stu-id="b600d-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="b600d-158">Semplificare la collaborazione</span><span class="sxs-lookup"><span data-stu-id="b600d-158">Make collaboration easier</span></span> | <span data-ttu-id="b600d-159">Teams, SharePoint Online, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b600d-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="b600d-160">Migliorare la produttività per utenti remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="b600d-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="b600d-161">Carichi di lavoro e dati sul cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="b600d-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b600d-162">Favorire la creatività e l'innovazione</span><span class="sxs-lookup"><span data-stu-id="b600d-162">Increase creativity and innovation</span></span> | <span data-ttu-id="b600d-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b600d-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="b600d-164">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b600d-164">Security</span></span> |  |  |
|  | <span data-ttu-id="b600d-165">Gestione di identità e accesso</span><span class="sxs-lookup"><span data-stu-id="b600d-165">Identity & access management</span></span> | <span data-ttu-id="b600d-166">Account dedicati per gli amministratore globali con MFA (Multi-factor authentication) e Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="b600d-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="b600d-167">MFA per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="b600d-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="b600d-168">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="b600d-168">Conditional access</span></span> <BR> <span data-ttu-id="b600d-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b600d-169">Windows Hello</span></span> <BR> <span data-ttu-id="b600d-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="b600d-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="b600d-171">Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="b600d-171">Threat protection</span></span> | <span data-ttu-id="b600d-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="b600d-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="b600d-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b600d-173">Windows Defender</span></span> <BR> <span data-ttu-id="b600d-174">Protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="b600d-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b600d-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b600d-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b600d-176">Analisi delle minacce e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="b600d-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="b600d-177">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="b600d-177">Information protection</span></span> | <span data-ttu-id="b600d-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b600d-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="b600d-179">Prevenzione perdita di dati (DLP) di Office 365</span><span class="sxs-lookup"><span data-stu-id="b600d-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="b600d-180">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="b600d-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="b600d-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b600d-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="b600d-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b600d-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b600d-183">Gestione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="b600d-183">Security management</span></span> | <span data-ttu-id="b600d-184">Centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="b600d-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="b600d-185">Windows Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="b600d-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="b600d-186">Accesso remoto e mobile e partner commerciali</span><span class="sxs-lookup"><span data-stu-id="b600d-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="b600d-187">Migliorare la sicurezza per lavoratori remoti e mobili</span><span class="sxs-lookup"><span data-stu-id="b600d-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="b600d-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b600d-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b600d-189">Ridurre l'infrastruttura di accesso remoto per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="b600d-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="b600d-190">Carichi di lavoro e dati sul cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="b600d-190">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b600d-191">Fornire migliore connettività e ridurre le spese per le transazioni B2B</span><span class="sxs-lookup"><span data-stu-id="b600d-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="b600d-192">Autenticazione federata e risorse basate su cloud</span><span class="sxs-lookup"><span data-stu-id="b600d-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="b600d-193">Conformità</span><span class="sxs-lookup"><span data-stu-id="b600d-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="b600d-194">Rispettare i requisiti normativi applicabili</span><span class="sxs-lookup"><span data-stu-id="b600d-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="b600d-195">Funzionalità per il GDPR in Office 365</span><span class="sxs-lookup"><span data-stu-id="b600d-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="b600d-196">Gestione</span><span class="sxs-lookup"><span data-stu-id="b600d-196">Management</span></span> |  |  |
|  | <span data-ttu-id="b600d-197">Ridurre la spesa IT per installare gli aggiornamenti del client</span><span class="sxs-lookup"><span data-stu-id="b600d-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="b600d-198">Anelli di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b600d-198">Deployment rings</span></span> <BR> <span data-ttu-id="b600d-199">Aggiornamento sul posto a Windows 10 e Autopilot</span><span class="sxs-lookup"><span data-stu-id="b600d-199">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="b600d-200">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="b600d-200">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="b600d-201">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b600d-201">Next step</span></span>

<span data-ttu-id="b600d-202">[Informazioni](contoso-networking.md) sulla rete locale dell'azienda Contoso e come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b600d-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b600d-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b600d-203">See also</span></span>

[<span data-ttu-id="b600d-204">Guida all'implementazione</span><span class="sxs-lookup"><span data-stu-id="b600d-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b600d-205">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="b600d-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
