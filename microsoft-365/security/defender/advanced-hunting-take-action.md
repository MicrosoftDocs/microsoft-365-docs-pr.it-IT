---
title: Eseguire azioni sui risultati delle query di ricerca avanzate in Microsoft 365 Defender
description: Affrontare rapidamente le minacce e gli asset interessati nei risultati delle query di ricerca avanzate
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, agire
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
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952609"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="893a0-104">Eseguire un'azione sui risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="893a0-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="893a0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="893a0-105">**Applies to:**</span></span>
- <span data-ttu-id="893a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="893a0-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="893a0-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="893a0-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="893a0-108">Puoi contenere rapidamente minacce o affrontare asset compromessi che trovi nella ricerca [avanzata](advanced-hunting-overview.md) usando opzioni di azione potenti e complete.</span><span class="sxs-lookup"><span data-stu-id="893a0-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="893a0-109">Con queste opzioni, è possibile:</span><span class="sxs-lookup"><span data-stu-id="893a0-109">With these options, you can:</span></span>

- <span data-ttu-id="893a0-110">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="893a0-110">Take various actions on devices</span></span>
- <span data-ttu-id="893a0-111">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="893a0-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="893a0-112">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="893a0-112">Required permissions</span></span>
<span data-ttu-id="893a0-113">Per essere in grado di eseguire azioni tramite la ricerca avanzata, è necessario un ruolo in Microsoft Defender per Endpoint con autorizzazioni per inviare azioni di correzione [nei dispositivi](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="893a0-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="893a0-114">Se non è possibile eseguire un'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:</span><span class="sxs-lookup"><span data-stu-id="893a0-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="893a0-115">*Azioni di correzione attive > minacce e gestione delle vulnerabilità - Gestione delle correzioni*</span><span class="sxs-lookup"><span data-stu-id="893a0-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="893a0-116">Eseguire varie azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="893a0-116">Take various actions on devices</span></span>
<span data-ttu-id="893a0-117">Puoi eseguire le azioni seguenti nei dispositivi identificati dalla `DeviceId` colonna nei risultati delle query:</span><span class="sxs-lookup"><span data-stu-id="893a0-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="893a0-118">Isolare i dispositivi interessati per contenere un'infezione o impedire lo spostamento laterale di attacchi</span><span class="sxs-lookup"><span data-stu-id="893a0-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="893a0-119">Raccogliere un pacchetto di indagine per ottenere ulteriori informazioni forensi</span><span class="sxs-lookup"><span data-stu-id="893a0-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="893a0-120">Eseguire un'analisi antivirus per trovare e rimuovere le minacce utilizzando gli ultimi aggiornamenti di security intelligence</span><span class="sxs-lookup"><span data-stu-id="893a0-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="893a0-121">Avviare un'indagine automatizzata per controllare e correggere le minacce nel dispositivo e probabilmente in altri dispositivi interessati</span><span class="sxs-lookup"><span data-stu-id="893a0-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="893a0-122">Limitare l'esecuzione dell'app solo ai file eseguibili firmati da Microsoft, impedendo attività di minacce successive tramite malware o altri file eseguibili non attendibili</span><span class="sxs-lookup"><span data-stu-id="893a0-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="893a0-123">Per altre informazioni su come vengono eseguite queste azioni di risposta tramite Microsoft Defender for Endpoint, [leggi azioni di risposta nei dispositivi](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="893a0-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="893a0-124">File in quarantena</span><span class="sxs-lookup"><span data-stu-id="893a0-124">Quarantine files</span></span>
<span data-ttu-id="893a0-125">È possibile distribuire *l'azione di* quarantena sui file in modo che siano automaticamente messi in quarantena quando vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="893a0-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="893a0-126">Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query da mettere in quarantena:</span><span class="sxs-lookup"><span data-stu-id="893a0-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="893a0-127">`SHA1` — Nella maggior parte delle tabelle di ricerca avanzate, si tratta dell'SHA-1 del file interessato dall'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="893a0-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="893a0-128">Ad esempio, se un file è stato copiato, si tratta del file copiato.</span><span class="sxs-lookup"><span data-stu-id="893a0-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="893a0-129">`InitiatingProcessSHA1` — Nella maggior parte delle tabelle di ricerca avanzate, questo è il file responsabile dell'avvio dell'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="893a0-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="893a0-130">Ad esempio, se è stato avviato un processo figlio, si tratta del processo padre.</span><span class="sxs-lookup"><span data-stu-id="893a0-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="893a0-131">`SHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="893a0-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="893a0-132">`InitiatingProcessSHA256` - Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="893a0-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="893a0-133">Per ulteriori informazioni su come vengono eseguite le azioni di quarantena e su come è possibile ripristinare i file, [vedere Azioni di risposta nei file](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="893a0-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="893a0-134">Per individuare i file e mettereli in quarantena, i risultati della query devono includere `DeviceId` anche valori come identificatori di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="893a0-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="893a0-135">Entra in azione</span><span class="sxs-lookup"><span data-stu-id="893a0-135">Take action</span></span>
<span data-ttu-id="893a0-136">Per eseguire una delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic **su Azioni.**</span><span class="sxs-lookup"><span data-stu-id="893a0-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="893a0-137">Una procedura guidata ti guiderà nel processo di selezione e invio delle azioni preferite.</span><span class="sxs-lookup"><span data-stu-id="893a0-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Immagine del record selezionato con il pannello per l'ispezione del record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="893a0-139">Rivedere le azioni intraprese</span><span class="sxs-lookup"><span data-stu-id="893a0-139">Review actions taken</span></span>
<span data-ttu-id="893a0-140">Ogni azione viene registrata singolarmente nel centro notifiche [in](m365d-action-center.md) **Cronologia centro** notifiche (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="893a0-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="893a0-141">Passare al centro notifiche per controllare lo stato di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="893a0-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="893a0-142">Alcune tabelle di questo articolo potrebbero non essere disponibili in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="893a0-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="893a0-143">[Attivare Microsoft 365 Defender per](m365d-enable.md) cercare minacce che usano più origini dati.</span><span class="sxs-lookup"><span data-stu-id="893a0-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="893a0-144">Puoi spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender per Endpoint a Microsoft 365 Defender seguendo la procedura descritta in Eseguire la migrazione di query di ricerca avanzate da [Microsoft Defender per Endpoint.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="893a0-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="893a0-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="893a0-145">Related topics</span></span>
- [<span data-ttu-id="893a0-146">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="893a0-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="893a0-147">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="893a0-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="893a0-148">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="893a0-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="893a0-149">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="893a0-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="893a0-150">Panoramica del centro notifiche</span><span class="sxs-lookup"><span data-stu-id="893a0-150">Action center overview</span></span>](m365d-action-center.md)
