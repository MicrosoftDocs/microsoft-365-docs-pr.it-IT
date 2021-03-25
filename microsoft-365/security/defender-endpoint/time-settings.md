---
title: Impostazioni del fuso orario di Microsoft Defender Security Center
description: Usa le informazioni contenute qui per configurare le impostazioni del fuso orario di Microsoft Defender Security Center e visualizzare le informazioni sulla licenza.
keywords: impostazioni, Microsoft Defender, cybersecurity threat intelligence, protezione avanzata dalle minacce, fuso orario, utc, ora locale, licenza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c6338155aae3605ac5721958363b8c2d86618d9b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183850"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="736dd-104">Impostazioni del fuso orario di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="736dd-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="736dd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="736dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="736dd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="736dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="736dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="736dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="736dd-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="736dd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="736dd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="736dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="736dd-110">Usa il menu **Fuso orario** Impostazioni fuso orario icon1 per configurare il fuso orario e visualizzare le informazioni ![ sulla ](images/atp-time-zone.png) licenza.</span><span class="sxs-lookup"><span data-stu-id="736dd-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="736dd-111">Impostazioni fuso orario</span><span class="sxs-lookup"><span data-stu-id="736dd-111">Time zone settings</span></span>
<span data-ttu-id="736dd-112">L'aspetto del tempo è importante nella valutazione e nell'analisi degli attacchi informatici percepiti ed effettivi.</span><span class="sxs-lookup"><span data-stu-id="736dd-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="736dd-113">Le indagini cyberforensiche spesso si basano su indicatori di data e ora per riunire la sequenza di eventi.</span><span class="sxs-lookup"><span data-stu-id="736dd-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="736dd-114">È importante che il sistema rifletta le impostazioni corrette del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="736dd-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="736dd-115">Microsoft Defender for Endpoint può visualizzare l'ora UTC (Coordinated Universal Time) o l'ora locale.</span><span class="sxs-lookup"><span data-stu-id="736dd-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="736dd-116">L'impostazione del fuso orario corrente viene visualizzata nel menu Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="736dd-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="736dd-117">È possibile modificare il fuso orario visualizzato nel menu **Fuso** orario.</span><span class="sxs-lookup"><span data-stu-id="736dd-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Icona Impostazioni fuso orario2](images/atp-time-zone-menu.png)<span data-ttu-id="736dd-119">.</span><span class="sxs-lookup"><span data-stu-id="736dd-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="736dd-120">Fuso orario UTC</span><span class="sxs-lookup"><span data-stu-id="736dd-120">UTC time zone</span></span>
<span data-ttu-id="736dd-121">Microsoft Defender for Endpoint usa l'ora UTC per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="736dd-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="736dd-122">Se si imposta il fuso orario di Microsoft Defender per Endpoint su UTC, verranno visualizzati tutti i timestamp di sistema (avvisi, eventi e altri) in formato UTC per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="736dd-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="736dd-123">Questo può aiutare gli analisti della sicurezza che lavorano in diverse località in tutto il mondo a usare gli stessi indicatori di data e ora durante l'analisi degli eventi.</span><span class="sxs-lookup"><span data-stu-id="736dd-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="736dd-124">Fuso orario locale</span><span class="sxs-lookup"><span data-stu-id="736dd-124">Local time zone</span></span>
<span data-ttu-id="736dd-125">Puoi scegliere di fare in modo che Microsoft Defender for Endpoint usi le impostazioni del fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="736dd-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="736dd-126">Tutti gli avvisi e gli eventi verranno visualizzati utilizzando il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="736dd-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="736dd-127">Il fuso orario locale viene preso dalle impostazioni internazionali del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="736dd-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="736dd-128">Se si modificano le impostazioni internazionali, verrà modificato anche il fuso orario di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="736dd-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="736dd-129">Se si sceglie questa impostazione, i timestamp visualizzati in Microsoft Defender for Endpoint verranno allineati all'ora locale per tutti gli utenti di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="736dd-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="736dd-130">Gli analisti che si trovano in diverse posizioni globali ora visualizzano gli avvisi di Microsoft Defender for Endpoint in base alle impostazioni internazionali.</span><span class="sxs-lookup"><span data-stu-id="736dd-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="736dd-131">La scelta di utilizzare l'ora locale può essere utile se gli analisti si trovano in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="736dd-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="736dd-132">In questo caso potrebbe essere più facile correlare gli eventi all'ora locale, ad esempio quando un utente locale fa clic su un collegamento di posta elettronica sospetto.</span><span class="sxs-lookup"><span data-stu-id="736dd-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="736dd-133">Impostare il fuso orario</span><span class="sxs-lookup"><span data-stu-id="736dd-133">Set the time zone</span></span>
<span data-ttu-id="736dd-134">Il fuso orario di Microsoft Defender for Endpoint è impostato per impostazione predefinita su UTC.</span><span class="sxs-lookup"><span data-stu-id="736dd-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="736dd-135">L'impostazione del fuso orario cambia anche gli orari per tutte le visualizzazioni di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="736dd-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="736dd-136">Per impostare il fuso orario:</span><span class="sxs-lookup"><span data-stu-id="736dd-136">To set the time zone:</span></span>

