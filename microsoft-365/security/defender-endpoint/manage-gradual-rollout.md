---
title: Gestire il processo di implementazione graduale per gli aggiornamenti di Microsoft Defender
description: Informazioni sul processo di aggiornamento graduale e sui controlli
keywords: aggiornamento, processo di aggiornamento, controlli, rilascio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fac6205e3045828cf2bbcc27a9a8020c3d63186c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105612"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="18589-104">Gestire il processo di implementazione graduale per gli aggiornamenti di Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="18589-104">Manage the gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="18589-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="18589-105">**Applies to:**</span></span>

- [<span data-ttu-id="18589-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="18589-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="18589-107">È importante assicurarsi che i componenti client siano aggiornati per offrire funzionalità di protezione critiche e prevenire gli attacchi.</span><span class="sxs-lookup"><span data-stu-id="18589-107">It is important to ensure that client components are up-to-date to deliver critical protection capabilities and prevent attacks.</span></span>

<span data-ttu-id="18589-108">Le funzionalità vengono fornite tramite diversi componenti:</span><span class="sxs-lookup"><span data-stu-id="18589-108">Capabilities are provided through several components:</span></span> 

- [<span data-ttu-id="18589-109">Endpoint Detection & Response</span><span class="sxs-lookup"><span data-stu-id="18589-109">Endpoint Detection & Response</span></span>](overview-endpoint-detection-response.md) 
- <span data-ttu-id="18589-110">[Protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) con [protezione basata sul cloud](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="18589-110">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md)</span></span> 
- [<span data-ttu-id="18589-111">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="18589-111">Attack Surface Reduction</span></span>](overview-attack-surface-reduction.md)

<span data-ttu-id="18589-112">Gli aggiornamenti vengono rilasciati mensilmente utilizzando un processo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-112">Updates are released monthly using a gradual release process.</span></span> <span data-ttu-id="18589-113">Questo processo consente di consentire al rilevamento di errori anticipati di rilevare l'impatto man quando si verifica e di affrontarlo rapidamente prima di un'implementazione più ampia.</span><span class="sxs-lookup"><span data-stu-id="18589-113">This process helps to enable early failure detection to catch impact as it occurs and address it quickly before a larger rollout.</span></span> 

> [!NOTE]
> <span data-ttu-id="18589-114">Per ulteriori informazioni su come controllare gli aggiornamenti giornalieri delle definizioni, vedere Pianificare gli aggiornamenti delle definizioni Antivirus Microsoft Defender - Windows [sicurezza | Documenti Microsoft](manage-protection-update-schedule-microsoft-defender-antivirus.md). Gli aggiornamenti delle definizioni garantiscono che la protezione di nuova generazione possa difendersi dalle nuove minacce, anche se la protezione consegnata dal cloud non è disponibile per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="18589-114">For more information on how to control daily definition updates, see [Schedule Microsoft Defender Antivirus definition updates - Windows security | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definition updates ensure that next-generation protection can defend against new threats, even if cloud-delivered protection is not available to the endpoint.</span></span>

## <a name="microsoft-gradual-rollout-model"></a><span data-ttu-id="18589-115">Modello di implementazione graduale Microsoft</span><span class="sxs-lookup"><span data-stu-id="18589-115">Microsoft gradual rollout model</span></span>

<span data-ttu-id="18589-116">Il modello di implementazione graduale seguente viene seguito per gli aggiornamenti mensili di Defender:</span><span class="sxs-lookup"><span data-stu-id="18589-116">The following gradual rollout model is followed for monthly Defender updates:</span></span>

1. <span data-ttu-id="18589-117">La prima versione viene rilasciata ai sottoscrittori del canale Beta.</span><span class="sxs-lookup"><span data-stu-id="18589-117">The first release goes out to Beta channel subscribers.</span></span>
2. <span data-ttu-id="18589-118">Dopo la convalida, il feedback e le correzioni, iniziamo il processo di implementazione graduale in modo limitato e prima di visualizzare in anteprima i sottoscrittori del canale.</span><span class="sxs-lookup"><span data-stu-id="18589-118">After validation, feedback, and fixes, we start the gradual rollout process in a throttled way and to Preview channel subscribers first.</span></span>
3. <span data-ttu-id="18589-119">Si procede quindi a rilasciare l'aggiornamento al resto della popolazione globale, scalando dal 10 al 100%.</span><span class="sxs-lookup"><span data-stu-id="18589-119">We then proceed to release the update to the rest of the global population, scaling out from 10-100%.</span></span>

<span data-ttu-id="18589-120">I nostri tecnici monitorano continuamente l'impatto ed esercitino l'escalation di eventuali problemi per creare una correzione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="18589-120">Our engineers continuously monitor impact and escalate any issues to create a fix as needed.</span></span>

## <a name="how-to-customize-your-internal-deployment-process"></a><span data-ttu-id="18589-121">Come personalizzare il processo di distribuzione interno</span><span class="sxs-lookup"><span data-stu-id="18589-121">How to customize your internal deployment process</span></span>

<span data-ttu-id="18589-122">Se i computer ricevono gli aggiornamenti di Defender da Windows Update, il processo di implementazione graduale potrebbe comportare la ricezione degli aggiornamenti di Defender da parte di alcuni computer prima di altri.</span><span class="sxs-lookup"><span data-stu-id="18589-122">If your machines are receiving Defender updates from Windows Update, the gradual rollout process may result in some of your machines receiving Defender updates sooner than others.</span></span> <span data-ttu-id="18589-123">La sezione seguente spiega come definire una strategia che consentirà agli aggiornamenti automatici di fluire in modo diverso a gruppi specifici di dispositivi sfruttando la configurazione del canale di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="18589-123">The following section explains how to define a strategy that will allow automatic updates to flow differently to specific groups of devices by leveraging update channel configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="18589-124">Quando si pianifica la propria versione graduale, assicurarsi di avere sempre una selezione di dispositivi sottoscritti ai canali di anteprima e a fasi.</span><span class="sxs-lookup"><span data-stu-id="18589-124">When planning for your own gradual release, please make sure to always have a selection of devices subscribed to the preview and staged channels.</span></span> <span data-ttu-id="18589-125">Ciò offrirà all'organizzazione e a Microsoft l'opportunità di prevenire o individuare e risolvere i problemi specifici dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="18589-125">This will provide your organization as well as Microsoft the opportunity to prevent or find and fix issues specific to your environment.</span></span>

<span data-ttu-id="18589-126">Per i computer che ricevono aggiornamenti tramite, ad esempio, Windows Server Update Services (WSUS) o Microsoft Endpoint Configuration Manager (MECM), sono disponibili altre opzioni per tutti gli aggiornamenti di Windows, incluse le opzioni per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="18589-126">For machines receiving updates through, for example, Windows Server Update Services (WSUS) or Microsoft Endpoint Configuration Manager (MECM), more options are available to all Windows updates, including options  for Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="18589-127">Per ulteriori informazioni su come usare una soluzione come WSUS, MECM per gestire la distribuzione e l'applicazione degli aggiornamenti, vedere [Manage Antivirus Microsoft Defender updates and apply baselines - Windows security | Documenti Microsoft](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span><span class="sxs-lookup"><span data-stu-id="18589-127">Read more about how to use a solution like WSUS, MECM to manage the distribution and application of updates at [Manage Microsoft Defender Antivirus updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span></span>

## <a name="update-channels-for-monthly-updates"></a><span data-ttu-id="18589-128">Aggiornare i canali per gli aggiornamenti mensili</span><span class="sxs-lookup"><span data-stu-id="18589-128">Update channels for monthly updates</span></span>

<span data-ttu-id="18589-129">Puoi assegnare un computer a un canale di aggiornamento per definire la cadenza in cui un computer riceve aggiornamenti mensili del motore e della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="18589-129">You can assign a machine to an update channel to define the cadence in which a machine receives monthly engine and platform updates.</span></span>

<span data-ttu-id="18589-130">Per altre informazioni su come configurare gli aggiornamenti, vedi [Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender.](configure-updates.md)</span><span class="sxs-lookup"><span data-stu-id="18589-130">For more information on how to configure updates, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>

<span data-ttu-id="18589-131">Sono disponibili i seguenti canali di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="18589-131">The following update channels are available:</span></span>

| <span data-ttu-id="18589-132">Nome canale</span><span class="sxs-lookup"><span data-stu-id="18589-132">Channel name</span></span>  | <span data-ttu-id="18589-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18589-133">Description</span></span>  | <span data-ttu-id="18589-134">Applicazione</span><span class="sxs-lookup"><span data-stu-id="18589-134">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="18589-135">Canale beta - Versione non definitiva</span><span class="sxs-lookup"><span data-stu-id="18589-135">Beta Channel - Prerelease</span></span>  | <span data-ttu-id="18589-136">Testare gli aggiornamenti prima di altri</span><span class="sxs-lookup"><span data-stu-id="18589-136">Test updates before others</span></span>  | <span data-ttu-id="18589-137">I dispositivi impostati su questo canale saranno i primi a ricevere nuovi aggiornamenti mensili.</span><span class="sxs-lookup"><span data-stu-id="18589-137">Devices set to this channel will be the first to receive new monthly updates.</span></span> <span data-ttu-id="18589-138">Seleziona Canale beta per partecipare all'identificazione e alla segnalazione di problemi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18589-138">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="18589-139">I dispositivi nel Windows Insider Sono sottoscritti a questo canale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="18589-139">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="18589-140">Da utilizzare solo in ambienti di test.</span><span class="sxs-lookup"><span data-stu-id="18589-140">For use in test environments only.</span></span>  |
| <span data-ttu-id="18589-141">Canale corrente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="18589-141">Current Channel (Preview)</span></span>  | <span data-ttu-id="18589-142">Ottenere gli aggiornamenti del canale **corrente in precedenza** durante il rilascio graduale</span><span class="sxs-lookup"><span data-stu-id="18589-142">Get Current Channel updates **earlier** during gradual release</span></span>  | <span data-ttu-id="18589-143">Ai dispositivi impostati su questo canale verranno offerti gli aggiornamenti prima durante il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-143">Devices set to this channel will be offered updates earliest during the gradual release cycle.</span></span> <span data-ttu-id="18589-144">Consigliato per ambienti di pre-produzione/convalida.</span><span class="sxs-lookup"><span data-stu-id="18589-144">Suggested for pre-production/validation environments.</span></span>  |
| <span data-ttu-id="18589-145">Canale corrente (a fasi)</span><span class="sxs-lookup"><span data-stu-id="18589-145">Current Channel (Staged)</span></span>  | <span data-ttu-id="18589-146">Ottenere gli aggiornamenti del canale corrente in un secondo momento durante il rilascio graduale</span><span class="sxs-lookup"><span data-stu-id="18589-146">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="18589-147">I dispositivi verranno offerti aggiornamenti in un secondo momento durante il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-147">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="18589-148">Consigliato per l'applicazione a una piccola parte rappresentativa della popolazione del dispositivo (~10%).</span><span class="sxs-lookup"><span data-stu-id="18589-148">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="18589-149">Canale corrente (broad)</span><span class="sxs-lookup"><span data-stu-id="18589-149">Current Channel (Broad)</span></span> | <span data-ttu-id="18589-150">Ottenere aggiornamenti alla fine del rilascio graduale</span><span class="sxs-lookup"><span data-stu-id="18589-150">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="18589-151">Ai dispositivi verranno offerti aggiornamenti solo al termine del ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-151">Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="18589-152">Consigliato per l'applicazione a un ampio set di dispositivi nella popolazione di produzione (~10-100%).</span><span class="sxs-lookup"><span data-stu-id="18589-152">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  |
| <span data-ttu-id="18589-153">(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="18589-153">(default)</span></span>  |   | <span data-ttu-id="18589-154">Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà nel Canale corrente (predefinito): rimanere aggiornato automaticamente durante il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-154">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="18589-155">Adatto per la maggior parte dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="18589-155">Suitable for most devices.</span></span>  |

### <a name="update-channels-for-daily-definition-updates"></a><span data-ttu-id="18589-156">Aggiornare i canali per gli aggiornamenti delle definizioni giornalieri</span><span class="sxs-lookup"><span data-stu-id="18589-156">Update channels for daily definition updates</span></span>

<span data-ttu-id="18589-157">Puoi anche assegnare un computer a un canale per definire la cadenza in cui riceve gli aggiornamenti giornalieri delle definizioni.</span><span class="sxs-lookup"><span data-stu-id="18589-157">You can also assign a machine to a channel to define the cadence in which it receives daily definition updates.</span></span> <span data-ttu-id="18589-158">A differenza del processo mensile, non esiste alcun canale Beta e questo ciclo di rilascio graduale si verifica più volte al giorno.</span><span class="sxs-lookup"><span data-stu-id="18589-158">Note that unlike the monthly process, there is no Beta channel and this gradual release cycle occurs multiple times a day.</span></span>
  
| <span data-ttu-id="18589-159">Nome canale</span><span class="sxs-lookup"><span data-stu-id="18589-159">Channel name</span></span>  | <span data-ttu-id="18589-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18589-160">Description</span></span>  | <span data-ttu-id="18589-161">Applicazione</span><span class="sxs-lookup"><span data-stu-id="18589-161">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="18589-162">Canale corrente (a fasi)</span><span class="sxs-lookup"><span data-stu-id="18589-162">Current Channel (Staged)</span></span>  | <span data-ttu-id="18589-163">Ottenere gli aggiornamenti del canale corrente in un secondo momento durante il rilascio graduale</span><span class="sxs-lookup"><span data-stu-id="18589-163">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="18589-164">I dispositivi verranno offerti aggiornamenti in un secondo momento durante il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-164">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="18589-165">Consigliato per l'applicazione a una piccola parte rappresentativa della popolazione del dispositivo (~10%).</span><span class="sxs-lookup"><span data-stu-id="18589-165">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="18589-166">Canale corrente (broad)</span><span class="sxs-lookup"><span data-stu-id="18589-166">Current Channel (Broad)</span></span> | <span data-ttu-id="18589-167">Ottenere aggiornamenti alla fine del rilascio graduale</span><span class="sxs-lookup"><span data-stu-id="18589-167">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="18589-168">I dispositivi verranno offerti aggiornamenti dopo il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-168">Devices will be offered updates after the gradual release cycle.</span></span> <span data-ttu-id="18589-169">Ideale per i computer datacenter che ricevono solo aggiornamenti limitati.</span><span class="sxs-lookup"><span data-stu-id="18589-169">Best for datacenter machines that only receive limited updates.</span></span> <span data-ttu-id="18589-170">Nota: questa impostazione si applica a tutti gli aggiornamenti di Defender.</span><span class="sxs-lookup"><span data-stu-id="18589-170">Note: this setting applies to all Defender updates.</span></span>  |
| <span data-ttu-id="18589-171">(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="18589-171">(default)</span></span>  |   | <span data-ttu-id="18589-172">Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà nel Canale corrente (predefinito): rimanere aggiornato automaticamente durante il ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-172">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="18589-173">Adatto alla maggior parte dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="18589-173">Suitable for most devices</span></span>  |

> [!NOTE]
> <span data-ttu-id="18589-174">Nel caso in cui si desideri forzare un aggiornamento alla firma più recente anziché sfruttare il ritardo, sarà necessario rimuovere prima questo criterio.</span><span class="sxs-lookup"><span data-stu-id="18589-174">In case you wish to force an update to the newest signature instead of leveraging the time delay, you will need to remove this policy first.</span></span>

## <a name="update-guidance"></a><span data-ttu-id="18589-175">Linee guida per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="18589-175">Update guidance</span></span>

<span data-ttu-id="18589-176">Nella maggior parte dei casi, la configurazione consigliata quando si usa Windows Update è consentire agli endpoint di ricevere e applicare aggiornamenti di Defender mensili non appena arrivano.</span><span class="sxs-lookup"><span data-stu-id="18589-176">In most cases, the recommended configuration when using Windows Update is to allow endpoints to receive and apply monthly Defender updates as they arrive.</span></span> <span data-ttu-id="18589-177">In questo modo si garantisce il miglior equilibrio tra protezione e possibile impatto associato alle modifiche che possono introdurre.</span><span class="sxs-lookup"><span data-stu-id="18589-177">This provides the best balance between protection and possible impact associated with the changes they can introduce.</span></span>

<span data-ttu-id="18589-178">Per gli ambienti in cui è necessaria un'implementazione graduale più controllata degli aggiornamenti automatici di Defender, prendere in considerazione un approccio con i gruppi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="18589-178">For environments where there is a need for a more controlled gradual rollout of automatic Defender updates, consider an approach with deployment groups:</span></span>

1. <span data-ttu-id="18589-179">Partecipa al programma Windows Insider o assegna un gruppo di dispositivi al Canale beta.</span><span class="sxs-lookup"><span data-stu-id="18589-179">Participate in the Windows Insider program or assign a group of devices to the Beta Channel.</span></span>
2. <span data-ttu-id="18589-180">Designare un gruppo pilota che acconsenta esplicitamente al canale di anteprima, in genere ambienti di convalida, per ricevere nuovi aggiornamenti in anticipo.</span><span class="sxs-lookup"><span data-stu-id="18589-180">Designate a pilot group that opts-in to Preview Channel, typically validation environments, to receive new updates early.</span></span>
3. <span data-ttu-id="18589-181">Designare un gruppo di computer che ricevono gli aggiornamenti in un secondo momento durante l'implementazione graduale dal canale a fasi.</span><span class="sxs-lookup"><span data-stu-id="18589-181">Designate a group of machines that receive updates later during the gradual rollout from Staged channel.</span></span> <span data-ttu-id="18589-182">In genere, si tratta di un rappresentante che rappresenta il 10% della popolazione.</span><span class="sxs-lookup"><span data-stu-id="18589-182">Typically, this would be a representative ~10% of the population.</span></span>
4. <span data-ttu-id="18589-183">Designare un gruppo di computer che ricevono gli aggiornamenti al termine del ciclo di rilascio graduale.</span><span class="sxs-lookup"><span data-stu-id="18589-183">Designate a group of machines that receive updates after the gradual release cycle completes.</span></span> <span data-ttu-id="18589-184">Si tratta in genere di sistemi di produzione importanti.</span><span class="sxs-lookup"><span data-stu-id="18589-184">These are typically important production systems.</span></span>

<span data-ttu-id="18589-185">Per il resto dei dispositivi, l'impostazione predefinita è ricevere nuovi aggiornamenti quando arrivano durante il processo di implementazione graduale di Microsoft e non sono necessarie ulteriori configurazioni.</span><span class="sxs-lookup"><span data-stu-id="18589-185">For the remainder of devices, the default setting is to receive new updates as they arrive during the Microsoft gradual rollout process and no further configuration is required.</span></span> 

<span data-ttu-id="18589-186">Adozione di questo modello:</span><span class="sxs-lookup"><span data-stu-id="18589-186">Adopting this model:</span></span>
- <span data-ttu-id="18589-187">Consente di testare le versioni iniziali prima che raggiungano un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="18589-187">Allows you to test early releases before they reach a production environment</span></span> 
- <span data-ttu-id="18589-188">Assicurarsi che l'ambiente di produzione riceva comunque aggiornamenti regolari e garantire la protezione dalle minacce critiche.</span><span class="sxs-lookup"><span data-stu-id="18589-188">Ensure the production environment still receives regular updates and ensure protection against critical threats.</span></span>

## <a name="management-tools"></a><span data-ttu-id="18589-189">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="18589-189">Management tools</span></span>
<span data-ttu-id="18589-190">Per creare un processo di implementazione graduale personalizzato per gli aggiornamenti mensili, è possibile utilizzare gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="18589-190">To create your own custom gradual rollout process for monthly updates, you can use the following tools:</span></span>

- <span data-ttu-id="18589-191">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="18589-191">Group policy</span></span>
- <span data-ttu-id="18589-192">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="18589-192">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="18589-193">PowerShell</span><span class="sxs-lookup"><span data-stu-id="18589-193">PowerShell</span></span>

<span data-ttu-id="18589-194">Per informazioni dettagliate su come usare questi strumenti, vedi [Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender.](configure-updates.md)</span><span class="sxs-lookup"><span data-stu-id="18589-194">For details on how to use these tools, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>