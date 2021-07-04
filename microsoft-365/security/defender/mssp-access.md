---
title: Fornire l'accesso msSP (Managed Security Service Provider)
description: Informazioni sulle modifiche dall'Microsoft Defender Security Center al Centro sicurezza Microsoft 365 sicurezza
keywords: Introduzione al centro sicurezza Microsoft 365, Microsoft Defender per Office 365, Microsoft Defender for Endpoint, MDO, MDE, riquadro singolo di vetro, portale convergente, portale di sicurezza, portale di sicurezza, portale di sicurezza defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: ddc28149ca2ab43b7c14d3bdbaeeecdad1b18387
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289764"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="c0000-104">Fornire l'accesso msSP (Managed Security Service Provider)</span><span class="sxs-lookup"><span data-stu-id="c0000-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="c0000-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c0000-105">**Applies to:**</span></span>

- [<span data-ttu-id="c0000-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0000-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="c0000-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c0000-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="c0000-108">Per implementare una soluzione di accesso delegato multi-tenant, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c0000-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="c0000-109">Abilitare [il controllo dell'accesso](/windows/security/threat-protection/microsoft-defender-atp/rbac) basato sui ruoli in Defender for Endpoint nel Centro sicurezza Microsoft 365 e connettersi con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c0000-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="c0000-110">Configurare i [pacchetti di accesso di](/azure/active-directory/governance/identity-governance-overview) governance per la richiesta di accesso e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="c0000-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="c0000-111">Gestire le richieste di accesso e i controlli in [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="c0000-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="c0000-112">Abilitare i controlli di accesso basati sui ruoli in Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 sicurezza</span><span class="sxs-lookup"><span data-stu-id="c0000-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="c0000-113">**Creare gruppi di accesso per le risorse MSSP in Customer AAD: Gruppi**</span><span class="sxs-lookup"><span data-stu-id="c0000-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="c0000-114">Questi gruppi verranno collegati ai ruoli creati in Defender per Endpoint nel centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0000-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="c0000-115">A tale scopo, nel tenant AD del cliente creare tre gruppi.</span><span class="sxs-lookup"><span data-stu-id="c0000-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="c0000-116">Nell'approccio di esempio vengono creati i gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0000-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="c0000-117">Analista di livello 1</span><span class="sxs-lookup"><span data-stu-id="c0000-117">Tier 1 Analyst</span></span>
    - <span data-ttu-id="c0000-118">Analista di livello 2</span><span class="sxs-lookup"><span data-stu-id="c0000-118">Tier 2 Analyst</span></span>
    - <span data-ttu-id="c0000-119">Responsabili approvazione analista MSSP</span><span class="sxs-lookup"><span data-stu-id="c0000-119">MSSP Analyst Approvers</span></span>  

2. <span data-ttu-id="c0000-120">Creare ruoli defender per endpoint per i livelli di accesso appropriati in Customer Defender for Endpoint Microsoft 365 gruppi e ruoli del centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0000-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="c0000-121">Per abilitare RBAC nel Centro sicurezza Microsoft 365 clienti, accedere a Autorizzazioni **> Endpoints** ruoli & gruppi > Ruoli con un account utente con diritti di amministratore globale o amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0000-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Immagine dell'accesso MSSP](../../media/mssp-access.png)

    <span data-ttu-id="c0000-123">Creare quindi ruoli RBAC per soddisfare le esigenze del livello SOC MSSP.</span><span class="sxs-lookup"><span data-stu-id="c0000-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="c0000-124">Collegare questi ruoli ai gruppi di utenti creati tramite "Gruppi di utenti assegnati".</span><span class="sxs-lookup"><span data-stu-id="c0000-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="c0000-125">Due possibili ruoli:</span><span class="sxs-lookup"><span data-stu-id="c0000-125">Two possible roles:</span></span>

    - <span data-ttu-id="c0000-126">**Analisti di livello 1**</span><span class="sxs-lookup"><span data-stu-id="c0000-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="c0000-127">Eseguire tutte le azioni ad eccezione della risposta in tempo reale e gestire le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0000-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="c0000-128">**Analisti di livello 2**</span><span class="sxs-lookup"><span data-stu-id="c0000-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="c0000-129">Funzionalità di livello 1 con l'aggiunta della [risposta in tempo reale](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="c0000-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="c0000-130">Per ulteriori informazioni, vedere [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span><span class="sxs-lookup"><span data-stu-id="c0000-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>

## <a name="configure-governance-access-packages"></a><span data-ttu-id="c0000-131">Configurare i pacchetti di accesso alla governance</span><span class="sxs-lookup"><span data-stu-id="c0000-131">Configure Governance Access Packages</span></span>

1. <span data-ttu-id="c0000-132">**Aggiungere MSSP come organizzazione connessa in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c0000-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c0000-133">L'aggiunta di MSSP come organizzazione connessa consentirà al provider mssp di richiedere e disporre degli accessi di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="c0000-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="c0000-134">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Connected organization.</span><span class="sxs-lookup"><span data-stu-id="c0000-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="c0000-135">Aggiungere una nuova organizzazione e cercare il tenant dell'analista MSSP tramite l'ID tenant o il dominio.</span><span class="sxs-lookup"><span data-stu-id="c0000-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="c0000-136">Ti consigliamo di creare un tenant AD separato per gli analisti MSSP.</span><span class="sxs-lookup"><span data-stu-id="c0000-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="c0000-137">**Creare un catalogo delle risorse in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c0000-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c0000-138">I cataloghi delle risorse sono una raccolta logica di pacchetti di accesso, creati nel tenant AD del cliente.</span><span class="sxs-lookup"><span data-stu-id="c0000-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="c0000-139">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Catalogs e aggiungere **New Catalog.**</span><span class="sxs-lookup"><span data-stu-id="c0000-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="c0000-140">In questo esempio, verrà chiamato **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="c0000-140">In our example, we will call it **MSSP Accesses**.</span></span>

    ![Immagine del nuovo catalogo](../../media/goverance-catalog.png)

    <span data-ttu-id="c0000-142">Per ulteriori informazioni, vedere [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span><span class="sxs-lookup"><span data-stu-id="c0000-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>

3. <span data-ttu-id="c0000-143">**Creare pacchetti di accesso per le risorse MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c0000-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c0000-144">I pacchetti di accesso sono la raccolta di diritti e accessi a cui un richiedente verrà concesso all'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c0000-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="c0000-145">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Access Packages e aggiungere **New Access Package.**</span><span class="sxs-lookup"><span data-stu-id="c0000-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="c0000-146">Creare un pacchetto di accesso per i responsabili approvazione MSSP e ogni livello di analista.</span><span class="sxs-lookup"><span data-stu-id="c0000-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="c0000-147">Ad esempio, la configurazione dell'analista di livello 1 seguente crea un pacchetto di accesso che:</span><span class="sxs-lookup"><span data-stu-id="c0000-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="c0000-148">Richiede a un membro del gruppo AD **Responsabili approvazione analisti MSSP** di autorizzare nuove richieste</span><span class="sxs-lookup"><span data-stu-id="c0000-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="c0000-149">Ha revisioni di accesso annuali, in cui gli analisti SOC possono richiedere un'estensione di accesso</span><span class="sxs-lookup"><span data-stu-id="c0000-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="c0000-150">Può essere richiesto solo dagli utenti nel tenant SOC MSSP</span><span class="sxs-lookup"><span data-stu-id="c0000-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="c0000-151">Access scade automaticamente dopo 365 giorni</span><span class="sxs-lookup"><span data-stu-id="c0000-151">Access auto expires after 365 days</span></span>

    ![Immagine del nuovo pacchetto di accesso](../../media/new-access-package.png)

    <span data-ttu-id="c0000-153">Per ulteriori informazioni, vedere [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="c0000-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>

4. <span data-ttu-id="c0000-154">**Fornire il collegamento della richiesta di accesso alle risorse MSSP da Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c0000-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c0000-155">Il collegamento al portale My Access viene utilizzato dagli analisti SOC di MSSP per richiedere l'accesso tramite i pacchetti di accesso creati.</span><span class="sxs-lookup"><span data-stu-id="c0000-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="c0000-156">Il collegamento è durevole, ovvero lo stesso collegamento può essere utilizzato nel tempo per i nuovi analisti.</span><span class="sxs-lookup"><span data-stu-id="c0000-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="c0000-157">La richiesta dell'analista viene inviata in una coda per l'approvazione da parte dei responsabili approvazione degli analisti **MSSP.**</span><span class="sxs-lookup"><span data-stu-id="c0000-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    ![Immagine delle proprietà di accesso](../../media/access-properties.png)

    <span data-ttu-id="c0000-159">Il collegamento si trova nella pagina di panoramica di ogni pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="c0000-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="c0000-160">Gestire accessi</span><span class="sxs-lookup"><span data-stu-id="c0000-160">Manage access</span></span>

1. <span data-ttu-id="c0000-161">Esaminare e autorizzare le richieste di accesso in Customer e/o MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="c0000-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="c0000-162">Le richieste di accesso vengono gestite nel cliente Accesso personale dai membri del gruppo Responsabili approvazione analista MSSP.</span><span class="sxs-lookup"><span data-stu-id="c0000-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="c0000-163">A tale scopo, accedere all'account myaccess del cliente usando: `https://myaccess.microsoft.com/@<Customer Domain>` .</span><span class="sxs-lookup"><span data-stu-id="c0000-163">To do so, access the customer's myaccess using: `https://myaccess.microsoft.com/@<Customer Domain>`.</span></span>

    <span data-ttu-id="c0000-164">Esempio: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="c0000-164">Example: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>

2. <span data-ttu-id="c0000-165">Approvare o rifiutare le richieste nella **sezione Approvazioni** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c0000-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="c0000-166">A questo punto, è stato effettuato il provisioning dell'accesso dell'analista e ogni analista dovrebbe essere in grado di accedere al Centro sicurezza Microsoft 365 cliente:</span><span class="sxs-lookup"><span data-stu-id="c0000-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span>

    <span data-ttu-id="c0000-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` con le autorizzazioni e i ruoli a cui sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="c0000-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0000-168">L'accesso delegato a Microsoft Defender for Endpoint nel centro sicurezza Microsoft 365 consente attualmente l'accesso a un singolo tenant per finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="c0000-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>
