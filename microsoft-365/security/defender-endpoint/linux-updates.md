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
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.

> [!WARNING]
> Ogni versione di Defender per Endpoint su Linux ha una data di scadenza, dopo la quale non continuerà più a proteggere il dispositivo. È necessario aggiornare il prodotto prima di questa data. Per verificare la data di scadenza, eseguire il comando seguente:
> ```bash
> mdatp health --field product_expiration
> ```

Per aggiornare manualmente Defender per Endpoint su Linux, eseguire uno dei comandi seguenti:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL e varianti (CentOS e Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES e varianti

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Sistemi Ubuntu e Debian

```bash
sudo apt-get install --only-upgrade mdatp
```
