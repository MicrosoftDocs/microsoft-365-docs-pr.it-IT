---
title: Eseguire il progetto pilota di Microsoft 365 Defender
description: Eseguire il progetto pilota di Microsoft 365 Defender in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Progetto pilota di Microsoft Threat Protection, eseguire un progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, progetto pilota di Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, eventi imprevisti, analisi e correzione automatizzate, ricerca avanzata
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933031"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="e18bf-104">Eseguire il progetto pilota di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e18bf-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e18bf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e18bf-105">**Applies to:**</span></span>
- <span data-ttu-id="e18bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e18bf-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e18bf-107">Questa guida consente di eseguire un progetto pilota fornendo puntatori per assicurarsi di disporre di un piano ben strutturato, guidando l'utente attraverso l'uso della funzionalità di simulazione degli attacchi e infine concludendo il progetto pilota con le principali attività da eseguire per riflettere e documentare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e18bf-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasi dell'esecuzione di un progetto pilota di Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="e18bf-109">L'esecuzione di un progetto pilota consente di determinare in modo efficace i vantaggi dell'adozione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e18bf-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="e18bf-110">Prima di abilitare Microsoft 365 Defender nell'ambiente di produzione e iniziare i casi d'uso, è meglio pianificare di determinare le attività da eseguire per il progetto pilota e impostare i criteri di successo.</span><span class="sxs-lookup"><span data-stu-id="e18bf-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="e18bf-111">Come usare questo playbook pilota</span><span class="sxs-lookup"><span data-stu-id="e18bf-111">How to use this pilot playbook</span></span>

<span data-ttu-id="e18bf-112">Questa guida fornisce una panoramica di Microsoft 365 Defender e istruzioni dettagliate su come configurare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="e18bf-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="e18bf-113">Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale pre e post-violazione unificata che coordina in modo nativo la protezione, il rilevamento, la prevenzione, l'indagine e la risposta tra endpoint, identità, posta elettronica e applicazioni per fornire protezione integrata da attacchi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="e18bf-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="e18bf-114">A tale scopo, combinando e orchestrando le funzionalità seguenti in un'unica soluzione di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="e18bf-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="e18bf-115">Microsoft Defender for Endpoint, il nuovo nome per Microsoft Defender Advanced Threat Protection (endpoint)</span><span class="sxs-lookup"><span data-stu-id="e18bf-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="e18bf-116">Microsoft Defender per Office 365, il nuovo nome per Office 365 ATP (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="e18bf-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="e18bf-117">Microsoft Defender for Identity, il nuovo nome per Azure ATP (identità)</span><span class="sxs-lookup"><span data-stu-id="e18bf-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="e18bf-118">Microsoft Cloud App Security (app)</span><span class="sxs-lookup"><span data-stu-id="e18bf-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="e18bf-120">Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia ricevuti da Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Defender for Identity e Microsoft Cloud App Security e determinare l'ambito completo e l'impatto della minaccia, come è entrato nell'ambiente, cosa ne è interessato e in che modo influisce attualmente sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e18bf-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="e18bf-121">Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="e18bf-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="e18bf-122">Per informazioni dettagliate, vedere la panoramica [di Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="e18bf-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="e18bf-123">La sequenza temporale di esempio seguente varia in base alla disponibilità delle risorse giuste nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e18bf-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="e18bf-124">Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="e18bf-124">Some detections and workflows might need more learning time than the others.</span></span>

