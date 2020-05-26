---
title: Introduzione a Esplora contenuto
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
ms.openlocfilehash: 731ae51a02e4a6fbd35b5be7c0bf083c814ddfd3
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327852"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="cc206-103">Introduzione a Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="cc206-103">Get started with content explorer</span></span>

<span data-ttu-id="cc206-104">Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.</span><span class="sxs-lookup"><span data-stu-id="cc206-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![schermata compressa di Esplora contenuto](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="cc206-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cc206-106">Prerequisites</span></span>

<span data-ttu-id="cc206-107">A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="cc206-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="cc206-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cc206-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="cc206-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cc206-109">Office 365 (E5)</span></span>
- <span data-ttu-id="cc206-110">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="cc206-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="cc206-111">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="cc206-111">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="cc206-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cc206-112">Permissions</span></span>

<span data-ttu-id="cc206-113">Per accedere alla scheda Esplora contenuto, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="cc206-113">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="cc206-114">I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="cc206-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="cc206-115">Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](sensitive-information-type-entity-definitions.md) in varie aree geografiche, pronte per l'uso.</span><span class="sxs-lookup"><span data-stu-id="cc206-115">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="cc206-116">Ad esempio, un numero di carta di credito, numeri di conto corrente bancario, numeri di documento di identità e numeri di servizio Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="cc206-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="cc206-117">**Gruppi di ruoli di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="cc206-117">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="cc206-118">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="cc206-118">Global administrator</span></span>
- <span data-ttu-id="cc206-119">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="cc206-119">Compliance administrator</span></span>
- <span data-ttu-id="cc206-120">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="cc206-120">Security administrator</span></span>
- <span data-ttu-id="cc206-121">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="cc206-121">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc206-122">L'appartenenza a questi gruppi di ruoli non consente di visualizzare l'elenco di elementi in Esplora contenuto o di visualizzare il contenuto degli elementi in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-122">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="cc206-123">Autorizzazioni necessarie per accedere agli elementi in Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="cc206-123">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="cc206-124">L'accesso a Esplora contenuto è estremamente limitato perché consente di leggere il contenuto dei file digitalizzati.</span><span class="sxs-lookup"><span data-stu-id="cc206-124">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc206-125">Queste autorizzazioni sostituiscono le autorizzazioni assegnate in locale, che permettono di visualizzare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-125">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="cc206-126">Sono due i ruoli che consentono di accedere a Esplora contenuto:</span><span class="sxs-lookup"><span data-stu-id="cc206-126">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="cc206-127">**Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo gruppo di ruoli consente di visualizzare ogni elemento e la relativa posizione nella visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="cc206-127">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="cc206-128">Il ruolo `data classification list viewer` è stato preassegnato a questo gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="cc206-128">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="cc206-129">**Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo gruppo di ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="cc206-129">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="cc206-130">Il ruolo `data classification content viewer` è stato preassegnato a questo gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="cc206-130">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="cc206-131">L'account usato per accedere a Esplora contenuto deve essere presente in uno o entrambi i gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="cc206-131">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="cc206-132">Si tratta di gruppi di ruoli indipendenti e non cumulativi.</span><span class="sxs-lookup"><span data-stu-id="cc206-132">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="cc206-133">Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-133">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="cc206-134">Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-134">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="cc206-135">È anche possibile assegnare uno o entrambi i ruoli a un gruppo di ruoli personalizzato per personalizzare l'accesso a Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-135">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="cc206-136">Un amministratore globale, un amministratore di conformità o un amministratore dei dati può assegnare l'appartenenza ai gruppi di ruolo Visualizzatore elenco di Esplora contenuto e Visualizzatore contenuto di Esplora contenuto necessaria.</span><span class="sxs-lookup"><span data-stu-id="cc206-136">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="cc206-137">Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="cc206-137">Content explorer</span></span>

<span data-ttu-id="cc206-138">Esplora contenuto mostra uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc206-138">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="cc206-139">Tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="cc206-139">Sensitive information types</span></span>

<span data-ttu-id="cc206-140">I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="cc206-140">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="cc206-141">Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](sensitive-information-type-entity-definitions.md) di diverse aree geografiche, pronte per l'uso.</span><span class="sxs-lookup"><span data-stu-id="cc206-141">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="cc206-142">Ad esempio, un numero di carta di credito, numeri di conti corrente bancari, numeri di documenti di identità e numeri di servizio Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="cc206-142">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="cc206-143">Al momento Esplora contenuto non analizza i tipi di informazioni sensibili in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cc206-143">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="cc206-144">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="cc206-144">Sensitivity labels</span></span>

<span data-ttu-id="cc206-145">Un'[etichetta di sensibilità](sensitivity-labels.md) è semplicemente un contrassegno che indica il valore dell'elemento per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc206-145">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="cc206-146">Può essere applicata manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc206-146">It can be applied manually, or automatically.</span></span> <span data-ttu-id="cc206-147">Una volta applicata, viene incorporata nel documento e lo seguirà ovunque.</span><span class="sxs-lookup"><span data-stu-id="cc206-147">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="cc206-148">Un'etichetta di riservatezza abilita varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="cc206-148">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="cc206-149">Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="cc206-149">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="cc206-150">Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="cc206-150">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="cc206-151">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="cc206-151">Retention labels</span></span>

