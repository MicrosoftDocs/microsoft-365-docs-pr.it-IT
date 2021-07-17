---
title: Creare criteri per le app
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
description: Creare criteri per le app.
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438061"
---
# <a name="create-app-policies"></a><span data-ttu-id="69a0a-103">Creare criteri per le app</span><span class="sxs-lookup"><span data-stu-id="69a0a-103">Create app policies</span></span>

><span data-ttu-id="69a0a-104">*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="69a0a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="69a0a-105">Oltre a un set predefinito di funzionalità per rilevare il comportamento anomalo delle app e generare avvisi, i criteri delle app nella governance delle app Microsoft sono un modo per:</span><span class="sxs-lookup"><span data-stu-id="69a0a-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="69a0a-106">Specificare le condizioni in base alle quali la governance delle app può avvisare l'utente del comportamento dell'app per la correzione automatica o manuale.</span><span class="sxs-lookup"><span data-stu-id="69a0a-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="69a0a-107">Implementare i criteri di conformità delle app per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="69a0a-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="69a0a-108">È possibile creare criteri per le app dai modelli forniti personalizzabili oppure è possibile creare criteri personalizzati per le app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="69a0a-109">Per creare un nuovo criterio dell'app, passare a **Centro conformità Microsoft 365 > Governance delle app > Panoramica > Criteri**:</span><span class="sxs-lookup"><span data-stu-id="69a0a-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="69a0a-110">Per creare un nuovo criterio dell'app con modelli progettati per l'utilizzo dell'app, selezionare **Crea criterio** in **Crea un criterio di utilizzo delle app**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="69a0a-111">Per creare un nuovo criterio dell'app con modelli progettati per il permesso dell'app, selezionare **Crea criterio** in **Crea un criterio di permesso delle app**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="69a0a-112">Per creare un nuovo criterio dell'app per la certificazione dell'app o un criterio personalizzato, selezionare **Crea nuovo**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="69a0a-113">Modelli di criteri per le app</span><span class="sxs-lookup"><span data-stu-id="69a0a-113">App policy templates</span></span>

<span data-ttu-id="69a0a-114">Per creare un nuovo criterio dell'app basato su un modello di criteri dell'app, nella pagina **Scegli modello di criteri dell'app** selezionare una categoria di modello di app, selezionare il nome del modello e infine scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="69a0a-115">La governance delle app include tre categorie di modelli di criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="69a0a-116">Utenti dell'app e accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="69a0a-116">App users and data access</span></span>

<span data-ttu-id="69a0a-117">La governance delle app include questi modelli per generare avvisi per l'utilizzo delle app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="69a0a-118">Nome modello</span><span class="sxs-lookup"><span data-stu-id="69a0a-118">Template name</span></span> | <span data-ttu-id="69a0a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69a0a-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="69a0a-120">Nuova app con un volume elevato di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="69a0a-120">New app with a high volume of data access</span></span> | <span data-ttu-id="69a0a-121">Evidenzia tutte le app registrate di recente con accesso a grandi volumi di dati per garantire che siano previsti tali modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="69a0a-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="69a0a-p101">Per impostazione predefinita, questo criterio contrassegnerà tutte le app registrate negli ultimi 7 giorni e che hanno avuto più di 1 GB di accesso ai dati in quel periodo. Questo criterio può essere personalizzato con più condizioni e azioni.</span><span class="sxs-lookup"><span data-stu-id="69a0a-p101">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period. This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="69a0a-124">Autorizzazioni app</span><span class="sxs-lookup"><span data-stu-id="69a0a-124">App Permissions</span></span>

