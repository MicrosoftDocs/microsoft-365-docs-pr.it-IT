---
title: Monitorare e visualizzare i report-Centro sicurezza
description: In questo articolo viene descritto il modo in cui Microsoft 365 Security Center fornisce un riepilogo rapido dello stato di protezione e sicurezza.
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, stato
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356884"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="536e6-104">Monitorare e visualizzare i report nel centro sicurezza di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="536e6-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="536e6-105">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="536e6-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="536e6-106">È possibile [valutarla in un ambiente lab](https://aka.ms/mtp-trial-lab) o [eseguire il progetto pilota in produzione](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="536e6-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="536e6-107">Microsoft 365 Security Center fornisce un riepilogo degli Stati di protezione e sicurezza nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="536e6-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="536e6-108">Il Centro sicurezza include una sezione di **report** che contiene una serie di schede che coprono una vasta gamma di aree.</span><span class="sxs-lookup"><span data-stu-id="536e6-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="536e6-109">Gli analisti di sicurezza e gli amministratori possono monitorare le schede come parte delle operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="536e6-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="536e6-110">In drill-down, le schede forniscono report dettagliati e, in alcuni casi, le opzioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="536e6-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="536e6-111">Personalizzare le visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="536e6-111">Customize views</span></span>

<span data-ttu-id="536e6-112">Per impostazione predefinita, le schede sono raggruppate in queste categorie:</span><span class="sxs-lookup"><span data-stu-id="536e6-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="536e6-113">[Identità](monitor-and-report-identities.md) -account utente e credenziali</span><span class="sxs-lookup"><span data-stu-id="536e6-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="536e6-114">[Dati](monitor-data.md) -posta elettronica e contenuto del documento</span><span class="sxs-lookup"><span data-stu-id="536e6-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="536e6-115">[Dispositivi](monitor-devices.md) -computer, telefoni cellulari e altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="536e6-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="536e6-116">[Apps](monitor-apps.md) -programmi e servizi online associati</span><span class="sxs-lookup"><span data-stu-id="536e6-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="536e6-117">Passare a **Group by Topic**, per riorganizzare le schede e raggrupparle negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="536e6-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="536e6-118">**Risk** -card che evidenziano le entità, ad esempio account e dispositivi, che potrebbero essere a rischio.</span><span class="sxs-lookup"><span data-stu-id="536e6-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="536e6-119">Tali schede evidenziano anche possibili fonti di rischio, ad esempio le nuove campagne di minacce e le app Cloud privilegiate</span><span class="sxs-lookup"><span data-stu-id="536e6-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="536e6-120">**Tendenze di rilevamento** -schede che evidenziano nuove individuazioni di minacce, anomalie e violazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="536e6-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="536e6-121">Schede di **configurazione e integrità** che coprono la configurazione e la distribuzione dei controlli di sicurezza, compresi gli Stati di onboarding del dispositivo per i servizi di gestione</span><span class="sxs-lookup"><span data-stu-id="536e6-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="536e6-122">**Altro** : tutte le altre schede non categorizzate in altri argomenti</span><span class="sxs-lookup"><span data-stu-id="536e6-122">**Other** - all other cards not categorized under other topics</span></span>
