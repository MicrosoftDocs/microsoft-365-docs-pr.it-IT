---
title: Guida introduttiva a Office 365 Content Delivery Network (CDN)
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
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Guida introduttiva a Office 365 Content Delivery Network (CDN)
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921595"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="e4e27-103">Guida introduttiva a Office 365 Content Delivery Network (CDN)</span><span class="sxs-lookup"><span data-stu-id="e4e27-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="e4e27-104">È possibile utilizzare la rete **CDN (Content Delivery Network) di Office 365** incorporata per ospitare asset statici (immagini, JavaScript, fogli di stile, file WOFF) per garantire prestazioni migliori per le pagine di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4e27-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="e4e27-105">La rete per la distribuzione di contenuti di Office 365 consente di migliorare le prestazioni in quanto le risorse statiche vengono memorizzate nella cache più vicina ai browser che le richiedono. Questo consente di velocizzare i download e ridurre la latenza.</span><span class="sxs-lookup"><span data-stu-id="e4e27-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="e4e27-106">Inoltre, la rete CDN di Office 365 usa il protocollo HTTP/2 per migliorare la compressione e il pipelining HTTP.</span><span class="sxs-lookup"><span data-stu-id="e4e27-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="e4e27-107">Il servizio della rete per la distribuzione di contenuti di Office 365 è incluso nell'abbonamento a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4e27-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="e4e27-108">Per informazioni più dettagliate, vedere [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="e4e27-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="e4e27-109">La rete CDN di Office 365 è disponibile solo per i tenant nel cloud di produzione (in tutto il mondo).</span><span class="sxs-lookup"><span data-stu-id="e4e27-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="e4e27-110">I tenant nel cloud del governo degli Stati Uniti, della Cina e della Germania non supportano attualmente la rete CDN di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4e27-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="e4e27-111">Usare lo strumento Diagnostica pagine per SharePoint per identificare gli elementi non presenti nella rete CDN</span><span class="sxs-lookup"><span data-stu-id="e4e27-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="e4e27-112">È possibile utilizzare l'estensione del browser Strumenti di Diagnostica pagine per **SharePoint** per elencare facilmente gli asset nelle pagine di SharePoint Online che possono essere aggiunte a un'origine CDN.</span><span class="sxs-lookup"><span data-stu-id="e4e27-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="e4e27-113">Lo **strumento Diagnostica pagine per SharePoint** è un'estensione del browser per i nuovi browser Microsoft Edge e Chrome che analizza sia il portale moderno di SharePoint Online che le pagine classiche del sito di https://www.microsoft.com/edge) pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e4e27-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="e4e27-114">Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e4e27-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="e4e27-115">Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](./page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="e4e27-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="e4e27-116">Quando si esegue lo strumento Diagnostica pagine per SharePoint in una pagina di SharePoint Online, è possibile fare clic sulla scheda **Test** di diagnostica per visualizzare un elenco degli asset non ospitati dalla rete CDN.</span><span class="sxs-lookup"><span data-stu-id="e4e27-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="e4e27-117">Questi asset verranno elencati sotto l'intestazione Controllo rete per la distribuzione di contenuti **(CDN),** come illustrato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="e4e27-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnostica delle pagine](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="e4e27-119">Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e4e27-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="e4e27-120">Panoramica della rete CDN</span><span class="sxs-lookup"><span data-stu-id="e4e27-120">CDN Overview</span></span>

<span data-ttu-id="e4e27-121">La rete CDN di Office 365 è progettata per ottimizzare le prestazioni per gli utenti distribuendo oggetti a cui si accede di frequente come immagini e file javascript su una rete globale ad alta velocità, riducendo i tempi di caricamento delle pagine e fornendo l'accesso agli oggetti ospitati il più vicino possibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="e4e27-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="e4e27-122">La rete CDN recupera gli asset da una posizione denominata _origine._</span><span class="sxs-lookup"><span data-stu-id="e4e27-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="e4e27-123">Un'origine può essere un sito di SharePoint, una raccolta documenti o una cartella accessibile da un URL.</span><span class="sxs-lookup"><span data-stu-id="e4e27-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="e4e27-124">La rete CDN di Office 365 è suddivisa in due tipi di base:</span><span class="sxs-lookup"><span data-stu-id="e4e27-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="e4e27-125">**La rete CDN** pubblica è progettata per l'uso per JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) e per immagini non proprietarie come i logo aziendali.</span><span class="sxs-lookup"><span data-stu-id="e4e27-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="e4e27-126">**La rete CDN** privata è progettata per essere utilizzata per le immagini (PNG, JPG, JPEG e così via).</span><span class="sxs-lookup"><span data-stu-id="e4e27-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="e4e27-127">È possibile scegliere di avere origini pubbliche o private per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4e27-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="e4e27-128">La maggior parte delle organizzazioni sceglie di implementare una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="e4e27-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="e4e27-129">Entrambe le opzioni pubbliche e private offrono prestazioni simili, ma ognuna ha attributi e vantaggi univoci.</span><span class="sxs-lookup"><span data-stu-id="e4e27-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="e4e27-130">Per ulteriori informazioni sulle origini cdN pubbliche e private, vedere Scegliere se ogni origine [deve essere pubblica o privata.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="e4e27-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="e4e27-131">Come abilitare la rete CDN pubblica e privata con la configurazione predefinita</span><span class="sxs-lookup"><span data-stu-id="e4e27-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="e4e27-132">Prima di apportare modifiche alle impostazioni della rete CDN tenant, è necessario verificare che soddisfi i criteri di conformità, sicurezza e privacy dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4e27-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="e4e27-133">Per impostazioni di configurazione più dettagliate o se la rete CDN è già stata abilitata e si desidera aggiungere ulteriori posizioni (origini), vedere la sezione Configurare e configurare la rete CDN di [Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) tramite SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="e4e27-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="e4e27-134">Connettersi al tenant tramite SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e4e27-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="e4e27-135">Per consentire all'organizzazione di utilizzare sia origini pubbliche che private con la configurazione predefinita, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e4e27-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="e4e27-136">L'output di questi cmdlet dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e4e27-136">Output of these cmdlets should look like the following:</span></span>

![Output di Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="e4e27-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e27-138">See also</span></span>

[<span data-ttu-id="e4e27-139">Usare lo strumento Diagnostica pagine per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e4e27-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="e4e27-140">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e4e27-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="e4e27-141">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="e4e27-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="e4e27-142">Pianificazione della rete e ottimizzazione delle prestazioni per Office 365</span><span class="sxs-lookup"><span data-stu-id="e4e27-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="e4e27-143">Serie di prestazioni di SharePoint - Serie video cdN di Office 365</span><span class="sxs-lookup"><span data-stu-id="e4e27-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)