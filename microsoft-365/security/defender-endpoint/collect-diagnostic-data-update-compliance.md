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
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Raccogliere i dati di diagnostica di conformità degli aggiornamenti per Antivirus Microsoft Defender valutazione


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In questo articolo viene descritto come raccogliere dati di diagnostica che possono essere utilizzati dai team di supporto e progettazione Microsoft per risolvere i problemi che possono verificarsi quando si utilizza la sezione valutazione di Antivirus Microsoft Defender nel componente aggiuntivo Conformità aggiornamenti.

Prima di tentare questo processo, verificare di aver letto Risoluzione dei problemi Antivirus Microsoft Defender [report,](troubleshoot-reporting.md)aver soddisfatto tutti i prerequisiti e aver eseguito qualsiasi altra procedura di risoluzione dei problemi suggerita.

In almeno due dispositivi che non segnalano o non vengono visualizzati in Conformità aggiornamento, ottenere il file di diagnostica .cab seguendo la procedura seguente:

1. Aprire una versione a livello di amministratore del prompt dei comandi come segue:
        
    a. Apri il menu **Start.**

    b. Digitare **cmd**. Fai clic con il pulsante **destro del mouse** su Prompt dei comandi e quindi scegli Esegui come **amministratore.**

    c. Specificare le credenziali di amministratore o approvare il prompt.
        
2. Passare alla directory Windows Defender. Per impostazione predefinita, è `C:\Program Files\Windows Defender` .

3. Digitare il comando seguente e quindi premere **INVIO**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Verrà .cab un file contenente diversi log di diagnostica. Il percorso del file verrà specificato nell'output nel prompt dei comandi. Per impostazione predefinita, il percorso è `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Copiare .cab file in un percorso accessibile dal supporto Tecnico Microsoft. Un esempio potrebbe essere una cartella OneDrive protetta da password che puoi condividere con noi.

6. Inviare un messaggio di posta elettronica utilizzando <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">il modello</a>di posta elettronica di supporto per la conformità degli aggiornamenti e compilare il modello con le informazioni seguenti:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Vedere anche

- [Risolvere i Windows Defender Antivirus Microsoft Defender report](troubleshoot-reporting.md)