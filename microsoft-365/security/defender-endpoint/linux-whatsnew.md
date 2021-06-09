---
title: Novità di Microsoft Defender per Endpoint su Linux
description: Elenco delle modifiche principali per Microsoft Defender per Endpoint su Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, novità, rilascio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651129"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="80df3-104">Novità di Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="80df3-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="80df3-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="80df3-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="80df3-106">A partire da questa versione, le minacce rilevate durante le analisi antivirus su richiesta attivate tramite il client della riga di comando vengono corretti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="80df3-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="80df3-107">Le minacce rilevate durante le analisi attivate tramite l'interfaccia utente richiedono comunque un'azione manuale.</span><span class="sxs-lookup"><span data-stu-id="80df3-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="80df3-108">`mdatp diagnostic real-time-protection-statistics` ora supporta due opzioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="80df3-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="80df3-109">`--sort`: ordina l'output in ordine decrescente in base al numero totale di file analizzati</span><span class="sxs-lookup"><span data-stu-id="80df3-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="80df3-110">`--top N`: visualizza i primi N risultati (funziona solo se `--sort` viene specificato anche)</span><span class="sxs-lookup"><span data-stu-id="80df3-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="80df3-111">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="80df3-112">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="80df3-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="80df3-113">Microsoft Defender per Endpoint su Linux è ora disponibile in anteprima per i clienti del governo statunitense.</span><span class="sxs-lookup"><span data-stu-id="80df3-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="80df3-114">Per altre informazioni, vedi [Microsoft Defender for Endpoint per i clienti del governo statunitense.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="80df3-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="80df3-115">È stato risolto un problema a causa del quale l'uso di Microsoft Defender per Endpoint su Linux in sistemi con filesystem FUSE causava il blocco del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="80df3-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="80df3-116">Miglioramenti delle prestazioni & altre correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="80df3-117">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="80df3-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="80df3-118">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="80df3-119">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="80df3-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="80df3-120">Miglioramento delle prestazioni per la situazione in cui un intero punto di montaggio viene aggiunto all'elenco di esclusione antivirus.</span><span class="sxs-lookup"><span data-stu-id="80df3-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="80df3-121">Prima di questa versione, l'attività dei file originata dal punto di montaggio era ancora elaborata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="80df3-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="80df3-122">A partire da questa versione, l'attività dei file per i punti di montaggio esclusi viene eliminata, con un miglioramento delle prestazioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="80df3-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="80df3-123">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="80df3-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="80df3-124">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="80df3-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="80df3-125">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="80df3-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="80df3-126">101.18.53</span></span>

- <span data-ttu-id="80df3-127">EDR per Linux è ora [disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="80df3-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="80df3-128">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="80df3-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="80df3-129">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="80df3-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="80df3-130">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="80df3-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="80df3-131">101.12.99</span></span>

- <span data-ttu-id="80df3-132">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="80df3-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="80df3-133">101.04.76</span></span>

- <span data-ttu-id="80df3-134">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="80df3-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="80df3-135">101.03.48</span></span>

- <span data-ttu-id="80df3-136">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="80df3-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="80df3-137">101.02.55</span></span>

- <span data-ttu-id="80df3-138">È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="80df3-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="80df3-139">È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="80df3-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="80df3-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="80df3-140">101.00.75</span></span>

- <span data-ttu-id="80df3-141">È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="80df3-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="80df3-142">Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="80df3-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="80df3-143">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="80df3-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="80df3-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="80df3-145">Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES.</span><span class="sxs-lookup"><span data-stu-id="80df3-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="80df3-146">Ciò è dovuto a una modifica importante in un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="80df3-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="80df3-147">Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente.</span><span class="sxs-lookup"><span data-stu-id="80df3-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="80df3-148">Questo problema non esiste nelle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="80df3-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="80df3-149">Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="80df3-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="80df3-150">Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="80df3-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="80df3-151">Miglioramenti per rendere più affidabile l'installazione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="80df3-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="80df3-152">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="80df3-152">Performance improvements & bug fixes</span></span>
