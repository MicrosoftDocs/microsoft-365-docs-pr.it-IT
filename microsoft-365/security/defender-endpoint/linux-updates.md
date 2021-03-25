---
title: Distribuire gli aggiornamenti per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come distribuire gli aggiornamenti per Microsoft Defender ATP per Linux in ambienti aziendali.
keywords: microsoft, defender, atp, linux, aggiornamenti, distribuire
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187722"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="01a7d-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="01a7d-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="01a7d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="01a7d-105">**Applies to:**</span></span>
- [<span data-ttu-id="01a7d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="01a7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01a7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01a7d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="01a7d-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="01a7d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="01a7d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="01a7d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="01a7d-110">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="01a7d-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="01a7d-111">Ogni versione di Defender per Endpoint per Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="01a7d-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="01a7d-112">È necessario aggiornare il prodotto prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="01a7d-112">You must update the product prior to this date.</span></span> <span data-ttu-id="01a7d-113">Per verificare la data di scadenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="01a7d-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="01a7d-114">Per aggiornare manualmente Defender per Endpoint per Linux, eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="01a7d-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="01a7d-115">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="01a7d-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="01a7d-116">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="01a7d-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="01a7d-117">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="01a7d-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
