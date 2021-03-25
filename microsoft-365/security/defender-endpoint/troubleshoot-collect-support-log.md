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
ms.openlocfilehash: 50e7bc6d84714411c89f014bb0018a3102617cb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066058"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="23ff2-104">Raccogliere i log di supporto in Microsoft Defender for Endpoint usando la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="23ff2-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="23ff2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="23ff2-105">**Applies to:**</span></span>
- [<span data-ttu-id="23ff2-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="23ff2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="23ff2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23ff2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23ff2-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="23ff2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23ff2-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="23ff2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="23ff2-110">Quando si contatta il supporto, potrebbe essere richiesto di fornire il pacchetto di output dello strumento Microsoft Defender for Endpoint Client Analyzer.</span><span class="sxs-lookup"><span data-stu-id="23ff2-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="23ff2-111">In questo argomento vengono fornite istruzioni su come eseguire lo strumento tramite Live Response.</span><span class="sxs-lookup"><span data-stu-id="23ff2-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="23ff2-112">Scaricare lo script appropriato</span><span class="sxs-lookup"><span data-stu-id="23ff2-112">Download the appropriate script</span></span>
    * <span data-ttu-id="23ff2-113">Solo i registri del sensore client di Microsoft Defender per Endpoint: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span><span class="sxs-lookup"><span data-stu-id="23ff2-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="23ff2-114">Dimensioni approssimative del pacchetto dei risultati: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="23ff2-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="23ff2-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span><span class="sxs-lookup"><span data-stu-id="23ff2-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="23ff2-116">Dimensioni approssimative del pacchetto dei risultati: ~10Mb</span><span class="sxs-lookup"><span data-stu-id="23ff2-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="23ff2-117">Avviare una [sessione di Risposta](live-response.md#initiate-a-live-response-session-on-a-device) in tempo reale nel computer che è necessario analizzare.</span><span class="sxs-lookup"><span data-stu-id="23ff2-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="23ff2-118">Selezionare **Carica file nella raccolta**.</span><span class="sxs-lookup"><span data-stu-id="23ff2-118">Select **Upload file to library**.</span></span>

    ![Immagine del file di caricamento](images/upload-file.png)

4. <span data-ttu-id="23ff2-120">Selezionare **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="23ff2-120">Select **Choose file**.</span></span>

    ![Immagine del pulsante Scegli file1](images/choose-file.png)

5. <span data-ttu-id="23ff2-122">Selezionare il file scaricato denominato MDELiveAnalyzer.ps1 e quindi fare clic su **Conferma**</span><span class="sxs-lookup"><span data-stu-id="23ff2-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![Immagine del pulsante Scegli file2](images/analyzer-file.png)


6. <span data-ttu-id="23ff2-124">Durante la sessione LiveResponse, utilizzare i comandi seguenti per eseguire l'analizzatore e raccogliere il file dei risultati:</span><span class="sxs-lookup"><span data-stu-id="23ff2-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![Immagine dei comandi](images/analyzer-commands.png)


>[!NOTE]
> - <span data-ttu-id="23ff2-126">La versione di anteprima più recente di MDEClientAnalyzer può essere scaricata qui: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .</span><span class="sxs-lookup"><span data-stu-id="23ff2-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="23ff2-127">Lo script LiveAnalyzer scarica il pacchetto di risoluzione dei problemi nel computer di destinazione da: https://mdatpclientanalyzer.blob.core.windows.net .</span><span class="sxs-lookup"><span data-stu-id="23ff2-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="23ff2-128">Se non è possibile consentire al computer di raggiungere l'URL precedente, caricare MDEClientAnalyzerPreview.zip file nella raccolta prima di eseguire lo script LiveAnalyzer:</span><span class="sxs-lookup"><span data-stu-id="23ff2-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="23ff2-129">Per ulteriori informazioni sulla raccolta di dati in locale in un computer nel caso in cui il computer non comunichi con i servizi cloud di Microsoft Defender for Endpoint o non venga visualizzato nel portale di Microsoft Defender per endpoint come previsto, vedere Verificare la connettività client a Microsoft Defender per gli URL del servizio [endpoint.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</span><span class="sxs-lookup"><span data-stu-id="23ff2-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls).</span></span>
