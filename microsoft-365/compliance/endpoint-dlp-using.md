---
title: Uso della prevenzione della perdita di dati degli endpoint (anteprima)
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
ms.openlocfilehash: 0f1fc3159de6545007ddd62da2fca17ce87ad1dc
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636817"
---
# <a name="using-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="2e1ef-103">Uso della prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-103">Using Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="2e1ef-104">Questo articolo illustra tre scenari in cui si creano e modificano criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="2e1ef-105">Impostazioni DLP</span><span class="sxs-lookup"><span data-stu-id="2e1ef-105">DLP settings</span></span>

<span data-ttu-id="2e1ef-106">Prima di iniziare, è necessario configurare le impostazioni di prevenzione della perdita dei dati da applicare a tutti i criteri DLP per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="2e1ef-107">Vanno configurate se si prevede di creare criteri che impongono:</span><span class="sxs-lookup"><span data-stu-id="2e1ef-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="2e1ef-108">restrizioni di uscita dal cloud</span><span class="sxs-lookup"><span data-stu-id="2e1ef-108">cloud egress restrictions</span></span>
- <span data-ttu-id="2e1ef-109">restrizioni per app non consentite</span><span class="sxs-lookup"><span data-stu-id="2e1ef-109">unallowed apps restrictions</span></span>

<span data-ttu-id="2e1ef-110">Oppure</span><span class="sxs-lookup"><span data-stu-id="2e1ef-110">Or</span></span>

- <span data-ttu-id="2e1ef-111">Se si vogliono escludere dal monitoraggio i percorsi di file con troppi disturbi</span><span class="sxs-lookup"><span data-stu-id="2e1ef-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="2e1ef-112">![Impostazioni DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="2e1ef-113">Esclusioni di percorsi di file</span><span class="sxs-lookup"><span data-stu-id="2e1ef-113">File path exclusions</span></span>

<span data-ttu-id="2e1ef-114">È possibile escludere alcuni percorsi dal monitoraggio DLP, dagli avvisi DLP e dall'applicazione dei criteri DLP nei dispositivi, perché sono troppo disturbati o non contengono file a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="2e1ef-115">I file presenti in tali posizioni non verranno controllati e i file creati o modificati in tali posizioni non saranno soggetti all'applicazione dei criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="2e1ef-116">È possibile configurare le esclusioni di percorsi nelle impostazioni DLP.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="2e1ef-117">Per creare esclusioni di percorsi si può usare questa logica:</span><span class="sxs-lookup"><span data-stu-id="2e1ef-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="2e1ef-118">Percorso file valido che termina con "\", per indicare solo i file direttamente nella cartella.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="2e1ef-119">Ad esempio, C:\Temp</span><span class="sxs-lookup"><span data-stu-id="2e1ef-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="2e1ef-120">Percorso file valido che termina con "\*", per indicare solo i file all'interno di sottocartelle, oltre ai file direttamente nella cartella.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="2e1ef-121">Ad esempio, C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="2e1ef-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="2e1ef-122">Percorso file valido che termina senza "\" o "\*", per indicare tutti i file direttamente nella cartella e in tutte le sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="2e1ef-123">Ad esempio, C:\Temp</span><span class="sxs-lookup"><span data-stu-id="2e1ef-123">For example: C:\Temp</span></span>

- <span data-ttu-id="2e1ef-124">Percorso con carattere jolly compreso tra "\" su entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="2e1ef-125">Ad esempio, C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="2e1ef-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="2e1ef-126">Percorso con carattere jolly compreso tra "\" su entrambi i lati e con "(numero)" per indicare il numero esatto di sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="2e1ef-127">Ad esempio, C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="2e1ef-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="2e1ef-128">Un percorso con variabili di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="2e1ef-129">Ad esempio, %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="2e1ef-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="2e1ef-130">Una combinazione di tutti gli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-130">A mix of all the above.</span></span> <br/><span data-ttu-id="2e1ef-131">Ad esempio, %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="2e1ef-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="2e1ef-132">Domini del servizio</span><span class="sxs-lookup"><span data-stu-id="2e1ef-132">Service domains</span></span>

