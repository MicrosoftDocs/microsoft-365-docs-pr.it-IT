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
ms.openlocfilehash: adc19192764e8c57a20f14cc908be23e8d9bdbc8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062453"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="428aa-104">Distribuire gli aggiornamenti per Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="428aa-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="428aa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="428aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="428aa-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="428aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="428aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="428aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="428aa-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="428aa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="428aa-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="428aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="428aa-110">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="428aa-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="428aa-111">Ogni versione di Defender per Endpoint per Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="428aa-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="428aa-112">È necessario aggiornare il prodotto prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="428aa-112">You must update the product prior to this date.</span></span> <span data-ttu-id="428aa-113">Per verificare la data di scadenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="428aa-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="428aa-114">Per aggiornare manualmente Defender per Endpoint per Linux, eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="428aa-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="428aa-115">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="428aa-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="428aa-116">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="428aa-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="428aa-117">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="428aa-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
