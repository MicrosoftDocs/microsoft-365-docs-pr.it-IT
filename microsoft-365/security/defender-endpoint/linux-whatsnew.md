---
title: Novità di Microsoft Defender per Endpoint per Linux
description: Elenco delle modifiche principali per Microsoft Defender ATP per Linux.
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581003"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="26032-104">Novità di Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="26032-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="26032-105">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="26032-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="26032-106">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="26032-107">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="26032-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="26032-108">Miglioramento delle prestazioni per la situazione in cui un intero punto di montaggio viene aggiunto all'elenco di esclusione antivirus.</span><span class="sxs-lookup"><span data-stu-id="26032-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="26032-109">Prima di questa versione, l'attività dei file originata dal punto di montaggio era ancora elaborata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="26032-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="26032-110">A partire da questa versione, l'attività dei file per i punti di montaggio esclusi viene eliminata, con un miglioramento delle prestazioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="26032-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="26032-111">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="26032-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="26032-112">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="26032-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="26032-113">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="26032-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="26032-114">101.18.53</span></span>

- <span data-ttu-id="26032-115">EDR per Linux è [ora disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="26032-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="26032-116">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="26032-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="26032-117">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="26032-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="26032-118">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="26032-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="26032-119">101.12.99</span></span>

- <span data-ttu-id="26032-120">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="26032-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="26032-121">101.04.76</span></span>

- <span data-ttu-id="26032-122">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="26032-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="26032-123">101.03.48</span></span>

- <span data-ttu-id="26032-124">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="26032-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="26032-125">101.02.55</span></span>

- <span data-ttu-id="26032-126">È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="26032-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="26032-127">È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="26032-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="26032-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="26032-128">101.00.75</span></span>

- <span data-ttu-id="26032-129">È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="26032-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="26032-130">Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="26032-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="26032-131">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="26032-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="26032-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="26032-133">Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES.</span><span class="sxs-lookup"><span data-stu-id="26032-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="26032-134">Ciò è dovuto a una modifica importante in un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="26032-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="26032-135">Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente.</span><span class="sxs-lookup"><span data-stu-id="26032-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="26032-136">Questo problema non esiste nelle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="26032-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="26032-137">Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="26032-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="26032-138">Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="26032-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="26032-139">Miglioramenti per rendere più affidabile l'installazione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="26032-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="26032-140">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="26032-140">Performance improvements & bug fixes</span></span>
