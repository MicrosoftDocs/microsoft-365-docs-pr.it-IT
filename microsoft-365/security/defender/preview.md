---
title: Funzionalità di anteprima in Microsoft 365 Defender
description: Ulteriori informazioni sulle nuove funzionalità nella Sicurezza Microsoft 365
keywords: anteprima, novità, sicurezza m365, sicurezza, 365, funzionalità
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430817"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="7ce29-104">Microsoft 365 Defender funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="7ce29-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7ce29-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7ce29-105">**Applies to:**</span></span>
- <span data-ttu-id="7ce29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ce29-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ce29-107">Il Microsoft 365 Defender viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7ce29-107">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="7ce29-108">Informazioni sulle nuove funzionalità nella versione Microsoft 365 Defender anteprima ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.</span><span class="sxs-lookup"><span data-stu-id="7ce29-108">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="7ce29-109">Per ulteriori informazioni sulle nuove funzionalità disponibili in genere, vedere [Novità di Microsoft 365 Defender](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="7ce29-109">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="7ce29-110">Cosa è necessario sapere</span><span class="sxs-lookup"><span data-stu-id="7ce29-110">What you need to know</span></span>

<span data-ttu-id="7ce29-111">Quando si lavora con le funzionalità in anteprima pubblica, queste funzionalità:</span><span class="sxs-lookup"><span data-stu-id="7ce29-111">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="7ce29-112">Può avere funzionalità limitate o limitate.</span><span class="sxs-lookup"><span data-stu-id="7ce29-112">May have restricted or limited functionality.</span></span> <span data-ttu-id="7ce29-113">Ad esempio, la funzionalità può essere applicata solo a una piattaforma.</span><span class="sxs-lookup"><span data-stu-id="7ce29-113">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="7ce29-114">In genere, le modifiche delle funzionalità vengono apportate prima che siano disponibili in genere.</span><span class="sxs-lookup"><span data-stu-id="7ce29-114">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="7ce29-115">Sono completamente supportati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ce29-115">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="7ce29-116">Può essere disponibile solo in aree geografiche o ambienti cloud selezionati.</span><span class="sxs-lookup"><span data-stu-id="7ce29-116">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="7ce29-117">Ad esempio, la funzionalità potrebbe non esistere nel cloud per enti pubblici.</span><span class="sxs-lookup"><span data-stu-id="7ce29-117">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="7ce29-118">Le singole funzionalità in anteprima possono avere più restrizioni di utilizzo e supporto.</span><span class="sxs-lookup"><span data-stu-id="7ce29-118">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="7ce29-119">In tal caso, queste informazioni vengono in genere riportate nella documentazione relativa alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7ce29-119">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="7ce29-120">Le versioni di anteprima sono fornite con un livello di supporto standard e possono essere utilizzate per gli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="7ce29-120">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="required-permissions"></a><span data-ttu-id="7ce29-121">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="7ce29-121">Required permissions</span></span>

<span data-ttu-id="7ce29-122">Gli account assegnati ai ruoli Azure Active Directory (Azure AD) seguenti possono attivare le funzionalità Microsoft 365 Defender Preview:</span><span class="sxs-lookup"><span data-stu-id="7ce29-122">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="7ce29-123">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="7ce29-123">Global administrator</span></span>
- <span data-ttu-id="7ce29-124">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7ce29-124">Security administrator</span></span>
- <span data-ttu-id="7ce29-125">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7ce29-125">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="7ce29-126">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="7ce29-126">Turn on preview features</span></span>

<span data-ttu-id="7ce29-127">Avrai accesso alle funzionalità future su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="7ce29-127">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="7ce29-128">Attivare l'opzione esperienza di anteprima per essere tra i primi a provare le funzionalità che saranno introdotte.</span><span class="sxs-lookup"><span data-stu-id="7ce29-128">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="7ce29-129">Nel riquadro di spostamento selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="7ce29-129">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="7ce29-130">Selezionare **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="7ce29-130">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="7ce29-131">Selezionare **Funzionalità di anteprima** > **Attivare le funzionalità di anteprima**.</span><span class="sxs-lookup"><span data-stu-id="7ce29-131">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="7ce29-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7ce29-132">Select **Save**.</span></span>

<span data-ttu-id="7ce29-133">Se la casella di controllo **Attivare le funzionalità di anteprima** è selezionata, significa che le funzionalità di anteprima sono attivate.</span><span class="sxs-lookup"><span data-stu-id="7ce29-133">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="7ce29-134">Funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="7ce29-134">Preview features</span></span>

<span data-ttu-id="7ce29-135">Le caratteristiche e i miglioramenti seguenti sono attualmente disponibili in anteprima:</span><span class="sxs-lookup"><span data-stu-id="7ce29-135">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="7ce29-136">**[Visualizzare report per tag di minaccia:](threat-analytics.md#view-reports-per-threat-tags)** i tag di minaccia consentono di concentrarsi su categorie di minacce specifiche ed esaminare i report più rilevanti.</span><span class="sxs-lookup"><span data-stu-id="7ce29-136">**[View reports per threat tags](threat-analytics.md#view-reports-per-threat-tags)** - Threat tags help you focus on specific threat categories and review the most relevant reports.</span></span>
- <span data-ttu-id="7ce29-137">**[API di streaming:](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender supporta lo streaming di tutti gli eventi disponibili tramite Advanced Hunting a un hub eventi e/o a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7ce29-137">**[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender supports streaming all the events available through Advanced Hunting to an Event Hubs and/or Azure storage account.</span></span>
- <span data-ttu-id="7ce29-138">**[Microsoft 365 Defender API:](api-overview.md)** le API di Microsoft 365 Defender di primo livello consentono di automatizzare i flussi di lavoro in base alle tabelle di ricerca avanzate e degli eventi imprevisti condivisi.</span><span class="sxs-lookup"><span data-stu-id="7ce29-138">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="7ce29-139">**[Eseguire azioni nella ricerca avanzata-](advanced-hunting-take-action.md)** Contiene rapidamente minacce o indirizzi di asset compromessi che si trovano nella [ricerca avanzata.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7ce29-139">**[Take action in advanced hunting](advanced-hunting-take-action.md)** - Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="7ce29-140">**[Informazioni di riferimento sullo schema nel](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** portale- Ottenere informazioni sulle tabelle dello schema di ricerca avanzata direttamente nel Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7ce29-140">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="7ce29-141">Oltre alle descrizioni di tabelle e colonne, questo riferimento include tipi di eventi supportati `ActionType` (valori) e query di esempio.</span><span class="sxs-lookup"><span data-stu-id="7ce29-141">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="7ce29-142">**[Funzione DeviceFromIP():](advanced-hunting-devicefromip-function.md)** consente di ottenere informazioni sui dispositivi a cui è stato assegnato uno o più indirizzi IP specifici in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7ce29-142">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)** - Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