<span data-ttu-id="2e1ef-133">È possibile aggiungere domini a questo elenco, a cui Microsoft Edge Chromium farà riferimento durante l'applicazione della restrizione di accesso relativa al caricamento nel cloud di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="2e1ef-134">Se la modalità dell'elenco è impostata su **Blocca**, l'utente non potrà caricare elementi sensibili in tali domini.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-134">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="2e1ef-135">Quando un'azione di caricamento viene bloccata perché un elemento corrisponde a un criterio di prevenzione della perdita dei dati, DLP genera un avviso o blocca il caricamento dell'elemento sensibile.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-135">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="2e1ef-136">Se la modalità dell'elenco è impostata su **Consenti**, gli utenti possono caricare gli elementi sensibili \**_solo_*_ in questi domini e l'accesso in caricamento a tutti gli altri domini non è consentito.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-136">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_*_ to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="2e1ef-137">App non consentite</span><span class="sxs-lookup"><span data-stu-id="2e1ef-137">Unallowed apps</span></span>

<span data-ttu-id="2e1ef-138">Quando l'impostazione _*Accesso da app e browser non consentiti*\* di un criterio è attivata e gli utenti tentano di usare queste app per accedere a un file protetto, l'attività viene consentita, bloccata oppure bloccata ma gli utenti possono ignorare la restrizione.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-138">When a policy's _*Access by unallowed apps and browsers*\* setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="2e1ef-139">Tutte le attività sono controllate e disponibili per la revisione in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-139">All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="2e1ef-140">Browser non consentiti</span><span class="sxs-lookup"><span data-stu-id="2e1ef-140">Unallowed browsers</span></span>

<span data-ttu-id="2e1ef-141">È possibile aggiungere browser, identificati dai nomi eseguibili, a cui verrà impedito di accedere ai file che corrispondono alle condizioni di un criterio DLP applicato in cui la restrizione relativa al caricamento nei servizi cloud è impostata su Blocca o Blocca con override.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-141">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="2e1ef-142">Quando a questi browser viene impedito di accedere a un file, gli utenti finali vedranno una notifica di tipo avviso popup che chiede di aprire il file con Microsoft Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-142">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

[!IMPORTANT]
<span data-ttu-id="2e1ef-143">Non includere il percorso del file eseguibile, ma solo il nome eseguibile, (ossia browser. exe).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-143">Do not include the path to the executable, but only the executable name (i.e., browser.exe).</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="2e1ef-144">Unione di impostazioni DLP</span><span class="sxs-lookup"><span data-stu-id="2e1ef-144">Tying DLP settings together</span></span>

