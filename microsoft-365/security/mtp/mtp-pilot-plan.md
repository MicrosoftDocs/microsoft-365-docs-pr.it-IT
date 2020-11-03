---
title: Pianificazione del progetto pilota Microsoft 365 Defender
description: Pianificare il progetto pilota Microsoft 365 Defender con le parti interessate per gestire le aspettative e garantire esito positivo.
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: ec2bfe52308231577e4f2749e1f4cdf24a36f604
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846021"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="6f9c7-104">Pianificazione del progetto pilota Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-104">Planning your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6f9c7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6f9c7-105">**Applies to:**</span></span>
- <span data-ttu-id="6f9c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Pianificare il progetto pilota Microsoft 365 Defender" />
      <br/><span data-ttu-id="6f9c7-108">Pianificare</a></span><span class="sxs-lookup"><span data-stu-id="6f9c7-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/><span data-ttu-id="6f9c7-110">Preparazione</a></span><span class="sxs-lookup"><span data-stu-id="6f9c7-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Eseguire le simulazioni di attacco di Microsoft 365 Defender" />
     <br/><span data-ttu-id="6f9c7-112">Simula attacco</a></span><span class="sxs-lookup"><span data-stu-id="6f9c7-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Chiudere e riepilogare il pilota Microsoft 365 Defender" />
     <br/><span data-ttu-id="6f9c7-114">Chiudi e riepiloga</a></span><span class="sxs-lookup"><span data-stu-id="6f9c7-114">Close and summarize</a></span></span><br>
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

<span data-ttu-id="6f9c7-115">Si è attualmente in fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="6f9c7-116">Per assicurarsi che il progetto pilota sia un successo, è essenziale pianificare con attenzione e ottenere le approvazioni dalle parti interessate all'inizio.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="6f9c7-117">Gli elementi di pianificazione includono l'ambito di identificazione, i casi di utilizzo, i requisiti e i criteri di successo.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="6f9c7-118">In questa guida viene illustrato come pianificare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="6f9c7-119">Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="6f9c7-120">Scope</span><span class="sxs-lookup"><span data-stu-id="6f9c7-120">Scope</span></span>

<span data-ttu-id="6f9c7-121">L'ambito del progetto pilota determinerà il livello di ampiezza del test, in base all'ambiente e ai metodi di testing accettabili.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="6f9c7-122">Di seguito sono riportate alcune considerazioni di esempio:</span><span class="sxs-lookup"><span data-stu-id="6f9c7-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="6f9c7-123">Ambiente di sviluppo o di testing che include endpoint, server, controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="6f9c7-124">Ambiente di produzione con Microsoft 365, Azure, servizi, endpoint e server di Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f9c7-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="6f9c7-125">[! Nota] se non si dispone ancora delle licenze complete, è possibile ottenere licenze di prova per [valutare Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – pianificare, preparare, installare, configurare ed eseguire il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="6f9c7-126">Le parti interessate giocheranno un ruolo importante nell'agevolare il processo dall'inizio alla fine.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="6f9c7-127">I tipi di sistemi operativi da valutare devono essere anche definiti in base al trucco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="6f9c7-128">Questo può includere gli [endpoint Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), i [server Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), gli [endpoint di windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="6f9c7-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="6f9c7-129">Casi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="6f9c7-129">Use cases</span></span>

