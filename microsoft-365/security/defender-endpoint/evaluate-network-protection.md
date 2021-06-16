---
title: Valutare la protezione di rete
description: Scopri come funziona la protezione di rete testando scenari comuni da cui protegge.
keywords: Protezione di rete, exploit, sito Web dannoso, ip, dominio, domini, valutare, testare, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 03d05966401c8f3a8bdcec413e85c9a6d2a3ec5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926572"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="85f62-104">Valutare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="85f62-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="85f62-105">**Applies to:**</span></span>
- [<span data-ttu-id="85f62-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="85f62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="85f62-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85f62-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="85f62-108">[La protezione di](network-protection.md) rete consente di impedire ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet.</span><span class="sxs-lookup"><span data-stu-id="85f62-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="85f62-109">Questo articolo consente di valutare la protezione di rete abilitando la funzionalità e guidando l'utente a un sito di testing.</span><span class="sxs-lookup"><span data-stu-id="85f62-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="85f62-110">I siti in questo articolo di valutazione non sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="85f62-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="85f62-111">Sono siti Web creati appositamente che fingono di essere dannosi.</span><span class="sxs-lookup"><span data-stu-id="85f62-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="85f62-112">Il sito replica il comportamento che si verifica se un utente visita un sito o un dominio dannoso.</span><span class="sxs-lookup"><span data-stu-id="85f62-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="85f62-113">Puoi anche visitare il sito Web Microsoft Defender Testground [all'demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per vedere come funzionano le altre funzionalità di protezione.</span><span class="sxs-lookup"><span data-stu-id="85f62-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="85f62-114">Abilitare la protezione di rete in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="85f62-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="85f62-115">Abilitare la protezione di rete in modalità di controllo per vedere quali indirizzi IP e domini sarebbero stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="85f62-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="85f62-116">Puoi assicurarti che non influisca sulle app line-of-business o avere un'idea della frequenza con cui si verificano i blocchi.</span><span class="sxs-lookup"><span data-stu-id="85f62-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="85f62-117">Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**</span><span class="sxs-lookup"><span data-stu-id="85f62-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="85f62-118">Immettere il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="85f62-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="85f62-119">Visitare un dominio dannoso (falso)</span><span class="sxs-lookup"><span data-stu-id="85f62-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="85f62-120">Apri Internet Explorer, Google Chrome o qualsiasi altro browser di tua scelta.</span><span class="sxs-lookup"><span data-stu-id="85f62-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="85f62-121">Vai a [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="85f62-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="85f62-122">La connessione di rete sarà consentita e verrà visualizzato un messaggio di prova.</span><span class="sxs-lookup"><span data-stu-id="85f62-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Notifica di esempio che indica connessione bloccata: l'amministratore IT ha Sicurezza di Windows bloccare questa connessione di rete.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="85f62-125">Esaminare gli eventi di protezione di rete nel Visualizzatore Windows eventi</span><span class="sxs-lookup"><span data-stu-id="85f62-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="85f62-126">Per esaminare le app che sarebbero state bloccate, aprire il Visualizzatore eventi e filtrare l'ID evento 1125 nel registro microsoft-Windows-Windows-Defender/Operativo.</span><span class="sxs-lookup"><span data-stu-id="85f62-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="85f62-127">Nella tabella seguente sono elencati tutti gli eventi di protezione di rete.</span><span class="sxs-lookup"><span data-stu-id="85f62-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="85f62-128">ID evento</span><span class="sxs-lookup"><span data-stu-id="85f62-128">Event ID</span></span> | <span data-ttu-id="85f62-129">Provide/Source</span><span class="sxs-lookup"><span data-stu-id="85f62-129">Provide/Source</span></span> | <span data-ttu-id="85f62-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85f62-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="85f62-131">5007</span><span class="sxs-lookup"><span data-stu-id="85f62-131">5007</span></span> | <span data-ttu-id="85f62-132">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="85f62-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="85f62-133">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="85f62-133">Event when settings are changed</span></span> |
|<span data-ttu-id="85f62-134">1125</span><span class="sxs-lookup"><span data-stu-id="85f62-134">1125</span></span> | <span data-ttu-id="85f62-135">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="85f62-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="85f62-136">Evento quando viene verificata una connessione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="85f62-137">1126</span><span class="sxs-lookup"><span data-stu-id="85f62-137">1126</span></span> | <span data-ttu-id="85f62-138">Windows Defender (operativo)</span><span class="sxs-lookup"><span data-stu-id="85f62-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="85f62-139">Evento quando viene bloccata una connessione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="85f62-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85f62-140">See also</span></span>

* [<span data-ttu-id="85f62-141">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="85f62-142">Abilitare la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="85f62-143">Risolvere i problemi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="85f62-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
