---
title: Implementare aggiornamenti per Microsoft Defender per endpoint su Linux
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274725"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="d8ca6-104">Implementare aggiornamenti per Microsoft Defender per endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="d8ca6-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d8ca6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d8ca6-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8ca6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d8ca6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8ca6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8ca6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8ca6-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d8ca6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d8ca6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d8ca6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d8ca6-110">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d8ca6-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="d8ca6-111">Ogni versione di Defender per Endpoint su Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d8ca6-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="d8ca6-112">È necessario aggiornare il prodotto prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="d8ca6-112">You must update the product prior to this date.</span></span> <span data-ttu-id="d8ca6-113">Per verificare la data di scadenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d8ca6-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="d8ca6-114">Le funzionalità di Microsoft Defender for Endpoint disponibili in genere sono equivalenti indipendentemente dal canale di aggiornamento utilizzato per una distribuzione (Beta (Insider), Anteprima (esterna), Corrente (produzione)).</span><span class="sxs-lookup"><span data-stu-id="d8ca6-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="d8ca6-115">Per aggiornare manualmente Defender per Endpoint su Linux, eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8ca6-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="d8ca6-116">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="d8ca6-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="d8ca6-117">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="d8ca6-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="d8ca6-118">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="d8ca6-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