<span data-ttu-id="cc206-152">Un'[etichetta di conservazione](labels.md) consente di definire per quanto tempo viene conservato un elemento etichettato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="cc206-152">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="cc206-153">Vengono applicate manualmente o automaticamente tramite criteri.</span><span class="sxs-lookup"><span data-stu-id="cc206-153">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="cc206-154">Possono essere utili per favorire la conformità dell'organizzazione ai requisiti di legge e normativi.</span><span class="sxs-lookup"><span data-stu-id="cc206-154">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="cc206-155">Come usare Esplora contenuto</span><span class="sxs-lookup"><span data-stu-id="cc206-155">How to use content explorer</span></span>

1. <span data-ttu-id="cc206-156">Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.</span><span class="sxs-lookup"><span data-stu-id="cc206-156">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="cc206-157">Se si conosce il nome dell'etichetta o il tipo di informazioni sensibili, è possibile digitarlo nella casella filtro.</span><span class="sxs-lookup"><span data-stu-id="cc206-157">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="cc206-158">In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="cc206-158">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="cc206-159">Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.</span><span class="sxs-lookup"><span data-stu-id="cc206-159">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="cc206-160">Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="cc206-160">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="cc206-161">Esporta</span><span class="sxs-lookup"><span data-stu-id="cc206-161">Export</span></span>
<span data-ttu-id="cc206-162">Il controllo **Esporta** crea un file .csv che contiene un elenco di tutti gli elementi visualizzati nel riquadro **Tutte le posizioni**.</span><span class="sxs-lookup"><span data-stu-id="cc206-162">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![controllo esporta per classificazione dati](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="cc206-164">Ricerca</span><span class="sxs-lookup"><span data-stu-id="cc206-164">Search</span></span>

<span data-ttu-id="cc206-165">Quando viene eseguito il drill-down in una posizione, come una cartella di Exchange o un sito SharePoint o OneDrive, si apre lo strumento di **ricerca**.</span><span class="sxs-lookup"><span data-stu-id="cc206-165">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![strumento di ricerca di Esplora contenuto](../media/data_classification_search_tool.png)


<span data-ttu-id="cc206-167">L'ambito dello strumento di ricerca è il contenuto del riquadro **Tutte le posizioni** e ciò che è possibile cercare varia in base alla posizione selezionata.</span><span class="sxs-lookup"><span data-stu-id="cc206-167">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="cc206-168">Quando la posizione selezionata è **Exchange**, è possibile effettuare la ricerca nell'intero indirizzo di posta elettronica della cassetta postale, ad esempio `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="cc206-168">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="cc206-169">Quando la posizione selezionata è **SharePoint** o **OneDrive**, lo strumento di ricerca si apre quando viene eseguito il drill-down dei nomi dei siti, delle cartelle e dei file.</span><span class="sxs-lookup"><span data-stu-id="cc206-169">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="cc206-170">**OneDrive** Durante il programma di anteprima, abbiamo ascoltato i preziosi feedback degli utenti sull'integrazione di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cc206-170">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="cc206-171">In base al feedback ricevuto, la funzionalità OneDrive rimarrà in anteprima finché non saranno disponibili tutte le correzioni.</span><span class="sxs-lookup"><span data-stu-id="cc206-171">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="cc206-172">In base al tenant, alcuni clienti potrebbero non vedere OneDrive come posizione.</span><span class="sxs-lookup"><span data-stu-id="cc206-172">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="cc206-173">Apprezziamo molto il continuo supporto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="cc206-173">We appreciate your continued support on this.</span></span>

<span data-ttu-id="cc206-174">Ecco cosa è possibile cercare:</span><span class="sxs-lookup"><span data-stu-id="cc206-174">You can search on:</span></span>


|<span data-ttu-id="cc206-175">valore</span><span class="sxs-lookup"><span data-stu-id="cc206-175">value</span></span>|<span data-ttu-id="cc206-176">esempio</span><span class="sxs-lookup"><span data-stu-id="cc206-176">example</span></span>  |
|---------|---------|
|<span data-ttu-id="cc206-177">nome completo del sito</span><span class="sxs-lookup"><span data-stu-id="cc206-177">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="cc206-178">nome della cartella radice - ricerca tutte le sottocartelle</span><span class="sxs-lookup"><span data-stu-id="cc206-178">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="cc206-179">nome del file</span><span class="sxs-lookup"><span data-stu-id="cc206-179">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="cc206-180">testo all'inizio del nome del file</span><span class="sxs-lookup"><span data-stu-id="cc206-180">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="cc206-181">testo dopo un trattino basso (_) nel nome del file</span><span class="sxs-lookup"><span data-stu-id="cc206-181">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="cc206-182">`Resume` o `1234`</span><span class="sxs-lookup"><span data-stu-id="cc206-182">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="cc206-183">estensione del file</span><span class="sxs-lookup"><span data-stu-id="cc206-183">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="cc206-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc206-184">See also</span></span>

- [<span data-ttu-id="cc206-185">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="cc206-185">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="cc206-186">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="cc206-186">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="cc206-187">Sensitive information type entity definitions.md</span><span class="sxs-lookup"><span data-stu-id="cc206-187">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="cc206-188">Panoramica dei criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="cc206-188">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="cc206-189">Panoramica della prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="cc206-189">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
