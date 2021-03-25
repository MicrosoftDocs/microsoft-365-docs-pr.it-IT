---
title: Concedere l'accesso al provider del servizio di sicurezza gestito (MSSP)
description: Eseguire le operazioni necessarie per configurare l'integrazione di MSSP con Microsoft Defender ATP
keywords: provider di servizi di sicurezza gestiti, mssp, configurare, integrazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1bb7bc3565bbb7c05f165c5649f3672ff33bb18b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165454"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="8e894-104">Concedere l'accesso msSP (Managed Security Service Provider) (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8e894-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e894-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8e894-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e894-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8e894-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e894-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e894-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="8e894-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8e894-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8e894-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8e894-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="8e894-110">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="8e894-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8e894-111">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8e894-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8e894-112">Per implementare una soluzione di accesso delegato multi-tenant, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="8e894-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="8e894-113">Abilitare [il controllo dell'accesso](rbac.md) basato sui ruoli in Defender for Endpoint e connettersi ai gruppi di Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="8e894-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="8e894-114">Configurare i [pacchetti di accesso di](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) governance per la richiesta di accesso e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="8e894-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="8e894-115">Gestire le richieste di accesso e i controlli in [Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="8e894-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8e894-116">Abilitare i controlli di accesso basati sui ruoli in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e894-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="8e894-117">**Creare gruppi di accesso per le risorse MSSP in Customer AAD: Gruppi**</span><span class="sxs-lookup"><span data-stu-id="8e894-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="8e894-118">Questi gruppi verranno collegati ai ruoli creati in Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8e894-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="8e894-119">A tale scopo, nel tenant AD del cliente creare tre gruppi.</span><span class="sxs-lookup"><span data-stu-id="8e894-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="8e894-120">Nell'approccio di esempio vengono creati i gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e894-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="8e894-121">Analista di livello 1</span><span class="sxs-lookup"><span data-stu-id="8e894-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="8e894-122">Analista di livello 2</span><span class="sxs-lookup"><span data-stu-id="8e894-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="8e894-123">Responsabili approvazione analista MSSP</span><span class="sxs-lookup"><span data-stu-id="8e894-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="8e894-124">Creare ruoli defender per endpoint per i livelli di accesso appropriati in Customer Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8e894-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="8e894-125">Per abilitare RBAC nel cliente Microsoft Defender Security Center, accedere a Impostazioni **> Autorizzazioni > Ruoli** e "Attiva ruoli", da un account utente con diritti di amministratore globale o amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8e894-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Immagine dell'accesso MSSP](images/mssp-access.png)

    <span data-ttu-id="8e894-127">Creare quindi ruoli RBAC per soddisfare le esigenze del livello SOC MSSP.</span><span class="sxs-lookup"><span data-stu-id="8e894-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="8e894-128">Collegare questi ruoli ai gruppi di utenti creati tramite "Gruppi di utenti assegnati".</span><span class="sxs-lookup"><span data-stu-id="8e894-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="8e894-129">Due possibili ruoli:</span><span class="sxs-lookup"><span data-stu-id="8e894-129">Two possible roles:</span></span>

    - <span data-ttu-id="8e894-130">**Analisti di livello 1**</span><span class="sxs-lookup"><span data-stu-id="8e894-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="8e894-131">Eseguire tutte le azioni ad eccezione della risposta in tempo reale e gestire le impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8e894-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="8e894-132">**Analisti di livello 2**</span><span class="sxs-lookup"><span data-stu-id="8e894-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="8e894-133">Funzionalità di livello 1 con l'aggiunta della [risposta in tempo reale](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="8e894-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="8e894-134">Per ulteriori informazioni, vedere [Use role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="8e894-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="8e894-135">Configurare i pacchetti di accesso alla governance</span><span class="sxs-lookup"><span data-stu-id="8e894-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="8e894-136">**Aggiungere MSSP come organizzazione connessa in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="8e894-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="8e894-137">L'aggiunta di MSSP come organizzazione connessa consentirà al provider mssp di richiedere e disporre degli accessi di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="8e894-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="8e894-138">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Connected organization.</span><span class="sxs-lookup"><span data-stu-id="8e894-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="8e894-139">Aggiungere una nuova organizzazione e cercare il tenant dell'analista MSSP tramite l'ID tenant o il dominio.</span><span class="sxs-lookup"><span data-stu-id="8e894-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="8e894-140">Ti consigliamo di creare un tenant AD separato per gli analisti MSSP.</span><span class="sxs-lookup"><span data-stu-id="8e894-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="8e894-141">**Creare un catalogo delle risorse in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="8e894-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e894-142">I cataloghi delle risorse sono una raccolta logica di pacchetti di accesso, creati nel tenant AD del cliente.</span><span class="sxs-lookup"><span data-stu-id="8e894-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="8e894-143">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Catalogs e aggiungere **New Catalog.**</span><span class="sxs-lookup"><span data-stu-id="8e894-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="8e894-144">In questo esempio, verrà chiamato **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="8e894-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Immagine del nuovo catalogo](images/goverance-catalog.png)

    <span data-ttu-id="8e894-146">Per ulteriori informazioni, vedere [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span><span class="sxs-lookup"><span data-stu-id="8e894-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="8e894-147">**Creare pacchetti di accesso per le risorse MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="8e894-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e894-148">I pacchetti di accesso sono la raccolta di diritti e accessi a cui un richiedente verrà concesso all'approvazione.</span><span class="sxs-lookup"><span data-stu-id="8e894-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="8e894-149">A tale scopo, nel tenant AD del cliente, accedere a Identity Governance: Access Packages e aggiungere **New Access Package.**</span><span class="sxs-lookup"><span data-stu-id="8e894-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="8e894-150">Creare un pacchetto di accesso per i responsabili approvazione MSSP e ogni livello di analista.</span><span class="sxs-lookup"><span data-stu-id="8e894-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="8e894-151">Ad esempio, la configurazione dell'analista di livello 1 seguente crea un pacchetto di accesso che:</span><span class="sxs-lookup"><span data-stu-id="8e894-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="8e894-152">Richiede a un membro del gruppo AD **Responsabili approvazione analisti MSSP** di autorizzare nuove richieste</span><span class="sxs-lookup"><span data-stu-id="8e894-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="8e894-153">Ha revisioni di accesso annuali, in cui gli analisti SOC possono richiedere un'estensione di accesso</span><span class="sxs-lookup"><span data-stu-id="8e894-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="8e894-154">Può essere richiesto solo dagli utenti nel tenant SOC MSSP</span><span class="sxs-lookup"><span data-stu-id="8e894-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="8e894-155">Access scade automaticamente dopo 365 giorni</span><span class="sxs-lookup"><span data-stu-id="8e894-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8e894-156">![Immagine del nuovo pacchetto di accesso](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="8e894-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="8e894-157">Per ulteriori informazioni, vedere [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="8e894-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="8e894-158">**Fornire il collegamento della richiesta di accesso alle risorse MSSP da Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="8e894-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8e894-159">Il collegamento al portale My Access viene utilizzato dagli analisti SOC di MSSP per richiedere l'accesso tramite i pacchetti di accesso creati.</span><span class="sxs-lookup"><span data-stu-id="8e894-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="8e894-160">Il collegamento è durevole, ovvero lo stesso collegamento può essere utilizzato nel tempo per i nuovi analisti.</span><span class="sxs-lookup"><span data-stu-id="8e894-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="8e894-161">La richiesta dell'analista viene inviata in una coda per l'approvazione da parte dei responsabili approvazione degli analisti **MSSP.**</span><span class="sxs-lookup"><span data-stu-id="8e894-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8e894-162">![Immagine delle proprietà di accesso](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="8e894-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="8e894-163">Il collegamento si trova nella pagina di panoramica di ogni pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="8e894-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="8e894-164">Gestire accessi</span><span class="sxs-lookup"><span data-stu-id="8e894-164">Manage access</span></span> 

1. <span data-ttu-id="8e894-165">Esaminare e autorizzare le richieste di accesso in Customer e/o MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="8e894-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="8e894-166">Le richieste di accesso vengono gestite nel cliente Accesso personale dai membri del gruppo Responsabili approvazione analista MSSP.</span><span class="sxs-lookup"><span data-stu-id="8e894-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="8e894-167">A tale scopo, accedere all'account myaccess del cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="8e894-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="8e894-168">Esempio:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="8e894-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="8e894-169">Approvare o rifiutare le richieste nella **sezione Approvazioni** dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8e894-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="8e894-170">A questo punto, è stato effettuato il provisioning dell'accesso degli analisti e ogni analista dovrebbe essere in grado di accedere al Microsoft Defender Security Center del cliente: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="8e894-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e894-171">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8e894-171">Related topics</span></span>
- [<span data-ttu-id="8e894-172">Accedere al portale dei clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="8e894-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8e894-173">Configurare le notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="8e894-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="8e894-174">Recuperare gli avvisi dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="8e894-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

