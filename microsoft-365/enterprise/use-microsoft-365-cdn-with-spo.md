---
title: Usare la rete per la distribuzione di contenuti (CDN) di Office 365 con SharePoint Online
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
description: Informazioni su come usare la rete per la distribuzione di contenuti (CDN) di Office 365 per velocizzare la distribuzione delle risorse di SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690975"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="e8ac5-103">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="e8ac5-104">È possibile usare la rete per la distribuzione di contenuti di Office 365 predefinita per ospitare risorse statiche e migliorare le prestazioni delle pagine di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="e8ac5-105">La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="e8ac5-106">Inoltre, la rete CDN di Office 365 usa il [protocollo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) per migliorare la compressione e il pipelining HTTP.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="e8ac5-107">Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-108">La rete CDN di Office 365 è disponibile solo per i tenant nel cloud **di** produzione (internazionale).</span><span class="sxs-lookup"><span data-stu-id="e8ac5-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="e8ac5-109">I tenant nei cloud del governo statunitense, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="e8ac5-110">La rete per la distribuzione di contenuti di Office 365 è costituita da diverse reti per la distribuzione di contenuti che consentono di ospitare le risorse statiche in più località o _origini_ e gestirle da reti globali ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="e8ac5-111">In base al tipo di contenuto che si vuole ospitare nella rete per la distribuzione di contenuti di Office 365, è possibile aggiungere origini **pubbliche**, origini **private** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="e8ac5-112">Per [ulteriori informazioni sulla](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) differenza tra origini pubbliche e private, vedere Scegliere se ogni origine deve essere pubblica o privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="e8ac5-113">![Diagramma concettuale della rete CDN di Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagramma concettuale della rete CDN di Office 365")</span><span class="sxs-lookup"><span data-stu-id="e8ac5-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="e8ac5-114">Se si ha già familiarità con il funzionamento delle reti CDN, è necessario completare solo alcuni passaggi per abilitare la rete CDN di Office 365 per il tenant.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="e8ac5-115">In questo argomento viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-115">This topic describes how.</span></span> <span data-ttu-id="e8ac5-116">Continua a leggere per informazioni su come iniziare a ospitare gli asset statici.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-117">Esistono altre reti CDN ospitate da Microsoft che possono essere usate con Office 365 per scenari di utilizzo specializzati, ma non sono descritte in questo argomento perché non rientrano nell'ambito della rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-118">Per ulteriori informazioni, vedere [Altre reti CDN Microsoft.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="e8ac5-119">**Tornare alla pianificazione [della rete e all'ottimizzazione delle prestazioni per Office 365.](https://aka.ms/tune)**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="e8ac5-120">Panoramica dell'utilizzo della rete CDN di Office 365 in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="e8ac5-121">Per configurare la rete CDN di Office 365 per l'organizzazione, attenersi alla seguente procedura di base:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="e8ac5-122">Pianificare la distribuzione della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="e8ac5-123">[Determinare quali risorse statiche si desidera ospitare nella rete CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="e8ac5-124">[Determinare dove archiviare le risorse.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="e8ac5-125">Questo percorso può essere un sito, una raccolta o una cartella di SharePoint ed è denominato _origine._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="e8ac5-126">[Scegliere se ogni origine deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="e8ac5-127">È possibile aggiungere più origini di tipi pubblici e privati.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="e8ac5-128">Configurare la rete CDN tramite PowerShell o l'interfaccia dell'interfaccia utente di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="e8ac5-129">Configurare la rete CDN tramite SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8ac5-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="e8ac5-130">Configurare la rete CDN tramite PowerShell PnP</span><span class="sxs-lookup"><span data-stu-id="e8ac5-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="e8ac5-131">Configurare la rete CDN tramite l'interfaccia cli di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="e8ac5-132">Al termine di questo passaggio, si avranno le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="e8ac5-133">È stata abilitata la rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="e8ac5-134">Sono state aggiunte le origini, identificando ogni origine come pubblica o privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="e8ac5-135">Al termine dell'installazione, è possibile gestire la rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) nel tempo:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="e8ac5-136">Aggiunta, aggiornamento e rimozione di risorse</span><span class="sxs-lookup"><span data-stu-id="e8ac5-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="e8ac5-137">Aggiunta e rimozione di origini</span><span class="sxs-lookup"><span data-stu-id="e8ac5-137">Adding and removing origins</span></span>
+ <span data-ttu-id="e8ac5-138">Configurazione dei criteri per la rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="e8ac5-139">Se necessario, disabilitando la rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="e8ac5-140">Infine, vedi Uso delle risorse della rete [CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) per informazioni sull'accesso alle risorse della rete CDN da origini pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="e8ac5-141">Per indicazioni sulla risoluzione dei problemi comuni, vedere Risoluzione dei problemi relativi alla rete CDN di [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="e8ac5-142">Pianificare la distribuzione della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-143">Prima di distribuire la rete CDN di Office 365 per il tenant di Office 365, è necessario considerare i fattori seguenti come parte del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="e8ac5-144">Determinare quali risorse statiche si desidera ospitare nella rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="e8ac5-145">Determinare dove archiviare le risorse</span><span class="sxs-lookup"><span data-stu-id="e8ac5-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="e8ac5-146">Scegliere se ogni origine deve essere pubblica o privata</span><span class="sxs-lookup"><span data-stu-id="e8ac5-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="e8ac5-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="e8ac5-148">Determinare quali risorse statiche si desidera ospitare nella rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="e8ac5-149">In generale, le reti CDN sono più efficaci per ospitare asset _statici_ o asset che non cambiano molto spesso.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="e8ac5-150">Una buona regola generale è identificare i file che soddisfano alcune o tutte queste condizioni:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="e8ac5-151">File statici incorporati in una pagina (ad esempio script e immagini) che possono avere un impatto incrementale significativo sui tempi di caricamento delle pagine</span><span class="sxs-lookup"><span data-stu-id="e8ac5-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="e8ac5-152">File di grandi dimensioni come eseguibili e file di installazione</span><span class="sxs-lookup"><span data-stu-id="e8ac5-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="e8ac5-153">Librerie di risorse che supportano il codice sul lato client</span><span class="sxs-lookup"><span data-stu-id="e8ac5-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="e8ac5-154">Ad esempio, file di piccole dimensioni richiesti ripetutamente come immagini e script del sito possono migliorare in modo significativo le prestazioni di rendering del sito e ridurre in modo incrementale il carico sui siti di SharePoint Online quando vengono aggiunti a un'origine CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="e8ac5-155">File di dimensioni maggiori, ad esempio eseguibili di installazione, possono essere scaricati dalla rete CDN, con un impatto positivo sulle prestazioni e una conseguente riduzione del carico sul sito di SharePoint Online, anche se non vi si accede con la frequenza richiesta.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="e8ac5-156">Il miglioramento delle prestazioni in base ai file dipende da molti fattori, tra cui la prossimità del client all'endpoint della rete CDN più vicino, le condizioni temporanee sulla rete locale e così via.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="e8ac5-157">Molti file statici sono piuttosto piccoli e possono essere scaricati da Office 365 in meno di un secondo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="e8ac5-158">Tuttavia, una pagina Web può contenere molti file incorporati con un tempo di download cumulativo di diversi secondi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="e8ac5-159">La pubblicazione di questi file dalla rete CDN può ridurre in modo significativo il tempo di caricamento complessivo delle pagine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="e8ac5-160">Vedere [Quali miglioramenti delle prestazioni offre una rete CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Per un esempio.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="e8ac5-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="e8ac5-162">Determinare dove archiviare le risorse</span><span class="sxs-lookup"><span data-stu-id="e8ac5-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="e8ac5-163">La rete CDN recupera le risorse da una posizione denominata _origine._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="e8ac5-164">Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="e8ac5-165">Quando si specificano le origini per l'organizzazione, è possibile disporre di una notevole flessibilità.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="e8ac5-166">Ad esempio, è possibile specificare più origini o una singola origine in cui inserire tutti gli asset della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="e8ac5-167">È possibile scegliere di avere origini pubbliche o private per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="e8ac5-168">La maggior parte delle organizzazioni sceglie di implementare una combinazione di queste due soluzioni.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="e8ac5-169">È possibile creare un nuovo contenitore per le origini, ad esempio cartelle o raccolte documenti, e aggiungere i file che si desidera rendere disponibili dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="e8ac5-170">Si tratta di un approccio utile se si dispone di un set specifico di risorse che si desidera essere disponibili dalla rete CDN e si desidera limitare il set di asset della rete CDN solo a tali file nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="e8ac5-171">È inoltre possibile configurare una raccolta siti, un sito, una raccolta o una cartella esistente come origine, in modo da rendere tutti gli asset idonei nel contenitore disponibili dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="e8ac5-172">Prima di aggiungere un contenitore esistente come origine, è importante assicurarsi di conoscere il contenuto e le autorizzazioni in modo da non esporre inavvertitamente le risorse agli utenti anonimi o non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="e8ac5-173">È possibile definire _criteri per la rete CDN_ per escludere il contenuto delle origini dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="e8ac5-174">I criteri cdn escludono le risorse in origini pubbliche o private da attributi quali il tipo di _file_ e la classificazione del sito e vengono applicati a tutte le origini di CdnType (privato o pubblico) specificato nei criteri.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="e8ac5-175">Ad esempio, se si aggiunge un'origine privata costituita da un sito contenente più siti  secondari, è possibile definire un criterio per escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata la classificazione non sia servito dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="e8ac5-176">Il criterio verrà applicato al contenuto _di_ tutte le origini private aggiunte alla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="e8ac5-177">Tenere presente che maggiore è il numero di origini, maggiore sarà l'impatto sul tempo necessario al servizio CDN per elaborare le richieste.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="e8ac5-178">È consigliabile limitare il più possibile il numero di origini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="e8ac5-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="e8ac5-180">Scegliere se ogni origine deve essere pubblica o privata</span><span class="sxs-lookup"><span data-stu-id="e8ac5-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="e8ac5-181">Quando si identifica un'origine, è necessario specificare se deve essere resa _pubblica_ o _privata._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="e8ac5-182">L'accesso alle risorse cdn in origini pubbliche è anonimo e il contenuto della rete CDN in origini private è protetto da token generati dinamicamente per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="e8ac5-183">Indipendentemente dall'opzione scelta, Microsoft fa tutto il lavoro necessario per l'amministrazione della rete CDN stessa.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="e8ac5-184">Inoltre, è possibile cambiare idea in un secondo momento, dopo aver configurato la rete CDN e identificato le origini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="e8ac5-185">Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna presenta attributi e vantaggi univoci.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="e8ac5-186">**Le** origini pubbliche all'interno della rete CDN di Office 365 sono accessibili in modo anonimo ed è possibile accedere alle risorse ospitate da chiunque abbia l'URL dell'asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="e8ac5-187">Dal momento che l'accesso al contenuto in origini pubbliche è anonimo, è consigliabile usarle solo per memorizzare nella cache contenuti generici non riservati, ad esempio file JavaScript, script, icone e immagini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="e8ac5-188">**Le** origini private all'interno della rete CDN di Office 365 forniscono accesso privato al contenuto degli utenti, ad esempio raccolte documenti, siti e immagini proprietarie di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="e8ac5-189">L'accesso al contenuto in origini private è protetto da token generati dinamicamente in modo che sia accessibile solo agli utenti con autorizzazioni per la raccolta documenti originale o il percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="e8ac5-190">Le origini private nella rete CDN di Office 365 possono essere usate solo per il contenuto di SharePoint Online ed è possibile accedere alle risorse in origini private solo tramite il reindirizzamento dal tenant di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="e8ac5-191">Per altre informazioni sul funzionamento dell'accesso della rete CDN alle risorse in un'origine privata, vedere [Uso di risorse in origini private.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="e8ac5-192">Attributi e vantaggi dell'hosting di risorse in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="e8ac5-193">Gli asset esposti in un'origine pubblica sono accessibili da tutti in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="e8ac5-194">Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="e8ac5-195">Se si rimuove un asset da un'origine pubblica, l'asset potrebbe continuare a essere disponibile per un massimo di 30 giorni dalla cache. Tuttavia, i collegamenti all'asset nella rete CDN verranno invalidati entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="e8ac5-196">Quando si ospitano fogli di stile (file CSS) in un'origine pubblica, è possibile utilizzare percorsi e URI relativi all'interno del codice.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="e8ac5-197">Ciò significa che puoi fare riferimento alla posizione delle immagini di sfondo e di altri oggetti rispetto alla posizione dell'asset che la chiama.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="e8ac5-198">Sebbene sia possibile codificare a livello di codice l'URL di un'origine pubblica, questa operazione non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="e8ac5-199">Il motivo è che se l'accesso alla rete CDN diventa non disponibile, l'URL non verrà risolto automaticamente nell'organizzazione in SharePoint Online e potrebbe causare collegamenti interrotti e altri errori.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="e8ac5-200">I tipi di file predefiniti inclusi per le origini pubbliche sono .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="e8ac5-201">È possibile specificare tipi di file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="e8ac5-202">È possibile configurare un criterio per escludere le risorse identificate dalle classificazioni del sito specificate.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="e8ac5-203">Ad esempio, è possibile scegliere di escludere tutte le risorse contrassegnate come "riservate" o "limitate" anche se sono un tipo di file consentito e si trovano in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="e8ac5-204">Attributi e vantaggi dell'hosting di risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="e8ac5-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="e8ac5-205">Le origini private possono essere utilizzate solo per le risorse di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="e8ac5-206">Gli utenti possono accedere alle risorse da un'origine privata solo se dispongono delle autorizzazioni per accedere al contenitore.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="e8ac5-207">L'accesso anonimo a queste risorse non è consentito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="e8ac5-208">Le risorse di origini private devono essere indicate dal tenant di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="e8ac5-209">L'accesso diretto alle risorse della rete CDN privata non funziona.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="e8ac5-210">Se si rimuove un asset dall'origine privata, l'asset potrebbe continuare a essere disponibile fino a un'ora dalla cache. Tuttavia, i collegamenti all'asset nella rete CDN verranno invalidati entro 15 minuti dalla rimozione dell'asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="e8ac5-211">I tipi di file predefiniti inclusi per le origini private sono .gif, .ico, .jpeg, .jpg, .js e .png.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="e8ac5-212">È possibile specificare tipi di file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="e8ac5-213">Analogamente alle origini pubbliche, è possibile configurare un criterio per escludere le risorse identificate dalle classificazioni dei siti specificate anche se si utilizzano caratteri jolly per includere tutte le risorse all'interno di una cartella o di una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="e8ac5-214">Per ulteriori informazioni sul motivo per cui usare la rete CDN di Office 365, i concetti generali della rete CDN e altre reti CDN Microsoft che è possibile usare con il tenant di Office 365, vedere Reti per la distribuzione di [contenuti.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="e8ac5-215">Origini predefinite della rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-215">Default CDN origins</span></span>

<span data-ttu-id="e8ac5-216">Se non diversamente specificato, Office 365 configura automaticamente alcune origini predefinite quando si abilita la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-217">Se inizialmente scegli di non eseguirle, puoi aggiungere queste origini dopo aver completato la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="e8ac5-218">A meno che non si comprenda le conseguenze del saltare la configurazione delle origini predefinite e non si abbia un motivo specifico per farlo, è consigliabile consentirne la creazione quando si abilita la rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="e8ac5-219">Origini predefinite della rete CDN privata:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="e8ac5-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="e8ac5-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="e8ac5-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="e8ac5-221">\*/siteassets</span></span>

<span data-ttu-id="e8ac5-222">Origini predefinite della rete CDN pubblica:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="e8ac5-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="e8ac5-223">\*/masterpage</span></span>
+ <span data-ttu-id="e8ac5-224">\*/style library</span><span class="sxs-lookup"><span data-stu-id="e8ac5-224">\*/style library</span></span>
+ <span data-ttu-id="e8ac5-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="e8ac5-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-226">_clientsideassets_ è un'origine pubblica predefinita aggiunta al servizio CDN di Office 365 a dicembre 2017.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="e8ac5-227">Questa origine deve essere presente perché le soluzioni SharePoint Framework nella rete CDN funzionino.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="e8ac5-228">Se la rete CDN di Office 365 è stata abilitata prima di dicembre 2017 o se è stata ignorata la configurazione delle origini predefinite quando è stata abilitata la rete CDN, è possibile aggiungere manualmente questa origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="e8ac5-229">Per ulteriori informazioni, vedere La web part sul lato client o la soluzione [SharePoint Framework non funziona.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="e8ac5-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="e8ac5-231">Configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8ac5-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e8ac5-232">Le procedure descritte in questa sezione richiedono l'utilizzo di SharePoint Online Management Shell per connettersi a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="e8ac5-233">Per istruzioni, vedere [Connettersi a PowerShell di SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="e8ac5-234">Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="e8ac5-235">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="e8ac5-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="e8ac5-236">Abilitare l'organizzazione a usare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-237">Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="e8ac5-238">Connettersi al tenant tramite SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="e8ac5-239">A questo punto, utilizzare il cmdlet **Get-SPOTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-240">Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="e8ac5-241">Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-242">È possibile consentire all'organizzazione di usare origini pubbliche, origini private o entrambe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="e8ac5-243">Puoi anche configurare la rete CDN in modo da ignorare la configurazione delle origini predefinite quando la abiliti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="e8ac5-244">È sempre possibile aggiungere queste origini più avanti, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="e8ac5-245">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="e8ac5-246">Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e8ac5-247">Per consentire all'organizzazione di utilizzare origini pubbliche e private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="e8ac5-248">Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e il potenziale impatto di ignorare la configurazione delle origini predefinite.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="e8ac5-249">Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="e8ac5-250">Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="e8ac5-251">Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="e8ac5-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="e8ac5-253">Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-254">Quando si definiscono i tipi di file utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-255">Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="e8ac5-256">Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="e8ac5-257">Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, gif, jpg e js.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="e8ac5-258">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="e8ac5-259">Ad esempio, per consentire alla rete CDN di ospitare file con estensione css e png, immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="e8ac5-260">Per visualizzare i tipi di file attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-261">Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="e8ac5-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="e8ac5-263">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-264">Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-SPOTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-265">Se si desidera escludere ulteriori classificazioni del sito, utilizzare prima il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme alle nuove.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="e8ac5-266">Utilizzare il cmdlet **Set-SPOTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili sulla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e8ac5-267">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="e8ac5-268">In Windows PowerShell per SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="e8ac5-269">Per sapere quali classificazioni di siti sono attualmente limitate, utilizzare il cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-270">Le proprietà che verranno restituite _sono IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="e8ac5-271">La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-272">Le estensioni di file predefinite sono diverse tra pubblico e privato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="e8ac5-273">La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="e8ac5-274">Ad esempio, è possibile  escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata tale classificazione non verrà servito dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="e8ac5-275">La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="e8ac5-276">Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni **e disabilitato** per _i siti_ classici.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="e8ac5-277">Dipende dalle impostazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="e8ac5-278">Per ulteriori informazioni su questi cmdlet, vedere [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="e8ac5-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="e8ac5-280">Aggiungere un'origine per le risorse</span><span class="sxs-lookup"><span data-stu-id="e8ac5-280">Add an origin for your assets</span></span>

<span data-ttu-id="e8ac5-281">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire un'origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="e8ac5-282">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-282">You can define multiple origins.</span></span> <span data-ttu-id="e8ac5-283">L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8ac5-284">Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="e8ac5-285">Il valore _del percorso_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="e8ac5-286">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="e8ac5-287">Origins supporta i caratteri jolly anteposti all'URL.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="e8ac5-288">In questo modo è possibile creare origini che si estendono su più siti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="e8ac5-289">Ad esempio, per includere tutte le risorse nella cartella masterpages di tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="e8ac5-290">Il modificatore con caratteri jolly \* può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i **/** segmenti di URL nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="e8ac5-291">Il percorso può puntare a una raccolta documenti, una cartella o un sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="e8ac5-292">Ad esempio, il percorso _\*/site1_ corrisponderà a tutte le raccolte documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="e8ac5-293">È possibile aggiungere un'origine con un percorso relativo specifico.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="e8ac5-294">Non è possibile aggiungere un'origine utilizzando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="e8ac5-295">In questo esempio viene aggiunta un'origine privata della raccolta siti in un sito specifico:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e8ac5-296">In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta di risorse del sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="e8ac5-297">Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="e8ac5-298">Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta di risorse del sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="e8ac5-299">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-300">Nelle origini private, le risorse condivise da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="e8ac5-301">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-302">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="e8ac5-304">Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="e8ac5-305">In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-306">Tuttavia, se si desidera abilitarle manualmente, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="e8ac5-307">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la libreria di stili come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="e8ac5-308">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire le pagine master come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="e8ac5-309">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="e8ac5-310">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-311">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="e8ac5-313">Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="e8ac5-314">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="e8ac5-315">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="e8ac5-316">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="e8ac5-317">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="e8ac5-318">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-319">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="e8ac5-321">Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="e8ac5-322">Utilizzare il cmdlet **Add-SPOTenantCdnOrigin** per definire una raccolta siti come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="e8ac5-323">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e8ac5-324">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="e8ac5-325">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="e8ac5-327">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="e8ac5-329">Gestire la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-330">Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="e8ac5-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="e8ac5-332">Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-333">Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere le risorse esistenti quando vuoi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="e8ac5-334">È sufficiente apportare le modifiche alle risorse nella cartella o nella raccolta di SharePoint identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e8ac5-335">Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="e8ac5-336">Se tuttavia si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="e8ac5-337">Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="e8ac5-338">Per informazioni su come utilizzare questo cmdlet, vedere [Get-SPOTenantCdnOrigins.](https://technet.microsoft.com/library/mt790770.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="e8ac5-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="e8ac5-340">Rimuovere un'origine dalla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-341">È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e8ac5-342">A tale scopo, utilizzare il cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="e8ac5-343">Per informazioni su come utilizzare questo cmdlet, vedere [Remove-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790761.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="e8ac5-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="e8ac5-345">Modificare un'origine nella rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-346">Non è possibile modificare un'origine creata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="e8ac5-347">Rimuovi invece l'origine e quindi aggiungine una nuova.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="e8ac5-348">Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e Per aggiungere un'origine [per le risorse.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="e8ac5-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e8ac5-350">Disabilitare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-351">Utilizzare il cmdlet **Set-SPOTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="e8ac5-352">Se per la rete CDN sono abilitate sia l'origine pubblica che l'origine privata, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="e8ac5-353">Per disabilitare l'uso di origini pubbliche nella rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="e8ac5-354">Per disabilitare l'uso delle origini private nella rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="e8ac5-355">Per ulteriori informazioni su questo cmdlet, vedere [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="e8ac5-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="e8ac5-357">Configurare la rete CDN di Office 365 tramite PowerShell PnP</span><span class="sxs-lookup"><span data-stu-id="e8ac5-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="e8ac5-358">Le procedure descritte in questa sezione richiedono l'utilizzo di PnP PowerShell per connettersi a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="e8ac5-359">Per istruzioni, vedere [Introduzione a PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="e8ac5-360">Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite PowerShell PnP.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="e8ac5-361">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="e8ac5-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="e8ac5-362">Abilitare l'organizzazione a usare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-363">Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario recuperare lo stato corrente della configurazione della rete CDN privata nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="e8ac5-364">Connettersi al tenant tramite PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="e8ac5-365">A questo punto, utilizzare il cmdlet **Get-PnPTenantCdnEnabled** per recuperare le impostazioni di stato della rete CDN dal tenant:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-366">Lo stato della rete CDN per l'oggetto CdnType specificato verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="e8ac5-367">Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per consentire all'organizzazione di utilizzare la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-368">È possibile consentire all'organizzazione di usare origini pubbliche, origini private o entrambe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="e8ac5-369">Puoi anche configurare la rete CDN in modo da ignorare la configurazione delle origini predefinite quando la abiliti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="e8ac5-370">È sempre possibile aggiungere queste origini più avanti, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="e8ac5-371">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="e8ac5-372">Ad esempio, per consentire all'organizzazione di utilizzare sia origini pubbliche che private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e8ac5-373">Per consentire all'organizzazione di utilizzare origini pubbliche e private ma ignorare la configurazione delle origini predefinite, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="e8ac5-374">Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365 e il potenziale impatto di ignorare la configurazione delle origini predefinite.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="e8ac5-375">Per consentire all'organizzazione di utilizzare origini pubbliche, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="e8ac5-376">Per consentire all'organizzazione di utilizzare origini private, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="e8ac5-377">Per ulteriori informazioni su questo cmdlet, vedere [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="e8ac5-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="e8ac5-379">Modificare l'elenco dei tipi di file da includere nella rete CDN di Office 365 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-380">Quando si definiscono i tipi di file utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-381">Se si desidera aggiungere ulteriori tipi di file all'elenco, utilizzare innanzitutto il cmdlet per individuare i tipi di file già consentiti e includerli nell'elenco insieme a quelli nuovi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="e8ac5-382">Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per definire i tipi di file statici che possono essere ospitati da origini pubbliche e private nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="e8ac5-383">Per impostazione predefinita, sono consentiti tipi di asset comuni, ad esempio css, gif, jpg e js.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="e8ac5-384">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="e8ac5-385">Ad esempio, per consentire alla rete CDN di ospitare file con estensione css e png, immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="e8ac5-386">Per sapere quali tipi di file sono attualmente consentiti dalla rete CDN, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-387">Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="e8ac5-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="e8ac5-389">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365 (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-390">Quando si escludono le classificazioni dei siti utilizzando il cmdlet **Set-PnPTenantCdnPolicy,** si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-391">Se si desidera escludere ulteriori classificazioni del sito, utilizzare prima il cmdlet per individuare le classificazioni già escluse e quindi aggiungerle insieme alle nuove.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="e8ac5-392">Utilizzare il cmdlet **Set-PnPTenantCdnPolicy** per escludere le classificazioni dei siti che non si desidera rendere disponibili sulla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e8ac5-393">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="e8ac5-394">In PowerShell PnP:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="e8ac5-395">Per sapere quali classificazioni di sito sono attualmente limitate, utilizzare il cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="e8ac5-396">Le proprietà che verranno restituite _sono IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ _e ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="e8ac5-397">La _proprietà IncludeFileExtensions_ contiene l'elenco delle estensioni di file che verranno gestite dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-398">Le estensioni di file predefinite sono diverse tra pubblico e privato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="e8ac5-399">La _proprietà ExcludeRestrictedSiteClassifications_ contiene le classificazioni dei siti che si desidera escludere dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="e8ac5-400">Ad esempio, è possibile  escludere i siti contrassegnati come Riservati in modo che il contenuto dei siti a cui è applicata tale classificazione non verrà servito dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="e8ac5-401">La _proprietà ExcludeIfNoScriptDisabled_ esclude il contenuto dalla rete CDN in base alle impostazioni dell'attributo _NoScript_ a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="e8ac5-402">Per impostazione predefinita, _l'attributo NoScript_ è impostato su **Abilitato** per i _siti_ moderni **e disabilitato** per _i siti_ classici.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="e8ac5-403">Dipende dalle impostazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="e8ac5-404">Per ulteriori informazioni su questi cmdlet, vedere [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="e8ac5-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="e8ac5-406">Aggiungere un'origine per le risorse</span><span class="sxs-lookup"><span data-stu-id="e8ac5-406">Add an origin for your assets</span></span>

<span data-ttu-id="e8ac5-407">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire un'origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="e8ac5-408">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-408">You can define multiple origins.</span></span> <span data-ttu-id="e8ac5-409">L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8ac5-410">Non inserire mai risorse che contengono informazioni sull'utente o che sono considerate sensibili all'organizzazione in un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="e8ac5-411">Il valore _del percorso_ è il percorso relativo alla raccolta o alla cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="e8ac5-412">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="e8ac5-413">Origins supporta i caratteri jolly anteposti all'URL.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="e8ac5-414">In questo modo è possibile creare origini che si estendono su più siti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="e8ac5-415">Ad esempio, per includere tutte le risorse nella cartella masterpages di tutti i siti come origine pubblica all'interno della rete CDN, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="e8ac5-416">Il modificatore con caratteri jolly \* può essere utilizzato solo all'inizio del percorso e corrisponderà a tutti i **/** segmenti di URL nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="e8ac5-417">Il percorso può puntare a una raccolta documenti, una cartella o un sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="e8ac5-418">Ad esempio, il percorso _\*/site1_ corrisponderà a tutte le raccolte documenti del sito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="e8ac5-419">È possibile aggiungere un'origine con un percorso relativo specifico.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="e8ac5-420">Non è possibile aggiungere un'origine utilizzando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="e8ac5-421">In questo esempio viene aggiunta un'origine privata della raccolta di risorse del sito in un sito specifico:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e8ac5-422">In questo esempio viene aggiunta un'origine privata della _cartella folder1_ nella raccolta di risorse del sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="e8ac5-423">Se nel percorso è presente uno spazio, è possibile racchiudere il percorso tra virgolette doppie o sostituire lo spazio con la codifica URL %20.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="e8ac5-424">Negli esempi seguenti viene aggiunta un'origine privata della cartella _1_ nella raccolta di risorse del sito della raccolta siti:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="e8ac5-425">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-426">Nelle origini private, le risorse condivise da un'origine devono avere una versione principale pubblicata prima di poter essere accessibili dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="e8ac5-427">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-428">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="e8ac5-430">Esempio: Configurare un'origine pubblica per le pagine master e per la raccolta stili per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="e8ac5-431">In genere, queste origini vengono impostate automaticamente quando si abilita la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="e8ac5-432">Tuttavia, se si desidera abilitarle manualmente, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="e8ac5-433">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la libreria di stili come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="e8ac5-434">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire le pagine master come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="e8ac5-435">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e8ac5-436">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-437">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="e8ac5-439">Esempio: Configurare un'origine privata per le risorse del sito, le pagine del sito e le immagini di pubblicazione per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="e8ac5-440">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle risorse del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="e8ac5-441">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle pagine del sito come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="e8ac5-442">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire la cartella delle immagini di pubblicazione come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="e8ac5-443">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e8ac5-444">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-445">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="e8ac5-447">Esempio: Configurare un'origine privata per una raccolta siti per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="e8ac5-448">Utilizzare il cmdlet **Add-PnPTenantCdnOrigin** per definire una raccolta siti come origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="e8ac5-449">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="e8ac5-450">Per ulteriori informazioni su questo comando e sulla relativa sintassi, vedere [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="e8ac5-451">Dopo aver eseguito il comando, il sistema sincronizza la configurazione nel datacenter.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="e8ac5-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="e8ac5-453">Questa operazione può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="e8ac5-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="e8ac5-455">Gestire la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-456">Dopo aver configurato la rete CDN, è possibile apportare modifiche alla configurazione durante l'aggiornamento del contenuto o in base alle esigenze, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="e8ac5-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="e8ac5-458">Aggiungere, aggiornare o rimuovere asset dalla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-459">Dopo aver completato i passaggi di configurazione, puoi aggiungere nuovi asset e aggiornare o rimuovere le risorse esistenti quando vuoi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="e8ac5-460">È sufficiente apportare le modifiche alle risorse nella cartella o nella raccolta di SharePoint identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e8ac5-461">Se aggiungi un nuovo asset, questo sarà immediatamente disponibile tramite la rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="e8ac5-462">Se tuttavia si aggiorna l'asset, la propagazione della nuova copia e la disponibilità della nuova copia nella rete CDN saranno fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="e8ac5-463">Se è necessario recuperare il percorso dell'origine, è possibile utilizzare il cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="e8ac5-464">Per informazioni su come utilizzare questo cmdlet, vedere [Get-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e8ac5-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="e8ac5-466">Rimuovere un'origine dalla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-467">È possibile rimuovere l'accesso a una cartella o a una raccolta di SharePoint identificata come origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="e8ac5-468">A tale scopo, utilizzare il cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="e8ac5-469">Per informazioni su come utilizzare questo cmdlet, vedere [Remove-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="e8ac5-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="e8ac5-471">Modificare un'origine nella rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-472">Non è possibile modificare un'origine creata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="e8ac5-473">Rimuovi invece l'origine e quindi aggiungine una nuova.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="e8ac5-474">Per ulteriori informazioni, vedere Per rimuovere un'origine dalla rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e Per aggiungere un'origine [per le risorse.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="e8ac5-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e8ac5-476">Disabilitare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-477">Utilizzare il cmdlet **Set-PnPTenantCdnEnabled** per disabilitare la rete CDN per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="e8ac5-478">Se per la rete CDN sono abilitate sia l'origine pubblica che l'origine privata, è necessario eseguire il cmdlet due volte, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="e8ac5-479">Per disabilitare l'uso di origini pubbliche nella rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="e8ac5-480">Per disabilitare l'uso delle origini private nella rete CDN, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="e8ac5-481">Per ulteriori informazioni su questo cmdlet, vedere [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="e8ac5-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="e8ac5-483">Configurare la rete CDN di Office 365 tramite l'interfaccia cli di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="e8ac5-484">Le procedure descritte in questa sezione richiedono l'installazione dell'interfaccia della riga di comando di [Office 365.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="e8ac5-485">Successivamente, connettersi al tenant di Office 365 usando il [comando di](https://pnp.github.io/office365-cli/cmd/login/) accesso.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="e8ac5-486">Completare questi passaggi per configurare la rete CDN per ospitare le risorse in SharePoint Online tramite l'interfaccia cli di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="e8ac5-487">Fare clic per espandere</span><span class="sxs-lookup"><span data-stu-id="e8ac5-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="e8ac5-488">Abilitare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-489">È possibile gestire lo stato della rete CDN di Office 365 nel tenant usando il comando [spo cdn set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="e8ac5-490">Per abilitare la rete CDN pubblica di Office 365 nel tenant, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="e8ac5-491">Per abilitare la rete CDN di Office 365 SharePoint, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="e8ac5-492">Visualizzare lo stato corrente della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-493">Per verificare se il tipo specifico di rete CDN di Office 365 è abilitato o disabilitato, usare il comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="e8ac5-494">Per verificare se la rete CDN pubblica di Office 365 è abilitata, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="e8ac5-495">Visualizzare le origini della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="e8ac5-496">Per visualizzare le origini della rete CDN pubblica di Office 365 attualmente configurate, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="e8ac5-497">Vedere [Origini della rete CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) predefinita per informazioni sulle origini di cui viene eseguito il provisioning per impostazione predefinita quando si abilita la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="e8ac5-498">Aggiungere un'origine cdN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8ac5-499">Non inserire mai risorse considerate sensibili per l'organizzazione in una raccolta documenti di SharePoint configurata come origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="e8ac5-500">Utilizzare il [comando spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) per definire un'origine CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="e8ac5-501">È possibile definire più origini.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-501">You can define multiple origins.</span></span> <span data-ttu-id="e8ac5-502">L'origine è un URL che punta a una raccolta o a una cartella di SharePoint contenente gli asset che si desidera ospitare dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="e8ac5-503">Dove `path` è il percorso relativo della cartella che contiene gli asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="e8ac5-504">Oltre ai percorsi relativi, è possibile utilizzare i caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="e8ac5-505">Per includere tutte le risorse nella raccolta pagine **master** di tutti i siti come origine pubblica, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="e8ac5-506">Per configurare un'origine privata per una raccolta siti specifica, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="e8ac5-507">Dopo aver aggiunto un'origine CDN, potrebbero essere necessari fino a 15 minuti prima che tu sia in grado di recuperare i file tramite il servizio CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="e8ac5-508">È possibile verificare se la determinata origine è già stata abilitata utilizzando il comando [spo cdn origin list.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="e8ac5-509">Rimuovere un'origine della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="e8ac5-510">Utilizzare il [comando spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) per rimuovere un'origine CDN per il tipo di rete CDN specificato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="e8ac5-511">Per rimuovere un'origine pubblica dalla configurazione della rete CDN, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="e8ac5-512">La rimozione di un'origine CDN non influisce sui file archiviati in alcuna raccolta documenti corrispondente a tale origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="e8ac5-513">Se si fa riferimento a queste risorse utilizzando l'URL di SharePoint, SharePoint tornerà automaticamente all'URL originale che punta alla raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="e8ac5-514">Se, tuttavia, è stato fatto riferimento alle risorse utilizzando un URL della rete CDN pubblica, la rimozione dell'origine interromperà il collegamento e sarà necessario modificarli manualmente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="e8ac5-515">Modificare un'origine della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="e8ac5-516">Non è possibile modificare un'origine CDN esistente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="e8ac5-517">È invece consigliabile rimuovere l'origine della rete CDN definita in precedenza utilizzando il comando e `spo cdn origin remove` aggiungerne una nuova utilizzando il `spo cdn origin add` comando.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="e8ac5-518">Modificare i tipi di file da includere nella rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-519">Per impostazione predefinita, nella rete CDN sono inclusi i tipi di file seguenti: _css, eot, gif, ico, jpeg, jpg, js, map, png, svg, ttf, woff e woff2._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="e8ac5-520">Se è necessario includere tipi di file aggiuntivi nella rete CDN, è possibile modificare la configurazione della rete CDN utilizzando il comando [spo cdn policy set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-521">Quando si modifica l'elenco dei tipi di file, si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-522">Se si desidera includere tipi di file aggiuntivi, utilizzare innanzitutto il comando dell'elenco dei criteri per la rete [cdn di Spo](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) per individuare i tipi di file attualmente configurati.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="e8ac5-523">Per aggiungere il _tipo di_ file JSON all'elenco predefinito dei tipi di file inclusi nella rete CDN pubblica, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="e8ac5-524">Modificare l'elenco delle classificazioni dei siti che si desidera escludere dalla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-525">Utilizzare il [comando spo cdn policy set per](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) escludere le classificazioni dei siti che non si desidera rendere disponibili nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="e8ac5-526">Per impostazione predefinita, non vengono escluse classificazioni di siti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-527">Quando si modifica l'elenco delle classificazioni di sito escluse, si sovrascrive l'elenco attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="e8ac5-528">Se si desidera escludere classificazioni aggiuntive, utilizzare innanzitutto il comando dell'elenco dei criteri per la rete [cdn di Spo](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) per individuare le classificazioni attualmente configurate.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="e8ac5-529">Per escludere i siti _classificati come HBI_ dalla rete CDN pubblica, eseguire</span><span class="sxs-lookup"><span data-stu-id="e8ac5-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="e8ac5-530">Disabilitare la rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-531">Per disabilitare la rete CDN di Office 365, utilizzare `spo cdn set` il comando, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="e8ac5-532">Uso delle risorse della rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-532">Using your CDN assets</span></span>

<span data-ttu-id="e8ac5-533">Dopo aver abilitato la rete CDN e configurato origini e criteri, è possibile iniziare a usare le risorse della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="e8ac5-534">In questa sezione viene illustrato come utilizzare gli URL della rete CDN nelle pagine e nel contenuto di SharePoint in modo che SharePoint reindirizza le richieste di risorse sia di origine pubblica che privata alla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="e8ac5-535">Aggiornamento dei collegamenti alle risorse della rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="e8ac5-536">Uso di risorse in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="e8ac5-537">Uso di risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="e8ac5-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="e8ac5-538">Per informazioni su come usare la rete CDN per ospitare web part sul lato client, vedere l'argomento Ospitare la web part sul lato client dalla rete CDN di [Office 365 (Hello World parte 4).](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-539">Se si aggiunge la _cartella ClientSideAssets_ all'elenco delle origini **della** rete CDN privata, il rendering delle web part personalizzate ospitate dalla rete CDN non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="e8ac5-540">I file utilizzati dalle web part SPFX possono utilizzare solo la rete CDN pubblica e la cartella ClientSideAssets è un'origine predefinita per la rete CDN pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="e8ac5-541">Aggiornamento dei collegamenti alle risorse della rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-541">Updating links to CDN assets</span></span>

<span data-ttu-id="e8ac5-542">Per utilizzare gli asset aggiunti a un'origine, è sufficiente aggiornare i collegamenti al file originale con il percorso del file nell'origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="e8ac5-543">Modificare la pagina o il contenuto che contiene i collegamenti alle risorse aggiunte a un'origine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="e8ac5-544">È inoltre possibile utilizzare uno dei diversi metodi per cercare e sostituire a livello globale i collegamenti in un sito o una raccolta siti immessi se si desidera aggiornare il collegamento a un determinato asset ovunque venga visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="e8ac5-545">Per ogni collegamento a un asset in un'origine, sostituire il percorso con il percorso del file nell'origine della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="e8ac5-546">È possibile utilizzare percorsi relativi.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-546">You can use relative paths.</span></span>
+ <span data-ttu-id="e8ac5-547">Salvare la pagina o il contenuto.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-547">Save the page or content.</span></span>

<span data-ttu-id="e8ac5-548">Si consideri ad esempio l'immagine _/site/SiteAssets/images/image.png,_ copiata nella cartella della raccolta documenti _/site/CDN_origins/public/._</span><span class="sxs-lookup"><span data-stu-id="e8ac5-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="e8ac5-549">Per utilizzare l'asset cdn, sostituire il percorso originale del file di immagine con il percorso dell'origine per rendere il nuovo URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="e8ac5-550">Se vuoi usare l'URL completo dell'asset invece di un percorso relativo, crea il collegamento in questo modo:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="e8ac5-551">In generale, non è consigliabile codificare gli URL direttamente agli asset nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="e8ac5-552">Tuttavia, è possibile creare manualmente url per gli asset di origini pubbliche, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="e8ac5-553">Per ulteriori informazioni, vedere [Hardcoding CDN URLs for public assets.](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="e8ac5-554">Per informazioni su come verificare che le risorse vengano servite dalla rete CDN, vedere Come verificare che le risorse siano servite dalla [rete CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) nella sezione risoluzione dei problemi della rete CDN di [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="e8ac5-555">Uso di risorse in origini pubbliche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-555">Using assets in public origins</span></span>

<span data-ttu-id="e8ac5-556">La **funzionalità** di pubblicazione in SharePoint Online riscrive automaticamente gli URL delle risorse archiviate in origini pubbliche negli equivalenti della rete CDN in modo che le risorse siano servite dal servizio CDN anziché da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="e8ac5-557">Se l'origine si trova in un sito con la caratteristica Pubblicazione abilitata e le risorse che si desidera scaricare nella rete CDN sono in una delle categorie seguenti, SharePoint riscriverà automaticamente gli URL delle risorse nell'origine, purché l'asset non sia stato escluso da un criterio cdn.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="e8ac5-558">Di seguito è riportata una panoramica dei collegamenti che vengono riscritti automaticamente dalla caratteristica Pubblicazione SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="e8ac5-559">URL IMG/LINK/CSS nelle risposte HTML delle pagine di pubblicazione classiche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="e8ac5-560">Sono incluse le immagini aggiunte dagli autori all'interno del contenuto HTML di una pagina</span><span class="sxs-lookup"><span data-stu-id="e8ac5-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="e8ac5-561">URL immagine web part Raccolta immagini SlideShow</span><span class="sxs-lookup"><span data-stu-id="e8ac5-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="e8ac5-562">Campi immagine nei risultati dell'API REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="e8ac5-563">Utilizzare la nuova proprietà _ImageFieldsToTryRewriteToCdnUrls_ per fornire un elenco delimitato da virgole di campi</span><span class="sxs-lookup"><span data-stu-id="e8ac5-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="e8ac5-564">Supporta campi collegamento ipertestuale e campi PublishingImage</span><span class="sxs-lookup"><span data-stu-id="e8ac5-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="e8ac5-565">Rendering di immagini di SharePoint</span><span class="sxs-lookup"><span data-stu-id="e8ac5-565">SharePoint image renditions</span></span>

<span data-ttu-id="e8ac5-566">Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine pubblica.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="e8ac5-567">![Diagramma del flusso di lavoro: Recupero delle risorse della rete CDN di Office 365 da un'origine pubblica](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Flusso di lavoro: recupero di risorse della rete CDN di Office 365 da un'origine pubblica")</span><span class="sxs-lookup"><span data-stu-id="e8ac5-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="e8ac5-568">Se si desidera disabilitare la riscrittura automatica per URL specifici in una pagina, è possibile estrarre la pagina e aggiungere il parametro della stringa di **query? NoAutoReWrites=true** alla fine di ogni collegamento che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="e8ac5-569">URL cdn hardcoding per risorse pubbliche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="e8ac5-570">Se  la caratteristica pubblicazione non è abilitata per un'origine pubblica o l'asset non è uno dei tipi di collegamento supportati dalla funzionalità di riscrittura automatica del servizio CDN, è possibile creare manualmente gli URL nel percorso della rete CDN degli asset e utilizzare questi URL nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-571">Non è possibile codificare in modo hardcoded gli URL della rete CDN per gli asset in un'origine privata perché il token di accesso necessario che costituisce l'ultima sezione dell'URL viene generato al momento della richiesta della risorsa.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="e8ac5-572">Per gli asset della rete CDN pubblica, il formato dell'URL sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="e8ac5-573">Sostituire **TenantHostName** con il nome del tenant.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="e8ac5-574">Esempio:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="e8ac5-575">Uso di risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="e8ac5-575">Using assets in private origins</span></span>

<span data-ttu-id="e8ac5-576">Non è necessaria alcuna configurazione aggiuntiva per l'utilizzo di risorse in origini private.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="e8ac5-577">SharePoint Online riscrive automaticamente gli URL delle risorse in origini private in modo che le richieste per tali risorse siano sempre servite dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="e8ac5-578">Non è possibile creare manualmente URL in asset cdn in origini private perché contengono token che devono essere generati automaticamente da SharePoint Online al momento della richiesta dell'asset.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="e8ac5-579">L'accesso alle risorse in origini private è protetto da token generati dinamicamente in base alle autorizzazioni utente per l'origine, con le avvertenze descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="e8ac5-580">Gli utenti devono disporre almeno **dell'accesso** in lettura alle origini per consentire il rendering del contenuto da parte della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="e8ac5-581">Nel diagramma seguente viene illustrato il flusso di lavoro quando SharePoint riceve una richiesta per una pagina contenente risorse da un'origine privata.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="e8ac5-582">![Diagramma del flusso di lavoro: Recupero delle risorse della rete CDN di Office 365 da un'origine privata](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Flusso di lavoro: recupero di asset della rete CDN di Office 365 da un'origine privata")</span><span class="sxs-lookup"><span data-stu-id="e8ac5-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="e8ac5-583">Autorizzazione basata su token in origini private</span><span class="sxs-lookup"><span data-stu-id="e8ac5-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="e8ac5-584">L'accesso alle risorse in origini private nella rete CDN di Office 365 viene concesso dai token generati da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="e8ac5-585">Agli utenti che dispongono già dell'autorizzazione per accedere alla cartella o alla raccolta designata dall'origine vengono automaticamente concessi token che consentono all'utente di accedere al file in base al livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="e8ac5-586">Questi token di accesso sono validi da 30 a 90 minuti dopo la generazione per evitare attacchi di riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="e8ac5-587">Una volta generato il token di accesso, SharePoint Online restituisce un URI personalizzato al client contenente due parametri di autorizzazione _(token_ di autorizzazione edge) e _oat_ (token di autorizzazione di origine).</span><span class="sxs-lookup"><span data-stu-id="e8ac5-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="e8ac5-588">La struttura di ogni token è<'ora di scadenza nel formato epoche >__< _'firma sicura'>_.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="e8ac5-589">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="e8ac5-590">Chiunque sia in possesso del token può accedere alla risorsa nella rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="e8ac5-591">Tuttavia, gli URL contenenti questi token di accesso vengono condivisi solo tramite HTTPS, quindi, a meno che l'URL non sia esplicitamente condiviso da un utente finale prima della scadenza del token, l'asset non sarà accessibile agli utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="e8ac5-592">Le autorizzazioni a livello di elemento non sono supportate per le risorse in origini private</span><span class="sxs-lookup"><span data-stu-id="e8ac5-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="e8ac5-593">È importante notare che SharePoint Online non supporta le autorizzazioni a livello di elemento per le risorse di origini private.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="e8ac5-594">Ad esempio, per un file che si trova in , gli utenti hanno `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` accesso effettivo al file in base alle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="e8ac5-595">Utente</span><span class="sxs-lookup"><span data-stu-id="e8ac5-595">User</span></span>  |<span data-ttu-id="e8ac5-596">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e8ac5-596">Permissions</span></span>  |<span data-ttu-id="e8ac5-597">Accesso efficace</span><span class="sxs-lookup"><span data-stu-id="e8ac5-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e8ac5-598">Utente 1</span><span class="sxs-lookup"><span data-stu-id="e8ac5-598">User 1</span></span>     |<span data-ttu-id="e8ac5-599">Ha accesso a folder1</span><span class="sxs-lookup"><span data-stu-id="e8ac5-599">Has access to folder1</span></span>         |<span data-ttu-id="e8ac5-600">Può accedere image1.jpg dalla rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="e8ac5-601">Utente 2</span><span class="sxs-lookup"><span data-stu-id="e8ac5-601">User 2</span></span>     |<span data-ttu-id="e8ac5-602">Non ha accesso a folder1</span><span class="sxs-lookup"><span data-stu-id="e8ac5-602">Does not have access to folder1</span></span>         |<span data-ttu-id="e8ac5-603">Impossibile accedere image1.jpg dalla rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="e8ac5-604">Utente 3</span><span class="sxs-lookup"><span data-stu-id="e8ac5-604">User 3</span></span>     |<span data-ttu-id="e8ac5-605">Non dispone dell'accesso a folder1, ma dispone dell'autorizzazione esplicita per accedere image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="e8ac5-606">Può accedere alle risorse image1.jpg direttamente da SharePoint Online, ma non dalla rete CDN</span><span class="sxs-lookup"><span data-stu-id="e8ac5-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="e8ac5-607">Utente 4</span><span class="sxs-lookup"><span data-stu-id="e8ac5-607">User 4</span></span>     |<span data-ttu-id="e8ac5-608">Ha accesso a folder1, ma gli è stato esplicitamente negato l'accesso image1.jpg in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="e8ac5-609">Non è possibile accedere all'asset da SharePoint Online, ma può accedere all'asset dalla rete CDN nonostante sia stato negato l'accesso al file in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8ac5-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="e8ac5-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="e8ac5-611">Risoluzione dei problemi relativi alla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="e8ac5-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ac5-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="e8ac5-613">Come verificare che le risorse siano servite dalla rete CDN?</span><span class="sxs-lookup"><span data-stu-id="e8ac5-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="e8ac5-614">Dopo aver aggiunto i collegamenti agli asset della rete CDN a una pagina, puoi verificare che l'asset venga servito dalla rete CDN visualizzando la pagina, facendo clic con il pulsante destro del mouse sull'immagine dopo il rendering e esaminando l'URL dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="e8ac5-615">Puoi anche usare gli strumenti di sviluppo del browser per visualizzare l'URL di ogni risorsa in una pagina o usare uno strumento di traccia di rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ac5-616">Se si usa uno strumento di rete come Fiddler per testare gli asset all'esterno del rendering dell'asset da una pagina di SharePoint, è necessario aggiungere manualmente l'intestazione referer "Referer: " alla richiesta GET in cui l'URL è l'URL radice del tenant di `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="e8ac5-617">Non è possibile testare gli URL della rete CDN direttamente in un Web browser perché è necessario disporre di un referenziatore proveniente da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="e8ac5-618">Tuttavia, se si aggiunge l'URL dell'asset della rete CDN a una pagina di SharePoint e quindi si apre la pagina in un browser, nella pagina verrà visualizzato il rendering dell'asset della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="e8ac5-619">Per altre informazioni sull'uso degli strumenti di sviluppo nel browser Microsoft Edge, vedi [Strumenti di sviluppo di Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="e8ac5-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="e8ac5-620">Per guardare un breve video ospitato nel canale YouTube dei modelli e delle procedure per sviluppatori di [SharePoint](https://aka.ms/sppnp-videos) che illustra come verificare il funzionamento della rete [CDN,](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)vedere Verificare l'utilizzo della rete CDN e garantire una connettività di rete ottimale.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="e8ac5-621">Perché le risorse di una nuova origine non sono disponibili?</span><span class="sxs-lookup"><span data-stu-id="e8ac5-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="e8ac5-622">Gli asset nelle nuove origini non saranno immediatamente disponibili per l'uso, perché la registrazione richiede tempo per la propagazione tramite la rete CDN e per il caricamento degli asset dall'origine all'archiviazione della rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="e8ac5-623">Il tempo necessario per la disponibilità delle risorse nella rete CDN dipende dal numero di asset e dalle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="e8ac5-624">La web part sul lato client o la soluzione SharePoint Framework non funziona</span><span class="sxs-lookup"><span data-stu-id="e8ac5-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="e8ac5-625">Quando si abilita la rete CDN di Office 365 per origini pubbliche, il servizio CDN crea automaticamente queste origini predefinite:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="e8ac5-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="e8ac5-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="e8ac5-627">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="e8ac5-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="e8ac5-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="e8ac5-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="e8ac5-629">Se l'origine \*/clientsideassets è mancante, le soluzioni di SharePoint Framework avranno esito negativo e non verranno generati messaggi di avviso o di errore.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="e8ac5-630">Questa origine potrebbe non essere presente perché la rete CDN è stata abilitata con il parametro _-NoDefaultOrigins_ impostato su **$true** oppure perché l'origine è stata eliminata manualmente.</span><span class="sxs-lookup"><span data-stu-id="e8ac5-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="e8ac5-631">È possibile verificare quali origini sono presenti con il comando PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="e8ac5-632">Oppure è possibile verificare con l'interfaccia cli di Office 365:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="e8ac5-633">Per aggiungere l'origine in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="e8ac5-634">Per aggiungere l'origine nell'interfaccia cli di Office 365:</span><span class="sxs-lookup"><span data-stu-id="e8ac5-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="e8ac5-635">Quali moduli di PowerShell e shell cli sono necessari per utilizzare la rete CDN di Office 365?</span><span class="sxs-lookup"><span data-stu-id="e8ac5-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="e8ac5-636">È possibile scegliere di utilizzare la rete CDN di Office 365 usando il modulo PowerShell di **SharePoint Online Management Shell** o l'interfaccia cli di Office **365.**</span><span class="sxs-lookup"><span data-stu-id="e8ac5-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="e8ac5-637">Guida introduttiva a SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e8ac5-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="e8ac5-638">Installazione dell'interfaccia cli di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="e8ac5-639">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ac5-639">See also</span></span>

[<span data-ttu-id="e8ac5-640">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="e8ac5-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="e8ac5-641">Pianificazione della rete e ottimizzazione delle prestazioni per Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="e8ac5-642">Serie di prestazioni di SharePoint - Serie di video sulla rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e8ac5-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
