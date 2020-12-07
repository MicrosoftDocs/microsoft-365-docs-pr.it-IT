---
title: Uso della prevenzione della perdita di dati degli endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Informazioni su come configurare i criteri di prevenzione della perdita dei dati (DLP) per usare le posizioni di Prevenzione della perdita di dati degli endpoint di Microsoft 365.
ms.openlocfilehash: 0a6883bd785141af6f198f0cd871c11794618e27
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561683"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="906c9-103">Uso della prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="906c9-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="906c9-104">Questo articolo illustra tre scenari in cui si creano e modificano criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="906c9-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="906c9-105">Impostazioni DLP</span><span class="sxs-lookup"><span data-stu-id="906c9-105">DLP settings</span></span>

<span data-ttu-id="906c9-106">Prima di iniziare, è necessario configurare le impostazioni di prevenzione della perdita dei dati da applicare a tutti i criteri DLP per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="906c9-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="906c9-107">Vanno configurate se si prevede di creare criteri che impongono:</span><span class="sxs-lookup"><span data-stu-id="906c9-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="906c9-108">restrizioni di uscita dal cloud</span><span class="sxs-lookup"><span data-stu-id="906c9-108">cloud egress restrictions</span></span>
- <span data-ttu-id="906c9-109">restrizioni per app non consentite</span><span class="sxs-lookup"><span data-stu-id="906c9-109">unallowed apps restrictions</span></span>

<span data-ttu-id="906c9-110">Oppure</span><span class="sxs-lookup"><span data-stu-id="906c9-110">Or</span></span>

- <span data-ttu-id="906c9-111">Se si vogliono escludere dal monitoraggio i percorsi di file con troppi disturbi</span><span class="sxs-lookup"><span data-stu-id="906c9-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="906c9-112">![Impostazioni DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="906c9-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="906c9-113">Esclusioni di percorsi di file</span><span class="sxs-lookup"><span data-stu-id="906c9-113">File path exclusions</span></span>

<span data-ttu-id="906c9-114">È possibile escludere alcuni percorsi dal monitoraggio DLP, dagli avvisi DLP e dall'applicazione dei criteri DLP nei dispositivi, perché sono troppo disturbati o non contengono file a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="906c9-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="906c9-115">I file presenti in tali posizioni non verranno controllati e i file creati o modificati in tali posizioni non saranno soggetti all'applicazione dei criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="906c9-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="906c9-116">È possibile configurare le esclusioni di percorsi nelle impostazioni DLP.</span><span class="sxs-lookup"><span data-stu-id="906c9-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="906c9-117">Per creare esclusioni di percorsi si può usare questa logica:</span><span class="sxs-lookup"><span data-stu-id="906c9-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="906c9-118">Percorso file valido che termina con "\", per indicare solo i file direttamente nella cartella.</span><span class="sxs-lookup"><span data-stu-id="906c9-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="906c9-119">Ad esempio, C:\Temp</span><span class="sxs-lookup"><span data-stu-id="906c9-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="906c9-120">Percorso file valido che termina con "\*", per indicare solo i file all'interno di sottocartelle, oltre ai file direttamente nella cartella.</span><span class="sxs-lookup"><span data-stu-id="906c9-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="906c9-121">Ad esempio, C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="906c9-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="906c9-122">Percorso file valido che termina senza "\" o "\*", per indicare tutti i file direttamente nella cartella e in tutte le sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="906c9-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="906c9-123">Ad esempio, C:\Temp</span><span class="sxs-lookup"><span data-stu-id="906c9-123">For example: C:\Temp</span></span>

- <span data-ttu-id="906c9-124">Percorso con carattere jolly compreso tra "\" su entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="906c9-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="906c9-125">Ad esempio, C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="906c9-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="906c9-126">Percorso con carattere jolly compreso tra "\" su entrambi i lati e con "(numero)" per indicare il numero esatto di sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="906c9-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="906c9-127">Ad esempio, C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="906c9-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="906c9-128">Un percorso con variabili di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="906c9-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="906c9-129">Ad esempio, %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="906c9-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="906c9-130">Una combinazione di tutti gli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="906c9-130">A mix of all the above.</span></span> <br/><span data-ttu-id="906c9-131">Ad esempio, %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="906c9-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="906c9-132">App non consentite</span><span class="sxs-lookup"><span data-stu-id="906c9-132">Unallowed apps</span></span>

