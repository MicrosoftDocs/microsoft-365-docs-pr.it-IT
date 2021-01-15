---
title: Creare un payload per la formazione di simulazione di attacco
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a creare payload personalizzati per la formazione di simulazione di attacco in Microsoft Defender per Office 365.
ms.openlocfilehash: e3285b99d5b64255b9fdbda8c76b6f133aa013b2
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870864"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="e6fd4-103">Creare un payload personalizzato per la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="e6fd4-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="e6fd4-104">Microsoft offre un robusto catalogo di payload per varie tecniche di social engineering per la combinazione con la formazione di simulazione di attacco.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="e6fd4-105">Tuttavia, potrebbe essere necessario creare payload personalizzati che funzioneranno meglio per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="e6fd4-106">In questo articolo viene descritto come creare un payload nell'esercitazione sulla simulazione di attacco in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e6fd4-107">È possibile creare un payload facendo clic su **Crea un payload** nella [scheda **payload** dedicati](https://security.microsoft.com/attacksimulator?viewid=payload) o nella [procedura guidata](attack-simulation-training.md#selecting-a-payload)per la creazione di una simulazione.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="e6fd4-108">Il primo passaggio della procedura guidata consentirà di selezionare un tipo di payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="e6fd4-109">**Attualmente, solo la posta elettronica è disponibile**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="e6fd4-110">Successivamente, selezionare una tecnica associata.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-110">Next, select an associated technique.</span></span> <span data-ttu-id="e6fd4-111">Per ulteriori informazioni, vedere tecniche per [la scelta di una tecnica di social engineering](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="e6fd4-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="e6fd4-112">Nel passaggio successivo denominare il payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-112">In the next step name your payload.</span></span> <span data-ttu-id="e6fd4-113">Facoltativamente, è possibile assegnargli una descrizione.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="e6fd4-114">Configurare il payload</span><span class="sxs-lookup"><span data-stu-id="e6fd4-114">Configure payload</span></span>

<span data-ttu-id="e6fd4-115">Ora è il momento di creare il payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-115">Now it's time to build your payload.</span></span> <span data-ttu-id="e6fd4-116">Inserire il nome del mittente, l'indirizzo di posta elettronica e l'oggetto del messaggio di posta elettronica nella sezione dei **Dettagli del mittente** .</span><span class="sxs-lookup"><span data-stu-id="e6fd4-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="e6fd4-117">Selezionare un URL di phishing dall'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="e6fd4-118">Questo URL verrà incorporato in un secondo momento nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="e6fd4-119">È possibile scegliere un messaggio di posta elettronica interno per il mittente del payload, che consentirà di visualizzare il payload come proveniente da un altro dipendente della società.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="e6fd4-120">Ciò aumenterà la suscettibilità al payload e contribuirà a istruire i dipendenti sul rischio di minacce interne.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="e6fd4-121">Un editor di testo RTF è disponibile per creare il payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="e6fd4-122">È inoltre possibile importare un messaggio di posta elettronica creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="e6fd4-123">Quando si crea il corpo del messaggio di posta elettronica, utilizzare i **tag dinamici** per personalizzare il messaggio di posta elettronica per i destinatari.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="e6fd4-124">Fare clic su **collegamento di phishing** per aggiungere l'URL di phishing precedentemente selezionato nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Collegamento di phishing e tag dinamici evidenziati nella creazione di payload per Microsoft Defender per Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="e6fd4-126">Per risparmiare tempo, attiva l'opzione per **sostituire tutti i collegamenti del messaggio di posta elettronica con il collegamento di phishing**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="e6fd4-127">Dopo aver completato la creazione del payload a proprio piacimento, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="e6fd4-128">Aggiunta di indicatori</span><span class="sxs-lookup"><span data-stu-id="e6fd4-128">Adding indicators</span></span>

<span data-ttu-id="e6fd4-129">Gli indicatori consentiranno ai dipendenti che passano attraverso la simulazione di attacco di comprendere l'indizio che possono cercare negli attacchi futuri.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="e6fd4-130">Per iniziare, fare clic su **Aggiungi indicatore**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="e6fd4-131">Selezionare un indicatore che si desidera utilizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="e6fd4-132">Questo elenco è curato per contenere gli indizi più comuni che compaiono nei messaggi di posta elettronica di phishing.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="e6fd4-133">Dopo aver selezionato, verificare che la posizione dell'indicatore sia impostata sul **corpo del messaggio di posta elettronica** e fare clic su **Seleziona testo**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="e6fd4-134">Evidenziare la parte del payload in cui viene visualizzato l'indicatore e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Testo evidenziato nel corpo del messaggio da aggiungere a un indicatore nell'esercitazione sulla simulazione di attacco](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="e6fd4-136">Aggiungere una descrizione personalizzata per descrivere l'indicatore e fare clic all'interno della cornice di anteprima dell'indicatore per visualizzare un'anteprima dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="e6fd4-137">Una volta fatto, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-137">Once done, click **Add**.</span></span> <span data-ttu-id="e6fd4-138">Ripetere questi passaggi finché non sono stati descritti tutti gli indicatori nel payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="e6fd4-139">Verifica payload</span><span class="sxs-lookup"><span data-stu-id="e6fd4-139">Review payload</span></span>

<span data-ttu-id="e6fd4-140">La creazione del payload è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-140">You're done building your payload.</span></span> <span data-ttu-id="e6fd4-141">Ora è il momento di esaminare i dettagli e visualizzare un'anteprima del payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="e6fd4-142">L'anteprima includerà tutti gli indicatori che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="e6fd4-143">È possibile modificare ogni parte del payload da questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="e6fd4-144">Una volta soddisfatti, **inviare** il payload.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6fd4-145">I payload creati avranno **tenant** come origine.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="e6fd4-146">Quando si seleziona payload, assicurarsi di non escludere il **tenant**.</span><span class="sxs-lookup"><span data-stu-id="e6fd4-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="e6fd4-147">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="e6fd4-147">Related links</span></span>

[<span data-ttu-id="e6fd4-148">Iniziare a usare la formazione di simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="e6fd4-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="e6fd4-149">Creare una simulazione di attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="e6fd4-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="e6fd4-150">Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="e6fd4-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
