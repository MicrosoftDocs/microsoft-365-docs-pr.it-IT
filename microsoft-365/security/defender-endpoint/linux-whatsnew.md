---
title: Novità di Microsoft Defender per Endpoint su Linux
description: Elenco delle modifiche principali per Microsoft Defender per Endpoint su Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: 999463f92c014e061bc4e2fdc22eedcd8f680a72
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903815"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ab7c8-104">Novità di Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="ab7c8-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="ab7c8-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ab7c8-106">Microsoft Defender per Endpoint su Linux è ora disponibile in anteprima per i clienti del governo statunitense.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="ab7c8-107">Per altre informazioni, vedi [Microsoft Defender for Endpoint per i clienti del governo statunitense.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="ab7c8-108">È stato risolto un problema a causa del quale l'uso di Microsoft Defender per Endpoint su Linux in sistemi con filesystem FUSE causava il blocco del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="ab7c8-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="ab7c8-109">Miglioramenti delle prestazioni & altre correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="ab7c8-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ab7c8-111">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="ab7c8-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="ab7c8-113">Miglioramento delle prestazioni per la situazione in cui un intero punto di montaggio viene aggiunto all'elenco di esclusione antivirus.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="ab7c8-114">Prima di questa versione, l'attività dei file originata dal punto di montaggio era ancora elaborata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="ab7c8-115">A partire da questa versione, l'attività dei file per i punti di montaggio esclusi viene eliminata, con un miglioramento delle prestazioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="ab7c8-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="ab7c8-116">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="ab7c8-117">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="ab7c8-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="ab7c8-118">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="ab7c8-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="ab7c8-119">101.18.53</span></span>

- <span data-ttu-id="ab7c8-120">EDR per Linux è [ora disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="ab7c8-121">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="ab7c8-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="ab7c8-122">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="ab7c8-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="ab7c8-123">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="ab7c8-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="ab7c8-124">101.12.99</span></span>

- <span data-ttu-id="ab7c8-125">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="ab7c8-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="ab7c8-126">101.04.76</span></span>

- <span data-ttu-id="ab7c8-127">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="ab7c8-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="ab7c8-128">101.03.48</span></span>

- <span data-ttu-id="ab7c8-129">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="ab7c8-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="ab7c8-130">101.02.55</span></span>

- <span data-ttu-id="ab7c8-131">È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ab7c8-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="ab7c8-132">È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="ab7c8-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="ab7c8-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="ab7c8-133">101.00.75</span></span>

- <span data-ttu-id="ab7c8-134">È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="ab7c8-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="ab7c8-135">Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ab7c8-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="ab7c8-136">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="ab7c8-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="ab7c8-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="ab7c8-138">Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="ab7c8-139">Ciò è dovuto a una modifica importante in un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="ab7c8-140">Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="ab7c8-141">Questo problema non esiste nelle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="ab7c8-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="ab7c8-142">Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="ab7c8-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="ab7c8-143">Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="ab7c8-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="ab7c8-144">Miglioramenti per rendere più affidabile l'installazione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="ab7c8-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="ab7c8-145">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="ab7c8-145">Performance improvements & bug fixes</span></span>
