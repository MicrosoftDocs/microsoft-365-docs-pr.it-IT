---
title: Gestire i criteri delle app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Gestire i criteri di governance delle app.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420400"
---
# <a name="manage-app-policies"></a><span data-ttu-id="9ac6f-103">Gestire i criteri delle app</span><span class="sxs-lookup"><span data-stu-id="9ac6f-103">Manage app policies</span></span>

><span data-ttu-id="9ac6f-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="9ac6f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9ac6f-105">Per restare al passo con le app più recenti che l'organizzazione usa, rispondere a nuovi attacchi basati su app e per le continue modifiche alle esigenze di conformità delle app, potrebbe essere necessario gestire i criteri delle app in questi modi:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="9ac6f-106">Crea nuovi criteri destinati alle nuove app</span><span class="sxs-lookup"><span data-stu-id="9ac6f-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="9ac6f-107">Modifica lo stato di un criterio esistente (attivo, inattivo, modalità di controllo)</span><span class="sxs-lookup"><span data-stu-id="9ac6f-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="9ac6f-108">Modifica le condizioni di un criterio esistente</span><span class="sxs-lookup"><span data-stu-id="9ac6f-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="9ac6f-109">Modifica le azioni di un criterio esistente per la correzione automatica degli avvisi</span><span class="sxs-lookup"><span data-stu-id="9ac6f-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="9ac6f-110">Ecco un esempio di processo per la gestione di un criterio esistente:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="9ac6f-111">Modifica il criterio:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-111">Edit the policy:</span></span>

  - <span data-ttu-id="9ac6f-112">Modifica le impostazioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="9ac6f-113">Se necessario, modifica lo stato in **modalità di controllo** per i test.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="9ac6f-114">Verifica il comportamento previsto, ad esempio gli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="9ac6f-115">Se il comportamento non è previsto, torna al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="9ac6f-116">Se il comportamento è previsto, modifica il criterio e modificane lo stato in attivo (se necessario).</span><span class="sxs-lookup"><span data-stu-id="9ac6f-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![Flusso di lavoro per la gestione dei criteri dell'app](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="9ac6f-118">Modifica di una configurazione dei criteri dell'app</span><span class="sxs-lookup"><span data-stu-id="9ac6f-118">Editing an app policy configuration</span></span>

<span data-ttu-id="9ac6f-119">Per modificare la configurazione di un criterio app esistente:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="9ac6f-120">Seleziona il criterio nell'elenco dei criteri e quindi seleziona **Modifica** nel riquadro dei criteri dell'app.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="9ac6f-121">Seleziona i puntini di sospensione verticali per il criterio nell'elenco, e quindi seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="9ac6f-122">Per la pagina **Modifica criterio**, scorri le pagine e apporta le modifiche appropriate:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="9ac6f-123">**Descrizione**: modifica la descrizione per semplificare la comprensione dello scopo del criterio.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="9ac6f-124">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="9ac6f-124">**Severity**</span></span>
- <span data-ttu-id="9ac6f-125">**Impostazioni dei criteri**: modifica il set di app a cui si applicano i criteri.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="9ac6f-126">È anche possibile scegliere di usare le condizioni esistenti o di modificare le condizioni</span><span class="sxs-lookup"><span data-stu-id="9ac6f-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="9ac6f-127">**Azioni**: modifica l'azione di correzione automatica per gli avvisi generati dai criteri.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="9ac6f-128">**Stato**: modifica lo stato dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="9ac6f-129">Eliminazione di un criterio dell'app</span><span class="sxs-lookup"><span data-stu-id="9ac6f-129">Deleting an app policy</span></span>

<span data-ttu-id="9ac6f-130">Per eliminare un criterio dell'app, puoi fare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ac6f-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="9ac6f-131">Seleziona il criterio nell'elenco dei criteri e seleziona **Elimina** nel riquadro dei criteri dell'app.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="9ac6f-132">Seleziona i puntini di sospensione verticali per il criterio nell'elenco e quindi seleziona **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="9ac6f-133">Un'alternativa all'eliminazione di un criterio dell'app consiste nel modificarne lo stato in inattivo.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="9ac6f-134">Una volta inattivo, non genererà avvisi.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="9ac6f-135">Ad esempio, invece di eliminare un criterio app per un'app con un set specifico di condizioni utili per un criterio futuro, rinomina il criterio dell'app per indicarne l'utilità e impostarne lo stato su inattivo.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="9ac6f-136">In un secondo momento è possibile tornare al criterio e modificarlo per un'app simile e impostarne lo stato sulla modalità di controllo o inattivo.</span><span class="sxs-lookup"><span data-stu-id="9ac6f-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
