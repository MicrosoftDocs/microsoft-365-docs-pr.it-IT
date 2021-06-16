---
title: Attività post-migrazione per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: attività post-migrazione dopo il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a servizi Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930416"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="853da-103">Attività post-migrazione per la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="853da-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="853da-104">Le sezioni seguenti forniscono attività post-migrazione per più servizi dopo il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a servizi Office 365 nella nuova area data center tedesca.</span><span class="sxs-lookup"><span data-stu-id="853da-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="853da-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="853da-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="853da-106">Autenticazione federata di Azure AD con ADFS</span><span class="sxs-lookup"><span data-stu-id="853da-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="853da-107">**Si applica a:** Tutti i clienti che usano l'autenticazione federata con ADFS</span><span class="sxs-lookup"><span data-stu-id="853da-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="853da-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="853da-108">Step(s)</span></span> | <span data-ttu-id="853da-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853da-109">Description</span></span> | <span data-ttu-id="853da-110">Impatto</span><span class="sxs-lookup"><span data-stu-id="853da-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="853da-111">Rimuovere attendibilità relying party da Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="853da-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="853da-112">Al termine del cut-over ad Azure AD, l'organizzazione usa completamente i servizi Office 365 e non è più connessa a Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="853da-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="853da-113">A questo punto, il cliente deve rimuovere l'attendibilità del relying party per gli endpoint di Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="853da-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="853da-114">Questa operazione può essere eseguita solo quando nessuna delle applicazioni del cliente punta agli endpoint di Microsoft Cloud Deutschland quando Azure AD viene utilizzato come provider di identità (IdP).</span><span class="sxs-lookup"><span data-stu-id="853da-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="853da-115">Organizzazioni con autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="853da-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="853da-116">Approvazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="853da-116">Group approvals</span></span>
<span data-ttu-id="853da-117">**Si applica a:** Utenti finali le cui richieste di approvazione di gruppo di Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione</span><span class="sxs-lookup"><span data-stu-id="853da-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="853da-118">Step(s)</span><span class="sxs-lookup"><span data-stu-id="853da-118">Step(s)</span></span> | <span data-ttu-id="853da-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853da-119">Description</span></span> | <span data-ttu-id="853da-120">Impatto</span><span class="sxs-lookup"><span data-stu-id="853da-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="853da-121">Le richieste di partecipazione a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere nuovamente richieste se la richiesta originale non è stata approvata.</span><span class="sxs-lookup"><span data-stu-id="853da-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="853da-122">Se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione, i clienti dell'utente finale dovranno usare il pannello di accesso per inviare di nuovo una richiesta di partecipazione a un gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="853da-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="853da-123">Come utente finale:</span><span class="sxs-lookup"><span data-stu-id="853da-123">As an end-user:</span></span> <ol><li><span data-ttu-id="853da-124">Passare a [Pannello di accesso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="853da-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="853da-125">Trovare un gruppo di Azure AD per il quale l'approvazione dell'appartenenza era in sospeso durante i 30 giorni precedenti la migrazione.</span><span class="sxs-lookup"><span data-stu-id="853da-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="853da-126">Richiedere di aggiungere di nuovo il gruppo di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="853da-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="853da-127">Le richieste di partecipazione a un gruppo attivo meno di 30 giorni prima della migrazione non possono essere approvate, a meno che non vengano richieste di nuovo dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="853da-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="853da-128">Aggiornamenti DNS personalizzati</span><span class="sxs-lookup"><span data-stu-id="853da-128">Custom DNS updates</span></span>
<span data-ttu-id="853da-129">**Si applica a:**  Tutti i clienti che gestiscono le proprie zone DNS</span><span class="sxs-lookup"><span data-stu-id="853da-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="853da-130">Step(s)</span><span class="sxs-lookup"><span data-stu-id="853da-130">Step(s)</span></span> | <span data-ttu-id="853da-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853da-131">Description</span></span> | <span data-ttu-id="853da-132">Impatto</span><span class="sxs-lookup"><span data-stu-id="853da-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="853da-133">Aggiornare i servizi DNS locali per Office 365 endpoint dei servizi locali.</span><span class="sxs-lookup"><span data-stu-id="853da-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="853da-134">Le voci DNS gestite dal cliente che puntano a Microsoft Cloud Deutschland devono essere aggiornate in modo che puntino Office 365 endpoint dei servizi globali.</span><span class="sxs-lookup"><span data-stu-id="853da-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="853da-135">Fare riferimento a [Domini nell'Microsoft 365 di amministrazione](https://admin.microsoft.com/Adminportal/Home#/Domains) e applicare le modifiche nella configurazione DNS.</span><span class="sxs-lookup"><span data-stu-id="853da-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="853da-136">L'esito negativo di questa operazione può causare un errore del servizio o dei client software.</span><span class="sxs-lookup"><span data-stu-id="853da-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="853da-137">Servizi di terze parti</span><span class="sxs-lookup"><span data-stu-id="853da-137">Third-party services</span></span>
<span data-ttu-id="853da-138">**Si applica a:** Clienti che usano servizi di terze parti per Office 365 endpoint dei servizi</span><span class="sxs-lookup"><span data-stu-id="853da-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="853da-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="853da-139">Step(s)</span></span> | <span data-ttu-id="853da-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853da-140">Description</span></span> | <span data-ttu-id="853da-141">Impatto</span><span class="sxs-lookup"><span data-stu-id="853da-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="853da-142">Aggiornare i partner e i servizi di terze parti per Office 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="853da-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="853da-143">I servizi e i partner di terze parti che puntano a Office 365 Germania devono essere aggiornati per puntare agli endpoint Office 365 services.</span><span class="sxs-lookup"><span data-stu-id="853da-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="853da-144">Esempio: registrare di nuovo, in linea con i fornitori e i partner, la versione dell'app raccolta delle applicazioni, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="853da-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="853da-145">Puntare tutte le applicazioni personalizzate che sfruttano Graph API da `graph.microsoft.de` a `graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="853da-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="853da-146">Anche altre API con endpoint modificati devono essere aggiornate, se sfruttate.</span><span class="sxs-lookup"><span data-stu-id="853da-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="853da-147">Modificare tutte le applicazioni aziendali non di prima parte in modo che reindirizzano agli endpoint globali.</span><span class="sxs-lookup"><span data-stu-id="853da-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="853da-148">Azione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="853da-148">Required action.</span></span> <span data-ttu-id="853da-149">L'esito negativo di questa operazione può causare un errore del servizio o dei client software.</span><span class="sxs-lookup"><span data-stu-id="853da-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||