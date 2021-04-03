---
title: Creare e visualizzare le eccezioni per i suggerimenti per la sicurezza - gestione delle minacce e delle vulnerabilità
description: Creare e monitorare le eccezioni per i suggerimenti sulla sicurezza nella gestione delle minacce e delle vulnerabilità.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13ac09b1ad918ed945edec6167fd57ea02b616ea
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500191"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="ed1fb-104">Creare e visualizzare le eccezioni per i suggerimenti per la sicurezza - gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="ed1fb-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ed1fb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ed1fb-105">**Applies to:**</span></span>

- [<span data-ttu-id="ed1fb-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ed1fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ed1fb-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="ed1fb-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ed1fb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed1fb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ed1fb-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ed1fb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed1fb-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="ed1fb-111">In alternativa a una richiesta di correzione quando al momento un suggerimento non è rilevante, è possibile creare eccezioni per i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="ed1fb-112">Se l'organizzazione dispone di gruppi di dispositivi, sarà possibile impostare l'ambito dell'eccezione a gruppi di dispositivi specifici.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="ed1fb-113">Le eccezioni possono essere create per i gruppi di dispositivi selezionati o per tutti i gruppi di dispositivi passati e presenti.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="ed1fb-114">Quando viene creata un'eccezione per un suggerimento, il suggerimento sarà attivo solo alla fine della durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="ed1fb-115">Lo stato del suggerimento verrà modificato in **Eccezione completa** o **Eccezione parziale** (per gruppo di dispositivi).</span><span class="sxs-lookup"><span data-stu-id="ed1fb-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="ed1fb-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ed1fb-116">Permissions</span></span>

<span data-ttu-id="ed1fb-117">Solo gli utenti con autorizzazioni di "gestione delle eccezioni" possono gestire le eccezioni (inclusa la creazione o l'annullamento).</span><span class="sxs-lookup"><span data-stu-id="ed1fb-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="ed1fb-118">[Ulteriori informazioni sui ruoli RBAC.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ed1fb-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Visualizzazione dell'autorizzazione di gestione delle eccezioni.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="ed1fb-120">Creare un'eccezione</span><span class="sxs-lookup"><span data-stu-id="ed1fb-120">Create an exception</span></span>

<span data-ttu-id="ed1fb-121">Selezionare un suggerimento per la sicurezza per cui si desidera creare un'eccezione, quindi selezionare **Opzioni eccezione** e compilare il modulo.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Visualizzazione del punto in cui si trova il pulsante per le "opzioni di eccezione" in un riquadro a comparsa dei suggerimenti per la sicurezza.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="ed1fb-123">Eccezione per gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="ed1fb-123">Exception by device group</span></span>

<span data-ttu-id="ed1fb-124">Applica l'eccezione a tutti i gruppi di dispositivi correnti o scegli gruppi di dispositivi specifici.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="ed1fb-125">I gruppi di dispositivi futuri non verranno inclusi nell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="ed1fb-126">I gruppi di dispositivi che hanno già un'eccezione non verranno visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="ed1fb-127">Se si selezionano solo determinati gruppi di dispositivi, lo stato di raccomandazione cambierà da "attivo" a "eccezione parziale".</span><span class="sxs-lookup"><span data-stu-id="ed1fb-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="ed1fb-128">Lo stato verrà modificato in "eccezione completa" se si selezionano tutti i gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Elenco a discesa del gruppo di dispositivi.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="ed1fb-130">Visualizzazioni filtrate</span><span class="sxs-lookup"><span data-stu-id="ed1fb-130">Filtered views</span></span>

<span data-ttu-id="ed1fb-131">Se hai filtrato per gruppo di dispositivi in una qualsiasi delle pagine di gestione delle minacce e delle vulnerabilità, solo i gruppi di dispositivi filtrati verranno visualizzati come opzioni.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="ed1fb-132">Questo è il pulsante per filtrare in base al gruppo di dispositivi in una delle pagine di gestione delle minacce e delle vulnerabilità:</span><span class="sxs-lookup"><span data-stu-id="ed1fb-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Visualizzazione del filtro dei gruppi di dispositivi selezionati.](images/tvm-selected-device-groups.png)

<span data-ttu-id="ed1fb-134">Visualizzazione eccezioni con gruppi di dispositivi filtrati:</span><span class="sxs-lookup"><span data-stu-id="ed1fb-134">Exception view with filtered device groups:</span></span>

![Elenco a discesa del gruppo di dispositivi filtrato.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="ed1fb-136">Numero elevato di gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="ed1fb-136">Large number of device groups</span></span>

<span data-ttu-id="ed1fb-137">Se l'organizzazione ha più di 20 gruppi di dispositivi, seleziona **Modifica** accanto all'opzione gruppo di dispositivi filtrato.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Viene illustrato come modificare un numero elevato di gruppi.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="ed1fb-139">Verrà visualizzato un riquadro a comparsa in cui è possibile cercare e scegliere i gruppi di dispositivi che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="ed1fb-140">Seleziona l'icona del segno di spunta sotto Cerca per selezionare/deselezionare tutto.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Visualizzazione del riquadro a comparsa gruppo di dispositivi di grandi dimensioni.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="ed1fb-142">Eccezioni globali</span><span class="sxs-lookup"><span data-stu-id="ed1fb-142">Global exceptions</span></span>

<span data-ttu-id="ed1fb-143">Se si dispone delle autorizzazioni di amministratore globale (denominato amministratore di Microsoft Defender ATP), sarà possibile creare e annullare un'eccezione globale.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="ed1fb-144">Influisce **su tutti** i gruppi di dispositivi correnti e futuri nell'organizzazione e solo un utente con autorizzazioni simili sarà in grado di modificarlo.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="ed1fb-145">Lo stato di raccomandazione cambierà da "attivo" a "eccezione completa".</span><span class="sxs-lookup"><span data-stu-id="ed1fb-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Opzione di eccezione globale visualizzata.](images/tvm-exception-global.png)

<span data-ttu-id="ed1fb-147">Alcuni aspetti da tenere presenti:</span><span class="sxs-lookup"><span data-stu-id="ed1fb-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="ed1fb-148">Se un suggerimento è in un'eccezione globale, le nuove eccezioni create per i gruppi di dispositivi verranno sospese fino alla scadenza o all'annullamento dell'eccezione globale.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="ed1fb-149">Dopo questo punto, le nuove eccezioni del gruppo di dispositivi saranno effettive fino alla scadenza.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="ed1fb-150">Se un suggerimento contiene già eccezioni per gruppi di dispositivi specifici e viene creata un'eccezione globale, l'eccezione del gruppo di dispositivi verrà sospesa fino alla scadenza o all'annullamento dell'eccezione globale prima della scadenza.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="ed1fb-151">Giustificazione</span><span class="sxs-lookup"><span data-stu-id="ed1fb-151">Justification</span></span>

<span data-ttu-id="ed1fb-152">Seleziona la giustificazione per l'eccezione che devi creare invece di correggere il suggerimento per la sicurezza in questione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="ed1fb-153">Compila il contesto di giustificazione, quindi imposta la durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="ed1fb-154">L'elenco seguente elenca in dettaglio le giustificazioni alla base delle opzioni di eccezione:</span><span class="sxs-lookup"><span data-stu-id="ed1fb-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="ed1fb-155">**Controllo di terze parti** - Un prodotto o un software di terze parti già si rivolge a questa raccomandazione- La scelta di questo tipo di giustificazione ridurrà il punteggio di esposizione e aumenterà il punteggio sicuro perché il rischio è ridotto</span><span class="sxs-lookup"><span data-stu-id="ed1fb-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="ed1fb-156">**Mitigazione alternativa** - Uno strumento interno è già in grado di risolvere questo consiglio: la scelta di questo tipo di giustificazione ridurrà il punteggio di esposizione e aumenterà il punteggio sicuro perché il rischio è ridotto</span><span class="sxs-lookup"><span data-stu-id="ed1fb-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="ed1fb-157">**Rischio accettato** - Pone un rischio basso e/o l'implementazione della raccomandazione è troppo costosa</span><span class="sxs-lookup"><span data-stu-id="ed1fb-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="ed1fb-158">**Correzione pianificata (tolleranza):** già pianificata ma in attesa di esecuzione o autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ed1fb-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="ed1fb-159">Visualizzare tutte le eccezioni</span><span class="sxs-lookup"><span data-stu-id="ed1fb-159">View all exceptions</span></span>

<span data-ttu-id="ed1fb-160">Passare alla **scheda Eccezioni** nella **pagina Correzione.**</span><span class="sxs-lookup"><span data-stu-id="ed1fb-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="ed1fb-161">È possibile filtrare in base a giustificazione, tipo e stato.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="ed1fb-162">Seleziona un'eccezione per aprire un riquadro a comparsa con altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="ed1fb-163">Le eccezioni per gruppo di dispositivi includeranno un elenco di tutti i gruppi di dispositivi trattati dall'eccezione, che puoi esportare.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="ed1fb-164">È inoltre possibile visualizzare il suggerimento correlato o annullare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-164">You can also view the related recommendation or cancel the exception.</span></span>

![Visualizzazione della scheda "Eccezioni" nella pagina Correzione.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="ed1fb-166">Come annullare un'eccezione</span><span class="sxs-lookup"><span data-stu-id="ed1fb-166">How to cancel an exception</span></span>

<span data-ttu-id="ed1fb-167">Per annullare un'eccezione, passare alla **scheda Eccezioni** nella **pagina Correzione.**</span><span class="sxs-lookup"><span data-stu-id="ed1fb-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="ed1fb-168">Selezionare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-168">Select the exception.</span></span>

<span data-ttu-id="ed1fb-169">Per annullare l'eccezione per tutti i gruppi di dispositivi o per un'eccezione globale, seleziona il **pulsante Annulla eccezione per tutti i gruppi di** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="ed1fb-170">Potrai annullare solo le eccezioni per i gruppi di dispositivi per cui hai le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![Pulsante Annulla.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="ed1fb-172">Annullare l'eccezione per un gruppo di dispositivi specifico</span><span class="sxs-lookup"><span data-stu-id="ed1fb-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="ed1fb-173">Seleziona il gruppo di dispositivi specifico per annullare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="ed1fb-174">Verrà visualizzato un riquadro a comparsa per il gruppo di dispositivi ed è possibile selezionare **Annulla eccezione.**</span><span class="sxs-lookup"><span data-stu-id="ed1fb-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Mostra come selezionare un gruppo di dispositivi specifico.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="ed1fb-176">Impatto della visualizzazione dopo l'applicazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="ed1fb-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="ed1fb-177">Nella pagina Suggerimenti per la sicurezza seleziona **Personalizza** colonne e seleziona le caselle dispositivi esposti **(dopo** le eccezioni) e **Impatto (dopo le eccezioni).**</span><span class="sxs-lookup"><span data-stu-id="ed1fb-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Visualizzazione delle opzioni di personalizzazione delle colonne.](images/tvm-after-exceptions.png)

<span data-ttu-id="ed1fb-179">La colonna dispositivi esposti (dopo le eccezioni) mostra i dispositivi rimanenti che sono ancora esposti alle vulnerabilità dopo l'applicazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="ed1fb-180">Le giustificazioni di eccezione che influiscono sull'esposizione includono "controllo di terze parti" e "mitigazione alternativa".</span><span class="sxs-lookup"><span data-stu-id="ed1fb-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="ed1fb-181">Altre giustificazioni non riducono l'esposizione di un dispositivo e vengono comunque considerate esposte.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="ed1fb-182">L'impatto (dopo le eccezioni) mostra l'impatto rimanente sul punteggio di esposizione o sul punteggio sicuro dopo l'applicazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="ed1fb-183">Le giustificazioni delle eccezioni che influiscono sui punteggi includono "controllo di terze parti" e "mitigazione alternativa".</span><span class="sxs-lookup"><span data-stu-id="ed1fb-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="ed1fb-184">Altre giustificazioni non riducono l'esposizione di un dispositivo e quindi il punteggio di esposizione e il punteggio sicuro non cambiano.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Visualizzazione delle colonne nella tabella.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="ed1fb-186">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ed1fb-186">Related topics</span></span>

- [<span data-ttu-id="ed1fb-187">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="ed1fb-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ed1fb-188">Correggere le vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="ed1fb-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="ed1fb-189">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="ed1fb-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="ed1fb-190">Punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="ed1fb-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="ed1fb-191">Punteggio di sicurezza Microsoft per dispositivi</span><span class="sxs-lookup"><span data-stu-id="ed1fb-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
