---
title: Usare lo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Informazioni su come usare la prevenzione della perdita dei dati di Microsoft 365 nello scanner locale per analizzare i dati inattivi e implementare azioni di protezione per le condivisioni di file locali e le cartelle e raccolte documenti di SharePoint locali.
ms.openlocfilehash: 34be93f5c9980a7f8ea8ad31b708af14a8725f73
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417363"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="628d2-103">Usare lo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="628d2-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="628d2-104">Per acquisire familiarità con le funzionalità locali di prevenzione della perdita dei dati (DPL) e su come vengono visualizzate nei criteri DLP, sono stati predisposti alcuni scenari da seguire.</span><span class="sxs-lookup"><span data-stu-id="628d2-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="628d2-105">Questi scenari locali DLP non costituiscono le procedure ufficiali per la creazione e l'ottimizzazione di criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="628d2-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="628d2-106">Vedere gli argomenti seguenti quando è necessario usare i criteri di prevenzione della perdita dei dati in situazioni generiche:</span><span class="sxs-lookup"><span data-stu-id="628d2-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="628d2-107">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-107">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="628d2-108">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="628d2-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="628d2-109">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="628d2-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="628d2-110">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="628d2-111">Scenario: individuare i file che corrispondono alle regole di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="628d2-112">I dati dello scanner locale DPL vengono visualizzati in diverse aree</span><span class="sxs-lookup"><span data-stu-id="628d2-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="628d2-113">Esplora attività</span><span class="sxs-lookup"><span data-stu-id="628d2-113">Activity explorer</span></span>

 <span data-ttu-id="628d2-114">La prevenzione della perdita dei dati Microsoft per le soluzioni locali rileva le corrispondenze DPL e le segnala a [Esplora attività](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="628d2-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="628d2-115">Log di audit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="628d2-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="628d2-116">Durante l'anteprima pubblica, le corrispondenze delle regole DPL sono disponibili nell'interfaccia utente del log di audit, vedere [Individuare i log di audit nel Centro conformità](search-the-audit-log-in-security-and-compliance.md) o accessibili tramite PowerShell [Search UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="628d2-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="628d2-117">AIP</span><span class="sxs-lookup"><span data-stu-id="628d2-117">AIP</span></span>

<span data-ttu-id="628d2-118">I dati di individuazione sono disponibili in un report locale in formato CSV archiviato in:</span><span class="sxs-lookup"><span data-stu-id="628d2-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="628d2-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="628d2-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="628d2-120">Cercare le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="628d2-120">Look for the following columns:</span></span>
- <span data-ttu-id="628d2-121">Modalità DPL</span><span class="sxs-lookup"><span data-stu-id="628d2-121">DLP Mode</span></span>
- <span data-ttu-id="628d2-122">Stato DPL</span><span class="sxs-lookup"><span data-stu-id="628d2-122">DLP Status</span></span>
- <span data-ttu-id="628d2-123">Commento DPL</span><span class="sxs-lookup"><span data-stu-id="628d2-123">DLP Comment</span></span>
- <span data-ttu-id="628d2-124">Nome delle regole DPL per azioni DPL</span><span class="sxs-lookup"><span data-stu-id="628d2-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="628d2-125">Proprietario</span><span class="sxs-lookup"><span data-stu-id="628d2-125">Owner</span></span>
- <span data-ttu-id="628d2-126">Autorizzazioni NTFS correnti (SDDL)</span><span class="sxs-lookup"><span data-stu-id="628d2-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="628d2-127">Autorizzazioni NTFS applicate (SDDL)</span><span class="sxs-lookup"><span data-stu-id="628d2-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="628d2-128">Tipo di autorizzazioni NTFS</span><span class="sxs-lookup"><span data-stu-id="628d2-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="628d2-129">Scenario: applicazione delle regole di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="628d2-130">Per applicare le regole DPL ai file analizzati, occorre abilitare l'applicazione sia nel processo di analisi dei contenuti in AIP che a livello di criteri in DLP.</span><span class="sxs-lookup"><span data-stu-id="628d2-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="628d2-131">Configurare la prevenzione della perdita dei dati per l'applicazione delle azioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="628d2-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="628d2-132">Aprire la [pagina della Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies) e selezionare i criteri DPL destinati ai repository delle posizioni locali configurati in AIP.</span><span class="sxs-lookup"><span data-stu-id="628d2-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="628d2-133">Modificare il criterio.</span><span class="sxs-lookup"><span data-stu-id="628d2-133">Edit the policy.</span></span>
3. <span data-ttu-id="628d2-134">Nella pagina **Testare o abilitare il criterio** selezionare **Sì, abilitalo immediatamente**.</span><span class="sxs-lookup"><span data-stu-id="628d2-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="628d2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="628d2-135">See also</span></span>

- [<span data-ttu-id="628d2-136">Informazioni sullo scanner locale per la prevenzione della perdita dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="628d2-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="628d2-137">Introduzione allo scanner DPL locale (anteprima)</span><span class="sxs-lookup"><span data-stu-id="628d2-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="628d2-138">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-138">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="628d2-139">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="628d2-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="628d2-140">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="628d2-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
