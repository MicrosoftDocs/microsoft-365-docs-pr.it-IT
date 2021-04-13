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
ms.topic: how-to
ms.openlocfilehash: ae7dbea7d476e8a8f6198378e1d1bb29e24c37a2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688346"
---
# <a name="protect-your-network"></a><span data-ttu-id="9984a-104">Proteggere la rete</span><span class="sxs-lookup"><span data-stu-id="9984a-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9984a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9984a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9984a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9984a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9984a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9984a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9984a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9984a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9984a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9984a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9984a-110">La protezione di rete consente di ridurre la superficie di attacco dei dispositivi da eventi basati su Internet.</span><span class="sxs-lookup"><span data-stu-id="9984a-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="9984a-111">Impedisce ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet.</span><span class="sxs-lookup"><span data-stu-id="9984a-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="9984a-112">La protezione di rete espande l'ambito di [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) per bloccare tutto il traffico HTTP in uscita che tenta di connettersi a origini con reputazione scarsa (in base al dominio o al nome host).</span><span class="sxs-lookup"><span data-stu-id="9984a-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="9984a-113">La protezione di rete è supportata in Windows, a partire da Windows 10 versione 1709.</span><span class="sxs-lookup"><span data-stu-id="9984a-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="9984a-114">La protezione di rete non è ancora supportata in altri sistemi operativi, ma la protezione Web è supportata con il nuovo Microsoft Edge basato su Chromium.</span><span class="sxs-lookup"><span data-stu-id="9984a-114">Network protection is not yet supported on other operating systems, but web protection is supported using th new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="9984a-115">Per ulteriori informazioni, vedere [Protezione Web.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9984a-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="9984a-116">la protezione di rete estende la protezione della [protezione Web](web-protection-overview.md) al livello del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9984a-116">network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="9984a-117">Fornisce funzionalità di protezione Web in Edge ad altri browser supportati e applicazioni non browser.</span><span class="sxs-lookup"><span data-stu-id="9984a-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="9984a-118">Inoltre, la protezione di rete fornisce visibilità e blocco degli indicatori di compromissione (I/O) se usati con il rilevamento [e la risposta degli endpoint.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="9984a-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="9984a-119">Ad esempio, la protezione di rete funziona con [gli indicatori personalizzati](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="9984a-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="9984a-120">Per ulteriori informazioni su come abilitare la protezione di rete, vedere [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="9984a-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="9984a-121">Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.</span><span class="sxs-lookup"><span data-stu-id="9984a-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="9984a-122">Per informazioni sul funzionamento della protezione di rete, vedere il sito di test di Microsoft Defender ATP [all'indirizzo demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)</span><span class="sxs-lookup"><span data-stu-id="9984a-122">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="9984a-123">La protezione di rete funziona in modo ottimale [con Microsoft Defender for Endpoint,](microsoft-defender-endpoint.md)che fornisce report dettagliati sugli eventi e i blocchi di protezione da exploit come parte degli scenari di analisi degli [avvisi.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9984a-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="9984a-124">Quando la protezione di rete blocca una connessione, viene visualizzata una notifica dal Centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="9984a-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="9984a-125">Il team delle operazioni di sicurezza [può personalizzare la notifica](customize-attack-surface-reduction.md#customize-the-notification) con i dettagli e le informazioni di contatto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9984a-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="9984a-126">Inoltre, le singole regole di riduzione della superficie di attacco possono essere abilitate e personalizzate in base a determinate tecniche da monitorare.</span><span class="sxs-lookup"><span data-stu-id="9984a-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="9984a-127">È inoltre possibile utilizzare la [modalità di controllo](audit-windows-defender.md) per valutare l'impatto della protezione di rete sull'organizzazione se fosse abilitata.</span><span class="sxs-lookup"><span data-stu-id="9984a-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="9984a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9984a-128">Requirements</span></span>

