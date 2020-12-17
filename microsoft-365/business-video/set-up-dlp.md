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
ROBOTS: NOINDEX, NOFOLLOW
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
description: Informazioni su come gestire i criteri di prevenzione della perdita dei dati.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702907"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="ad1ba-103">Prevenire la perdita di dati con DLP</span><span class="sxs-lookup"><span data-stu-id="ad1ba-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="ad1ba-104">I criteri di prevenzione della perdita di dati consentono di identificare e proteggere le informazioni riservate dell'azienda, come i numeri di previdenza sociale o i record medici.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="ad1ba-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="ad1ba-105">Try it!</span></span>

1. <span data-ttu-id="ad1ba-106">Per iniziare, passare all'interfaccia di [Amministrazione](https://admin.microsoft.com)e selezionare **Setup**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="ad1ba-107">Scorrere verso il basso per **impostare la prevenzione della perdita di dati**, quindi selezionare **Visualizza** e quindi **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="ad1ba-108">Per modificare un criterio, selezionarlo, scegliere **modifica criterio** e quindi selezionare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="ad1ba-109">Ad esempio, selezionare **percorsi** per modificare ciò che viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="ad1ba-110">Per abilitare l'analisi del contenuto in Microsoft teams, impostare l'interruttore toggle **sulla posizione attivata** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="ad1ba-111">Per modificare le impostazioni del criterio, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="ad1ba-112">Sarà necessario impostare regole distinte che si applicano a piccole e grandi quantità di contenuto sensibile rilevate.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="ad1ba-113">Espandi la regola del volume basso.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-113">Expand your low volume rule.</span></span> <span data-ttu-id="ad1ba-114">Scegliere **Modifica regola**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="ad1ba-115">Rivedere le impostazioni e modificarle in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="ad1ba-116">Ad esempio, è possibile scegliere di **personalizzare il testo del messaggio di posta elettronica** e **personalizzare il testo del suggerimento per i criteri**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="ad1ba-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-117">Select **Save**.</span></span>
1. <span data-ttu-id="ad1ba-118">Ripetere la regola per il volume alto.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="ad1ba-119">Selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="ad1ba-120">Per creare un nuovo criterio, selezionare **Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="ad1ba-121">È possibile creare un criterio personalizzato o iniziare con un modello.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="ad1ba-122">Ad esempio, per creare un criterio HIPAA, selezionare il modello di **integrità e medicale** , quindi selezionare **U.S. Health Insurance Act (HIPAA)**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="ad1ba-123">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-123">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-124">Immettere un nome e una descrizione per i criteri.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="ad1ba-125">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-125">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-126">Scegliere le posizioni da analizzare.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-126">Choose the locations to scan.</span></span> <span data-ttu-id="ad1ba-127">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-127">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-128">Scegliere il tipo di contenuto che si desidera proteggere.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="ad1ba-129">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-129">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-130">Scegliere ciò che si desidera verificare se vengono rilevate informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="ad1ba-131">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-131">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-132">Personalizzare le autorizzazioni di accesso e di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-132">Customize your access and override permissions.</span></span> <span data-ttu-id="ad1ba-133">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-133">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-134">Scegliere quando si desidera che il criterio abbia effetto.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="ad1ba-135">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-135">Select **Next**.</span></span>
1. <span data-ttu-id="ad1ba-136">Rivedere le impostazioni e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="ad1ba-137">Dopo che il criterio è stato applicato, la posta elettronica contenente le informazioni riservate descritte verrà bloccata e il mittente che ha tentato di inviare tali informazioni visualizzerà un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="ad1ba-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>