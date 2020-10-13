---
title: Eseguire un'azione sui risultati delle query di ricerca avanzata in Microsoft Threat Protection
description: Indirizzare rapidamente le minacce e gli asset coinvolti nei risultati della query di ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, Take Action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429655"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="7ff20-104">Eseguire un'azione sui risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7ff20-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ff20-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7ff20-105">**Applies to:**</span></span>
- <span data-ttu-id="7ff20-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7ff20-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7ff20-107">È possibile contenere rapidamente le minacce o l'indirizzo di risorse compromesse che si trovano in [Advanced Hunting](advanced-hunting-overview.md) con opzioni di azione avanzate e potenti.</span><span class="sxs-lookup"><span data-stu-id="7ff20-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="7ff20-108">Con queste opzioni, è possibile:</span><span class="sxs-lookup"><span data-stu-id="7ff20-108">With these options, you can:</span></span>

- <span data-ttu-id="7ff20-109">Eseguire diverse azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7ff20-109">Take various actions on devices</span></span>
- <span data-ttu-id="7ff20-110">File di quarantena</span><span class="sxs-lookup"><span data-stu-id="7ff20-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7ff20-111">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="7ff20-111">Required permissions</span></span>
<span data-ttu-id="7ff20-112">Per poter intervenire tramite la caccia avanzata, è necessario un ruolo in Microsoft Defender ATP con [autorizzazioni per l'invio di azioni correttive sui dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="7ff20-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="7ff20-113">Se non è possibile eseguire l'azione, contattare un amministratore globale per ottenere l'autorizzazione seguente:</span><span class="sxs-lookup"><span data-stu-id="7ff20-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="7ff20-114">*Azioni correttive attive > gestione delle minacce e delle vulnerabilità-gestione della correzione*</span><span class="sxs-lookup"><span data-stu-id="7ff20-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="7ff20-115">Eseguire diverse azioni sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7ff20-115">Take various actions on devices</span></span>
<span data-ttu-id="7ff20-116">È possibile eseguire le azioni seguenti sui dispositivi identificati dalla `DeviceId` colonna nei risultati delle query:</span><span class="sxs-lookup"><span data-stu-id="7ff20-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="7ff20-117">Isolare i dispositivi coinvolti per contenere un'infezione o impedire che gli attacchi vengano spostati lateralmente</span><span class="sxs-lookup"><span data-stu-id="7ff20-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="7ff20-118">Raccolta del pacchetto di analisi per ottenere ulteriori informazioni forensi</span><span class="sxs-lookup"><span data-stu-id="7ff20-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="7ff20-119">Eseguire un'analisi antivirus per individuare e rimuovere le minacce con gli aggiornamenti più recenti di intelligence sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="7ff20-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="7ff20-120">Avviare un'indagine automatizzata per controllare e correggere le minacce sul dispositivo e, eventualmente, su altri dispositivi coinvolti</span><span class="sxs-lookup"><span data-stu-id="7ff20-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="7ff20-121">Limitare l'esecuzione delle app solo ai file eseguibili con firma Microsoft, impedendo successive attività di minacce tramite malware o altri eseguibili non attendibili</span><span class="sxs-lookup"><span data-stu-id="7ff20-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="7ff20-122">Per ulteriori informazioni sul modo in cui vengono eseguite queste azioni di risposta tramite Microsoft Defender ATP, [leggere informazioni sulle azioni di risposta sui dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="7ff20-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="7ff20-123">File di quarantena</span><span class="sxs-lookup"><span data-stu-id="7ff20-123">Quarantine files</span></span>
<span data-ttu-id="7ff20-124">È possibile distribuire l'azione di *quarantena* sui file in modo che vengano automaticamente messi in quarantena quando vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="7ff20-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="7ff20-125">Quando si seleziona questa azione, è possibile scegliere tra le colonne seguenti per identificare i file nei risultati della query per la quarantena:</span><span class="sxs-lookup"><span data-stu-id="7ff20-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="7ff20-126">`SHA1` -Nella maggior parte delle tabelle di caccia avanzate, questo è l'SHA-1 del file che è stato influenzato dall'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="7ff20-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="7ff20-127">Ad esempio, se un file è stato copiato, questo è il file copiato.</span><span class="sxs-lookup"><span data-stu-id="7ff20-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="7ff20-128">`InitiatingProcessSHA1` -Nella maggior parte delle tabelle di caccia avanzate, questo è il file responsabile dell'avvio dell'azione registrata.</span><span class="sxs-lookup"><span data-stu-id="7ff20-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="7ff20-129">Ad esempio, se è stato avviato un processo figlio, questo è il processo padre.</span><span class="sxs-lookup"><span data-stu-id="7ff20-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="7ff20-130">`SHA256` : Questo è l'equivalente SHA-256 del file identificato dalla `SHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="7ff20-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="7ff20-131">`InitiatingProcessSHA256` : Questo è l'equivalente SHA-256 del file identificato dalla `InitiatingProcessSHA1` colonna.</span><span class="sxs-lookup"><span data-stu-id="7ff20-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="7ff20-132">Per ulteriori informazioni sul modo in cui vengono eseguite le operazioni di quarantena e sulla modalità di ripristino dei file, [leggere informazioni sulle azioni di risposta sui file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="7ff20-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="7ff20-133">Per individuare i file e metterli in quarantena, i risultati della query devono includere anche `DeviceId` valori come identificatori di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ff20-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="7ff20-134">Azione</span><span class="sxs-lookup"><span data-stu-id="7ff20-134">Take action</span></span>
<span data-ttu-id="7ff20-135">Per eseguire una qualsiasi delle azioni descritte, selezionare uno o più record nei risultati della query e quindi fare clic su **azioni**.</span><span class="sxs-lookup"><span data-stu-id="7ff20-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="7ff20-136">Una procedura guidata vi guiderà nel processo di selezione e quindi di invio delle azioni preferite.</span><span class="sxs-lookup"><span data-stu-id="7ff20-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Immagine del record selezionato con pannello per l'ispezione del record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="7ff20-138">Esaminare le azioni intraprese</span><span class="sxs-lookup"><span data-stu-id="7ff20-138">Review actions taken</span></span>
<span data-ttu-id="7ff20-139">Ogni azione viene registrata singolarmente nell' [Action Center](mtp-action-center.md) in **Action Center**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="7ff20-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="7ff20-140">Andare al centro azioni per controllare lo stato di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="7ff20-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="7ff20-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7ff20-141">Related topics</span></span>
- [<span data-ttu-id="7ff20-142">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7ff20-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ff20-143">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7ff20-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7ff20-144">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="7ff20-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7ff20-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="7ff20-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7ff20-146">Panoramica del centro operazioni</span><span class="sxs-lookup"><span data-stu-id="7ff20-146">Action center overview</span></span>](mtp-action-center.md)