![Sequenza temporale di esempio nell'esecuzione di un progetto pilota di Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="e18bf-126">Per ottenere risultati ottimali, seguire le istruzioni pilota il più attentamente possibile.</span><span class="sxs-lookup"><span data-stu-id="e18bf-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="e18bf-127">Fasi del playbook pilota</span><span class="sxs-lookup"><span data-stu-id="e18bf-127">Pilot playbook phases</span></span> 

<span data-ttu-id="e18bf-128">L'esecuzione di un progetto pilota di Microsoft 365 Defender è in quattro fasi:</span><span class="sxs-lookup"><span data-stu-id="e18bf-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="e18bf-129">Fase</span><span class="sxs-lookup"><span data-stu-id="e18bf-129">Phase</span></span> | <span data-ttu-id="e18bf-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e18bf-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="e18bf-131">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="e18bf-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="e18bf-132">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="e18bf-132">~ 1 day</span></span>| <span data-ttu-id="e18bf-133">Informazioni su cosa è necessario considerare prima di eseguire il progetto pilota di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="e18bf-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="e18bf-134">- Ambito</span><span class="sxs-lookup"><span data-stu-id="e18bf-134">- Scope</span></span> <br> <span data-ttu-id="e18bf-135">- Casi d'uso</span><span class="sxs-lookup"><span data-stu-id="e18bf-135">- Use cases</span></span> <br><span data-ttu-id="e18bf-136">- Requisiti</span><span class="sxs-lookup"><span data-stu-id="e18bf-136">- Requirements</span></span> <br><span data-ttu-id="e18bf-137">- Piano di test</span><span class="sxs-lookup"><span data-stu-id="e18bf-137">- Test plan</span></span> <br> <span data-ttu-id="e18bf-138">- Criteri di successo</span><span class="sxs-lookup"><span data-stu-id="e18bf-138">- Success criteria</span></span> <br> <span data-ttu-id="e18bf-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="e18bf-139">- Scorecard</span></span> 
| [<span data-ttu-id="e18bf-140">Preparazione</span><span class="sxs-lookup"><span data-stu-id="e18bf-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="e18bf-141">~2 giorni</span><span class="sxs-lookup"><span data-stu-id="e18bf-141">~2 days</span></span>|  <span data-ttu-id="e18bf-142">Accedere al Centro sicurezza Microsoft 365 per configurare l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e18bf-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="e18bf-143">L'utente verrà guidato a:</span><span class="sxs-lookup"><span data-stu-id="e18bf-143">You'll be guided to:</span></span><br><br><span data-ttu-id="e18bf-144">- Identificare le parti interessate e richiedere la disconnessione per il progetto pilota</span><span class="sxs-lookup"><span data-stu-id="e18bf-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="e18bf-145">- Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="e18bf-145">- Environment considerations</span></span> <br><span data-ttu-id="e18bf-146">- Access</span><span class="sxs-lookup"><span data-stu-id="e18bf-146">- Access</span></span> <br><span data-ttu-id="e18bf-147">- Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e18bf-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e18bf-148">- Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="e18bf-148">- Configuration order</span></span> <br> <span data-ttu-id="e18bf-149">- Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e18bf-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="e18bf-150">- Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="e18bf-150">- Configure domain</span></span> <br><span data-ttu-id="e18bf-151">- Assegnare le licenze di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e18bf-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="e18bf-152">- Completare la configurazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="e18bf-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="e18bf-153">Simulazione degli attacchi</span><span class="sxs-lookup"><span data-stu-id="e18bf-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="e18bf-154">~2 giorni</span><span class="sxs-lookup"><span data-stu-id="e18bf-154">~2 days</span></span>| <span data-ttu-id="e18bf-155">Per simulare un attacco, verrà indicato come:</span><span class="sxs-lookup"><span data-stu-id="e18bf-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="e18bf-156">- Verificare i requisiti dell'ambiente di testing</span><span class="sxs-lookup"><span data-stu-id="e18bf-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="e18bf-157">- Eseguire la simulazione</span><span class="sxs-lookup"><span data-stu-id="e18bf-157">-  Run the simulation</span></span> <br><span data-ttu-id="e18bf-158">- Analizzare un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e18bf-158">- Investigate an incident</span></span> <br><span data-ttu-id="e18bf-159">- Risolvere l'evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="e18bf-159">- resolve the incident</span></span> 
| [<span data-ttu-id="e18bf-160">Chiusura e riepilogo</span><span class="sxs-lookup"><span data-stu-id="e18bf-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="e18bf-161">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="e18bf-161">~ 1 day</span></span>| <span data-ttu-id="e18bf-162">Una volta raggiunta la fine del processo, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="e18bf-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="e18bf-163">- Passare attraverso l'output finale</span><span class="sxs-lookup"><span data-stu-id="e18bf-163">- Go through your final output</span></span><br><span data-ttu-id="e18bf-164">- Presentare l'output alle parti interessate</span><span class="sxs-lookup"><span data-stu-id="e18bf-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="e18bf-165">- Inviare commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="e18bf-165">- Provide feedback</span></span> <br><span data-ttu-id="e18bf-166">- Eseguire i passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e18bf-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="e18bf-167">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e18bf-167">Next step</span></span>
|[<span data-ttu-id="e18bf-168">Fase di pianificazione</span><span class="sxs-lookup"><span data-stu-id="e18bf-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="e18bf-169">Pianificare il progetto pilota di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e18bf-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