1. <span data-ttu-id="736dd-137">Fare clic sul menu **Fuso orario** Icona Impostazioni ![ fuso ](images/atp-time-zone.png) orario3.</span><span class="sxs-lookup"><span data-stu-id="736dd-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="736dd-138">Selezionare **l'indicatore UTC fuso orario.**</span><span class="sxs-lookup"><span data-stu-id="736dd-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="736dd-139">Selezionare **Fuso orario UTC** o il fuso orario locale, ad esempio -7:00.</span><span class="sxs-lookup"><span data-stu-id="736dd-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="736dd-140">Impostazioni internazionali</span><span class="sxs-lookup"><span data-stu-id="736dd-140">Regional settings</span></span>
<span data-ttu-id="736dd-141">Per applicare formati di data diversi per Microsoft Defender for Endpoint, usa le impostazioni internazionali per Internet Explorer (IE) e Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="736dd-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="736dd-142">Se si usa un altro browser, ad esempio Google Chrome, seguire i passaggi necessari per modificare le impostazioni di data e ora per tale browser.</span><span class="sxs-lookup"><span data-stu-id="736dd-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="736dd-143">**Internet Explorer (IE) e Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="736dd-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="736dd-144">IE e Microsoft Edge usano **le impostazioni area** geografica configurate nell'opzione **Orologi,** lingua e area geografica nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="736dd-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="736dd-145">Problemi noti con i formati regionali</span><span class="sxs-lookup"><span data-stu-id="736dd-145">Known issues with regional formats</span></span>

<span data-ttu-id="736dd-146">**Formati di data e ora**</span><span class="sxs-lookup"><span data-stu-id="736dd-146">**Date and time formats**</span></span><br>
<span data-ttu-id="736dd-147">Esistono alcuni problemi noti relativi ai formati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="736dd-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="736dd-148">Se si configurano le impostazioni internazionali in un formato diverso dai formati supportati, il portale potrebbe non riflettere correttamente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="736dd-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="736dd-149">Sono supportati i formati di data e ora seguenti:</span><span class="sxs-lookup"><span data-stu-id="736dd-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="736dd-150">Formato data MM/gg/aaaa</span><span class="sxs-lookup"><span data-stu-id="736dd-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="736dd-151">Formato data gg/MM/aaaa</span><span class="sxs-lookup"><span data-stu-id="736dd-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="736dd-152">Formato ora hh:mm:ss (formato 12 ore)</span><span class="sxs-lookup"><span data-stu-id="736dd-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="736dd-153">I formati di data e ora seguenti non sono attualmente supportati:</span><span class="sxs-lookup"><span data-stu-id="736dd-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="736dd-154">Formato data aaaa-MM-gg</span><span class="sxs-lookup"><span data-stu-id="736dd-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="736dd-155">Formato data d-MMM-aa</span><span class="sxs-lookup"><span data-stu-id="736dd-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="736dd-156">Formato data gg/MM/aa</span><span class="sxs-lookup"><span data-stu-id="736dd-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="736dd-157">Formato data MM/gg/aa</span><span class="sxs-lookup"><span data-stu-id="736dd-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="736dd-158">Formato data con yy.</span><span class="sxs-lookup"><span data-stu-id="736dd-158">Date format with yy.</span></span> <span data-ttu-id="736dd-159">Mostrerà solo aaaa.</span><span class="sxs-lookup"><span data-stu-id="736dd-159">Will only show yyyy.</span></span>
- <span data-ttu-id="736dd-160">Formato ora HH:mm:ss (formato 24 ore)</span><span class="sxs-lookup"><span data-stu-id="736dd-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="736dd-161">**Simbolo decimale utilizzato nei numeri**</span><span class="sxs-lookup"><span data-stu-id="736dd-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="736dd-162">Il simbolo decimale utilizzato è sempre un punto, anche se è selezionata una virgola nelle **impostazioni** formato numeri in **Impostazioni** area geografica.</span><span class="sxs-lookup"><span data-stu-id="736dd-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="736dd-163">Ad esempio, 15,5K viene visualizzato come 15,5K.</span><span class="sxs-lookup"><span data-stu-id="736dd-163">For example, 15,5K is displayed as 15.5K.</span></span>


