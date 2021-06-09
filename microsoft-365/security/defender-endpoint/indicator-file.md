---
title: Creare indicatori per file.
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
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730535"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="29272-104">Creare indicatori per file.</span><span class="sxs-lookup"><span data-stu-id="29272-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29272-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="29272-105">**Applies to:**</span></span>
- [<span data-ttu-id="29272-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="29272-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29272-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29272-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="29272-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="29272-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="29272-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="29272-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="29272-110">Impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="29272-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="29272-111">Se si conosce un file pe (Portable Executable) potenzialmente dannoso, è possibile bloccarlo.</span><span class="sxs-lookup"><span data-stu-id="29272-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="29272-112">Questa operazione ne impedirà la lettura, la scrittura o l'esecuzione nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="29272-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="29272-113">Esistono tre modi per creare indicatori per i file:</span><span class="sxs-lookup"><span data-stu-id="29272-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="29272-114">Creando un indicatore tramite la pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="29272-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="29272-115">Creando un indicatore contestuale usando il pulsante Aggiungi indicatore dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="29272-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="29272-116">Creando un indicatore tramite [l'API indicator](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="29272-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="29272-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="29272-117">Before you begin</span></span>

<span data-ttu-id="29272-118">Prima di creare indicatori per i file, è importante comprendere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="29272-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="29272-119">Questa funzionalità è disponibile se l'organizzazione usa **Antivirus Microsoft Defender (in** modalità attiva) e la **protezione basata su cloud è abilitata.**</span><span class="sxs-lookup"><span data-stu-id="29272-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="29272-120">Per ulteriori informazioni, vedere [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="29272-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="29272-121">La versione del client Antimalware deve essere 4.18.1901.x o successiva.</span><span class="sxs-lookup"><span data-stu-id="29272-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="29272-122">Vedi [Versioni mensili di piattaforme e motori](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="29272-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="29272-123">Supportato nei dispositivi con Windows 10 versione 1703 o successiva, Windows Server 2016 2019.</span><span class="sxs-lookup"><span data-stu-id="29272-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="29272-124">Per iniziare a bloccare i file, devi innanzitutto attivare la funzionalità "blocca o [consenti"](advanced-features.md) in Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="29272-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="29272-125">Questa funzionalità è progettata per impedire il download di malware sospetti (o file potenzialmente dannosi) dal Web.</span><span class="sxs-lookup"><span data-stu-id="29272-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="29272-126">Attualmente supporta file eseguibili portabili (PE), inclusi .exe e .dll file.</span><span class="sxs-lookup"><span data-stu-id="29272-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="29272-127">La copertura verrà estesa nel tempo.</span><span class="sxs-lookup"><span data-stu-id="29272-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="29272-128">Creare un indicatore per i file dalla pagina delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="29272-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="29272-129">Nel riquadro di spostamento selezionare Impostazioni > **indicatori**.</span><span class="sxs-lookup"><span data-stu-id="29272-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="29272-130">Selezionare la **scheda Hash file.**  </span><span class="sxs-lookup"><span data-stu-id="29272-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="29272-131">Selezionare **Aggiungi indicatore**.</span><span class="sxs-lookup"><span data-stu-id="29272-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="29272-132">Specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="29272-132">Specify the following details:</span></span>
    - <span data-ttu-id="29272-133">Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="29272-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="29272-134">Azione: specificare l'azione da eseguire e fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="29272-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="29272-135">Ambito: definire l'ambito del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="29272-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="29272-136">Esaminare i dettagli nella scheda Riepilogo, quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="29272-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="29272-137">Creare un indicatore contestuale dalla pagina dei dettagli del file</span><span class="sxs-lookup"><span data-stu-id="29272-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="29272-138">Una delle opzioni disponibili per eseguire [azioni di risposta su un file](respond-file-alerts.md)è l'aggiunta di un indicatore per il   file.</span><span class="sxs-lookup"><span data-stu-id="29272-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="29272-139">Quando aggiungi un hash indicatore per un file, puoi scegliere di generare un avviso e bloccare il file ogni volta che un dispositivo dell'organizzazione tenta di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="29272-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="29272-140">I file bloccati automaticamente da un indicatore non verranno visualizzati nel centro notifiche del file, ma gli avvisi saranno comunque visibili nella coda avvisi.</span><span class="sxs-lookup"><span data-stu-id="29272-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="29272-141">In genere, i blocchi di file vengono applicati e rimossi entro un paio di minuti, ma possono richiedere fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="29272-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
>- <span data-ttu-id="29272-142">Se sono presenti criteri indicatore file in conflitto, viene applicato il criterio di applicazione dei criteri più sicuri.</span><span class="sxs-lookup"><span data-stu-id="29272-142">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="29272-143">Ad esempio, un criterio indicatore hash file SHA-256 ha la precedenza su un criterio indicatore hash file MD5 se entrambi i tipi di hash definiscono lo stesso file.</span><span class="sxs-lookup"><span data-stu-id="29272-143">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>
>- <span data-ttu-id="29272-144">Se i criteri di gruppo EnableFileHashComputation sono disabilitati, la precisione di blocco del file IoC viene ridotta.</span><span class="sxs-lookup"><span data-stu-id="29272-144">If EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="29272-145">Tuttavia, l'abilitazione di EnableFileHashComputation può influire sulle prestazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29272-145">However, enabling EnableFileHashComputation may impact device performance.</span></span>
>    - <span data-ttu-id="29272-146">Ad esempio, la copia di file di grandi dimensioni da una condivisione di rete nel dispositivo locale, in particolare tramite una connessione VPN, può avere un effetto sulle prestazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29272-146">For example, copying large files from a network share onto your local device, especially over a VPN connection, may have an effect on device performance.</span></span>
>    - <span data-ttu-id="29272-147">Per ulteriori informazioni sui criteri di gruppo EnableFileHashComputation, vedere [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="29272-147">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="29272-148">Gestione dei conflitti dei criteri</span><span class="sxs-lookup"><span data-stu-id="29272-148">Policy conflict handling</span></span>  

<span data-ttu-id="29272-149">I conflitti di gestione dei criteri Cert e File IoC seguiranno l'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="29272-149">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="29272-150">Se il file non è consentito Windows Defender criteri/criteri della modalità di imposizione di Controllo applicazioni e AppLocker, **blocca**</span><span class="sxs-lookup"><span data-stu-id="29272-150">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="29272-151">Else se il file è consentito dall'Antivirus Microsoft Defender, allora **Allow**</span><span class="sxs-lookup"><span data-stu-id="29272-151">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="29272-152">Else se il file è bloccato o avvisato da un blocco o avvisa file IoC, **quindi Blocca/Avvisa**</span><span class="sxs-lookup"><span data-stu-id="29272-152">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="29272-153">Else se il file è consentito da un criterio IoC consenti file, quindi **Consenti**</span><span class="sxs-lookup"><span data-stu-id="29272-153">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="29272-154">Else se il file è bloccato dalle regole asr, CFA, AV, SmartScreen, quindi **Block**</span><span class="sxs-lookup"><span data-stu-id="29272-154">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="29272-155">Else **Allow** (passa Windows Defender Controllo applicazione & criteri di AppLocker, non si applicano regole IoC)</span><span class="sxs-lookup"><span data-stu-id="29272-155">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="29272-156">Se sono presenti criteri IoC di file in conflitto con lo stesso tipo di imposizione e destinazione, verrà applicato il criterio dell'hash più sicuro (ovvero più lungo).</span><span class="sxs-lookup"><span data-stu-id="29272-156">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="29272-157">Ad esempio, un criterio IoC hash di file SHA-256 vincerà un criterio IoC hash di file MD5 se entrambi i tipi di hash definiscono lo stesso file.</span><span class="sxs-lookup"><span data-stu-id="29272-157">For example, a SHA-256 file hash IoC policy will win over a MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="29272-158">Tieni presente gestione di minacce e vulnerabilità delle funzionalità delle applicazioni vulnerabili di blocco usa gli ioC dei file per l'imposizione e seguirà l'ordine di gestione dei conflitti precedente.</span><span class="sxs-lookup"><span data-stu-id="29272-158">Note that threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="29272-159">Esempi</span><span class="sxs-lookup"><span data-stu-id="29272-159">Examples</span></span>

|<span data-ttu-id="29272-160">Componente</span><span class="sxs-lookup"><span data-stu-id="29272-160">Component</span></span> |<span data-ttu-id="29272-161">Applicazione dei componenti</span><span class="sxs-lookup"><span data-stu-id="29272-161">Component enforcement</span></span> |<span data-ttu-id="29272-162">Indicatore file Azione</span><span class="sxs-lookup"><span data-stu-id="29272-162">File indicator Action</span></span> |<span data-ttu-id="29272-163">Risultato</span><span class="sxs-lookup"><span data-stu-id="29272-163">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="29272-164">Esclusione del percorso del file di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="29272-164">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="29272-165">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-165">Allow</span></span> |<span data-ttu-id="29272-166">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-166">Block</span></span> |<span data-ttu-id="29272-167">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-167">Block</span></span>
|<span data-ttu-id="29272-168">Regola di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="29272-168">Attack surface reduction rule</span></span> |<span data-ttu-id="29272-169">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-169">Block</span></span> |<span data-ttu-id="29272-170">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-170">Allow</span></span> |<span data-ttu-id="29272-171">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-171">Allow</span></span>
|<span data-ttu-id="29272-172">Controllo di applicazioni di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="29272-172">Windows Defender Application Control</span></span> |<span data-ttu-id="29272-173">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-173">Allow</span></span> |<span data-ttu-id="29272-174">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-174">Block</span></span> |<span data-ttu-id="29272-175">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-175">Allow</span></span> |
|<span data-ttu-id="29272-176">Controllo di applicazioni di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="29272-176">Windows Defender Application Control</span></span> |<span data-ttu-id="29272-177">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-177">Block</span></span> |<span data-ttu-id="29272-178">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-178">Allow</span></span> |<span data-ttu-id="29272-179">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-179">Block</span></span>
|<span data-ttu-id="29272-180">Antivirus Microsoft Defender esclusione</span><span class="sxs-lookup"><span data-stu-id="29272-180">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="29272-181">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-181">Allow</span></span> |<span data-ttu-id="29272-182">Blocca</span><span class="sxs-lookup"><span data-stu-id="29272-182">Block</span></span> |<span data-ttu-id="29272-183">Consenti</span><span class="sxs-lookup"><span data-stu-id="29272-183">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="29272-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29272-184">See also</span></span>

- [<span data-ttu-id="29272-185">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="29272-185">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="29272-186">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="29272-186">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="29272-187">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="29272-187">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="29272-188">Gestire indicatori</span><span class="sxs-lookup"><span data-stu-id="29272-188">Manage indicators</span></span>](indicator-manage.md)
