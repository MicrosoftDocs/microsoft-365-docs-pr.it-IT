---
title: Eseguire il progetto pilota Microsoft 365 Defender progetto
description: Eseguire il progetto Microsoft 365 Defender progetto pilota nell'ambiente di produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Microsoft 365 Defender pilota, eseguire un progetto pilota Microsoft 365 Defender, valutare Microsoft 365 Defender in produzione, progetto pilota Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289956"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="e4d4a-104">Eseguire il progetto pilota Microsoft 365 Defender progetto</span><span class="sxs-lookup"><span data-stu-id="e4d4a-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e4d4a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e4d4a-105">**Applies to:**</span></span>
- <span data-ttu-id="e4d4a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4d4a-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e4d4a-107">Questa guida consente di eseguire un progetto pilota fornendo puntatori per garantire un piano ben strutturato, guidando l'utente attraverso l'utilizzo della funzionalità di simulazione degli attacchi e infine concludendo il progetto pilota con le principali attività da eseguire per riflettere e documentare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasi dell'esecuzione di un Microsoft 365 Defender pilota](../../media/pilotphases.png)


<span data-ttu-id="e4d4a-109">L'esecuzione di un progetto pilota consente di determinare in modo efficace i vantaggi dell'adozione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="e4d4a-110">Prima di Microsoft 365 Defender nell'ambiente di produzione e avviare i casi di utilizzo, è meglio pianificare le attività da eseguire per il progetto pilota e impostare i criteri di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="e4d4a-111">Come usare questo playbook pilota</span><span class="sxs-lookup"><span data-stu-id="e4d4a-111">How to use this pilot playbook</span></span>

<span data-ttu-id="e4d4a-112">Questa guida fornisce una panoramica Microsoft 365 Defender istruzioni dettagliate su come configurare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="e4d4a-113">Microsoft 365 Defender è una suite di difesa aziendale unificata pre e post-violazione che coordina in modo nativo protezione, rilevamento, prevenzione, indagine e risposta tra endpoint, identità, posta elettronica e applicazioni per fornire una protezione integrata da attacchi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="e4d4a-114">A tale scopo, combinando e orchestrando le funzionalità seguenti in un'unica soluzione di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>

