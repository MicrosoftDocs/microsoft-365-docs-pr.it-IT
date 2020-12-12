---
title: Eseguire il progetto pilota Microsoft 365 Defender
description: Eseguire il progetto pilota Microsoft 365 Defender in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Pilota di Microsoft Threat Protection, eseguire il progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, progetto pilota di Microsoft Threat Protection, sicurezza cibernetica, Advanced Persistent Threat, sicurezza dell'organizzazione, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659322"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="cdf11-104">Eseguire il progetto pilota Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdf11-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cdf11-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cdf11-105">**Applies to:**</span></span>
- <span data-ttu-id="cdf11-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdf11-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="cdf11-107">In questa guida viene illustrato come eseguire un progetto pilota fornendo puntatori per garantire che si disponga di un piano ben strutturato, che consenta di utilizzare la funzionalità di simulazione degli attacchi e infine di concludere il pilota con i principali take-away per riflettere e documentare i risultati.</span><span class="sxs-lookup"><span data-stu-id="cdf11-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasi di esecuzione di un pilota Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="cdf11-109">L'esecuzione di un progetto pilota consente di determinare efficacemente il vantaggio di adoptiing Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="cdf11-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="cdf11-110">Prima di abilitare Microsoft 365 Defender nell'ambiente di produzione e iniziare i casi di utilizzo, è preferibile pianificare la determinazione delle attività da eseguire per il progetto pilota e impostare i criteri di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf11-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="cdf11-111">Come usare questo pilota PlayBook</span><span class="sxs-lookup"><span data-stu-id="cdf11-111">How to use this pilot playbook</span></span>

