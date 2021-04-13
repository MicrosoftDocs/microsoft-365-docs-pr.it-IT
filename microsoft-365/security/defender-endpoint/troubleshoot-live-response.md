---
title: Risolvere i problemi di risposta live di Microsoft Defender for Endpoint
description: Risolvere i problemi che potrebbero verificarsi quando si usa la risposta in tempo reale in Microsoft Defender per Endpoint
keywords: risolvere i problemi di risposta in tempo reale, live, risposta, bloccato, file
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 2601001687fc22da98ca3cd81010237d12705ea4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687412"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Risolvere i problemi di risposta live di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

In questa pagina vengono descritti i passaggi dettagliati per la risoluzione dei problemi di risposta in tempo reale.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Non è possibile accedere al file durante le sessioni di risposta in tempo reale
Se durante il tentativo di eseguire un'azione durante una sessione di risposta attiva viene visualizzato un messaggio di errore che indica che non è possibile accedere al file, è necessario eseguire la procedura seguente per risolvere il problema.

1. Copiare il frammento di codice di script seguente e salvarlo come file PS1:

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. Aggiungi lo script alla raccolta di risposte in tempo reale.
3. Eseguire lo script con un solo parametro: il percorso del file da copiare.
4. Passare alla cartella TEMP.
5. Eseguire l'azione che si desidera eseguire sul file copiato.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Sessioni di risposta in tempo reale lente o ritardi durante le connessioni iniziali
La risposta in tempo reale sfrutta defender per la registrazione del sensore endpoint con il servizio WNS in Windows. Se si verificano problemi di connettività con la risposta in tempo reale, verificare i dettagli seguenti:
1. `notify.windows.com` non è bloccato nell'ambiente. Per ulteriori informazioni, vedere Configure [device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).
2. WpnService (servizio di sistema notifiche Push Windows) non è disabilitato.

Fare riferimento agli articoli seguenti per comprendere appieno il comportamento e i requisiti del servizio WpnService:
- [Panoramica di Windows Push Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Configurazioni di firewall e proxy aziendali per supportare il traffico WNS](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft Push Notifications Service (MPNS) Public IP ranges](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

