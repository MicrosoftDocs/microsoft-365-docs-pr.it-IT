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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818858"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="51c1c-103">Utilizzo di Esplora contenuto di classificazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="51c1c-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="51c1c-104">Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.</span><span class="sxs-lookup"><span data-stu-id="51c1c-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="51c1c-105">Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="51c1c-105">Content explorer</span></span>

<span data-ttu-id="51c1c-106">Esplora contenuto mostra uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51c1c-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="51c1c-107">Tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="51c1c-107">Sensitive information types</span></span>

<span data-ttu-id="51c1c-108">I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="51c1c-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="51c1c-109">Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](what-the-sensitive-information-types-look-for.md) in varie aree geografiche, pronte per l'uso.</span><span class="sxs-lookup"><span data-stu-id="51c1c-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="51c1c-110">Ad esempio, un numero di carta di credito, numeri di conto corrente bancario, numeri di documento di identità e numeri di servizio Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="51c1c-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="51c1c-111">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="51c1c-111">Sensitivity labels</span></span>

<span data-ttu-id="51c1c-112">Un'[etichetta di sensibilità](sensitivity-labels.md) è semplicemente un contrassegno che indica il valore dell'elemento per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51c1c-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="51c1c-113">Può essere applicata manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="51c1c-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="51c1c-114">Una volta applicata, viene incorporata nel documento e lo seguirà ovunque.</span><span class="sxs-lookup"><span data-stu-id="51c1c-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="51c1c-115">Un'etichetta di riservatezza abilita varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="51c1c-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="51c1c-116">Con la protezione dell'endpoint abilitata, è anche possibile impedire a un elemento di eludere il controllo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51c1c-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="51c1c-117">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="51c1c-117">Retention labels</span></span>

<span data-ttu-id="51c1c-118">Un'[etichetta di conservazione](labels.md) consente di definire per quanto tempo viene conservato un elemento etichettato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="51c1c-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="51c1c-119">Vengono applicate manualmente o automaticamente tramite criteri.</span><span class="sxs-lookup"><span data-stu-id="51c1c-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="51c1c-120">Possono essere utili per favorire la conformità dell'organizzazione ai requisiti di legge e normativi.</span><span class="sxs-lookup"><span data-stu-id="51c1c-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![schermata compressa di Esplora contenuto](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="51c1c-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="51c1c-122">Permissions</span></span>

<span data-ttu-id="51c1c-123">Esistono due ruoli che consentono di accedere a Esplora contenuto:</span><span class="sxs-lookup"><span data-stu-id="51c1c-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="51c1c-124">**Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare ogni elemento e la relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="51c1c-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="51c1c-125">**Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="51c1c-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="51c1c-126">L'account usato per accedere a Esplora contenuto deve essere in uno o entrambi i ruoli.</span><span class="sxs-lookup"><span data-stu-id="51c1c-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="51c1c-127">Questi sono ruoli indipendenti e non cumulativi.</span><span class="sxs-lookup"><span data-stu-id="51c1c-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="51c1c-128">Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="51c1c-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="51c1c-129">Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="51c1c-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="51c1c-130">Come usare Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="51c1c-130">How to use content explorer</span></span>

1. <span data-ttu-id="51c1c-131">Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.</span><span class="sxs-lookup"><span data-stu-id="51c1c-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="51c1c-132">Se si conosce il nome dell'etichetta o il tipo di informazioni riservate, è possibile digitarlo nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="51c1c-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="51c1c-133">In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco. Di seguito viene mostrato un elemento della parte di etichetta di conservazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="51c1c-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="51c1c-134">Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.</span><span class="sxs-lookup"><span data-stu-id="51c1c-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="51c1c-135">Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="51c1c-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c1c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c1c-136">See also</span></span>

- [<span data-ttu-id="51c1c-137">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="51c1c-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="51c1c-138">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="51c1c-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="51c1c-139">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="51c1c-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="51c1c-140">Panoramica dei criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="51c1c-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="51c1c-141">Panoramica della prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="51c1c-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
