---
title: Decrittografia in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come gli strumenti di Microsoft 365 eDiscovery gestiscono i documenti crittografati allegati ai messaggi di posta elettronica.
ms.openlocfilehash: 91d5689bfb64d272c896c0e92422ce1f45fd5f72
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984900"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Decrittografia negli strumenti di Microsoft 365 eDiscovery

La crittografia è una parte importante della strategia di protezione dei file e della protezione delle informazioni. Le organizzazioni di tutti i tipi utilizzano la tecnologia di crittografia per proteggere i contenuti sensibili all'interno dell'organizzazione e assicurarsi che solo le persone giuste abbiano accesso a tale contenuto.

Per eseguire le attività comuni di eDiscovery su contenuto crittografato, i manager di eDiscovery sono stati tenuti a decrittografare il contenuto del messaggio di posta elettronica come è stato esportato dalle ricerche di contenuto, i casi di eDiscovery di base e Il contenuto crittografato con le tecnologie di crittografia Microsoft non è stato disponibile per la revisione finché non è stato esportato.

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery, gli strumenti di Microsoft 365 eDiscovery ora incorporano la decrittografia dei file crittografati allegati ai messaggi di posta elettronica e inviati in Exchange Online. Prima di questa nuova funzionalità, solo il contenuto di un messaggio di posta elettronica protetto da Rights Management (e non i file allegati) è stato decrittografato. Se un file crittografato con una tecnologia di crittografia Microsoft è associato a un messaggio di posta elettronica che corrisponde ai criteri di ricerca, il file crittografato verrà decrittografato quando i risultati della ricerca verranno preparati per la revisione. Questo consente ai responsabili di eDiscovery di visualizzare il contenuto degli allegati di posta elettronica crittografati quando si visualizzano in anteprima i risultati della ricerca e di verificarli dopo averli aggiunti a un set di revisione in Advanced eDiscovery.

> [!NOTE]
> A partire da Microsoft 365 eDiscovery Tools supporterà documenti crittografati archiviati in SharePoint Online e OneDrive for business. Verranno inclusi i documenti crittografati a causa delle etichette di riservatezza applicate.

## <a name="supported-encryption-technologies"></a>Tecnologie di crittografia supportate

Gli strumenti di Microsoft eDiscovery supportano gli elementi crittografati con le tecnologie di crittografia Microsoft. Queste tecnologie includono la crittografia dei messaggi di Office e Azure Rights Management. Per ulteriori informazioni sulle tecnologie di crittografia Microsoft, vedere [Encryption](encryption.md). Il contenuto crittografato dalle tecnologie di crittografia di terze parti non è supportato. Questo non include il supporto per l'anteprima o l'esportazione di contenuto crittografato con le tecnologie non Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>attività di eDiscovery che supportano gli elementi crittografati

Nella tabella seguente vengono identificate le attività eseguite negli strumenti di Microsoft 365 eDiscovery che supportano la decrittografia dei file crittografati allegati ai massaggi tramite posta elettronica. Le attività di supporto possono essere eseguite su un file crittografato collegato a un messaggio di posta elettronica che corrisponde ai criteri di una ricerca. Il valore "N/A" indica che la funzione non è disponibile nello strumento eDiscovery corrispondente.

|attività di eDiscovery  |Ricerca contenuto  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Ricerca di contenuto nei file crittografati     |Sì      |Sì      |Sì      |
|Visualizzare in anteprima i file crittografati     |Sì      |Sì     |Sì       |
|Esaminare i file crittografati in un set di Revisione    |N/D      |N/D        | Sì        |
|Esportare file crittografati    |Sì       |Sì  |Sì    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisiti per la decrittografia in eDiscovery

È necessario essere assegnati al ruolo RMS Decrypt per visualizzare in anteprima, esaminare ed esportare i file allegati crittografati con Microsoft Encryption Technologies. È inoltre necessario essere assegnati a questo ruolo per esaminare e interrogare gli allegati di posta elettronica crittografati che vengono aggiunti a un set di revisione in Advanced eDiscovery.

Questo ruolo viene assegnato per impostazione predefinita al gruppo di ruoli eDiscovery Manager nel centro sicurezza & conformità di Office 365. Per ulteriori informazioni sul ruolo di decrittografia RMS, vedere [assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md#rms-decrypt).