<span data-ttu-id="9984a-129">La protezione di rete richiede Windows 10 Pro o Enterprise e microsoft Defender Antivirus in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9984a-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="9984a-130">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="9984a-130">Windows version</span></span> | <span data-ttu-id="9984a-131">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9984a-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="9984a-132">Windows 10 versione 1709 o successiva</span><span class="sxs-lookup"><span data-stu-id="9984a-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="9984a-133">Windows Server 1803 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="9984a-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="9984a-134">[La protezione in tempo reale](configure-real-time-protection-microsoft-defender-antivirus.md) di Microsoft Defender Antivirus e la protezione con distribuzione [cloud](enable-cloud-protection-microsoft-defender-antivirus.md) devono essere abilitate</span><span class="sxs-lookup"><span data-stu-id="9984a-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="9984a-135">Dopo aver abilitato i servizi, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra i servizi e i dispositivi (denominati anche endpoint).</span><span class="sxs-lookup"><span data-stu-id="9984a-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="9984a-136">Esaminare gli eventi di protezione di rete in Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="9984a-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="9984a-137">Microsoft Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di analisi [degli avvisi.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="9984a-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="9984a-138">Puoi eseguire query su Microsoft Defender per i dati dell'endpoint usando [la ricerca avanzata.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9984a-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="9984a-139">Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di protezione di rete influirebbero sull'ambiente se fossero abilitate.</span><span class="sxs-lookup"><span data-stu-id="9984a-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="9984a-140">Ecco una query di esempio</span><span class="sxs-lookup"><span data-stu-id="9984a-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="9984a-141">Esaminare gli eventi di protezione di rete nel Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="9984a-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="9984a-142">È possibile esaminare il registro eventi di Windows per visualizzare gli eventi creati quando la protezione di rete blocca (o controlla) l'accesso a un IP o a un dominio dannoso:</span><span class="sxs-lookup"><span data-stu-id="9984a-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="9984a-143">[Copiare il codice XML direttamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="9984a-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="9984a-144">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9984a-144">Select **OK**.</span></span>

<span data-ttu-id="9984a-145">Questa procedura crea una visualizzazione personalizzata che filtra in modo da visualizzare solo gli eventi seguenti correlati alla protezione di rete:</span><span class="sxs-lookup"><span data-stu-id="9984a-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="9984a-146">ID evento</span><span class="sxs-lookup"><span data-stu-id="9984a-146">Event ID</span></span> | <span data-ttu-id="9984a-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9984a-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="9984a-148">5007</span><span class="sxs-lookup"><span data-stu-id="9984a-148">5007</span></span> | <span data-ttu-id="9984a-149">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="9984a-149">Event when settings are changed</span></span> |
| <span data-ttu-id="9984a-150">1125</span><span class="sxs-lookup"><span data-stu-id="9984a-150">1125</span></span> | <span data-ttu-id="9984a-151">Evento quando viene attivata la protezione di rete in modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="9984a-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="9984a-152">1126</span><span class="sxs-lookup"><span data-stu-id="9984a-152">1126</span></span> | <span data-ttu-id="9984a-153">Evento quando viene attivata la protezione di rete in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="9984a-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="9984a-154">Considerazioni sul desktop virtuale Windows che esegue Windows 10 Enterprise Multi-Session</span><span class="sxs-lookup"><span data-stu-id="9984a-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="9984a-155">A causa della natura multi-utente di Windows 10 Enterprise, tenere presenti i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9984a-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="9984a-156">La protezione di rete è una funzionalità a livello di dispositivo e non può essere destinata a sessioni utente specifiche.</span><span class="sxs-lookup"><span data-stu-id="9984a-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="9984a-157">Anche i criteri di filtro del contenuto Web sono a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9984a-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="9984a-158">Se è necessario distinguere i gruppi di utenti, prendere in considerazione la creazione di pool host Desktop virtuale Windows e assegnazioni separati.</span><span class="sxs-lookup"><span data-stu-id="9984a-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="9984a-159">Testare la protezione di rete in modalità di controllo per valutarne il comportamento prima dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="9984a-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="9984a-160">È consigliabile ridimensionare la distribuzione se si dispone di un numero elevato di utenti o di un numero elevato di sessioni multi-utente.</span><span class="sxs-lookup"><span data-stu-id="9984a-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="9984a-161">Opzione alternativa per la protezione di rete</span><span class="sxs-lookup"><span data-stu-id="9984a-161">Alternative option for network protection</span></span>

<span data-ttu-id="9984a-162">Per Windows 10 Enterprise Multi-Session 1909 e versione successiva, usata in Desktop virtuale Windows in Azure, la protezione di rete per Microsoft Edge può essere abilitata usando il metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="9984a-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="9984a-163">Usa [Attiva protezione di rete](enable-network-protection.md) e segui le istruzioni per applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="9984a-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="9984a-164">Eseguire il comando di PowerShell seguente: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="9984a-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="9984a-165">Risoluzione dei problemi di protezione di rete</span><span class="sxs-lookup"><span data-stu-id="9984a-165">Network protection troubleshooting</span></span>

<span data-ttu-id="9984a-166">A causa dell'ambiente in cui viene eseguito Protezione di rete, Microsoft potrebbe non essere in grado di rilevare le impostazioni proxy del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9984a-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="9984a-167">In alcuni casi, i client di protezione di rete non sono in grado di raggiungere il servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="9984a-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="9984a-168">Per risolvere il problema di connettività, i clienti con licenze E5 devono configurare una delle seguenti chiavi del Registro di sistema defender:</span><span class="sxs-lookup"><span data-stu-id="9984a-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="9984a-169">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9984a-169">Related articles</span></span>

- <span data-ttu-id="9984a-170">[Valutare i criteri di protezione](evaluate-network-protection.md) | Eseguire uno scenario rapido che illustra il funzionamento della funzionalità e gli eventi che in genere verrebbero creati.</span><span class="sxs-lookup"><span data-stu-id="9984a-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="9984a-171">[Abilitare la protezione di](enable-network-protection.md) rete | Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.</span><span class="sxs-lookup"><span data-stu-id="9984a-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
