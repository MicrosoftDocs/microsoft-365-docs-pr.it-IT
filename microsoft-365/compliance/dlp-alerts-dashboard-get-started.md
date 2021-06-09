---
title: Introduzione alla dashboard degli avvisi per la prevenzione delle perdita dei dati
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Introduzione alla definizione e alla gestione degli avvisi per i criteri di prevenzione della perdita di dati.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843867"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="dc8b7-103">Introduzione alla dashboard degli avvisi per la prevenzione delle perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="dc8b7-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="dc8b7-104">I criteri di prevenzione della perdita dei dati (DLP) possono intraprendere azioni di protezione per impedire la condivisione involontaria di elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="dc8b7-105">Quando viene eseguita un'azione su un elemento sensibile, è possibile ricevere una notifica configurando gli avvisi per DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="dc8b7-106">In questo articolo viene illustrato come definire criteri di avviso rtf collegati ai criteri di prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="dc8b7-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="dc8b7-107">Vedrai come usare il dashboard di gestione [](https://compliance.microsoft.com/) degli avvisi [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) nel Centro conformità Microsoft 365 per visualizzare avvisi, eventi e metadati associati per le violazioni dei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="dc8b7-108">Se non si ha la novità degli avvisi DLP, vedere Informazioni sul dashboard degli avvisi di [prevenzione della perdita dei dati](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dc8b7-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dc8b7-109">Before you begin</span></span>

