---
title: Utilizzare la protezione di rete per impedire connessioni a siti non consentiti
description: Proteggere la rete impedendo agli utenti di accedere a indirizzi di rete sospetti e dannosi noti
keywords: Protezione di rete, exploit, sito Web dannoso, ip, dominio, domini
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.openlocfilehash: b6069d392da1b8610d018908d172dc27044baffc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061341"
---
# <a name="protect-your-network"></a><span data-ttu-id="573e8-104">Proteggere la rete</span><span class="sxs-lookup"><span data-stu-id="573e8-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="573e8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="573e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="573e8-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="573e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="573e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="573e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="573e8-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="573e8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="573e8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="573e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="573e8-110">La protezione di rete consente di ridurre la superficie di attacco dei dispositivi da eventi basati su Internet.</span><span class="sxs-lookup"><span data-stu-id="573e8-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="573e8-111">Impedisce ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet.</span><span class="sxs-lookup"><span data-stu-id="573e8-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="573e8-112">La protezione di rete espande l'ambito di [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) per bloccare tutto il traffico HTTP in uscita che tenta di connettersi a origini con reputazione scarsa (in base al dominio o al nome host).</span><span class="sxs-lookup"><span data-stu-id="573e8-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="573e8-113">La protezione di rete è supportata in Windows, a partire da Windows 10 versione 1709.</span><span class="sxs-lookup"><span data-stu-id="573e8-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="573e8-114">Per ulteriori informazioni su come abilitare la protezione di rete, vedere [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="573e8-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="573e8-115">Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.</span><span class="sxs-lookup"><span data-stu-id="573e8-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="573e8-116">Per informazioni sul funzionamento della protezione di rete, vedere il sito di test di Microsoft Defender ATP [all'indirizzo demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="573e8-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="573e8-117">La protezione di rete funziona in modo ottimale [con Microsoft Defender for Endpoint,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)che fornisce report dettagliati sugli eventi e i blocchi di protezione da exploit come parte degli scenari di analisi degli [avvisi.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="573e8-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="573e8-118">Quando la protezione di rete blocca una connessione, viene visualizzata una notifica dal Centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="573e8-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="573e8-119">Il team delle operazioni di sicurezza [può personalizzare la notifica](customize-attack-surface-reduction.md#customize-the-notification) con i dettagli e le informazioni di contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="573e8-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="573e8-120">Inoltre, le singole regole di riduzione della superficie di attacco possono essere abilitate e personalizzate in base a determinate tecniche da monitorare.</span><span class="sxs-lookup"><span data-stu-id="573e8-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="573e8-121">È inoltre possibile utilizzare la [modalità di controllo](audit-windows-defender.md) per valutare l'impatto della protezione di rete sull'organizzazione se fosse abilitata.</span><span class="sxs-lookup"><span data-stu-id="573e8-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="573e8-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="573e8-122">Requirements</span></span>

<span data-ttu-id="573e8-123">La protezione di rete richiede Windows 10 Pro o Enterprise e microsoft Defender Antivirus in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="573e8-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="573e8-124">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="573e8-124">Windows version</span></span> | <span data-ttu-id="573e8-125">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="573e8-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="573e8-126">Windows 10 versione 1709 o successiva</span><span class="sxs-lookup"><span data-stu-id="573e8-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="573e8-127">Windows Server 1803 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="573e8-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="573e8-128">[La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) di Microsoft Defender Antivirus e la protezione con distribuzione [cloud](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) devono essere abilitate</span><span class="sxs-lookup"><span data-stu-id="573e8-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="573e8-129">Dopo aver abilitato i servizi, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra i servizi e i dispositivi (denominati anche endpoint).</span><span class="sxs-lookup"><span data-stu-id="573e8-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="573e8-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="573e8-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="573e8-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="573e8-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="573e8-132">Esaminare gli eventi di protezione di rete in Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="573e8-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="573e8-133">Microsoft Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di analisi [degli avvisi.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="573e8-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="573e8-134">Puoi eseguire una query su Microsoft Defender per i dati dell'endpoint usando [Ricerca avanzata.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="573e8-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="573e8-135">Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di protezione di rete influirebbero sull'ambiente se fossero abilitate.</span><span class="sxs-lookup"><span data-stu-id="573e8-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="573e8-136">Ecco una query di esempio</span><span class="sxs-lookup"><span data-stu-id="573e8-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="573e8-137">Esaminare gli eventi di protezione di rete nel Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="573e8-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="573e8-138">È possibile esaminare il registro eventi di Windows per visualizzare gli eventi creati quando la protezione di rete blocca (o controlla) l'accesso a un IP o a un dominio dannoso:</span><span class="sxs-lookup"><span data-stu-id="573e8-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="573e8-139">[Copiare il codice XML direttamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="573e8-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="573e8-140">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="573e8-140">Select **OK**.</span></span>

<span data-ttu-id="573e8-141">Questa procedura crea una visualizzazione personalizzata che filtra in modo da visualizzare solo gli eventi seguenti correlati alla protezione di rete:</span><span class="sxs-lookup"><span data-stu-id="573e8-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="573e8-142">ID evento</span><span class="sxs-lookup"><span data-stu-id="573e8-142">Event ID</span></span> | <span data-ttu-id="573e8-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="573e8-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="573e8-144">5007</span><span class="sxs-lookup"><span data-stu-id="573e8-144">5007</span></span> | <span data-ttu-id="573e8-145">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="573e8-145">Event when settings are changed</span></span> |
| <span data-ttu-id="573e8-146">1125</span><span class="sxs-lookup"><span data-stu-id="573e8-146">1125</span></span> | <span data-ttu-id="573e8-147">Evento quando viene attivata la protezione di rete in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="573e8-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="573e8-148">1126</span><span class="sxs-lookup"><span data-stu-id="573e8-148">1126</span></span> | <span data-ttu-id="573e8-149">Evento quando viene attivata la protezione di rete in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="573e8-149">Event when network protection fires in block mode</span></span> |

## <a name="related-articles"></a><span data-ttu-id="573e8-150">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="573e8-150">Related articles</span></span>

- <span data-ttu-id="573e8-151">[Valutare i criteri di protezione](evaluate-network-protection.md) | Eseguire uno scenario rapido che illustra il funzionamento della funzionalità e gli eventi che in genere verrebbero creati.</span><span class="sxs-lookup"><span data-stu-id="573e8-151">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="573e8-152">[Abilitare la protezione di](enable-network-protection.md) rete | Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.</span><span class="sxs-lookup"><span data-stu-id="573e8-152">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
