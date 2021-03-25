---
title: Controllare l'integrità del servizio Microsoft Defender ATP
description: Controllare l'integrità del servizio Microsoft Defender ATP, verificare se si sono verificati problemi nel servizio ed esaminare i problemi precedenti che sono stati risolti.
keywords: dashboard, servizio, problemi, integrità del servizio, stato corrente, cronologia dello stato, riepilogo dell'impatto, causa radice preliminare, risoluzione, tempo di risoluzione, tempo di risoluzione previsto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 45782fcce51e15adf61757d836d313d229558571
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064877"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="cfe99-104">Controllare l'integrità del servizio endpoint in Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cfe99-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cfe99-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cfe99-105">**Applies to:**</span></span>
- [<span data-ttu-id="cfe99-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cfe99-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="cfe99-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cfe99-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cfe99-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cfe99-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="cfe99-109">**L'integrità** del servizio fornisce informazioni sullo stato corrente del servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="cfe99-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="cfe99-110">Sarà possibile verificare che l'integrità del servizio sia integra o se sono presenti problemi correnti.</span><span class="sxs-lookup"><span data-stu-id="cfe99-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="cfe99-111">In caso di problemi, verranno visualizzate informazioni quali il momento in cui è stato rilevato il problema, la causa principale preliminare e il tempo di risoluzione previsto.</span><span class="sxs-lookup"><span data-stu-id="cfe99-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="cfe99-112">Verranno inoltre visualizzate informazioni sui problemi cronologici risolti e dettagli quali la data e l'ora in cui il problema è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="cfe99-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="cfe99-113">Quando non si verificano problemi nel servizio, verrà visualizzato uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="cfe99-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="cfe99-114">È possibile visualizzare i dettagli sull'integrità del servizio facendo clic sul riquadro nel **dashboard** Operazioni di sicurezza o selezionando il menu **Integrità servizio** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="cfe99-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="cfe99-115">Nella **pagina Dettagli integrità** servizio sono disponibili le schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfe99-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="cfe99-116">**Stato corrente**</span><span class="sxs-lookup"><span data-stu-id="cfe99-116">**Current status**</span></span>
- <span data-ttu-id="cfe99-117">**Cronologia stato**</span><span class="sxs-lookup"><span data-stu-id="cfe99-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="cfe99-118">Stato corrente</span><span class="sxs-lookup"><span data-stu-id="cfe99-118">Current status</span></span>
<span data-ttu-id="cfe99-119">La **scheda Stato** corrente mostra lo stato corrente del servizio Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="cfe99-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="cfe99-120">Quando il servizio viene eseguito senza problemi, viene visualizzata un'integrità del servizio integra.</span><span class="sxs-lookup"><span data-stu-id="cfe99-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="cfe99-121">In caso di problemi, vengono mostrati i dettagli del servizio seguenti per ottenere informazioni più approfondite sul problema:</span><span class="sxs-lookup"><span data-stu-id="cfe99-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="cfe99-122">Data e ora in cui è stato rilevato il problema</span><span class="sxs-lookup"><span data-stu-id="cfe99-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="cfe99-123">Breve descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="cfe99-123">A short description of the issue</span></span>
- <span data-ttu-id="cfe99-124">Ora aggiornamento</span><span class="sxs-lookup"><span data-stu-id="cfe99-124">Update time</span></span>
- <span data-ttu-id="cfe99-125">Riepilogo dell'impatto</span><span class="sxs-lookup"><span data-stu-id="cfe99-125">Summary of impact</span></span>
- <span data-ttu-id="cfe99-126">Causa radice preliminare</span><span class="sxs-lookup"><span data-stu-id="cfe99-126">Preliminary root cause</span></span>
- <span data-ttu-id="cfe99-127">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cfe99-127">Next steps</span></span>
- <span data-ttu-id="cfe99-128">Tempo di risoluzione previsto</span><span class="sxs-lookup"><span data-stu-id="cfe99-128">Expected resolution time</span></span>

<span data-ttu-id="cfe99-129">Gli aggiornamenti sullo stato di avanzamento di un problema vengono visualizzati nella pagina quando il problema viene risolto.</span><span class="sxs-lookup"><span data-stu-id="cfe99-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="cfe99-130">Verranno visualizzati aggiornamenti sulle informazioni, ad esempio il tempo di risoluzione della stima aggiornato o i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="cfe99-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="cfe99-131">Quando un problema viene risolto, viene registrato nella **scheda Cronologia** stato.</span><span class="sxs-lookup"><span data-stu-id="cfe99-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="cfe99-132">Cronologia stato</span><span class="sxs-lookup"><span data-stu-id="cfe99-132">Status history</span></span>
<span data-ttu-id="cfe99-133">La **scheda Cronologia** stato riflette tutti i problemi cronologici che sono stati visti e risolti.</span><span class="sxs-lookup"><span data-stu-id="cfe99-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="cfe99-134">Verranno visualizzati i dettagli dei problemi risolti insieme alle altre informazioni incluse durante la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="cfe99-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="cfe99-135">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="cfe99-135">Related topic</span></span>
- [<span data-ttu-id="cfe99-136">Visualizzare il dashboard delle operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cfe99-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
