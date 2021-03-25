---
title: Creare un payload per il training della simulazione di attacco
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a creare payload personalizzati per la formazione sulla simulazione di attacchi in Microsoft Defender per Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205194"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="36fc7-103">Creare un payload personalizzato per la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="36fc7-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="36fc7-104">Microsoft offre un solido catalogo di payload per varie tecniche di social engineering da associare alla formazione di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="36fc7-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="36fc7-105">Tuttavia, potresti voler creare payload personalizzati che funzionino meglio per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36fc7-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="36fc7-106">Questo articolo descrive come creare un payload nel training di simulazione degli attacchi in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="36fc7-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="36fc7-107">Puoi creare un payload facendo clic su **Crea un payload** nella scheda Payload [ **dedicati**](https://security.microsoft.com/attacksimulator?viewid=payload) o nella procedura guidata di creazione [della simulazione.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="36fc7-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="36fc7-108">Nel primo passaggio della procedura guidata verrà selezionato un tipo di payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="36fc7-109">**Attualmente, è disponibile solo la posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="36fc7-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="36fc7-110">Selezionare quindi una tecnica associata.</span><span class="sxs-lookup"><span data-stu-id="36fc7-110">Next, select an associated technique.</span></span> <span data-ttu-id="36fc7-111">Per ulteriori dettagli sulle tecniche, vedere [Selezione di una tecnica di social engineering.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="36fc7-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="36fc7-112">Nel passaggio successivo assegnare un nome al payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-112">In the next step name your payload.</span></span> <span data-ttu-id="36fc7-113">Facoltativamente, è possibile fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="36fc7-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="36fc7-114">Configurare il payload</span><span class="sxs-lookup"><span data-stu-id="36fc7-114">Configure payload</span></span>

<span data-ttu-id="36fc7-115">Ora è il momento di creare il payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-115">Now it's time to build your payload.</span></span> <span data-ttu-id="36fc7-116">Immettere il nome del mittente, l'indirizzo di posta elettronica e l'oggetto del messaggio nella **sezione Dettagli mittente.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="36fc7-117">Selezionare un URL di phishing nell'elenco fornito.</span><span class="sxs-lookup"><span data-stu-id="36fc7-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="36fc7-118">Questo URL verrà successivamente incorporato nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="36fc7-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="36fc7-119">Puoi scegliere un messaggio di posta elettronica interno per il mittente del payload, in modo che il payload venga visualizzato come proveniente da un altro dipendente dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="36fc7-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="36fc7-120">Ciò aumenterà la suscettibilità al payload e aiuterà a informare i dipendenti sul rischio di minacce interne.</span><span class="sxs-lookup"><span data-stu-id="36fc7-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="36fc7-121">È disponibile un editor di testo RTF per creare il payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="36fc7-122">È inoltre possibile importare un messaggio di posta elettronica creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="36fc7-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="36fc7-123">Quando crei il corpo del messaggio di posta elettronica, sfrutta i **tag dinamici** per personalizzare il messaggio di posta elettronica in base alle tue destinazioni.</span><span class="sxs-lookup"><span data-stu-id="36fc7-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="36fc7-124">Fare **clic sul collegamento Phishing** per aggiungere l'URL di phishing selezionato in precedenza nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="36fc7-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Collegamento di phishing e tag dinamici evidenziati nella creazione di payload per Microsoft Defender per Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="36fc7-126">Per risparmiare tempo, attivare l'opzione per sostituire tutti i collegamenti nel **messaggio di posta elettronica con il collegamento di phishing.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="36fc7-127">Dopo aver finito di creare il payload a proprio piacimento, fai clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="36fc7-128">Aggiunta di indicatori</span><span class="sxs-lookup"><span data-stu-id="36fc7-128">Adding indicators</span></span>

<span data-ttu-id="36fc7-129">Gli indicatori aiuteranno i dipendenti a passare attraverso la simulazione di attacco a comprendere l'indizio che possono cercare negli attacchi futuri.</span><span class="sxs-lookup"><span data-stu-id="36fc7-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="36fc7-130">Per iniziare, fare clic **su Aggiungi indicatore.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="36fc7-131">Selezionare un indicatore che si desidera utilizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="36fc7-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="36fc7-132">Questo elenco è curato per contenere gli indizi più comuni che vengono visualizzati nei messaggi di posta elettronica di phishing.</span><span class="sxs-lookup"><span data-stu-id="36fc7-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="36fc7-133">Una volta selezionato, assicurati che il posizionamento dell'indicatore sia impostato su **Dal corpo del** messaggio di posta elettronica e fai clic su Seleziona **testo.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="36fc7-134">Evidenzia la parte del payload in cui viene visualizzato l'indicatore e fai clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="36fc7-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Testo evidenziato nel corpo del messaggio da aggiungere a un indicatore nel training della simulazione di attacco](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="36fc7-136">Aggiungi una descrizione personalizzata per descrivere l'indicatore e fai clic all'interno del fotogramma di anteprima dell'indicatore per visualizzare un'anteprima dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="36fc7-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="36fc7-137">Al termine, fare clic **su Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="36fc7-137">Once done, click **Add**.</span></span> <span data-ttu-id="36fc7-138">Ripeti questi passaggi finché non hai coperto tutti gli indicatori nel payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="36fc7-139">Esaminare il payload</span><span class="sxs-lookup"><span data-stu-id="36fc7-139">Review payload</span></span>

<span data-ttu-id="36fc7-140">Hai finito di creare il payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-140">You're done building your payload.</span></span> <span data-ttu-id="36fc7-141">Ora è il momento di esaminare i dettagli e visualizzare un'anteprima del payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="36fc7-142">L'anteprima includerà tutti gli indicatori creati.</span><span class="sxs-lookup"><span data-stu-id="36fc7-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="36fc7-143">Puoi modificare ogni parte del payload da questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="36fc7-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="36fc7-144">Una volta soddisfatto, puoi **inviare il** payload.</span><span class="sxs-lookup"><span data-stu-id="36fc7-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36fc7-145">I payload creati avranno **Tenant** come origine.</span><span class="sxs-lookup"><span data-stu-id="36fc7-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="36fc7-146">Quando si selezionano payload, assicurarsi di non filtrare **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="36fc7-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="36fc7-147">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="36fc7-147">Related links</span></span>

[<span data-ttu-id="36fc7-148">Introduzione alla formazione sull’uso di Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="36fc7-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="36fc7-149">Creare una simulazione di attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="36fc7-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="36fc7-150">Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="36fc7-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