<span data-ttu-id="69a0a-125">La governance delle app include questi modelli per generare avvisi per le autorizzazioni delle app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="69a0a-126">Nome modello</span><span class="sxs-lookup"><span data-stu-id="69a0a-126">Template name</span></span> | <span data-ttu-id="69a0a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69a0a-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="69a0a-128">App con privilegi eccessivi</span><span class="sxs-lookup"><span data-stu-id="69a0a-128">Overprivileged apps</span></span> | <span data-ttu-id="69a0a-129">Evidenzia tutte le app con più autorizzazioni concesse rispetto a quelle usate dalle app in modo da identificare opportunità di riduzione potenziale delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="69a0a-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="69a0a-130">Per impostazione predefinita, questo criterio contrassegnerà tutte le app contrassegnate con privilegi eccessivi se non usate per 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="69a0a-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="69a0a-131">Questo filtro del periodo di tempo può essere personalizzato con più condizioni e azioni.</span><span class="sxs-lookup"><span data-stu-id="69a0a-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="69a0a-132">Nuova app con autorizzazioni di privilegio elevato</span><span class="sxs-lookup"><span data-stu-id="69a0a-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="69a0a-133">Evidenzia tutte le nuove app che hanno autorizzazioni con privilegi elevati in modo da identificare quali sono le app più adottate che potrebbe essere necessario controllare.</span><span class="sxs-lookup"><span data-stu-id="69a0a-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="69a0a-134">Per impostazione predefinita, questo criterio contrassegnerà tutte le app registrate negli ultimi 7 giorni che dispongono di autorizzazioni di ambito elevato.</span><span class="sxs-lookup"><span data-stu-id="69a0a-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="69a0a-135">Certificazione delle app</span><span class="sxs-lookup"><span data-stu-id="69a0a-135">App certification</span></span>

<span data-ttu-id="69a0a-136">La governance delle app include questi modelli per generare avvisi per la certificazione delle app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="69a0a-137">Nome modello</span><span class="sxs-lookup"><span data-stu-id="69a0a-137">Template name</span></span> | <span data-ttu-id="69a0a-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69a0a-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="69a0a-139">Nuova app non certificata</span><span class="sxs-lookup"><span data-stu-id="69a0a-139">New uncertified app</span></span> | <span data-ttu-id="69a0a-140">Evidenzia le nuove app che non hanno superato il processo di certificazione delle app in modo da assicurarsi che siano previste nel tenant.</span><span class="sxs-lookup"><span data-stu-id="69a0a-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="69a0a-141">Per impostazione predefinita, questo criterio contrassegnerà tutte le app registrate negli ultimi 7 giorni e non sono certificate.</span><span class="sxs-lookup"><span data-stu-id="69a0a-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="69a0a-142">Criteri app personalizzati</span><span class="sxs-lookup"><span data-stu-id="69a0a-142">Custom app policies</span></span>

<span data-ttu-id="69a0a-143">Usare un criterio app personalizzato quando è necessario eseguire un'operazione non ancora eseguita da uno dei modelli incorporati.</span><span class="sxs-lookup"><span data-stu-id="69a0a-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="69a0a-144">Per creare un nuovo criterio dell'app personalizzato, selezionare **Crea nuovo** nella pagina **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="69a0a-145">Nella **pagina Scegli modello di criteri app** selezionare la categoria **Personalizzato**, il modello **Criterio personalizzato** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="69a0a-146">Nella pagina **Nome e descrizione** configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="69a0a-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="69a0a-147">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="69a0a-147">Policy Name</span></span>

- <span data-ttu-id="69a0a-148">Descrizione criterio</span><span class="sxs-lookup"><span data-stu-id="69a0a-148">Policy Description</span></span>

- <span data-ttu-id="69a0a-149">Selezionare la gravità dei criteri, che imposta la gravità degli avvisi generati da questo criterio.</span><span class="sxs-lookup"><span data-stu-id="69a0a-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="69a0a-150">Alto</span><span class="sxs-lookup"><span data-stu-id="69a0a-150">High</span></span>
  - <span data-ttu-id="69a0a-151">Medio</span><span class="sxs-lookup"><span data-stu-id="69a0a-151">Medium</span></span>
  - <span data-ttu-id="69a0a-152">Basso</span><span class="sxs-lookup"><span data-stu-id="69a0a-152">Low</span></span>

