---
title: Monitorare e visualizzare i report - Centro sicurezza
description: Descrive in che modo il Centro sicurezza Microsoft 365 fornisce un riepilogo rapido dello stato di protezione e sicurezza.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, stato
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930403"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="12852-104">Monitorare e visualizzare i report nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12852-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="12852-105">Si vuole provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="12852-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="12852-106">È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="12852-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="12852-107">Il Centro sicurezza Microsoft 365 fornisce un riepilogo degli stati di protezione e sicurezza nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12852-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="12852-108">Il Centro sicurezza include una **sezione Report** che include una serie di schede che coprono un'ampia gamma di aree.</span><span class="sxs-lookup"><span data-stu-id="12852-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="12852-109">Gli analisti e gli amministratori della sicurezza possono tenere traccia delle schede nell'ambito delle operazioni quotidiane.</span><span class="sxs-lookup"><span data-stu-id="12852-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="12852-110">Nel drill-down le schede forniscono report dettagliati e, in alcuni casi, opzioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="12852-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="12852-111">Personalizzare le visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="12852-111">Customize views</span></span>

<span data-ttu-id="12852-112">Per impostazione predefinita, le schede sono raggruppate in queste categorie:</span><span class="sxs-lookup"><span data-stu-id="12852-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="12852-113">[Identità](monitor-and-report-identities.md) - account utente e credenziali</span><span class="sxs-lookup"><span data-stu-id="12852-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="12852-114">[Dati](monitor-data.md) - posta elettronica e contenuto del documento</span><span class="sxs-lookup"><span data-stu-id="12852-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="12852-115">[Dispositivi](monitor-devices.md) - computer, telefoni cellulari e altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="12852-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="12852-116">[App](monitor-apps.md) - programmi e servizi online allegati</span><span class="sxs-lookup"><span data-stu-id="12852-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="12852-117">Passare a **Raggruppa per argomento** per riorganizzare le schede e raggrupparle negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="12852-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="12852-118">**Rischio:** schede che evidenziano entità, ad esempio account e dispositivi, che potrebbero essere a rischio.</span><span class="sxs-lookup"><span data-stu-id="12852-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="12852-119">Queste schede evidenziano anche le possibili fonti di rischio, ad esempio nuove campagne per le minacce e app cloud privilegiate</span><span class="sxs-lookup"><span data-stu-id="12852-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="12852-120">**Tendenze di rilevamento** - schede che evidenziano nuovi rilevamenti di minacce, anomalie e violazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="12852-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="12852-121">**Configurazione e integrità:** schede che coprono la configurazione e la distribuzione dei controlli di sicurezza, inclusi gli stati di onboarding dei dispositivi nei servizi di gestione</span><span class="sxs-lookup"><span data-stu-id="12852-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="12852-122">**Altro:** tutte le altre schede non classificate in altri argomenti</span><span class="sxs-lookup"><span data-stu-id="12852-122">**Other** - all other cards not categorized under other topics</span></span>
