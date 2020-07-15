---
title: Introduzione alla classificazione dei dati
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
description: Il dashboard di classificazione dei dati offre visibilità sulla quantità di dati riservati che sono stati individuati e classificati nell'organizzazione.
ms.openlocfilehash: a9c7a275a0f3f2db7d931be5af77b00291cdad83
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127221"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="d40d1-103">Conoscere i dati - Panoramica della classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d40d1-103">Know your data - data classification overview</span></span>

<span data-ttu-id="d40d1-104">Gli amministratori di Microsoft 365 o gli amministratori di conformità possono valutare e poi contrassegnare i contenuti all'interno dell'organizzazione per controllarne gli spostamenti, per proteggerli indipendentemente dalla posizione e per garantire che vengano conservati ed eliminati in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="d40d1-105">Queste operazioni possono essere eseguite mediante l'applicazione di [etichette di riservatezza](sensitivity-labels.md), di [etichette di conservazione](retention.md#retention-labels) e tramite la classificazione della tipologia delle informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="d40d1-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="d40d1-106">Esistono vari modi per eseguire l'individuazione, la valutazione e l'aggiunta di tag, ma il risultato finale è che potrebbe essere presente un numero molto elevato di documenti e messaggi di posta elettronica contrassegnati e classificati con una o entrambe le etichette.</span><span class="sxs-lookup"><span data-stu-id="d40d1-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="d40d1-107">Dopo aver applicato le etichette di conservazione e le etichette di riservatezza, è opportuno verificarne l'utilizzo nel tenant e controllare le operazioni che vengono svolte con tali elementi.</span><span class="sxs-lookup"><span data-stu-id="d40d1-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="d40d1-108">La pagina di classificazione dei dati consente di avere visibilità sui contenuti, in particolare:</span><span class="sxs-lookup"><span data-stu-id="d40d1-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="d40d1-109">il numero degli elementi classificati come tipologie di informazioni riservate e quali sono le tipologie di classificazione</span><span class="sxs-lookup"><span data-stu-id="d40d1-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="d40d1-110">le principali etichette di riservatezza applicate sia in Microsoft 365 che in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d40d1-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="d40d1-111">le principali etichette di conservazione applicate</span><span class="sxs-lookup"><span data-stu-id="d40d1-111">the top applied retention labels</span></span>
- <span data-ttu-id="d40d1-112">il riepilogo delle attività che gli utenti svolgono sui contenuti riservati</span><span class="sxs-lookup"><span data-stu-id="d40d1-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="d40d1-113">le posizioni dei dati riservati e conservati</span><span class="sxs-lookup"><span data-stu-id="d40d1-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="d40d1-114">Queste funzionalità vengono anche gestite nella pagina di classificazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="d40d1-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="d40d1-115">classificatori sottoponibili a training</span><span class="sxs-lookup"><span data-stu-id="d40d1-115">trainable classifiers</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="d40d1-116">tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="d40d1-116">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)

<span data-ttu-id="d40d1-117">La funzionalità Classificazione dei dati è disponibile nel **Centro conformità Microsoft 365**o nel **Centro sicurezza Microsoft 365** > **Classificazione** > **Classificazione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="d40d1-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="d40d1-118">Seguire una presentazione video sulle funzionalità di classificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d40d1-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="d40d1-119">Classificazione dei dati consentità di analizzare il contenuto riservato e il contenuto con etichetta prima di creare criteri.</span><span class="sxs-lookup"><span data-stu-id="d40d1-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="d40d1-120">Tale operazione è nota come **gestione senza modifiche**.</span><span class="sxs-lookup"><span data-stu-id="d40d1-120">This is called **zero change management**.</span></span> <span data-ttu-id="d40d1-121">Consente di vedere l'impatto di tutte le etichette di conservazione e di riservatezza sul proprio ambiente e permette di valutare la necessità di iniziare a usare criteri di protezione e di governance.</span><span class="sxs-lookup"><span data-stu-id="d40d1-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d40d1-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d40d1-122">Prerequisites</span></span>

