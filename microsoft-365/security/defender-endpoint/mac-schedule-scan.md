---
title: Come pianificare le analisi con Microsoft Defender for Endpoint in macOS
description: Scopri come pianificare un tempo di analisi automatica per Microsoft Defender for Endpoint in macOS per proteggere meglio le risorse dell'organizzazione.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, analisi, antivirus
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
ms.openlocfilehash: 2c1dc16dc3fbb61a77e1d7348d47fdfd778c56e2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934514"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Pianificare le analisi con Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Anche se puoi avviare un'analisi delle minacce in qualsiasi momento con Microsoft Defender for Endpoint, la tua azienda potrebbe trarre vantaggio da analisi pianificate o a tempo. Ad esempio, è possibile pianificare l'esecuzione di un'analisi all'inizio di ogni giorno lavorativo o settimana. 

## <a name="schedule-a-scan-with-launchd"></a>Pianificare un'analisi con *avviata*

Puoi creare una pianificazione di analisi usando *il* daemon avviato in un dispositivo macOS.

1. Nel codice seguente viene illustrato lo schema che è necessario utilizzare per pianificare un'analisi. Aprire un editor di testo e utilizzare questo esempio come guida per il proprio file di analisi pianificato.

    Per altre informazioni sul formato di file *plist* usato qui, vedi [Informazioni](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) sui file dell'elenco delle proprietà delle informazioni nel sito Web ufficiale degli sviluppatori Apple.

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

2. Salvare il file *come com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Per eseguire un'analisi completa anziché un'analisi rapida, modificare la riga 12, , per utilizzare l'opzione anziché (ad esempio ) e salvare il file come `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* anziché *com.microsoft.wdav.sched **quick** scan.plist*.

3. Apri **Terminale**.
4. Immettere i comandi seguenti per caricare il file:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. L'analisi pianificata verrà eseguita alla data, all'ora e alla frequenza definite nell'elenco p. Nell'esempio, l'analisi viene eseguita ogni venerdì alle 2:00. 

    Il `Weekday` valore di utilizza un numero intero per indicare il quinto giorno della settimana o il `StartCalendarInterval` venerdì.

 > [!IMPORTANT]
 > Gli agenti *eseguiti con launchd* non verranno eseguiti all'ora pianificata mentre il dispositivo è in stato di sospensione. Verranno invece eseguiti quando il dispositivo riprende dalla modalità sospensione.
 >
 > Se il dispositivo è disattivato, l'analisi verrà eseguita alla successiva analisi pianificata.

## <a name="schedule-a-scan-with-intune"></a>Pianificare un'analisi con Intune

È inoltre possibile pianificare le analisi con Microsoft Intune. Lo [script runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell disponibile in Scripts for Microsoft Defender for [Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) verrà mantenuto quando il dispositivo riprende dalla modalità sospensione. 

Per [istruzioni più dettagliate su](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) come usare questo script nell'organizzazione, vedi Usare script della shell nei dispositivi macOS in Intune.
