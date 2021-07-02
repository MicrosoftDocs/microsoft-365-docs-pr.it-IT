---
title: Creare indicatori per file
ms.reviewer: ''
description: Creare indicatori per un hash di file che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: file, hash, gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256916"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="48b3e-104">Creare indicatori per file</span><span class="sxs-lookup"><span data-stu-id="48b3e-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48b3e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="48b3e-105">**Applies to:**</span></span>
- [<span data-ttu-id="48b3e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="48b3e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48b3e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48b3e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="48b3e-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="48b3e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48b3e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="48b3e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="48b3e-110">Impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="48b3e-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="48b3e-111">Se si conosce un file pe (Portable Executable) potenzialmente dannoso, è possibile bloccarlo.</span><span class="sxs-lookup"><span data-stu-id="48b3e-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="48b3e-112">Questa operazione ne impedirà la lettura, la scrittura o l'esecuzione nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="48b3e-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="48b3e-113">Esistono tre modi per creare indicatori per i file:</span><span class="sxs-lookup"><span data-stu-id="48b3e-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="48b3e-114">Creando un indicatore tramite la pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="48b3e-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="48b3e-115">Creando un indicatore contestuale usando il pulsante Aggiungi indicatore dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="48b3e-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="48b3e-116">Creando un indicatore tramite [l'API indicator](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="48b3e-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="48b3e-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="48b3e-117">Before you begin</span></span>

<span data-ttu-id="48b3e-118">Prima di creare indicatori per i file, è importante comprendere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="48b3e-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="48b3e-119">Questa funzionalità è disponibile se l'organizzazione usa **Antivirus Microsoft Defender (in** modalità attiva) e la **protezione basata su cloud è abilitata.**</span><span class="sxs-lookup"><span data-stu-id="48b3e-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="48b3e-120">Per ulteriori informazioni, vedere [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="48b3e-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="48b3e-121">La versione del client Antimalware deve essere 4.18.1901.x o successiva.</span><span class="sxs-lookup"><span data-stu-id="48b3e-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="48b3e-122">Vedi [Versioni mensili di piattaforme e motori](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="48b3e-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="48b3e-123">Supportato nei dispositivi con Windows 10 versione 1703 o successiva, Windows Server 2016 2019.</span><span class="sxs-lookup"><span data-stu-id="48b3e-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="48b3e-124">Per iniziare a bloccare i file, devi innanzitutto attivare la funzionalità "blocca o [consenti"](advanced-features.md) in Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="48b3e-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="48b3e-125">Questa funzionalità è progettata per impedire il download di malware sospetti (o file potenzialmente dannosi) dal Web.</span><span class="sxs-lookup"><span data-stu-id="48b3e-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="48b3e-126">Attualmente supporta file eseguibili portabili (PE), inclusi .exe e .dll file.</span><span class="sxs-lookup"><span data-stu-id="48b3e-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="48b3e-127">La copertura verrà estesa nel tempo.</span><span class="sxs-lookup"><span data-stu-id="48b3e-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="48b3e-128">Creare un indicatore per i file dalla pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="48b3e-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="48b3e-129">Nel riquadro di spostamento selezionare Impostazioni > **indicatori**.</span><span class="sxs-lookup"><span data-stu-id="48b3e-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="48b3e-130">Selezionare la **scheda Hash file.**  </span><span class="sxs-lookup"><span data-stu-id="48b3e-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="48b3e-131">Selezionare **Aggiungi indicatore**.</span><span class="sxs-lookup"><span data-stu-id="48b3e-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="48b3e-132">Specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="48b3e-132">Specify the following details:</span></span>
    - <span data-ttu-id="48b3e-133">Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="48b3e-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="48b3e-134">Azione: specificare l'azione da eseguire e fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="48b3e-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="48b3e-135">Ambito: definire l'ambito del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="48b3e-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="48b3e-136">Esaminare i dettagli nella scheda Riepilogo, quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="48b3e-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="48b3e-137">Creare un indicatore contestuale dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="48b3e-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="48b3e-138">Una delle opzioni disponibili per eseguire [azioni di risposta su un file](respond-file-alerts.md)è l'aggiunta di un indicatore per il   file.</span><span class="sxs-lookup"><span data-stu-id="48b3e-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="48b3e-139">Quando aggiungi un hash indicatore per un file, puoi scegliere di generare un avviso e bloccare il file ogni volta che un dispositivo dell'organizzazione tenta di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="48b3e-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="48b3e-140">I file bloccati automaticamente da un indicatore non verranno visualizzati nel centro notifiche del file, ma gli avvisi saranno comunque visibili nella coda avvisi.</span><span class="sxs-lookup"><span data-stu-id="48b3e-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="48b3e-141">In genere, i blocchi di file vengono applicati e rimossi entro un paio di minuti, ma possono richiedere fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="48b3e-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="48b3e-142">Se sono presenti criteri IoC file in conflitto con lo stesso tipo di imposizione e destinazione, verrà applicato il criterio dell'hash più sicuro.</span><span class="sxs-lookup"><span data-stu-id="48b3e-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="48b3e-143">Un criterio IoC con hash di file SHA-256 vincerà su un criterio IoC hash di file SHA-1, che vincerà su un criterio IoC hash di file MD5 se i tipi di hash definiscono lo stesso file.</span><span class="sxs-lookup"><span data-stu-id="48b3e-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="48b3e-144">Questo è sempre vero indipendentemente dal gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="48b3e-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="48b3e-145">In tutti gli altri casi, se i criteri IoC dei file in conflitto con la stessa destinazione di imposizione vengono applicati a tutti i dispositivi e al gruppo del dispositivo, per un dispositivo, il criterio nel gruppo di dispositivi vincerà.</span><span class="sxs-lookup"><span data-stu-id="48b3e-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="48b3e-146">Se il criterio di gruppo EnableFileHashComputation è disabilitato, la precisione di blocco del file IoC viene ridotta.</span><span class="sxs-lookup"><span data-stu-id="48b3e-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="48b3e-147">Tuttavia, `EnableFileHashComputation` l'abilitazione può influire sulle prestazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="48b3e-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="48b3e-148">Ad esempio, la copia di file di grandi dimensioni da una condivisione di rete nel dispositivo locale, in particolare tramite una connessione VPN, potrebbe avere un effetto sulle prestazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="48b3e-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="48b3e-149">Per ulteriori informazioni sui criteri di gruppo EnableFileHashComputation, vedere [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="48b3e-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="48b3e-150">Gestione dei conflitti dei criteri</span><span class="sxs-lookup"><span data-stu-id="48b3e-150">Policy conflict handling</span></span>  

<span data-ttu-id="48b3e-151">I conflitti di gestione dei criteri Cert e File IoC seguiranno l'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="48b3e-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="48b3e-152">Se il file non è consentito Windows Defender criteri/criteri della modalità di imposizione di Controllo applicazioni e AppLocker, **blocca**</span><span class="sxs-lookup"><span data-stu-id="48b3e-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="48b3e-153">Else se il file è consentito dall'Antivirus Microsoft Defender, allora **Allow**</span><span class="sxs-lookup"><span data-stu-id="48b3e-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="48b3e-154">Else se il file è bloccato o avvisato da un blocco o avvisa file IoC, **quindi Blocca/Avvisa**</span><span class="sxs-lookup"><span data-stu-id="48b3e-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="48b3e-155">Else se il file è consentito da un criterio IoC consenti file, quindi **Consenti**</span><span class="sxs-lookup"><span data-stu-id="48b3e-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="48b3e-156">Else se il file è bloccato dalle regole asr, CFA, AV, SmartScreen, quindi **Block**</span><span class="sxs-lookup"><span data-stu-id="48b3e-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="48b3e-157">Else **Allow** (passa Windows Defender Controllo applicazione & criteri di AppLocker, non si applicano regole IoC)</span><span class="sxs-lookup"><span data-stu-id="48b3e-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="48b3e-158">Se sono presenti criteri IoC di file in conflitto con lo stesso tipo di imposizione e destinazione, verrà applicato il criterio dell'hash più sicuro (ovvero più lungo).</span><span class="sxs-lookup"><span data-stu-id="48b3e-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="48b3e-159">Ad esempio, un criterio IoC hash di file SHA-256 vincerà un criterio IoC hash di file MD5 se entrambi i tipi di hash definiscono lo stesso file.</span><span class="sxs-lookup"><span data-stu-id="48b3e-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="48b3e-160">Le funzionalità gestione delle vulnerabilità delle applicazioni vulnerabili di threat e gestione delle vulnerabilità utilizzano gli IoC dei file per l'applicazione e seguiranno l'ordine di gestione dei conflitti precedente.</span><span class="sxs-lookup"><span data-stu-id="48b3e-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="48b3e-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="48b3e-161">Examples</span></span>

|<span data-ttu-id="48b3e-162">Componente</span><span class="sxs-lookup"><span data-stu-id="48b3e-162">Component</span></span> |<span data-ttu-id="48b3e-163">Applicazione dei componenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-163">Component enforcement</span></span> |<span data-ttu-id="48b3e-164">Indicatore file Azione</span><span class="sxs-lookup"><span data-stu-id="48b3e-164">File indicator Action</span></span> |<span data-ttu-id="48b3e-165">Risultato</span><span class="sxs-lookup"><span data-stu-id="48b3e-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="48b3e-166">Esclusione del percorso del file di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="48b3e-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="48b3e-167">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-167">Allow</span></span> |<span data-ttu-id="48b3e-168">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-168">Block</span></span> |<span data-ttu-id="48b3e-169">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-169">Block</span></span>
|<span data-ttu-id="48b3e-170">Regola di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="48b3e-170">Attack surface reduction rule</span></span> |<span data-ttu-id="48b3e-171">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-171">Block</span></span> |<span data-ttu-id="48b3e-172">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-172">Allow</span></span> |<span data-ttu-id="48b3e-173">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-173">Allow</span></span>
|<span data-ttu-id="48b3e-174">Controllo di applicazioni di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="48b3e-174">Windows Defender Application Control</span></span> |<span data-ttu-id="48b3e-175">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-175">Allow</span></span> |<span data-ttu-id="48b3e-176">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-176">Block</span></span> |<span data-ttu-id="48b3e-177">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-177">Allow</span></span> |
|<span data-ttu-id="48b3e-178">Controllo di applicazioni di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="48b3e-178">Windows Defender Application Control</span></span> |<span data-ttu-id="48b3e-179">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-179">Block</span></span> |<span data-ttu-id="48b3e-180">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-180">Allow</span></span> |<span data-ttu-id="48b3e-181">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-181">Block</span></span>
|<span data-ttu-id="48b3e-182">Antivirus Microsoft Defender esclusione</span><span class="sxs-lookup"><span data-stu-id="48b3e-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="48b3e-183">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-183">Allow</span></span> |<span data-ttu-id="48b3e-184">Blocca</span><span class="sxs-lookup"><span data-stu-id="48b3e-184">Block</span></span> |<span data-ttu-id="48b3e-185">Consenti</span><span class="sxs-lookup"><span data-stu-id="48b3e-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="48b3e-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48b3e-186">See also</span></span>

- [<span data-ttu-id="48b3e-187">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="48b3e-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="48b3e-188">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="48b3e-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="48b3e-189">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="48b3e-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="48b3e-190">Gestire indicatori</span><span class="sxs-lookup"><span data-stu-id="48b3e-190">Manage indicators</span></span>](indicator-manage.md)
