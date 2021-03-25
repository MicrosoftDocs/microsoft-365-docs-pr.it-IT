---
title: Gestire gli indicatori
ms.reviewer: ''
description: Gestire gli indicatori per un hash di file, un indirizzo IP, url o domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185946"
---
# <a name="manage-indicators"></a><span data-ttu-id="9d48a-104">Gestire gli indicatori</span><span class="sxs-lookup"><span data-stu-id="9d48a-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9d48a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9d48a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d48a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9d48a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d48a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d48a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="9d48a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9d48a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9d48a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9d48a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="9d48a-110">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.</span><span class="sxs-lookup"><span data-stu-id="9d48a-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="9d48a-111">Seleziona la scheda del tipo di entità che vuoi gestire.</span><span class="sxs-lookup"><span data-stu-id="9d48a-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="9d48a-112">Aggiorna i dettagli dell'indicatore e  fai clic su **Salva** o fai clic sul pulsante Elimina se vuoi rimuovere l'entità dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9d48a-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="9d48a-113">Importare un elenco di I/O</span><span class="sxs-lookup"><span data-stu-id="9d48a-113">Import a list of IoCs</span></span>

<span data-ttu-id="9d48a-114">Puoi anche scegliere di caricare un file CSV che definisce gli attributi degli indicatori, l'azione da eseguire e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="9d48a-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="9d48a-115">Scarica il file CSV di esempio per conoscere gli attributi di colonna supportati.</span><span class="sxs-lookup"><span data-stu-id="9d48a-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="9d48a-116">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.</span><span class="sxs-lookup"><span data-stu-id="9d48a-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="9d48a-117">Seleziona la scheda del tipo di entità per cui vuoi importare gli indicatori.</span><span class="sxs-lookup"><span data-stu-id="9d48a-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="9d48a-118">Selezionare **Importa**  >  **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="9d48a-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="9d48a-119">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="9d48a-119">Select **Import**.</span></span> <span data-ttu-id="9d48a-120">Eseguire questa operazione per tutti i file che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="9d48a-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="9d48a-121">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="9d48a-121">Select **Done**.</span></span>

