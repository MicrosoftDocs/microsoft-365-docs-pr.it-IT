---
title: Evitare la perdita di dati
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come gestire la configurazione dei criteri di prevenzione della perdita di dati.
ms.openlocfilehash: 04dbbcfd39186b8161fb497b72ddb070fbfb7471
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580439"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="b64a7-103">Prevenire la perdita di dati con DLP</span><span class="sxs-lookup"><span data-stu-id="b64a7-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="b64a7-104">I criteri di prevenzione della perdita dei dati consentono di identificare e proteggere le informazioni riservate dell'azienda, ad esempio i numeri di previdenza sociale o le cartelle cliniche.</span><span class="sxs-lookup"><span data-stu-id="b64a7-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="b64a7-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="b64a7-105">Try it!</span></span>

1. <span data-ttu-id="b64a7-106">Per iniziare, accedere [all'interfaccia di amministrazione](https://admin.microsoft.com)e selezionare **Installazione.**</span><span class="sxs-lookup"><span data-stu-id="b64a7-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="b64a7-107">Scorrere verso il basso **fino a Configurare la prevenzione della perdita di** dati e quindi selezionare **Visualizza** e **quindi Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="b64a7-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="b64a7-108">Per modificare un criterio, selezionarlo, scegliere **Modifica criterio,** quindi selezionare cosa modificare.</span><span class="sxs-lookup"><span data-stu-id="b64a7-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="b64a7-109">Ad esempio, selezionare **Posizioni per** modificare gli elementi analizzati.</span><span class="sxs-lookup"><span data-stu-id="b64a7-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="b64a7-110">Per abilitare l'analisi del contenuto in Microsoft Teams,  attivare l'interruttore attiva e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="b64a7-111">Per modificare le impostazioni dei criteri, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="b64a7-112">Dovrai impostare regole separate che si applicano a piccole e grandi quantità di contenuto sensibile rilevato.</span><span class="sxs-lookup"><span data-stu-id="b64a7-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="b64a7-113">Espandere la regola di volume basso.</span><span class="sxs-lookup"><span data-stu-id="b64a7-113">Expand your low volume rule.</span></span> <span data-ttu-id="b64a7-114">Scegliere **Modifica regola**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="b64a7-115">Rivedere le impostazioni e regolarle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b64a7-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="b64a7-116">Ad esempio, è possibile scegliere di personalizzare **il testo del messaggio di posta elettronica** e personalizzare il testo del **suggerimento per i criteri.**</span><span class="sxs-lookup"><span data-stu-id="b64a7-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="b64a7-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-117">Select **Save**.</span></span>
1. <span data-ttu-id="b64a7-118">Ripetere l'operazione per la regola di volume elevato.</span><span class="sxs-lookup"><span data-stu-id="b64a7-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="b64a7-119">Selezionare **Salva** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="b64a7-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="b64a7-120">Per creare un nuovo criterio, selezionare **Crea un criterio.**</span><span class="sxs-lookup"><span data-stu-id="b64a7-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="b64a7-121">È possibile creare criteri personalizzati o iniziare con un modello.</span><span class="sxs-lookup"><span data-stu-id="b64a7-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="b64a7-122">Ad esempio, per creare un criterio HIPAA, selezionare il modello Medical **and health** e quindi selezionare **U.S. Health Insurance Act (HIPAA)**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="b64a7-123">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-123">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-124">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b64a7-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="b64a7-125">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-125">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-126">Scegliere i percorsi da analizzare.</span><span class="sxs-lookup"><span data-stu-id="b64a7-126">Choose the locations to scan.</span></span> <span data-ttu-id="b64a7-127">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-127">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-128">Scegliere il tipo di contenuto che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="b64a7-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="b64a7-129">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-129">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-130">Scegli cosa vuoi che accada se vengono rilevate informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="b64a7-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="b64a7-131">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-131">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-132">Personalizzare le autorizzazioni di accesso ed eseguire l'override.</span><span class="sxs-lookup"><span data-stu-id="b64a7-132">Customize your access and override permissions.</span></span> <span data-ttu-id="b64a7-133">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-133">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-134">Scegliere quando si desidera che il criterio sia attivo.</span><span class="sxs-lookup"><span data-stu-id="b64a7-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="b64a7-135">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-135">Select **Next**.</span></span>
1. <span data-ttu-id="b64a7-136">Rivedere le impostazioni e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b64a7-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="b64a7-137">Dopo l'applicazione dei criteri, i messaggi di posta elettronica che contengono le informazioni riservate descritte verranno bloccati e il mittente che ha tentato di inviare le informazioni verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="b64a7-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>