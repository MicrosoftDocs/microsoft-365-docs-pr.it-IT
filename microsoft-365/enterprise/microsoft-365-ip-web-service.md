---
title: Servizio Web per URL e indirizzi IP di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Informazioni su come usare l'indirizzo IP e il servizio Web URL di Office 365 per identificare e distinguere meglio il traffico di rete di Office 365.
ms.openlocfilehash: 03e6eac86e66db6f9e94c3f98e6d7b565ffa0f14
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456460"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="7b9de-103">Servizio Web per URL e indirizzi IP di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="7b9de-104">Servizio Web per URL e indirizzi IP di Office 365 consentono di identificare e distinguere il traffico di rete di Office 365, semplificando la valutazione, la configurazione e il miglioramento delle modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="7b9de-104">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes.</span></span> <span data-ttu-id="7b9de-105">Questo servizio Web basato su REST sostituisce i file XML scaricabili precedenti, che sono stati eliminati il 2 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="7b9de-105">This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="7b9de-106">Come cliente o fornitore di dispositivi perimetrali di rete, è possibile eseguire la compilazione con il servizio Web per gli indirizzi IP di Office 365 e le voci di FQDN.</span><span class="sxs-lookup"><span data-stu-id="7b9de-106">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries.</span></span> <span data-ttu-id="7b9de-107">È possibile accedere ai dati direttamente in un Web browser usando questi URL:</span><span class="sxs-lookup"><span data-stu-id="7b9de-107">You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="7b9de-108">Per la versione più recente degli URL e degli intervalli di indirizzi IP di Office 365, usare [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7b9de-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="7b9de-109">Per i dati sulla pagina degli URL e degli intervalli di indirizzi IP di Office 365 per firewall e server proxy, usare [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7b9de-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="7b9de-110">Per ottenere tutte le ultime modifiche apportate da luglio 2018, quando il servizio Web ha iniziato a essere disponibile, usare [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7b9de-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="7b9de-111">Un cliente può utilizzare questo servizio Web per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b9de-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="7b9de-112">Aggiornare gli script di PowerShell per ottenere i dati degli endpoint di Office 365 e modificare la formattazione dei dispositivi di rete in uso.</span><span class="sxs-lookup"><span data-stu-id="7b9de-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="7b9de-113">Usare queste informazioni per aggiornare i file PAC distribuiti ai computer client.</span><span class="sxs-lookup"><span data-stu-id="7b9de-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="7b9de-114">Un fornitore di dispositivi di rete perimetrale può utilizzare questo servizio Web per le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b9de-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="7b9de-115">Creare e testare il software dei dispositivi per scaricare l'elenco per la configurazione automatizzata.</span><span class="sxs-lookup"><span data-stu-id="7b9de-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="7b9de-116">Verificare la versione corrente.</span><span class="sxs-lookup"><span data-stu-id="7b9de-116">Check for the current version.</span></span>
- <span data-ttu-id="7b9de-117">Conoscere le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="7b9de-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="7b9de-118">Se si usa Azure ExpressRoute per connettersi a Office 365, vedere [Azure ExpressRoute per Office 365](azure-expressroute.md) per acquisire familiarità con i servizi di Office 365 supportati su Azure ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="7b9de-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="7b9de-119">Per comprendere quali richieste di rete per le applicazioni di Office 365 richiedono la connettività Internet, vedere l'articolo [URL e intervalli di indirizzi IP di Office 365](urls-and-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="7b9de-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="7b9de-120">Queste precauzioni consentiranno di migliorare la configurazione dei dispositivi di protezione perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7b9de-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="7b9de-121">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="7b9de-121">For more information, see:</span></span>

