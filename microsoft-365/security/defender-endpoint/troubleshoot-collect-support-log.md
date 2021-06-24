---
title: Raccogliere i log di supporto in Microsoft Defender per gli endpoint usando la risposta in tempo reale
description: Informazioni su come raccogliere i log usando la risposta in tempo reale per risolvere i problemi di Microsoft Defender for Endpoints
keywords: supporto, log, raccolta, risoluzione dei problemi, risposta in tempo reale, liveanalyzer, analizzatore, live, risposta
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
ms.openlocfilehash: 0e7634177e58b558381fdc230533b55cade9dc13
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108512"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Raccogliere i log di supporto in Microsoft Defender for Endpoint usando la risposta in tempo reale 


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Quando si contatta il supporto, potrebbe essere richiesto di fornire il pacchetto di output dello strumento Microsoft Defender for Endpoint Client Analyzer.

In questo argomento vengono fornite istruzioni su come eseguire lo strumento tramite Live Response.

1. Scaricare lo script appropriato
    * Solo i registri del sensore client di Microsoft Defender per Endpoint: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).
      - Dimensioni approssimative del pacchetto dei risultati: ~100Kb 
    *  Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).
       - Dimensioni approssimative del pacchetto dei risultati: ~10Mb 
 
2.  Avviare una [sessione di Risposta](live-response.md#initiate-a-live-response-session-on-a-device) in tempo reale nel computer che è necessario analizzare.

3.  Selezionare **Upload file da raccolta.**

    ![Immagine del file di caricamento](images/upload-file.png)

4. Selezionare **Scegli file**.

    ![Immagine del pulsante Scegli file1](images/choose-file.png)

5. Selezionare il file scaricato denominato MDELiveAnalyzer.ps1 e quindi fare clic su **Conferma**


   ![Immagine del pulsante Scegli file2](images/analyzer-file.png)


6. Durante la sessione LiveResponse, utilizzare i comandi seguenti per eseguire l'analizzatore e raccogliere il file dei risultati:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![Immagine dei comandi ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)


>[!NOTE]
> - La versione di anteprima più recente di MDEClientAnalyzer può essere scaricata qui: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .
> 
> - Lo script LiveAnalyzer scarica il pacchetto di risoluzione dei problemi nel computer di destinazione da: https://mdatpclientanalyzer.blob.core.windows.net .
> 
>   Se non è possibile consentire al computer di raggiungere l'URL precedente, caricare MDEClientAnalyzerPreview.zip file nella raccolta prima di eseguire lo script LiveAnalyzer:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" 
>   ```
> 
> - Per ulteriori informazioni sulla raccolta di dati in locale in un computer nel caso in cui il computer non comunichi con i servizi cloud di Microsoft Defender for Endpoint o non venga visualizzato nel portale di Microsoft Defender per endpoint come previsto, vedere Verificare la connettività client a Microsoft Defender per gli URL del servizio [endpoint.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)
