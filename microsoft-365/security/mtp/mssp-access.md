---
title: Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365
description: Informazioni sulle modifiche dal Centro sicurezza Microsoft Defender al Centro sicurezza Microsoft 365
keywords: Introduzione al Centro sicurezza Microsoft 365, OATP, MDATP, MDO, MDE, riquadro singolo di vetro, portale convergente, portale di sicurezza, portale di sicurezza, portale di sicurezza defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242964"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="e61c1-104">Fornire l'accesso al provider di servizi di sicurezza gestito (MSSP)</span><span class="sxs-lookup"><span data-stu-id="e61c1-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="e61c1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e61c1-105">**Applies to:**</span></span>

- [<span data-ttu-id="e61c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e61c1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="e61c1-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e61c1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="e61c1-108">Per implementare una soluzione di accesso delegato multi-tenant, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e61c1-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="e61c1-109">Abilitare [il controllo dell'accesso](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) basato sui ruoli in Defender per Endpoint nel Centro sicurezza Microsoft 365 e connettersi ai gruppi di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e61c1-109">Enable [role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="e61c1-110">Configurare i [pacchetti di accesso di](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) governance per la richiesta di accesso e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="e61c1-110">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="e61c1-111">Gestire le richieste di accesso e i controlli in [Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="e61c1-111">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="e61c1-112">Abilitare i controlli di accesso in base al ruolo in Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e61c1-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="e61c1-113">**Creare gruppi di accesso per le risorse MSSP in Customer AAD: Gruppi**</span><span class="sxs-lookup"><span data-stu-id="e61c1-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="e61c1-114">Questi gruppi verranno collegati ai ruoli creati in Defender per Endpoint nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e61c1-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="e61c1-115">A tale scopo, nel tenant di Active Directory del cliente crea tre gruppi.</span><span class="sxs-lookup"><span data-stu-id="e61c1-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="e61c1-116">Nell'approccio di esempio vengono creati i gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e61c1-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="e61c1-117">Analista di livello 1</span><span class="sxs-lookup"><span data-stu-id="e61c1-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="e61c1-118">Analista di livello 2</span><span class="sxs-lookup"><span data-stu-id="e61c1-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="e61c1-119">Responsabili approvazione analista MSSP</span><span class="sxs-lookup"><span data-stu-id="e61c1-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="e61c1-120">Creare ruoli di Defender per endpoint per i livelli di accesso appropriati in Ruoli e gruppi del Centro sicurezza Microsoft 365 in Customer Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e61c1-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="e61c1-121">Per abilitare RBAC nel Centro sicurezza Microsoft 365 del cliente, accedere ai ruoli Autorizzazioni **> Endpoints** & gruppi > Ruoli con un account utente con diritti di amministratore globale o amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e61c1-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Immagine dell'accesso MSSP](../../media/mssp-access.png)

    <span data-ttu-id="e61c1-123">Creare quindi i ruoli RBAC per soddisfare le esigenze del livello SOC MSSP.</span><span class="sxs-lookup"><span data-stu-id="e61c1-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="e61c1-124">Collegare questi ruoli ai gruppi di utenti creati tramite "Gruppi di utenti assegnati".</span><span class="sxs-lookup"><span data-stu-id="e61c1-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="e61c1-125">Due possibili ruoli:</span><span class="sxs-lookup"><span data-stu-id="e61c1-125">Two possible roles:</span></span>

    - <span data-ttu-id="e61c1-126">**Analisti di livello 1**</span><span class="sxs-lookup"><span data-stu-id="e61c1-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="e61c1-127">Eseguire tutte le azioni ad eccezione della risposta in tempo reale e gestire le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e61c1-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="e61c1-128">**Analisti di livello 2**</span><span class="sxs-lookup"><span data-stu-id="e61c1-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="e61c1-129">Funzionalità di livello 1 con l'aggiunta della [risposta in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="e61c1-129">Tier 1 capabilities with the addition to [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="e61c1-130">Per ulteriori informazioni, vedere [Use role-based access control.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="e61c1-130">For more information, see [Use role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="e61c1-131">Configurare i pacchetti di accesso alla governance</span><span class="sxs-lookup"><span data-stu-id="e61c1-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="e61c1-132">**Aggiungere MSSP come organizzazione connessa in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="e61c1-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="e61c1-133">L'aggiunta del provider di servizi condivisi come organizzazione connessa consentirà al provider di servizi condivisi di richiedere e di disporre degli accessi di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="e61c1-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="e61c1-134">A tale scopo, nel tenant di Active Directory del cliente, accedere a Identity Governance: Organizzazione connessa.</span><span class="sxs-lookup"><span data-stu-id="e61c1-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="e61c1-135">Aggiungere una nuova organizzazione e cercare il tenant dell'analista MSSP tramite l'ID tenant o il dominio.</span><span class="sxs-lookup"><span data-stu-id="e61c1-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="e61c1-136">È consigliabile creare un tenant AD separato per gli analisti MSSP.</span><span class="sxs-lookup"><span data-stu-id="e61c1-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="e61c1-137">**Creare un catalogo delle risorse in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="e61c1-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e61c1-138">I cataloghi delle risorse sono una raccolta logica di pacchetti di accesso, creati nel tenant di Active Directory del cliente.</span><span class="sxs-lookup"><span data-stu-id="e61c1-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="e61c1-139">A tale scopo, nel tenant di Active Directory del cliente, accedere a Identity Governance: Cataloghi e aggiungere **Nuovo catalogo.**</span><span class="sxs-lookup"><span data-stu-id="e61c1-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="e61c1-140">In questo esempio verrà chiamato **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="e61c1-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Immagine del nuovo catalogo](../../media/goverance-catalog.png)

    <span data-ttu-id="e61c1-142">Per ulteriori informazioni, vedere [Creare un catalogo di risorse.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="e61c1-142">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="e61c1-143">**Creare pacchetti di accesso per le risorse MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="e61c1-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e61c1-144">I pacchetti di accesso sono la raccolta di diritti e accessi a cui verrà concesso un richiedente all'approvazione.</span><span class="sxs-lookup"><span data-stu-id="e61c1-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="e61c1-145">A tale scopo, nel tenant di Active Directory del cliente, accedere a Identity Governance: Pacchetti di accesso e aggiungere **nuovo pacchetto di accesso.**</span><span class="sxs-lookup"><span data-stu-id="e61c1-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="e61c1-146">Creare un pacchetto di accesso per i responsabili approvazione mssp e ogni livello di analista.</span><span class="sxs-lookup"><span data-stu-id="e61c1-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="e61c1-147">Ad esempio, la seguente configurazione dell'analista di livello 1 crea un pacchetto di accesso che:</span><span class="sxs-lookup"><span data-stu-id="e61c1-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="e61c1-148">Richiede a un membro del gruppo AD **responsabili approvazione analista MSSP** di autorizzare nuove richieste</span><span class="sxs-lookup"><span data-stu-id="e61c1-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="e61c1-149">Ha revisioni di accesso annuali, in cui gli analisti SOC possono richiedere un'estensione di accesso</span><span class="sxs-lookup"><span data-stu-id="e61c1-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="e61c1-150">Può essere richiesto solo dagli utenti nel tenant SOC MSSP</span><span class="sxs-lookup"><span data-stu-id="e61c1-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="e61c1-151">Access scade automaticamente dopo 365 giorni</span><span class="sxs-lookup"><span data-stu-id="e61c1-151">Access auto expires after 365 days</span></span>

    ![Immagine del nuovo pacchetto di accesso](../../media/new-access-package.png)

    <span data-ttu-id="e61c1-153">Per altre informazioni, vedi [Creare un nuovo pacchetto di accesso.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="e61c1-153">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="e61c1-154">**Fornire il collegamento alla richiesta di accesso alle risorse MSSP da Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="e61c1-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="e61c1-155">Il collegamento al portale My Access viene usato dagli analisti SOC di MSSP per richiedere l'accesso tramite i pacchetti di accesso creati.</span><span class="sxs-lookup"><span data-stu-id="e61c1-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="e61c1-156">Il collegamento è permanente, ovvero lo stesso collegamento può essere usato nel tempo per i nuovi analisti.</span><span class="sxs-lookup"><span data-stu-id="e61c1-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="e61c1-157">La richiesta dell'analista entra in una coda per l'approvazione da parte dei responsabili approvazione **analista MSSP.**</span><span class="sxs-lookup"><span data-stu-id="e61c1-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Immagine delle proprietà di accesso](../../media/access-properties.png)

    <span data-ttu-id="e61c1-159">Il collegamento si trova nella pagina di panoramica di ogni pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="e61c1-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="e61c1-160">Gestire accessi</span><span class="sxs-lookup"><span data-stu-id="e61c1-160">Manage access</span></span> 

1. <span data-ttu-id="e61c1-161">Esaminare e autorizzare le richieste di accesso in Myaccess del cliente e/o del provider mssp.</span><span class="sxs-lookup"><span data-stu-id="e61c1-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="e61c1-162">Le richieste di accesso vengono gestite nel cliente Accesso personale dai membri del gruppo Responsabili approvazione analista MSSP.</span><span class="sxs-lookup"><span data-stu-id="e61c1-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="e61c1-163">A tale scopo, accedere all'accesso del cliente tramite:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="e61c1-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="e61c1-164">Esempio:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="e61c1-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="e61c1-165">Approvare o rifiutare le richieste nella **sezione Approvazioni** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e61c1-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="e61c1-166">A questo punto, è stato effettuato il provisioning dell'accesso dell'analista e ogni analista dovrebbe essere in grado di accedere al Centro sicurezza Microsoft 365 del cliente:</span><span class="sxs-lookup"><span data-stu-id="e61c1-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="e61c1-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` con le autorizzazioni e i ruoli a cui sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="e61c1-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e61c1-168">L'accesso delegato a Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365 attualmente consente l'accesso a un singolo tenant per finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="e61c1-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span> 