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
ms.openlocfilehash: 99a52188dd5f6eca2f8368aa3c114d0bfb950b10
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844155"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="810c8-104">Risolvere i problemi di risposta live di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="810c8-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="810c8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="810c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="810c8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="810c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="810c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="810c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="810c8-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="810c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="810c8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="810c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="810c8-110">In questa pagina vengono descritti i passaggi dettagliati per la risoluzione dei problemi di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="810c8-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="810c8-111">Non è possibile accedere al file durante le sessioni di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="810c8-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="810c8-112">Se durante il tentativo di eseguire un'azione durante una sessione di risposta attiva viene visualizzato un messaggio di errore che indica che non è possibile accedere al file, è necessario eseguire la procedura seguente per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="810c8-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="810c8-113">Copiare il frammento di codice di script seguente e salvarlo come file PS1:</span><span class="sxs-lookup"><span data-stu-id="810c8-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

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


2. <span data-ttu-id="810c8-114">Aggiungi lo script alla raccolta di risposte in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="810c8-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="810c8-115">Eseguire lo script con un solo parametro: il percorso del file da copiare.</span><span class="sxs-lookup"><span data-stu-id="810c8-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="810c8-116">Passare alla cartella TEMP.</span><span class="sxs-lookup"><span data-stu-id="810c8-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="810c8-117">Eseguire l'azione che si desidera eseguire sul file copiato.</span><span class="sxs-lookup"><span data-stu-id="810c8-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="810c8-118">Sessioni di risposta in tempo reale lente o ritardi durante le connessioni iniziali</span><span class="sxs-lookup"><span data-stu-id="810c8-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="810c8-119">La risposta in tempo reale sfrutta Defender per la registrazione del sensore endpoint con il servizio WNS in Windows.</span><span class="sxs-lookup"><span data-stu-id="810c8-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="810c8-120">Se si verificano problemi di connettività con la risposta in tempo reale, verificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="810c8-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="810c8-121">`notify.windows.com` non è bloccato nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="810c8-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="810c8-122">Per ulteriori informazioni, vedere Configure [device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="810c8-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="810c8-123">WpnService (Windows servizio di sistema notifiche Push) non è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="810c8-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="810c8-124">Fare riferimento agli articoli seguenti per comprendere appieno il comportamento e i requisiti del servizio WpnService:</span><span class="sxs-lookup"><span data-stu-id="810c8-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="810c8-125">Windows Panoramica Notification Services push (WNS)</span><span class="sxs-lookup"><span data-stu-id="810c8-125">Windows Push Notification Services (WNS) overview</span></span>](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="810c8-126">Enterprise Configurazioni firewall e proxy per supportare il traffico WNS</span><span class="sxs-lookup"><span data-stu-id="810c8-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="810c8-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span><span class="sxs-lookup"><span data-stu-id="810c8-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

