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
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636279"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="eadb0-104">Risolvere i problemi e trovare risposte alle domande frequenti su Microsoft Defender per Endpoint su iOS</span><span class="sxs-lookup"><span data-stu-id="eadb0-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eadb0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eadb0-105">**Applies to:**</span></span>
- [<span data-ttu-id="eadb0-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="eadb0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eadb0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eadb0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eadb0-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="eadb0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eadb0-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="eadb0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="eadb0-110">In questo argomento vengono fornite informazioni per la risoluzione dei problemi che possono verificarsi quando usi Microsoft Defender for Endpoint in iOS.</span><span class="sxs-lookup"><span data-stu-id="eadb0-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="eadb0-111">Defender for Endpoint in iOS userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="eadb0-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="eadb0-112">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="eadb0-113">Le app non funzionano quando la VPN è attivata</span><span class="sxs-lookup"><span data-stu-id="eadb0-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="eadb0-114">Alcune app non funzionano più quando viene rilevata una VPN attiva.</span><span class="sxs-lookup"><span data-stu-id="eadb0-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="eadb0-115">Puoi disabilitare la VPN durante l'uso di tali app.</span><span class="sxs-lookup"><span data-stu-id="eadb0-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="eadb0-116">Per impostazione predefinita, Defender per Endpoint in iOS include e abilita la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="eadb0-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="eadb0-117">[La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="eadb0-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="eadb0-118">Defender for Endpoint su iOS usa una VPN per fornire questa protezione.</span><span class="sxs-lookup"><span data-stu-id="eadb0-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="eadb0-119">Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="eadb0-120">Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn.</span><span class="sxs-lookup"><span data-stu-id="eadb0-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="eadb0-121">Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN.</span><span class="sxs-lookup"><span data-stu-id="eadb0-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="eadb0-122">In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="eadb0-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="eadb0-123">Nel dispositivo iOS, apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**</span><span class="sxs-lookup"><span data-stu-id="eadb0-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="eadb0-124">Tocca o fai clic sul pulsante "i" per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eadb0-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="eadb0-125">Disattiva la **Connessione su richiesta per** disabilitare la VPN.</span><span class="sxs-lookup"><span data-stu-id="eadb0-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="eadb0-126">![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="eadb0-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="eadb0-127">Protezione Web non sarà disponibile quando LA VPN è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="eadb0-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="eadb0-128">Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**</span><span class="sxs-lookup"><span data-stu-id="eadb0-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="eadb0-129">Problemi con più profili VPN</span><span class="sxs-lookup"><span data-stu-id="eadb0-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="eadb0-130">Apple iOS non supporta più VPN a livello di dispositivo per essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="eadb0-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="eadb0-131">Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.</span><span class="sxs-lookup"><span data-stu-id="eadb0-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="eadb0-132">Consumo batteria</span><span class="sxs-lookup"><span data-stu-id="eadb0-132">Battery consumption</span></span>

<span data-ttu-id="eadb0-133">L'utilizzo della batteria da parte di un'app viene calcolato da Apple in base a numerosi fattori, tra cui l'utilizzo della CPU e della rete.</span><span class="sxs-lookup"><span data-stu-id="eadb0-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="eadb0-134">Microsoft Defender for Endpoint usa una VPN locale/loop-back in background per controllare il traffico Web per eventuali siti Web o connessioni dannose.</span><span class="sxs-lookup"><span data-stu-id="eadb0-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="eadb0-135">I pacchetti di rete da qualsiasi app passano attraverso questo controllo e questo causa il calcolo impreciso dell'utilizzo della batteria di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eadb0-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="eadb0-136">Questo dà una falsa impressione all'utente.</span><span class="sxs-lookup"><span data-stu-id="eadb0-136">This gives a false impression to the user.</span></span> <span data-ttu-id="eadb0-137">Il consumo effettivo della batteria di Microsoft Defender for Endpoint è inferiore a quello visualizzato nella pagina Batteria Impostazioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="eadb0-138">Si basa sui test eseguiti nell'app Microsoft Defender for Endpoint per comprendere il consumo della batteria.</span><span class="sxs-lookup"><span data-stu-id="eadb0-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="eadb0-139">Anche la VPN utilizzata è una VPN locale e, a differenza di una VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="eadb0-140">Utilizzo dei dati</span><span class="sxs-lookup"><span data-stu-id="eadb0-140">Data usage</span></span>

<span data-ttu-id="eadb0-141">Microsoft Defender for Endpoint usa una VPN locale/loopback per controllare il traffico Web per eventuali connessioni o siti Web dannosi.</span><span class="sxs-lookup"><span data-stu-id="eadb0-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="eadb0-142">Per questo motivo Apple account utilizzo dei dati di Microsoft Defender per Endpoint in modo impreciso.</span><span class="sxs-lookup"><span data-stu-id="eadb0-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="eadb0-143">L'utilizzo effettivo dei dati da parte di Microsoft Defender per Endpoint non è significativo e molto inferiore a quello mostrato nella pagina Utilizzo dati Impostazioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="eadb0-144">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="eadb0-144">Report unsafe site</span></span>

<span data-ttu-id="eadb0-145">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="eadb0-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="eadb0-146">Visitare la [pagina Fornire commenti e suggerimenti](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) sulla protezione di rete per segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="eadb0-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="eadb0-147">Rilevato sito dannoso</span><span class="sxs-lookup"><span data-stu-id="eadb0-147">Malicious site detected</span></span>

<span data-ttu-id="eadb0-148">Microsoft Defender for Endpoint ti protegge dal phishing o da altri attacchi basati sul Web.</span><span class="sxs-lookup"><span data-stu-id="eadb0-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="eadb0-149">Se viene rilevato un sito dannoso, la connessione viene bloccata e viene inviato un avviso al portale del Centro sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eadb0-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="eadb0-150">L'avviso include il nome di dominio della connessione, l'indirizzo IP remoto e i dettagli del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eadb0-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="eadb0-151">Inoltre, nel dispositivo iOS viene visualizzata una notifica.</span><span class="sxs-lookup"><span data-stu-id="eadb0-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="eadb0-152">Toccando la notifica si apre la schermata seguente per l'utente per esaminare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="eadb0-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eadb0-153">![Immagine del sito segnalato come notifica non sicura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="eadb0-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="eadb0-154">Dati e privacy</span><span class="sxs-lookup"><span data-stu-id="eadb0-154">Data and Privacy</span></span>

<span data-ttu-id="eadb0-155">Per informazioni dettagliate sui dati raccolti e sulla privacy, vedi [Informazioni sulla privacy - Microsoft Defender per Endpoint su iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="eadb0-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