<span data-ttu-id="6f9c7-130">I casi di utilizzo rappresentano istruzioni sul modo in cui lo strumento da testare deve essere utilizzato dagli utenti previsti.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="6f9c7-131">Tali informazioni possono essere formulate come storie utente dal punto di vista di una persona specifica, ad esempio un analista SOC.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="6f9c7-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6f9c7-132">For example:</span></span>
- <span data-ttu-id="6f9c7-133">Come analista SOC, è necessario visualizzare, correlare, valutare e gestire avvisi ed eventi tra i dispositivi, gli utenti e le cassette postali della rete.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="6f9c7-134">[Gestione degli incidenti]</span><span class="sxs-lookup"><span data-stu-id="6f9c7-134">[Incident management]</span></span>
- <span data-ttu-id="6f9c7-135">Come analista SOC, è necessario disporre dello strumento e del processo per analizzare e rispondere automaticamente agli eventi dannosi nella rete.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="6f9c7-136">[IR automatico]</span><span class="sxs-lookup"><span data-stu-id="6f9c7-136">[Auto IR]</span></span>
- <span data-ttu-id="6f9c7-137">Come analista SOC, è necessario eseguire la ricerca dei dati dal proprio ambiente per individuare minacce note e potenziali e attività sospette.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="6f9c7-138">[Caccia avanzata]</span><span class="sxs-lookup"><span data-stu-id="6f9c7-138">[Advanced Hunting]</span></span>

<span data-ttu-id="6f9c7-139">Tenere presente che questi casi di utilizzo devono essere creati all'interno dei parametri dell'ambito definito.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="6f9c7-140">Se, ad esempio, l'ambito del testing non include una valutazione di strumenti quali Microsoft cloud app Security, utilizzare i casi che si basano su questa operazione come origine dati non deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f9c7-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f9c7-141">Requirements</span></span>

<span data-ttu-id="6f9c7-142">Nell'elenco dei casi di utilizzo è possibile iniziare a creare i requisiti.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="6f9c7-143">Requisiti: funzionalità è necessario uno strumento per soddisfare i casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="6f9c7-144">Questi requisiti possono essere suddivisi in categorie quali la configurazione e la manutenzione, il supporto per le integrazioni e i requisiti specifici per le funzionalità come la capacità di caccia e la possibilità di creare avvisi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="6f9c7-145">Piano di testing</span><span class="sxs-lookup"><span data-stu-id="6f9c7-145">Test plan</span></span>

<span data-ttu-id="6f9c7-146">A seconda dei requisiti, è possibile che i diversi metodi di test siano adatti.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="6f9c7-147">Ad esempio, se l'esigenza è quella di valutare l'efficacia della correzione automatica, il piano di test deve includere dei passaggi per generare i comportamenti che avrebbero attivato un'azione di correzione automatica all'interno di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft 365 Defender.</span></span> <span data-ttu-id="6f9c7-148">Se il requisito consiste nel rilevare un comportamento o un attacco specifico, il test può comportare più passaggi.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="6f9c7-149">Il punto è che è necessario disporre di un piano per testare accuratamente le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="6f9c7-150">Criteri di esito positivo</span><span class="sxs-lookup"><span data-stu-id="6f9c7-150">Success criteria</span></span>

<span data-ttu-id="6f9c7-151">I criteri di esito positivo sono infine il set di barre su misura rispetto a ciò che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="6f9c7-152">Se si sta testando Microsoft 365 Defender (o qualsiasi altra tecnologia per questo motivo) rispetto ad altri strumenti o da solo, devono essere disponibili alcuni criteri quantificabili per determinare il valore fornito dallo strumento.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-152">Whether you are testing Microsoft 365 Defender (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="6f9c7-153">In base all'ambito, ai requisiti e al piano di testing, i criteri di esito positivo determineranno la modalità di valutazione del test.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="6f9c7-154">Questo valore deve essere inferiore a un passaggio o a un errore e più di un punteggio ponderato in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="6f9c7-155">Ad esempio, per avere esito positivo, potrebbe essere necessario uno strumento per ottenere un punteggio maggiore di 80% in determinate aree critiche identificate.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="6f9c7-156">Scorecard</span><span class="sxs-lookup"><span data-stu-id="6f9c7-156">Scorecard</span></span>

