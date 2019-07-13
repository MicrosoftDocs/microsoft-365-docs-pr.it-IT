---
title: Dettagli del tenant di Azure Active Directory
description: In questo argomento vengono descritte le modifiche apportate all'account AAD quando si effettua la registrazione in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643947"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="d0dee-104">Dettagli del tenant di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0dee-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="d0dee-105">{dettagli cruenti sugli account, le chiamate API, le permanenti e così via, ecc.}</span><span class="sxs-lookup"><span data-stu-id="d0dee-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="d0dee-106">Dati trasmessi da e verso l'account AAD</span><span class="sxs-lookup"><span data-stu-id="d0dee-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="d0dee-107">Dati inviati all'account da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d0dee-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="d0dee-108">Nomi di gruppi</span><span class="sxs-lookup"><span data-stu-id="d0dee-108">Group names</span></span>
- <span data-ttu-id="d0dee-109">Configurazione del criterio di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0dee-109">Security policy configuration</span></span>
- <span data-ttu-id="d0dee-110">Ordini di dispositivi</span><span class="sxs-lookup"><span data-stu-id="d0dee-110">Device orders</span></span>
- <span data-ttu-id="d0dee-111">Account utente (MSadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="d0dee-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="d0dee-112">Assegnazione della licenza E5 agli account utente</span><span class="sxs-lookup"><span data-stu-id="d0dee-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="d0dee-113">Criteri di Windows Update per gli anelli di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d0dee-113">Windows update policies for update rings</span></span>

<span data-ttu-id="d0dee-114">Dati inviati a Microsoft dall'account:</span><span class="sxs-lookup"><span data-stu-id="d0dee-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="d0dee-115">Aggiornamento dei dispositivi, dati di utilizzo e affidabilità</span><span class="sxs-lookup"><span data-stu-id="d0dee-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="d0dee-116">Dati di distribuzione e affidabilità delle app</span><span class="sxs-lookup"><span data-stu-id="d0dee-116">App deployment and reliability data</span></span>
- <span data-ttu-id="d0dee-117">Dati sulla distribuzione dei criteri di aggiornamento e di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d0dee-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="d0dee-118">Utenti assegnati ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="d0dee-118">Users assigned to devices</span></span>  

<span data-ttu-id="d0dee-119">I dati trasmessi dall'account sono archiviati nei database SQL di Azure nel tenant Microsoft ospitato negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="d0dee-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="d0dee-120">I dati vengono archiviati e gestiti secondo i criteri descritti in {Microsoft Azure Security}.</span><span class="sxs-lookup"><span data-stu-id="d0dee-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="d0dee-121">Autorizzazioni e chiamate API</span><span class="sxs-lookup"><span data-stu-id="d0dee-121">API permissions and calls</span></span>

<span data-ttu-id="d0dee-122">**Durante la registrazione:**</span><span class="sxs-lookup"><span data-stu-id="d0dee-122">**During enrollment:**</span></span>

<span data-ttu-id="d0dee-123">Autorizzazioni API:</span><span class="sxs-lookup"><span data-stu-id="d0dee-123">API permissions:</span></span>
- <span data-ttu-id="d0dee-124">DeviceManagementServiceConfig. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-125">Directory. AccessAsUser. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="d0dee-126">User. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-127">DeviceManagementConfiguration. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-128">DeviceManagementManagedDevices. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-129">Group. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="d0dee-130">Chiamate API:</span><span class="sxs-lookup"><span data-stu-id="d0dee-130">API calls:</span></span>
- <span data-ttu-id="d0dee-131">POST/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="d0dee-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="d0dee-132">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="d0dee-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="d0dee-133">GET/POST/Users</span><span class="sxs-lookup"><span data-stu-id="d0dee-133">GET/POST /users</span></span>
- <span data-ttu-id="d0dee-134">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="d0dee-134">GET/POST /groups</span></span>
- <span data-ttu-id="d0dee-135">PATCH/groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="d0dee-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="d0dee-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="d0dee-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="d0dee-137">OTTENERE/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="d0dee-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="d0dee-138">**Dopo la registrazione, durante la gestione ordinaria:**</span><span class="sxs-lookup"><span data-stu-id="d0dee-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="d0dee-139">Autorizzazioni API:</span><span class="sxs-lookup"><span data-stu-id="d0dee-139">API permissions:</span></span>
- <span data-ttu-id="d0dee-140">DeviceManagementManagedDevices. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-141">DeviceManagementApps. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-142">DeviceManagementConfiguration. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-143">Reports. Read. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-143">Reports.Read.All</span></span>
- <span data-ttu-id="d0dee-144">User. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-145">Group. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="d0dee-146">Directory. AccessAsUser. All</span><span class="sxs-lookup"><span data-stu-id="d0dee-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="d0dee-147">Chiamate API:</span><span class="sxs-lookup"><span data-stu-id="d0dee-147">API calls:</span></span>
- <span data-ttu-id="d0dee-148">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="d0dee-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="d0dee-149">GET/PATCH/POST/Users</span><span class="sxs-lookup"><span data-stu-id="d0dee-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="d0dee-150">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="d0dee-150">GET/POST /groups</span></span>
- <span data-ttu-id="d0dee-151">PATCH/groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="d0dee-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="d0dee-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="d0dee-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="d0dee-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="d0dee-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="d0dee-154">OTTENERE/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="d0dee-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="d0dee-155">OTTENERE/Devices</span><span class="sxs-lookup"><span data-stu-id="d0dee-155">GET /devices</span></span>
- <span data-ttu-id="d0dee-156">POST/Users/{ID | userPrincipalName}/assignLicense</span><span class="sxs-lookup"><span data-stu-id="d0dee-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="d0dee-157">OTTENERE/subscribedSkus</span><span class="sxs-lookup"><span data-stu-id="d0dee-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="d0dee-158">Account utilizzati da Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d0dee-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="d0dee-159">Account</span><span class="sxs-lookup"><span data-stu-id="d0dee-159">Account</span></span> | <span data-ttu-id="d0dee-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0dee-160">Description</span></span>  | <span data-ttu-id="d0dee-161">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d0dee-161">Conditional access</span></span>  | <span data-ttu-id="d0dee-162">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="d0dee-162">Multi-factor authentication</span></span>  | <span data-ttu-id="d0dee-163">Perché questo è OK</span><span class="sxs-lookup"><span data-stu-id="d0dee-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="d0dee-164">MSadmin @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="d0dee-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="d0dee-165">Account del servizio limitato con privilegi di amministratore, utilizzato come amministratore di Microsoft Intune e utente {che cos'è?}</span><span class="sxs-lookup"><span data-stu-id="d0dee-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="d0dee-166">per definire e configurare il tenant per i dispositivi desktop Microsoft moderni.</span><span class="sxs-lookup"><span data-stu-id="d0dee-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="d0dee-167">Non dispone di autorizzazioni di accesso interattive; esegue operazioni solo tramite il servizio.</span><span class="sxs-lookup"><span data-stu-id="d0dee-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="d0dee-168">Escluso, perché non è originato dalla rete</span><span class="sxs-lookup"><span data-stu-id="d0dee-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="d0dee-169">Escluso perché non è disponibile alcun accesso interattivo</span><span class="sxs-lookup"><span data-stu-id="d0dee-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="d0dee-170">Password memorizzata in Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="d0dee-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="d0dee-171">MSTest @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="d0dee-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="d0dee-172">mssupport @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="d0dee-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="d0dee-173">msadminint @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="d0dee-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
