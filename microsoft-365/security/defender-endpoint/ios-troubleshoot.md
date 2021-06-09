---
title: Risolvere i problemi e trovare risposte alle domande frequenti relative a Microsoft Defender per Endpoint su iOS
description: Risoluzione dei problemi e domande frequenti - Microsoft Defender per Endpoint su iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, risoluzione dei problemi, domande frequenti, come
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694366"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="cc02d-104">Risolvere i problemi e trovare risposte alle domande frequenti su Microsoft Defender per Endpoint su iOS</span><span class="sxs-lookup"><span data-stu-id="cc02d-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc02d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cc02d-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc02d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cc02d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc02d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc02d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cc02d-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cc02d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cc02d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cc02d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="cc02d-110">In questo argomento vengono fornite informazioni per la risoluzione dei problemi che possono verificarsi quando usi Microsoft Defender for Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="cc02d-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="cc02d-111">Defender for Endpoint in iOS userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="cc02d-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="cc02d-112">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="cc02d-113">Le app non funzionano quando la VPN è attivata</span><span class="sxs-lookup"><span data-stu-id="cc02d-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="cc02d-114">Alcune app non funzionano più quando viene rilevata una VPN attiva.</span><span class="sxs-lookup"><span data-stu-id="cc02d-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="cc02d-115">Puoi disabilitare la VPN durante l'uso di tali app.</span><span class="sxs-lookup"><span data-stu-id="cc02d-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="cc02d-116">Per impostazione predefinita, Defender per Endpoint in iOS include e abilita la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="cc02d-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="cc02d-117">[La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="cc02d-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="cc02d-118">Defender for Endpoint su iOS usa una VPN per fornire questa protezione.</span><span class="sxs-lookup"><span data-stu-id="cc02d-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="cc02d-119">Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="cc02d-120">Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn.</span><span class="sxs-lookup"><span data-stu-id="cc02d-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="cc02d-121">Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN.</span><span class="sxs-lookup"><span data-stu-id="cc02d-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="cc02d-122">In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="cc02d-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="cc02d-123">Nel dispositivo iOS, apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**</span><span class="sxs-lookup"><span data-stu-id="cc02d-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="cc02d-124">Tocca o fai clic sul pulsante "i" per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="cc02d-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="cc02d-125">Disattiva la **Connessione su richiesta per** disabilitare la VPN.</span><span class="sxs-lookup"><span data-stu-id="cc02d-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cc02d-126">![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="cc02d-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="cc02d-127">Protezione Web non sarà disponibile quando LA VPN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="cc02d-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="cc02d-128">Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**</span><span class="sxs-lookup"><span data-stu-id="cc02d-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="cc02d-129">Problemi con più profili VPN</span><span class="sxs-lookup"><span data-stu-id="cc02d-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="cc02d-130">Apple iOS non supporta più VPN **a livello** di dispositivo per essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="cc02d-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="cc02d-131">Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.</span><span class="sxs-lookup"><span data-stu-id="cc02d-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="cc02d-132">Microsoft Defender for Endpoint VPN può coesistere con altri VPN configurati *come per app* o *"Personale".*</span><span class="sxs-lookup"><span data-stu-id="cc02d-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="cc02d-133">Consumo batteria</span><span class="sxs-lookup"><span data-stu-id="cc02d-133">Battery consumption</span></span>

<span data-ttu-id="cc02d-134">Nell'app Impostazioni, iOS mostra solo l'utilizzo della batteria delle app visibili all'utente per un periodo di tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="cc02d-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="cc02d-135">L'utilizzo della batteria da parte delle app visualizzate sullo schermo è solo per tale durata e viene calcolato da iOS in base a una serie di fattori, tra cui l'utilizzo della CPU e della rete.</span><span class="sxs-lookup"><span data-stu-id="cc02d-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="cc02d-136">Microsoft Defender for Endpoint usa una VPN locale/loop-back in background per controllare il traffico Web per eventuali siti Web o connessioni dannose.</span><span class="sxs-lookup"><span data-stu-id="cc02d-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="cc02d-137">I pacchetti di rete da qualsiasi app passano attraverso questo controllo e questo causa il calcolo impreciso dell'utilizzo della batteria di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="cc02d-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="cc02d-138">Il consumo effettivo della batteria di Microsoft Defender per Endpoint è molto inferiore a quello visualizzato nella pagina Batteria Impostazioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="cc02d-139">In media, l'utilizzo giornaliero della batteria da parte di Microsoft Defender for Endpoint in esecuzione in background è circa **l'8,81%** della batteria complessiva consumata in quel giorno.</span><span class="sxs-lookup"><span data-stu-id="cc02d-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="cc02d-140">Questa metrica viene riportata da Apple in base all'utilizzo effettivo di Microsoft Defender per Endpoint nei dispositivi degli utenti finali e, a causa di motivi menzionati in precedenza, può essere utilizzata anche per altre app con attività di rete.</span><span class="sxs-lookup"><span data-stu-id="cc02d-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="cc02d-141">Inoltre, la VPN utilizzata è una VPN locale e, a differenza di una VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="cc02d-142">Utilizzo dei dati</span><span class="sxs-lookup"><span data-stu-id="cc02d-142">Data usage</span></span>

<span data-ttu-id="cc02d-143">Microsoft Defender for Endpoint usa una VPN locale/loopback per controllare il traffico Web per eventuali connessioni o siti Web dannosi.</span><span class="sxs-lookup"><span data-stu-id="cc02d-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="cc02d-144">Per questo motivo, l'utilizzo dei dati di Microsoft Defender for Endpoint può essere inesatto.</span><span class="sxs-lookup"><span data-stu-id="cc02d-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="cc02d-145">L'utilizzo effettivo dei dati da parte di Microsoft Defender per Endpoint non è significativo e minore di quello mostrato nella pagina Utilizzo dati Impostazioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-145">The actual data usage by Microsoft Defender for Endpoint is not significant and lesser than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="cc02d-146">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="cc02d-146">Report unsafe site</span></span>

<span data-ttu-id="cc02d-147">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="cc02d-147">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="cc02d-148">Visitare la [pagina Fornire commenti e suggerimenti](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) sulla protezione di rete per segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="cc02d-148">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="cc02d-149">Rilevato sito dannoso</span><span class="sxs-lookup"><span data-stu-id="cc02d-149">Malicious site detected</span></span>

<span data-ttu-id="cc02d-150">Microsoft Defender for Endpoint ti protegge dal phishing o da altri attacchi basati sul Web.</span><span class="sxs-lookup"><span data-stu-id="cc02d-150">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="cc02d-151">Se viene rilevato un sito dannoso, la connessione viene bloccata e viene inviato un avviso al portale del Centro sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc02d-151">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="cc02d-152">L'avviso include il nome di dominio della connessione, l'indirizzo IP remoto e i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc02d-152">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="cc02d-153">Inoltre, nel dispositivo iOS viene visualizzata una notifica.</span><span class="sxs-lookup"><span data-stu-id="cc02d-153">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="cc02d-154">Toccando la notifica si apre la schermata seguente per l'utente per esaminare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="cc02d-154">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cc02d-155">![Immagine del sito segnalato come notifica non sicura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="cc02d-155">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="cc02d-156">Dati e privacy</span><span class="sxs-lookup"><span data-stu-id="cc02d-156">Data and Privacy</span></span>

<span data-ttu-id="cc02d-157">Per informazioni dettagliate sui dati raccolti e sulla privacy, vedi [Informazioni sulla privacy - Microsoft Defender per Endpoint su iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="cc02d-157">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

