---
title: Distribuire gli aggiornamenti per Microsoft Defender per Endpoint per Linux
ms.reviewer: ''
description: Descrive come distribuire gli aggiornamenti per Microsoft Defender for Endpoint per Linux in ambienti aziendali.
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
ms.openlocfilehash: 77b428e359596e73e08dc04f15190ecf68db29be
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861148"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ab3a8-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="ab3a8-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab3a8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ab3a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab3a8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ab3a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab3a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab3a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab3a8-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ab3a8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab3a8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ab3a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ab3a8-110">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ab3a8-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="ab3a8-111">Ogni versione di Defender per Endpoint per Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab3a8-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="ab3a8-112">È necessario aggiornare il prodotto prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="ab3a8-112">You must update the product prior to this date.</span></span> <span data-ttu-id="ab3a8-113">Per verificare la data di scadenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ab3a8-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="ab3a8-114">Per aggiornare manualmente Defender per Endpoint per Linux, eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab3a8-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="ab3a8-115">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="ab3a8-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="ab3a8-116">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="ab3a8-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="ab3a8-117">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="ab3a8-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
