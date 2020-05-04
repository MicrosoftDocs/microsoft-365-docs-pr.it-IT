---
title: Introduzione a Esplora contenuto (anteprima)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3d1c938d3a9d7ff25bb66a5b344cfbb29eace84c
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957266"
---
# <a name="get-started-with-content-explorer-preview"></a><span data-ttu-id="50afe-103">Introduzione a Esplora contenuto (anteprima)</span><span class="sxs-lookup"><span data-stu-id="50afe-103">Get started with content explorer (preview)</span></span>

<span data-ttu-id="50afe-104">Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.</span><span class="sxs-lookup"><span data-stu-id="50afe-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50afe-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="50afe-105">Prerequisites</span></span>

<span data-ttu-id="50afe-106">A ogni account che accede e usa Esplora attività deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="50afe-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="50afe-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="50afe-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="50afe-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="50afe-108">Office 365 (E5)</span></span>
- <span data-ttu-id="50afe-109">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="50afe-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="50afe-110">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="50afe-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="50afe-111">Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="50afe-111">Content explorer</span></span>

<span data-ttu-id="50afe-112">Esplora contenuto mostra uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50afe-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="50afe-113">Tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="50afe-113">Sensitive information types</span></span>

<span data-ttu-id="50afe-114">I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="50afe-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="50afe-115">Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](what-the-sensitive-information-types-look-for.md) in varie aree geografiche, pronte per l'uso.</span><span class="sxs-lookup"><span data-stu-id="50afe-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="50afe-116">Ad esempio, un numero di carta di credito, numeri di conto corrente bancario, numeri di documento di identità e numeri di servizio Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="50afe-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="50afe-117">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="50afe-117">Sensitivity labels</span></span>

<span data-ttu-id="50afe-118">Un'[etichetta di sensibilità](sensitivity-labels.md) è semplicemente un contrassegno che indica il valore dell'elemento per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50afe-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="50afe-119">Può essere applicata manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="50afe-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="50afe-120">Una volta applicata, viene incorporata nel documento e lo seguirà ovunque.</span><span class="sxs-lookup"><span data-stu-id="50afe-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="50afe-121">Un'etichetta di riservatezza abilita varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="50afe-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="50afe-122">Con la protezione dell'endpoint abilitata, è anche possibile impedire a un elemento di eludere il controllo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50afe-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="50afe-123">Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="50afe-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="50afe-124">Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="50afe-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="50afe-125">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="50afe-125">Retention labels</span></span>

<span data-ttu-id="50afe-126">Un'[etichetta di conservazione](labels.md) consente di definire per quanto tempo viene conservato un elemento etichettato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="50afe-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="50afe-127">Vengono applicate manualmente o automaticamente tramite criteri.</span><span class="sxs-lookup"><span data-stu-id="50afe-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="50afe-128">Possono essere utili per favorire la conformità dell'organizzazione ai requisiti di legge e normativi.</span><span class="sxs-lookup"><span data-stu-id="50afe-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![schermata compressa di Esplora contenuto](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="50afe-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="50afe-130">Permissions</span></span>

<span data-ttu-id="50afe-131">Sono due i ruoli che consentono di accedere a Esplora contenuto:</span><span class="sxs-lookup"><span data-stu-id="50afe-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="50afe-132">**Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo gruppo di ruoli consente di visualizzare ogni elemento e la relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="50afe-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="50afe-133">Il ruolo `data classification list viewer` è stato preassegnato a questo gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="50afe-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="50afe-134">**Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo gruppo di ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="50afe-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="50afe-135">Il ruolo `data classification content viewer` è stato preassegnato a questo gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="50afe-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="50afe-136">L'account usato per accedere a Esplora contenuto deve essere presente in uno o entrambi i gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="50afe-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="50afe-137">Si tratta di gruppi di ruoli indipendenti e non cumulativi.</span><span class="sxs-lookup"><span data-stu-id="50afe-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="50afe-138">Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="50afe-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="50afe-139">Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="50afe-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="50afe-140">È anche possibile assegnare uno o entrambi i ruoli a un gruppo di ruoli personalizzato per personalizzare l'accesso a Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="50afe-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="50afe-141">Un amministratore globale, un amministratore di conformità o un amministratore dei dati può assegnare l'appartenenza ai gruppi di ruolo Visualizzatore elenco di Esplora contenuto e Visualizzatore contenuto di Esplora contenuto necessaria.</span><span class="sxs-lookup"><span data-stu-id="50afe-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="50afe-142">Come usare Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="50afe-142">How to use content explorer</span></span>

1. <span data-ttu-id="50afe-143">Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.</span><span class="sxs-lookup"><span data-stu-id="50afe-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="50afe-144">Se si conosce il nome dell'etichetta o il tipo di informazioni riservate, è possibile digitarlo nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="50afe-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="50afe-145">In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco. Di seguito viene mostrato un elemento della parte di etichetta di conservazione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="50afe-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="50afe-146">Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.</span><span class="sxs-lookup"><span data-stu-id="50afe-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="50afe-147">Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="50afe-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="50afe-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50afe-148">See also</span></span>

- [<span data-ttu-id="50afe-149">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="50afe-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="50afe-150">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="50afe-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="50afe-151">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="50afe-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="50afe-152">Panoramica dei criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="50afe-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="50afe-153">Panoramica della prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="50afe-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
