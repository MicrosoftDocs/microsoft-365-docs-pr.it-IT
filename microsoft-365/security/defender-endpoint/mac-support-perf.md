---
title: Risolvere i problemi di prestazioni per Microsoft Defender ATP per Mac
description: Risolvere i problemi di prestazioni in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, prestazioni
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185910"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="763c5-104">Risolvere i problemi di prestazioni per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="763c5-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="763c5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="763c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="763c5-106">Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="763c5-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="763c5-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="763c5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="763c5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="763c5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="763c5-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="763c5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="763c5-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="763c5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="763c5-111">Questo argomento fornisce alcuni passaggi generali che possono essere usati per limitare i problemi di prestazioni correlati a Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="763c5-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="763c5-112">La protezione in tempo reale (RTP) è una funzionalità di Microsoft Defender per Endpoint per Mac che monitora e protegge continuamente il dispositivo dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="763c5-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="763c5-113">È costituito dal monitoraggio di file e processi e da altre euristiche.</span><span class="sxs-lookup"><span data-stu-id="763c5-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="763c5-114">A seconda delle applicazioni in esecuzione e delle caratteristiche del dispositivo, è possibile che si verifichino prestazioni non ottimali quando si esegue Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="763c5-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="763c5-115">In particolare, le applicazioni o i processi di sistema che accedono a molte risorse in un breve periodo di tempo possono causare problemi di prestazioni in Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="763c5-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="763c5-116">I passaggi seguenti possono essere utilizzati per risolvere e attenuare questi problemi:</span><span class="sxs-lookup"><span data-stu-id="763c5-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="763c5-117">Disabilitare la protezione in tempo reale utilizzando uno dei metodi seguenti e osservare se le prestazioni migliorano.</span><span class="sxs-lookup"><span data-stu-id="763c5-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="763c5-118">Questo approccio consente di stabilire se Microsoft Defender per Endpoint per Mac contribuisce ai problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="763c5-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="763c5-119">Se il dispositivo non è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="763c5-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="763c5-120">Dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="763c5-120">From the user interface.</span></span> <span data-ttu-id="763c5-121">Apri Microsoft Defender per Endpoint per Mac e passa a **Gestisci impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="763c5-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Schermata Gestisci protezione in tempo reale](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="763c5-123">Dal terminale.</span><span class="sxs-lookup"><span data-stu-id="763c5-123">From the Terminal.</span></span> <span data-ttu-id="763c5-124">Per motivi di sicurezza, questa operazione richiede l'elevazione.</span><span class="sxs-lookup"><span data-stu-id="763c5-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="763c5-125">Se il dispositivo è gestito dall'organizzazione, la protezione in tempo reale può essere disabilitata dall'amministratore usando le istruzioni in Impostare le preferenze per [Microsoft Defender per Endpoint per Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="763c5-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="763c5-126">Apri il Finder e passa a **Utilità**  >  **applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="763c5-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="763c5-127">Aprire **Monitoraggio attività** e analizzare le applicazioni che utilizzano le risorse del sistema.</span><span class="sxs-lookup"><span data-stu-id="763c5-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="763c5-128">Esempi tipici sono gli aggiornamenti software e i compilatori.</span><span class="sxs-lookup"><span data-stu-id="763c5-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="763c5-129">Configurare Microsoft Defender per Endpoint per Mac con esclusioni per i processi o le posizioni del disco che contribuiscono ai problemi di prestazioni e ri-abilitare la protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="763c5-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="763c5-130">Per [informazioni dettagliate, vedi](mac-exclusions.md) Configurare e convalidare le esclusioni per Microsoft Defender per Endpoint per Mac.</span><span class="sxs-lookup"><span data-stu-id="763c5-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
