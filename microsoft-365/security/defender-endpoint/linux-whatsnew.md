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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062450"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="72170-104">Novità di Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="72170-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="72170-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="72170-105">101.18.53</span></span>

- <span data-ttu-id="72170-106">EDR per Linux è [ora disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="72170-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="72170-107">È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="72170-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="72170-108">Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa</span><span class="sxs-lookup"><span data-stu-id="72170-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="72170-109">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="72170-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="72170-110">101.12.99</span></span>

- <span data-ttu-id="72170-111">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="72170-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="72170-112">101.04.76</span></span>

- <span data-ttu-id="72170-113">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="72170-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="72170-114">101.03.48</span></span>

- <span data-ttu-id="72170-115">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="72170-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="72170-116">101.02.55</span></span>

- <span data-ttu-id="72170-117">È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento</span><span class="sxs-lookup"><span data-stu-id="72170-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="72170-118">È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto</span><span class="sxs-lookup"><span data-stu-id="72170-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="72170-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="72170-119">101.00.75</span></span>

- <span data-ttu-id="72170-120">È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="72170-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="72170-121">Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="72170-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="72170-122">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="72170-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="72170-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="72170-124">Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES.</span><span class="sxs-lookup"><span data-stu-id="72170-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="72170-125">Ciò è dovuto a una modifica importante in un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="72170-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="72170-126">Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente.</span><span class="sxs-lookup"><span data-stu-id="72170-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="72170-127">Questo problema non esiste nelle versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="72170-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="72170-128">Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="72170-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="72170-129">Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="72170-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="72170-130">Miglioramenti per rendere più affidabile l'installazione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="72170-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="72170-131">Miglioramenti delle prestazioni & correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="72170-131">Performance improvements & bug fixes</span></span>
