---
title: Risoluzione dei problemi di AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Risolvere gli errori per Azure AzCopy durante il caricamento di dati non Di Office 365 per la correzione degli errori in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4a4499bb9790ffeaec6a2be36b5eaff030afc010
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546456"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Risoluzione dei problemi di AzCopy in Advanced eDiscovery

When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to. Per caricare i documenti, copiare questo comando ed eseguirlo in un prompt dei comandi nel computer locale.  Lo screenshot seguente mostra un esempio di comando AzCopy:

![Caricare file non Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

In genere, il comando fornito funziona quando viene eseguito. In alcuni casi, tuttavia, il comando visualizzato potrebbe non essere eseguito correttamente. Ecco alcuni motivi possibili.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>La versione supportata di AzCopy non è installata nel computer locale

Al momento, è necessario utilizzare AzCopy v8.1 per caricare dati non Microsoft 365 in Advanced eDiscovery. Il comando AzCopy visualizzato nella  pagina Carica file mostrato nello screenshot precedente restituisce un errore se non si utilizza AzCopy v8.1. Per installare questa versione, vedere [Trasferire dati con AzCopy v8.1 in Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy non è installato nel computer locale o non è installato nel percorso predefinito

Se AzCopy non è installato o è installato in un percorso diverso dal percorso di installazione predefinito , è possibile che venga visualizzato l'errore seguente quando si esegue il `%ProgramFiles(x86)%` comando AzCopy:

> Impossibile trovare il percorso specificato.

Se AzCopy non è installato nel computer locale, è possibile trovare informazioni sull'installazione in Trasferire dati con [AzCopy v8.1 in Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) Assicurarsi di installarlo nel percorso predefinito.

Se AzCopy è installato, ma viene installato in un percorso diverso da quello predefinito, è possibile copiare il comando, incollarlo in un file di testo e quindi modificare il percorso nel percorso in cui è installato AzCopy. Se ad esempio Azcopy si trova in , è possibile modificare la prima parte del `%ProgramFiles%` comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . Dopo aver apportato questa modifica, copiarla dal file di testo ed eseguirla al prompt dei comandi.

> [!TIP]
> Se AzCopy è installato in un percorso diverso da quello predefinito, provare a disinstallarlo e quindi a reinstallarlo nel percorso predefinito. Ciò consente di evitare questo problema in futuro.
