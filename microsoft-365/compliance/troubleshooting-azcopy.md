---
title: Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8b72112feea4af0a33ef3a0cc12005c8deea195
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637516"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery

Quando si caricano dati o documenti non Microsoft 365 per la correzione degli errori in Advanced eDiscovery, l'interfaccia utente fornisce un comando AzCopy di Azure che contiene parametri con il percorso in cui vengono archiviati i file che si desidera caricare e il percorso di archiviazione di Azure in cui verranno caricati i file. Per caricare i documenti, è possibile copiare questo comando e quindi eseguirlo in un prompt dei comandi nel computer locale.  Nello screenshot seguente è riportato un esempio di un comando AzCopy:

![Caricare file non Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

In genere, il comando fornito funziona quando lo si esegue. Tuttavia, è possibile che i casi in cui il comando visualizzato non venga eseguito correttamente. Ecco alcuni possibili motivi.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>La versione supportata di AzCopy non è installata nel computer locale

A questo punto, è necessario utilizzare AzCopy v 8.1 per caricare i dati non Microsoft 365 in Advanced eDiscovery. Il comando AzCopy visualizzato nella pagina **Carica file** visualizzata nella schermata precedente restituisce un errore se non si utilizza AzCopy v 8.1. Per installare questa versione, vedere [trasferire dati con AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy non è installato nel computer locale o non è installato nel percorso predefinito

Se AzCopy non è installato oppure è installato in un percorso diverso da quello predefinito (ovvero `%ProgramFiles(x86)%`), quando si esegue il comando AzCopy è possibile che venga visualizzato il messaggio di errore seguente:

    The system cannot find the path specified.

Se AzCopy non è installato nel computer locale, è possibile installarlo da [qui](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Assicurarsi di installarlo nel percorso predefinito.

Se AzCopy è installato, ma è installato in una posizione diversa da quella predefinita, è possibile copiare il comando, incollarlo in un file di testo e quindi cambiare il percorso in cui è installato AzCopy. Ad esempio, se si trova Azcopy `%ProgramFiles%`, è possibile modificare la prima parte del comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` Dopo aver apportato questa modifica, copiarla dal file di testo e quindi eseguirla come prompt dei comandi.

> [!TIP]
> Se AzCopy è installato in un percorso diverso dal percorso di installazione predefinito, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito. Ciò consentirà di prevenire questo problema in futuro.
