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
description: Informazioni su come gli strumenti di Microsoft 365 eDiscovery gestiscono i documenti crittografati allegati ai messaggi di posta elettronica e archiviati in SharePoint Online e OneDrive for business.
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713267"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Decrittografia negli strumenti di Microsoft 365 eDiscovery

La crittografia è una parte importante della strategia di protezione dei file e della protezione delle informazioni. Le organizzazioni di tutti i tipi utilizzano la tecnologia di crittografia per proteggere i contenuti sensibili all'interno dell'organizzazione e assicurarsi che solo le persone giuste abbiano accesso a tale contenuto.

Per eseguire le attività comuni di eDiscovery su contenuto crittografato, i manager di eDiscovery sono stati tenuti a decrittografare il contenuto del messaggio di posta elettronica come è stato esportato dalle ricerche di contenuto, i casi di eDiscovery di base e Il contenuto crittografato con le tecnologie di crittografia Microsoft non era disponibile per la revisione finché non è stato esportato.

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery, gli strumenti di Microsoft 365 eDiscovery ora incorporano la decrittografia dei file crittografati allegati ai messaggi di posta elettronica e inviati in Exchange Online. Inoltre, i documenti crittografati archiviati in SharePoint Online e OneDrive for business vengono decrittografati in Advanced eDiscovery. 

Prima di questa nuova funzionalità, solo il contenuto di un messaggio di posta elettronica protetto da Rights Management (e non i file allegati) è stato decrittografato. I documenti crittografati in SharePoint e OneDrive non possono essere decrittografati durante il flusso di lavoro di eDiscovery. A questo punto, se un file crittografato con una tecnologia di crittografia Microsoft è collegato a un messaggio di posta elettronica o si trova in un account di SharePoint o OneDrive, gli elementi crittografati vengono decrittografati quando i risultati della ricerca vengono preparati per l'anteprima, aggiunti a un set di revisione in Advanced eDiscovery ed esportati. Questo consente ai responsabili di eDiscovery di visualizzare il contenuto di allegati di posta elettronica crittografati e documenti del sito quando vengono visualizzati in anteprima i risultati della ricerca e di verificarli dopo che sono stati aggiunti a un set di revisione in Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Tecnologie di crittografia supportate

Gli strumenti di Microsoft eDiscovery supportano gli elementi crittografati con le tecnologie di crittografia Microsoft. Queste tecnologie includono la crittografia dei messaggi di Office, Azure Rights Management e Microsoft Information Protection (in particolare le etichette di riservatezza). Per ulteriori informazioni sulle tecnologie di crittografia Microsoft, vedere [Encryption](encryption.md). Il contenuto crittografato dalle tecnologie di crittografia di terze parti non è supportato. Ad esempio, la visualizzazione in anteprima o l'esportazione di contenuto crittografato con tecnologie non Microsoft non è supportata.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>attività di eDiscovery che supportano gli elementi crittografati

Nella tabella seguente vengono identificate le attività supportate che possono essere eseguite negli strumenti di Microsoft 365 eDiscovery su file crittografati allegati a massaggi tramite posta elettronica e documenti crittografati in SharePoint e OneDrive. Queste attività supportate possono essere eseguite su file crittografati che soddisfano i criteri di una ricerca. Il valore "N/A" indica che la funzionalità non è disponibile nello strumento eDiscovery corrispondente.

|attività di eDiscovery  |Ricerca contenuto  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Ricerca di contenuto in file crittografati in posta elettronica e siti     |Sì      |Sì      |Sì      |
|Visualizzare in anteprima i file crittografati allegati alla posta elettronica     |Sì      |Sì     |Sì       |
|Visualizzare in anteprima i documenti crittografati in SharePoint e OneDrive|No      |No    |Sì       |
|Esaminare i file crittografati in un set di Revisione    |N/D      |N/D        | Sì        |
|Esportare i file crittografati allegati alla posta elettronica    |Sì       |Sì  |Sì    |
|Esportare documenti crittografati in SharePoint e OneDrive    |No       |No  |Sì    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisiti per la decrittografia in eDiscovery

È necessario essere assegnati al ruolo RMS Decrypt per visualizzare in anteprima, esaminare ed esportare i file crittografati con le tecnologie di crittografia Microsoft. È inoltre necessario essere assegnati a questo ruolo per esaminare e eseguire query sui file crittografati che vengono aggiunti a un set di revisione in Advanced eDiscovery.

Questo ruolo viene assegnato per impostazione predefinita al gruppo di ruoli eDiscovery Manager nella pagina **autorizzazioni** nel centro sicurezza & conformità di Office 365. Per ulteriori informazioni sul ruolo di decrittografia RMS, vedere [assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md#rms-decrypt).