<span data-ttu-id="9d48a-122">Nella tabella seguente sono illustrati i parametri supportati.</span><span class="sxs-lookup"><span data-stu-id="9d48a-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="9d48a-123">Parametro</span><span class="sxs-lookup"><span data-stu-id="9d48a-123">Parameter</span></span> | <span data-ttu-id="9d48a-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d48a-124">Type</span></span>    |   <span data-ttu-id="9d48a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d48a-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="9d48a-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="9d48a-126">indicatorType</span></span> | <span data-ttu-id="9d48a-127">Enum</span><span class="sxs-lookup"><span data-stu-id="9d48a-127">Enum</span></span> | <span data-ttu-id="9d48a-128">Tipo dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="9d48a-128">Type of the indicator.</span></span> <span data-ttu-id="9d48a-129">I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="9d48a-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="9d48a-130">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9d48a-130">**Required**</span></span>
<span data-ttu-id="9d48a-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="9d48a-131">indicatorValue</span></span> | <span data-ttu-id="9d48a-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-132">String</span></span> | <span data-ttu-id="9d48a-133">Identità [dell'entità Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="9d48a-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="9d48a-134">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9d48a-134">**Required**</span></span>
<span data-ttu-id="9d48a-135">action</span><span class="sxs-lookup"><span data-stu-id="9d48a-135">action</span></span> | <span data-ttu-id="9d48a-136">Enum</span><span class="sxs-lookup"><span data-stu-id="9d48a-136">Enum</span></span> | <span data-ttu-id="9d48a-137">Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d48a-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="9d48a-138">I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="9d48a-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="9d48a-139">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9d48a-139">**Required**</span></span>
<span data-ttu-id="9d48a-140">title</span><span class="sxs-lookup"><span data-stu-id="9d48a-140">title</span></span> | <span data-ttu-id="9d48a-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-141">String</span></span> | <span data-ttu-id="9d48a-142">Titolo dell'avviso indicatore.</span><span class="sxs-lookup"><span data-stu-id="9d48a-142">Indicator alert title.</span></span> <span data-ttu-id="9d48a-143">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9d48a-143">**Required**</span></span>
<span data-ttu-id="9d48a-144">descrizione</span><span class="sxs-lookup"><span data-stu-id="9d48a-144">description</span></span> | <span data-ttu-id="9d48a-145">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-145">String</span></span> |  <span data-ttu-id="9d48a-146">Descrizione dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="9d48a-146">Description of the indicator.</span></span> <span data-ttu-id="9d48a-147">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9d48a-147">**Required**</span></span>
<span data-ttu-id="9d48a-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="9d48a-148">expirationTime</span></span> | <span data-ttu-id="9d48a-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9d48a-149">DateTimeOffset</span></span> | <span data-ttu-id="9d48a-150">Data di scadenza dell'indicatore nel formato seguente AAAA-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="9d48a-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="9d48a-151">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="9d48a-151">**Optional**</span></span>
<span data-ttu-id="9d48a-152">gravità</span><span class="sxs-lookup"><span data-stu-id="9d48a-152">severity</span></span> | <span data-ttu-id="9d48a-153">Enum</span><span class="sxs-lookup"><span data-stu-id="9d48a-153">Enum</span></span> | <span data-ttu-id="9d48a-154">Gravità dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="9d48a-154">The severity of the indicator.</span></span> <span data-ttu-id="9d48a-155">I valori possibili sono: "Informational", "Low", "Medium" e "High".</span><span class="sxs-lookup"><span data-stu-id="9d48a-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="9d48a-156">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="9d48a-156">**Optional**</span></span>
<span data-ttu-id="9d48a-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="9d48a-157">recommendedActions</span></span> | <span data-ttu-id="9d48a-158">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-158">String</span></span> | <span data-ttu-id="9d48a-159">Azioni consigliate per l'avviso dell'indicatore TI.</span><span class="sxs-lookup"><span data-stu-id="9d48a-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="9d48a-160">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="9d48a-160">**Optional**</span></span>
<span data-ttu-id="9d48a-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="9d48a-161">rbacGroupNames</span></span> | <span data-ttu-id="9d48a-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-162">String</span></span> | <span data-ttu-id="9d48a-163">Elenco delimitato da virgole di nomi di gruppi RBAC a cui verrà applicato l'indicatore.</span><span class="sxs-lookup"><span data-stu-id="9d48a-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="9d48a-164">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="9d48a-164">**Optional**</span></span>
<span data-ttu-id="9d48a-165">category</span><span class="sxs-lookup"><span data-stu-id="9d48a-165">category</span></span> | <span data-ttu-id="9d48a-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-166">String</span></span> | <span data-ttu-id="9d48a-167">Categoria dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="9d48a-167">Category of the alert.</span></span> <span data-ttu-id="9d48a-168">Alcuni esempi sono l'esecuzione e l'accesso alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="9d48a-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="9d48a-169">**Facoltativo**</span><span class="sxs-lookup"><span data-stu-id="9d48a-169">**Optional**</span></span>
<span data-ttu-id="9d48a-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="9d48a-170">mitretechniques</span></span>| <span data-ttu-id="9d48a-171">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d48a-171">String</span></span> | <span data-ttu-id="9d48a-172">MiTRE techniques code/id (comma separated).</span><span class="sxs-lookup"><span data-stu-id="9d48a-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="9d48a-173">Per ulteriori informazioni, vedere [Tattiche aziendali.](https://attack.mitre.org/tactics/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="9d48a-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="9d48a-174">**Facoltativo** È consigliabile aggiungere un valore nella categoria quando si utilizza una tecnica MITRE.</span><span class="sxs-lookup"><span data-stu-id="9d48a-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="9d48a-175">Per altre informazioni, vedi Le categorie di avviso di Microsoft Defender per endpoint sono ora allineate a [MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span><span class="sxs-lookup"><span data-stu-id="9d48a-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="9d48a-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d48a-176">See also</span></span>
- [<span data-ttu-id="9d48a-177">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="9d48a-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="9d48a-178">Creare indicatori per i file</span><span class="sxs-lookup"><span data-stu-id="9d48a-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="9d48a-179">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="9d48a-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="9d48a-180">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="9d48a-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