- <span data-ttu-id="e4d4a-115">Microsoft Defender per endpoint (endpoint)</span><span class="sxs-lookup"><span data-stu-id="e4d4a-115">Microsoft Defender for Endpoint (endpoints)</span></span>
- <span data-ttu-id="e4d4a-116">Microsoft Defender per Office 365 (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="e4d4a-116">Microsoft Defender for Office 365 (email)</span></span>
- <span data-ttu-id="e4d4a-117">Microsoft Defender for Identity (identità)</span><span class="sxs-lookup"><span data-stu-id="e4d4a-117">Microsoft Defender for Identity (identity)</span></span>
- <span data-ttu-id="e4d4a-118">Microsoft Cloud App Security (app)</span><span class="sxs-lookup"><span data-stu-id="e4d4a-118">Microsoft Cloud App Security (apps)</span></span>

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="e4d4a-120">Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia ricevuti da Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Defender for Identity e Microsoft Cloud App Security e determinare l'ambito completo e l'impatto della minaccia, il modo in cui è entrata nell'ambiente, le conseguenze e il suo impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="e4d4a-121">Microsoft 365 Defender azioni automatiche per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="e4d4a-122">Per informazioni [dettagliate, Microsoft 365 Defender panoramica dei](microsoft-365-defender.md) dati.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>

<span data-ttu-id="e4d4a-123">La sequenza temporale di esempio seguente varia a seconda della disponibilità delle risorse giuste nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="e4d4a-124">Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-124">Some detections and workflows might need more learning time than the others.</span></span>

![Sequenza temporale di esempio nell'esecuzione di Microsoft 365 Defender pilota](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> <span data-ttu-id="e4d4a-126">Per ottenere risultati ottimali, seguire le istruzioni pilota il più possibile.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>

### <a name="pilot-playbook-phases"></a><span data-ttu-id="e4d4a-127">Fasi del playbook pilota</span><span class="sxs-lookup"><span data-stu-id="e4d4a-127">Pilot playbook phases</span></span>

<span data-ttu-id="e4d4a-128">L'esecuzione di un progetto pilota Microsoft 365 Defender quattro fasi:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="e4d4a-129">Fase</span><span class="sxs-lookup"><span data-stu-id="e4d4a-129">Phase</span></span> | <span data-ttu-id="e4d4a-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-130">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="e4d4a-131">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="e4d4a-132">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="e4d4a-132">~ 1 day</span></span>| <span data-ttu-id="e4d4a-133">Informazioni su cosa è necessario prendere in considerazione prima di eseguire il Microsoft 365 Defender progetto pilota:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="e4d4a-134">- Ambito</span><span class="sxs-lookup"><span data-stu-id="e4d4a-134">- Scope</span></span> <br> <span data-ttu-id="e4d4a-135">- Casi d'uso</span><span class="sxs-lookup"><span data-stu-id="e4d4a-135">- Use cases</span></span> <br><span data-ttu-id="e4d4a-136">- Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4d4a-136">- Requirements</span></span> <br><span data-ttu-id="e4d4a-137">- Piano di test</span><span class="sxs-lookup"><span data-stu-id="e4d4a-137">- Test plan</span></span> <br> <span data-ttu-id="e4d4a-138">- Criteri di esito positivo</span><span class="sxs-lookup"><span data-stu-id="e4d4a-138">- Success criteria</span></span> <br> <span data-ttu-id="e4d4a-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="e4d4a-139">- Scorecard</span></span> 
| [<span data-ttu-id="e4d4a-140">Preparazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="e4d4a-141">~2 giorni</span><span class="sxs-lookup"><span data-stu-id="e4d4a-141">~2 days</span></span>|  <span data-ttu-id="e4d4a-142">Accedere Microsoft 365 Security Center per configurare l'Microsoft 365 Defender pilota.</span><span class="sxs-lookup"><span data-stu-id="e4d4a-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="e4d4a-143">Sarai guidato a:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-143">You'll be guided to:</span></span><br><br><span data-ttu-id="e4d4a-144">- Identificare le parti interessate e richiedere la disconnessione per il progetto pilota</span><span class="sxs-lookup"><span data-stu-id="e4d4a-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="e4d4a-145">- Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="e4d4a-145">- Environment considerations</span></span> <br><span data-ttu-id="e4d4a-146">- Accesso</span><span class="sxs-lookup"><span data-stu-id="e4d4a-146">- Access</span></span> <br><span data-ttu-id="e4d4a-147">- Azure Active Directory configurazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e4d4a-148">- Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-148">- Configuration order</span></span> <br> <span data-ttu-id="e4d4a-149">- Iscriversi per la Microsoft 365 E5 prova</span><span class="sxs-lookup"><span data-stu-id="e4d4a-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="e4d4a-150">- Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="e4d4a-150">- Configure domain</span></span> <br><span data-ttu-id="e4d4a-151">- Assegnare Microsoft 365 E5 licenze</span><span class="sxs-lookup"><span data-stu-id="e4d4a-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="e4d4a-152">- Completare la configurazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="e4d4a-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="e4d4a-153">Simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="e4d4a-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="e4d4a-154">~2 giorni</span><span class="sxs-lookup"><span data-stu-id="e4d4a-154">~2 days</span></span>| <span data-ttu-id="e4d4a-155">Per simulare un attacco, verrà indicato come:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="e4d4a-156">- Verificare i requisiti dell'ambiente di testing</span><span class="sxs-lookup"><span data-stu-id="e4d4a-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="e4d4a-157">- Eseguire la simulazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-157">-  Run the simulation</span></span> <br><span data-ttu-id="e4d4a-158">- Analizzare un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e4d4a-158">- Investigate an incident</span></span> <br><span data-ttu-id="e4d4a-159">- Risolvere l'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e4d4a-159">- resolve the incident</span></span> 
| [<span data-ttu-id="e4d4a-160">Chiusura e riepilogo</span><span class="sxs-lookup"><span data-stu-id="e4d4a-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="e4d4a-161">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="e4d4a-161">~ 1 day</span></span>| <span data-ttu-id="e4d4a-162">Una volta raggiunta la fine del processo, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="e4d4a-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="e4d4a-163">- Passare all'output finale</span><span class="sxs-lookup"><span data-stu-id="e4d4a-163">- Go through your final output</span></span><br><span data-ttu-id="e4d4a-164">- Presentare l'output ai cointeressati</span><span class="sxs-lookup"><span data-stu-id="e4d4a-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="e4d4a-165">- Fornire feedback</span><span class="sxs-lookup"><span data-stu-id="e4d4a-165">- Provide feedback</span></span> <br><span data-ttu-id="e4d4a-166">- Eseguire i passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e4d4a-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="e4d4a-167">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e4d4a-167">Next step</span></span>

|[<span data-ttu-id="e4d4a-168">Fase di pianificazione</span><span class="sxs-lookup"><span data-stu-id="e4d4a-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="e4d4a-169">Pianificare il Microsoft 365 Defender progetto pilota</span><span class="sxs-lookup"><span data-stu-id="e4d4a-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