<span data-ttu-id="6f9c7-157">Un modo per portare insieme tutti gli elementi del piano può essere quello di creare una scorecard.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="6f9c7-158">Vedere una scorecard di esempio in basso:</span><span class="sxs-lookup"><span data-stu-id="6f9c7-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="6f9c7-159">Use case</span><span class="sxs-lookup"><span data-stu-id="6f9c7-159">Use case</span></span> | <span data-ttu-id="6f9c7-160">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f9c7-160">Requirements</span></span> | <span data-ttu-id="6f9c7-161">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="6f9c7-161">Configuration requirements</span></span> | <span data-ttu-id="6f9c7-162">Piano di testing</span><span class="sxs-lookup"><span data-stu-id="6f9c7-162">Test plan</span></span> | <span data-ttu-id="6f9c7-163">Risultato previsto</span><span class="sxs-lookup"><span data-stu-id="6f9c7-163">Expected outcome</span></span> | <span data-ttu-id="6f9c7-164">Stato del test</span><span class="sxs-lookup"><span data-stu-id="6f9c7-164">Test status</span></span> | <span data-ttu-id="6f9c7-165">Punteggio</span><span class="sxs-lookup"><span data-stu-id="6f9c7-165">Score</span></span> | <span data-ttu-id="6f9c7-166">Note</span><span class="sxs-lookup"><span data-stu-id="6f9c7-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="6f9c7-167">Gestione degli incidenti</span><span class="sxs-lookup"><span data-stu-id="6f9c7-167">Incident management</span></span>|<span data-ttu-id="6f9c7-168">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-168">-  Microsoft 365 Defender</span></span>  </br></br><span data-ttu-id="6f9c7-169">-Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="6f9c7-169">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="6f9c7-170">-Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6f9c7-170">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="6f9c7-171">-Protezione delle app di Microsoft Cloud (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="6f9c7-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="6f9c7-172">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="6f9c7-173">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="6f9c7-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="6f9c7-174">Esaminare l'evento Incident</span><span class="sxs-lookup"><span data-stu-id="6f9c7-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="6f9c7-175">Gli investigatori possono comprendere l'ambito e l'impatto dell'incidente e gestire l'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="6f9c7-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="6f9c7-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="6f9c7-176">AutoIR</span></span>|<span data-ttu-id="6f9c7-177">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-177">-   Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="6f9c7-178">-Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="6f9c7-178">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="6f9c7-179">-Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6f9c7-179">- Microsoft Defender for Endpoint</span></span> |<span data-ttu-id="6f9c7-180">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="6f9c7-181">Abilitare AutoIR</span><span class="sxs-lookup"><span data-stu-id="6f9c7-181">Enable AutoIR</span></span>  |[<span data-ttu-id="6f9c7-182">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="6f9c7-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="6f9c7-183">Analisi automatizzata</span><span class="sxs-lookup"><span data-stu-id="6f9c7-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="6f9c7-184">Gli avvisi e gli eventi non consentiti vengono automaticamente corretti da Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-184">Alerts and incidents are automatically remediated by Microsoft 365 Defender</span></span>||||
|<span data-ttu-id="6f9c7-185">Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6f9c7-185">Advanced hunting</span></span>|<span data-ttu-id="6f9c7-186">-Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-186">- Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="6f9c7-187">-Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6f9c7-187">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="6f9c7-188">-Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6f9c7-188">-Microsoft Defender for Office 365</span></span> |<span data-ttu-id="6f9c7-189">Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="6f9c7-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="6f9c7-190">Scenario di caccia avanzato</span><span class="sxs-lookup"><span data-stu-id="6f9c7-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="6f9c7-191">Gli investigatori possono trovare dati tramite la ricerca avanzata, pivoting alle entità interessate e creando rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="6f9c7-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="6f9c7-192">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6f9c7-192">Next step</span></span>
|<span data-ttu-id="6f9c7-193">![Fase di preparazione](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="6f9c7-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="6f9c7-194">Fase di preparazione</span><span class="sxs-lookup"><span data-stu-id="6f9c7-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="6f9c7-195">Preparare l'ambiente pilota Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f9c7-195">Prepare your Microsoft 365 Defender pilot environment</span></span>
|:-------|:-----|
