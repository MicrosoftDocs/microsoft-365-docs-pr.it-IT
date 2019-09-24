---
title: Infrastruttura di base di Microsoft 365 Enterprise per organizzazioni non aziendali
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Esame delle fasi semplificate dell'infrastruttura di base per Microsoft 365 Enterprise per organizzazioni non aziendali.
ms.openlocfilehash: 37bbf04eafeb3adc63d9dd01d052376f98856df4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071735"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="610e0-103">Infrastruttura di base di Microsoft 365 Enterprise per organizzazioni non aziendali</span><span class="sxs-lookup"><span data-stu-id="610e0-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="610e0-104">Anche le organizzazioni non aziendali possono distribuire Microsoft 365 Enterprise e sfruttare in termini di business il valore di un'infrastruttura integrata e protetta che abilita il lavoro in team e libera la creatività.</span><span class="sxs-lookup"><span data-stu-id="610e0-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="610e0-105">Un'organizzazione non aziendale è in genere costituita da:</span><span class="sxs-lookup"><span data-stu-id="610e0-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="610e0-106">Numero ridotto di infrastrutture IT locali, ad esempio server di posta elettronica e file server e un dominio di Active Directory Domain Services (AD DS) o persino nessuna infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="610e0-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="610e0-107">Personale IT ridotto, in buona parte generico e non specializzato in una tecnologia o un carico di lavoro specifico, come la rete o la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="610e0-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="610e0-108">L'offerta Microsoft per le organizzazioni non aziendali di piccole dimensioni è [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="610e0-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="610e0-109">In alcuni casi può però essere necessario implementare Microsoft 365 Enterprise, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="610e0-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="610e0-110">Per l'organizzazione sono o saranno necessarie più di 300 licenze di Microsoft 365, che rappresentano il numero massimo di licenze gestibili per Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="610e0-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="610e0-111">L'organizzazione necessita di funzionalità di produttività, voce, sicurezza e analisi avanzate non disponibili con Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="610e0-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="610e0-112">Questo articolo analizza una distribuzione semplificata dell'infrastruttura di base di Microsoft 365 Enterprise adatta per le organizzazioni non aziendali.</span><span class="sxs-lookup"><span data-stu-id="610e0-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="610e0-113">Configurare l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="610e0-113">First, set up your subscription</span></span>

