---
title: Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Informazioni su come l'allenamento di simulazione degli attacchi in Microsoft 365 Security Center influisce sui dipendenti e acquisisce informazioni sui risultati di simulazione e formazione.
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615181"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="0550e-103">Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="0550e-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="0550e-104">All'interno della formazione sulla simulazione degli attacchi, Microsoft fornisce informazioni basate sui risultati di simulazioni e i dipendenti della formazione hanno attraversato.</span><span class="sxs-lookup"><span data-stu-id="0550e-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="0550e-105">Queste informazioni consentiranno di informarti sul progresso che i dipendenti stanno facendo sulla preparazione delle minacce, nonché di consigliare i passaggi successivi per preparare meglio i dipendenti e l'ambiente per gli attacchi.</span><span class="sxs-lookup"><span data-stu-id="0550e-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0550e-106">Stiamo lavorando continuamente su come espandere approfondimenti disponibili, con un impatto comportamentale e le azioni consigliate attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="0550e-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="0550e-107">Per iniziare, passare a [Attack Simulation Training on the Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="0550e-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="0550e-108">Impatto del comportamento sulla velocità di compromesso</span><span class="sxs-lookup"><span data-stu-id="0550e-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="0550e-109">Nella scheda **Panoramica** sulla formazione di attacchi di simulazione, è possibile trovare l' **impatto sul comportamento sulla scheda velocità di compromesso** .</span><span class="sxs-lookup"><span data-stu-id="0550e-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="0550e-110">Questa scheda illustra come i dipendenti hanno affrontato la simulazione che è stata eseguita in contrasto con il **tasso di compromesso previsto**.</span><span class="sxs-lookup"><span data-stu-id="0550e-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="0550e-111">È possibile utilizzare queste informazioni per monitorare lo stato di avanzamento della preparazione delle minacce dei dipendenti eseguendo più simulazioni sugli stessi gruppi di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0550e-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="0550e-112">Nel grafico è possibile vedere:</span><span class="sxs-lookup"><span data-stu-id="0550e-112">In the graph you can see:</span></span>

- <span data-ttu-id="0550e-113">**Tasso di compromesso previsto** che riflette il tasso medio di compromesso per le simulazioni usando lo stesso tipo di payload tra i tenant usando la formazione sulla simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="0550e-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="0550e-114">Il **tasso di compromesso effettivo** riflette la percentuale di dipendenti che sono caduti per la simulazione.</span><span class="sxs-lookup"><span data-stu-id="0550e-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="0550e-115">Inoltre, `<number> less susceptible to phishing` riflette la differenza tra il numero effettivo di dipendenti compromessi dall'attacco e il tasso di compromesso previsto.</span><span class="sxs-lookup"><span data-stu-id="0550e-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="0550e-116">Questo numero di dipendenti ha meno probabilità di essere compromesso da attacchi simili in futuro, mentre `<percent%> better than predicted rate` indica la modalità complessiva dei dipendenti in contrasto con il tasso di compromesso previsto.</span><span class="sxs-lookup"><span data-stu-id="0550e-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0550e-117">![Scheda impatto sulla simulazione dell'addestramento di attacco](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="0550e-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="0550e-118">Per visualizzare un report più dettagliato, fare clic su **Visualizza simulazioni e report sull'efficacia della formazione** che fornisce le stesse informazioni con un contesto aggiuntivo dalla simulazione stessa, come la tecnica di simulazione e gli utenti totali mirati.</span><span class="sxs-lookup"><span data-stu-id="0550e-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="0550e-119">Azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="0550e-119">Recommended actions</span></span>

<span data-ttu-id="0550e-120">Nella scheda [ **simulazioni**](https://security.microsoft.com/attacksimulator?viewid=simulations), selezionando una qualsiasi delle simulazioni, vengono illustrati i dettagli della simulazione.</span><span class="sxs-lookup"><span data-stu-id="0550e-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="0550e-121">Qui è disponibile la sezione **azioni consigliate** .</span><span class="sxs-lookup"><span data-stu-id="0550e-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="0550e-122">La sezione azioni consigliate descrive in dettaglio i suggerimenti disponibili in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="0550e-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="0550e-123">Questi suggerimenti si basano sul payload utilizzato nella simulazione e consentono di proteggere i dipendenti e il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="0550e-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="0550e-124">Facendo clic su ogni azione di miglioramento, vengono illustrati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="0550e-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0550e-125">![Sezione azioni consigliate sulla formazione sulla simulazione di attacco](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0550e-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="0550e-126">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="0550e-126">Related Links</span></span>

<span data-ttu-id="0550e-127">**Attacco simulatore** [creare una simulazione di attacco di phishing](attack-simulation-training.md) e [creare un payload per la formazione degli utenti](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="0550e-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
