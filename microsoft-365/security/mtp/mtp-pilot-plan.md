---
title: Pianificazione del progetto pilota di Microsoft Threat Protection
description: Pianificare il progetto pilota Microsoft Threat Protection con le parti interessate per gestire le aspettative e garantire esito positivo.
keywords: Pilota di Microsoft Threat Protection, pianificare il progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, Microsoft Threat Protection Project pilota, sicurezza cibernetica, Advanced Persistent Threat, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 21e6e3294b8fe722214d567963223b9e62737e34
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333679"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="93be9-104">Pianificazione del progetto pilota di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="93be9-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93be9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="93be9-105">**Applies to:**</span></span>
- <span data-ttu-id="93be9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="93be9-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Pianificare il progetto pilota di Microsoft Threat Protection" />
      <br/><span data-ttu-id="93be9-108">Piano</a></span><span class="sxs-lookup"><span data-stu-id="93be9-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota" />
      <br/><span data-ttu-id="93be9-110">Preparazione</a></span><span class="sxs-lookup"><span data-stu-id="93be9-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Eseguire le simulazioni di attacco di Microsoft Threat Protection" />
     <br/><span data-ttu-id="93be9-112">Simula attacco</a></span><span class="sxs-lookup"><span data-stu-id="93be9-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Chiudere e riepilogare il pilota di Microsoft Threat Protection" />
     <br/><span data-ttu-id="93be9-114">Chiudi e riepiloga</a></span><span class="sxs-lookup"><span data-stu-id="93be9-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="93be9-115">Si è attualmente in fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="93be9-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="93be9-116">Per assicurarsi che il progetto pilota sia un successo, è essenziale pianificare con attenzione e ottenere le approvazioni dalle parti interessate all'inizio.</span><span class="sxs-lookup"><span data-stu-id="93be9-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="93be9-117">Gli elementi di pianificazione includono l'ambito di identificazione, i casi di utilizzo, i requisiti e i criteri di successo.</span><span class="sxs-lookup"><span data-stu-id="93be9-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="93be9-118">In questa guida viene illustrato come pianificare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="93be9-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="93be9-119">Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="93be9-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="93be9-120">Scope</span><span class="sxs-lookup"><span data-stu-id="93be9-120">Scope</span></span>

