---
title: Monitorare e segnalare la protezione di Microsoft Defender Antivirus
description: Usa Configuration Manager o gli strumenti siem (Security Information and Event Management) per usare i report e monitorare Microsoft Defender AV con PowerShell e WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269589"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="f8cd0-104">Creare report in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f8cd0-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8cd0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f8cd0-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8cd0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f8cd0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f8cd0-107">Microsoft Defender Antivirus è integrato in Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="f8cd0-108">Microsoft Defender Antivirus è della protezione di nuova generazione in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f8cd0-109">La protezione di nuova generazione consente di proteggere i dispositivi da minacce software come virus, malware e spyware nella posta elettronica, nelle app, nel cloud e nel Web.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="f8cd0-110">Con Microsoft Defender Antivirus, sono disponibili diverse opzioni per esaminare lo stato di protezione e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="f8cd0-111">Puoi usare Microsoft Endpoint Manager per monitorare [Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) o creare avvisi di posta [elettronica.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="f8cd0-112">In caso contrario, è possibile monitorare la protezione [con Microsoft Intune.](/intune/introduction-intune)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="f8cd0-113">Microsoft Operations Management Suite include un componente aggiuntivo Conformità aggiornamenti [che](/windows/deployment/update/update-compliance-get-started) segnala i principali problemi di Microsoft Defender Antivirus, inclusi gli aggiornamenti della protezione e le impostazioni di protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="f8cd0-114">Se si dispone di un server SIEM (Security Information and Event Management) di terze parti, è inoltre possibile utilizzare Windows Defender [eventi client.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="f8cd0-115">Gli eventi di Windows includono diverse origini eventi di sicurezza, tra cui gli eventi [](/windows/device-security/auditing/security-auditing-overview) di Gestione account di sicurezza (SAM, Security Account Manager) (per[Windows 10,](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)vedi anche l'argomento Controllo della sicurezza) e [Windows Defender eventi.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f8cd0-116">Questi eventi possono essere aggregati centralmente tramite [l'agente di raccolta eventi di Windows.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="f8cd0-117">Spesso, i server SIEM dispongono di connettori per gli eventi di Windows, consentendo di correlare tutti gli eventi di sicurezza nel server SIEM.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="f8cd0-118">Puoi anche monitorare [gli eventi di malware usando la soluzione di valutazione malware in Log Analytics.](/azure/log-analytics/log-analytics-malware)</span><span class="sxs-lookup"><span data-stu-id="f8cd0-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="f8cd0-119">Per il monitoraggio o la determinazione dello stato con PowerShell, WMI o Microsoft Azure, vedere [la tabella delle opzioni di distribuzione,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)gestione e creazione di report.</span><span class="sxs-lookup"><span data-stu-id="f8cd0-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="f8cd0-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f8cd0-120">Related articles</span></span>

- [<span data-ttu-id="f8cd0-121">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f8cd0-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="f8cd0-122">Antivirus Microsoft Defender in Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="f8cd0-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="f8cd0-123">Distribuire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f8cd0-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)