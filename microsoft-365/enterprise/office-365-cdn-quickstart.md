---
title: Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- M365initiative-CoreDeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365
ms.openlocfilehash: e9975721b5cfaaed2c9ad7562c47f12c7a5a5bc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326890"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="58f3d-103">Guida introduttiva di rete per la distribuzione di contenuti (CDN) di Office 365</span><span class="sxs-lookup"><span data-stu-id="58f3d-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="58f3d-104">È possibile utilizzare la **rete di distribuzione dei contenuti (CDN) di Office 365** per ospitare risorse statiche (immagini, JavaScript, fogli di stile, file di WOFF) per offrire prestazioni migliori per le pagine di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58f3d-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="58f3d-105">La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza.</span><span class="sxs-lookup"><span data-stu-id="58f3d-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="58f3d-106">Inoltre, la rete CDN di Office 365 utilizza il protocollo HTTP/2 per migliorare la compressione e il pipelining HTTP.</span><span class="sxs-lookup"><span data-stu-id="58f3d-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="58f3d-107">Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58f3d-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="58f3d-108">Per informazioni più dettagliate, vedere [use the Office 365 Content Delivery Network (CDN) con SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="58f3d-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="58f3d-109">La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di produzione (tutto il mondo).</span><span class="sxs-lookup"><span data-stu-id="58f3d-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="58f3d-110">Gli inquilini del governo degli Stati Uniti, le nuvole cinesi e tedesche attualmente non supportano la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="58f3d-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="58f3d-111">Utilizzare lo strumento page Diagnostics for SharePoint per identificare gli elementi non presenti nella rete CDN</span><span class="sxs-lookup"><span data-stu-id="58f3d-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="58f3d-112">È possibile utilizzare l'estensione del browser di **diagnostica pagine per SharePoint Tool** per elencare facilmente le risorse nelle pagine di SharePoint Online che è possibile aggiungere a un'origine CDN.</span><span class="sxs-lookup"><span data-stu-id="58f3d-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="58f3d-113">Lo **strumento page Diagnostics for SharePoint** è un'estensione del browser per il nuovo Microsoft Edge ( https://www.microsoft.com/edge) e i browser Chrome che analizzano sia il portale moderno di SharePoint Online che le pagine del sito di pubblicazione classiche.</span><span class="sxs-lookup"><span data-stu-id="58f3d-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="58f3d-114">Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="58f3d-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="58f3d-115">Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](https://aka.ms/perftool).</span><span class="sxs-lookup"><span data-stu-id="58f3d-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](https://aka.ms/perftool).</span></span>

<span data-ttu-id="58f3d-116">Quando si esegue lo strumento page Diagnostics for SharePoint in una pagina di SharePoint Online, è possibile fare clic sulla scheda **test diagnostici** per visualizzare un elenco di risorse che non sono ospitate dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="58f3d-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="58f3d-117">Tali risorse verranno elencate sotto la casella di **controllo della rete di distribuzione del contenuto (CDN)** , come illustrato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="58f3d-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnostica pagina](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="58f3d-119">Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58f3d-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="58f3d-120">Panoramica della rete CDN</span><span class="sxs-lookup"><span data-stu-id="58f3d-120">CDN Overview</span></span>

<span data-ttu-id="58f3d-121">La rete CDN di Office 365 è progettata per ottimizzare le prestazioni per gli utenti distribuendo oggetti spesso accessibili, come immagini e file JavaScript, in un network globale ad alta velocità, riducendo il tempo di caricamento delle pagine e consentendo l'accesso agli oggetti ospitati il più vicino possibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="58f3d-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="58f3d-122">La rete CDN recupera le risorse da una posizione denominata _Origin_.</span><span class="sxs-lookup"><span data-stu-id="58f3d-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="58f3d-123">Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL.</span><span class="sxs-lookup"><span data-stu-id="58f3d-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="58f3d-124">La rete CDN di Office 365 è suddivisa in due tipi di base:</span><span class="sxs-lookup"><span data-stu-id="58f3d-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="58f3d-125">La rete **CDN pubblica** è progettata per essere utilizzata per JS (JavaScript), CSS (Stylesheets), file dei tipi di carattere Web (WOFF, WOFF2) e immagini non proprietarie come loghi dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="58f3d-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="58f3d-126">La rete **CDN privata** è progettata per essere utilizzata per le immagini (PNG, jpg, JPEG e così via).</span><span class="sxs-lookup"><span data-stu-id="58f3d-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="58f3d-127">È possibile scegliere di avere origini sia pubbliche che private per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58f3d-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="58f3d-128">La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="58f3d-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="58f3d-129">Entrambe le opzioni pubblico e privato offrono guadagni di prestazioni simili, ma ognuno ha attributi e vantaggi univoci.</span><span class="sxs-lookup"><span data-stu-id="58f3d-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="58f3d-130">Per ulteriori informazioni sulle origini della rete CDN pubblica e privata, vedere [scegliere se ogni origine deve essere pubblica o privata](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="58f3d-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="58f3d-131">Come abilitare la rete CDN pubblica e privata con la configurazione predefinita</span><span class="sxs-lookup"><span data-stu-id="58f3d-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="58f3d-132">Prima di apportare modifiche alle impostazioni della rete CDN del tenant, è necessario verificare che soddisfi i criteri di conformità, sicurezza e privacy dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58f3d-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="58f3d-133">Per le impostazioni di configurazione più dettagliate oppure se è già stata abilitata la rete CDN e si desidera aggiungere altre posizioni (Origins), vedere la sezione configurare [e configurare la rete CDN di Office 365 tramite SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="58f3d-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="58f3d-134">Connettersi al tenant tramite SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="58f3d-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="58f3d-135">Per consentire all'organizzazione di utilizzare le origini pubbliche e private con la configurazione predefinita, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="58f3d-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="58f3d-136">L'output di questi cmdlet dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="58f3d-136">Output of these cmdlets should look like the following:</span></span>

![Output di set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="58f3d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58f3d-138">See also</span></span>

[<span data-ttu-id="58f3d-139">Utilizzare lo strumento di diagnostica delle pagine per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="58f3d-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](https://aka.ms/perftool)

[<span data-ttu-id="58f3d-140">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="58f3d-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="58f3d-141">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="58f3d-141">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="58f3d-142">Pianificazione della rete e ottimizzazione delle prestazioni per Office 365</span><span class="sxs-lookup"><span data-stu-id="58f3d-142">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="58f3d-143">Serie di prestazioni di SharePoint-serie di video della rete CDN di Office 365</span><span class="sxs-lookup"><span data-stu-id="58f3d-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
