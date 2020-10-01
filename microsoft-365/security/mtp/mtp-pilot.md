---
title: Eseguire il progetto pilota di Microsoft Threat Protection
description: Eseguire il progetto pilota Microsoft Threat Protection in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft Threat Protection (MTP).
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 250c125648f734a13899a58dd22ee3bffb0921a9
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333735"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="23429-104">Eseguire il progetto pilota di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23429-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="23429-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="23429-105">**Applies to:**</span></span>
- <span data-ttu-id="23429-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23429-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="23429-107">Per determinare in modo efficace il vantaggio e l'adozione di Microsoft Threat Protection (MTP), è possibile eseguire un progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="23429-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="23429-108">Prima di abilitare Microsoft Threat Protection nell'ambiente di produzione e iniziare con i casi di utilizzo definiti, è preferibile passare attraverso un processo di pianificazione per determinare le attività che devono essere eseguite in questo progetto pilota e i criteri di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="23429-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="23429-109">Come usare questo pilota PlayBook</span><span class="sxs-lookup"><span data-stu-id="23429-109">How to use this pilot playbook</span></span>

<span data-ttu-id="23429-110">In questa guida viene fornita una panoramica di Microsoft Threat Protection e istruzioni dettagliate su come configurare il progetto pilota.</span><span class="sxs-lookup"><span data-stu-id="23429-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![Fasi di esecuzione di un pilota di Microsoft Threat Protection](../../media/pilotphases.png)

<span data-ttu-id="23429-112">La sequenza temporale di esempio seguente varia a seconda dell'utilizzo delle risorse corrette nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="23429-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="23429-113">Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.</span><span class="sxs-lookup"><span data-stu-id="23429-113">Some detections and workflows might need more learning time than the others.</span></span>

![Sequenza temporale di esempio per l'esecuzione di un pilota di Microsoft Threat Protection](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="23429-115">Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="23429-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="23429-116">Fasi pilota del PlayBook</span><span class="sxs-lookup"><span data-stu-id="23429-116">Pilot playbook phases</span></span> 

<span data-ttu-id="23429-117">Sono disponibili quattro fasi per l'esecuzione di un pilota di Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="23429-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="23429-118">Fase</span><span class="sxs-lookup"><span data-stu-id="23429-118">Phase</span></span> | <span data-ttu-id="23429-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23429-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="23429-120">![Pianificazione](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="23429-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="23429-121">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="23429-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="23429-122">Informazioni su ciò che è necessario prendere in considerazione prima di eseguire il progetto pilota di Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="23429-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="23429-123">-Scope</span><span class="sxs-lookup"><span data-stu-id="23429-123">- Scope</span></span> <br> <span data-ttu-id="23429-124">-Use Cases</span><span class="sxs-lookup"><span data-stu-id="23429-124">- Use cases</span></span> <br><span data-ttu-id="23429-125">- Requisiti</span><span class="sxs-lookup"><span data-stu-id="23429-125">- Requirements</span></span> <br><span data-ttu-id="23429-126">-Piano di testing</span><span class="sxs-lookup"><span data-stu-id="23429-126">- Test plan</span></span> <br> <span data-ttu-id="23429-127">-Criteri di esito positivo</span><span class="sxs-lookup"><span data-stu-id="23429-127">- Success criteria</span></span> <br> <span data-ttu-id="23429-128">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="23429-128">- Scorecard</span></span> 
| <span data-ttu-id="23429-129">![Preparazione](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="23429-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="23429-130">Preparazione</span><span class="sxs-lookup"><span data-stu-id="23429-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="23429-131">Accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="23429-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="23429-132">Verrà guidato per:</span><span class="sxs-lookup"><span data-stu-id="23429-132">You will be guided to:</span></span><br><br><span data-ttu-id="23429-133">-Identificare le parti interessate e cercare l'accesso per il pilota</span><span class="sxs-lookup"><span data-stu-id="23429-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="23429-134">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="23429-134">- Environment considerations</span></span> <br><span data-ttu-id="23429-135">-Access</span><span class="sxs-lookup"><span data-stu-id="23429-135">- Access</span></span> <br><span data-ttu-id="23429-136">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="23429-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="23429-137">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="23429-137">- Configuration order</span></span> <br> <span data-ttu-id="23429-138">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="23429-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="23429-139">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="23429-139">- Configure domain</span></span> <br><span data-ttu-id="23429-140">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="23429-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="23429-141">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="23429-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="23429-142">![Simulazione di attacco](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="23429-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="23429-143">Simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="23429-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="23429-144">Per simulare un attacco, sarà possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23429-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="23429-145">-Verificare i requisiti dell'ambiente di testing</span><span class="sxs-lookup"><span data-stu-id="23429-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="23429-146">-Eseguire la simulazione</span><span class="sxs-lookup"><span data-stu-id="23429-146">-  Run the simulation</span></span> <br><span data-ttu-id="23429-147">-Indagare su un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="23429-147">- Investigate an incident</span></span> <br><span data-ttu-id="23429-148">-risolvere l'evento non consentita</span><span class="sxs-lookup"><span data-stu-id="23429-148">- resolve the incident</span></span> 
| <span data-ttu-id="23429-149">![Chiusura e riepilogo](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="23429-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="23429-150">Chiusura e riepilogo</span><span class="sxs-lookup"><span data-stu-id="23429-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="23429-151">Dopo aver raggiunto la fine del processo, si verrà guidati a:</span><span class="sxs-lookup"><span data-stu-id="23429-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="23429-152">-Passare attraverso l'output finale</span><span class="sxs-lookup"><span data-stu-id="23429-152">- Go through your final output</span></span><br><span data-ttu-id="23429-153">-Presentare l'output alle parti interessate</span><span class="sxs-lookup"><span data-stu-id="23429-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="23429-154">-Fornire commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="23429-154">- Provide feedback</span></span> <br><span data-ttu-id="23429-155">-Eseguire i passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="23429-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="23429-156">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="23429-156">Next step</span></span>
|<span data-ttu-id="23429-157">![Fase di pianificazione](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="23429-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="23429-158">Fase di pianificazione</span><span class="sxs-lookup"><span data-stu-id="23429-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="23429-159">Pianificare il progetto pilota di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23429-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
