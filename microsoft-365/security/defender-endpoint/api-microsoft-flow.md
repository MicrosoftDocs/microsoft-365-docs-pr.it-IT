---
title: Microsoft Defender for Endpoint Flow connector
ms.reviewer: ''
description: Usa Microsoft Defender for Endpoint Flow connector per automatizzare la sicurezza e creare un flusso che verrà attivato ogni volta che si verifica un nuovo avviso nel tenant.
keywords: flusso, api supportate, api, flusso Microsoft, query, automazione
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769705"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="3ce67-104">Microsoft Power Automate (in precedenza Microsoft Flow) e Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="3ce67-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ce67-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3ce67-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ce67-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3ce67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ce67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ce67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="3ce67-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3ce67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ce67-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3ce67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="3ce67-110">L'automazione delle procedure di sicurezza è un requisito standard per ogni centro operativo di sicurezza moderno.</span><span class="sxs-lookup"><span data-stu-id="3ce67-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="3ce67-111">La mancanza di cyber defender professionali obbliga SOC a lavorare nel modo più efficiente e l'automazione è un must.</span><span class="sxs-lookup"><span data-stu-id="3ce67-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="3ce67-112">Microsoft Power Automate supporta connettori diversi che sono stati creati esattamente per questo.</span><span class="sxs-lookup"><span data-stu-id="3ce67-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="3ce67-113">È possibile creare un'automazione di routine end-to-end entro pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="3ce67-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="3ce67-114">Microsoft Defender API ha un connettore Flow con molte funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3ce67-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Immagine delle credenziali di modifica1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="3ce67-116">Per ulteriori informazioni sui prerequisiti di licenza per i connettori premium, vedere [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="3ce67-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="3ce67-117">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="3ce67-117">Usage example</span></span>

<span data-ttu-id="3ce67-118">L'esempio seguente illustra come creare un Flow che viene attivato ogni volta che si verifica un nuovo avviso nel tenant.</span><span class="sxs-lookup"><span data-stu-id="3ce67-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="3ce67-119">Accedere a [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3ce67-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="3ce67-120">Vai a **Flussi my**  >  **New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="3ce67-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Immagine delle credenziali di modifica2](images/api-flow-1.png)

3. <span data-ttu-id="3ce67-122">Scegli un nome per il Flow, cerca "Trigger Microsoft Defender ATP" come trigger e quindi seleziona il nuovo trigger Avvisi.</span><span class="sxs-lookup"><span data-stu-id="3ce67-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Immagine delle credenziali di modifica3](images/api-flow-2.png)

<span data-ttu-id="3ce67-124">Ora si dispone di Flow che viene attivato ogni volta che si verifica un nuovo avviso.</span><span class="sxs-lookup"><span data-stu-id="3ce67-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Immagine delle credenziali di modifica4](images/api-flow-3.png)

<span data-ttu-id="3ce67-126">Tutto quello che devi fare ora è scegliere i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="3ce67-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="3ce67-127">Ad esempio, puoi isolare il dispositivo se la gravità dell'avviso è Alta e inviare un messaggio di posta elettronica al riguardo.</span><span class="sxs-lookup"><span data-stu-id="3ce67-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="3ce67-128">Il trigger Avviso fornisce solo l'ID avviso e l'ID computer.</span><span class="sxs-lookup"><span data-stu-id="3ce67-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="3ce67-129">È possibile utilizzare il connettore per espandere queste entità.</span><span class="sxs-lookup"><span data-stu-id="3ce67-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="3ce67-130">Ottenere l'entità Alert usando il connettore</span><span class="sxs-lookup"><span data-stu-id="3ce67-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="3ce67-131">Scegliere **Microsoft Defender ATP** per il nuovo passaggio.</span><span class="sxs-lookup"><span data-stu-id="3ce67-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="3ce67-132">Scegliere **Avvisi - Api per il singolo avviso.**</span><span class="sxs-lookup"><span data-stu-id="3ce67-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="3ce67-133">Imposta **l'ID avviso** dell'ultimo passaggio come **Input**.</span><span class="sxs-lookup"><span data-stu-id="3ce67-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Immagine delle credenziali di modifica5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="3ce67-135">Isolare il dispositivo se la gravità dell'avviso è Alta</span><span class="sxs-lookup"><span data-stu-id="3ce67-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="3ce67-136">Aggiungi **condizione** come nuovo passaggio.</span><span class="sxs-lookup"><span data-stu-id="3ce67-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="3ce67-137">Verificare se la gravità **dell'avviso è uguale a** Alta.</span><span class="sxs-lookup"><span data-stu-id="3ce67-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="3ce67-138">Se sì, aggiungi **l'azione Microsoft Defender ATP - Isolare il** computer con l'ID computer e un commento.</span><span class="sxs-lookup"><span data-stu-id="3ce67-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Immagine delle credenziali di modifica6](images/api-flow-5.png)

3. <span data-ttu-id="3ce67-140">Aggiungi un nuovo passaggio per l'invio tramite posta elettronica dell'avviso e dell'isolamento.</span><span class="sxs-lookup"><span data-stu-id="3ce67-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="3ce67-141">Esistono più connettori di posta elettronica molto facili da usare, ad esempio Outlook o Gmail.</span><span class="sxs-lookup"><span data-stu-id="3ce67-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="3ce67-142">Salvare il flusso.</span><span class="sxs-lookup"><span data-stu-id="3ce67-142">Save your flow.</span></span>

<span data-ttu-id="3ce67-143">È inoltre possibile creare un **flusso pianificato** che esegue query di ricerca avanzata e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="3ce67-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="3ce67-144">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="3ce67-144">Related topic</span></span>
- [<span data-ttu-id="3ce67-145">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3ce67-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
