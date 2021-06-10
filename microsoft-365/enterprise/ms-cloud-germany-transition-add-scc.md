---
title: Informazioni sull'esperienza di eDiscovery durante la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Riepilogo: passaggi di migrazione di eDiscovery per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844251"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="f98dd-103">Informazioni sull'esperienza di eDiscovery durante la migrazione da Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="f98dd-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="f98dd-104">Nelle sezioni seguenti vengono fornite ulteriori informazioni sull'esperienza di eDiscovery durante il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi Office 365 nella nuova area data center tedesca.</span><span class="sxs-lookup"><span data-stu-id="f98dd-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="f98dd-105">Amministrazione di eDiscovery fino alla fase 4</span><span class="sxs-lookup"><span data-stu-id="f98dd-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="f98dd-106">Fino alla fase 4, il Centro sicurezza e conformità sarà completamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="f98dd-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="f98dd-107">Tutto il contenuto rimane ancora in Microsoft Cloud Germania ed è gestibile dal Centro sicurezza e conformità di Microsoft Cloud Germania ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="f98dd-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="f98dd-108">Esperienza di eDiscovery tra la fase 4 e la fine della fase 9</span><span class="sxs-lookup"><span data-stu-id="f98dd-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="f98dd-109">Dall'inizio della fase 4 fino al completamento della fase 9, le ricerche eDiscovery avranno esito negativo o restituiranno 0 risultati per i percorsi di SharePoint Online, OneDrive for Business e Exchange Online migrati.</span><span class="sxs-lookup"><span data-stu-id="f98dd-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="f98dd-110">Durante la migrazione, i clienti possono continuare a creare casi, blocchi, ricerche ed esportazioni nel [Centro sicurezza & conformità,](/microsoft-365/compliance/manage-legal-investigations)inclusa [ricerca contenuto.](/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="f98dd-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="f98dd-111">Tuttavia, le ricerche in SharePoint online, OneDrive for Business e Exchange Online di cui è stata eseguita la migrazione restituiranno 0 risultati o genereranno un errore.</span><span class="sxs-lookup"><span data-stu-id="f98dd-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="f98dd-112">Nel caso in cui una ricerca restituisca zero risultati o un errore durante la migrazione, eseguire l'azione seguente per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="f98dd-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="f98dd-113">Scaricare i siti direttamente dal sito SharePoint Online o OneDrive for Business seguendo le istruzioni in Scaricare file e cartelle da OneDrive [o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span><span class="sxs-lookup"><span data-stu-id="f98dd-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="f98dd-114">Questo metodo richiederà SharePoint di amministratore online o autorizzazioni di sola lettura per il sito.</span><span class="sxs-lookup"><span data-stu-id="f98dd-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="f98dd-115">Se vengono superati i limiti, come illustrato in Scaricare file e cartelle da OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)i clienti possono utilizzare il client di sincronizzazione di OneDrive for Business seguendo le indicazioni in Sincronizzare i file [di SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)e Teams con il computer .</span><span class="sxs-lookup"><span data-stu-id="f98dd-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="f98dd-116">Per ulteriori informazioni, vedere [eDiscovery sul posto in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span><span class="sxs-lookup"><span data-stu-id="f98dd-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="f98dd-117">Amministrazione di eDiscovery dopo la fase 9</span><span class="sxs-lookup"><span data-stu-id="f98dd-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="f98dd-118">**Si applica a:** Tutti i clienti che utilizzano eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f98dd-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="f98dd-119">Nella fase 9 verranno completati i passaggi finali per il passaggio alla nuova area data center tedesca.</span><span class="sxs-lookup"><span data-stu-id="f98dd-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="f98dd-120">In questa fase verrà eseguita la migrazione di tutti i componenti del servizio rimanenti.</span><span class="sxs-lookup"><span data-stu-id="f98dd-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="f98dd-121">Dopo la fase 9, l'uso del Centro sicurezza e conformità in Microsoft Cloud Germania (protection.office.de) non è più supportato.</span><span class="sxs-lookup"><span data-stu-id="f98dd-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="f98dd-122">Usa invece il nuovo [Centro sicurezza](https://security.microsoft.com/) o [Centro](https://compliance.microsoft.com/) conformità.</span><span class="sxs-lookup"><span data-stu-id="f98dd-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="f98dd-123">Tutti i dati sono stati migrati nei nuovi portali di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f98dd-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="f98dd-124">Step(s)</span><span class="sxs-lookup"><span data-stu-id="f98dd-124">Step(s)</span></span> | <span data-ttu-id="f98dd-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f98dd-125">Description</span></span> | <span data-ttu-id="f98dd-126">Impatto</span><span class="sxs-lookup"><span data-stu-id="f98dd-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="f98dd-127">Tutte le SharePoint online, OneDrive for Business e Exchange Online sono state migrate insieme al Centro sicurezza e conformità (SCC).</span><span class="sxs-lookup"><span data-stu-id="f98dd-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="f98dd-128">Tutte le attività di eDiscovery devono essere eseguite dal tenant globale.</span><span class="sxs-lookup"><span data-stu-id="f98dd-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="f98dd-129">Le ricerche avranno ora esito positivo al 100%.</span><span class="sxs-lookup"><span data-stu-id="f98dd-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="f98dd-130">Eventuali errori o errori devono seguire i normali canali di supporto.</span><span class="sxs-lookup"><span data-stu-id="f98dd-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="f98dd-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f98dd-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="f98dd-132">Criteri di conservazione di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f98dd-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="f98dd-133">**Si applica a:**  Tutti i clienti che hanno applicato un criterio di conservazione nell'ambito della procedura di pre-migrazione</span><span class="sxs-lookup"><span data-stu-id="f98dd-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="f98dd-134">Step(s)</span><span class="sxs-lookup"><span data-stu-id="f98dd-134">Step(s)</span></span> | <span data-ttu-id="f98dd-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f98dd-135">Description</span></span> | <span data-ttu-id="f98dd-136">Impatto</span><span class="sxs-lookup"><span data-stu-id="f98dd-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="f98dd-137">Rimuovere i criteri di conservazione a livello di organizzazione creati durante la procedura di pre-migrazione</span><span class="sxs-lookup"><span data-stu-id="f98dd-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="f98dd-138">I clienti possono rimuovere i criteri di conservazione a livello di organizzazione creati durante le attività di pre-migrazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="f98dd-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="f98dd-139">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f98dd-139">None</span></span> |
||||
