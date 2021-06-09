---
title: Usare Office 365 rete per la distribuzione di contenuti (rete CDN) con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Scopri come usare il Office 365 rete per la distribuzione di contenuti (rete CDN) per velocizzare la distribuzione delle risorse SharePoint Online.
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570406"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="4d9e3-103">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="4d9e3-104">È possibile usare la rete per la distribuzione di contenuti di Office 365 predefinita per ospitare risorse statiche e migliorare le prestazioni delle pagine di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="4d9e3-105">La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="4d9e3-106">Inoltre, il Office 365 rete CDN utilizza il [protocollo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e il pipelining HTTP.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="4d9e3-107">Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-108">Il Office 365 rete CDN è disponibile solo per i tenant **nel** cloud di produzione (globale).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="4d9e3-109">I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="4d9e3-110">La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="4d9e3-111">In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="4d9e3-112">Per ulteriori informazioni sulla differenza tra origini pubbliche e [private,](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) vedere Scegliere se ogni origine deve essere pubblica o privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="4d9e3-113">![Office 365 rete CDN concettuale](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 rete CDN concettuale")</span><span class="sxs-lookup"><span data-stu-id="4d9e3-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="4d9e3-114">Se si ha già familiarità con il funzionamento delle reti CDN, è necessario eseguire solo alcuni passaggi per abilitare il Office 365 rete CDN per il tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="4d9e3-115">In questo argomento viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-115">This topic describes how.</span></span> <span data-ttu-id="4d9e3-116">Continua a leggere per informazioni su come iniziare a ospitare gli asset statici.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-117">Esistono altre reti CDN ospitate da Microsoft che possono essere usate con Office 365 per scenari di utilizzo specializzati, ma non sono descritte in questo argomento perché non rientrano nell'ambito del Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-118">Per ulteriori informazioni, vedere [Other Microsoft CDN](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="4d9e3-119">**Tornare a [Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](./network-planning-and-performance.md).**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="4d9e3-120">Panoramica dell'utilizzo del Office 365 rete CDN in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="4d9e3-121">Per configurare il Office 365 rete CDN per l'organizzazione, attenersi alla seguente procedura di base:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="4d9e3-122">Pianificare la distribuzione del Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="4d9e3-123">[Determinare quali asset statici si desidera ospitare nell'rete CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="4d9e3-124">[Determinare dove archiviare gli asset.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="4d9e3-125">Questo percorso può essere un SharePoint, una raccolta o una cartella ed è denominato _origine._</span><span class="sxs-lookup"><span data-stu-id="4d9e3-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="4d9e3-126">[Scegliere se ogni origine deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="4d9e3-127">È possibile aggiungere più origini di tipi pubblici e privati.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="4d9e3-128">Configurare e configurare il rete CDN tramite PowerShell o l'interfaccia SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="4d9e3-129">Configurare e configurare il rete CDN tramite SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="4d9e3-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="4d9e3-130">Configurare e configurare la rete CDN tramite PowerShell PnP</span><span class="sxs-lookup"><span data-stu-id="4d9e3-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="4d9e3-131">Configurare e configurare il rete CDN tramite l'interfaccia Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="4d9e3-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="4d9e3-132">Al termine di questo passaggio, si avranno:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="4d9e3-133">Abilitato il rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="4d9e3-134">Sono state aggiunte le origini, identificando ogni origine come pubblica o privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="4d9e3-135">Al termine dell'installazione, è [possibile](use-microsoft-365-cdn-with-spo.md#CDNManage) gestire l'Office 365 rete CDN nel tempo:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="4d9e3-136">Aggiunta, aggiornamento e rimozione di asset</span><span class="sxs-lookup"><span data-stu-id="4d9e3-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="4d9e3-137">Aggiunta e rimozione di origini</span><span class="sxs-lookup"><span data-stu-id="4d9e3-137">Adding and removing origins</span></span>
+ <span data-ttu-id="4d9e3-138">Configurazione di rete CDN criteri</span><span class="sxs-lookup"><span data-stu-id="4d9e3-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="4d9e3-139">Se necessario, disabilitare il rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="4d9e3-140">Infine, vedi [Uso delle risorse rete CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) per informazioni sull'accesso alle risorse rete CDN da origini pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="4d9e3-141">Vedi [Risoluzione dei Office 365 rete CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) per indicazioni sulla risoluzione dei problemi comuni.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="4d9e3-142">Pianificare la distribuzione del Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-143">Prima di distribuire il Office 365 rete CDN per il tenant Office 365, è necessario considerare i fattori seguenti come parte del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="4d9e3-144">Determinare quali asset statici si desidera ospitare nel rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="4d9e3-145">Determinare dove archiviare gli asset</span><span class="sxs-lookup"><span data-stu-id="4d9e3-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="4d9e3-146">Scegliere se ogni origine deve essere pubblica o privata</span><span class="sxs-lookup"><span data-stu-id="4d9e3-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="4d9e3-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="4d9e3-148">Determinare quali asset statici si desidera ospitare nel rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="4d9e3-149">In generale, le reti CDN sono più efficaci per ospitare asset _statici_ o asset che non cambiano molto spesso.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="4d9e3-150">Una buona regola generale è identificare i file che soddisfano alcune o tutte queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="4d9e3-151">File statici incorporati in una pagina (ad esempio script e immagini) che possono avere un impatto incrementale significativo sui tempi di caricamento delle pagine</span><span class="sxs-lookup"><span data-stu-id="4d9e3-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="4d9e3-152">File di grandi dimensioni come file eseguibili e file di installazione</span><span class="sxs-lookup"><span data-stu-id="4d9e3-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="4d9e3-153">Librerie di risorse che supportano il codice sul lato client</span><span class="sxs-lookup"><span data-stu-id="4d9e3-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="4d9e3-154">Ad esempio, file di piccole dimensioni che vengono ripetutamente richiesti come immagini e script del sito possono migliorare in modo significativo le prestazioni di rendering del sito e ridurre in modo incrementale il carico sui siti di SharePoint Online quando vengono aggiunti a un'origine rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="4d9e3-155">I file di dimensioni maggiori, ad esempio i file eseguibili di installazione, possono essere scaricati dal rete CDN, offrendo un impatto positivo sulle prestazioni e una conseguente riduzione del carico sul sito di SharePoint Online, anche se non vi si accede con la frequenza più frequente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="4d9e3-156">Il miglioramento delle prestazioni in base al file dipende da molti fattori, tra cui la prossimità del client all'endpoint rete CDN più vicino, le condizioni temporanee sulla rete locale e così via.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="4d9e3-157">Molti file statici sono piuttosto piccoli e possono essere scaricati da Office 365 in meno di un secondo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="4d9e3-158">Tuttavia, una pagina Web può contenere molti file incorporati con un tempo di download cumulativo di diversi secondi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="4d9e3-159">La pubblicazione di questi file dal rete CDN può ridurre in modo significativo il tempo di caricamento complessivo delle pagine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="4d9e3-160">Per [un esempio, vedere](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Quali vantaggi rete CDN prestazioni?</span><span class="sxs-lookup"><span data-stu-id="4d9e3-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="4d9e3-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="4d9e3-162">Determinare dove archiviare gli asset</span><span class="sxs-lookup"><span data-stu-id="4d9e3-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="4d9e3-163">Il rete CDN recupera gli asset da una posizione denominata _origine._</span><span class="sxs-lookup"><span data-stu-id="4d9e3-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="4d9e3-164">Un'origine può essere un SharePoint, una raccolta documenti o una cartella accessibile da un URL.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="4d9e3-165">Si ha una grande flessibilità quando si specificano le origini per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="4d9e3-166">Ad esempio, è possibile specificare più origini o una singola origine in cui si desidera inserire tutti i rete CDN risorse.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="4d9e3-167">È possibile scegliere di avere origini pubbliche o private per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="4d9e3-168">La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="4d9e3-169">È possibile creare un nuovo contenitore per le origini, ad esempio cartelle o raccolte documenti, e aggiungere file che si desidera rendere disponibili dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="4d9e3-170">Si tratta di un buon approccio se si dispone di un set specifico di risorse che si desidera essere disponibili da rete CDN e si desidera limitare il set di asset di rete CDN solo a tali file nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="4d9e3-171">È inoltre possibile configurare una raccolta siti, un sito, una raccolta o una cartella esistente come origine, in modo da rendere disponibili dal rete CDN tutte le risorse idonee nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="4d9e3-172">Prima di aggiungere un contenitore esistente come origine, è importante assicurarsi di conoscerne il contenuto e le autorizzazioni, in modo da non esporre inavvertitamente le risorse agli utenti non autorizzati o agli accessi anonimi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="4d9e3-173">È possibile definire _rete CDN criteri_ per escludere il contenuto nelle origini dall'rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="4d9e3-174">i criteri di rete CDN escludono gli asset nelle origini pubbliche o private in base ad attributi quali il tipo di _file_ e la classificazione del sito e vengono applicati a tutte le origini del CdnType (privato o pubblico) specificato nel criterio.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="4d9e3-175">Ad esempio, se si aggiunge un'origine privata costituita da un sito che contiene più  siti secondari, è possibile definire un criterio per escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti con tale classificazione applicata non sia servito dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="4d9e3-176">Il criterio verrà applicato al contenuto _di_ tutte le origini private aggiunte alla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="4d9e3-177">Tenere presente che maggiore è il numero di origini, maggiore sarà l'impatto sul tempo necessario al servizio rete CDN per elaborare le richieste.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="4d9e3-178">Ti consigliamo di limitare il più possibile il numero di origini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="4d9e3-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="4d9e3-180">Scegliere se ogni origine deve essere pubblica o privata</span><span class="sxs-lookup"><span data-stu-id="4d9e3-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="4d9e3-181">Quando si identifica un'origine, è necessario specificare se deve essere resa _pubblica_ o _privata._</span><span class="sxs-lookup"><span data-stu-id="4d9e3-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="4d9e3-182">L'accesso rete CDN risorse in origini pubbliche è anonimo e rete CDN contenuto in origini private è protetto da token generati dinamicamente per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="4d9e3-183">Indipendentemente dall'opzione scelta, Microsoft fa tutto il lavoro pesante per l'utente quando si tratta di amministrazione del rete CDN stesso.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="4d9e3-184">Inoltre, puoi cambiare idea in un secondo momento, dopo aver configurato il rete CDN e identificato le origini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="4d9e3-185">Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna ha attributi e vantaggi univoci.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="4d9e3-186">**Le** origini pubbliche all'interno Office 365 rete CDN sono accessibili in modo anonimo e gli asset ospitati sono accessibili da chiunque abbia l'URL dell'asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="4d9e3-187">Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="4d9e3-188">**Le** origini private all'interno Office 365 rete CDN l'accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="4d9e3-189">L'accesso al contenuto in origini private è protetto da token generati dinamicamente in modo che sia accessibile solo agli utenti con autorizzazioni per la raccolta documenti originale o il percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="4d9e3-190">Le origini private nell'Office 365 rete CDN possono essere usate solo per il contenuto di SharePoint Online ed è possibile accedere solo alle risorse di origini private tramite il reindirizzamento dal tenant di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="4d9e3-191">Per altre informazioni sul funzionamento rete CDN'accesso alle risorse in un'origine privata, vedere [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="4d9e3-192">Attributi e vantaggi dell'hosting di asset in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="4d9e3-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="4d9e3-193">Gli asset esposti in un'origine pubblica sono accessibili da tutti in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="4d9e3-194">Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="4d9e3-195">Se si rimuove un asset da un'origine pubblica, l'asset potrebbe continuare a essere disponibile per un massimo di 30 giorni dalla cache. Tuttavia, verranno invalidati i collegamenti all'asset nel rete CDN entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="4d9e3-196">Quando si ospitano fogli di stile (file CSS) in un'origine pubblica, è possibile utilizzare percorsi relativi e URI all'interno del codice.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="4d9e3-197">Ciò significa che puoi fare riferimento alla posizione delle immagini di sfondo e di altri oggetti rispetto alla posizione dell'asset che la chiama.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="4d9e3-198">Sebbene sia possibile creare l'URL di un'origine pubblica, è consigliabile procedere con cautela e assicurarsi di utilizzare la proprietà di contesto della pagina e seguire le indicazioni per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="4d9e3-199">Il motivo è che se l'accesso al rete CDN diventa non disponibile, l'URL non verrà risolto automaticamente nell'organizzazione in SharePoint Online e potrebbe causare collegamenti interrotti e altri errori.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="4d9e3-200">L'URL è inoltre soggetto a modifiche, motivo per cui non deve essere codificato solo a livello di codice in base al valore corrente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="4d9e3-201">I tipi di file predefiniti inclusi per le origini pubbliche sono .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="4d9e3-202">È possibile specificare tipi di file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="4d9e3-203">È possibile configurare un criterio per escludere gli asset identificati dalle classificazioni del sito specificate.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="4d9e3-204">Ad esempio, è possibile scegliere di escludere tutti gli asset contrassegnati come "riservati" o "limitati" anche se sono un tipo di file consentito e si trovano in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="4d9e3-205">Attributi e vantaggi dell'hosting di asset in origini private</span><span class="sxs-lookup"><span data-stu-id="4d9e3-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="4d9e3-206">Le origini private possono essere utilizzate solo per SharePoint online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="4d9e3-207">Gli utenti possono accedere agli asset da un'origine privata solo se dispongono delle autorizzazioni per accedere al contenitore.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="4d9e3-208">L'accesso anonimo a questi asset non è consentito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="4d9e3-209">Gli asset di origini private devono essere indicati dal tenant SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="4d9e3-210">L'accesso diretto alle rete CDN private non funziona.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="4d9e3-211">Se si rimuove un asset dall'origine privata, l'asset potrebbe continuare a essere disponibile fino a un'ora dalla cache. tuttavia, verranno invalidati i collegamenti all'asset nel rete CDN entro 15 minuti dalla rimozione dell'asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="4d9e3-212">I tipi di file predefiniti inclusi per le origini private sono .gif, ico, jpeg, .jpg, .js e .png.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="4d9e3-213">È possibile specificare tipi di file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="4d9e3-214">Analogamente alle origini pubbliche, è possibile configurare un criterio per escludere le risorse identificate dalle classificazioni dei siti specificate anche se si utilizzano caratteri jolly per includere tutte le risorse all'interno di una cartella o di una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="4d9e3-215">Per ulteriori informazioni sul motivo per cui usare i concetti Office 365 rete CDN, generici rete CDN e altre reti CDN Microsoft che è possibile usare con il tenant di Office 365, vedere [Content Delivery Networks](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="4d9e3-216">Origini rete CDN predefinite</span><span class="sxs-lookup"><span data-stu-id="4d9e3-216">Default CDN origins</span></span>

<span data-ttu-id="4d9e3-217">Se non diversamente specificato, Office 365 alcune origini predefinite quando abiliti il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-218">Se inizialmente scegli di non effettuare il provisioning, puoi aggiungere queste origini dopo aver completato l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="4d9e3-219">A meno che non si comprenda le conseguenze di ignorare la configurazione delle origini predefinite e di avere un motivo specifico per farlo, è consigliabile consentirne la creazione quando si abilita il rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="4d9e3-220">Origini rete CDN predefinite:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="4d9e3-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="4d9e3-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="4d9e3-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="4d9e3-222">\*/siteassets</span></span>

<span data-ttu-id="4d9e3-223">Origini rete CDN predefinite:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="4d9e3-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="4d9e3-224">\*/masterpage</span></span>
+ <span data-ttu-id="4d9e3-225">\*/style library</span><span class="sxs-lookup"><span data-stu-id="4d9e3-225">\*/style library</span></span>
+ <span data-ttu-id="4d9e3-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="4d9e3-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-227">_clientsideassets_ è un'origine pubblica predefinita aggiunta al servizio Office 365 rete CDN nel mese di dicembre 2017.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="4d9e3-228">Questa origine deve essere presente perché SharePoint Framework soluzioni nel rete CDN funzionino.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="4d9e3-229">Se il Office 365 rete CDN è stato abilitato prima di dicembre 2017 o se è stata ignorata la configurazione delle origini predefinite quando è stato abilitato il rete CDN, è possibile aggiungere manualmente questa origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="4d9e3-230">Per ulteriori informazioni, vedere [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="4d9e3-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="4d9e3-232">Configurare e configurare il Office 365 rete CDN tramite SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="4d9e3-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="4d9e3-233">Le procedure descritte in questa sezione richiedono l'utilizzo di SharePoint Online Management Shell per connettersi a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="4d9e3-234">Per istruzioni, [vedere Connessione to SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="4d9e3-235">Completare questi passaggi per configurare il rete CDN per ospitare gli asset in SharePoint Online tramite SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="4d9e3-236">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="4d9e3-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="4d9e3-237">Consentire all'organizzazione di utilizzare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-238">Prima di apportare modifiche alle impostazioni rete CDN tenant, è necessario recuperare lo stato corrente della configurazione rete CDN privata nel tenant Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="4d9e3-239">Connessione al tenant tramite SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="4d9e3-240">A questo punto, utilizzare il cmdlet **Get-SPOTenantCdnEnabled** per recuperare le impostazioni rete CDN stato del tenant:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-241">Lo stato del rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="4d9e3-242">Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per consentire all'organizzazione di utilizzare il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-243">È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="4d9e3-244">Puoi anche configurare il rete CDN per ignorare l'impostazione delle origini predefinite quando lo abiliti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="4d9e3-245">È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="4d9e3-246">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="4d9e3-247">Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="4d9e3-248">Per consentire all'organizzazione di utilizzare sia origini pubbliche che private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="4d9e3-249">Vedere [Origini](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) rete CDN predefinite per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita il Office 365 rete CDN e sull'impatto potenziale di ignorare la configurazione delle origini predefinite.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="4d9e3-250">Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="4d9e3-251">Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="4d9e3-252">Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="4d9e3-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="4d9e3-254">Modificare l'elenco dei tipi di file da includere nel Office 365 rete CDN (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-255">Quando si definiscono i tipi di file utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-256">Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="4d9e3-257">Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="4d9e3-258">Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="4d9e3-259">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="4d9e3-260">Ad esempio, per abilitare il rete CDN per ospitare i file css e .png, immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="4d9e3-261">Per sapere quali tipi di file sono attualmente consentiti dal rete CDN, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-262">Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="4d9e3-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="4d9e3-264">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dal Office 365 rete CDN (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-265">Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-266">Se si desidera escludere classificazioni di siti aggiuntive, utilizzare innanzitutto il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme a quelle nuove.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="4d9e3-267">Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili nel rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="4d9e3-268">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="4d9e3-269">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="4d9e3-270">Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-271">Le proprietà che verranno restituite sono _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="4d9e3-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="4d9e3-272">La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dall'rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-273">Le estensioni di file predefinite sono diverse tra pubblico e privato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="4d9e3-274">La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="4d9e3-275">Ad esempio, è possibile  escludere i siti contrassegnati come Riservato in modo che il contenuto dei siti con tale classificazione applicata non sia servito dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="4d9e3-276">La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dall'rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="4d9e3-277">Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni e **Disabilitato per** _i siti_ classici.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="4d9e3-278">Dipende dalle impostazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="4d9e3-279">Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="4d9e3-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="4d9e3-281">Aggiungere un'origine per le risorse</span><span class="sxs-lookup"><span data-stu-id="4d9e3-281">Add an origin for your assets</span></span>

<span data-ttu-id="4d9e3-282">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire un'origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="4d9e3-283">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-283">You can define multiple origins.</span></span> <span data-ttu-id="4d9e3-284">L'origine è un URL che punta a una raccolta SharePoint o a una cartella che contiene gli asset che si desidera ospitare dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d9e3-285">Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="4d9e3-286">Il valore _di path_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="4d9e3-287">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="4d9e3-288">Origins supporta i caratteri jolly anteposti all'URL.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="4d9e3-289">In questo modo è possibile creare origini che si estendono su più siti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="4d9e3-290">Ad esempio, per includere tutti gli asset nella cartella masterpages per tutti i siti come origine pubblica all'interno del rete CDN, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="4d9e3-291">Il modificatore con caratteri jolly \* può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i segmenti **/** di URL nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="4d9e3-292">Il percorso può puntare a una raccolta documenti, una cartella o un sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="4d9e3-293">Ad esempio, il percorso _\*/site1_ corrisponderà a tutte le raccolte documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="4d9e3-294">È possibile aggiungere un'origine con un percorso relativo specifico.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="4d9e3-295">Non è possibile aggiungere un'origine utilizzando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="4d9e3-296">In questo esempio viene aggiunta un'origine privata della raccolta siti in un sito specifico:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="4d9e3-297">In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta risorse sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="4d9e3-298">Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="4d9e3-299">Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta risorse sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="4d9e3-300">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-301">Nelle origini private, gli asset condivisi da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="4d9e3-302">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-303">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="4d9e3-305">Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="4d9e3-306">In genere, queste origini vengono impostate automaticamente quando si abilita il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-307">Tuttavia, se si desidera abilitarli manualmente, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="4d9e3-308">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la libreria di stili come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="4d9e3-309">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire le pagine master come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="4d9e3-310">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="4d9e3-311">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-312">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="4d9e3-314">Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="4d9e3-315">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="4d9e3-316">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="4d9e3-317">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="4d9e3-318">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="4d9e3-319">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-320">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="4d9e3-322">Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="4d9e3-323">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire una raccolta siti come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="4d9e3-324">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="4d9e3-325">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="4d9e3-326">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-327">È possibile che venga visualizzato _un messaggio_ di configurazione in sospeso previsto quando il tenant di SharePoint Online si connette al servizio rete CDN online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="4d9e3-328">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="4d9e3-330">Gestire il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-331">Dopo aver configurato il rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="4d9e3-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="4d9e3-333">Aggiungere, aggiornare o rimuovere asset dalla Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-334">Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere gli asset esistenti quando vuoi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="4d9e3-335">Basta apportare le modifiche alle risorse nella cartella o SharePoint raccolta identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="4d9e3-336">Se aggiungi una nuova risorsa, questa sarà disponibile tramite il rete CDN immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="4d9e3-337">Tuttavia, se aggiorni l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nel rete CDN saranno fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="4d9e3-338">Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="4d9e3-339">Per informazioni su come utilizzare questo cmdlet, vedere [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="4d9e3-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="4d9e3-341">Rimuovere un'origine dal Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-342">È possibile rimuovere l'accesso a una cartella o SharePoint raccolta identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="4d9e3-343">A tale scopo, utilizzare il cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="4d9e3-344">Per informazioni su come utilizzare questo cmdlet, [vedere Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="4d9e3-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="4d9e3-346">Modificare un'origine nel Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-347">Non è possibile modificare un'origine creata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="4d9e3-348">Rimuovi invece l'origine e quindi aggiungine una nuova.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="4d9e3-349">Per ulteriori informazioni, vedere [To remove an origin from the Office 365 rete CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and To add an origin for your [assets.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="4d9e3-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="4d9e3-351">Disabilitare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-352">Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per disabilitare il rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="4d9e3-353">Se sono abilitate sia le origini pubbliche che private per il rete CDN, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="4d9e3-354">Per disabilitare l'uso di origini pubbliche nel rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="4d9e3-355">Per disabilitare l'uso delle origini private nel rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="4d9e3-356">Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="4d9e3-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="4d9e3-358">Configurare e configurare la Office 365 rete CDN tramite PowerShell PnP</span><span class="sxs-lookup"><span data-stu-id="4d9e3-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="4d9e3-359">Le procedure descritte in questa sezione richiedono l'utilizzo di PowerShell PnP per connettersi a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="4d9e3-360">Per istruzioni, vedere [Introduzione a PowerShell PnP.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="4d9e3-361">Completare questi passaggi per configurare il rete CDN per ospitare gli asset in SharePoint Online tramite PowerShell PnP.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="4d9e3-362">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="4d9e3-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="4d9e3-363">Consentire all'organizzazione di utilizzare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-364">Prima di apportare modifiche alle impostazioni rete CDN tenant, è necessario recuperare lo stato corrente della configurazione rete CDN privata nel tenant Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="4d9e3-365">Connessione al tenant tramite PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="4d9e3-366">A questo punto, utilizzare il cmdlet **Get-PnPTenantCdnEnabled** per recuperare le impostazioni rete CDN stato del tenant:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-367">Lo stato del rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="4d9e3-368">Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per consentire all'organizzazione di utilizzare il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-369">È possibile consentire all'organizzazione di utilizzare origini pubbliche, origini private o entrambe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="4d9e3-370">Puoi anche configurare il rete CDN per ignorare l'impostazione delle origini predefinite quando lo abiliti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="4d9e3-371">È sempre possibile aggiungere queste origini in un secondo momento, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="4d9e3-372">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="4d9e3-373">Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="4d9e3-374">Per consentire all'organizzazione di utilizzare sia origini pubbliche che private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="4d9e3-375">Vedere [Origini](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) rete CDN predefinite per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita il Office 365 rete CDN e sull'impatto potenziale di ignorare la configurazione delle origini predefinite.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="4d9e3-376">Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="4d9e3-377">Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="4d9e3-378">Per ulteriori informazioni su questo cmdlet, [vedere Set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="4d9e3-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="4d9e3-380">Modificare l'elenco dei tipi di file da includere nel Office 365 rete CDN (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-381">Quando si definiscono i tipi di file utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-382">Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="4d9e3-383">Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nel rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="4d9e3-384">Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="4d9e3-385">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="4d9e3-386">Ad esempio, per abilitare il rete CDN per ospitare i file css e .png, immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="4d9e3-387">Per sapere quali tipi di file sono attualmente consentiti dal rete CDN, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-388">Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="4d9e3-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="4d9e3-390">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dal Office 365 rete CDN (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-391">Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-392">Se si desidera escludere classificazioni di siti aggiuntive, utilizzare innanzitutto il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme a quelle nuove.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="4d9e3-393">Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili nel rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="4d9e3-394">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="4d9e3-395">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="4d9e3-396">Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="4d9e3-397">Le proprietà che verranno restituite sono _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="4d9e3-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="4d9e3-398">La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dall'rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-399">Le estensioni di file predefinite sono diverse tra pubblico e privato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="4d9e3-400">La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="4d9e3-401">Ad esempio, è possibile  escludere i siti contrassegnati come Riservato in modo che il contenuto dei siti con tale classificazione applicata non sia servito dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="4d9e3-402">La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dall'rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="4d9e3-403">Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni e **Disabilitato per** _i siti_ classici.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="4d9e3-404">Dipende dalle impostazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="4d9e3-405">Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="4d9e3-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="4d9e3-407">Aggiungere un'origine per le risorse</span><span class="sxs-lookup"><span data-stu-id="4d9e3-407">Add an origin for your assets</span></span>

<span data-ttu-id="4d9e3-408">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire un'origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="4d9e3-409">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-409">You can define multiple origins.</span></span> <span data-ttu-id="4d9e3-410">L'origine è un URL che punta a una raccolta SharePoint o a una cartella che contiene gli asset che si desidera ospitare dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d9e3-411">Non inserire mai risorse che contengono informazioni sugli utenti o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="4d9e3-412">Il valore _di path_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="4d9e3-413">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="4d9e3-414">Origins supporta i caratteri jolly anteposti all'URL.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="4d9e3-415">In questo modo è possibile creare origini che si estendono su più siti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="4d9e3-416">Ad esempio, per includere tutti gli asset nella cartella masterpages per tutti i siti come origine pubblica all'interno del rete CDN, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="4d9e3-417">Il modificatore con caratteri jolly \* può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i segmenti **/** di URL nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="4d9e3-418">Il percorso può puntare a una raccolta documenti, una cartella o un sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="4d9e3-419">Ad esempio, il percorso _\*/site1_ corrisponderà a tutte le raccolte documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="4d9e3-420">È possibile aggiungere un'origine con un percorso relativo specifico.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="4d9e3-421">Non è possibile aggiungere un'origine utilizzando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="4d9e3-422">In questo esempio viene aggiunta un'origine privata della raccolta di risorse del sito in un sito specifico:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="4d9e3-423">In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta risorse sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="4d9e3-424">Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="4d9e3-425">Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta risorse sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="4d9e3-426">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-427">Nelle origini private, gli asset condivisi da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="4d9e3-428">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-429">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="4d9e3-431">Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="4d9e3-432">In genere, queste origini vengono impostate automaticamente quando si abilita il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="4d9e3-433">Tuttavia, se si desidera abilitarli manualmente, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="4d9e3-434">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la libreria di stili come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="4d9e3-435">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire le pagine master come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="4d9e3-436">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="4d9e3-437">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-438">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="4d9e3-440">Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="4d9e3-441">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="4d9e3-442">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="4d9e3-443">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="4d9e3-444">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="4d9e3-445">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-446">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="4d9e3-448">Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="4d9e3-449">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire una raccolta siti come origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="4d9e3-450">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="4d9e3-451">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="4d9e3-452">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="4d9e3-453">È possibile che venga visualizzato _un messaggio_ di configurazione in sospeso previsto quando il tenant di SharePoint Online si connette al servizio rete CDN online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="4d9e3-454">L'operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="4d9e3-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="4d9e3-456">Gestire il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-457">Dopo aver configurato il rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="4d9e3-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="4d9e3-459">Aggiungere, aggiornare o rimuovere asset dalla Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-460">Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere gli asset esistenti quando vuoi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="4d9e3-461">Basta apportare le modifiche alle risorse nella cartella o SharePoint raccolta identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="4d9e3-462">Se aggiungi una nuova risorsa, questa sarà disponibile tramite il rete CDN immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="4d9e3-463">Tuttavia, se aggiorni l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nel rete CDN saranno fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="4d9e3-464">Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="4d9e3-465">Per informazioni su come utilizzare questo cmdlet, vedere [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="4d9e3-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="4d9e3-467">Rimuovere un'origine dal Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-468">È possibile rimuovere l'accesso a una cartella o SharePoint raccolta identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="4d9e3-469">A tale scopo, utilizzare il cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="4d9e3-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="4d9e3-470">Per informazioni su come utilizzare questo cmdlet, [vedere Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="4d9e3-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="4d9e3-472">Modificare un'origine nel Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-473">Non è possibile modificare un'origine creata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="4d9e3-474">Rimuovi invece l'origine e quindi aggiungine una nuova.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="4d9e3-475">Per ulteriori informazioni, vedere [To remove an origin from the Office 365 rete CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and To add an origin for your [assets.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="4d9e3-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="4d9e3-477">Disabilitare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-478">Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per disabilitare il rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="4d9e3-479">Se sono abilitate sia le origini pubbliche che private per il rete CDN, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="4d9e3-480">Per disabilitare l'uso di origini pubbliche nel rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="4d9e3-481">Per disabilitare l'uso delle origini private nel rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="4d9e3-482">Per ulteriori informazioni su questo cmdlet, [vedere Set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="4d9e3-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="4d9e3-484">Configurare e configurare l'Office 365 rete CDN tramite l'interfaccia Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="4d9e3-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="4d9e3-485">Le procedure descritte in questa sezione richiedono l'installazione [dell'Office 365 CLI.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="4d9e3-486">Successivamente, connettersi al tenant Office 365 usando il comando [di](https://pnp.github.io/office365-cli/cmd/login/) accesso.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="4d9e3-487">Completare questi passaggi per configurare il rete CDN per ospitare gli asset in SharePoint Online tramite l'interfaccia Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="4d9e3-488">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="4d9e3-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="4d9e3-489">Abilitare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-490">Puoi gestire lo stato dell'Office 365 rete CDN nel tenant usando il comando [spo cdn set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="4d9e3-491">Per abilitare la Office 365 pubblica rete CDN nel tenant eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="4d9e3-492">Per abilitare il Office 365 SharePoint rete CDN, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="4d9e3-493">Visualizzare lo stato corrente del Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-494">Per verificare se il particolare tipo di Office 365 rete CDN è abilitato o disabilitato, utilizzare il comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="4d9e3-495">Per verificare se il Office 365 public rete CDN è abilitato, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="4d9e3-496">Visualizzare le Office 365 rete CDN di origine</span><span class="sxs-lookup"><span data-stu-id="4d9e3-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="4d9e3-497">Per visualizzare l'origine Office 365 di rete CDN pubblica attualmente configurata:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="4d9e3-498">Vedere [Origini rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinite per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita il Office 365 rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="4d9e3-499">Aggiungere un'Office 365 rete CDN origine</span><span class="sxs-lookup"><span data-stu-id="4d9e3-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d9e3-500">Non inserire mai risorse considerate riservate all'organizzazione in una raccolta SharePoint documenti configurata come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="4d9e3-501">Utilizzare il [comando spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) per definire un'rete CDN origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="4d9e3-502">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-502">You can define multiple origins.</span></span> <span data-ttu-id="4d9e3-503">L'origine è un URL che punta a una raccolta SharePoint o a una cartella che contiene gli asset che si desidera ospitare dal rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="4d9e3-504">Dove `path` è il percorso relativo della cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="4d9e3-505">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="4d9e3-506">Per includere tutti gli asset nella raccolta **pagine master** di tutti i siti come origine pubblica, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="4d9e3-507">Per configurare un'origine privata per una raccolta siti specifica, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="4d9e3-508">Dopo aver aggiunto rete CDN origine, potrebbero essere necessari fino a 15 minuti per poter recuperare i file tramite il servizio rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="4d9e3-509">È possibile verificare se la determinata origine è già stata abilitata utilizzando il comando [spo cdn origin list.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="4d9e3-510">Rimuovere un'Office 365 rete CDN origine</span><span class="sxs-lookup"><span data-stu-id="4d9e3-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="4d9e3-511">Utilizzare il [comando spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) per rimuovere un'origine rete CDN per il tipo di rete CDN specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="4d9e3-512">Per rimuovere un'origine pubblica dalla rete CDN, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="4d9e3-513">La rimozione di rete CDN'origine non influisce sui file archiviati in alcuna raccolta documenti corrispondente a tale origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="4d9e3-514">Se a queste risorse è stato fatto riferimento utilizzando il relativo URL SharePoint, SharePoint automaticamente torna all'URL originale che punta alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="4d9e3-515">Se, tuttavia, è stato fatto riferimento agli asset utilizzando un URL rete CDN pubblico, la rimozione dell'origine interromperà il collegamento e sarà necessario modificarli manualmente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="4d9e3-516">Modificare un'Office 365 rete CDN origine</span><span class="sxs-lookup"><span data-stu-id="4d9e3-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="4d9e3-517">Non è possibile modificare un'origine rete CDN esistente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="4d9e3-518">Devi invece rimuovere l'origine rete CDN definita in precedenza usando il comando e aggiungerne una `spo cdn origin remove` nuova usando il `spo cdn origin add` comando.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="4d9e3-519">Modificare i tipi di file da includere nella Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-520">Per impostazione predefinita, nel rete CDN sono inclusi i seguenti tipi di file: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2_.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="4d9e3-521">Se è necessario includere tipi di file aggiuntivi nel rete CDN, è possibile modificare la configurazione rete CDN utilizzando il comando [spo cdn policy set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-522">Quando si modifica l'elenco dei tipi di file, si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-523">Se si desidera includere tipi di file aggiuntivi, utilizzare innanzitutto il comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) per individuare i tipi di file attualmente configurati.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="4d9e3-524">Per aggiungere il tipo di file _JSON_ all'elenco predefinito dei tipi di file inclusi nel rete CDN pubblico, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="4d9e3-525">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dal Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-526">Utilizzare il [comando spo cdn policy set per](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) escludere le classificazioni dei siti che non si desidera rendere disponibili nel rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="4d9e3-527">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-528">Quando si modifica l'elenco delle classificazioni dei siti escluse, si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="4d9e3-529">Se si desidera escludere classificazioni aggiuntive, utilizzare innanzitutto il comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) per individuare le classificazioni attualmente configurate.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="4d9e3-530">Per escludere i siti _classificati come HBI_ dalla rete CDN pubblica, eseguire</span><span class="sxs-lookup"><span data-stu-id="4d9e3-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="4d9e3-531">Disabilitare il Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-532">Per disabilitare il Office 365 rete CDN utilizzare `spo cdn set` il comando, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="4d9e3-533">Uso delle rete CDN di lavoro</span><span class="sxs-lookup"><span data-stu-id="4d9e3-533">Using your CDN assets</span></span>

<span data-ttu-id="4d9e3-534">Dopo aver abilitato l'rete CDN e configurato origini e criteri, puoi iniziare a usare le risorse rete CDN esistenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="4d9e3-535">Questa sezione ti aiuterà a comprendere come usare gli URL di rete CDN nelle pagine e nel contenuto di SharePoint in modo che SharePoint reindirizza le richieste di risorse di origine pubblica e privata al rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="4d9e3-536">Aggiornamento dei collegamenti rete CDN risorse</span><span class="sxs-lookup"><span data-stu-id="4d9e3-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="4d9e3-537">Utilizzo di risorse in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="4d9e3-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="4d9e3-538">Utilizzo di risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="4d9e3-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="4d9e3-539">Per informazioni su come utilizzare il rete CDN per ospitare web part sul lato client, vedere l'argomento Ospitare la web part sul lato client da [Office 365 rete CDN (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-540">Se si aggiunge la _cartella ClientSideAssets_ all'elenco delle origini rete CDN private, il rendering delle web part personalizzate ospitate da rete CDN non verrà eseguito. </span><span class="sxs-lookup"><span data-stu-id="4d9e3-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="4d9e3-541">I file utilizzati dalle web part SPFX possono utilizzare solo il rete CDN pubblico e la cartella ClientSideAssets è un'origine predefinita per le web part rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="4d9e3-542">Aggiornamento dei collegamenti rete CDN risorse</span><span class="sxs-lookup"><span data-stu-id="4d9e3-542">Updating links to CDN assets</span></span>

<span data-ttu-id="4d9e3-543">Per usare gli asset aggiunti a un'origine, è sufficiente aggiornare i collegamenti al file originale con il percorso del file nell'origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="4d9e3-544">Modificare la pagina o il contenuto contenente i collegamenti alle risorse aggiunte a un'origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="4d9e3-545">È inoltre possibile utilizzare uno dei diversi metodi per cercare e sostituire a livello globale i collegamenti in un sito o in una raccolta siti se si desidera aggiornare il collegamento a una determinata risorsa ovunque venga visualizzato.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="4d9e3-546">Per ogni collegamento a un asset in un'origine, sostituisci il percorso con il percorso del file nell'rete CDN origine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="4d9e3-547">È possibile utilizzare percorsi relativi.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-547">You can use relative paths.</span></span>
+ <span data-ttu-id="4d9e3-548">Salvare la pagina o il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-548">Save the page or content.</span></span>

<span data-ttu-id="4d9e3-549">Si consideri ad esempio l'immagine _/site/SiteAssets/images/image.png_, copiata nella cartella della raccolta documenti _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="4d9e3-550">Per utilizzare l'asset rete CDN, sostituire il percorso originale del file di immagine con il percorso dell'origine per rendere il nuovo URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="4d9e3-551">Se vuoi usare l'URL completo dell'asset invece di un percorso relativo, crea il collegamento in questo modo:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="4d9e3-552">In generale, non è consigliabile codificare gli URL direttamente agli asset nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="4d9e3-553">Tuttavia, è possibile creare manualmente URL per gli asset di origini pubbliche, se necessario.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="4d9e3-554">Per ulteriori informazioni, vedere [Hardcoding rete CDN URL per gli asset pubblici.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md).</span></span>

<span data-ttu-id="4d9e3-555">Per informazioni su come verificare che gli asset vengano serviti dal rete CDN, vedere Come verificare che gli asset vengano serviti dal [rete CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in Risoluzione dei problemi relativi alla [Office 365 rete CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="4d9e3-556">Utilizzo di risorse in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="4d9e3-556">Using assets in public origins</span></span>

<span data-ttu-id="4d9e3-557">La **funzionalità di** pubblicazione di SharePoint Online riscrive automaticamente gli URL degli asset archiviati in origini pubbliche negli equivalenti di rete CDN in modo che gli asset siano serviti dal servizio rete CDN anziché SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="4d9e3-558">Se l'origine si trova in un sito con la caratteristica Pubblicazione abilitata e gli asset che si desidera scaricare nel rete CDN sono inclusi in una delle categorie seguenti, SharePoint riscriverà automaticamente gli URL per gli asset nell'origine, a condizione che l'asset non sia stato escluso da un criterio di rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="4d9e3-559">Di seguito è riportata una panoramica dei collegamenti riscritti automaticamente dalla SharePoint pubblicazione:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="4d9e3-560">URL IMG/LINK/CSS nelle risposte HTML della pagina di pubblicazione classica</span><span class="sxs-lookup"><span data-stu-id="4d9e3-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="4d9e3-561">Sono incluse le immagini aggiunte dagli autori all'interno del contenuto HTML di una pagina</span><span class="sxs-lookup"><span data-stu-id="4d9e3-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="4d9e3-562">URL immagine web part Raccolta immagini SlideShow</span><span class="sxs-lookup"><span data-stu-id="4d9e3-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="4d9e3-563">Campi immagine nei risultati dell'API REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="4d9e3-564">Utilizzare la nuova _proprietà ImageFieldsToTryRewriteToCdnUrls_ per fornire un elenco delimitato da virgole di campi</span><span class="sxs-lookup"><span data-stu-id="4d9e3-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="4d9e3-565">Supporta i campi collegamento ipertestuale e i campi PublishingImage</span><span class="sxs-lookup"><span data-stu-id="4d9e3-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="4d9e3-566">SharePoint rendering di immagini</span><span class="sxs-lookup"><span data-stu-id="4d9e3-566">SharePoint image renditions</span></span>

<span data-ttu-id="4d9e3-567">Il diagramma seguente illustra il flusso di lavoro quando SharePoint una richiesta per una pagina contenente risorse da un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="4d9e3-568">![Diagramma del flusso di lavoro: recupero Office 365 rete CDN risorse da un'origine pubblica](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flusso di lavoro: recupero di Office 365 rete CDN risorse da un'origine pubblica")</span><span class="sxs-lookup"><span data-stu-id="4d9e3-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="4d9e3-569">Se si desidera disabilitare la riscrittura automatica per URL specifici in una pagina, è possibile estrarre la pagina e aggiungere il parametro della stringa di query **? NoAutoReWrites=true** alla fine di ogni collegamento che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="4d9e3-570">Creazione di rete CDN URL per gli asset pubblici</span><span class="sxs-lookup"><span data-stu-id="4d9e3-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="4d9e3-571">Se  la caratteristica Pubblicazione non è abilitata per un'origine pubblica o se l'asset non è uno dei tipi di collegamento supportati dalla funzionalità di riscrittura automatica del servizio rete CDN, è possibile creare manualmente gli URL nel percorso rete CDN degli asset e utilizzarli nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-572">Non è possibile creare hardcoded o creare URL rete CDN per gli asset in un'origine privata perché il token di accesso necessario che costituisce l'ultima sezione dell'URL viene generato al momento della richiesta della risorsa.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="4d9e3-573">Puoi creare l'URL per public rete CDN e l'URL non deve essere hard coded perché è soggetto a modifiche.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="4d9e3-574">Per le rete CDN pubbliche, il formato dell'URL sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="4d9e3-575">Sostituire **TenantHostName** con il nome del tenant.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="4d9e3-576">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="4d9e3-577">La proprietà di contesto della pagina deve essere utilizzata per costruire il prefisso anziché hard coding " https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="4d9e3-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="4d9e3-578">L'URL è soggetto a modifiche e non deve essere hard coded.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="4d9e3-579">Se si utilizzano modelli di visualizzazione con Classic SharePoint Online, è possibile utilizzare la proprietà "window._spPageContextInfo.publicCdnBaseUrl" nel modello di visualizzazione per il prefisso dell'URL.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="4d9e3-580">Se si SPFx web part per le web part moderne e classiche SharePoint è possibile utilizzare la proprietà "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="4d9e3-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="4d9e3-581">In questo modo verrà fornito il prefisso in modo che, se viene modificato, l'implementazione si aggiornerà con esso.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="4d9e3-582">Come esempio per SPFx, l'URL può essere costruito utilizzando la proprietà "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL per l'elemento".</span><span class="sxs-lookup"><span data-stu-id="4d9e3-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="4d9e3-583">Vedere [Using rete CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) che fa parte della [serie di prestazioni della prima stagione](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="4d9e3-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="4d9e3-584">Utilizzo di risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="4d9e3-584">Using assets in private origins</span></span>

<span data-ttu-id="4d9e3-585">Non è necessaria alcuna configurazione aggiuntiva per utilizzare gli asset in origini private.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="4d9e3-586">SharePoint Online riscrive automaticamente gli URL per gli asset di origini private in modo che le richieste per tali asset siano sempre servite dall'rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="4d9e3-587">Non è possibile creare manualmente URL rete CDN asset in origini private perché questi URL contengono token che devono essere generati automaticamente da SharePoint Online al momento della richiesta dell'asset.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="4d9e3-588">L'accesso agli asset in origini private è protetto da token generati dinamicamente in base alle autorizzazioni utente per l'origine, con le avvertenze descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="4d9e3-589">Gli utenti devono disporre almeno **dell'accesso in** lettura alle origini per consentire rete CDN il rendering del contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="4d9e3-590">Il diagramma seguente illustra il flusso di lavoro quando SharePoint una richiesta per una pagina contenente risorse da un'origine privata.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="4d9e3-591">![Diagramma del flusso di lavoro: recupero Office 365 rete CDN risorse da un'origine privata](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flusso di lavoro: recupero Office 365 rete CDN risorse da un'origine privata")</span><span class="sxs-lookup"><span data-stu-id="4d9e3-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="4d9e3-592">Autorizzazione basata su token in origini private</span><span class="sxs-lookup"><span data-stu-id="4d9e3-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="4d9e3-593">L'accesso agli asset in origini private nel Office 365 rete CDN viene concesso dai token generati da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="4d9e3-594">Agli utenti che dispongono già dell'autorizzazione di accesso alla cartella o alla raccolta designata dall'origine vengono automaticamente concessi token che consentono all'utente di accedere al file in base al livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="4d9e3-595">Questi token di accesso sono validi da 30 a 90 minuti dopo la generazione per evitare attacchi di riesecuzione dei token.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="4d9e3-596">Dopo la generazione del token di accesso, SharePoint Online restituisce un URI personalizzato al client contenente due parametri di autorizzazione _(token_ di autorizzazione edge) e _avena_ (token di autorizzazione di origine).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="4d9e3-597">La struttura di ogni token _<'ora_ di scadenza nel formato di data e ora >__< della firma >.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="4d9e3-598">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="4d9e3-599">Chiunque sia in possesso del token può accedere alla risorsa nel rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="4d9e3-600">Tuttavia, gli URL contenenti questi token di accesso vengono condivisi solo tramite HTTPS, quindi, a meno che l'URL non sia esplicitamente condiviso da un utente finale prima della scadenza del token, l'asset non sarà accessibile agli utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="4d9e3-601">Le autorizzazioni a livello di elemento non sono supportate per gli asset in origini private</span><span class="sxs-lookup"><span data-stu-id="4d9e3-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="4d9e3-602">È importante notare che SharePoint Online non supporta le autorizzazioni a livello di elemento per gli asset di origini private.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="4d9e3-603">Ad esempio, per un file che si trova in , gli utenti hanno `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` accesso effettivo al file in base alle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="4d9e3-604">Utente</span><span class="sxs-lookup"><span data-stu-id="4d9e3-604">User</span></span>  |<span data-ttu-id="4d9e3-605">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4d9e3-605">Permissions</span></span>  |<span data-ttu-id="4d9e3-606">Accesso efficace</span><span class="sxs-lookup"><span data-stu-id="4d9e3-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4d9e3-607">Utente 1</span><span class="sxs-lookup"><span data-stu-id="4d9e3-607">User 1</span></span>     |<span data-ttu-id="4d9e3-608">Ha accesso a folder1</span><span class="sxs-lookup"><span data-stu-id="4d9e3-608">Has access to folder1</span></span>         |<span data-ttu-id="4d9e3-609">Può accedere image1.jpg dalla rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="4d9e3-610">Utente 2</span><span class="sxs-lookup"><span data-stu-id="4d9e3-610">User 2</span></span>     |<span data-ttu-id="4d9e3-611">Non ha accesso a folder1</span><span class="sxs-lookup"><span data-stu-id="4d9e3-611">Does not have access to folder1</span></span>         |<span data-ttu-id="4d9e3-612">Impossibile accedere image1.jpg dall'rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="4d9e3-613">Utente 3</span><span class="sxs-lookup"><span data-stu-id="4d9e3-613">User 3</span></span>     |<span data-ttu-id="4d9e3-614">Non dispone dell'accesso a folder1, ma viene concessa l'autorizzazione esplicita per accedere image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="4d9e3-615">Può accedere alla risorsa image1.jpg direttamente da SharePoint Online, ma non dal rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="4d9e3-616">Utente 4</span><span class="sxs-lookup"><span data-stu-id="4d9e3-616">User 4</span></span>     |<span data-ttu-id="4d9e3-617">Ha accesso a folder1, ma è stato esplicitamente negato l'accesso a image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="4d9e3-618">Non è possibile accedere all'asset da SharePoint Online, ma può accedere all'asset dal rete CDN nonostante sia stato negato l'accesso al file in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d9e3-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="4d9e3-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="4d9e3-620">Risoluzione dei problemi Office 365 rete CDN</span><span class="sxs-lookup"><span data-stu-id="4d9e3-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="4d9e3-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="4d9e3-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="4d9e3-622">Come è possibile verificare che gli asset siano serviti dal rete CDN?</span><span class="sxs-lookup"><span data-stu-id="4d9e3-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="4d9e3-623">Dopo aver aggiunto i collegamenti agli asset di rete CDN a una pagina, puoi confermare che l'asset viene servito dal rete CDN visualizzando la pagina, facendo clic con il pulsante destro del mouse sull'immagine dopo aver eseguito il rendering e esaminando l'URL dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="4d9e3-624">Puoi anche usare gli strumenti di sviluppo del browser per visualizzare l'URL di ogni risorsa in una pagina o uno strumento di traccia di rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9e3-625">Se usi uno strumento di rete come Fiddler per testare gli asset al di fuori del rendering dell'asset da una pagina di SharePoint, devi aggiungere manualmente l'intestazione referer "Referer: " alla richiesta GET in cui l'URL è l'URL radice del `https://yourdomain.sharepoint.com` tenant di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="4d9e3-626">Non è possibile testare rete CDN url direttamente in un Web browser perché è necessario disporre di un referer proveniente da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="4d9e3-627">Tuttavia, se aggiungi l'URL dell'asset rete CDN a una pagina di SharePoint e quindi apri la pagina in un browser, nella pagina verrà visualizzato il rendering dell'asset rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="4d9e3-628">Per ulteriori informazioni sull'uso degli strumenti di sviluppo nel browser Microsoft Edge, vedere [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="4d9e3-629">Per guardare un breve video ospitato nel canale [YouTube](https://aka.ms/sppnp-videos) SharePoint Developer Patterns and Practices in cui viene illustrato come verificare il funzionamento del rete CDN, vedere [Verifying your rete CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span><span class="sxs-lookup"><span data-stu-id="4d9e3-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="4d9e3-630">Perché gli asset di una nuova origine non sono disponibili?</span><span class="sxs-lookup"><span data-stu-id="4d9e3-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="4d9e3-631">Gli asset nelle nuove origini non saranno immediatamente disponibili per l'utilizzo, poiché richiede tempo per la propagazione della registrazione tramite il rete CDN e per il caricamento delle risorse dall'origine all'archiviazione rete CDN.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="4d9e3-632">Il tempo necessario per la disponibilità delle risorse nell'rete CDN dipende dal numero di asset e dalle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="4d9e3-633">La web part sul lato client o SharePoint Framework non funziona</span><span class="sxs-lookup"><span data-stu-id="4d9e3-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="4d9e3-634">Quando si abilita il Office 365 rete CDN per le origini pubbliche, il servizio rete CDN crea automaticamente queste origini predefinite:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="4d9e3-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="4d9e3-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="4d9e3-636">\*/LIBRERIA DI STILI</span><span class="sxs-lookup"><span data-stu-id="4d9e3-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="4d9e3-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="4d9e3-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="4d9e3-638">Se l'origine \*/clientsideassets non è presente, le SharePoint Framework non riusciranno e non verranno generati messaggi di avviso o di errore.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="4d9e3-639">Questa origine potrebbe non essere presente perché il rete CDN è stato abilitato con il parametro _-NoDefaultOrigins_ impostato su **$true** oppure perché l'origine è stata eliminata manualmente.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="4d9e3-640">È possibile verificare quali origini sono presenti con il seguente comando di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="4d9e3-641">Oppure puoi controllare con l'Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="4d9e3-642">Per aggiungere l'origine in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="4d9e3-643">Per aggiungere l'origine nell'Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="4d9e3-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="4d9e3-644">Quali moduli di PowerShell e shell cli è necessario utilizzare con il Office 365 rete CDN?</span><span class="sxs-lookup"><span data-stu-id="4d9e3-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="4d9e3-645">È possibile scegliere di utilizzare il Office 365 rete CDN utilizzando il modulo **PowerShell di SharePoint Online Management Shell** o l'Office 365 **CLI**.</span><span class="sxs-lookup"><span data-stu-id="4d9e3-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="4d9e3-646">Guida introduttiva a SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="4d9e3-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="4d9e3-647">Installazione dell'interfaccia Office 365 cli</span><span class="sxs-lookup"><span data-stu-id="4d9e3-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="4d9e3-648">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d9e3-648">See also</span></span>

[<span data-ttu-id="4d9e3-649">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="4d9e3-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="4d9e3-650">Pianificazione della rete e ottimizzazione delle prestazioni per Office 365</span><span class="sxs-lookup"><span data-stu-id="4d9e3-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="4d9e3-651">SharePoint Serie di prestazioni - Office 365 rete CDN video</span><span class="sxs-lookup"><span data-stu-id="4d9e3-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)