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
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come gli strumenti di Microsoft 365 eDiscovery gestiscono i documenti crittografati allegati ai messaggi di posta elettronica.
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920731"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Decrittografia negli strumenti di Microsoft 365 eDiscovery

Le organizzazioni utilizzano la tecnologia di crittografia per proteggere i contenuti sensibili all'interno dell'organizzazione e assicurarsi che solo le persone giuste abbiano accesso a tale contenuto. Le organizzazioni utilizzano vari tipi di crittografia, sia Microsoft Encryption Technologies che di terze parti per soddisfare i propri requisiti di sicurezza e proteggere le informazioni riservate.

Fino ad oggi, la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery in Microsoft 365 richiede una gestione speciale degli elementi crittografati a seconda del tipo di crittografia utilizzata e della fase specifica del flusso di lavoro. Ciò è stato principalmente ottenuto decrittografando il contenuto del messaggio di posta elettronica quando è stato esportato dalle ricerche di contenuto, i casi di eDiscovery di base e i casi avanzati di eDiscovery Non è stato possibile visualizzare in anteprima il contenuto crittografato con le tecnologie di crittografia Microsoft fino all'esportazione. In Advanced eDiscovery, il contenuto crittografato è stato contrassegnato da un errore di elaborazione, che richiedeva di scaricare l'elemento crittografato, decrittografarlo e quindi caricare il file decrittografato in un set di revisione.

Per semplificare la gestione del contenuto crittografato nel flusso di lavoro di eDiscovery, Microsoft 365 eDiscovery Tools è in grado di decrittografare i file crittografati allegati ai messaggi di posta elettronica e inviati in Exchange Online. Prima di questa nuova funzionalità, solo il contenuto di un messaggio di posta elettronica protetto da Rights Management (e non i file allegati) è stato decrittografato. Se un file crittografato con una tecnologia di crittografia Microsoft è associato a un messaggio di posta elettronica che corrisponde ai criteri di ricerca, il file crittografato verrà decrittografato quando i risultati della ricerca verranno preparati per l'anteprima. Questo consente ai responsabili di eDiscovery di visualizzare il contenuto degli allegati di posta elettronica crittografati quando si visualizzano i risultati della ricerca.

> [!NOTE]
> A partire da gennaio 2021, gli strumenti di Microsoft 365 eDiscovery supporteranno i documenti crittografati archiviati in SharePoint Online e OneDrive for business.

## <a name="supported-encryption-technologies"></a>Tecnologie di crittografia supportate

Gli strumenti di Microsoft eDiscovery supportano gli elementi crittografati con le tecnologie di crittografia Microsoft. Queste tecnologie includono la crittografia dei messaggi di Office, Microsoft Information Protection (Sensitivity labels) e Azure Rights Management. Per ulteriori informazioni sulle tecnologie di crittografia Microsoft, vedere [Encryption](encryption.md). Il contenuto crittografato dalle tecnologie di crittografia di terze parti non è supportato. Questo non include il supporto per l'anteprima o l'esportazione di contenuto crittografato con le tecnologie non Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>attività di eDiscovery che supportano gli elementi crittografati

Nella tabella seguente vengono identificate le attività eseguite negli strumenti di Microsoft 365 eDiscovery che supportano la decrittografia dei file crittografati allegati ai massaggi tramite posta elettronica. Le attività di supporto possono essere eseguite su un file crittografato collegato a un messaggio di posta elettronica che corrisponde ai criteri di una ricerca. Il valore "N/A" indica che la funzione non è disponibile nello strumento eDiscovery corrispondente.

|attività di eDiscovery  |Ricerca contenuto  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Ricerca di contenuto nei file crittografati     |No      |No      |No      |
|Visualizzare in anteprima i file crittografati     |Sì      |Sì     |Sì       |
|Esaminare i file crittografati in un set di Revisione    |N/D      |N/D        | Sì        |
|Esportare file crittografati    |Sì       |Sì  |Sì    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisiti per la decrittografia in eDiscovery

È necessario essere assegnati al ruolo RMS Decrypt per visualizzare in anteprima, esaminare ed esportare i file allegati crittografati con Microsoft Encryption Technologies. È inoltre necessario essere assegnati a questo ruolo per esaminare e interrogare gli allegati di posta elettronica crittografati che vengono aggiunti a un set di revisione in Advanced eDiscovery.

Questo ruolo viene assegnato per impostazione predefinita al gruppo di ruoli eDiscovery Manager nel centro sicurezza & conformità di Office 365. Per ulteriori informazioni sul ruolo di decrittografia RMS, vedere [assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md#rms-decrypt).
