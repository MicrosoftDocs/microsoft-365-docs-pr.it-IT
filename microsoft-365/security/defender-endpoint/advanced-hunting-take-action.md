---
title: Eseguire azioni sui risultati delle query di ricerca avanzata in Microsoft Threat Protection
description: Affrontare rapidamente le minacce e gli asset interessati nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, evitare timeout, righe di comando, ID processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067413"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="7961f-104">Eseguire un'azione sui risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7961f-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="7961f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7961f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7961f-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="7961f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="7961f-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7961f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7961f-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7961f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="7961f-109">Puoi contenere rapidamente minacce o affrontare asset compromessi che trovi nella ricerca [avanzata](advanced-hunting-overview.md) usando opzioni di azione potenti e complete.</span><span class="sxs-lookup"><span data-stu-id="7961f-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="7961f-110">Con queste opzioni, è possibile:</span><span class="sxs-lookup"><span data-stu-id="7961f-110">With these options, you can:</span></span>

- <span data-ttu-id="7961f-111">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7961f-111">Take various actions on devices</span></span>
- <span data-ttu-id="7961f-112">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="7961f-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7961f-113">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="7961f-113">Required permissions</span></span>

<span data-ttu-id="7961f-114">Per essere in grado di eseguire azioni tramite la ricerca avanzata, è necessario un ruolo in Defender per Endpoint con autorizzazioni per inviare azioni di correzione [nei dispositivi](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="7961f-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="7961f-115">Se non è possibile eseguire un'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:</span><span class="sxs-lookup"><span data-stu-id="7961f-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="7961f-116">*Azioni di correzione attive > gestione delle minacce e delle vulnerabilità - Gestione delle correzioni*</span><span class="sxs-lookup"><span data-stu-id="7961f-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="7961f-117">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7961f-117">Take various actions on devices</span></span>

<span data-ttu-id="7961f-118">È possibile eseguire le azioni seguenti nei dispositivi identificati dalla `DeviceId` colonna nei risultati della query:</span><span class="sxs-lookup"><span data-stu-id="7961f-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="7961f-119">Isolare i dispositivi interessati per contenere un'infezione o impedire lo spostamento laterale di attacchi</span><span class="sxs-lookup"><span data-stu-id="7961f-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="7961f-120">Raccogliere un pacchetto di indagine per ottenere ulteriori informazioni forensi</span><span class="sxs-lookup"><span data-stu-id="7961f-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="7961f-121">Eseguire un'analisi antivirus per trovare e rimuovere le minacce utilizzando gli ultimi aggiornamenti di security intelligence</span><span class="sxs-lookup"><span data-stu-id="7961f-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="7961f-122">Avviare un'indagine automatizzata per controllare e correggere le minacce nel dispositivo e probabilmente in altri dispositivi interessati</span><span class="sxs-lookup"><span data-stu-id="7961f-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="7961f-123">Limitare l'esecuzione dell'app solo ai file eseguibili firmati da Microsoft, impedendo attività di minacce successive tramite malware o altri file eseguibili non attendibili</span><span class="sxs-lookup"><span data-stu-id="7961f-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="7961f-124">Per altre informazioni su come vengono eseguite queste azioni di risposta tramite Defender for Endpoint, [leggi azioni di risposta nei dispositivi](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7961f-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="7961f-125">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="7961f-125">Quarantine files</span></span>

<span data-ttu-id="7961f-126">È possibile distribuire *l'azione di* quarantena sui file in modo che siano automaticamente messi in quarantena quando vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="7961f-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="7961f-127">Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query da mettere in quarantena:</span><span class="sxs-lookup"><span data-stu-id="7961f-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="7961f-128">`SHA1` — Nella maggior parte delle tabelle di ricerca avanzate, si tratta dell'SHA-1 del file interessato dall'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="7961f-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="7961f-129">Ad esempio, se un file è stato copiato, si tratta del file copiato.</span><span class="sxs-lookup"><span data-stu-id="7961f-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="7961f-130">`InitiatingProcessSHA1` — Nella maggior parte delle tabelle di ricerca avanzate, questo è il file responsabile dell'avvio dell'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="7961f-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="7961f-131">Ad esempio, se è stato avviato un processo figlio, si tratta del processo padre.</span><span class="sxs-lookup"><span data-stu-id="7961f-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="7961f-132">`SHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="7961f-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="7961f-133">`InitiatingProcessSHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="7961f-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="7961f-134">Per ulteriori informazioni su come vengono eseguite le azioni di quarantena e su come è possibile ripristinare i file, [vedere Azioni di risposta nei file](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7961f-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="7961f-135">Per individuare i file e mettereli in quarantena, i risultati della query devono includere `DeviceId` anche valori come identificatori di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7961f-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="7961f-136">Eseguire un'azione</span><span class="sxs-lookup"><span data-stu-id="7961f-136">Take action</span></span>

<span data-ttu-id="7961f-137">Per eseguire una delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic **su Azioni.**</span><span class="sxs-lookup"><span data-stu-id="7961f-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="7961f-138">Una procedura guidata ti guiderà nel processo di selezione e invio delle azioni preferite.</span><span class="sxs-lookup"><span data-stu-id="7961f-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Immagine del record selezionato con il pannello per l'ispezione del record](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="7961f-140">Rivedere le azioni intraprese</span><span class="sxs-lookup"><span data-stu-id="7961f-140">Review actions taken</span></span>

<span data-ttu-id="7961f-141">Ogni azione viene registrata singolarmente nel centro notifiche, in **Cronologia centro** notifiche (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="7961f-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="7961f-142">Passare al centro notifiche per controllare lo stato di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="7961f-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="7961f-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7961f-143">Related topics</span></span>

- [<span data-ttu-id="7961f-144">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7961f-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7961f-145">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7961f-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7961f-146">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7961f-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="7961f-147">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="7961f-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7961f-148">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="7961f-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7961f-149">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="7961f-149">Custom detections overview</span></span>](overview-custom-detections.md)