<span data-ttu-id="69a0a-153">Nella pagina **Scegli le impostazioni e le condizioni dei criteri**, in **Scegli per quali app è applicabile questo criterio**, selezionare:</span><span class="sxs-lookup"><span data-stu-id="69a0a-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="69a0a-154">Tutte le app</span><span class="sxs-lookup"><span data-stu-id="69a0a-154">All Apps</span></span>
- <span data-ttu-id="69a0a-155">Scegli le app specifiche</span><span class="sxs-lookup"><span data-stu-id="69a0a-155">Choose specific apps</span></span>

  <span data-ttu-id="69a0a-156">Un riquadro consente di selezionare una o più app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="69a0a-157">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-157">Select **Add**.</span></span>

<span data-ttu-id="69a0a-158">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-158">Select **Next**.</span></span>

<span data-ttu-id="69a0a-159">Nella pagina **Scegli le impostazioni e le condizioni dei criteri** selezionare **Imposta nuove condizioni per i criteri** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="69a0a-160">Il riquadro **Crea regola** consente di selezionare le condizioni per una nuova regola.</span><span class="sxs-lookup"><span data-stu-id="69a0a-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="69a0a-161">Selezionare **Aggiungi condizione**, selezionare dall'elenco delle condizioni e infine specificare il valore della condizione.</span><span class="sxs-lookup"><span data-stu-id="69a0a-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="69a0a-162">È possibile aggiungere più condizioni.</span><span class="sxs-lookup"><span data-stu-id="69a0a-162">You can add multiple conditions.</span></span>