<span data-ttu-id="610e0-114">È necessario configurare i domini DNS (Domain Name System) per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="610e0-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="610e0-115">Se si ha un abbonamento a Office 365, questa operazione è già stata completata.</span><span class="sxs-lookup"><span data-stu-id="610e0-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="610e0-116">In caso contrario, seguire le istruzioni in [Aggiungere un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="610e0-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="610e0-117">In seguito, è necessario configurare la sicurezza aggiuntiva per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="610e0-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="610e0-118">Seguire le istruzioni in [Configurare il tenant di Office 365 per una maggiore sicurezza](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="610e0-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="610e0-119">Fase 1: Funzionalità di rete</span><span class="sxs-lookup"><span data-stu-id="610e0-119">Phase 1: Networking</span></span>

<span data-ttu-id="610e0-120">Le organizzazioni non aziendali dispongono in genere di connessioni a Internet locali in ogni ufficio e non usano server proxy, firewall o dispositivi di controllo dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="610e0-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="610e0-121">Il provider di servizi Internet (ISP) a servizio in ogni ufficio dispone di un server DNS locale a livello di area geografica, di conseguenza il traffico viene reindirizzato al percorso di rete di Microsoft 365 più vicini agli uffici e agli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="610e0-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="610e0-122">È quindi necessario solo verificare con l'ISP che la connessione in ogni ufficio:</span><span class="sxs-lookup"><span data-stu-id="610e0-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="610e0-123">Usi un server DNS locale a livello di area geografica.</span><span class="sxs-lookup"><span data-stu-id="610e0-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="610e0-124">Sia adeguata per le esigenze attuali e future, quando gli utenti inizieranno a usare altri servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="610e0-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="610e0-125">Se si usano server proxy, firewall o dispositivi di controllo dei pacchetti, per altre [informazioni, vedere infrastruttura di rete](networking-infrastructure.md) per Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-126">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-126">Your configuration so far</span></span>

<span data-ttu-id="610e0-127">Ecco una grafica riepilogativa in cui è evidenziato l'elemento della fase 1.</span><span class="sxs-lookup"><span data-stu-id="610e0-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="610e0-128">La dicitura **Organizzazione** può corrispondere a più uffici, ognuno dei quali dispone di una connessione Internet locale con un ISP che usa un server DNS locale a livello di area geografica.</span><span class="sxs-lookup"><span data-stu-id="610e0-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="610e0-129">Grazie all'ISP, gli utenti di ogni ufficio possono raggiungere il percorso di rete Microsoft 365 più vicino e le risorse dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="610e0-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="610e0-130">Fase 2: Identità</span><span class="sxs-lookup"><span data-stu-id="610e0-130">Phase 2: Identity</span></span>

<span data-ttu-id="610e0-131">Ogni dipendente dell'organizzazione deve essere in grado di eseguire l'accesso. Per tale operazione è richiesto un account utente nel tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="610e0-132">Si usano quindi i gruppi per contenere gli account utente e altri gruppi per comunicare o accedere alle risorse autorizzate, ad esempio un sito di SharePoint Online o un team.</span><span class="sxs-lookup"><span data-stu-id="610e0-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="610e0-133">Account amministratore</span><span class="sxs-lookup"><span data-stu-id="610e0-133">Administrator accounts</span></span>

<span data-ttu-id="610e0-134">Per proteggere gli account utente di amministratore globale, richiedere password complesse e l'autenticazione a più fattori (MFA).</span><span class="sxs-lookup"><span data-stu-id="610e0-134">Protect your global administrator user accounts by requiring strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="610e0-135">Per altre informazioni, vedere [Proteggere gli account amministratore globale](identity-create-protect-global-admins.md#protect-global-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="610e0-135">See [Protect your Office 365 global administrator accounts](identity-create-protect-global-admins.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="610e0-136">Se l'organizzazione richiede una sicurezza elevata e si dispone di Microsoft 365 Enterprise E5, usare Azure AD Privileged Identity Management per abilitare l'accesso come amministratore just-in-time.</span><span class="sxs-lookup"><span data-stu-id="610e0-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="610e0-137">Per altre informazioni, vedere [Configurare gli amministratori globali su richiesta](identity-create-protect-global-admins.md#identity-pim).</span><span class="sxs-lookup"><span data-stu-id="610e0-137">See [Set up on-demand global administrators](identity-create-protect-global-admins.md#identity-pim) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="610e0-138">Consigli per i gruppi</span><span class="sxs-lookup"><span data-stu-id="610e0-138">Recommendations for groups</span></span>

<span data-ttu-id="610e0-139">Se si dispone di un dominio di AD DS locale, continuare a usare i gruppi di Microsoft 365 Enterprise come gruppi in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="610e0-140">Se non si dispone di un dominio di AD DS locale, creare gruppi di sicurezza in Azure AD con questi livelli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="610e0-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="610e0-141">Livello di protezione</span><span class="sxs-lookup"><span data-stu-id="610e0-141">Security level</span></span> | <span data-ttu-id="610e0-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="610e0-142">Description</span></span> | <span data-ttu-id="610e0-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="610e0-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="610e0-144">Di base</span><span class="sxs-lookup"><span data-stu-id="610e0-144">Baseline</span></span> | <span data-ttu-id="610e0-145">Si tratta di uno standard minimo predefinito per la protezione dei dati, delle identità e dei dispositivi che accedono ai dati.</span><span class="sxs-lookup"><span data-stu-id="610e0-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="610e0-146">È adatto, in genere, alla maggior parte dei dati dell'organizzazione gestiti dalla maggior parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="610e0-147">Gruppi per gli operatori sul campo, che operano ad esempio nel settore vendite, marketing, assistenza clienti, amministrazione e produzione.</span><span class="sxs-lookup"><span data-stu-id="610e0-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="610e0-148">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="610e0-148">Sensitive</span></span> | <span data-ttu-id="610e0-149">Si tratta di un livello di protezione aggiuntivo per un sottoinsieme di dati che richiedono un livello di protezione ulteriore rispetto a quello di base.</span><span class="sxs-lookup"><span data-stu-id="610e0-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="610e0-150">Questi gruppi includono utenti che usano e creano dati riservati specifici di reparti e progetti e che non devono essere disponibili per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="610e0-151">Team di prodotto o marketing che sviluppano prodotti futuri</span><span class="sxs-lookup"><span data-stu-id="610e0-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="610e0-152">Riservatezza elevata</span><span class="sxs-lookup"><span data-stu-id="610e0-152">Highly regulated</span></span> | <span data-ttu-id="610e0-153">Si tratta del livello di protezione più elevato per una quantità generalmente ridotta di dati classificati come altamente riservati, considerati come proprietà intellettuale o segreti commerciali, oppure per dati soggetti al rispetto di normative di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="610e0-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="610e0-154">Team di ricerca, legale, finanziario o team che archiviano o usano i dati di clienti o partner.</span><span class="sxs-lookup"><span data-stu-id="610e0-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="610e0-155">Identità ibrida</span><span class="sxs-lookup"><span data-stu-id="610e0-155">Hybrid identity</span></span>

<span data-ttu-id="610e0-156">Se si ha un dominio di Active Directory locale, è necessario sincronizzare il set di account utente, gruppi e contatti del dominio con il tenant di Azure AD dell'abbonamento a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="610e0-157">Per un’organizzazione non aziendale, configurare Azure AD Connect in un server con sincronizzazione dell'hash delle password (PHS).</span><span class="sxs-lookup"><span data-stu-id="610e0-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="610e0-158">Per altre informazioni, vedere [Sincronizzare le identità](identity-add-user-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="610e0-158">See [Synchronize identities](identity-add-user-accounts.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="610e0-159">Accessi utente più sicuri con i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="610e0-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="610e0-160">Azure AD valuta le condizioni degli accessi utente e può usare i criteri di accesso condizionale per concedere o negare l'accesso, nonché imporre ulteriori azioni da eseguire per completare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="610e0-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="610e0-161">Ad esempio, se Azure AD stabilisce che l'accesso avviene in condizioni di rischio medio o elevato, può richiedere all'utente di eseguire l'autenticazione a più fattori per completare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="610e0-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="610e0-162">I criteri di accesso condizionale vengono applicati agli account utente o ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="610e0-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="610e0-163">Per facilitare l'assegnazione dei criteri di accesso condizionale, creare i gruppi di sicurezza di Azure AD seguenti nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="610e0-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="610e0-164">BASELINE</span><span class="sxs-lookup"><span data-stu-id="610e0-164">Baseline</span></span>

  <span data-ttu-id="610e0-165">Include i gruppi o gli account utente per gli utenti con accesso ai dati di base.</span><span class="sxs-lookup"><span data-stu-id="610e0-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="610e0-166">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="610e0-166">Sensitive</span></span>

  <span data-ttu-id="610e0-167">Include i gruppi o gli account utente per gli utenti con accesso ai dati riservati.</span><span class="sxs-lookup"><span data-stu-id="610e0-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="610e0-168">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="610e0-169">Include i gruppi o gli account utente per gli utenti con accesso ai dati con riservatezza elevata.</span><span class="sxs-lookup"><span data-stu-id="610e0-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="610e0-170">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="610e0-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="610e0-171">Gruppo vuoto da usare per escludere temporaneamente un utente dai criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="610e0-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="610e0-172">Ecco un elenco dei criteri di accesso condizionale di Azure AD da abilitare o creare.</span><span class="sxs-lookup"><span data-stu-id="610e0-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="610e0-173">Criterio di accesso condizionale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="610e0-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="610e0-174">Gruppi a cui si applica il criterio</span><span class="sxs-lookup"><span data-stu-id="610e0-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="610e0-175">Criterio di base: Richiedere l'autenticazione a più fattori per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="610e0-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="610e0-176">Questo criterio si applica ai ruoli amministratore, pertanto non è necessario specificare i gruppi.</span><span class="sxs-lookup"><span data-stu-id="610e0-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="610e0-177">Questo criterio deve solo essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="610e0-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="610e0-178">Tutti i criteri successivi devono essere creati e abilitati.</span><span class="sxs-lookup"><span data-stu-id="610e0-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="610e0-179">Bloccare i client che non supportano l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="610e0-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="610e0-180">Selezionare "Tutti gli utenti" nelle impostazioni di criteri.</span><span class="sxs-lookup"><span data-stu-id="610e0-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="610e0-181">Richiedere l'autenticazione a più fattori quando il rischio di accesso è considerato medio o elevato (richiede Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="610e0-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="610e0-182">BASELINE</span><span class="sxs-lookup"><span data-stu-id="610e0-182">Baseline</span></span> |
| <span data-ttu-id="610e0-183">Richiedere l'autenticazione a più fattori quando il rischio di accesso è considerato basso, medio o elevato (richiede Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="610e0-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="610e0-184">SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="610e0-184">Sensitive</span></span> |
| <span data-ttu-id="610e0-185">Richiedere sempre l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="610e0-185">Always require MFA</span></span> | <span data-ttu-id="610e0-186">HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-187">Richiedere app approvate in dispositivi iOS e Android</span><span class="sxs-lookup"><span data-stu-id="610e0-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="610e0-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-189">Richiedere computer conformi</span><span class="sxs-lookup"><span data-stu-id="610e0-189">Require compliant PCs</span></span> | <span data-ttu-id="610e0-190">BASELINE</span><span class="sxs-lookup"><span data-stu-id="610e0-190">Baseline</span></span> |
| <span data-ttu-id="610e0-191">Richiedere computer e dispositivi iOS e Android conformi</span><span class="sxs-lookup"><span data-stu-id="610e0-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="610e0-192">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="610e0-193">Ecco il criterio di rischio utente di Azure AD Identity Protection (richiede Microsoft 365 Enterprise E5) da creare e abilitare.</span><span class="sxs-lookup"><span data-stu-id="610e0-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="610e0-194">Criterio di rischio utente di Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="610e0-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="610e0-195">Gruppi a cui si applica il criterio</span><span class="sxs-lookup"><span data-stu-id="610e0-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="610e0-196">Gli utenti a rischio elevato devono modificare le password</span><span class="sxs-lookup"><span data-stu-id="610e0-196">High risk users must change passwords</span></span> | <span data-ttu-id="610e0-197">Selezionare "Tutti gli utenti" nelle impostazioni di criteri.</span><span class="sxs-lookup"><span data-stu-id="610e0-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="610e0-198">Per le istruzioni, vedere [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="610e0-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="610e0-199">Gruppi per facilitare la gestione</span><span class="sxs-lookup"><span data-stu-id="610e0-199">Groups for easier management</span></span>

<span data-ttu-id="610e0-200">Ecco alcune funzionalità che consentono di facilitare la gestione di gruppi e licenze.</span><span class="sxs-lookup"><span data-stu-id="610e0-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="610e0-201">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="610e0-201">Feature</span></span> | <span data-ttu-id="610e0-202">Uso</span><span class="sxs-lookup"><span data-stu-id="610e0-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="610e0-203">Gestione gruppi self-service</span><span class="sxs-lookup"><span data-stu-id="610e0-203">Self-service group management</span></span> | <span data-ttu-id="610e0-204">Consentire la gestione dei gruppi di Azure AD ai proprietari del gruppo anziché al personale IT.</span><span class="sxs-lookup"><span data-stu-id="610e0-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="610e0-205">Per altre informazioni, vedere [Gestione gruppi self-service](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups).</span><span class="sxs-lookup"><span data-stu-id="610e0-205">See [Self-service group management](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="610e0-206">Appartenenza a gruppi dinamici</span><span class="sxs-lookup"><span data-stu-id="610e0-206">Dynamic group membership</span></span> | <span data-ttu-id="610e0-207">Configurare l'aggiunta o la rimozione automatica degli account utente dai gruppi di Azure AD in base agli attributi dell'account utente, ad esempio il reparto o il paese.</span><span class="sxs-lookup"><span data-stu-id="610e0-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="610e0-208">Per altre informazioni, vedere [Appartenenza a gruppi dinamici](identity-use-group-management.md#set-up-dynamic-group-membership).</span><span class="sxs-lookup"><span data-stu-id="610e0-208">See [Dynamic group membership](identity-use-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="610e0-209">Licenze basate sui gruppi</span><span class="sxs-lookup"><span data-stu-id="610e0-209">Group-based licensing</span></span> | <span data-ttu-id="610e0-210">Usare l'appartenenza ai gruppi per assegnare o rimuovere automaticamente le licenze per gli account utente.</span><span class="sxs-lookup"><span data-stu-id="610e0-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="610e0-211">Per altre informazioni, vedere [Licenze basate sui gruppi](identity-use-group-management.md#set-up-automatic-licensing).</span><span class="sxs-lookup"><span data-stu-id="610e0-211">See [Group-based licensing](identity-use-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="610e0-212">Se si usano licenze basate sui gruppi, creare un gruppo denominato LICENSED che includerà i nomi degli account utente a cui è assegnata una licenza di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="610e0-213">Monitorare gli accessi utente</span><span class="sxs-lookup"><span data-stu-id="610e0-213">Monitor user access</span></span>

<span data-ttu-id="610e0-214">Se si dispone di Microsoft 365 Enterprise E5, è possibile usare Azure AD Identity Protection per monitorare e analizzare gli accessi utente e verificare se le credenziali sono state compromesse.</span><span class="sxs-lookup"><span data-stu-id="610e0-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="610e0-215">Per altre informazioni, vedere [Proteggere dalla compromissione delle credenziali](identity-secure-user-sign-ins.md#protect-against-credential-compromise).</span><span class="sxs-lookup"><span data-stu-id="610e0-215">See [Protect against credential compromise](identity-secure-user-sign-ins.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-216">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-216">Your configuration so far</span></span>

<span data-ttu-id="610e0-217">Ecco una grafica riepilogativa della fase Identità per l'identità ibrida in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="610e0-218">Gli elementi nuovi ed evidenziati della fase identità ibrida includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="610e0-219">Un dominio di AD DS locale con gruppi e account utente.</span><span class="sxs-lookup"><span data-stu-id="610e0-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="610e0-220">Un server basato su Windows che esegue Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="610e0-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="610e0-221">Il set sincronizzato di gruppi e account di AD DS in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="610e0-222">Impostazioni di Azure AD per l'autenticazione, per proteggere gli account globali e semplificare la gestione dei gruppi e delle licenze.</span><span class="sxs-lookup"><span data-stu-id="610e0-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="610e0-223">Criteri di accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="610e0-224">Ecco una grafica riepilogativa della fase identità solo cloud in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="610e0-225">Gli elementi nuovi ed evidenziati della fase solo cloud includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="610e0-226">Impostazioni di Azure AD per l'autenticazione, per proteggere gli account globali e semplificare la gestione dei gruppi e delle licenze.</span><span class="sxs-lookup"><span data-stu-id="610e0-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="610e0-227">Criteri di accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="610e0-228">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="610e0-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="610e0-229">Per assicurarsi che i dispositivi Windows 10 Enterprise vengano integrati nell'infrastruttura di identità e sicurezza di Microsoft 365, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="610e0-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="610e0-230">Ibrido (un dominio di AD DS locale non è disponibile)</span><span class="sxs-lookup"><span data-stu-id="610e0-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="610e0-231">Aggiungere al tenant di Azure AD ogni dispositivo Windows 10 Enterprise esistente già presente nel dominio di AD DS.</span><span class="sxs-lookup"><span data-stu-id="610e0-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="610e0-232">Per altre informazioni, vedere [Come configurare dispositivi aggiunti all'identità ibrida di Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="610e0-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="610e0-233">Aggiungere ogni nuovo dispositivo Windows 10 Enterprise al dominio di AD DS e al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="610e0-234">Registrare ogni dispositivo Windows 10 Enterprise per la gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="610e0-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="610e0-235">Vedere [Registrare un dispositivo di Windows 10 usando i Criteri di gruppo](https://go.microsoft.com/fwlink/p/?linkid=872871) per le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="610e0-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="610e0-236">Solo cloud (un dominio di AD DS locale non è disponibile)</span><span class="sxs-lookup"><span data-stu-id="610e0-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="610e0-237">Aggiungere ogni dispositivo Windows 10 Enterprise al tenant di Azure AD dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="610e0-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="610e0-238">Per altre informazioni, vedere [Aggiungere il dispositivo aziendale alla rete dell'organizzazione](https://docs.microsoft.com/it-IT/azure/active-directory/user-help/user-help-join-device-on-network).</span><span class="sxs-lookup"><span data-stu-id="610e0-238">See [Join your work device to your organization's network](https://docs.microsoft.com/it-IT/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="610e0-239">Dopo essere stato installato e aggiunto ogni dispositivo Windows 10 Enterprise installa automaticamente gli aggiornamenti per il servizio cloud Windows Update per le aziende.</span><span class="sxs-lookup"><span data-stu-id="610e0-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="610e0-240">In un'organizzazione non aziendale non è in genere necessario configurare un'infrastruttura per distribuire e installare gli aggiornamenti Windows 10.</span><span class="sxs-lookup"><span data-stu-id="610e0-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-241">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-241">Your configuration so far</span></span>

<span data-ttu-id="610e0-242">Ecco una grafica riepilogativa della fase Windows 10 Enterprise in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="610e0-243">Gli elementi nuovi ed evidenziati della fase Windows 10 Enterprise includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="610e0-244">Windows 10 Enterprise installato in dispositivi di Windows, con il portatile locale come esempio.</span><span class="sxs-lookup"><span data-stu-id="610e0-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="610e0-245">Centro servizi per contratti multilicenza, che fornisce le immagini per le nuove installazioni di Windows 10 Enterprise, e il servizio Windows Update per le aziende, che fornisce gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="610e0-246">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="610e0-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="610e0-247">Microsoft 365 Enterprise include Office 365 ProPlus, la versione in abbonamento di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="610e0-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="610e0-248">Come Office 2016 o Office 2019, Office 365 ProPlus viene installato direttamente nei dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="610e0-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="610e0-249">Office 365 ProPlus riceve però regolarmente gli aggiornamenti delle nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="610e0-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="610e0-250">Per altre informazioni, vedere [Informazioni su Office 365 ProPlus nell'azienda](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="610e0-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="610e0-251">Per l'organizzazione non aziendale, installare manualmente Office 365 ProPlus nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="610e0-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="610e0-252">Questa operazione può essere eseguita dall'amministratore durante la preparazione di un nuovo dispositivo per l'uso oppure dall'utente durante il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="610e0-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="610e0-253">In entrambi i casi, l'amministratore o l'utente accede al portale di Office 365 disponibile all'indirizzo https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="610e0-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="610e0-254">Nella scheda **Microsoft Office Home** fare clic su **Installa Office** ed eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="610e0-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="610e0-255">Gli aggiornamenti delle funzionalità di Office 365 ProPlus vengono scaricati ogni mese da ogni computer in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="610e0-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="610e0-256">In un'organizzazione non aziendale non è in genere necessario configurare un'infrastruttura per distribuire gli aggiornamenti di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="610e0-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-257">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-257">Your configuration so far</span></span>

<span data-ttu-id="610e0-258">Ecco una grafica riepilogativa della fase Office 365 ProPlus in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="610e0-259">Gli elementi nuovi ed evidenziati della fase Office 365 ProPlus includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="610e0-260">Office 365 ProPlus installato nei dispositivi, con un portatile locale come esempio.</span><span class="sxs-lookup"><span data-stu-id="610e0-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="610e0-261">Rete per la distribuzione di contenuti di Office (CDN) per Office 365 ProPlus, a cui i dispositivi accedono per scaricare gli aggiornamenti di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="610e0-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="610e0-262">Fase 5: Gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="610e0-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="610e0-263">Microsoft 365 Enterprise include Microsoft Intune per la gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="610e0-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="610e0-264">Con Intune è possibile gestire dispositivi Windows, iOS, Android e macOS per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati.</span><span class="sxs-lookup"><span data-stu-id="610e0-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="610e0-265">Intune usa gli account utente, del gruppo e del computer di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="610e0-266">Intune offre due tipi di gestione dei dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="610e0-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="610e0-267">La gestione dei dispositivi mobili (MDM) avviene quando i dispositivi vengono registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="610e0-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="610e0-268">Dopo la registrazione diventano dispositivi gestiti e possono ricevere i criteri, le regole e le impostazioni usate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="610e0-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="610e0-269">Questi tipi di dispositivi appartengono in genere all'organizzazione e vengono concessi ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="610e0-270">È possibile che gli utenti con dispositivi personali non vogliano registrare i propri dispositivi o consentirne la gestione in Intune con criteri e impostazioni dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="610e0-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="610e0-271">È comunque necessario proteggere le risorse e i dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="610e0-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="610e0-272">Per questo scenario è possibile proteggere le app con la gestione di applicazioni mobili (MAM).</span><span class="sxs-lookup"><span data-stu-id="610e0-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="610e0-273">I criteri di Intune consentono di attivare la conformità dei dispositivi e la protezione delle app.</span><span class="sxs-lookup"><span data-stu-id="610e0-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="610e0-274">Ecco l'elenco dei criteri di Intune da creare.</span><span class="sxs-lookup"><span data-stu-id="610e0-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="610e0-275">Criteri di Intune</span><span class="sxs-lookup"><span data-stu-id="610e0-275">Intune policies</span></span> | <span data-ttu-id="610e0-276">Gruppi a cui si applica il criterio</span><span class="sxs-lookup"><span data-stu-id="610e0-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="610e0-277">Criteri di conformità dei dispositivi per Windows</span><span class="sxs-lookup"><span data-stu-id="610e0-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="610e0-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-279">Criteri di conformità dei dispositivi per iOS</span><span class="sxs-lookup"><span data-stu-id="610e0-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="610e0-280">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-281">Conformità dei dispositivi per MacOS</span><span class="sxs-lookup"><span data-stu-id="610e0-281">Device compliance for macOS</span></span> | <span data-ttu-id="610e0-282">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-283">Criteri di conformità dei dispositivi per Android e Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="610e0-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="610e0-284">SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-285">Criteri di protezione delle app per iOS</span><span class="sxs-lookup"><span data-stu-id="610e0-285">App protection policy for iOS</span></span> | <span data-ttu-id="610e0-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-287">Criteri di protezione delle app per MacOS</span><span class="sxs-lookup"><span data-stu-id="610e0-287">App protection policy for macOS</span></span> | <span data-ttu-id="610e0-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="610e0-289">Criteri di protezione delle app per Android e Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="610e0-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="610e0-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span><span class="sxs-lookup"><span data-stu-id="610e0-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="610e0-291">Per le istruzioni, vedere [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="610e0-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-292">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-292">Your configuration so far</span></span>

<span data-ttu-id="610e0-293">Ecco una grafica riepilogativa della fase Gestione dei dispositivi mobili in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="610e0-294">Gli elementi nuovi ed evidenziati della fase Gestione dei dispositivi mobili includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="610e0-295">Dispositivi registrati in Intune, che mostrano un portatile locale che esegue Windows 10 Enterprise come esempio.</span><span class="sxs-lookup"><span data-stu-id="610e0-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="610e0-296">Criteri di Intune per la conformità dei dispositivi e la protezione delle app.</span><span class="sxs-lookup"><span data-stu-id="610e0-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="610e0-297">Fase 6: Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="610e0-297">Phase 6: Information protection</span></span>

<span data-ttu-id="610e0-298">Microsoft 365 Enterprise include numerose funzionalità di protezione delle informazioni che consentono di trattare in modo diverso le classificazioni dei dati applicando diversi livelli di governance, sicurezza e protezione.</span><span class="sxs-lookup"><span data-stu-id="610e0-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="610e0-299">Ad esempio, la normale corrispondenza tra la maggior parte dei dipendenti e i documenti a cui lavorano richiedono un determinato livello di base di protezione.</span><span class="sxs-lookup"><span data-stu-id="610e0-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="610e0-300">I record finanziari, i dati dei clienti e la proprietà intellettuale richiedono un livello di protezione superiore.</span><span class="sxs-lookup"><span data-stu-id="610e0-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="610e0-301">Il primo passo per una strategia di protezione delle informazioni consiste nel determinare i livelli di protezione.</span><span class="sxs-lookup"><span data-stu-id="610e0-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="610e0-302">Molte organizzazioni usano questi livelli, che vengono già usati per i criteri di accesso condizionale:</span><span class="sxs-lookup"><span data-stu-id="610e0-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="610e0-303">Di base</span><span class="sxs-lookup"><span data-stu-id="610e0-303">Baseline</span></span>

  <span data-ttu-id="610e0-304">Gli esempi includono le normali comunicazioni aziendali (posta elettronica) e i file dei dipendenti dei reparti di amministrazione, vendita e supporto.</span><span class="sxs-lookup"><span data-stu-id="610e0-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="610e0-305">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="610e0-305">Sensitive</span></span>

  <span data-ttu-id="610e0-306">Gli esempi includono le informazioni finanziarie e legali, nonché i dati di ricerca e sviluppo relativi a nuovi prodotti o servizi.</span><span class="sxs-lookup"><span data-stu-id="610e0-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="610e0-307">Riservatezza elevata</span><span class="sxs-lookup"><span data-stu-id="610e0-307">Highly regulated</span></span>

  <span data-ttu-id="610e0-308">Gli esempi includono i dati identificabili come personali di clienti e partner, le informazioni finanziarie e la proprietà intellettuale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="610e0-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="610e0-309">In base a questi livelli di sicurezza dei dati, il passaggio successivo consiste nell'identificare e implementare:</span><span class="sxs-lookup"><span data-stu-id="610e0-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="610e0-310">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="610e0-310">Custom sensitive information types</span></span>

  <span data-ttu-id="610e0-311">Microsoft 365 offre un'ampia scelta di tipi di informazioni riservate, ad esempio il codice fiscale o il numero della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="610e0-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="610e0-312">Se non si riesce a trovare quello necessario nell'elenco, è possibile crearne uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="610e0-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="610e0-313">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="610e0-313">Retention labels</span></span>

  <span data-ttu-id="610e0-314">Per garantire la conformità ai criteri dell'organizzazione e alle normative locali, può essere necessario specificare il periodo di conservazione di tipi di documenti specifici o documenti con contenuti specifici.</span><span class="sxs-lookup"><span data-stu-id="610e0-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="610e0-315">È possibile implementare questa funzionalità per la posta elettronica e il documento usando le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="610e0-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="610e0-316">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="610e0-316">Sensitivity labels</span></span>

  <span data-ttu-id="610e0-317">È possibile assegnare a documenti o messaggi di posta elettronica un'etichetta di riservatezza denominata per applicare i livelli aggiuntivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="610e0-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="610e0-318">Alcuni esempi sono le filigrane, la crittografia e le autorizzazioni che consentono di specificare gli utenti autorizzati ad accedere alla posta elettronica e ai documenti e le operazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="610e0-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="610e0-319">Per altre informazioni, vedere [Tipi di classificazione Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types).</span><span class="sxs-lookup"><span data-stu-id="610e0-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="610e0-320">Se si usano le etichette di riservatezza con le autorizzazioni, può essere necessario creare gruppi di sicurezza di Azure AD aggiuntivi per definire gli utenti autorizzati a eseguire determinate operazioni su posta elettronica e documenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="610e0-321">Ad esempio, è necessario creare un'etichetta di riservatezza RESEARCH per proteggere la posta elettronica e i documenti del team di ricerca.</span><span class="sxs-lookup"><span data-stu-id="610e0-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="610e0-322">È possibile stabilire se:</span><span class="sxs-lookup"><span data-stu-id="610e0-322">You determine that:</span></span>

- <span data-ttu-id="610e0-323">I ricercatori devono essere in grado di modificare i documenti contrassegnati dall'etichetta della sensibilità della ricerca.</span><span class="sxs-lookup"><span data-stu-id="610e0-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="610e0-324">I dipendenti non ricercatori devono solo avere la possibilità di visualizzare documenti contrassegnati dall'etichetta della sensibilità della ricerca.</span><span class="sxs-lookup"><span data-stu-id="610e0-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="610e0-325">Questo significa che è necessario creare e gestire due gruppi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="610e0-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="610e0-326">RESEARCH-ALL</span><span class="sxs-lookup"><span data-stu-id="610e0-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="610e0-327">RESEARCH-VIEW</span><span class="sxs-lookup"><span data-stu-id="610e0-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="610e0-328">Questi gruppi e le relative autorizzazioni vengono incluse nella configurazione dell'etichetta di riservatezza RESEARCH.</span><span class="sxs-lookup"><span data-stu-id="610e0-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="610e0-329">Per le etichette di riservatezza configurate con le autorizzazioni basate su gruppi, è necessario gestire l'appartenenza a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="610e0-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="610e0-330">Configurazione attuale</span><span class="sxs-lookup"><span data-stu-id="610e0-330">Your configuration so far</span></span>

<span data-ttu-id="610e0-331">Ecco una grafica riepilogativa della fase Protezione delle informazioni in cui sono evidenziati i nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="610e0-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="610e0-332">Gli elementi nuovi ed evidenziati della fase Protezione delle informazioni includono:</span><span class="sxs-lookup"><span data-stu-id="610e0-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="610e0-333">Etichette di riservatezza per i tre livelli di sicurezza che gli utenti possono applicare ai documenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="610e0-334">La grafica non include i tipi di informazioni e etichette di conservazione e personalizzati.</span><span class="sxs-lookup"><span data-stu-id="610e0-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="610e0-335">Onboarding</span><span class="sxs-lookup"><span data-stu-id="610e0-335">User Onboarding</span></span>

<span data-ttu-id="610e0-336">Con l'infrastruttura aziendale di Microsoft 365 Enterprise, è possibile aggiungere facilmente i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="610e0-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="610e0-337">Un nuovo dispositivo Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="610e0-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="610e0-338">Prima di assegnare a un dipendente un nuovo dispositivo Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="610e0-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="610e0-339">Per identità ibrida</span><span class="sxs-lookup"><span data-stu-id="610e0-339">For hybrid identity</span></span>

  <span data-ttu-id="610e0-340">Aggiungere il dispositivo al dominio AD DS, aggiungere il dispositivo al tenant di Azure AD e quindi registrare il dispositivo in Intune.</span><span class="sxs-lookup"><span data-stu-id="610e0-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="610e0-341">Per identità solo cloud</span><span class="sxs-lookup"><span data-stu-id="610e0-341">For cloud-only identity</span></span>

  <span data-ttu-id="610e0-342">Aggiungere il dispositivo al tenant di Azure AD dell'abbonamento a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="610e0-343">Dipendente esistente con un account utente di AD DS</span><span class="sxs-lookup"><span data-stu-id="610e0-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="610e0-344">Durante l'onboarding iniziale per l'organizzazione quando si usa l'identità ibrida, aggiungere l'account utente di AD DS ai gruppi di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="610e0-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="610e0-345">LICENSED</span><span class="sxs-lookup"><span data-stu-id="610e0-345">Licensed</span></span>
- <span data-ttu-id="610e0-346">I gruppi di sicurezza di AD DS o Azure AD appropriati che fanno parte dei gruppi BASELINE, SENSITIVE e HIGHLY-REGULATED di Azure AD</span><span class="sxs-lookup"><span data-stu-id="610e0-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="610e0-347">Gruppi di etichette di riservatezza (se necessari)</span><span class="sxs-lookup"><span data-stu-id="610e0-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="610e0-348">Il dipendente esistente dovrebbe già essere aggiunto ai gruppi di AD DS a livello di gruppo di lavoro, reparto e area geografica.</span><span class="sxs-lookup"><span data-stu-id="610e0-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="610e0-349">È possibile aggiungere un account utente a più gruppi di Azure AD nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="610e0-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="610e0-350">Nelle proprietà dell'account utente fare clic su **Gestisci gruppi > Aggiungere le membership**.</span><span class="sxs-lookup"><span data-stu-id="610e0-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="610e0-351">Se si vuole usare PowerShell, vedere questa [cartella di lavoro](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true)di Excel scaricabile, che genera i comandi di PowerShell basati su un account utente specificato e i nomi dei gruppi selezionati.</span><span class="sxs-lookup"><span data-stu-id="610e0-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="610e0-352">Nuovo dipendente con account utente solo cloud</span><span class="sxs-lookup"><span data-stu-id="610e0-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="610e0-353">Durante l'onboarding iniziale per l'organizzazione quando si usa l'identità solo cloud, aggiungere il nuovo account utente a questi gruppi:</span><span class="sxs-lookup"><span data-stu-id="610e0-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="610e0-354">LICENSED</span><span class="sxs-lookup"><span data-stu-id="610e0-354">Licensed</span></span>
- <span data-ttu-id="610e0-355">I gruppi di sicurezza di Azure AD appropriati che fanno parte dei gruppi BASELINE, SENSITIVE e HIGHLY-REGULATED di Azure AD</span><span class="sxs-lookup"><span data-stu-id="610e0-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="610e0-356">Gruppi a livello di gruppo di lavoro, reparto e area geografica</span><span class="sxs-lookup"><span data-stu-id="610e0-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="610e0-357">Gruppi di etichette di riservatezza (se necessari)</span><span class="sxs-lookup"><span data-stu-id="610e0-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="610e0-358">Accesso iniziale a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="610e0-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="610e0-359">Per i dipendenti che accedono per la prima volta a Microsoft 365, istruirli a:</span><span class="sxs-lookup"><span data-stu-id="610e0-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="610e0-360">Accedere ai dispositivi con le credenziali del proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="610e0-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="610e0-361">In un browser accedere al portale di Office 365 all'indirizzo https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="610e0-361">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="610e0-362">Nella scheda **Office 365 Home** fare clic su **Installa Office** per installare Office 365 ProPlus nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="610e0-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="610e0-363">Risultati finali</span><span class="sxs-lookup"><span data-stu-id="610e0-363">End results</span></span>

<span data-ttu-id="610e0-364">Ecco i risultati della configurazione dell'infrastruttura di base di Microsoft 365 Enterprise per l'organizzazione non aziendale.</span><span class="sxs-lookup"><span data-stu-id="610e0-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="610e0-365">Risultati per l'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="610e0-365">Infrastructure results</span></span>

<span data-ttu-id="610e0-366">Dopo la creazione e la configurazione dell'infrastruttura di Microsoft 365 Enterprise, si dovrebbe avere:</span><span class="sxs-lookup"><span data-stu-id="610e0-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="610e0-367">Una connessione Internet locale per ogni ufficio con una larghezza di banda sufficiente, fornita da un ISP che usa un server DNS locale a livello di area geografica.</span><span class="sxs-lookup"><span data-stu-id="610e0-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="610e0-368">Per l'identità ibrida, Azure AD Connect in esecuzione in un server che sincronizza il dominio di AD DS locale con il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="610e0-369">Questi gruppi:</span><span class="sxs-lookup"><span data-stu-id="610e0-369">These universal groups include:</span></span>
  - <span data-ttu-id="610e0-370">LICENSED</span><span class="sxs-lookup"><span data-stu-id="610e0-370">Licensed</span></span>
  - <span data-ttu-id="610e0-371">COND-ACCESS-EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="610e0-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="610e0-372">I gruppi di sicurezza di AD DS o Azure AD appropriati che fanno parte anche dei gruppi BASELINE, SENSITIVE e HIGHLY-REGULATED di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="610e0-373">Gruppi a livello di gruppo di lavoro, reparto e area geografica</span><span class="sxs-lookup"><span data-stu-id="610e0-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="610e0-374">Gruppi di etichette di riservatezza (se necessari)</span><span class="sxs-lookup"><span data-stu-id="610e0-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="610e0-375">I criteri di accesso condizionale dell'accesso ad Azure AD che usano i gruppi BASELINE, SENSITIVE, HIGHLY-REGULATED e COND-ACCESS-EXCLUDE di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="610e0-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="610e0-376">Criteri di conformità dei dispositivi e delle applicazioni Intune.</span><span class="sxs-lookup"><span data-stu-id="610e0-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="610e0-377">Tipi di informazioni riservate personalizzati (se necessari).</span><span class="sxs-lookup"><span data-stu-id="610e0-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="610e0-378">Etichette di conservazione (se necessarie).</span><span class="sxs-lookup"><span data-stu-id="610e0-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="610e0-379">Etichette di riservatezza (se necessarie).</span><span class="sxs-lookup"><span data-stu-id="610e0-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="610e0-380">Ecco una grafica riepilogativa dell'infrastruttura se l'organizzazione usa l'identità ibrida, che include il dominio di AD DS, un server Azure AD Connect, nonché utenti e gruppi AD DS sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="610e0-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="610e0-381">Ecco una grafica riepilogativa dell'infrastruttura se l'organizzazione usa l'identità solo cloud.</span><span class="sxs-lookup"><span data-stu-id="610e0-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="610e0-382">Risultati per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="610e0-382">Employee results</span></span>

<span data-ttu-id="610e0-383">Dopo l'onboarding ogni dipendente dovrebbe avere:</span><span class="sxs-lookup"><span data-stu-id="610e0-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="610e0-384">Un percorso di rete locale con prestazioni elevate per accedere dal dispositivo ai servizi cloud di Microsoft 365 nella propria area geografica.</span><span class="sxs-lookup"><span data-stu-id="610e0-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="610e0-385">Un account utente con queste appartenenze a gruppi:</span><span class="sxs-lookup"><span data-stu-id="610e0-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="610e0-386">LICENSED</span><span class="sxs-lookup"><span data-stu-id="610e0-386">Licensed</span></span>
   - <span data-ttu-id="610e0-387">I gruppi di sicurezza di AD DS o Azure AD appropriati che fanno parte anche dei gruppi BASELINE, SENSITIVE e HIGHLY-REGULATED di Azure AD per i criteri di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="610e0-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="610e0-388">Gruppi appropriati a livello di gruppo di lavoro, reparto e area geografica</span><span class="sxs-lookup"><span data-stu-id="610e0-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="610e0-389">Gruppi di etichette di riservatezza (se necessari)</span><span class="sxs-lookup"><span data-stu-id="610e0-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="610e0-390">Un dispositivo Windows 10 Enterprise che:</span><span class="sxs-lookup"><span data-stu-id="610e0-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="610e0-391">Appartiene al tenant di Azure AD (solo cloud) oppure sia al tenant di Azure AD che al dominio di AD DS (ibrido).</span><span class="sxs-lookup"><span data-stu-id="610e0-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="610e0-392">Si aggiorna automaticamente con i miglioramenti e le opzioni di sicurezza più recenti dei prodotti Windows 10.</span><span class="sxs-lookup"><span data-stu-id="610e0-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="610e0-393">Include Office 365 ProPlus, che si aggiorna automaticamente con i miglioramenti e le opzioni di sicurezza più recenti dei prodotti Office.</span><span class="sxs-lookup"><span data-stu-id="610e0-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="610e0-394">Viene registrato in Intune ed è soggetto ai criteri di conformità dei dispositivi e di protezione delle app di Intune.</span><span class="sxs-lookup"><span data-stu-id="610e0-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="610e0-395">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="610e0-395">Next step</span></span>

<span data-ttu-id="610e0-396">Distribuire i [carichi di lavoro e gli scenari](deploy-workloads.md) per sfruttare le funzionalità e la configurazione dell'infrastruttura di base di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="610e0-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