<span data-ttu-id="906c9-133">Quando l'impostazione **Accesso da app e browser non consentiti** di un criterio è attivata e gli utenti tentano di usare queste app per accedere a un file protetto, l'attività viene consentita, bloccata oppure bloccata ma gli utenti possono ignorare la restrizione.</span><span class="sxs-lookup"><span data-stu-id="906c9-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="906c9-134">Tutte le attività sono controllate e disponibili per la revisione in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="906c9-135">Non includere il percorso del file eseguibile, ma solo il nome (ad esempio browser.exe).</span><span class="sxs-lookup"><span data-stu-id="906c9-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="906c9-136">Restrizioni del browser e del dominio</span><span class="sxs-lookup"><span data-stu-id="906c9-136">Browser and domain restrictions</span></span>
<span data-ttu-id="906c9-137">Limitare la condivisione dei file riservati che corrispondono ai criteri, con i domini del servizio cloud senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="906c9-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="906c9-138">Domini di servizio</span><span class="sxs-lookup"><span data-stu-id="906c9-138">Service domains</span></span>

<span data-ttu-id="906c9-139">È possibile controllare se i file riservati protetti dai criteri possono essere caricati in specifici domini di servizio da Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="906c9-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="906c9-140">Se la modalità elenco è impostata su **Blocca**, l'utente non potrà caricare elementi sensibili in tali domini.</span><span class="sxs-lookup"><span data-stu-id="906c9-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="906c9-141">Quando un'azione di caricamento viene bloccata perché un elemento corrisponde a un criterio di prevenzione della perdita dei dati, DLP genera un avviso o blocca il caricamento dell'elemento sensibile.</span><span class="sxs-lookup"><span data-stu-id="906c9-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="906c9-142">Se la modalità elenco è impostata su **Consenti**, gli utenti possono caricare gli elementi sensibili \**_solo_* _ in tali domini e l'accesso di caricamento a tutti gli altri domini non è consentito.</span><span class="sxs-lookup"><span data-stu-id="906c9-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="906c9-143">Browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="906c9-143">Unallowed browsers</span></span>

<span data-ttu-id="906c9-144">È possibile aggiungere browser, identificati dai nomi eseguibili, a cui verrà impedito di accedere ai file che corrispondono alle condizioni di un criterio DLP applicato in cui la restrizione relativa al caricamento nei servizi cloud è impostata su Blocca o Blocca con override.</span><span class="sxs-lookup"><span data-stu-id="906c9-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="906c9-145">Quando a tali browser viene impedito di accedere a un file, gli utenti finali visualizzeranno un avviso popup con la richiesta di aprire il file con Microsoft Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="906c9-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="always-audit-file-activity-from-onboarded-devices"></a><span data-ttu-id="906c9-146">Controllare sempre l'attività dei file di controllo dai dispositivi di cui è stato eseguito l’onboarding</span><span class="sxs-lookup"><span data-stu-id="906c9-146">Always audit file activity from onboarded devices</span></span>

<span data-ttu-id="906c9-147">Controllare se l'attività di prevenzione della perdita dei dati per i file Office, PDF e CSV è verificata automaticamente e disponibile per la revisione nella telemetria di controllo e in Esplora attività dai dispositivi di cui è stato eseguito l’onboarding.</span><span class="sxs-lookup"><span data-stu-id="906c9-147">Control whether DLP activity for Office, PDF, and CSV files is automatically audited and available for review in the audit telemetry and the Activity Explorer from onboarded devices.</span></span> 

<span data-ttu-id="906c9-148">Se tale impostazione è attivata (impostazione predefinita), le attività dei file sono sempre verificate per i dispositivi di cui è stato eseguito l’onboarding, indipendentemente dal fatto che siano o meno inclusi in un criterio di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="906c9-148">If this is turned On (the default), file activity is always audited for onboarded devices, regardless of whether or not they are included in an active DLP policy.</span></span>
<span data-ttu-id="906c9-149">Se l’impostazione è disattivata, le attività dei file sono verificate per i dispositivi di cui è stato eseguito l’onboarding solo quando sono inclusi in un criterio attivo di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="906c9-149">If this is turned off, file activity is audited for onboarded devices only when they are included in an active DLP policy.</span></span> 


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="906c9-150">Collegamento delle impostazioni DLP</span><span class="sxs-lookup"><span data-stu-id="906c9-150">Tying DLP settings together</span></span>