- [<span data-ttu-id="7b9de-122">Post di blog dell'annuncio nel forum della community IT di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="7b9de-123">Forum della community IT di Office 365 per domande sull'uso dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="7b9de-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="7b9de-124">Parametri comuni</span><span class="sxs-lookup"><span data-stu-id="7b9de-124">Common parameters</span></span>

<span data-ttu-id="7b9de-125">Questi parametri sono comuni a tutti i metodi di servizio Web:</span><span class="sxs-lookup"><span data-stu-id="7b9de-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="7b9de-126">**formato = < JSON | CSV >** — Per impostazione predefinita il formato dei dati restituiti è JSON.</span><span class="sxs-lookup"><span data-stu-id="7b9de-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="7b9de-127">Questo parametro facoltativo consente di restituire i dati con valori delimitati da virgole (CSV).</span><span class="sxs-lookup"><span data-stu-id="7b9de-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="7b9de-128">**ClientRequestId =\<guid>** — GUID necessario creato per l'associazione di client.</span><span class="sxs-lookup"><span data-stu-id="7b9de-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="7b9de-129">Generare un GUID univoco per ogni computer che chiama il servizio Web, ossia gli script inclusi in questa pagina generano un GUID.</span><span class="sxs-lookup"><span data-stu-id="7b9de-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="7b9de-130">Non usare i GUID illustrati negli esempi seguenti perché potrebbero essere bloccati dal servizio web in futuro.</span><span class="sxs-lookup"><span data-stu-id="7b9de-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="7b9de-131">Il formato GUID è _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, dove x rappresenta un numero esadecimale.</span><span class="sxs-lookup"><span data-stu-id="7b9de-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="7b9de-132">Per generare un GUID, è possibile usare il comando di PowerShell [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) oppure usare un servizio online come [generatore di GUID online](https://www.guidgenerator.com/).</span><span class="sxs-lookup"><span data-stu-id="7b9de-132">To generate a GUID, you can use the [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="7b9de-133">Metodo per la versione web</span><span class="sxs-lookup"><span data-stu-id="7b9de-133">Version web method</span></span>

<span data-ttu-id="7b9de-134">Microsoft aggiorna l'indirizzo IP e le voci di FQDN di Office 365 alla fine di ogni mese.</span><span class="sxs-lookup"><span data-stu-id="7b9de-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="7b9de-135">Gli aggiornamenti out-of-band sono talvolta pubblicati a causa di problemi di supporto, aggiornamenti della sicurezza o altri requisiti operativi.</span><span class="sxs-lookup"><span data-stu-id="7b9de-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="7b9de-136">Ai dati di ogni istanza pubblicata è assegnato un numero di versione e la versione metodo Web consente di controllare la versione più recente di ogni istanza di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-136">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="7b9de-137">È consigliabile controllare la versione non più di una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="7b9de-137">We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="7b9de-138">I parametri per il metodo per la versione web sono:</span><span class="sxs-lookup"><span data-stu-id="7b9de-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="7b9de-139">**Completaversioni = < true | False >** — Per impostazione predefinita la versione restituita è la più recente.</span><span class="sxs-lookup"><span data-stu-id="7b9de-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="7b9de-140">Includere questo parametro facoltativo per richiedere tutte le versioni pubblicate dopo il primo rilascio del servizio web.</span><span class="sxs-lookup"><span data-stu-id="7b9de-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="7b9de-141">**Format=< JSON | CSV | RSS >** — oltre ai formati JSON e CSV, la versione metodo web supporta inoltre RSS.</span><span class="sxs-lookup"><span data-stu-id="7b9de-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="7b9de-142">È possibile usare questo parametro facoltativo con _AllVersions=true_ per richiedere un feed RSS che può essere usato con Outlook o altri lettori RSS.</span><span class="sxs-lookup"><span data-stu-id="7b9de-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="7b9de-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**: questo parametro facoltativo specifica l'istanza per ripristinare la versione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="7b9de-144">Se omesso, vengono restituite tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="7b9de-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="7b9de-145">Le istanze valide sono: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="7b9de-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="7b9de-146">La metodo Web per la versione non è limitata a tariffe e non restituisce mai i codici di risposta HTTP 429.</span><span class="sxs-lookup"><span data-stu-id="7b9de-146">The version web method is not rate limited and does not ever return 429 HTTP Response Codes.</span></span> <span data-ttu-id="7b9de-147">La risposta al metodo Web per la versione include un'intestazione cache-controllo che consiglia la memorizzazione nella cache dei dati per 1 ora.</span><span class="sxs-lookup"><span data-stu-id="7b9de-147">The response to the version web method does include a cache-control header recommending caching of the data for 1 hour.</span></span> <span data-ttu-id="7b9de-148">Il risultato ottenuto dal metodo Web per la versione potrebbe essere un singolo record o una matrice di record. </span><span class="sxs-lookup"><span data-stu-id="7b9de-148">The result from the version web method can be a single record or an array of records.</span></span> <span data-ttu-id="7b9de-149">Gli elementi di ogni record sono:</span><span class="sxs-lookup"><span data-stu-id="7b9de-149">The elements of each record are:</span></span>

- <span data-ttu-id="7b9de-150">instance: il nome breve dell'istanza del servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="7b9de-151">latest: l'ultima versione degli endpoint dell'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="7b9de-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="7b9de-152">versioni: elenco di tutte le versioni precedenti per l'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="7b9de-152">versions — A list of all previous versions for the specified instance.</span></span> <span data-ttu-id="7b9de-153">Questo elemento è incluso solo se il parametro _allversions _ è vero.</span><span class="sxs-lookup"><span data-stu-id="7b9de-153">This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="7b9de-154">Esempi:</span><span class="sxs-lookup"><span data-stu-id="7b9de-154">Examples:</span></span>

<span data-ttu-id="7b9de-155">URI della richiesta di esempio 1: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p113">Questo URI restituisce l'ultima versione di ogni istanza del servizio di Office 365. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p113">This URI returns the latest version of each Office 365 service instance. Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="7b9de-p114">Il GUID del parametro ClientRequestID in questi URI è solo un esempio. Per provare gli URI del servizio Web, generare il proprio GUID. I GUID mostrati in questi esempi potrebbero essere bloccati dal servizio Web in futuro.</span><span class="sxs-lookup"><span data-stu-id="7b9de-p114">The GUID for the ClientRequestID parameter in these URIs are only an example. To try the web service URIs out, generate your own GUID. The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="7b9de-161">URI della richiesta di esempio 2: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p115">Questo URI restituisce l'ultima versione dell'istanza del servizio di Office 365 specificata. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p115">This URI returns the latest version of the specified Office 365 service instance. Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="7b9de-164">URI della richiesta di esempio 3: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p116">Questo URI mostra l'output in formato CSV. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p116">This URI shows output in CSV format. Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="7b9de-167">URI della richiesta di esempio 4: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p117">Questo URI mostra tutte le versioni precedenti che sono state pubblicate per l'istanza Worldwide del servizio di Office 365. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p117">This URI shows all prior versions that have been published for the Office 365 worldwide service instance. Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="7b9de-170">URI del feed RSS di esempio 5: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="7b9de-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="7b9de-p118">Questo URI mostra un feed RSS delle versioni pubblicate che includono collegamenti all'elenco di modifiche di ogni versione. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p118">This URI shows an RSS feed of the published versions that include links to the list of changes for each version. Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="7b9de-173">Metodo Web per gli endpoint</span><span class="sxs-lookup"><span data-stu-id="7b9de-173">Endpoints web method</span></span>

<span data-ttu-id="7b9de-174">Il metodo web per gli endpoint restituisce tutti i record per intervalli di indirizzi IP e URL del servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="7b9de-175">Per la configurazione dei dispositivi di rete, è consigliabile usare sempre i dati più recenti del metodo Web endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="7b9de-176">Microsoft fornisce un preavviso 30 giorni prima di pubblicare nuove aggiunte per fornire il tempo necessario per aggiornare gli elenchi di controllo di accesso e gli elenchi di esclusioni del server proxy.</span><span class="sxs-lookup"><span data-stu-id="7b9de-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="7b9de-177">È consigliabile chiamare il metodo web per gli endpoint solo quando la versione metodo web indica che è disponibile una nuova versione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b9de-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="7b9de-178">I parametri per il metodo web per gli endpoint sono:</span><span class="sxs-lookup"><span data-stu-id="7b9de-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="7b9de-179">**ServiceAreas = < comuni | Exchange | SharePoint | Skype >**, un elenco delle aree di servizio separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="7b9de-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="7b9de-180">Sono validi _Common_, _Exchange_, _SharePoint_ e _Skype_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="7b9de-181">Poiché gli elementi dell’area di servizio di _Common_ sono un prerequisito per tutte le altre aree di servizio, il servizio web li includerà sempre.</span><span class="sxs-lookup"><span data-stu-id="7b9de-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="7b9de-182">Se non si include questo parametro, tutte le aree del servizio vengono restituite.</span><span class="sxs-lookup"><span data-stu-id="7b9de-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="7b9de-183">**TenantName=< tenant_name >** - Nome tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="7b9de-184">Il servizio web prende il nome specificato e lo inserisce in parti dell'URL che includono il nome del tenant.</span><span class="sxs-lookup"><span data-stu-id="7b9de-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="7b9de-185">Se non si specifica alcun nome tenant, tali parti dell'URL avranno il carattere jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="7b9de-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="7b9de-186">**NoIPv6=<true | false>**: Impostare questo parametro su _true_ per escludere gli indirizzi IPv6 dall'output, se non si usa il protocollo IPv6 nella propria rete.</span><span class="sxs-lookup"><span data-stu-id="7b9de-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="7b9de-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>**. Questo parametro obbligatorio specifica l'istanza da cui restituire gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="7b9de-188">Le istanze valide sono: _Worldwide_, _China_, _Germany_, _USGovDoD_ e _USGovGCCHigh_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="7b9de-189">Se si chiama il metodo Web per gli endpoint troppe volte dallo stesso indirizzo IP client, si potrebbe ricevere il codice di risposta HTTP _429 (Troppe richieste)_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="7b9de-190">Se viene visualizzato questo codice di risposta, attendere un'ora prima di ripetere la richiesta o generare un nuovo GUID per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="7b9de-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="7b9de-191">Come procedura consigliata, pianificare la chiamata del metodo Web per gli endpoint solo quando la versione metodo Web indica che è disponibile una nuova versione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b9de-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="7b9de-192">Il risultato ottenuto dal metodo Web per gli endpoint è una matrice di record in cui ogni record rappresenta uno specifico set di endpoint. </span><span class="sxs-lookup"><span data-stu-id="7b9de-192">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set.</span></span> <span data-ttu-id="7b9de-193">Gli elementi per ogni record sono:</span><span class="sxs-lookup"><span data-stu-id="7b9de-193">The elements for each record are:</span></span>

- <span data-ttu-id="7b9de-194">id: il numero ID non modificabile del set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="7b9de-195">serviceArea: l'area del servizio di cui fa parte: _Common_, _Exchange_, _SharePoint_o _Skype_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="7b9de-196">URL: URL per il set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-196">urls — URLs for the endpoint set.</span></span> <span data-ttu-id="7b9de-197">Una matrice JSON di record DNS.</span><span class="sxs-lookup"><span data-stu-id="7b9de-197">A JSON array of DNS records.</span></span> <span data-ttu-id="7b9de-198">Questo elemento viene omesso se non specificato.</span><span class="sxs-lookup"><span data-stu-id="7b9de-198">Omitted if blank.</span></span>
- <span data-ttu-id="7b9de-199">tcpPorts: porte TCP per il set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-199">tcpPorts — TCP ports for the endpoint set.</span></span> <span data-ttu-id="7b9de-200">Tutti gli elementi Ports sono formattati come un elenco con valori delimitati da virgole (-).</span><span class="sxs-lookup"><span data-stu-id="7b9de-200">All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-).</span></span> <span data-ttu-id="7b9de-201">Le porte sono valide per tutti gli indirizzi IP e per tutti gli URL del set di endpoint di una specifica categoria.</span><span class="sxs-lookup"><span data-stu-id="7b9de-201">Ports apply to all IP addresses and all URLs in the endpoint set for a given category.</span></span> <span data-ttu-id="7b9de-202">Questo elemento viene omesso se non specificato.</span><span class="sxs-lookup"><span data-stu-id="7b9de-202">Omitted if blank.</span></span>
- <span data-ttu-id="7b9de-203">udpPorts: le porte UDP degli intervalli di indirizzi IP nel set di endpoint. </span><span class="sxs-lookup"><span data-stu-id="7b9de-203">udpPorts — UDP ports for the IP address ranges in this endpoint set.</span></span> <span data-ttu-id="7b9de-204">Questo elemento viene omesso se non specificato.</span><span class="sxs-lookup"><span data-stu-id="7b9de-204">Omitted if blank.</span></span>
- <span data-ttu-id="7b9de-205">ips: gli intervalli di indirizzi IP associati al set di endpoint come associati alle porte UDP o TCP elencate.</span><span class="sxs-lookup"><span data-stu-id="7b9de-205">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports.</span></span> <span data-ttu-id="7b9de-206">Una matrice JSON di intervalli di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="7b9de-206">A JSON array of IP address ranges.</span></span> <span data-ttu-id="7b9de-207">Questo elemento viene omesso se non specificato.</span><span class="sxs-lookup"><span data-stu-id="7b9de-207">Omitted if blank.</span></span>
- <span data-ttu-id="7b9de-208">Categoria: categoria di connettività per il set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="7b9de-209">I valori validi sono _Ottimizza_, _Consenti_ e_Predefinito_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="7b9de-210">Se si esegue una ricerca nell'output del metodo Web endpoint per la categoria di un indirizzo IP o URL specifico, è possibile che la query restituisca più categorie.</span><span class="sxs-lookup"><span data-stu-id="7b9de-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="7b9de-211">In tal caso, seguire le indicazioni della categoria priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="7b9de-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="7b9de-212">Se ad esempio il punto finale compare sia in _Ottimizza_ che in _Consenti_, seguire i requisiti per _Ottimizza_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="7b9de-213">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-213">Required.</span></span>
- <span data-ttu-id="7b9de-214">expressRoute: _True_ se il set di endpoint sfrutta la connessione ExpressRoute, _False_ in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="7b9de-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="7b9de-215">required: _True_ se il set di endpoint deve avere una connettività per Office 365 che sia supportata.</span><span class="sxs-lookup"><span data-stu-id="7b9de-215">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported.</span></span> <span data-ttu-id="7b9de-216">_False_ se il set di endpoint è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7b9de-216">_False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="7b9de-217">notes: per gli endpoint facoltativi, questo testo descrive la funzionalità di Office 365 che non sarà disponibile se gli URL o gli indirizzi IP nel set di endpoint non sono accessibili al livello della rete.</span><span class="sxs-lookup"><span data-stu-id="7b9de-217">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer.</span></span> <span data-ttu-id="7b9de-218">Questo elemento viene omesso se non specificato.</span><span class="sxs-lookup"><span data-stu-id="7b9de-218">Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="7b9de-219">Esempi:</span><span class="sxs-lookup"><span data-stu-id="7b9de-219">Examples:</span></span>

<span data-ttu-id="7b9de-220">URI della richiesta di esempio 1: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-221">Questo URI ottiene tutti gli endpoint per l'istanza Worldwide di Office 365 per tutti i carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7b9de-221">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads.</span></span> <span data-ttu-id="7b9de-222">Risultato dell'esempio che mostra un estratto dell'output:</span><span class="sxs-lookup"><span data-stu-id="7b9de-222">Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="7b9de-223">Si noti che l'output completo della richiesta in questo esempio conterrebbe altri set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="7b9de-224">URI della richiesta di esempio 2: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-225">In questo esempio si ottengono gli endpoint per l'istanza Worldwide di Office 365 solo per Exchange Online e le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="7b9de-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="7b9de-226">L'output dell'esempio 2 è simile a quello dell'esempio 1, ad eccezione del fatto che i risultati non includerebbero endpoint per SharePoint Online o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7b9de-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="7b9de-227">Metodo Web per le modifiche</span><span class="sxs-lookup"><span data-stu-id="7b9de-227">Changes web method</span></span>

<span data-ttu-id="7b9de-228">Il metodo Web per le modifiche restituisce gli aggiornamenti più recenti che sono stati pubblicati, in genere le modifiche apportate al mese precedente agli intervalli di indirizzi IP e degli URL.</span><span class="sxs-lookup"><span data-stu-id="7b9de-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="7b9de-229">Le modifiche più importanti ai dati degli endpoint sono nuovi URL e indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="7b9de-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="7b9de-230">Se non si aggiunge un indirizzo IP a un elenco di controllo di accesso del firewall o un URL a un elenco di bypass del server proxy, è possibile che si sia verificata un'interruzione per gli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="7b9de-231">In deroga ai requisiti operativi, i nuovi endpoint vengono pubblicati nel servizio Web 30 giorni prima della data di provisioning degli endpoint da usare per fornire il tempo necessario per aggiornare gli elenchi di controllo di accesso e gli elenchi di esclusioni del server proxy.</span><span class="sxs-lookup"><span data-stu-id="7b9de-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="7b9de-232">Il parametro obbligatorio del metodo Web per le modifiche è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7b9de-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="7b9de-233">**Versione =\<YYYYMMDDNN>** - Parametro obbligatorio di route URL.</span><span class="sxs-lookup"><span data-stu-id="7b9de-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="7b9de-234">Questo valore deve corrispondere alla versione attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="7b9de-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="7b9de-235">Il servizio Web restituisce le modifiche apportate dopo tale versione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="7b9de-236">Il formato è _AAAAMMGGNN_, dove _NN_ è un numero naturale incrementabile se è necessario pubblicare più versioni nello stesso giorno, con _00_ che rappresenta il primo aggiornamento del giorno.</span><span class="sxs-lookup"><span data-stu-id="7b9de-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="7b9de-237">Il servizio Web richiede che il parametro della _versione_ contenga esattamente 10 cifre.</span><span class="sxs-lookup"><span data-stu-id="7b9de-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="7b9de-238">Il metodo Web per le modifiche ha frequenza limitata, allo stesso modo del metodo Web per gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="7b9de-239">Se viene visualizzato il codice di risposta 429 HTTP, attendere un'ora prima di ripetere la richiesta o generare un nuovo GUID per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="7b9de-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="7b9de-240">Il risultato ottenuto dal metodo Web per le modifiche è una matrice di record in cui ogni record rappresenta una modifica in una specifica versione di endpoint. </span><span class="sxs-lookup"><span data-stu-id="7b9de-240">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints.</span></span> <span data-ttu-id="7b9de-241">Gli elementi per ogni record sono:</span><span class="sxs-lookup"><span data-stu-id="7b9de-241">The elements for each record are:</span></span>

- <span data-ttu-id="7b9de-242">id: l'ID non modificabile del record della modifica.</span><span class="sxs-lookup"><span data-stu-id="7b9de-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="7b9de-243">endpointSetId: l'ID del record del set di endpoint cui è stata apportata la modifica.</span><span class="sxs-lookup"><span data-stu-id="7b9de-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="7b9de-244">disposizione: descrive la modifica apportata al record set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="7b9de-245">I valori sono_cambia_, _aggiungi_ o_rimuovi_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="7b9de-246">impatto: non tutte le modifiche saranno ugualmente importanti per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="7b9de-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="7b9de-247">Questo elemento descrive l'impatto atteso di un ambiente perimetrale della rete aziendale in seguito a questa modifica.</span><span class="sxs-lookup"><span data-stu-id="7b9de-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="7b9de-248">Questo elemento è incluso solo in Change Records della versione **2018112800** e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7b9de-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="7b9de-249">Le opzioni per l'impatto sono:-AddedIp-un indirizzo IP è stato aggiunto a Office 365 e sarà presto disponibile per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="7b9de-250">Rappresenta una modifica da eseguire in un firewall o un dispositivo di rete perimetrale di livello 3.</span><span class="sxs-lookup"><span data-stu-id="7b9de-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="7b9de-251">Se non si aggiunge prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7b9de-252">— AddedUrl: un URL è stato aggiunto a Office 365 e sarà presto live nel servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="7b9de-253">Rappresenta una modifica da eseguire in un server proxy o in un dispositivo di rete perimetrale per analisi URL.</span><span class="sxs-lookup"><span data-stu-id="7b9de-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="7b9de-254">Se non si aggiunge tale URL prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7b9de-255">-AddedIpAndUrl-sono stati aggiunti sia un indirizzo IP che un URL.</span><span class="sxs-lookup"><span data-stu-id="7b9de-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="7b9de-256">Rappresenta una modifica da eseguire in un dispositivo firewall di livello 3 o un server proxy o in un dispositivo per analisi URL.</span><span class="sxs-lookup"><span data-stu-id="7b9de-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="7b9de-257">Se non si aggiunge tale IP/URL prima di iniziare a usarlo, può verificarsi un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7b9de-258">-RemovedIpOrUrl: almeno un indirizzo IP o un URL è stato rimosso da Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="7b9de-259">Rimuovere gli endpoint di rete dai dispositivi perimetrali, ma non c’è una scadenza per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="7b9de-260">-ChangedIsExpressRoute: è stato modificato l'attributo di supporto ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="7b9de-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="7b9de-261">Se si usa ExpressRoute, potrebbe essere necessario eseguire un'azione in base alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="7b9de-262">— MovedIpOrUrl: abbiamo spostato un indirizzo IP o un Url da questo set di endpoint a un altro.</span><span class="sxs-lookup"><span data-stu-id="7b9de-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="7b9de-263">In genere, non è necessario alcun intervento.</span><span class="sxs-lookup"><span data-stu-id="7b9de-263">Generally no action is required.</span></span>
  <span data-ttu-id="7b9de-264">— RemovedDuplicateIpOrUrl: abbiamo rimosso un indirizzo IP o URL duplicato ma questo è ancora pubblicato per Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b9de-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="7b9de-265">In genere, non è necessario alcun intervento.</span><span class="sxs-lookup"><span data-stu-id="7b9de-265">Generally no action is required.</span></span>
  <span data-ttu-id="7b9de-266">— OtherNonPriorityChanges: abbiamo modificato qualcosa di meno critico rispetto a tutte le altre opzioni, ad esempio il contenuto di un campo della nota.</span><span class="sxs-lookup"><span data-stu-id="7b9de-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="7b9de-267">Versione: versione del set di endpoint pubblicato in cui è stata introdotta la modifica.</span><span class="sxs-lookup"><span data-stu-id="7b9de-267">version — The version of the published endpoint set in which the change was introduced.</span></span> <span data-ttu-id="7b9de-268">I numeri delle versioni sono in formato _AAAAMMGGNN_, dove _NN_ è un numero naturale incrementabile se è necessario pubblicare più versioni in un singolo giorno.</span><span class="sxs-lookup"><span data-stu-id="7b9de-268">Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="7b9de-269">previous: una sottostruttura che descrive dettagliatamente i valori precedenti degli elementi modificati nel set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="7b9de-270">Non sarà inclusa per i set di endpoint appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="7b9de-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="7b9de-271">Include _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="7b9de-272">current: una sottostruttura che descrive dettagliatamente i valori aggiornati degli elementi di modifica nel set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="7b9de-273">Include _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="7b9de-274">add: una sottostruttura che descrive nel dettaglio gli elementi da aggiungere alle raccolte dei set di endpoint. </span><span class="sxs-lookup"><span data-stu-id="7b9de-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="7b9de-275">Questo elemento viene omesso se non ci sono aggiunte.</span><span class="sxs-lookup"><span data-stu-id="7b9de-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="7b9de-276">effectiveDate: definisce la data in cui le aggiunte saranno effettive nel servizio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="7b9de-277">ips: gli elementi da aggiungere alla matrice di _indirizzi IP_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="7b9de-278">urls: gli elementi da aggiungere alla matrice di _urls_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="7b9de-279">remove: una sottostruttura che descrive nel dettaglio gli elementi da rimuovere dal set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b9de-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="7b9de-280">Questo elemento viene omesso se non ci sono rimozioni.</span><span class="sxs-lookup"><span data-stu-id="7b9de-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="7b9de-281">ips: gli elementi da rimuovere dalla matrice di _indirizzi IP_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="7b9de-282">urls: gli elementi da rimuovere dalla matrice di _URL_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="7b9de-283">Esempi:</span><span class="sxs-lookup"><span data-stu-id="7b9de-283">Examples:</span></span>

<span data-ttu-id="7b9de-284">URI della richiesta di esempio 1: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p144">Richiede tutte le modifiche precedenti apportate all'istanza Worldwide del servizio di Office 365. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p144">This requests all previous changes to the Office 365 worldwide service instance. Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="7b9de-287">URI della richiesta di esempio 2: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7b9de-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7b9de-p145">Richiede le modifiche apportate all'istanza Worldwide di Office 365 a partire dalla versione specificata. In questo caso, la versione specificata è la più recente. Risultato dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="7b9de-p145">This requests changes since the specified version to the Office 365 Worldwide instance. In this case, the version specified is the latest. Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="7b9de-291">Script di PowerShell di esempio</span><span class="sxs-lookup"><span data-stu-id="7b9de-291">Example PowerShell Script</span></span>

<span data-ttu-id="7b9de-292">È possibile eseguire questo script di PowerShell per verificare se esistono attività da eseguire per ottenere dati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="7b9de-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="7b9de-293">È possibile eseguire lo script come attività programmata per verificare la necessità di un aggiornamento della versione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="7b9de-294">Per evitare un carico eccessivo nel servizio Web, provare a non eseguire lo script più di una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="7b9de-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="7b9de-295">Questo script consente di:</span><span class="sxs-lookup"><span data-stu-id="7b9de-295">The script does the following:</span></span>

- <span data-ttu-id="7b9de-296">Controlla il numero di versione degli endpoint di istanza correnti di Office 365 in tutto il mondo chiamando l'API REST per il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7b9de-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="7b9de-297">Verifica la presenza di un file di versione corrente _$Env:TEMP\O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="7b9de-298">Il percorso della variabile globale **$ENV: temp** in genere _è C:\Users\\< nomeutente\>\AppData\Local\Temp_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="7b9de-299">Se è la prima volta che si esegue lo script, lo script restituirà la versione corrente e tutti gli URL e gli indirizzi IP correnti, scriverà la versione di endpoint nel file _$Env:TEMP\O365_endpoints_latestversion.txt_ e gli endpoint l'output dei dati nel file _$Env:TEMP\O365_endpoints_data.txt_..</span><span class="sxs-lookup"><span data-stu-id="7b9de-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="7b9de-300">È possibile modificare il percorso e/o il nome del file di output modificando le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b9de-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="7b9de-301">In ogni successiva esecuzione dello script, se la versione più recente del servizio Web è identica alla versione del file _O365_endpoints_latestversion. txt_, lo script esce senza apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="7b9de-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="7b9de-302">Se la versione più recente del servizio Web è più recente della versione_O365_endpoints_latestversion.txt_, lo script restituirà gli endpoint e i filtri per la versione **Consenti** e **Ottimizza**endpoint di categoria, aggiorna la versione nel file _O365_endpoints_latestversion.txt_ e scrive i dati aggiornati nel file_O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="7b9de-303">Lo script genera un _ClientRequestId_ univoco per il computer in cui è stato eseguito e riutilizza questo ID tra più chiamate.</span><span class="sxs-lookup"><span data-stu-id="7b9de-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="7b9de-304">Questo ID viene archiviato nel file_O365_endpoints_latestversion. txt_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="7b9de-305">Per eseguire lo script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b9de-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="7b9de-306">Copiare lo script e salvarlo nel disco rigido locale o nel percorso dello script come_Get-O365WebServiceUpdates.ps1_.</span><span class="sxs-lookup"><span data-stu-id="7b9de-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="7b9de-307">Eseguire lo script nell'editor di script preferito, ad esempio il codice di PowerShell ISE o VS, o da una console di PowerShell con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7b9de-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="7b9de-308">Non sono disponibili parametri per passare allo script.</span><span class="sxs-lookup"><span data-stu-id="7b9de-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="7b9de-309">Script di Python di esempio</span><span class="sxs-lookup"><span data-stu-id="7b9de-309">Example Python Script</span></span>

<span data-ttu-id="7b9de-p150">Di seguito è riportato uno script di Python, testato con Python 3.6.3 su Windows 10, che è possibile eseguire per verificare se sono presenti azioni che è necessario effettuare per i dati aggiornati. Questo script controlla il numero di versione degli endpoint dell'istanza Worldwide di Office 365. Quando è presente una modifica, scarica gli endpoint e li filtra per quelli di categoria _Allow_ e _Optimize_. Inoltre, usa un ClientRequestId unico tra più chiamate e salva l'ultima versione trovata in un file temporaneo. È necessario chiamare questo script ogni ora per verificare la disponibilità di un aggiornamento della versione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-p150">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="7b9de-315">Controllo delle versioni dell'interfaccia del servizio Web</span><span class="sxs-lookup"><span data-stu-id="7b9de-315">Web Service interface versioning</span></span>

<span data-ttu-id="7b9de-316">In futuro potrebbero essere necessari aggiornamenti ai parametri o ai risultati di questi metodi di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7b9de-316">Updates to the parameters or results for these web service methods may be required in the future.</span></span> <span data-ttu-id="7b9de-317">Dopo la pubblicazione della versione della disponibilità generale di tali servizi Web, Microsoft adotterà misure ragionevoli per fornire un avviso anticipato agli aggiornamenti del materiale al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7b9de-317">After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service.</span></span> <span data-ttu-id="7b9de-318">Se Microsoft ritiene che un aggiornamento richiederà modifiche ai client che usano il servizio Web, Microsoft manterrà la versione precedente, ossia una versione posteriore, del servizio Web, disponibile per almeno 12 mesi dopo il rilascio della nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7b9de-318">When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version.</span></span> <span data-ttu-id="7b9de-319">I clienti che non eseguono l'aggiornamento durante quel periodo potrebbero non essere in grado di accedere al servizio Web e ai relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="7b9de-319">Customers who do not upgrade during that time may be unable to access the web service and its methods.</span></span> <span data-ttu-id="7b9de-320">I clienti devono accertarsi che i client del servizio Web continuino a funzionare senza errori se sono state apportate le modifiche seguenti alla firma dell'interfaccia del servizio Web:</span><span class="sxs-lookup"><span data-stu-id="7b9de-320">Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="7b9de-321">L'aggiunta di un nuovo parametro opzionale a un metodo Web esistente che non deve essere fornito dai client precedenti e che non influisce sul risultato ottenuto da un client precedente.</span><span class="sxs-lookup"><span data-stu-id="7b9de-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="7b9de-322">L'aggiunta di un nuovo attributo denominato in una delle colonne aggiuntive o in uno degli elementi REST della risposta nel CSV di risposta.</span><span class="sxs-lookup"><span data-stu-id="7b9de-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="7b9de-323">L'aggiunta di un nuovo metodo Web con un nuovo nome che non è chiamato dai client precedenti.</span><span class="sxs-lookup"><span data-stu-id="7b9de-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="7b9de-324">Notifiche sugli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="7b9de-324">Update notifications</span></span>

<span data-ttu-id="7b9de-325">Per ricevere notifiche tramite posta elettronica, è possibile usare diversi metodi, quando le modifiche apportate agli indirizzi IP e agli URL vengono pubblicate nel servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7b9de-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="7b9de-326">Per usare una soluzione di Microsoft Flow, vedere [Usare Microsoft Flow per ricevere un messaggio di posta elettronica per le modifiche apportate agli indirizzi IP e agli URL di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span><span class="sxs-lookup"><span data-stu-id="7b9de-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="7b9de-327">Per distribuire un'app logica di Azure con un modello ARM, [vedere notifica di aggiornamento di Office 365 (v 1.1)](https://aka.ms/ipurlws-updates-template).</span><span class="sxs-lookup"><span data-stu-id="7b9de-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="7b9de-328">Per scrivere uno script di notifica personalizzato con PowerShell, [vedere Invio-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span><span class="sxs-lookup"><span data-stu-id="7b9de-328">To write your own notification script using PowerShell, see [Send-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="7b9de-329">Esportare un file PAC Proxy</span><span class="sxs-lookup"><span data-stu-id="7b9de-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="7b9de-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) è uno script di PowerShell che legge gli ultimi endpoint di rete dall'indirizzo IP e dall'URL di Office 365 e crea un file PAC di esempio.</span><span class="sxs-lookup"><span data-stu-id="7b9de-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="7b9de-331">Per informazioni sull'uso di Get-PacFile, vedere [Usare un file PAC per il routing diretto del traffico vitale di Office 365](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="7b9de-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b9de-332">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7b9de-332">Related Topics</span></span>
  
[<span data-ttu-id="7b9de-333">URL e intervalli di indirizzi IP per Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="7b9de-334">Gestione degli endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="7b9de-335">Domande frequenti sugli endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="7b9de-336">Principi della connettività di rete di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="7b9de-337">Ottimizzazione delle prestazioni e della rete di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="7b9de-338">Valutazione della connettività di rete di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="7b9de-339">Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b9de-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="7b9de-340">Ottimizzazione della rete per Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b9de-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="7b9de-341">Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni</span><span class="sxs-lookup"><span data-stu-id="7b9de-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="7b9de-342">Piano di risoluzione dei problemi di prestazioni per Office 365</span><span class="sxs-lookup"><span data-stu-id="7b9de-342">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)
