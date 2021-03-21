---
title: Risolvere i problemi di AzCopy in Advanced eDiscovery
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
description: Risolvere gli errori per Azure AzCopy durante il caricamento di dati non di Office 365 per la correzione degli errori in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919292"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Risolvere i problemi di AzCopy in Advanced eDiscovery

Quando si caricano dati o documenti non Di Microsoft 365 per la correzione degli errori in Advanced eDiscovery, l'interfaccia utente fornisce un comando Azure AzCopy che contiene i parametri con il percorso in cui vengono archiviati i file che si desidera caricare e il percorso di archiviazione di Azure in cui verranno caricati i file. Per caricare i documenti, copiare questo comando ed eseguirlo in un prompt dei comandi nel computer locale.  Lo screenshot seguente mostra un esempio di comando AzCopy:

![Caricare file non Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

In genere, il comando fornito funziona quando viene eseguito. Tuttavia, in alcuni casi il comando visualizzato non verrà eseguito correttamente. Ecco alcuni possibili motivi.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>La versione supportata di AzCopy non è installata nel computer locale

Al momento, è necessario utilizzare AzCopy v8.1 per caricare dati non Microsoft 365 in Advanced eDiscovery. Il comando AzCopy visualizzato nella  pagina Carica file visualizzata nello screenshot precedente restituisce un errore se non si utilizza AzCopy v8.1. Per installare questa versione, vedi [Trasferire dati con AzCopy v8.1 in Windows.](/previous-versions/azure/storage/storage-use-azcopy)

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy non è installato nel computer locale o non è installato nel percorso predefinito

Se AzCopy non è installato o è installato in un percorso diverso da quello di installazione predefinito (ovvero ), è possibile che venga visualizzato il seguente errore quando si esegue il `%ProgramFiles(x86)%` comando AzCopy:

> Impossibile trovare il percorso specificato.

Se AzCopy non è installato nel computer locale, è possibile trovare informazioni sull'installazione in Trasferire dati [con AzCopy v8.1 in Windows](/previous-versions/azure/storage/storage-use-azcopy). Assicurarsi di installarlo nel percorso predefinito.

Se AzCopy è installato, ma è installato in un percorso diverso da quello predefinito, è possibile copiare il comando, incollarlo in un file di testo e quindi modificare il percorso nel percorso in cui è installato AzCopy. Ad esempio, se Azcopy si trova in , è possibile modificare la prima parte del `%ProgramFiles%` comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . Dopo aver apportato questa modifica, copiarla dal file di testo ed eseguirla al prompt dei comandi.

> [!TIP]
> Se AzCopy è installato in un percorso diverso, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito. Ciò consente di evitare questo problema in futuro.