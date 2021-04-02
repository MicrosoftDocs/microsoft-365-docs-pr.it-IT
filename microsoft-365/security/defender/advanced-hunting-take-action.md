---
title: Eseguire azioni sui risultati delle query di ricerca avanzate in Microsoft 365 Defender
description: Affrontare rapidamente le minacce e gli asset interessati nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, azione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ee35bcc29ef8a283b6b04cb34ab97705d5dd15f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498234"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="9c09a-104">Eseguire un'azione sui risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9c09a-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9c09a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9c09a-105">**Applies to:**</span></span>
- <span data-ttu-id="9c09a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c09a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9c09a-107">Puoi contenere rapidamente minacce o affrontare asset compromessi che trovi nella ricerca [avanzata](advanced-hunting-overview.md) usando opzioni di azione potenti e complete.</span><span class="sxs-lookup"><span data-stu-id="9c09a-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="9c09a-108">Con queste opzioni, è possibile:</span><span class="sxs-lookup"><span data-stu-id="9c09a-108">With these options, you can:</span></span>

- <span data-ttu-id="9c09a-109">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="9c09a-109">Take various actions on devices</span></span>
- <span data-ttu-id="9c09a-110">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="9c09a-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="9c09a-111">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="9c09a-111">Required permissions</span></span>
<span data-ttu-id="9c09a-112">Per essere in grado di eseguire azioni tramite la ricerca avanzata, è necessario un ruolo in Microsoft Defender per Endpoint con autorizzazioni per inviare azioni di correzione [nei dispositivi](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="9c09a-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="9c09a-113">Se non è possibile eseguire un'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:</span><span class="sxs-lookup"><span data-stu-id="9c09a-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="9c09a-114">*Azioni di correzione attive > gestione delle minacce e delle vulnerabilità - Gestione delle correzioni*</span><span class="sxs-lookup"><span data-stu-id="9c09a-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="9c09a-115">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="9c09a-115">Take various actions on devices</span></span>
<span data-ttu-id="9c09a-116">Puoi eseguire le azioni seguenti nei dispositivi identificati dalla `DeviceId` colonna nei risultati delle query:</span><span class="sxs-lookup"><span data-stu-id="9c09a-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="9c09a-117">Isolare i dispositivi interessati per contenere un'infezione o impedire lo spostamento laterale di attacchi</span><span class="sxs-lookup"><span data-stu-id="9c09a-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="9c09a-118">Raccogliere un pacchetto di indagine per ottenere ulteriori informazioni forensi</span><span class="sxs-lookup"><span data-stu-id="9c09a-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="9c09a-119">Eseguire un'analisi antivirus per trovare e rimuovere le minacce utilizzando gli ultimi aggiornamenti di security intelligence</span><span class="sxs-lookup"><span data-stu-id="9c09a-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="9c09a-120">Avviare un'indagine automatizzata per controllare e correggere le minacce nel dispositivo e probabilmente in altri dispositivi interessati</span><span class="sxs-lookup"><span data-stu-id="9c09a-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="9c09a-121">Limitare l'esecuzione dell'app solo ai file eseguibili firmati da Microsoft, impedendo attività di minacce successive tramite malware o altri file eseguibili non attendibili</span><span class="sxs-lookup"><span data-stu-id="9c09a-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="9c09a-122">Per altre informazioni su come vengono eseguite queste azioni di risposta tramite Microsoft Defender for Endpoint, [leggi azioni di risposta nei dispositivi](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="9c09a-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="9c09a-123">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="9c09a-123">Quarantine files</span></span>
<span data-ttu-id="9c09a-124">È possibile distribuire *l'azione di* quarantena sui file in modo che siano automaticamente messi in quarantena quando vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="9c09a-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="9c09a-125">Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query da mettere in quarantena:</span><span class="sxs-lookup"><span data-stu-id="9c09a-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="9c09a-126">`SHA1` — Nella maggior parte delle tabelle di ricerca avanzate, si tratta dell'SHA-1 del file interessato dall'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="9c09a-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="9c09a-127">Ad esempio, se un file è stato copiato, si tratta del file copiato.</span><span class="sxs-lookup"><span data-stu-id="9c09a-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="9c09a-128">`InitiatingProcessSHA1` — Nella maggior parte delle tabelle di ricerca avanzate, questo è il file responsabile dell'avvio dell'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="9c09a-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="9c09a-129">Ad esempio, se è stato avviato un processo figlio, si tratta del processo padre.</span><span class="sxs-lookup"><span data-stu-id="9c09a-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="9c09a-130">`SHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="9c09a-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="9c09a-131">`InitiatingProcessSHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="9c09a-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="9c09a-132">Per ulteriori informazioni su come vengono eseguite le azioni di quarantena e su come è possibile ripristinare i file, [vedere Azioni di risposta nei file](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="9c09a-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="9c09a-133">Per individuare i file e mettereli in quarantena, i risultati della query devono includere `DeviceId` anche valori come identificatori di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9c09a-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="9c09a-134">Eseguire un'azione</span><span class="sxs-lookup"><span data-stu-id="9c09a-134">Take action</span></span>
<span data-ttu-id="9c09a-135">Per eseguire una delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic **su Azioni.**</span><span class="sxs-lookup"><span data-stu-id="9c09a-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="9c09a-136">Una procedura guidata ti guiderà nel processo di selezione e invio delle azioni preferite.</span><span class="sxs-lookup"><span data-stu-id="9c09a-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Immagine del record selezionato con il pannello per l'ispezione del record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="9c09a-138">Rivedere le azioni intraprese</span><span class="sxs-lookup"><span data-stu-id="9c09a-138">Review actions taken</span></span>
<span data-ttu-id="9c09a-139">Ogni azione viene registrata singolarmente nel centro notifiche [in](m365d-action-center.md) **Cronologia centro** notifiche (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="9c09a-139">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="9c09a-140">Passare al centro notifiche per controllare lo stato di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="9c09a-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="9c09a-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9c09a-141">Related topics</span></span>
- [<span data-ttu-id="9c09a-142">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="9c09a-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9c09a-143">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="9c09a-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9c09a-144">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="9c09a-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="9c09a-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="9c09a-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9c09a-146">Panoramica del centro notifiche</span><span class="sxs-lookup"><span data-stu-id="9c09a-146">Action center overview</span></span>](m365d-action-center.md)