<span data-ttu-id="d40d1-123">A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="d40d1-123">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="d40d1-124">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="d40d1-124">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="d40d1-125">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="d40d1-125">Office 365 (E5)</span></span>
- <span data-ttu-id="d40d1-126">Componente aggiuntivo Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="d40d1-126">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="d40d1-127">Componente aggiuntivo Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="d40d1-127">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="d40d1-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d40d1-128">Permissions</span></span>

 <span data-ttu-id="d40d1-129">Per accedere alla pagina di classificazione dei dati, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="d40d1-129">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="d40d1-130">**Gruppi di ruoli di Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="d40d1-130">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="d40d1-131">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="d40d1-131">Global administrator</span></span>
- <span data-ttu-id="d40d1-132">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="d40d1-132">Compliance administrator</span></span>
- <span data-ttu-id="d40d1-133">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d40d1-133">Security administrator</span></span>
- <span data-ttu-id="d40d1-134">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="d40d1-134">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="d40d1-135">Tipologie di informazioni riservate usate più di frequente nei contenuti</span><span class="sxs-lookup"><span data-stu-id="d40d1-135">Sensitive information types used most in your content</span></span>

<span data-ttu-id="d40d1-136">Microsoft 365 fornisce diverse definizioni delle tipologie di informazioni riservate, ad esempio un elemento che contiene un codice di previdenza sociale o un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="d40d1-136">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="d40d1-137">Per altre informazioni sui tipi di informazioni sensibili, vedere [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d40d1-137">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="d40d1-138">La scheda tipologie di informazioni riservate mostra le principali tipologie di informazioni riservate individuate ed etichettate all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-138">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![tipologie principali di informazioni riservate](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="d40d1-140">Per determinare il numero di elementi in una determinata categoria di classificazione, passare il puntatore del mouse sulla barra della categoria.</span><span class="sxs-lookup"><span data-stu-id="d40d1-140">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![principali tipologie di informazioni riservate visualizzate al passaggio del mouse](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="d40d1-142">Se la scheda mostra il messaggio "Nessun dato trovato per le informazioni riservate".</span><span class="sxs-lookup"><span data-stu-id="d40d1-142">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="d40d1-143">Questo significa che non sono presenti elementi nell'organizzazione classificati come tipologia di informazioni riservate o sottoposti a ricerca per indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-143">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="d40d1-144">Per iniziare a usare le etichette, vedere:</span><span class="sxs-lookup"><span data-stu-id="d40d1-144">To get started with labels, see:</span></span>
>- [<span data-ttu-id="d40d1-145">Iniziare a usare le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="d40d1-145">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="d40d1-146">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="d40d1-146">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="d40d1-147">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="d40d1-147">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="d40d1-148">Principali etichette di riservatezza applicate ai contenuti</span><span class="sxs-lookup"><span data-stu-id="d40d1-148">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="d40d1-149">Quando si applica un'etichetta di riservatezza a un elemento tramite Microsoft 365 o Azure Information Protection (AIP), si verificano le seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="d40d1-149">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="d40d1-150">il tag che indica il valore dell'elemento per l'organizzazione viene incorporato nel documento e lo seguirà ovunque</span><span class="sxs-lookup"><span data-stu-id="d40d1-150">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="d40d1-151">la presenza del tag permette varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia.</span><span class="sxs-lookup"><span data-stu-id="d40d1-151">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="d40d1-152">Con la protezione dell'endpoint abilitata, è anche possibile impedire a un elemento di eludere il controllo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-152">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="d40d1-153">Per ulteriori informazioni sulle etichette di riservatezza, vedere [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="d40d1-153">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="d40d1-154">Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d40d1-154">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="d40d1-155">Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="d40d1-155">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="d40d1-156">La scheda etichetta di riservatezza mostra il numero di elementi (e-mail o documenti) in base al livello di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="d40d1-156">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![schermata della scomposizione dei contenuti in base al segnaposto di classificazione delle etichette di riservatezza](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="d40d1-158">Se non sono state create o pubblicate etichette di riservatezza o non è stata applicata alcuna etichetta di riservatezza ai contenuti, la scheda visualizzerà il messaggio "Non sono state rilevate etichette di riservatezza".</span><span class="sxs-lookup"><span data-stu-id="d40d1-158">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="d40d1-159">Per iniziare a usare le etichette, vedere:</span><span class="sxs-lookup"><span data-stu-id="d40d1-159">To get started with labels, see:</span></span>
>- <span data-ttu-id="d40d1-160">[etichette di riservatezza](sensitivity-labels.md) oppure per AIP [Configurare i criteri di protezione delle informazioni in Azure](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="d40d1-160">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="d40d1-161">Principali etichette di conservazione applicate ai contenuti</span><span class="sxs-lookup"><span data-stu-id="d40d1-161">Top retention labels applied to content</span></span>

<span data-ttu-id="d40d1-162">Le etichette di conservazione vengono usate per gestire l'eliminazione dei contenuti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-162">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="d40d1-163">Se applicate, possono essere usate per controllare il periodo di conservazione di un documento prima dell'eliminazione, se deve essere esaminato prima dell'eliminazione, quando scade il periodo di conservazione oppure se deve essere contrassegnato come record che non deve essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="d40d1-163">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="d40d1-164">Per altre informazioni, vedere [Informazioni sui criteri e sulle etichette di conservazione](retention.md).</span><span class="sxs-lookup"><span data-stu-id="d40d1-164">For more information see, [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="d40d1-165">Le scheda delle principali etichette di conservazione applicate mostra il numero di elementi con una determinata etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-165">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![schermata segnaposto delle principali etichette di conservazione](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="d40d1-167">Se la scheda mostra il messaggio "Non sono state rilevate etichette di conservazione" significa che non sono state create o pubblicate etichette di conservazione o non è stata applicata alcuna etichetta di conservazione ai contenuti.</span><span class="sxs-lookup"><span data-stu-id="d40d1-167">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="d40d1-168">Per iniziare a usare le etichette di conservazione, vedere:</span><span class="sxs-lookup"><span data-stu-id="d40d1-168">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="d40d1-169">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="d40d1-169">Get started with retention policies and retention lables</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="d40d1-170">Attività principali rilevate</span><span class="sxs-lookup"><span data-stu-id="d40d1-170">Top activities detected</span></span>

<span data-ttu-id="d40d1-171">Questa scheda offre un breve riepilogo delle azioni più comuni eseguite dagli utenti con gli elementi con etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="d40d1-171">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="d40d1-172">È possibile usare [Esplora attività](data-classification-activity-explorer.md) per eseguire il drill-down avanzato su otto diverse attività di cui Microsoft 365 tiene traccia sui contenuti etichettati e su contenuti presenti negli endpoint di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d40d1-172">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="d40d1-173">Se la scheda visualizza il messaggio "Non è stata rilevata alcuna attività", significa che non sono state rilevate attività sui file o che non è stato attivato il controllo da parte dell'utente e dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="d40d1-173">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="d40d1-174">Per attivare i log di controllo, vedere:</span><span class="sxs-lookup"><span data-stu-id="d40d1-174">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="d40d1-175">Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d40d1-175">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="d40d1-176">Dati con etichette di riservatezza e conservazione in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="d40d1-176">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="d40d1-177">Il motivo della classificazione dei dati consiste nel fornire visibilità sul numero di elementi etichettati e della relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="d40d1-177">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="d40d1-178">Queste schede consentono di conoscere il numero di elementi etichettati in Exchange, SharePoint, OneDrive e così via.</span><span class="sxs-lookup"><span data-stu-id="d40d1-178">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="d40d1-179">Se la scheda visualizza il messaggio "Non sono state rilevate posizioni" significa che non sono state create o pubblicate etichette di riservatezza o che non è stata applicata alcuna etichetta di conservazione ai contenuti.</span><span class="sxs-lookup"><span data-stu-id="d40d1-179">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="d40d1-180">Per iniziare a usare le etichette di riservatezza vedere:</span><span class="sxs-lookup"><span data-stu-id="d40d1-180">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="d40d1-181">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="d40d1-181">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="d40d1-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d40d1-182">See also</span></span>

- [<span data-ttu-id="d40d1-183">Visualizzazione delle attività con etichette (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d40d1-183">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d40d1-184">Visualizzare il contenuto con etichetta (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d40d1-184">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="d40d1-185">Informazioni sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="d40d1-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d40d1-186">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="d40d1-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="d40d1-187">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="d40d1-187">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="d40d1-188">Introduzione ai classificatori sottoponibili a training (anteprima)</span><span class="sxs-lookup"><span data-stu-id="d40d1-188">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
