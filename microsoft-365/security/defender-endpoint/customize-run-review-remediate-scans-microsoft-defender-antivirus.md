---
title: Eseguire e personalizzare analisi pianificate e su richiesta
description: Personalizzare e avviare le analisi di Microsoft Defender Antivirus sugli endpoint della rete.
keywords: analizzare, pianificare, personalizzare, esclusioni, escludere file, correzione, risultati dell'analisi, quarantena, rimuovere minacce, analisi rapida, analisi completa, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765696"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="56022-104">Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="56022-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56022-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="56022-105">**Applies to:**</span></span>

- [<span data-ttu-id="56022-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="56022-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="56022-107">È possibile utilizzare Criteri di gruppo, PowerShell e Strumentazione gestione Windows (WMI) per configurare le analisi di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="56022-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="56022-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="56022-108">In this section</span></span>

<span data-ttu-id="56022-109">Argomento</span><span class="sxs-lookup"><span data-stu-id="56022-109">Topic</span></span> | <span data-ttu-id="56022-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56022-110">Description</span></span>
---|---
[<span data-ttu-id="56022-111">Configurare e convalidare le esclusioni di file, cartelle e file aperti dal processo nelle analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="56022-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-112">È possibile escludere file (inclusi file modificati da processi specificati) e cartelle da analisi su richiesta, analisi pianificate e monitoraggio e analisi della protezione in tempo reale sempre attiva</span><span class="sxs-lookup"><span data-stu-id="56022-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="56022-113">Configurare le opzioni di analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="56022-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-114">Puoi configurare Microsoft Defender Antivirus per includere determinati tipi di file di archiviazione della posta elettronica, punti di backup o di analisi e file archiviati (ad esempio file ZIP) nelle analisi.</span><span class="sxs-lookup"><span data-stu-id="56022-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="56022-115">È inoltre possibile abilitare l'analisi dei file di rete</span><span class="sxs-lookup"><span data-stu-id="56022-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="56022-116">Configurare la correzione per le analisi</span><span class="sxs-lookup"><span data-stu-id="56022-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-117">Configurare l'operazione che Microsoft Defender Antivirus deve eseguire quando rileva una minaccia e per quanto tempo i file in quarantena devono essere conservati nella cartella di quarantena</span><span class="sxs-lookup"><span data-stu-id="56022-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="56022-118">Configurare le analisi pianificate</span><span class="sxs-lookup"><span data-stu-id="56022-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-119">Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide</span><span class="sxs-lookup"><span data-stu-id="56022-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="56022-120">Configurare ed eseguire analisi</span><span class="sxs-lookup"><span data-stu-id="56022-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-121">Eseguire e configurare analisi su richiesta tramite PowerShell, Strumentazione gestione Windows o singolarmente sugli endpoint con l'app Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="56022-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="56022-122">Esaminare i risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="56022-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="56022-123">Esaminare i risultati delle analisi tramite Microsoft Endpoint Configuration Manager, Microsoft Intune o l'app Sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="56022-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>