<span data-ttu-id="69a0a-163">Di seguito sono elencate le condizioni disponibili per un criterio app personalizzato.</span><span class="sxs-lookup"><span data-stu-id="69a0a-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="69a0a-164">Condizione</span><span class="sxs-lookup"><span data-stu-id="69a0a-164">Condition</span></span> | <span data-ttu-id="69a0a-165">Valori di condizione accettati</span><span class="sxs-lookup"><span data-stu-id="69a0a-165">Condition values accepted</span></span> | <span data-ttu-id="69a0a-166">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="69a0a-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="69a0a-167">Età della registrazione dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-167">App registration age</span></span> | <span data-ttu-id="69a0a-168">Negli ultimi X giorni</span><span class="sxs-lookup"><span data-stu-id="69a0a-168">Within last X days</span></span> |  |
| <span data-ttu-id="69a0a-169">Certificazione delle app</span><span class="sxs-lookup"><span data-stu-id="69a0a-169">App certification</span></span> | <span data-ttu-id="69a0a-170">Conformità di base, conformità MCAS o N/D</span><span class="sxs-lookup"><span data-stu-id="69a0a-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="69a0a-171">Certificazione Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69a0a-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="69a0a-172">Verifica autore</span><span class="sxs-lookup"><span data-stu-id="69a0a-172">Publisher verification</span></span> | <span data-ttu-id="69a0a-173">Sì o No</span><span class="sxs-lookup"><span data-stu-id="69a0a-173">Yes or No</span></span> | [<span data-ttu-id="69a0a-174">Verifica dell'autore</span><span class="sxs-lookup"><span data-stu-id="69a0a-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="69a0a-175">Autorizzazione applicazione</span><span class="sxs-lookup"><span data-stu-id="69a0a-175">Application Permission</span></span> | <span data-ttu-id="69a0a-176">Selezionare una o più autorizzazioni API dall'elenco</span><span class="sxs-lookup"><span data-stu-id="69a0a-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="69a0a-177">Informazioni di riferimento sulle autorizzazioni di Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="69a0a-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="69a0a-178">Autorizzazione delegata</span><span class="sxs-lookup"><span data-stu-id="69a0a-178">Delegated Permission</span></span> | <span data-ttu-id="69a0a-179">Selezionare una o più autorizzazioni API dall'elenco</span><span class="sxs-lookup"><span data-stu-id="69a0a-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="69a0a-180">Informazioni di riferimento sulle autorizzazioni di Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="69a0a-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="69a0a-181">Privilegio elevato</span><span class="sxs-lookup"><span data-stu-id="69a0a-181">High privilege</span></span> | <span data-ttu-id="69a0a-182">Sì o No</span><span class="sxs-lookup"><span data-stu-id="69a0a-182">Yes or No</span></span> | <span data-ttu-id="69a0a-183">Si tratta di una designazione interna basata sulla stessa logica usata da MCAS.</span><span class="sxs-lookup"><span data-stu-id="69a0a-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="69a0a-184">App con privilegi eccessivi</span><span class="sxs-lookup"><span data-stu-id="69a0a-184">Overprivileged app</span></span> | <span data-ttu-id="69a0a-185">Sì o No</span><span class="sxs-lookup"><span data-stu-id="69a0a-185">Yes or No</span></span> | <span data-ttu-id="69a0a-186">App con più autorizzazioni concesse rispetto a quelle utilizzate da tali app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="69a0a-187">Accesso ai dati dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-187">App data access</span></span> | <span data-ttu-id="69a0a-188">Accesso ai dati superiore a X GB all'ora</span><span class="sxs-lookup"><span data-stu-id="69a0a-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="69a0a-189">Tendenza di accesso ai dati dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-189">App data access trend</span></span> | <span data-ttu-id="69a0a-190">X% di aumento dell'utilizzo dei dati negli ultimi 7 giorni</span><span class="sxs-lookup"><span data-stu-id="69a0a-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="69a0a-191">Accesso all'API dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-191">App API Access</span></span> | <span data-ttu-id="69a0a-192">Più di X chiamate API all'ora</span><span class="sxs-lookup"><span data-stu-id="69a0a-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="69a0a-193">Tendenza di accesso all'API dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-193">App API Access trend</span></span> | <span data-ttu-id="69a0a-194">X% di aumento delle chiamate API negli ultimi 7 giorni</span><span class="sxs-lookup"><span data-stu-id="69a0a-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="69a0a-195">Utenti con consenso</span><span class="sxs-lookup"><span data-stu-id="69a0a-195">Users consented</span></span> | <span data-ttu-id="69a0a-196">(Maggiore o minore di) X utenti con consenso</span><span class="sxs-lookup"><span data-stu-id="69a0a-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="69a0a-197">Utente prioritario acconsentito</span><span class="sxs-lookup"><span data-stu-id="69a0a-197">Priority user consented</span></span> | <span data-ttu-id="69a0a-198">Sì o No</span><span class="sxs-lookup"><span data-stu-id="69a0a-198">Yes or No</span></span> | <span data-ttu-id="69a0a-199">Un utente con un [account prioritario](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="69a0a-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="69a0a-200">App consentita da</span><span class="sxs-lookup"><span data-stu-id="69a0a-200">App consented by</span></span> | <span data-ttu-id="69a0a-201">Selezionare uno o più utenti dall'elenco</span><span class="sxs-lookup"><span data-stu-id="69a0a-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="69a0a-202">Ruolo dell'utente che fornisce il consenso</span><span class="sxs-lookup"><span data-stu-id="69a0a-202">Consenting user’s role</span></span> | <span data-ttu-id="69a0a-203">Selezionare uno o più ruoli: amministratore di Teams, amministratori che leggono la directory, amministratore che legge i dati di sicurezza, amministratore di conformità, amministratore della sicurezza, amministratore di supporto tecnico, amministratore di SharePoint, amministratore di Exchange, lettore globale, amministratore globale, amministratore dati di conformità, amministratore utenti, amministratore del supporto dei servizio</span><span class="sxs-lookup"><span data-stu-id="69a0a-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="69a0a-204">Selezioni multiple consentite.</span><span class="sxs-lookup"><span data-stu-id="69a0a-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="69a0a-205">I ruoli Azure AD con un membro assegnato devono essere resi disponibili in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="69a0a-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="69a0a-206">Accesso al carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="69a0a-206">Workload accessed</span></span> | <span data-ttu-id="69a0a-207">OneDrive e/o SharePoint e/o Exchange</span><span class="sxs-lookup"><span data-stu-id="69a0a-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="69a0a-208">Selezioni multiple consentite.</span><span class="sxs-lookup"><span data-stu-id="69a0a-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="69a0a-209">Tasso di errore</span><span class="sxs-lookup"><span data-stu-id="69a0a-209">Error rate</span></span> | <span data-ttu-id="69a0a-210">Il tasso di errore è maggiore di X% negli ultimi 7 giorni, dove X è un valore definito dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="69a0a-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="69a0a-211">Per applicare questo criterio dell'app, è necessario soddisfare tutte le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="69a0a-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="69a0a-212">Dopo aver specificato le condizioni, selezionare **Salva** e infine scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="69a0a-213">Nella pagina **Definisci azioni criteri** selezionare **Disabilita app** se si desidera che la governance dell'app disabiliti l'app quando viene generato un avviso basato su questo criterio e infine selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="69a0a-214">Nella pagina **Definisci stato criteri** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69a0a-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="69a0a-215">**Modalità di controllo**: i criteri vengono valutati, ma le azioni configurate non verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="69a0a-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="69a0a-216">I criteri della modalità di controllo vengono visualizzati con lo stato di **Controlla** nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="69a0a-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="69a0a-217">**Attivo**: i criteri vengono valutati e verranno eseguite azioni configurate.</span><span class="sxs-lookup"><span data-stu-id="69a0a-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="69a0a-218">**Inattivo**: i criteri non vengono valutati e non verranno eseguite azioni configurate.</span><span class="sxs-lookup"><span data-stu-id="69a0a-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="69a0a-219">Testare e monitorare i nuovi criteri dell'app</span><span class="sxs-lookup"><span data-stu-id="69a0a-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="69a0a-220">Ora che i criteri dell'app sono stati creati, è necessario monitorarli nella pagina **Criteri** per assicurarsi che registrino un numero previsto di avvisi attivi e avvisi totali durante i test.</span><span class="sxs-lookup"><span data-stu-id="69a0a-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![Pagina di riepilogo dei criteri MAPG nel Centro conformità Microsoft 365 con un criterio evidenziato](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="69a0a-222">Se il numero di avvisi è un valore inaspettatamente basso, modificare le impostazioni del criterio dell'app per assicurarsi di averlo configurato correttamente prima di impostarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="69a0a-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="69a0a-223">Di seguito è riportato un esempio di processo per creare un nuovo criterio, testarlo e renderlo attivo:</span><span class="sxs-lookup"><span data-stu-id="69a0a-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="69a0a-224">Creare i nuovi criteri con gravità, app, condizioni e azioni impostati sui valori iniziali e lo stato impostato su **Modalità di controllo**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="69a0a-225">Verificare il comportamento previsto, ad esempio gli avvisi generati.</span><span class="sxs-lookup"><span data-stu-id="69a0a-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="69a0a-226">Se il comportamento non è previsto, modificare le impostazioni delle app, le condizioni e le azioni dei criteri in base alle esigenze e tornare al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="69a0a-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="69a0a-227">Se il comportamento è previsto, modificare il criterio e modificarne lo stato in **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="69a0a-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![Flusso di lavoro per la creazione di criteri dell'app](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="69a0a-229">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="69a0a-229">Next step</span></span>

[<span data-ttu-id="69a0a-230">Gestire i criteri delle app.</span><span class="sxs-lookup"><span data-stu-id="69a0a-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
