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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 si allinea al processo di eDiscovery descritto dal modello di riferimento per l'individuazione elettronica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727489"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="b93e6-103">Allineamento avanzato di eDiscovery con il modello di riferimento per l'individuazione elettronica</span><span class="sxs-lookup"><span data-stu-id="b93e6-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="b93e6-104">Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 si allinea al processo di eDiscovery descritto dal modello di riferimento per l'individuazione elettronica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="b93e6-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![EdRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

<span data-ttu-id="b93e6-106">(Origine immagine per gentile edrm.net.</span><span class="sxs-lookup"><span data-stu-id="b93e6-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="b93e6-107">L'immagine di origine è stata resa disponibile in Creative Commons Attribution 3.0 Unported License.</span><span class="sxs-lookup"><span data-stu-id="b93e6-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="b93e6-108">A livello di alto livello, ecco come Advanced eDiscovery supporta il flusso di lavoro EDRM:</span><span class="sxs-lookup"><span data-stu-id="b93e6-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="b93e6-109">**Identificazione.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-109">**Identification.**</span></span> <span data-ttu-id="b93e6-110">Dopo aver identificato le potenziali persone di interesse per un'indagine, è possibile aggiungerle come responsabili (detti anche responsabili dei dati *,* perché potrebbero disporre di informazioni rilevanti per l'indagine) a un caso advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b93e6-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="b93e6-111">Dopo l'aggiunta degli utenti come custodi, è facile conservare, raccogliere ed esaminare i documenti depositario.</span><span class="sxs-lookup"><span data-stu-id="b93e6-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="b93e6-112">**Conservazione.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-112">**Preservation.**</span></span> <span data-ttu-id="b93e6-113">Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di conservare legalmente le origini dati associate ai custodi in un caso.</span><span class="sxs-lookup"><span data-stu-id="b93e6-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="b93e6-114">È inoltre possibile mettere in attesa i dati non depositario.</span><span class="sxs-lookup"><span data-stu-id="b93e6-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="b93e6-115">Advanced eDiscovery include anche un flusso di lavoro integrato per le comunicazioni, in modo da poter inviare notifiche di blocco legale ai custodi e tenere traccia dei loro riconoscimenti.</span><span class="sxs-lookup"><span data-stu-id="b93e6-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="b93e6-116">**Insieme.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-116">**Collection.**</span></span> <span data-ttu-id="b93e6-117">Dopo aver identificato (e conservato) le origini dati rilevanti per l'indagine, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery per cercare e raccogliere dati in tempo reale dalle origini dati di custodia (e da origini dati non depositate, se applicabile) che potrebbero essere rilevanti per il caso.</span><span class="sxs-lookup"><span data-stu-id="b93e6-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="b93e6-118">**Elaborazione.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-118">**Processing.**</span></span> <span data-ttu-id="b93e6-119">Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nell'elaborarlo per un'ulteriore revisione e analisi.</span><span class="sxs-lookup"><span data-stu-id="b93e6-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="b93e6-120">In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set* di revisione), che fornisce una visualizzazione statica dei dati del caso.</span><span class="sxs-lookup"><span data-stu-id="b93e6-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="b93e6-121">**Revisione.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-121">**Review.**</span></span> <span data-ttu-id="b93e6-122">Dopo aver aggiunto i dati a un set di revisioni, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più rilevante per il caso.</span><span class="sxs-lookup"><span data-stu-id="b93e6-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="b93e6-123">Inoltre, è possibile aggiungere annotazioni e contrassegnare documenti specifici.</span><span class="sxs-lookup"><span data-stu-id="b93e6-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="b93e6-124">**Analisi.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-124">**Analysis.**</span></span> <span data-ttu-id="b93e6-125">Advanced eDiscovery offre uno strumento di analisi integrato che consente di aggiungere ulteriori dati dal set di revisione che si determina non è rilevante per l'indagine.</span><span class="sxs-lookup"><span data-stu-id="b93e6-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="b93e6-126">Oltre a ridurre il volume di dati rilevanti, Advance eDiscovery consente inoltre di risparmiare sui costi di revisione legale consentendo di organizzare il contenuto per semplificare ed efficienza il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="b93e6-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="b93e6-127">**Produzione** e **presentazione.**</span><span class="sxs-lookup"><span data-stu-id="b93e6-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="b93e6-128">Quando si è pronti, è possibile esportare i documenti da un set di recensioni per la revisione legale.</span><span class="sxs-lookup"><span data-stu-id="b93e6-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="b93e6-129">È possibile esportare i documenti nel formato nativo o in un formato specificato da EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b93e6-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="b93e6-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b93e6-130">More information</span></span>

<span data-ttu-id="b93e6-131">Per iniziare a usare Advanced eDiscovery, vedere:</span><span class="sxs-lookup"><span data-stu-id="b93e6-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="b93e6-132">Configurare Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b93e6-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="b93e6-133">Creare e gestire un caso advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b93e6-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)