<span data-ttu-id="2e1ef-145">Con Endpoint DLP e il Web browser Microsoft Edge Chromium, è possibile limitare la condivisione involontaria di elementi sensibili con app e i servizi cloud non consentiti.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-145">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="2e1ef-146">Microsoft Edge Chromium riconosce quando un elemento è limitato da un criterio di Endpoint DLP e impone restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-146">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="2e1ef-147">Quando si usano il browser Microsoft Edge Chromium e la posizione Endpoint DLP in un criterio di prevenzione della perdita dei dati configurato correttamente, i browser non consentiti definiti in queste impostazioni non potranno accedere agli elementi sensibili che corrispondono ai controlli del criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-147">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="2e1ef-148">Gli utenti verranno reindirizzati all'uso di Microsoft Edge Chromium, che comprende le restrizioni imposte dalla prevenzione della perdita dei dati e può bloccare o limitare attività quando le condizioni indicate nel criterio DLP sono soddisfatte.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-148">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="2e1ef-149">Per usare questa restrizione sarà necessario configurare tre elementi importanti:</span><span class="sxs-lookup"><span data-stu-id="2e1ef-149">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="2e1ef-150">Specificare le posizioni, ovvero servizi, domini o indirizzi IP, con cui si vuole impedire la condivisione di elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-150">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="2e1ef-151">Aggiungere i browser ai quali non è consentito accedere a determinati elementi sensibili in caso di corrispondenza con un criterio DLP.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-151">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="2e1ef-152">Configurare criteri DLP per definire i tipi di elementi sensibili per cui limitare il caricamento in queste posizioni, attivando **Carica nei servizi cloud** e **Accedi dai browser non consentiti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-152">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="2e1ef-153">È possibile continuare ad aggiungere nuovi servizi, app e criteri per estendere e aumentare le restrizioni in modo da soddisfare le esigenze dell'azienda e proteggere i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-153">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="2e1ef-154">Questa configurazione contribuirà a garantire la sicurezza dei dati, evitando anche restrizioni inutili che limitano la capacità degli utenti di accedere a elementi non riservati e condividerli.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-154">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="2e1ef-155">Scenari dei criteri di Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="2e1ef-155">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="2e1ef-156">Per acquisire familiarità con le funzionalità di Endpoint DLP e su come vengono visualizzate nei criteri DLP, sono stati predisposti alcuni scenari da seguire.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-156">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="2e1ef-157">Tutto il contenuto di Endpoint DLP verrà inserito nel set di contenuti principale sulla prevenzione della perdita dei dati quando Endpoint DLP diventerà disponibile a livello generale.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-157">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e1ef-158">Questi scenari di Endpoint DLP non sono le procedure ufficiali per la creazione e l'ottimizzazione di criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-158">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="2e1ef-159">Vedere gli argomenti seguenti quando è necessario usare i criteri di prevenzione della perdita dei dati in situazioni generiche:</span><span class="sxs-lookup"><span data-stu-id="2e1ef-159">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="2e1ef-160">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="2e1ef-160">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="2e1ef-161">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="2e1ef-161">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="2e1ef-162">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="2e1ef-162">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="2e1ef-163">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="2e1ef-163">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="2e1ef-164">Scenario 1: Creare un criterio da un modello, solo controllo</span><span class="sxs-lookup"><span data-stu-id="2e1ef-164">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="2e1ef-165">Per questi scenari è necessario aver già eseguito l'onboarding di dispositivi, che inviano report a Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-165">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="2e1ef-166">Se non si è ancora eseguito l'onboarding di dispositivi, vedere [Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-166">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention (preview)](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="2e1ef-167">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-167">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="2e1ef-168">Scegliere **Crea criterio (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-168">Choose **Create policy (preview)**.</span></span>

3. <span data-ttu-id="2e1ef-169">Per questo scenario, scegliere **Privacy** e poi **Informazioni personali (USA)**, quindi sceg **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-169">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="2e1ef-170">Impostare il campo **Stato** in posizione di disattivato per tutte le posizioni tranne **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-170">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="2e1ef-171">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-171">Choose **Next**.</span></span>

5. <span data-ttu-id="2e1ef-172">Accettare la selezione **Rivedere e personalizzare le impostazioni predefinite dal modello** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-172">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="2e1ef-173">Accettare i valori predefiniti per le **Azioni di protezione** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-173">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="2e1ef-174">Selezionare **Controlla o limita le attività nei dispositivi Windows** e uscire dalle azioni impostate su **Solo controllo**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-174">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="2e1ef-175">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-175">Choose **Next**.</span></span>

8. <span data-ttu-id="2e1ef-176">Accettare il valore predefinito **Vorrei prima testarli** e scegliere **Mostra i suggerimenti per i criteri in modalità di test**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-176">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="2e1ef-177">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-177">Choose **Next**.</span></span>

9. <span data-ttu-id="2e1ef-178">Rivedere le impostazioni e scegliere **Invia**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-178">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="2e1ef-179">Il nuovo criterio DLP verrà visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-179">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="2e1ef-180">Controllare i dati degli endpoint monitorati in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-180">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="2e1ef-181">Impostare il filtro della posizione per i dispositivi e aggiungere il criterio, quindi filtrare in base al nome del criterio per vederne l'impatto.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-181">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="2e1ef-182">Se necessario, vedere [Introduzione a Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-182">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="2e1ef-183">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-183">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="2e1ef-184">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-184">This should trigger the policy.</span></span>

13. <span data-ttu-id="2e1ef-185">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="2e1ef-186">Scenario 2: Modificare il criterio esistente, impostare un avviso</span><span class="sxs-lookup"><span data-stu-id="2e1ef-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="2e1ef-187">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="2e1ef-188">Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="2e1ef-189">Scegliere **Modifica criterio (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-189">Choose **edit policy (preview)**.</span></span>

4. <span data-ttu-id="2e1ef-190">Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Rilevato un volume ridotto di contenuti con informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="2e1ef-191">Scorrere verso il basso fino alla sezione **Report sugli eventi imprevisti** e impostare **Invia un avviso agli amministratori quando viene soddisfatta una regola** su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-191">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="2e1ef-192">Gli avvisi di posta elettronica verranno inviati automaticamente all'amministratore e a tutti gli altri utenti aggiunti all'elenco dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-192">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e1ef-193">![attivare il report sugli eventi imprevisti](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="2e1ef-194">Ai fini del presente scenario, scegliere **Invia un avviso ogni volta che un'attività corrisponde alla regola**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="2e1ef-195">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-195">Choose **Save**.</span></span>

8. <span data-ttu-id="2e1ef-196">Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="2e1ef-197">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-197">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="2e1ef-198">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-198">This should trigger the policy.</span></span>

10. <span data-ttu-id="2e1ef-199">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="2e1ef-200">Scenario 3: Modificare il criterio esistente, bloccare l'azione con Consenti override</span><span class="sxs-lookup"><span data-stu-id="2e1ef-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="2e1ef-201">Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="2e1ef-202">Scegliere il criterio **Informazioni personali (USA)** creato nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="2e1ef-203">Scegliere **Modifica criterio (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-203">Choose **edit policy (preview)**.</span></span>

4. <span data-ttu-id="2e1ef-204">Passare alla pagina **Regole avanzate di prevenzione della perdita dei dati** e modificare il **Rilevato un volume ridotto di contenuti con informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="2e1ef-205">Scorrere verso il basso fino alla sezione **Controlla o limita le attività nei dispositivi Windows** e per ogni attività impostare l'azione corrispondente su **Blocca con override**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e1ef-206">![impostare l'azione Blocca con override](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="2e1ef-207">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-207">Choose **Save**.</span></span>

7. <span data-ttu-id="2e1ef-208">Ripetere i passaggi da 4 a 7 per **Rilevato un volume elevato di contenuti con informazioni personali (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="2e1ef-209">Conservare tutte le impostazioni precedenti scegliendo **Avanti** e quindi **Invia** per applicare le modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="2e1ef-210">Provare a condividere con un utente esterno all'organizzazione un test con contenuto che attiverà la condizione Informazioni personali (USA).</span><span class="sxs-lookup"><span data-stu-id="2e1ef-210">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="2e1ef-211">Questo dovrebbe attivare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-211">This should trigger the policy.</span></span>

   <span data-ttu-id="2e1ef-212">Nel dispositivo client sarà visualizzato un popup come questo:</span><span class="sxs-lookup"><span data-stu-id="2e1ef-212">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e1ef-213">![notifica di override client bloccato di Endpoint DLP](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-213">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="2e1ef-214">Controllare l'evento in Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="2e1ef-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e1ef-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e1ef-215">See also</span></span>

- [<span data-ttu-id="2e1ef-216">Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-216">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="2e1ef-217">Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-217">Get started with Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="2e1ef-218">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="2e1ef-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2e1ef-219">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="2e1ef-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2e1ef-220">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="2e1ef-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2e1ef-221">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-221">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="2e1ef-222">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e1ef-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="2e1ef-223">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e1ef-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="2e1ef-224">Dispositivi aggiunti ad Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="2e1ef-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="2e1ef-225">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="2e1ef-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="2e1ef-226">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="2e1ef-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="2e1ef-227">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="2e1ef-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
