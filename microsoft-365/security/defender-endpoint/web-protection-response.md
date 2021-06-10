---
title: Rispondere alle minacce Web in Microsoft Defender for Endpoint
description: Rispondere agli avvisi relativi a siti Web dannosi e indesiderati. Comprendere in che modo Protezione dalle minacce Web informa gli utenti finali tramite i propri Web browser e Windows notifiche
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, avvisi, risposta, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser, notifiche, utenti finali, notifiche Windows, pagina di blocco,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688478"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="bc121-105">Rispondere alle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="bc121-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc121-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bc121-106">**Applies to:**</span></span>
- [<span data-ttu-id="bc121-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bc121-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc121-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc121-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bc121-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bc121-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc121-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="bc121-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="bc121-111">La protezione Web in Microsoft Defender for Endpoint consente di analizzare e rispondere in modo efficiente agli avvisi relativi a siti Web e siti Web dannosi nell'elenco di indicatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bc121-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="bc121-112">Visualizzare gli avvisi relativi alle minacce Web</span><span class="sxs-lookup"><span data-stu-id="bc121-112">View web threat alerts</span></span>
<span data-ttu-id="bc121-113">Microsoft Defender for Endpoint genera gli avvisi [seguenti per](manage-alerts.md) attività Web dannose o sospette:</span><span class="sxs-lookup"><span data-stu-id="bc121-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="bc121-114">**Connessione sospetta bloccata dalla** protezione di rete: questo avviso viene generato quando un tentativo  di accedere a un sito Web dannoso o a un sito Web nell'elenco di indicatori personalizzati viene arrestato dalla protezione di rete in *modalità* blocco</span><span class="sxs-lookup"><span data-stu-id="bc121-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="bc121-115">**Connessione sospetta rilevata** dalla protezione di rete: questo avviso viene generato quando un tentativo di accedere a un sito Web dannoso o a un sito Web nell'elenco di indicatori personalizzati viene rilevato dalla protezione di rete in *modalità solo* controllo</span><span class="sxs-lookup"><span data-stu-id="bc121-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="bc121-116">Ogni avviso fornisce le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc121-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="bc121-117">Dispositivo che ha tentato di accedere al sito Web bloccato</span><span class="sxs-lookup"><span data-stu-id="bc121-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="bc121-118">Applicazione o programma utilizzato per inviare la richiesta Web</span><span class="sxs-lookup"><span data-stu-id="bc121-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="bc121-119">URL o URL dannoso nell'elenco degli indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="bc121-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="bc121-120">Azioni consigliate per i risponditori</span><span class="sxs-lookup"><span data-stu-id="bc121-120">Recommended actions for responders</span></span>

![Immagine di un avviso relativo alla protezione dalle minacce Web](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="bc121-122">Per ridurre il volume di avvisi, Microsoft Defender for Endpoint consolida i rilevamenti di minacce Web per lo stesso dominio nello stesso dispositivo ogni giorno in un singolo avviso.</span><span class="sxs-lookup"><span data-stu-id="bc121-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="bc121-123">Nel report di protezione Web viene generato e conteggiato [un solo avviso.](web-protection-monitoring.md)</span><span class="sxs-lookup"><span data-stu-id="bc121-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="bc121-124">Esaminare i dettagli del sito Web</span><span class="sxs-lookup"><span data-stu-id="bc121-124">Inspect website details</span></span>
<span data-ttu-id="bc121-125">Puoi approfondire selezionando l'URL o il dominio del sito Web nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="bc121-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="bc121-126">Verrà aperta una pagina sull'URL o sul dominio specifico con diverse informazioni, tra cui:</span><span class="sxs-lookup"><span data-stu-id="bc121-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="bc121-127">Dispositivi che hanno tentato di accedere al sito Web</span><span class="sxs-lookup"><span data-stu-id="bc121-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="bc121-128">Eventi imprevisti e avvisi correlati al sito Web</span><span class="sxs-lookup"><span data-stu-id="bc121-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="bc121-129">Frequenza con cui il sito Web è stato visualizzato negli eventi dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bc121-129">How frequent the website was seen in events in your organization</span></span>

    ![Immagine della pagina dei dettagli del dominio o dell'entità URL](images/wtp-website-details.png)

[<span data-ttu-id="bc121-131">Altre informazioni sulle pagine dell'URL o dell'entità di dominio</span><span class="sxs-lookup"><span data-stu-id="bc121-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="bc121-132">Esaminare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc121-132">Inspect the device</span></span>
<span data-ttu-id="bc121-133">Puoi anche controllare il dispositivo che ha tentato di accedere a un URL bloccato.</span><span class="sxs-lookup"><span data-stu-id="bc121-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="bc121-134">Selezionando il nome del dispositivo nella pagina di avviso si apre una pagina con informazioni complete sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc121-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="bc121-135">Altre informazioni sulle pagine dell'entità dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc121-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="bc121-136">Web browser e notifiche Windows per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="bc121-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="bc121-137">Con la protezione Web in Microsoft Defender for Endpoint, agli utenti finali verrà impedito di visitare siti Web dannosi o indesiderati Microsoft Edge o altri browser.</span><span class="sxs-lookup"><span data-stu-id="bc121-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="bc121-138">Poiché il blocco viene eseguito dalla [protezione di](network-protection.md)rete, verrà visualizzato un errore generico dal Web browser.</span><span class="sxs-lookup"><span data-stu-id="bc121-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="bc121-139">Verrà inoltre visualizzata una notifica da Windows.</span><span class="sxs-lookup"><span data-stu-id="bc121-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="bc121-140">![Immagine di Microsoft Edge che mostra un errore 403 e la minaccia Web di Windows di notifica bloccata su ](images/wtp-browser-blocking-page.png)
 *Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="bc121-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="bc121-141">![Immagine del Web browser Chrome che mostra un avviso di connessione sicura e Windows ](images/wtp-chrome-browser-blocking-page.png)
 *web threat bloccata su Chrome*</span><span class="sxs-lookup"><span data-stu-id="bc121-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc121-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bc121-142">Related topics</span></span>
- [<span data-ttu-id="bc121-143">Panoramica protezione Web</span><span class="sxs-lookup"><span data-stu-id="bc121-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="bc121-144">Filtro contenuti Web</span><span class="sxs-lookup"><span data-stu-id="bc121-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="bc121-145">Protezione dalle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="bc121-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="bc121-146">Monitorare la sicurezza sul Web</span><span class="sxs-lookup"><span data-stu-id="bc121-146">Monitor web security</span></span>](web-protection-monitoring.md)
