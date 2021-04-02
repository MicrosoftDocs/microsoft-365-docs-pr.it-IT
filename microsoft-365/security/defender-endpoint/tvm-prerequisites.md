---
title: Prerequisiti per & autorizzazioni - gestione delle minacce e delle vulnerabilità
description: Prima di iniziare a utilizzare la gestione delle minacce e delle vulnerabilità, assicurarsi di disporre delle relative configurazioni e autorizzazioni.
keywords: prerequisiti & autorizzazioni di gestione delle vulnerabilità, prerequisiti per le autorizzazioni di gestione delle minacce e vulnerabilità, prerequisiti per le autorizzazioni MDATP TVM, gestione delle vulnerabilità
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1d9c3233f72541ccd0463eefef93bde5e7d9900f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499957"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="83770-104">Prerequisiti per & autorizzazioni - gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="83770-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83770-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="83770-105">**Applies to:**</span></span>

- [<span data-ttu-id="83770-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="83770-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="83770-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="83770-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="83770-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83770-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="83770-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="83770-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83770-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="83770-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="83770-111">Assicurati che i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="83770-111">Ensure that your devices:</span></span>

- <span data-ttu-id="83770-112">Vengono onboarded in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="83770-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="83770-113">Eseguire [sistemi operativi e piattaforme supportati](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="83770-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="83770-114">Installare e distribuire nella rete gli aggiornamenti obbligatori seguenti per aumentare la velocità di rilevamento della valutazione delle vulnerabilità:</span><span class="sxs-lookup"><span data-stu-id="83770-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="83770-115">Rilascio</span><span class="sxs-lookup"><span data-stu-id="83770-115">Release</span></span> | <span data-ttu-id="83770-116">Collegamento e numero KB dell'aggiornamento della sicurezza</span><span class="sxs-lookup"><span data-stu-id="83770-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="83770-117">Windows 10 versione 1709</span><span class="sxs-lookup"><span data-stu-id="83770-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="83770-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) e [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="83770-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="83770-119">Windows 10 versione 1803</span><span class="sxs-lookup"><span data-stu-id="83770-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="83770-120">[KB4493464](https://support.microsoft.com/help/4493464) e [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="83770-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="83770-121">Windows 10 versione 1809</span><span class="sxs-lookup"><span data-stu-id="83770-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="83770-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="83770-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="83770-123">Windows 10 versione 1903</span><span class="sxs-lookup"><span data-stu-id="83770-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="83770-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="83770-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="83770-125">Vengono onboarded in [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e Microsoft Endpoint  [Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) per correggere le minacce rilevate dalla gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="83770-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="83770-126">Se si usa Configuration Manager, aggiornare la console alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="83770-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="83770-127">**Nota:** se la connessione intune è abilitata, si ottiene un'opzione per creare un'attività di sicurezza di Intune durante la creazione di una richiesta di correzione.</span><span class="sxs-lookup"><span data-stu-id="83770-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="83770-128">Questa opzione non viene visualizzata se la connessione non è impostata.</span><span class="sxs-lookup"><span data-stu-id="83770-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="83770-129">Avere almeno un consiglio di sicurezza che può essere visualizzato nella pagina del dispositivo</span><span class="sxs-lookup"><span data-stu-id="83770-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="83770-130">Sono contrassegnati o contrassegnati come co-gestiti</span><span class="sxs-lookup"><span data-stu-id="83770-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="83770-131">Opzioni di autorizzazione pertinenti</span><span class="sxs-lookup"><span data-stu-id="83770-131">Relevant permission options</span></span>

1. <span data-ttu-id="83770-132">Accedere a Microsoft Defender Security Center con un account con un amministratore della sicurezza o un ruolo amministratore globale assegnato.</span><span class="sxs-lookup"><span data-stu-id="83770-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="83770-133">Nel riquadro di spostamento selezionare **Impostazioni > ruoli**.</span><span class="sxs-lookup"><span data-stu-id="83770-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="83770-134">Per ulteriori informazioni, vedere [Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="83770-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="83770-135">Visualizzare i dati</span><span class="sxs-lookup"><span data-stu-id="83770-135">View data</span></span>

- <span data-ttu-id="83770-136">**Operazioni di sicurezza** - Visualizzare tutti i dati relativi alle operazioni di sicurezza nel portale</span><span class="sxs-lookup"><span data-stu-id="83770-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="83770-137">**Gestione delle minacce e delle vulnerabilità** - Visualizzare i dati di gestione delle minacce e delle vulnerabilità nel portale</span><span class="sxs-lookup"><span data-stu-id="83770-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="83770-138">Azioni di correzione attive</span><span class="sxs-lookup"><span data-stu-id="83770-138">Active remediation actions</span></span>

- <span data-ttu-id="83770-139">**Operazioni di sicurezza:** eseguire azioni di risposta, approvare o ignorare le azioni di correzione in sospeso, gestire gli elenchi consentiti/bloccati per l'automazione e gli indicatori</span><span class="sxs-lookup"><span data-stu-id="83770-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="83770-140">**Gestione delle minacce e delle vulnerabilità - Gestione delle eccezioni** - Creare nuove eccezioni e gestire le eccezioni attive</span><span class="sxs-lookup"><span data-stu-id="83770-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="83770-141">**Gestione delle minacce e delle** vulnerabilità - Gestione delle correzioni - Inviare nuove richieste di correzione, creare ticket e gestire le attività di correzione esistenti</span><span class="sxs-lookup"><span data-stu-id="83770-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="83770-142">Per ulteriori informazioni, vedere [Opzioni di autorizzazione RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="83770-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="83770-143">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="83770-143">Related articles</span></span>

- [<span data-ttu-id="83770-144">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="83770-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="83770-145">Sistemi operativi e piattaforme supportati</span><span class="sxs-lookup"><span data-stu-id="83770-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="83770-146">Assegnare un valore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="83770-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="83770-147">Dashboard di gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="83770-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

