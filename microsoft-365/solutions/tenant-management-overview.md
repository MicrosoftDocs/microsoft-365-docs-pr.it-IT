---
title: Gestione tenant per Microsoft 365 per Enterprise
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
description: Una panoramica sulla pianificazione, la distribuzione e il funzionamento continuo dei tenant Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908635"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="eaf88-103">Gestione tenant per Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaf88-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="eaf88-104">La creazione di un percorso per la trasformazione digitale dell'organizzazione con il cloud computing richiede un solido fondamento su cui i dipendenti possono contare per la produttività, la collaborazione, le prestazioni, la privacy, la conformità e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaf88-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="eaf88-105">La corretta configurazione dei tenant di Microsoft 365 fornisce tale fondamento, lasciando i lavoratori a concentrarsi su come svolgere il proprio lavoro e il proprio reparto IT per concentrarsi sulle soluzioni end-to-end che forniscono un valore aziendale aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="eaf88-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="eaf88-106">Questa soluzione consente di eseguire la configurazione di tale fondamento nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="eaf88-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="eaf88-107">Determinare i tenant</span><span class="sxs-lookup"><span data-stu-id="eaf88-107">Determine your tenants</span></span>
2. <span data-ttu-id="eaf88-108">Ottimizzare la rete</span><span class="sxs-lookup"><span data-stu-id="eaf88-108">Optimize your networking</span></span>
3. <span data-ttu-id="eaf88-109">Sincronizzare le identità e applicare gli accessi sicuri</span><span class="sxs-lookup"><span data-stu-id="eaf88-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="eaf88-110">Eseguire la migrazione di dispositivi Windows, client di Office e server e dati locali di Office</span><span class="sxs-lookup"><span data-stu-id="eaf88-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="eaf88-111">Distribuire la gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="eaf88-111">Deploy device and app management</span></span>

<span data-ttu-id="eaf88-112">Tuttavia, prima di tutto, è necessario un momento per capire cosa è un tenant e cosa assomiglia a un tenant che fornisce una base stabile.</span><span class="sxs-lookup"><span data-stu-id="eaf88-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="eaf88-113">Un tenant di Microsoft 365 definito</span><span class="sxs-lookup"><span data-stu-id="eaf88-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="eaf88-114">Un tenant di Microsoft 365 è un'istanza dedicata dei servizi di Microsoft 365 e dei dati dell'organizzazione archiviati all'interno di una specifica posizione predefinita, ad esempio Europa o Nord America.</span><span class="sxs-lookup"><span data-stu-id="eaf88-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="eaf88-115">Questo percorso viene specificato quando si crea il tenant per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eaf88-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="eaf88-116">Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="eaf88-117">È possibile creare un tenant di Microsoft 365 quando si acquista uno o più prodotti da Microsoft, ad esempio Microsoft 365 E3 o E5, e un insieme di licenze per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="eaf88-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="eaf88-118">Il tenant Microsoft 365 include anche un tenant di Azure Active Directory (Azure AD), che è un'istanza dedicata di Azure AD per gli account utente, i gruppi e gli altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="eaf88-119">Ogni tenant di Azure AD è distinto, univoco e separato da tutti gli altri tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="eaf88-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="eaf88-120">Anche se l'organizzazione può disporre di più tenant di Azure AD che è possibile configurare con le sottoscrizioni di Azure, i tenant di Microsoft 365 possono utilizzare solo un singolo tenant di Azure AD, quello creato durante la creazione del tenant.</span><span class="sxs-lookup"><span data-stu-id="eaf88-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="eaf88-121">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="eaf88-121">Here is an example:</span></span>

