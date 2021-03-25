---
title: Creare indicatori per IP e URL/domini
ms.reviewer: ''
description: Creare indicatori per IP e URL/domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: ip, url, dominio, gestire, consentito, bloccato, bloccare, pulire, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067709"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="d692a-104">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="d692a-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d692a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d692a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d692a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d692a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d692a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d692a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="d692a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d692a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d692a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d692a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="d692a-110">Defender for Endpoint può bloccare ciò che Microsoft ritiene ip/URL dannosi, tramite Windows Defender SmartScreen per i browser Microsoft e tramite Protezione di rete per browser non Microsoft o chiamate effettuate all'esterno di un browser.</span><span class="sxs-lookup"><span data-stu-id="d692a-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="d692a-111">Il set di dati di intelligence per le minacce per questo è stato gestito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d692a-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="d692a-112">Creando indicatori per INDIRIZZI IP e URL o domini, ora puoi consentire o bloccare INDIRIZZI IP, URL o domini in base alla tua intelligence sulle minacce.</span><span class="sxs-lookup"><span data-stu-id="d692a-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="d692a-113">È possibile eseguire questa operazione tramite la pagina delle impostazioni o i gruppi di computer se si ritiene che alcuni gruppi siano più o meno a rischio di altri.</span><span class="sxs-lookup"><span data-stu-id="d692a-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="d692a-114">La notazione CIDR (Classless Inter-Domain Routing) per gli indirizzi IP non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d692a-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="d692a-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d692a-115">Before you begin</span></span>
<span data-ttu-id="d692a-116">È importante comprendere i prerequisiti seguenti prima di creare indicatori per IPS, URL o domini:</span><span class="sxs-lookup"><span data-stu-id="d692a-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="d692a-117">L'url/ip consentiti e il blocco si basa su Defender per l'attivazione di Network Protection del componente endpoint in modalità blocco.</span><span class="sxs-lookup"><span data-stu-id="d692a-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="d692a-118">Per ulteriori informazioni su Protezione di rete e istruzioni di configurazione, vedere [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d692a-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="d692a-119">La versione del client Antimalware deve essere 4.18.1906.x o successiva.</span><span class="sxs-lookup"><span data-stu-id="d692a-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="d692a-120">Supportato nei computer con Windows 10 versione 1709 o successiva.</span><span class="sxs-lookup"><span data-stu-id="d692a-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="d692a-121">Assicurati che **gli indicatori di rete personalizzati** siano abilitati in Microsoft Defender Security Center > impostazioni > funzionalità **avanzate.**</span><span class="sxs-lookup"><span data-stu-id="d692a-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="d692a-122">Per ulteriori informazioni, vedere [Funzionalità avanzate.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="d692a-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="d692a-123">Per il supporto degli indicatori in iOS, vedi [Configurare indicatori personalizzati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)</span><span class="sxs-lookup"><span data-stu-id="d692a-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d692a-124">Solo gli INDIRIZZI IP esterni possono essere aggiunti all'elenco degli indicatori.</span><span class="sxs-lookup"><span data-stu-id="d692a-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="d692a-125">Non è possibile creare indicatori per gli IP interni.</span><span class="sxs-lookup"><span data-stu-id="d692a-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="d692a-126">Per gli scenari di protezione Web, è consigliabile usare le funzionalità incorporate in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d692a-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="d692a-127">Microsoft Edge sfrutta Protezione di [rete per](network-protection.md) controllare il traffico di rete e consente blocchi per TCP, HTTP e HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="d692a-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="d692a-128">Per tutti gli altri processi, gli scenari di protezione Web sfruttano Protezione di rete per l'ispezione e l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d692a-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="d692a-129">NOTA:</span><span class="sxs-lookup"><span data-stu-id="d692a-129">NOTE:</span></span>
> - <span data-ttu-id="d692a-130">IP è supportato per tutti e tre i protocolli</span><span class="sxs-lookup"><span data-stu-id="d692a-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="d692a-131">Sono supportati solo indirizzi IP singoli (nessun blocco CIDR o intervalli IP)</span><span class="sxs-lookup"><span data-stu-id="d692a-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="d692a-132">Gli URL crittografati (percorso completo) possono essere bloccati solo nei browser di prima parte (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="d692a-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="d692a-133">Gli URL crittografati (solo FQDN) possono essere bloccati all'esterno dei browser di prima parte (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="d692a-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="d692a-134">I blocchi di percorso URL completo possono essere applicati a livello di dominio e tutti gli URL non crittografati</span><span class="sxs-lookup"><span data-stu-id="d692a-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="d692a-135">Possono essere presenti fino a 2 ore di latenza (in genere meno) tra il momento in cui viene eseguita l'azione e l'URL e l'IP bloccati.</span><span class="sxs-lookup"><span data-stu-id="d692a-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="d692a-136">Creare un indicatore per IP, URL o domini dalla pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="d692a-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="d692a-137">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.</span><span class="sxs-lookup"><span data-stu-id="d692a-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="d692a-138">Selezionare la **scheda Indirizzi IP o URL/Domini.**</span><span class="sxs-lookup"><span data-stu-id="d692a-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="d692a-139">Selezionare **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="d692a-139">Select **Add item**.</span></span>

4. <span data-ttu-id="d692a-140">Specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d692a-140">Specify the following details:</span></span>
   - <span data-ttu-id="d692a-141">Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="d692a-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="d692a-142">Azione: specificare l'azione da eseguire e fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="d692a-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="d692a-143">Ambito: definire l'ambito del gruppo di computer.</span><span class="sxs-lookup"><span data-stu-id="d692a-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="d692a-144">Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="d692a-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d692a-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d692a-145">Related topics</span></span>
- [<span data-ttu-id="d692a-146">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="d692a-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="d692a-147">Creare indicatori per i file</span><span class="sxs-lookup"><span data-stu-id="d692a-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="d692a-148">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="d692a-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="d692a-149">Gestire gli indicatori</span><span class="sxs-lookup"><span data-stu-id="d692a-149">Manage indicators</span></span>](indicator-manage.md)