<span data-ttu-id="cdf11-112">In questa guida viene fornita una panoramica di Microsoft 365 Defender e istruzioni dettagliate su come configurare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="cdf11-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="cdf11-113">Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale unificata che coordina in modo nativo la protezione, il rilevamento, la prevenzione, l'analisi e la risposta tra endpoint, identità, posta elettronica e applicazioni per garantire la protezione integrata da attacchi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="cdf11-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="cdf11-114">In questo modo, combinando e orchestrando le funzionalità seguenti in una singola soluzione di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="cdf11-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="cdf11-115">Microsoft Defender per endpoint, il nuovo nome di Microsoft Defender Advanced Threat Protection (Endpoints)</span><span class="sxs-lookup"><span data-stu-id="cdf11-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="cdf11-116">Microsoft Defender per Office 365, il nuovo nome per Office 365 ATP (posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="cdf11-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="cdf11-117">Microsoft Defender per Identity, il nuovo nome per Azure ATP (Identity)</span><span class="sxs-lookup"><span data-stu-id="cdf11-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="cdf11-118">Sicurezza delle app di Microsoft Cloud (app)</span><span class="sxs-lookup"><span data-stu-id="cdf11-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft soluzione Defender di 365 per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender per endpoint, per le app Cloud, per la sicurezza di Microsoft cloud app e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="cdf11-120">Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia che Microsoft Defender per endpoint, Microsoft Defender per Office 365, Microsoft Defender per Identity e Microsoft cloud app Security ricevono e determinare l'ambito e l'impatto completo della minaccia, il modo in cui è entrata nell'ambiente, le conseguenze e la modalità di impatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cdf11-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="cdf11-121">Microsoft 365 Defender esegue un'azione automatica per impedire o arrestare le cassette postali, gli endpoint e le identità degli utenti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="cdf11-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="cdf11-122">Per informazioni dettagliate, vedere [Microsoft 365 Defender Overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .</span><span class="sxs-lookup"><span data-stu-id="cdf11-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="cdf11-123">La sequenza temporale di esempio seguente varia a seconda dell'utilizzo delle risorse corrette nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="cdf11-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="cdf11-124">Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="cdf11-124">Some detections and workflows might need more learning time than the others.</span></span>

![Sequenza temporale di esempio per l'esecuzione di un pilota Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="cdf11-126">Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="cdf11-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="cdf11-127">Fasi pilota del PlayBook</span><span class="sxs-lookup"><span data-stu-id="cdf11-127">Pilot playbook phases</span></span> 

<span data-ttu-id="cdf11-128">Sono disponibili quattro fasi per l'esecuzione di un pilota Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="cdf11-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="cdf11-129">Fase</span><span class="sxs-lookup"><span data-stu-id="cdf11-129">Phase</span></span> | <span data-ttu-id="cdf11-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdf11-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="cdf11-131">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="cdf11-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="cdf11-132">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="cdf11-132">~ 1 day</span></span>| <span data-ttu-id="cdf11-133">Informazioni su ciò che è necessario prendere in considerazione prima di eseguire il progetto pilota Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="cdf11-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="cdf11-134">-Scope</span><span class="sxs-lookup"><span data-stu-id="cdf11-134">- Scope</span></span> <br> <span data-ttu-id="cdf11-135">-Use Cases</span><span class="sxs-lookup"><span data-stu-id="cdf11-135">- Use cases</span></span> <br><span data-ttu-id="cdf11-136">- Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdf11-136">- Requirements</span></span> <br><span data-ttu-id="cdf11-137">-Piano di testing</span><span class="sxs-lookup"><span data-stu-id="cdf11-137">- Test plan</span></span> <br> <span data-ttu-id="cdf11-138">-Criteri di esito positivo</span><span class="sxs-lookup"><span data-stu-id="cdf11-138">- Success criteria</span></span> <br> <span data-ttu-id="cdf11-139">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="cdf11-139">- Scorecard</span></span> 
| [<span data-ttu-id="cdf11-140">Preparazione</span><span class="sxs-lookup"><span data-stu-id="cdf11-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="cdf11-141">~ 2 giorni</span><span class="sxs-lookup"><span data-stu-id="cdf11-141">~2 days</span></span>|  <span data-ttu-id="cdf11-142">Accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="cdf11-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="cdf11-143">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="cdf11-143">You'll be guided to:</span></span><br><br><span data-ttu-id="cdf11-144">-Identificare le parti interessate e cercare l'accesso per il pilota</span><span class="sxs-lookup"><span data-stu-id="cdf11-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="cdf11-145">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="cdf11-145">- Environment considerations</span></span> <br><span data-ttu-id="cdf11-146">-Access</span><span class="sxs-lookup"><span data-stu-id="cdf11-146">- Access</span></span> <br><span data-ttu-id="cdf11-147">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cdf11-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="cdf11-148">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="cdf11-148">- Configuration order</span></span> <br> <span data-ttu-id="cdf11-149">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cdf11-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="cdf11-150">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="cdf11-150">- Configure domain</span></span> <br><span data-ttu-id="cdf11-151">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cdf11-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="cdf11-152">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="cdf11-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="cdf11-153">Simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="cdf11-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="cdf11-154">~ 2 giorni</span><span class="sxs-lookup"><span data-stu-id="cdf11-154">~2 days</span></span>| <span data-ttu-id="cdf11-155">Per simulare un attacco, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf11-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="cdf11-156">-Verificare i requisiti dell'ambiente di testing</span><span class="sxs-lookup"><span data-stu-id="cdf11-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="cdf11-157">-Eseguire la simulazione</span><span class="sxs-lookup"><span data-stu-id="cdf11-157">-  Run the simulation</span></span> <br><span data-ttu-id="cdf11-158">-Indagare su un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="cdf11-158">- Investigate an incident</span></span> <br><span data-ttu-id="cdf11-159">-risolvere l'evento non consentita</span><span class="sxs-lookup"><span data-stu-id="cdf11-159">- resolve the incident</span></span> 
| [<span data-ttu-id="cdf11-160">Chiusura e riepilogo</span><span class="sxs-lookup"><span data-stu-id="cdf11-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="cdf11-161">~ 1 giorno</span><span class="sxs-lookup"><span data-stu-id="cdf11-161">~ 1 day</span></span>| <span data-ttu-id="cdf11-162">Dopo aver raggiunto la fine del processo, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="cdf11-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="cdf11-163">-Passare attraverso l'output finale</span><span class="sxs-lookup"><span data-stu-id="cdf11-163">- Go through your final output</span></span><br><span data-ttu-id="cdf11-164">-Presentare l'output alle parti interessate</span><span class="sxs-lookup"><span data-stu-id="cdf11-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="cdf11-165">-Fornire commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="cdf11-165">- Provide feedback</span></span> <br><span data-ttu-id="cdf11-166">-Eseguire i passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cdf11-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="cdf11-167">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="cdf11-167">Next step</span></span>
|[<span data-ttu-id="cdf11-168">Fase di pianificazione</span><span class="sxs-lookup"><span data-stu-id="cdf11-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="cdf11-169">Pianificare il progetto pilota Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdf11-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
