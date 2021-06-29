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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194974"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="0cfa5-104">Risolvere i problemi e trovare risposte alle domande frequenti su Microsoft Defender per Endpoint su iOS</span><span class="sxs-lookup"><span data-stu-id="0cfa5-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0cfa5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0cfa5-105">**Applies to:**</span></span>
- [<span data-ttu-id="0cfa5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0cfa5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0cfa5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cfa5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0cfa5-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0cfa5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0cfa5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0cfa5-110">In questo argomento vengono fornite informazioni per la risoluzione dei problemi che possono verificarsi quando usi Microsoft Defender for Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="0cfa5-111">Defender for Endpoint in iOS userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0cfa5-112">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="0cfa5-113">Le app non funzionano quando la VPN è attivata</span><span class="sxs-lookup"><span data-stu-id="0cfa5-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="0cfa5-114">Alcune app non funzionano più quando viene rilevata una VPN attiva.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="0cfa5-115">Puoi disabilitare la VPN durante l'uso di tali app.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="0cfa5-116">Per impostazione predefinita, Defender per Endpoint in iOS include e abilita la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0cfa5-117">[La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0cfa5-118">Defender for Endpoint su iOS usa una VPN per fornire questa protezione.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0cfa5-119">Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0cfa5-120">Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0cfa5-121">Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0cfa5-122">In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0cfa5-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0cfa5-123">Nel dispositivo iOS, apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**</span><span class="sxs-lookup"><span data-stu-id="0cfa5-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0cfa5-124">Tocca o fai clic sul pulsante "i" per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="0cfa5-125">Disattiva la **Connessione su richiesta per** disabilitare la VPN.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0cfa5-126">![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0cfa5-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0cfa5-127">Protezione Web non sarà disponibile quando LA VPN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0cfa5-128">Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**</span><span class="sxs-lookup"><span data-stu-id="0cfa5-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-with-multiple-vpn-profiles"></a><span data-ttu-id="0cfa5-129">Coesistenza con più profili VPN</span><span class="sxs-lookup"><span data-stu-id="0cfa5-129">Co-existence with multiple VPN profiles</span></span>

<span data-ttu-id="0cfa5-130">Apple iOS non supporta più VPN **a livello** di dispositivo per essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="0cfa5-131">Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="0cfa5-132">Microsoft Defender for Endpoint VPN può coesistere con altri VPN configurati *come per app* o *"Personale".*</span><span class="sxs-lookup"><span data-stu-id="0cfa5-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="0cfa5-133">Consumo batteria</span><span class="sxs-lookup"><span data-stu-id="0cfa5-133">Battery consumption</span></span>

<span data-ttu-id="0cfa5-134">Nell'app Impostazioni, iOS mostra solo l'utilizzo della batteria delle app visibili all'utente per un periodo di tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="0cfa5-135">L'utilizzo della batteria da parte delle app visualizzate sullo schermo è solo per tale durata e viene calcolato da iOS in base a una serie di fattori, tra cui l'utilizzo della CPU e della rete.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="0cfa5-136">Microsoft Defender for Endpoint usa una VPN locale/loop-back in background per controllare il traffico Web per eventuali siti Web o connessioni dannose.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0cfa5-137">I pacchetti di rete da qualsiasi app passano attraverso questo controllo e questo causa il calcolo impreciso dell'utilizzo della batteria di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="0cfa5-138">Il consumo effettivo della batteria di Microsoft Defender per Endpoint è molto inferiore a quello visualizzato nella pagina Batteria Impostazioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="0cfa5-139">In media, l'utilizzo giornaliero della batteria da parte di Microsoft Defender for Endpoint in esecuzione in background è circa **l'8,81%** della batteria complessiva consumata in quel giorno.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="0cfa5-140">Questa metrica viene riportata da Apple in base all'utilizzo effettivo di Microsoft Defender per Endpoint nei dispositivi degli utenti finali e, a causa di motivi menzionati in precedenza, può essere utilizzata anche per altre app con attività di rete.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="0cfa5-141">Inoltre, la VPN utilizzata è una VPN locale e, a differenza di una VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="0cfa5-142">Utilizzo dei dati</span><span class="sxs-lookup"><span data-stu-id="0cfa5-142">Data usage</span></span>

<span data-ttu-id="0cfa5-143">Microsoft Defender for Endpoint usa una VPN locale/loopback per controllare il traffico Web per eventuali connessioni o siti Web dannosi.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0cfa5-144">Per questo motivo, l'utilizzo dei dati di Microsoft Defender for Endpoint può essere inesatto.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="0cfa5-145">Abbiamo anche osservato che se il dispositivo si trova solo sulla rete cellulare, l'utilizzo dei dati riportato dal provider di servizi è molto vicino al consumo effettivo, mentre nell'app Impostazioni Apple mostra da 1,5 a 2x dei dati effettivi utilizzati.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-145">We have also observed that if the device is on cellular network only, the data usage reported by service provider is very close to the actual consumption whereas in the Settings app, Apple shows about 1.5x to 2x of actual data consumed.</span></span>

<span data-ttu-id="0cfa5-146">Abbiamo osservazioni simili anche con altri servizi VPN e lo abbiamo segnalato ad Apple.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-146">We have similar observations with other VPN services as well and have reported this to Apple.</span></span>

<span data-ttu-id="0cfa5-147">Inoltre, è fondamentale che Microsoft Defender for Endpoint sia aggiornato con i servizi back-end per garantire una protezione migliore.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-147">In addition, it is critical for Microsoft Defender for Endpoint to be up to date with our backend services to provide better protection.</span></span> <span data-ttu-id="0cfa5-148">Tuttavia, stiamo lavorando all'ottimizzazione dell'utilizzo dei dati da parte di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-148">However, we are working on optimizing the data usage by Microsoft Defender for Endpoint.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0cfa5-149">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="0cfa5-149">Report unsafe site</span></span>

<span data-ttu-id="0cfa5-150">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-150">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0cfa5-151">Visitare la [pagina Fornire commenti e suggerimenti](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) sulla protezione di rete per segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-151">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="0cfa5-152">Rilevato sito dannoso</span><span class="sxs-lookup"><span data-stu-id="0cfa5-152">Malicious site detected</span></span>

<span data-ttu-id="0cfa5-153">Microsoft Defender for Endpoint ti protegge dal phishing o da altri attacchi basati sul Web.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-153">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="0cfa5-154">Se viene rilevato un sito dannoso, la connessione viene bloccata e viene inviato un avviso al portale del Centro sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-154">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="0cfa5-155">L'avviso include il nome di dominio della connessione, l'indirizzo IP remoto e i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-155">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="0cfa5-156">Inoltre, nel dispositivo iOS viene visualizzata una notifica.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-156">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="0cfa5-157">Toccando la notifica si apre la schermata seguente per l'utente per esaminare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="0cfa5-157">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0cfa5-158">![Immagine del sito segnalato come notifica non sicura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="0cfa5-158">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="0cfa5-159">Dati e privacy</span><span class="sxs-lookup"><span data-stu-id="0cfa5-159">Data and Privacy</span></span>

<span data-ttu-id="0cfa5-160">Per informazioni dettagliate sui dati raccolti e sulla privacy, vedi [Informazioni sulla privacy - Microsoft Defender per Endpoint su iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="0cfa5-160">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

