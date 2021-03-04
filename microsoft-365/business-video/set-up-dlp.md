---
title: Evitare la perdita di dati
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come gestire la configurazione dei criteri di prevenzione della perdita dei dati.
ms.openlocfilehash: 54cd508ef0b0cfcf8b71dc86a4903f77a5354c36
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422064"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="0c7b6-103">Prevenire la perdita di dati con DLP</span><span class="sxs-lookup"><span data-stu-id="0c7b6-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="0c7b6-104">I criteri di prevenzione della perdita dei dati consentono di identificare e proteggere le informazioni riservate dell'azienda, ad esempio i numeri di previdenza sociale o le cartelle cliniche.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="0c7b6-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="0c7b6-105">Try it!</span></span>

1. <span data-ttu-id="0c7b6-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="0c7b6-107">Scorrere verso il basso **fino a Configurare la prevenzione della** perdita dei dati, quindi selezionare **Visualizza** e **quindi Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="0c7b6-108">Per modificare un criterio, selezionarlo, scegliere **Modifica criterio,** quindi selezionare gli elementi da modificare.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="0c7b6-109">Ad esempio, selezionare **Posizioni per** modificare gli elementi analizzati.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="0c7b6-110">Per abilitare l'analisi del contenuto in Microsoft  Teams, attivare l'interruttore Attiva e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="0c7b6-111">Per modificare le impostazioni dei criteri, selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="0c7b6-112">Dovrai impostare regole separate che si applicano a piccole e grandi quantità di contenuti sensibili rilevati.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="0c7b6-113">Espandere la regola con volume ridotto.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-113">Expand your low volume rule.</span></span> <span data-ttu-id="0c7b6-114">Scegliere **Modifica regola.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="0c7b6-115">Rivedere le impostazioni e regolarle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="0c7b6-116">Ad esempio, è possibile scegliere di personalizzare il **testo del messaggio di posta elettronica** e il testo del **suggerimento per il criterio.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="0c7b6-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-117">Select **Save**.</span></span>
1. <span data-ttu-id="0c7b6-118">Ripetere l'operazione per la regola di volume elevato.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="0c7b6-119">Selezionare **Salva** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="0c7b6-120">Per creare un nuovo criterio, selezionare **Crea un criterio.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="0c7b6-121">È possibile creare un criterio personalizzato o iniziare con un modello.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="0c7b6-122">Ad esempio, per creare un criterio HIPAA, selezionare il modello Medical **and health** e quindi selezionare **U.S. Health Insurance Act (HIPAA)**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="0c7b6-123">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-123">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-124">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="0c7b6-125">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-125">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-126">Scegliere i percorsi da analizzare.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-126">Choose the locations to scan.</span></span> <span data-ttu-id="0c7b6-127">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-127">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-128">Scegliere il tipo di contenuto che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="0c7b6-129">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-129">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-130">Scegli cosa vuoi che accada se vengono rilevate informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="0c7b6-131">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-131">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-132">Personalizzare le autorizzazioni di accesso e override.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-132">Customize your access and override permissions.</span></span> <span data-ttu-id="0c7b6-133">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-133">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-134">Scegliere quando si desidera che il criterio sia attivo.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="0c7b6-135">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-135">Select **Next**.</span></span>
1. <span data-ttu-id="0c7b6-136">Rivedere le impostazioni e selezionare **Crea.**</span><span class="sxs-lookup"><span data-stu-id="0c7b6-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="0c7b6-137">Dopo l'applicazione dei criteri, i messaggi di posta elettronica che contengono le informazioni riservate descritte verranno bloccati e il mittente che ha tentato di inviare queste informazioni verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="0c7b6-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>