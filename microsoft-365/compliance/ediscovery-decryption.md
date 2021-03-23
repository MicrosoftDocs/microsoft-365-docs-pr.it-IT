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
description: Informazioni su come gli strumenti di eDiscovery di Microsoft 365 gestiscono i documenti crittografati allegati ai messaggi di posta elettronica e archiviati in SharePoint Online e OneDrive for Business.
ms.openlocfilehash: ad7ee9816e83caa49e437e1723655162a44c93fa
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034069"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Decrittografia negli strumenti di eDiscovery di Microsoft 365

La crittografia è una parte importante della strategia di protezione dei file e di protezione delle informazioni. Le organizzazioni di tutti i tipi utilizzano la tecnologia di crittografia per proteggere i contenuti sensibili all'interno dell'organizzazione e garantire che solo le persone giuste hanno accesso a tale contenuto.

Per eseguire attività comuni di eDiscovery sul contenuto crittografato, i responsabili di eDiscovery sono stati tenuti a decrittografare il contenuto dei messaggi di posta elettronica durante l'esportazione da ricerche di contenuto, casi di eDiscovery di base e casi di Advanced eDiscovery. Il contenuto crittografato con le tecnologie di crittografia Microsoft non era disponibile per la revisione fino a quando non è stato esportato.

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery, gli strumenti di eDiscovery di Microsoft 365 ora incorporano la decrittografia dei file crittografati allegati ai messaggi di posta elettronica e inviati in Exchange Online. Inoltre, i documenti crittografati archiviati in SharePoint Online e OneDrive for Business vengono decrittografati in Advanced eDiscovery.

Prima di questa nuova funzionalità, solo il contenuto di un messaggio di posta elettronica protetto da Rights Management (e non dai file allegati) era decrittografato. Non è stato possibile decrittografare i documenti crittografati in SharePoint e OneDrive durante il flusso di lavoro di eDiscovery. Ora, se un file crittografato con una tecnologia di crittografia Microsoft è allegato a un messaggio di posta elettronica o si trova in un account di SharePoint o OneDrive, tali elementi crittografati vengono decrittografati quando i risultati della ricerca vengono preparati per l'anteprima, aggiunti a un set di recensioni in Advanced eDiscovery ed esportati. In questo modo i responsabili di eDiscovery possono visualizzare il contenuto degli allegati di posta elettronica crittografati e dei documenti del sito quando visualizzano in anteprima i risultati della ricerca e rivederli dopo averli aggiunti a un set di recensioni in Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Tecnologie di crittografia supportate

Gli strumenti di Microsoft eDiscovery supportano gli elementi crittografati con le tecnologie di crittografia Microsoft. Queste tecnologie sono Azure Rights Management e Microsoft Information Protection (in particolare le etichette di riservatezza). Per ulteriori informazioni sulle tecnologie di crittografia Microsoft, vedere [Crittografia](encryption.md). Il contenuto crittografato da tecnologie di crittografia di terze parti non è supportato. Ad esempio, l'anteprima o l'esportazione di contenuto crittografato con tecnologie non Microsoft non è supportata.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Attività di eDiscovery che supportano elementi crittografati

Nella tabella seguente vengono identificate le attività supportate che possono essere eseguite negli strumenti di eDiscovery di Microsoft 365 sui file crittografati allegati ai messaggi di posta elettronica e ai documenti crittografati in SharePoint e OneDrive. Queste attività supportate possono essere eseguite su file crittografati che corrispondono ai criteri di una ricerca. Il valore di `N/A` indica che la funzionalità non è disponibile nello strumento eDiscovery corrispondente.

|Attività eDiscovery  |Ricerca contenuto  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Cercare contenuto in file crittografati in posta elettronica e siti     |Sì      |Sì      |Sì      |
|Anteprima dei file crittografati allegati alla posta elettronica     |Sì      |Sì     |Sì       |
|Anteprima dei documenti crittografati in SharePoint e OneDrive|No      |No    |Sì       |
|Esaminare i file crittografati in un set di revisione    |N/D      |N/D        | Sì        |
|Esportare i file crittografati allegati alla posta elettronica    |Sì       |Sì  |Sì    |
|Esportare documenti crittografati in SharePoint e OneDrive    |No       |No  |Sì    |
|||||

**Nota:** eDiscovery non supporta i file crittografati in SharePoint e OneDrive quando un'etichetta di riservatezza che ha applicato la crittografia è configurata con una delle impostazioni seguenti:

- Gli utenti possono assegnare autorizzazioni quando applicano manualmente l'etichetta a un documento. Questa operazione viene talvolta definita autorizzazioni *definite dall'utente.*<br/>

- L'accesso utente al documento ha un'impostazione di scadenza impostata su un valore diverso da **Never.**

Per ulteriori informazioni su queste impostazioni, vedere la sezione "Configurare le impostazioni di crittografia" in Limitare l'accesso al contenuto utilizzando etichette di riservatezza [per applicare la crittografia.](encryption-sensitivity-labels.md#configure-encryption-settings)

I documenti crittografati con le impostazioni precedenti possono comunque essere restituiti da una ricerca eDiscovery. Ciò può verificarsi quando una proprietà del documento (ad esempio il titolo, l'autore o la data di modifica) corrisponde ai criteri di ricerca. Anche se questi documenti potrebbero essere inclusi nei risultati della ricerca, non possono essere visualizzati in anteprima o esaminati. Questi documenti rimarranno crittografati anche quando vengono esportati in Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisiti per la decrittografia in eDiscovery

Per visualizzare in anteprima, esaminare ed esportare i file crittografati con le tecnologie di crittografia Microsoft, è necessario disporre del ruolo di decrittografia RMS. È inoltre necessario essere assegnati a questo ruolo per esaminare ed eseguire query su file crittografati che vengono aggiunti a un set di revisione in Advanced eDiscovery.

Questo ruolo viene assegnato per impostazione predefinita al  gruppo di ruoli Manager eDiscovery nella pagina Autorizzazioni nel Centro sicurezza e conformità & di Office 365. Per ulteriori informazioni sul ruolo di decrittografia RMS, vedere [Assign eDiscovery permissions.](assign-ediscovery-permissions.md#rms-decrypt)
