---
title: Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono scoprire come la formazione di simulazione di attacco nel centro sicurezza di Microsoft 365 influisce sui dipendenti e può ottenere informazioni dettagliate sulla simulazione e sulla formazione dei risultati.
ms.openlocfilehash: c283819550872691d8dd23d3921c22cb23637633
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870956"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="74e09-103">Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="74e09-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="74e09-104">All'interno della formazione sulla simulazione degli attacchi, Microsoft fornisce informazioni basate sui risultati delle simulazioni e degli allenamenti che i dipendenti hanno attraversato.</span><span class="sxs-lookup"><span data-stu-id="74e09-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="74e09-105">Queste informazioni consentono di tenere informati sul progresso della prontezza delle minacce dei dipendenti, nonché di consigliare i passaggi successivi per preparare meglio i dipendenti e l'ambiente per gli attacchi.</span><span class="sxs-lookup"><span data-stu-id="74e09-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="74e09-106">Stiamo lavorando continuamente per espandere le intuizioni che sono disponibili per l'utente.</span><span class="sxs-lookup"><span data-stu-id="74e09-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="74e09-107">L'impatto sul comportamento e le azioni consigliate sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="74e09-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="74e09-108">Per iniziare, passare a [Attack Simulation Training in Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="74e09-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="74e09-109">Impatto del comportamento sulla velocità di compromesso</span><span class="sxs-lookup"><span data-stu-id="74e09-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="74e09-110">Nella scheda **Panoramica** della formazione sulla simulazione di attacco, è possibile trovare l' **impatto sul comportamento sulla** scheda della velocità di compromesso.</span><span class="sxs-lookup"><span data-stu-id="74e09-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="74e09-111">Questa scheda illustra come i dipendenti hanno affrontato le simulazioni che sono state eseguiti in contrasto con il **tasso di compromesso previsto**.</span><span class="sxs-lookup"><span data-stu-id="74e09-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="74e09-112">È possibile utilizzare queste informazioni per monitorare lo stato di avanzamento della preparazione delle minacce dei dipendenti eseguendo più simulazioni sugli stessi gruppi di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="74e09-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="74e09-113">Nel grafico è possibile vedere:</span><span class="sxs-lookup"><span data-stu-id="74e09-113">In the graph you can see:</span></span>

- <span data-ttu-id="74e09-114">**Tasso di compromesso previsto** che riflette il tasso medio di compromesso per le simulazioni che utilizzano lo stesso tipo di payload tra gli altri tenant di Microsoft 365 che utilizzano la formazione di simulazione di attacco.</span><span class="sxs-lookup"><span data-stu-id="74e09-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="74e09-115">Il **tasso di compromesso effettivo** riflette la percentuale di dipendenti che sono caduti per la simulazione.</span><span class="sxs-lookup"><span data-stu-id="74e09-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="74e09-116">Inoltre, `<number> less susceptible to phishing` riflette la differenza tra il numero effettivo di dipendenti compromessi dall'attacco e il tasso di compromesso previsto.</span><span class="sxs-lookup"><span data-stu-id="74e09-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="74e09-117">Questo numero di dipendenti ha meno probabilità di essere compromesso da attacchi simili in futuro, mentre `<percent%> better than predicted rate` indica la modalità complessiva dei dipendenti in contrasto con il tasso di compromesso previsto.</span><span class="sxs-lookup"><span data-stu-id="74e09-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="74e09-118">![Scheda impatto sulla simulazione dell'addestramento di attacco](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="74e09-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="74e09-119">Per visualizzare un report più dettagliato, fare clic su **Visualizza simulazioni e report sull'efficacia del training**.</span><span class="sxs-lookup"><span data-stu-id="74e09-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="74e09-120">Questo rapporto fornisce le stesse informazioni con un contesto aggiuntivo dalla simulazione stessa (ad esempio, tecnica di simulazione e totale degli utenti mirati).</span><span class="sxs-lookup"><span data-stu-id="74e09-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="74e09-121">Azioni consigliate</span><span class="sxs-lookup"><span data-stu-id="74e09-121">Recommended actions</span></span>

<span data-ttu-id="74e09-122">Nella scheda [ **simulazioni**](https://security.microsoft.com/attacksimulator?viewid=simulations)Selezionare una simulazione vi consentirà di visualizzare i dettagli della simulazione, in cui è disponibile la sezione **azioni consigliate** .</span><span class="sxs-lookup"><span data-stu-id="74e09-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="74e09-123">La sezione azioni consigliate descrive in dettaglio i suggerimenti disponibili in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="74e09-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="74e09-124">Questi suggerimenti si basano sul payload utilizzato nella simulazione e consentono di proteggere i dipendenti e il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="74e09-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="74e09-125">Facendo clic su ogni azione di miglioramento, vengono illustrati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="74e09-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="74e09-126">![Sezione azioni consigliate sulla formazione sulla simulazione di attacco](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="74e09-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="74e09-127">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="74e09-127">Related Links</span></span>

[<span data-ttu-id="74e09-128">Iniziare a usare la formazione di simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="74e09-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="74e09-129">Creare una simulazione di attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="74e09-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="74e09-130">creare un payload per la formazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="74e09-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