<span data-ttu-id="dc8b7-110">Prima di iniziare, verificare di disporre dei prerequisiti necessari:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="dc8b7-111">Gestione delle licenze per il dashboard di gestione degli avvisi DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="dc8b7-112">Licenze per le opzioni di configurazione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="dc8b7-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="dc8b7-113">Ruoli</span><span class="sxs-lookup"><span data-stu-id="dc8b7-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="dc8b7-114">Gestione delle licenze per il dashboard di gestione degli avvisi DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="dc8b7-115">Tutti i tenant idonei per Office 365 DLP possono accedere al dashboard di gestione degli avvisi DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="dc8b7-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="dc8b7-117">Per ulteriori informazioni sui requisiti di licenza per Office 365 DLP, vedere Quali licenze forniscono a un utente i diritti a [beneficiare del servizio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span><span class="sxs-lookup"><span data-stu-id="dc8b7-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="dc8b7-118">I clienti che usano [Endpoint DLP](endpoint-dlp-learn-about.md) idonei per [Teams DLP](dlp-microsoft-teams.md) visualizzano gli avvisi dei criteri DLP degli endpoint e Teams gli avvisi dei criteri DLP nel dashboard di gestione degli avvisi DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="dc8b7-119">La **funzionalità di anteprima** del contenuto è disponibile solo per queste licenze:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="dc8b7-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="dc8b7-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-121">Office 365 (E5)</span></span>
- <span data-ttu-id="dc8b7-122">Componente aggiuntivo Conformità avanzata (E5)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="dc8b7-123">Microsoft 365 E5/A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="dc8b7-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="dc8b7-124">Conformità Microsft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="dc8b7-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="dc8b7-125">Licenze per le opzioni di configurazione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="dc8b7-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="dc8b7-126">Configurazione degli avvisi a evento **singolo**: le organizzazioni con una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 possono creare criteri di avviso solo quando viene attivato un avviso ogni volta che si verifica un'attività.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="dc8b7-127">**Configurazione degli avvisi aggregati:** per configurare i criteri di avviso aggregati in base a una soglia, è necessario una delle configurazioni di licenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="dc8b7-128">Un abbonamento E5 o G5</span><span class="sxs-lookup"><span data-stu-id="dc8b7-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="dc8b7-129">Una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 che include una delle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="dc8b7-130">Office 365 Advanced Threat Protection (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="dc8b7-131">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dc8b7-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="dc8b7-132">Microsoft 365 licenza del componente aggiuntivo eDiscovery e controllo</span><span class="sxs-lookup"><span data-stu-id="dc8b7-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="dc8b7-133">Ruoli</span><span class="sxs-lookup"><span data-stu-id="dc8b7-133">Roles</span></span>


<span data-ttu-id="dc8b7-134">Se si desidera visualizzare il dashboard di gestione degli avvisi DLP o modificare le opzioni di configurazione degli avvisi in un criterio DLP, è necessario essere membri di uno di questi gruppi di ruoli:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="dc8b7-135">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="dc8b7-135">Compliance Administrator</span></span>
- <span data-ttu-id="dc8b7-136">Amministratore dei dati di conformità</span><span class="sxs-lookup"><span data-stu-id="dc8b7-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="dc8b7-137">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc8b7-137">Security Administrator</span></span>
- <span data-ttu-id="dc8b7-138">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc8b7-138">Security Operator</span></span>
- <span data-ttu-id="dc8b7-139">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc8b7-139">Security Reader</span></span>

<span data-ttu-id="dc8b7-140">Per accedere al dashboard di gestione degli avvisi DLP, è necessario:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="dc8b7-141">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="dc8b7-141">Manage alerts</span></span>

<span data-ttu-id="dc8b7-142">e uno di questi due ruoli:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-142">and either of these two roles:</span></span>

- <span data-ttu-id="dc8b7-143">Gestione della conformità DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-143">DLP Compliance Management</span></span>
- <span data-ttu-id="dc8b7-144">View-Only conformità DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="dc8b7-145">Per accedere alla funzionalità Anteprima contenuto e alle funzionalità contenuto sensibile e contesto corrispondenti, è necessario essere membri di:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="dc8b7-146">Gruppo di ruoli Visualizzatore contenuto di Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="dc8b7-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="dc8b7-147">che ha il ruolo visualizzatore contenuto per la classificazione dei dati preassato.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="dc8b7-148">Configurazione degli avvisi DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-148">DLP alert configuration</span></span>

<span data-ttu-id="dc8b7-149">Per informazioni su come configurare un avviso nel criterio DLP, vedere [Da dove iniziare con la prevenzione della perdita dei dati.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="dc8b7-150">Configurazione dell'avviso di evento aggregato</span><span class="sxs-lookup"><span data-stu-id="dc8b7-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="dc8b7-151">Se l'organizzazione ha una licenza per [le opzioni di](#licensing-for-alert-configuration-options)configurazione degli avvisi aggregati, queste opzioni verranno visualizzati quando si crea o si modifica un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

<span data-ttu-id="dc8b7-153">Questa configurazione consente di configurare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni dei criteri o quando viene superata una determinata soglia, in base al numero di attività o in base al volume di dati esfiltrati.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="dc8b7-154">Configurazione avviso evento singolo</span><span class="sxs-lookup"><span data-stu-id="dc8b7-154">Single event alert configuration</span></span>

<span data-ttu-id="dc8b7-155">Se l'organizzazione ha una licenza per [le opzioni](#licensing-for-alert-configuration-options)di configurazione degli avvisi a evento singolo, queste opzioni verranno visualizzati quando si crea o si modifica un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="dc8b7-156">Utilizzare questa opzione per creare un avviso generato ogni volta che si verifica una corrispondenza di una regola DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi a evento singolo." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="dc8b7-158">Analizzare un avviso DLP</span><span class="sxs-lookup"><span data-stu-id="dc8b7-158">Investigate a DLP alert</span></span>

<span data-ttu-id="dc8b7-159">Per utilizzare il dashboard di gestione degli avvisi DLP:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="dc8b7-160">Nel Centro [Microsoft 365 conformità](https://www.compliance.microsoft.com)passare a Prevenzione della perdita **di dati**.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="dc8b7-161">Selezionare la **scheda Avvisi** per visualizzare il dashboard degli avvisi DLP.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="dc8b7-162">Selezionare un avviso per visualizzare i dettagli:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot che mostra i dettagli dell'avviso nel dashboard di gestione degli avvisi DLP." border="false":::

4. <span data-ttu-id="dc8b7-164">Selezionare la **scheda** Eventi per visualizzare tutti gli eventi associati all'avviso.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="dc8b7-165">Puoi scegliere un evento specifico per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="dc8b7-166">Per un elenco di alcuni dei dettagli dell'evento disponibili, vedere Informazioni sul dashboard avvisi di prevenzione della [perdita di dati.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="dc8b7-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="dc8b7-167">Selezionare **Dettagli** per aprire la **pagina Panoramica** per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="dc8b7-168">La pagina di panoramica fornisce un riepilogo:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="dc8b7-169">di ciò che è successo</span><span class="sxs-lookup"><span data-stu-id="dc8b7-169">of what happened</span></span>
    1. <span data-ttu-id="dc8b7-170">che ha eseguito le azioni che hanno causato la corrispondenza dei criteri</span><span class="sxs-lookup"><span data-stu-id="dc8b7-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="dc8b7-171">informazioni sui criteri corrispondenti e altro ancora</span><span class="sxs-lookup"><span data-stu-id="dc8b7-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="dc8b7-172">Scegliere la **scheda** Eventi per accedere a:</span><span class="sxs-lookup"><span data-stu-id="dc8b7-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="dc8b7-173">contenuto coinvolto</span><span class="sxs-lookup"><span data-stu-id="dc8b7-173">content involved</span></span>
    1. <span data-ttu-id="dc8b7-174">tipi di informazioni riservate corrispondenti</span><span class="sxs-lookup"><span data-stu-id="dc8b7-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="dc8b7-175">metadati</span><span class="sxs-lookup"><span data-stu-id="dc8b7-175">metadata</span></span>

7. <span data-ttu-id="dc8b7-176">Selezionare la **scheda Tipi di informazioni riservate** per visualizzare i dettagli sui tipi di informazioni riservate rilevati nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="dc8b7-177">I dettagli includono la probabilità, il conteggio e il contenuto corrispondente al tipo di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="dc8b7-178">Dopo aver indagato sull'avviso, tornare alla scheda **Panoramica** in cui è possibile gestire la triage e gestire l'eliminazione dell'avviso e aggiungere commenti.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="dc8b7-179">Per visualizzare la cronologia della gestione del flusso di lavoro, scegliere **Registro di gestione**.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="dc8b7-180">Dopo aver evaso l'azione necessaria per l'avviso, impostare lo stato dell'avviso su **Risolto**.</span><span class="sxs-lookup"><span data-stu-id="dc8b7-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc8b7-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc8b7-181">See also</span></span>

- [<span data-ttu-id="dc8b7-182">Informazioni sugli avvisi di prevenzione della perdita di dati e sul dashboard degli avvisi</span><span class="sxs-lookup"><span data-stu-id="dc8b7-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="dc8b7-183">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="dc8b7-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)