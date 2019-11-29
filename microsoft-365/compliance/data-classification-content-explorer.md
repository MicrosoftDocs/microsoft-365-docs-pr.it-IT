---
title: Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Esplora contenuto consente di visualizzare in modo nativo gli elementi con etichetta.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268550"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="c05da-103">Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c05da-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="c05da-104">Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.</span><span class="sxs-lookup"><span data-stu-id="c05da-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="c05da-105">Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="c05da-105">Content explorer</span></span>

<span data-ttu-id="c05da-106">Esplora contenuto è uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c05da-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![schermata compressa di Esplora contenuto](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="c05da-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c05da-108">Permissions</span></span>

<span data-ttu-id="c05da-109">Esistono due ruoli che consentono di accedere a Esplora contenuto:</span><span class="sxs-lookup"><span data-stu-id="c05da-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="c05da-110">**Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare ogni elemento e la relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="c05da-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="c05da-111">**Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c05da-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="c05da-112">L'account usato per accedere a Esplora contenuto deve essere in uno o entrambi i ruoli.</span><span class="sxs-lookup"><span data-stu-id="c05da-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="c05da-113">Questi sono ruoli indipendenti e non cumulativi.</span><span class="sxs-lookup"><span data-stu-id="c05da-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="c05da-114">Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="c05da-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="c05da-115">Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="c05da-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="c05da-116">Come usare Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="c05da-116">How to use content explorer</span></span>

1. <span data-ttu-id="c05da-117">Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.</span><span class="sxs-lookup"><span data-stu-id="c05da-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="c05da-118">Se si conosce il nome dell'etichetta o il tipo di informazioni riservate, è possibile digitarlo nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c05da-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="c05da-119">In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco. Di seguito viene mostrato un elemento della parte di etichetta di conservazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c05da-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="c05da-120">Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.</span><span class="sxs-lookup"><span data-stu-id="c05da-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="c05da-121">Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="c05da-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="c05da-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c05da-122">See also</span></span>

- [<span data-ttu-id="c05da-123">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="c05da-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c05da-124">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="c05da-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="c05da-125">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="c05da-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="c05da-126">Panoramica dei criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="c05da-126">Overview of retention policies</span></span>](retention-policies.md)
