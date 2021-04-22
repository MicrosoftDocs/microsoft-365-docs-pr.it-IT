---
title: Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Descrive come distribuire gli aggiornamenti per Microsoft Defender for Endpoint in Linux in ambienti aziendali.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, aggiornamenti, distribuire
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
ms.openlocfilehash: 9cb0c7375b538f502cf6165f13c68fd4b2fdcc64
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934754"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="db4e5-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="db4e5-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="db4e5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="db4e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="db4e5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="db4e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db4e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db4e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db4e5-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="db4e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="db4e5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="db4e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="db4e5-110">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="db4e5-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="db4e5-111">Ogni versione di Defender per Endpoint su Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db4e5-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="db4e5-112">È necessario aggiornare il prodotto prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="db4e5-112">You must update the product prior to this date.</span></span> <span data-ttu-id="db4e5-113">Per verificare la data di scadenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="db4e5-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="db4e5-114">Per aggiornare manualmente Defender per Endpoint su Linux, eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="db4e5-114">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="db4e5-115">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="db4e5-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="db4e5-116">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="db4e5-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="db4e5-117">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="db4e5-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