![Un esempio Microsoft 365 tenant con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="eaf88-123">*Gestione tenant* è la pianificazione, la distribuzione e il funzionamento continuo dei tenant Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="eaf88-124">Attributi di un tenant ben disegnato e operativo</span><span class="sxs-lookup"><span data-stu-id="eaf88-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="eaf88-125">Oltre al nome e alla posizione corretti per il tenant, sono disponibili ulteriori elementi per pianificare, distribuire e gestire le esperienze degli utenti con le app per la produttività del cloud, &mdash; ad esempio Microsoft teams ed Exchange Online, che &mdash; sono effettive, sicure e performanti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="eaf88-126">Ecco gli elementi:</span><span class="sxs-lookup"><span data-stu-id="eaf88-126">Here are the elements:</span></span>

- <span data-ttu-id="eaf88-127">Si dispone del set corretto di prodotti (abbonamenti) e licenze.</span><span class="sxs-lookup"><span data-stu-id="eaf88-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="eaf88-128">Il set di prodotti corrisponde alle esigenze aziendali, IT e di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaf88-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="eaf88-129">Vi è un numero adeguato di licenze per i dipendenti e le modifiche anticipate del personale.</span><span class="sxs-lookup"><span data-stu-id="eaf88-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="eaf88-130">Per la rete:</span><span class="sxs-lookup"><span data-stu-id="eaf88-130">For networking:</span></span>
  - <span data-ttu-id="eaf88-131">Sono stati configurati i nomi di dominio DNS corretti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="eaf88-132">Per le reti aziendali, il traffico di rete è stato ottimizzato per la rete Microsoft per i lavoratori onsite.</span><span class="sxs-lookup"><span data-stu-id="eaf88-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="eaf88-133">È stato ottimizzato il traffico di rete per i dipendenti remoti che utilizzano un client VPN.</span><span class="sxs-lookup"><span data-stu-id="eaf88-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="eaf88-134">Sono stati sincronizzati gli account di servizi di dominio Active Directory (AD DS), i gruppi e gli altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="eaf88-135">Gli account tenant di Azure AD vengono mappati alle cassette postali di Exchange Online con i domini DNS corretti per gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="eaf88-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="eaf88-136">Agli account utente sono state assegnate le licenze corrette dai prodotti acquistati corretti (come Microsoft 365 E3 o E5).</span><span class="sxs-lookup"><span data-stu-id="eaf88-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="eaf88-137">Sono state configurate forti identità e gestione degli accessi.</span><span class="sxs-lookup"><span data-stu-id="eaf88-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="eaf88-138">Si richiede l'accesso sicuro degli utenti con password o autenticazione a più fattori (AMF).</span><span class="sxs-lookup"><span data-stu-id="eaf88-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="eaf88-139">Si dispone di criteri di accesso condizionale che applicano i requisiti e le restrizioni per i livelli di sicurezza più elevati.</span><span class="sxs-lookup"><span data-stu-id="eaf88-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="eaf88-140">I server di Office locali e i relativi dati sono stati migrati nelle app Cloud o sono stati utilizzati in una configurazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="eaf88-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="eaf88-141">Si sta eseguendo la gestione dei dispositivi con Intune o la mobilità di base e la sicurezza integrata in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="eaf88-142">I dispositivi di proprietà dell'organizzazione vengono registrati e gestiti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="eaf88-143">Le app per i dispositivi personali vengono gestite.</span><span class="sxs-lookup"><span data-stu-id="eaf88-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="eaf88-144">Di seguito è riportato un esempio di tenant Microsoft 365 con tutti questi elementi sul posto.</span><span class="sxs-lookup"><span data-stu-id="eaf88-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Un esempio di Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="eaf88-146">In questa figura, il tenant di Microsoft 365 include:</span><span class="sxs-lookup"><span data-stu-id="eaf88-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="eaf88-147">Prodotti e licenze per Microsoft 365 E3 ed E5.</span><span class="sxs-lookup"><span data-stu-id="eaf88-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="eaf88-148">App per la produttività di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="eaf88-149">Intune con i dispositivi registrati e i criteri di dispositivo e applicazione.</span><span class="sxs-lookup"><span data-stu-id="eaf88-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="eaf88-150">Un tenant di Azure AD con account utente sincronizzato (gruppi e altri oggetti directory non visualizzati), domini e criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="eaf88-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="eaf88-151">Funzionalità tenant per Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaf88-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="eaf88-152">Nelle sezioni e nelle tabelle riportate di seguito sono elencate le funzionalità e le licenze principali per la procedura descritta in questa soluzione.</span><span class="sxs-lookup"><span data-stu-id="eaf88-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="eaf88-153">Tenant</span><span class="sxs-lookup"><span data-stu-id="eaf88-153">Tenant</span></span>

| <span data-ttu-id="eaf88-154">Capacità o funzionalità</span><span class="sxs-lookup"><span data-stu-id="eaf88-154">Capability or feature</span></span> | <span data-ttu-id="eaf88-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf88-155">Description</span></span> | <span data-ttu-id="eaf88-156">Licenze</span><span class="sxs-lookup"><span data-stu-id="eaf88-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="eaf88-157">Più tenant</span><span class="sxs-lookup"><span data-stu-id="eaf88-157">Multiple tenants</span></span> | <span data-ttu-id="eaf88-158">Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="eaf88-159">Con più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="eaf88-160">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-161">Migrazione delle cassette postali tra tenant</span><span class="sxs-lookup"><span data-stu-id="eaf88-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="eaf88-162">Gli amministratori tenant possono spostare le cassette postali tra i tenant con dipendenze dell'infrastruttura minime nei rispettivi sistemi locali.</span><span class="sxs-lookup"><span data-stu-id="eaf88-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="eaf88-163">In questo modo viene eliminata la necessità di disabilitare le cassette postali e di bordo.</span><span class="sxs-lookup"><span data-stu-id="eaf88-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="eaf88-164">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-165">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="eaf88-165">Multi-Geo</span></span> | <span data-ttu-id="eaf88-166">Il tenant può archiviare i dati a riposo nelle altre posizioni geografiche del datacenter che si è scelto di soddisfare i requisiti di residenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="eaf88-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="eaf88-167">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-168">Spostare i dati di base in un nuovo datacenter Geo</span><span class="sxs-lookup"><span data-stu-id="eaf88-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="eaf88-169">Poiché Microsoft aggiunge nuovo datacenter GEOS per ulteriori capacità e risorse di calcolo, è possibile richiedere una mossa geografica del datacenter per la residenza dei dati in-Geo per i dati di base dei clienti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="eaf88-170">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="eaf88-171">Rete</span><span class="sxs-lookup"><span data-stu-id="eaf88-171">Networking</span></span>

| <span data-ttu-id="eaf88-172">Capacità o funzionalità</span><span class="sxs-lookup"><span data-stu-id="eaf88-172">Capability or feature</span></span> | <span data-ttu-id="eaf88-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf88-173">Description</span></span> | <span data-ttu-id="eaf88-174">Licenze</span><span class="sxs-lookup"><span data-stu-id="eaf88-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="eaf88-175">Informazioni di rete</span><span class="sxs-lookup"><span data-stu-id="eaf88-175">Network Insights</span></span> | <span data-ttu-id="eaf88-176">Metriche delle prestazioni di rete raccolte dal tenant Microsoft 365 per facilitare la progettazione di perimetri di rete per le posizioni di Office.</span><span class="sxs-lookup"><span data-stu-id="eaf88-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="eaf88-177">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-178">Automatizzare gli aggiornamenti degli endpoint</span><span class="sxs-lookup"><span data-stu-id="eaf88-178">Automate endpoint updates</span></span> | <span data-ttu-id="eaf88-179">Automatizzare la configurazione e gli aggiornamenti in continuazione per gli endpoint di Microsoft 365 nei file PAC client e nei dispositivi e servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="eaf88-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="eaf88-180">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="eaf88-181">Identità</span><span class="sxs-lookup"><span data-stu-id="eaf88-181">Identity</span></span>

| <span data-ttu-id="eaf88-182">Capacità o funzionalità</span><span class="sxs-lookup"><span data-stu-id="eaf88-182">Capability or feature</span></span> | <span data-ttu-id="eaf88-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf88-183">Description</span></span> | <span data-ttu-id="eaf88-184">Licenze</span><span class="sxs-lookup"><span data-stu-id="eaf88-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="eaf88-185">Sincronizzare servizi di dominio Active Directory (AD DS) locali con il tenant di Azure AD</span><span class="sxs-lookup"><span data-stu-id="eaf88-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="eaf88-186">Sfruttare il provider di identità locale per gli account utente, i gruppi e gli altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="eaf88-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="eaf88-187">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="eaf88-188">MFA applicata con le impostazioni predefinite per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="eaf88-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="eaf88-189">Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.</span><span class="sxs-lookup"><span data-stu-id="eaf88-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="eaf88-190">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="eaf88-191">MFA applicata con l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="eaf88-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="eaf88-192">Richiedere l'AMF in base agli attributi dei criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="eaf88-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="eaf88-193">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-194">MFA applicata con l'accesso condizionale basato sul rischio</span><span class="sxs-lookup"><span data-stu-id="eaf88-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="eaf88-195">Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Microsoft Defender per identità.</span><span class="sxs-lookup"><span data-stu-id="eaf88-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="eaf88-196">Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="eaf88-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="eaf88-197">Reimpostazione della password self-service</span><span class="sxs-lookup"><span data-stu-id="eaf88-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="eaf88-198">Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.</span><span class="sxs-lookup"><span data-stu-id="eaf88-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="eaf88-199">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="eaf88-200">Migrazione</span><span class="sxs-lookup"><span data-stu-id="eaf88-200">Migration</span></span>

| <span data-ttu-id="eaf88-201">Capacità o funzionalità</span><span class="sxs-lookup"><span data-stu-id="eaf88-201">Capability or feature</span></span> | <span data-ttu-id="eaf88-202">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf88-202">Description</span></span> | <span data-ttu-id="eaf88-203">Licenze</span><span class="sxs-lookup"><span data-stu-id="eaf88-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="eaf88-204">Eseguire la migrazione a Windows 10</span><span class="sxs-lookup"><span data-stu-id="eaf88-204">Migrate to Windows 10</span></span> | <span data-ttu-id="eaf88-205">Eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8,1 a Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="eaf88-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="eaf88-206">Licenze di Windows 10 Enterprise incluse in Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-207">Eseguire la migrazione a Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaf88-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="eaf88-208">Eseguire la migrazione delle app client di Office, ad esempio Word e PowerPoint, alle versioni installate dal cloud aggiornate con nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="eaf88-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="eaf88-209">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-210">Eseguire la migrazione di dati e server locali a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eaf88-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="eaf88-211">Eseguire la migrazione delle cassette postali di Exchange, dei siti di SharePoint e di Skype for business online ai servizi cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="eaf88-212">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="eaf88-213">Gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="eaf88-213">Device and app management</span></span>

| <span data-ttu-id="eaf88-214">Capacità o funzionalità</span><span class="sxs-lookup"><span data-stu-id="eaf88-214">Capability or feature</span></span> | <span data-ttu-id="eaf88-215">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf88-215">Description</span></span> | <span data-ttu-id="eaf88-216">Licenze</span><span class="sxs-lookup"><span data-stu-id="eaf88-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="eaf88-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eaf88-217">Microsoft Intune</span></span> | <span data-ttu-id="eaf88-218">Servizio basato su cloud che fornisce la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM) per controllare il modo in cui vengono utilizzate l'applicazione e i dispositivi dell'organizzazione, inclusi telefoni cellulari, tablet e laptop.</span><span class="sxs-lookup"><span data-stu-id="eaf88-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="eaf88-219">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="eaf88-220">Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="eaf88-220">Basic Mobility and Security</span></span> | <span data-ttu-id="eaf88-221">Proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows con questo servizio incorporato.</span><span class="sxs-lookup"><span data-stu-id="eaf88-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="eaf88-222">Microsoft 365 E3 o E5</span><span class="sxs-lookup"><span data-stu-id="eaf88-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="eaf88-223">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eaf88-223">Next steps</span></span>

<span data-ttu-id="eaf88-224">Attenersi alla procedura seguente per configurare e gestire i tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eaf88-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="eaf88-225">Determinare i tenant</span><span class="sxs-lookup"><span data-stu-id="eaf88-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="eaf88-226">Ottimizzare la rete</span><span class="sxs-lookup"><span data-stu-id="eaf88-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="eaf88-227">Sincronizzare le identità e applicare gli accessi sicuri</span><span class="sxs-lookup"><span data-stu-id="eaf88-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="eaf88-228">Migrare i dati e i server di Office locali</span><span class="sxs-lookup"><span data-stu-id="eaf88-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="eaf88-229">Distribuire la gestione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="eaf88-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="eaf88-230">[![Passaggi per la distribuzione e la gestione di un tenant di Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="eaf88-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="eaf88-231">In ogni passaggio vengono descritte le opzioni di distribuzione, vengono riepilogati i risultati e le attività di manutenzione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eaf88-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="eaf88-232">Per comprendere come un'organizzazione multi-nazionale fittizia ma rappresentativa ha distribuito gli elementi del tenant Microsoft 365, vedere il [Case Study di Contoso](../enterprise/contoso-case-study.md).</span><span class="sxs-lookup"><span data-stu-id="eaf88-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>