<span data-ttu-id="93be9-121">L'ambito del progetto pilota determinerà il livello di ampiezza del test, in base all'ambiente e ai metodi di testing accettabili.</span><span class="sxs-lookup"><span data-stu-id="93be9-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="93be9-122">Di seguito sono riportate alcune considerazioni di esempio:</span><span class="sxs-lookup"><span data-stu-id="93be9-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="93be9-123">Ambiente di sviluppo o di testing che include endpoint, server, controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="93be9-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="93be9-124">Ambiente di produzione con Microsoft 365, Azure, servizi, endpoint e server di Active Directory</span><span class="sxs-lookup"><span data-stu-id="93be9-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="93be9-125">Se non si dispone ancora delle licenze complete, è possibile ottenere le licenze di valutazione per [valutare Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) : pianificare, preparare, configurare ed eseguire il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="93be9-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="93be9-126">Le parti interessate giocheranno un ruolo importante nell'agevolare il processo dall'inizio alla fine.</span><span class="sxs-lookup"><span data-stu-id="93be9-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="93be9-127">I tipi di sistemi operativi da valutare devono essere anche definiti in base al trucco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93be9-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="93be9-128">Questo può includere gli [endpoint Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), i [server Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), gli [endpoint di windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="93be9-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="93be9-129">Casi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="93be9-129">Use cases</span></span>

<span data-ttu-id="93be9-130">I casi di utilizzo rappresentano istruzioni sul modo in cui lo strumento da testare deve essere utilizzato dagli utenti previsti.</span><span class="sxs-lookup"><span data-stu-id="93be9-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="93be9-131">Tali informazioni possono essere formulate come storie utente dal punto di vista di una persona specifica, ad esempio un analista SOC.</span><span class="sxs-lookup"><span data-stu-id="93be9-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="93be9-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93be9-132">For example:</span></span>
- <span data-ttu-id="93be9-133">Come analista SOC, è necessario visualizzare, correlare, valutare e gestire avvisi ed eventi tra i dispositivi, gli utenti e le cassette postali della rete.</span><span class="sxs-lookup"><span data-stu-id="93be9-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="93be9-134">[Gestione degli incidenti]</span><span class="sxs-lookup"><span data-stu-id="93be9-134">[Incident management]</span></span>
- <span data-ttu-id="93be9-135">Come analista SOC, è necessario disporre dello strumento e del processo per analizzare e rispondere automaticamente agli eventi dannosi nella rete.</span><span class="sxs-lookup"><span data-stu-id="93be9-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="93be9-136">[IR automatico]</span><span class="sxs-lookup"><span data-stu-id="93be9-136">[Auto IR]</span></span>
- <span data-ttu-id="93be9-137">Come analista SOC, è necessario eseguire la ricerca dei dati dal proprio ambiente per individuare minacce note e potenziali e attività sospette.</span><span class="sxs-lookup"><span data-stu-id="93be9-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="93be9-138">[Caccia avanzata]</span><span class="sxs-lookup"><span data-stu-id="93be9-138">[Advanced Hunting]</span></span>

<span data-ttu-id="93be9-139">Tenere presente che questi casi di utilizzo devono essere creati all'interno dei parametri dell'ambito definito.</span><span class="sxs-lookup"><span data-stu-id="93be9-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="93be9-140">Se, ad esempio, l'ambito del testing non include una valutazione di strumenti quali Microsoft cloud app Security, utilizzare i casi che si basano su questa operazione come origine dati non deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="93be9-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="93be9-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93be9-141">Requirements</span></span>

<span data-ttu-id="93be9-142">Nell'elenco dei casi di utilizzo è possibile iniziare a creare i requisiti.</span><span class="sxs-lookup"><span data-stu-id="93be9-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="93be9-143">Requisiti: funzionalità è necessario uno strumento per soddisfare i casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="93be9-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="93be9-144">Questi requisiti possono essere suddivisi in categorie quali la configurazione e la manutenzione, il supporto per le integrazioni e i requisiti specifici per le funzionalità come la capacità di caccia e la possibilità di creare avvisi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="93be9-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="93be9-145">Piano di testing</span><span class="sxs-lookup"><span data-stu-id="93be9-145">Test plan</span></span>

<span data-ttu-id="93be9-146">A seconda dei requisiti, è possibile che i diversi metodi di test siano adatti.</span><span class="sxs-lookup"><span data-stu-id="93be9-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="93be9-147">Ad esempio, se l'esigenza è quella di valutare l'efficacia della correzione automatica, il piano di test deve includere dei passaggi per generare i comportamenti che avrebbero attivato un'azione di correzione automatica all'interno di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="93be9-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="93be9-148">Se il requisito consiste nel rilevare un comportamento o un attacco specifico, il test può comportare più passaggi.</span><span class="sxs-lookup"><span data-stu-id="93be9-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="93be9-149">Il punto è che è necessario disporre di un piano per testare accuratamente le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="93be9-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="93be9-150">Criteri di esito positivo</span><span class="sxs-lookup"><span data-stu-id="93be9-150">Success criteria</span></span>

<span data-ttu-id="93be9-151">I criteri di esito positivo sono infine il set di barre su misura rispetto a ciò che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="93be9-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="93be9-152">Se si sta testando Microsoft Threat Protection (o qualsiasi altra tecnologia per questo motivo) rispetto ad altri strumenti o da solo, devono essere disponibili alcuni criteri quantificabili per determinare il valore fornito dallo strumento.</span><span class="sxs-lookup"><span data-stu-id="93be9-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="93be9-153">In base all'ambito, ai requisiti e al piano di testing, i criteri di esito positivo determineranno la modalità di valutazione del test.</span><span class="sxs-lookup"><span data-stu-id="93be9-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="93be9-154">Questo valore deve essere inferiore a un passaggio o a un errore e più di un punteggio ponderato in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="93be9-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="93be9-155">Ad esempio, per avere esito positivo, potrebbe essere necessario uno strumento per ottenere un punteggio maggiore di 80% in determinate aree critiche identificate.</span><span class="sxs-lookup"><span data-stu-id="93be9-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="93be9-156">Scorecard</span><span class="sxs-lookup"><span data-stu-id="93be9-156">Scorecard</span></span>

<span data-ttu-id="93be9-157">Un modo per portare insieme tutti gli elementi del piano può essere quello di creare una scorecard.</span><span class="sxs-lookup"><span data-stu-id="93be9-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="93be9-158">Vedere una scorecard di esempio in basso:</span><span class="sxs-lookup"><span data-stu-id="93be9-158">See a sample scorecard below:</span></span>

|<span data-ttu-id="93be9-159">**Use case**</span><span class="sxs-lookup"><span data-stu-id="93be9-159">**Use case**</span></span>|<span data-ttu-id="93be9-160">**Requisiti**</span><span class="sxs-lookup"><span data-stu-id="93be9-160">**Requirements**</span></span>|<span data-ttu-id="93be9-161">**Requisiti di configurazione**</span><span class="sxs-lookup"><span data-stu-id="93be9-161">**Configuration requirements**</span></span>|<span data-ttu-id="93be9-162">**Piano di testing**</span><span class="sxs-lookup"><span data-stu-id="93be9-162">**Test plan**</span></span>|<span data-ttu-id="93be9-163">**Risultato previsto**</span><span class="sxs-lookup"><span data-stu-id="93be9-163">**Expected outcome**</span></span>|<span data-ttu-id="93be9-164">**Stato del test**</span><span class="sxs-lookup"><span data-stu-id="93be9-164">**Test status**</span></span>|<span data-ttu-id="93be9-165">**Punteggio**</span><span class="sxs-lookup"><span data-stu-id="93be9-165">**Score**</span></span>|<span data-ttu-id="93be9-166">**Note**</span><span class="sxs-lookup"><span data-stu-id="93be9-166">**Notes**</span></span>|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="93be9-167">Gestione degli incidenti</span><span class="sxs-lookup"><span data-stu-id="93be9-167">Incident management</span></span>|<span data-ttu-id="93be9-168">-Protezione dalle minacce di Microsoft</span><span class="sxs-lookup"><span data-stu-id="93be9-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="93be9-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-169">- Azure ATP</span></span> </br></br><span data-ttu-id="93be9-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="93be9-171">-Protezione delle app di Microsoft Cloud (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="93be9-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="93be9-172">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="93be9-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="93be9-173">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="93be9-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="93be9-174">Esaminare l'evento Incident</span><span class="sxs-lookup"><span data-stu-id="93be9-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="93be9-175">Gli investigatori possono comprendere l'ambito e l'impatto dell'incidente e gestire l'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="93be9-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="93be9-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="93be9-176">AutoIR</span></span>|<span data-ttu-id="93be9-177">-Protezione dalle minacce di Microsoft</span><span class="sxs-lookup"><span data-stu-id="93be9-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="93be9-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-178">- Azure ATP</span></span> </br></br><span data-ttu-id="93be9-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="93be9-180">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="93be9-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="93be9-181">Abilitare AutoIR</span><span class="sxs-lookup"><span data-stu-id="93be9-181">Enable AutoIR</span></span>  |[<span data-ttu-id="93be9-182">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="93be9-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="93be9-183">Analisi automatizzata</span><span class="sxs-lookup"><span data-stu-id="93be9-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="93be9-184">Gli avvisi e gli eventi non consentiti vengono corretti automaticamente da Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="93be9-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="93be9-185">Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="93be9-185">Advanced hunting</span></span>|<span data-ttu-id="93be9-186">-Protezione dalle minacce di Microsoft</span><span class="sxs-lookup"><span data-stu-id="93be9-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="93be9-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="93be9-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="93be9-188">- Office 365 ATP</span></span>   |<span data-ttu-id="93be9-189">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="93be9-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="93be9-190">Scenario di caccia avanzato</span><span class="sxs-lookup"><span data-stu-id="93be9-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="93be9-191">Gli investigatori possono trovare dati tramite la ricerca avanzata, pivoting alle entità interessate e creando rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="93be9-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="93be9-192">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="93be9-192">Next step</span></span>
|<span data-ttu-id="93be9-193">![Fase di preparazione](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="93be9-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="93be9-194">Fase di preparazione</span><span class="sxs-lookup"><span data-stu-id="93be9-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="93be9-195">Preparare l'ambiente pilota di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="93be9-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