<span data-ttu-id="906c9-151">Con Endpoint DLP e il Web browser Microsoft Edge Chromium, è possibile limitare la condivisione involontaria di elementi sensibili con app e i servizi cloud non consentiti.</span><span class="sxs-lookup"><span data-stu-id="906c9-151">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="906c9-152">Microsoft Edge Chromium riconosce quando un elemento è limitato da un criterio di Endpoint DLP e impone restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="906c9-152">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="906c9-153">Quando si usano il browser Microsoft Edge Chromium e la posizione Endpoint DLP in un criterio di prevenzione della perdita dei dati configurato correttamente, i browser non consentiti definiti in queste impostazioni non potranno accedere agli elementi sensibili che corrispondono ai controlli del criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="906c9-153">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="906c9-154">Gli utenti verranno reindirizzati all'uso di Microsoft Edge Chromium, che comprende le restrizioni imposte dalla prevenzione della perdita dei dati e può bloccare o limitare attività quando le condizioni indicate nel criterio DLP sono soddisfatte.</span><span class="sxs-lookup"><span data-stu-id="906c9-154">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="906c9-155">Per usare questa restrizione sarà necessario configurare tre elementi importanti:</span><span class="sxs-lookup"><span data-stu-id="906c9-155">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="906c9-156">Specificare le posizioni, ovvero servizi, domini o indirizzi IP, con cui si vuole impedire la condivisione di elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="906c9-156">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="906c9-157">Aggiungere i browser ai quali non è consentito accedere a determinati elementi sensibili in caso di corrispondenza con un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="906c9-157">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="906c9-158">Configurare i criteri DLP per definire i tipi di elementi sensibili per cui limitare il caricamento in queste posizioni, attivando _ *Carica nei servizi cloud*\* e **Accedi dai browser non consentiti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-158">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on _ *Upload to cloud services*\* and **Access from unallowed browser**.</span></span>

