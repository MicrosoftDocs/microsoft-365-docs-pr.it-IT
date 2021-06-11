---
title: Raccogliere dati di diagnostica per conformità degli aggiornamenti e Windows Defender Antivirus Microsoft Defender
description: Usare uno strumento per raccogliere dati per risolvere i problemi di conformità degli aggiornamenti quando si usa il componente aggiuntivo Antivirus Microsoft Defender valutazione
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903733"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a><span data-ttu-id="31aaa-104">Raccogliere i dati di diagnostica di conformità degli aggiornamenti per Antivirus Microsoft Defender valutazione</span><span class="sxs-lookup"><span data-stu-id="31aaa-104">Collect update compliance diagnostic data for Microsoft Defender Antivirus assessment</span></span>


<span data-ttu-id="31aaa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="31aaa-105">**Applies to:**</span></span>

- [<span data-ttu-id="31aaa-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="31aaa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="31aaa-107">In questo articolo viene descritto come raccogliere dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi che possono verificarsi quando si utilizza la sezione valutazione di Antivirus Microsoft Defender nel componente aggiuntivo Conformità aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="31aaa-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender Antivirus Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="31aaa-108">Prima di tentare questo processo, verificare di aver letto Risoluzione dei problemi Antivirus Microsoft Defender [report,](troubleshoot-reporting.md)aver soddisfatto tutti i prerequisiti e aver eseguito qualsiasi altra procedura di risoluzione dei problemi suggerita.</span><span class="sxs-lookup"><span data-stu-id="31aaa-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="31aaa-109">In almeno due dispositivi che non segnalano o non vengono visualizzati in Conformità aggiornamento, ottenere il file di diagnostica .cab seguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="31aaa-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="31aaa-110">Aprire una versione a livello di amministratore del prompt dei comandi come segue:</span><span class="sxs-lookup"><span data-stu-id="31aaa-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="31aaa-111">a.</span><span class="sxs-lookup"><span data-stu-id="31aaa-111">a.</span></span> <span data-ttu-id="31aaa-112">Apri il menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="31aaa-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="31aaa-113">b.</span><span class="sxs-lookup"><span data-stu-id="31aaa-113">b.</span></span> <span data-ttu-id="31aaa-114">Digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="31aaa-114">Type **cmd**.</span></span> <span data-ttu-id="31aaa-115">Fai clic con il pulsante **destro del mouse** su Prompt dei comandi e quindi scegli Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="31aaa-115">Right-click on **Command Prompt** and then select **Run as administrator**.</span></span>

    <span data-ttu-id="31aaa-116">c.</span><span class="sxs-lookup"><span data-stu-id="31aaa-116">c.</span></span> <span data-ttu-id="31aaa-117">Specificare le credenziali di amministratore o approvare il prompt.</span><span class="sxs-lookup"><span data-stu-id="31aaa-117">Specify administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="31aaa-118">Passare alla directory Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="31aaa-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="31aaa-119">Per impostazione predefinita, è `C:\Program Files\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="31aaa-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="31aaa-120">Digitare il comando seguente e quindi premere **INVIO**</span><span class="sxs-lookup"><span data-stu-id="31aaa-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="31aaa-121">Verrà .cab un file contenente diversi log di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="31aaa-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="31aaa-122">Il percorso del file verrà specificato nell'output nel prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="31aaa-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="31aaa-123">Per impostazione predefinita, il percorso è `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="31aaa-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="31aaa-124">Copiare .cab file in un percorso accessibile dal supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31aaa-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="31aaa-125">Un esempio potrebbe essere una cartella OneDrive protetta da password che puoi condividere con noi.</span><span class="sxs-lookup"><span data-stu-id="31aaa-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="31aaa-126">Inviare un messaggio di posta elettronica utilizzando <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">il modello</a>di posta elettronica di supporto per la conformità degli aggiornamenti e compilare il modello con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31aaa-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">update compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="31aaa-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31aaa-127">See also</span></span>

- [<span data-ttu-id="31aaa-128">Risolvere i Windows Defender Antivirus Microsoft Defender report</span><span class="sxs-lookup"><span data-stu-id="31aaa-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)