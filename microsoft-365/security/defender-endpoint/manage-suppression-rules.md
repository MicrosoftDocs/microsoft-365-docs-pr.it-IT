---
title: Gestire le regole di eliminazione di Microsoft Defender per endpoint
description: Potrebbe essere necessario impedire la visualizzazione degli avvisi nel portale utilizzando le regole di eliminazione. Scopri come gestire le regole di eliminazione in Microsoft Defender ATP.
keywords: gestire l'eliminazione, le regole, il nome della regola, l'ambito, l'azione, gli avvisi, attivare, disattivare
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
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063965"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="572fc-105">Gestire le regole di eliminazione</span><span class="sxs-lookup"><span data-stu-id="572fc-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="572fc-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="572fc-106">**Applies to:**</span></span>
- [<span data-ttu-id="572fc-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="572fc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="572fc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="572fc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="572fc-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="572fc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="572fc-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="572fc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="572fc-111">Potrebbero essere presenti scenari in cui è necessario eliminare la visualizzazione degli avvisi nel portale.</span><span class="sxs-lookup"><span data-stu-id="572fc-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="572fc-112">È possibile creare regole di eliminazione per avvisi specifici noti come innocui, ad esempio strumenti o processi noti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="572fc-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="572fc-113">Per ulteriori informazioni su come eliminare gli avvisi, vedere [Eliminazione di avvisi.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="572fc-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="572fc-114">È possibile visualizzare un elenco di tutte le regole di eliminazione e gestirle in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="572fc-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="572fc-115">È inoltre possibile attivare o disattivare una regola di eliminazione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="572fc-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="572fc-116">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Eliminazione avviso.**</span><span class="sxs-lookup"><span data-stu-id="572fc-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="572fc-117">Viene visualizzato l'elenco delle regole di eliminazione create dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="572fc-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="572fc-118">Selezionare una regola facendo clic sulla casella di controllo accanto al nome della regola.</span><span class="sxs-lookup"><span data-stu-id="572fc-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="572fc-119">Fare **clic su Attiva regola,** Modifica **regola** o **Elimina regola.**</span><span class="sxs-lookup"><span data-stu-id="572fc-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="572fc-120">Quando si apportano modifiche a una regola, è possibile scegliere di rilasciare gli avvisi già eliminati, indipendentemente dal fatto che corrispondano o meno ai nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="572fc-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="572fc-121">Visualizzare i dettagli di una regola di eliminazione</span><span class="sxs-lookup"><span data-stu-id="572fc-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="572fc-122">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Eliminazione avviso.**</span><span class="sxs-lookup"><span data-stu-id="572fc-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="572fc-123">Viene visualizzato l'elenco delle regole di eliminazione create dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="572fc-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="572fc-124">Fare clic sul nome di una regola.</span><span class="sxs-lookup"><span data-stu-id="572fc-124">Click on a rule name.</span></span> <span data-ttu-id="572fc-125">Vengono visualizzati i dettagli della regola.</span><span class="sxs-lookup"><span data-stu-id="572fc-125">Details of the rule is displayed.</span></span> <span data-ttu-id="572fc-126">Verranno visualizzati i dettagli della regola, ad esempio stato, ambito, azione, numero di avvisi corrispondenti, creati da e data di creazione della regola.</span><span class="sxs-lookup"><span data-stu-id="572fc-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="572fc-127">È inoltre possibile visualizzare gli avvisi associati e le condizioni della regola.</span><span class="sxs-lookup"><span data-stu-id="572fc-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="572fc-128">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="572fc-128">Related topics</span></span>

- [<span data-ttu-id="572fc-129">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="572fc-129">Manage alerts</span></span>](manage-alerts.md)