<span data-ttu-id="906c9-159">È possibile continuare ad aggiungere nuovi servizi, app e criteri per estendere e aumentare le restrizioni in modo da soddisfare le esigenze dell'azienda e proteggere i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="906c9-159">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="906c9-160">Questa configurazione contribuirà a garantire la sicurezza dei dati, evitando anche restrizioni inutili che limitano la capacità degli utenti di accedere a elementi non riservati e condividerli.</span><span class="sxs-lookup"><span data-stu-id="906c9-160">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="906c9-161">Scenari dei criteri di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="906c9-161">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="906c9-162">Per acquisire familiarità con le funzionalità di Endpoint DLP e su come vengono visualizzate nei criteri DLP, sono stati predisposti alcuni scenari da seguire.</span><span class="sxs-lookup"><span data-stu-id="906c9-162">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="906c9-163">Tutto il contenuto di Endpoint DLP verrà inserito nel set di contenuti principale sulla prevenzione della perdita dei dati quando Endpoint DLP diventerà disponibile a livello generale.</span><span class="sxs-lookup"><span data-stu-id="906c9-163">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="906c9-164">Questi scenari di Endpoint DLP non sono le procedure ufficiali per la creazione e l'ottimizzazione di criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="906c9-164">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="906c9-165">Vedere gli argomenti seguenti quando è necessario usare i criteri di prevenzione della perdita dei dati in situazioni generiche:</span><span class="sxs-lookup"><span data-stu-id="906c9-165">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="906c9-166">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="906c9-166">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="906c9-167">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="906c9-167">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="906c9-168">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="906c9-168">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="906c9-169">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="906c9-169">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="906c9-170">Scenario 1: Creare un criterio da un modello, solo controllo</span><span class="sxs-lookup"><span data-stu-id="906c9-170">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="906c9-171">Per questi scenari è necessario aver già eseguito l'onboarding dei dispositivi che inviano report a Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-171">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="906c9-172">Se non si è ancora eseguito l'onboarding di dispositivi, vedere [Introduzione alla prevenzione della perdita di dati degli endpoint](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="906c9-172">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="906c9-173">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="906c9-173">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="906c9-174">Scegliere **Crea criterio**.</span><span class="sxs-lookup"><span data-stu-id="906c9-174">Choose **Create policy**.</span></span>

3. <span data-ttu-id="906c9-175">Per questo scenario, scegliere **Privacy** e poi **Informazioni personali (USA)**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-175">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="906c9-176">Impostare il campo **Stato** in posizione di disattivato per tutte le posizioni tranne **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="906c9-176">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="906c9-177">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-177">Choose **Next**.</span></span>

5. <span data-ttu-id="906c9-178">Accettare la selezione **Rivedere e personalizzare le impostazioni predefinite dal modello** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-178">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="906c9-179">Accettare i valori predefiniti per le **Azioni di protezione** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-179">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="906c9-180">Selezionare **Controlla o limita le attività nei dispositivi Windows** e uscire dalle azioni impostate su **Solo controllo**.</span><span class="sxs-lookup"><span data-stu-id="906c9-180">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="906c9-181">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-181">Choose **Next**.</span></span>

8. <span data-ttu-id="906c9-182">Accettare il valore predefinito **Vorrei prima testarli** e scegliere **Mostra i suggerimenti per i criteri in modalità di test**.</span><span class="sxs-lookup"><span data-stu-id="906c9-182">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="906c9-183">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="906c9-183">Choose **Next**.</span></span>

9. <span data-ttu-id="906c9-184">Rivedere le impostazioni e scegliere **Invia**.</span><span class="sxs-lookup"><span data-stu-id="906c9-184">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="906c9-185">Il nuovo criterio DLP verrà visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="906c9-185">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="906c9-186">Controllare i dati degli endpoint monitorati in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-186">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="906c9-187">Impostare il filtro della posizione per i dispositivi e aggiungere il criterio, quindi filtrare in base al nome del criterio per vederne l'impatto.</span><span class="sxs-lookup"><span data-stu-id="906c9-187">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="906c9-188">Se necessario, vedere [Introduzione a Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="906c9-188">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="906c9-189">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="906c9-189">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="906c9-190">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="906c9-190">This should trigger the policy.</span></span>

13. <span data-ttu-id="906c9-191">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-191">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="906c9-192">Scenario 2: Modificare il criterio esistente, impostare un avviso</span><span class="sxs-lookup"><span data-stu-id="906c9-192">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="906c9-193">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="906c9-193">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="906c9-194">Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="906c9-194">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="906c9-195">Scegliere **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="906c9-195">Choose **edit policy**.</span></span>

4. <span data-ttu-id="906c9-196">Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Volume ridotto di contenuti rilevato nelle informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="906c9-196">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="906c9-197">Scorrere verso il basso fino alla sezione **Report sugli eventi imprevisti** e impostare **Invia un avviso agli amministratori quando viene soddisfatta una regola** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="906c9-197">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="906c9-198">Gli avvisi di posta elettronica verranno inviati automaticamente all'amministratore e a tutti gli altri utenti aggiunti all'elenco dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="906c9-198">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="906c9-199">![attivare il report sugli eventi imprevisti](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="906c9-199">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="906c9-200">Ai fini del presente scenario, scegliere **Invia un avviso ogni volta che un'attività corrisponde alla regola**.</span><span class="sxs-lookup"><span data-stu-id="906c9-200">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="906c9-201">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="906c9-201">Choose **Save**.</span></span>

8. <span data-ttu-id="906c9-202">Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="906c9-202">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="906c9-203">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="906c9-203">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="906c9-204">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="906c9-204">This should trigger the policy.</span></span>

10. <span data-ttu-id="906c9-205">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-205">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="906c9-206">Scenario 3: Modificare il criterio esistente, bloccare l'azione con Consenti override</span><span class="sxs-lookup"><span data-stu-id="906c9-206">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="906c9-207">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="906c9-207">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="906c9-208">Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="906c9-208">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="906c9-209">Scegliere **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="906c9-209">Choose **edit policy**.</span></span>

4. <span data-ttu-id="906c9-210">Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Rilevato un volume ridotto di contenuti con informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="906c9-210">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="906c9-211">Scorrere verso il basso fino alla sezione **Controlla o limita le attività nei dispositivi Windows** e per ogni attività impostare l'azione corrispondente su **Blocca con override**.</span><span class="sxs-lookup"><span data-stu-id="906c9-211">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="906c9-212">![impostare l'azione Blocca con override](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="906c9-212">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="906c9-213">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="906c9-213">Choose **Save**.</span></span>

7. <span data-ttu-id="906c9-214">Ripetere i passaggi da 4 a 7 per **Rilevato un volume elevato di contenuti con informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="906c9-214">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="906c9-215">Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="906c9-215">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="906c9-216">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="906c9-216">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="906c9-217">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="906c9-217">This should trigger the policy.</span></span>

   <span data-ttu-id="906c9-218">Nel dispositivo client sarà visualizzato un popup come questo:</span><span class="sxs-lookup"><span data-stu-id="906c9-218">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="906c9-219">![notifica di override client bloccato di Endpoint DLP](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="906c9-219">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="906c9-220">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="906c9-220">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="906c9-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="906c9-221">See also</span></span>

- [<span data-ttu-id="906c9-222">Informazioni sulla prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="906c9-222">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="906c9-223">Introduzione alla prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="906c9-223">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="906c9-224">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="906c9-224">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="906c9-225">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="906c9-225">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="906c9-226">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="906c9-226">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="906c9-227">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="906c9-227">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="906c9-228">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="906c9-228">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="906c9-229">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="906c9-229">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="906c9-230">Dispositivi aggiunti ad Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="906c9-230">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="906c9-231">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="906c9-231">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="906c9-232">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="906c9-232">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="906c9-233">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="906c9-233">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
