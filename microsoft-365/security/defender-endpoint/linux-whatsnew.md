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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198778"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="40d28-104">Novità di Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="40d28-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="40d28-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="40d28-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="40d28-106">Miglioramento delle prestazioni per la situazione in cui un intero punto di montaggio viene aggiunto all'elenco di esclusione antivirus.</span><span class="sxs-lookup"><span data-stu-id="40d28-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="40d28-107">Prima di questa versione, l'attività dei file originata dal punto di montaggio era ancora elaborata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="40d28-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="40d28-108">A partire da questa versione, l'attività dei file per i punti di montaggio esclusi viene eliminata, con un miglioramento delle prestazioni del prodotto</span><span class="sxs-lookup"><span data-stu-id="40d28-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="40d28-109">È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="40d28-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="40d28-110">Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="40d28-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="40d28-111">Altri miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="40d28-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="40d28-112">101.18.53</span></span>

- <span data-ttu-id="40d28-113">EDR per Linux è [ora disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="40d28-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="40d28-114">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="40d28-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="40d28-115">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="40d28-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="40d28-116">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="40d28-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="40d28-117">101.12.99</span></span>

- <span data-ttu-id="40d28-118">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="40d28-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="40d28-119">101.04.76</span></span>

- <span data-ttu-id="40d28-120">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="40d28-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="40d28-121">101.03.48</span></span>

- <span data-ttu-id="40d28-122">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="40d28-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="40d28-123">101.02.55</span></span>

- <span data-ttu-id="40d28-124">È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="40d28-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="40d28-125">È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="40d28-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="40d28-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="40d28-126">101.00.75</span></span>

- <span data-ttu-id="40d28-127">È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="40d28-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="40d28-128">Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="40d28-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="40d28-129">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="40d28-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="40d28-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="40d28-131">Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES.</span><span class="sxs-lookup"><span data-stu-id="40d28-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="40d28-132">Ciò è dovuto a una modifica importante in un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="40d28-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="40d28-133">Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente.</span><span class="sxs-lookup"><span data-stu-id="40d28-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="40d28-134">Questo problema non esiste nelle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="40d28-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="40d28-135">Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="40d28-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="40d28-136">Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="40d28-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="40d28-137">Miglioramenti per rendere più affidabile l'installazione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="40d28-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="40d28-138">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="40d28-138">Performance improvements & bug fixes</span></span>
