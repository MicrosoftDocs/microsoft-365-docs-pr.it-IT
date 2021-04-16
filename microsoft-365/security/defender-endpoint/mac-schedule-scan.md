---
title: Come pianificare le analisi con MDATP per macOS
description: Scopri come pianificare un tempo di analisi automatica per Microsoft Defender for Endpoint in macOS per proteggere meglio le risorse dell'organizzazione.
keywords: microsoft, defender, atp, mac, scansioni, antivirus
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
ms.openlocfilehash: 71576c777f58aa193f2a73db7edea832d29a97c6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860932"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="a0c74-104">Pianificare le analisi con Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="a0c74-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0c74-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a0c74-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0c74-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a0c74-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a0c74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0c74-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a0c74-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a0c74-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a0c74-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a0c74-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a0c74-110">Anche se puoi avviare un'analisi delle minacce in qualsiasi momento con Microsoft Defender for Endpoint, la tua azienda potrebbe trarre vantaggio da analisi pianificate o a tempo.</span><span class="sxs-lookup"><span data-stu-id="a0c74-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="a0c74-111">Ad esempio, è possibile pianificare l'esecuzione di un'analisi all'inizio di ogni giorno lavorativo o settimana.</span><span class="sxs-lookup"><span data-stu-id="a0c74-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="a0c74-112">Pianificare un'analisi con *avviata*</span><span class="sxs-lookup"><span data-stu-id="a0c74-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="a0c74-113">Puoi creare una pianificazione di analisi usando *il* daemon avviato in un dispositivo macOS.</span><span class="sxs-lookup"><span data-stu-id="a0c74-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="a0c74-114">Nel codice seguente viene illustrato lo schema che è necessario utilizzare per pianificare un'analisi.</span><span class="sxs-lookup"><span data-stu-id="a0c74-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="a0c74-115">Aprire un editor di testo e utilizzare questo esempio come guida per il proprio file di analisi pianificato.</span><span class="sxs-lookup"><span data-stu-id="a0c74-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="a0c74-116">Per altre informazioni sul formato di file *plist* usato qui, vedi [Informazioni](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) sui file dell'elenco delle proprietà delle informazioni nel sito Web ufficiale degli sviluppatori Apple.</span><span class="sxs-lookup"><span data-stu-id="a0c74-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="a0c74-117">Salvare il file *come com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="a0c74-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="a0c74-118">Per eseguire un'analisi completa anziché un'analisi rapida, modificare la riga 12, , per utilizzare l'opzione anziché (ad esempio ) e salvare il file come `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anziché *com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="a0c74-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="a0c74-119">Apri **Terminale**.</span><span class="sxs-lookup"><span data-stu-id="a0c74-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="a0c74-120">Immettere i comandi seguenti per caricare il file:</span><span class="sxs-lookup"><span data-stu-id="a0c74-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="a0c74-121">L'analisi pianificata verrà eseguita alla data, all'ora e alla frequenza definite nell'elenco p.</span><span class="sxs-lookup"><span data-stu-id="a0c74-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="a0c74-122">Nell'esempio, l'analisi viene eseguita ogni venerdì alle 2:00.</span><span class="sxs-lookup"><span data-stu-id="a0c74-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="a0c74-123">Il `Weekday` valore di utilizza un numero intero per indicare il quinto giorno della settimana o il `StartCalendarInterval` venerdì.</span><span class="sxs-lookup"><span data-stu-id="a0c74-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="a0c74-124">Gli agenti *eseguiti con launchd* non verranno eseguiti all'ora pianificata mentre il dispositivo è in stato di sospensione.</span><span class="sxs-lookup"><span data-stu-id="a0c74-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="a0c74-125">Verranno invece eseguiti quando il dispositivo riprende dalla modalità sospensione.</span><span class="sxs-lookup"><span data-stu-id="a0c74-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="a0c74-126">Se il dispositivo è disattivato, l'analisi verrà eseguita alla successiva analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="a0c74-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="a0c74-127">Pianificare un'analisi con Intune</span><span class="sxs-lookup"><span data-stu-id="a0c74-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="a0c74-128">È inoltre possibile pianificare le analisi con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c74-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="a0c74-129">Lo [script runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell disponibile in Scripts for Microsoft Defender for [Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verrà mantenuto quando il dispositivo riprende dalla modalità sospensione.</span><span class="sxs-lookup"><span data-stu-id="a0c74-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="a0c74-130">Per [istruzioni più dettagliate su](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) come usare questo script nell'organizzazione, vedi Usare script della shell nei dispositivi macOS in Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c74-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
