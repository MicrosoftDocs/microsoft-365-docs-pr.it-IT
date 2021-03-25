---
title: Monitoraggio della sicurezza dell'esplorazione Web in Microsoft Defender ATP
description: Usare la protezione Web in Microsoft Defender ATP per monitorare la sicurezza dell'esplorazione Web
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, monitoraggio, report, schede, elenco di domini, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5d5cb89bccb0d7ea0fa4891c3b5b0d11a7244cf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063706"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="9659d-104">Monitorare la sicurezza dell'esplorazione Web</span><span class="sxs-lookup"><span data-stu-id="9659d-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9659d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9659d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9659d-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9659d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9659d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9659d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9659d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9659d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9659d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9659d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="9659d-110">La protezione Web consente di monitorare la sicurezza dell'esplorazione Web dell'organizzazione tramite i report in Report **> protezione Web** in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="9659d-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9659d-111">Il report contiene schede che forniscono statistiche di rilevamento delle minacce Web.</span><span class="sxs-lookup"><span data-stu-id="9659d-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="9659d-112">**Rilevamenti di** Protezione dalle minacce Web nel tempo - Questa scheda tendenze visualizza il numero di minacce Web rilevate per tipo durante il periodo di tempo selezionato (Ultimi 30 giorni, Ultimi 3 mesi, Ultimi 6 mesi)</span><span class="sxs-lookup"><span data-stu-id="9659d-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Immagine della scheda che mostra i rilevamenti di protezione dalle minacce Web nel tempo](images/wtp-blocks-over-time.png)

- <span data-ttu-id="9659d-114">**Riepilogo di Protezione dalle** minacce Web: questa scheda visualizza i rilevamenti totali delle minacce Web negli ultimi 30 giorni, mostrando la distribuzione tra i diversi tipi di minacce Web.</span><span class="sxs-lookup"><span data-stu-id="9659d-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="9659d-115">Selezionando una sezione viene aperto l'elenco dei domini trovati con siti Web dannosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="9659d-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Immagine della scheda che mostra il riepilogo della protezione dalle minacce Web](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="9659d-117">Possono essere necessario fino a 12 ore prima che un blocco si rifletta nelle schede o nell'elenco dei domini.</span><span class="sxs-lookup"><span data-stu-id="9659d-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="9659d-118">Tipi di minacce Web</span><span class="sxs-lookup"><span data-stu-id="9659d-118">Types of web threats</span></span>

<span data-ttu-id="9659d-119">La protezione Web classifica i siti Web dannosi e indesiderati come:</span><span class="sxs-lookup"><span data-stu-id="9659d-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="9659d-120">**Phishing:** siti Web contenenti moduli Web contraffatti e altri meccanismi di phishing progettati per indurre gli utenti a divulgare credenziali e altre informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="9659d-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="9659d-121">**Dannoso:** siti Web che ospitano malware e codice di exploit</span><span class="sxs-lookup"><span data-stu-id="9659d-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="9659d-122">**Indicatore personalizzato** : siti Web i cui URL o domini sono stati aggiunti all'elenco [di indicatori personalizzati](manage-indicators.md) per il blocco</span><span class="sxs-lookup"><span data-stu-id="9659d-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="9659d-123">Visualizzare l'elenco dei domini</span><span class="sxs-lookup"><span data-stu-id="9659d-123">View the domain list</span></span>

<span data-ttu-id="9659d-124">Selezionare una categoria specifica di minacce Web nella **scheda di riepilogo** protezione dalle minacce Web per aprire la **pagina** Domini.</span><span class="sxs-lookup"><span data-stu-id="9659d-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="9659d-125">In questa pagina viene visualizzato l'elenco dei domini in tale categoria di minacce.</span><span class="sxs-lookup"><span data-stu-id="9659d-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="9659d-126">La pagina fornisce le informazioni seguenti per ogni dominio:</span><span class="sxs-lookup"><span data-stu-id="9659d-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="9659d-127">**Numero di** accessi - Numero di richieste di URL nel dominio</span><span class="sxs-lookup"><span data-stu-id="9659d-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="9659d-128">**Blocchi** : numero di volte in cui le richieste sono state bloccate</span><span class="sxs-lookup"><span data-stu-id="9659d-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="9659d-129">**Tendenza di accesso** - Modifica del numero di tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="9659d-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="9659d-130">**Categoria di minacce** - Tipo di minaccia Web</span><span class="sxs-lookup"><span data-stu-id="9659d-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="9659d-131">**Dispositivi** - Numero di dispositivi con tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="9659d-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="9659d-132">Seleziona un dominio per visualizzare l'elenco dei dispositivi che hanno tentato di accedere agli URL in tale dominio e l'elenco degli URL.</span><span class="sxs-lookup"><span data-stu-id="9659d-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9659d-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9659d-133">Related topics</span></span>

- [<span data-ttu-id="9659d-134">Panoramica della protezione Web</span><span class="sxs-lookup"><span data-stu-id="9659d-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="9659d-135">Filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="9659d-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="9659d-136">Protezione dalle minacce Web</span><span class="sxs-lookup"><span data-stu-id="9659d-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="9659d-137">Rispondere alle minacce Web</span><span class="sxs-lookup"><span data-stu-id="9659d-137">Respond to web threats</span></span>](web-protection-response.md)