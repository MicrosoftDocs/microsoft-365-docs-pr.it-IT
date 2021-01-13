---
title: Allineamento avanzato di eDiscovery con EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Il flusso di lavoro incorporato di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento di Electronic Discovery (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841634"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="a2932-103">Allineamento avanzato di eDiscovery con il modello di riferimento per l'individuazione elettronica</span><span class="sxs-lookup"><span data-stu-id="a2932-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="a2932-104">Il flusso di lavoro incorporato di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento di Electronic Discovery (EDRM).</span><span class="sxs-lookup"><span data-stu-id="a2932-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

<span data-ttu-id="a2932-106">(Fonte di immagini per gentile concessione di edrm.net.</span><span class="sxs-lookup"><span data-stu-id="a2932-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="a2932-107">L'immagine di origine è stata resa disponibile nella licenza Creative Commons Attribution 3,0 Unported.</span><span class="sxs-lookup"><span data-stu-id="a2932-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="a2932-108">A livello elevato, ecco come Advanced eDiscovery supporta il flusso di lavoro di EDRM:</span><span class="sxs-lookup"><span data-stu-id="a2932-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="a2932-109">**Identificazione.**</span><span class="sxs-lookup"><span data-stu-id="a2932-109">**Identification.**</span></span> <span data-ttu-id="a2932-110">Dopo aver identificato potenziali persone di interesse in un'indagine, è possibile aggiungerle come depositari (denominate anche *depositari dei dati*, in quanto potrebbero essere in possesso di informazioni rilevanti per l'indagine) in un caso di eDiscovery avanzato.</span><span class="sxs-lookup"><span data-stu-id="a2932-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="a2932-111">Dopo che gli utenti vengono aggiunti come depositari, è facile conservare, raccogliere e rivedere i documenti del custode.</span><span class="sxs-lookup"><span data-stu-id="a2932-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="a2932-112">**Conservazione.**</span><span class="sxs-lookup"><span data-stu-id="a2932-112">**Preservation.**</span></span> <span data-ttu-id="a2932-113">Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di inserire una conservazione legale sulle origini dati associate ai depositari in un caso.</span><span class="sxs-lookup"><span data-stu-id="a2932-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="a2932-114">È inoltre possibile inserire i dati non detentivi in attesa.</span><span class="sxs-lookup"><span data-stu-id="a2932-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="a2932-115">Advanced eDiscovery dispone anche di un flusso di lavoro di comunicazione incorporato in modo da poter inviare notifiche di archiviazione legale ai depositari e tenere conto dei loro ringraziamenti.</span><span class="sxs-lookup"><span data-stu-id="a2932-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="a2932-116">**Raccolta.**</span><span class="sxs-lookup"><span data-stu-id="a2932-116">**Collection.**</span></span> <span data-ttu-id="a2932-117">Dopo aver identificato (e conservato) le origini dati rilevanti per l'analisi, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery Search for and Collect Live Data from the detenzione Data Sources (e le origini dati non detentive, se applicabile) che potrebbero essere rilevanti per il caso.</span><span class="sxs-lookup"><span data-stu-id="a2932-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="a2932-118">**Elaborazione.**</span><span class="sxs-lookup"><span data-stu-id="a2932-118">**Processing.**</span></span> <span data-ttu-id="a2932-119">Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nel processo per ulteriori riesami e analisi.</span><span class="sxs-lookup"><span data-stu-id="a2932-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="a2932-120">In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set di revisione*), in cui viene fornita una visualizzazione statica dei dati del caso.</span><span class="sxs-lookup"><span data-stu-id="a2932-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="a2932-121">**Recensione.**</span><span class="sxs-lookup"><span data-stu-id="a2932-121">**Review.**</span></span> <span data-ttu-id="a2932-122">Dopo aver aggiunto i dati a un set di revisione, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più pertinente per il caso.</span><span class="sxs-lookup"><span data-stu-id="a2932-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="a2932-123">Inoltre, è possibile annotare e contrassegnare documenti specifici.</span><span class="sxs-lookup"><span data-stu-id="a2932-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="a2932-124">**Analisi.**</span><span class="sxs-lookup"><span data-stu-id="a2932-124">**Analysis.**</span></span> <span data-ttu-id="a2932-125">Advanced eDiscovery fornisce uno strumento di analisi integrata che consente di eliminare i dati dall'insieme di revisione che si determina non è pertinente per l'indagine.</span><span class="sxs-lookup"><span data-stu-id="a2932-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="a2932-126">Oltre a ridurre il volume dei dati rilevanti, Advance eDiscovery aiuta anche a salvare i costi di revisione legale, consentendo di organizzare il contenuto per semplificare e rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="a2932-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="a2932-127">**Produzione** e **presentazione.**</span><span class="sxs-lookup"><span data-stu-id="a2932-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="a2932-128">Quando si è pronti, è possibile esportare i documenti da un set di revisione per la revisione legale.</span><span class="sxs-lookup"><span data-stu-id="a2932-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="a2932-129">È possibile esportare documenti nel formato nativo o in un formato specificato per EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="a2932-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="a2932-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="a2932-130">More information</span></span>

<span data-ttu-id="a2932-131">Per iniziare a utilizzare Advanced eDiscovery, vedere:</span><span class="sxs-lookup"><span data-stu-id="a2932-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="a2932-132">Configurare Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a2932-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="a2932-133">Creazione e gestione di un caso di eDiscovery avanzato</span><span class="sxs-lookup"><span data-stu-id="a2932-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)