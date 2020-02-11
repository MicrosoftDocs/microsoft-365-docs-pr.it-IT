---
title: Rilevamento dei virus in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Informazioni sulla protezione antivirus in SharePoint Online.
ms.openlocfilehash: f22c2a3280148eb23f4ba53ff467a533186ed791
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887273"
---
# <a name="virus-detection-in-sharepoint-online"></a>Rilevamento dei virus in SharePoint Online

Office 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online. I file possono essere analizzati per i virus dopo che sono stati caricati. Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.

> [!IMPORTANT]
> Queste funzionalità antivirus in SharePoint Online sono un modo per contenere virus. Non sono intese come un singolo punto di difesa contro il malware per l'ambiente. Si consiglia a tutti i clienti di valutare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale. Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Cosa succede quando un file infetto viene caricato in SharePoint Online?

Office 365 utilizza un motore di rilevamento virus comune. Il motore viene eseguito in modo asincrono all'interno di SharePoint Online e analizza alcuni file dopo che sono stati caricati. Per determinare quali file vengono analizzati, è possibile utilizzare l'euristica. Quando un file viene trovato per contenere un virus, viene contrassegnato in modo che non possa essere scaricato di nuovo. Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.

Ecco cosa succede:

1. Un utente carica un file in SharePoint Online.

2. SharePoint Online determina se il file soddisfa i criteri per un'analisi.

3. Il motore di rilevamento dei virus analizza il file.

4. Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?

Se un file è infetto, gli utenti non possono scaricare il file da SharePoint Online utilizzando il browser.

Ecco cosa succede:

1. Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.

2. All'utente viene fornito un avviso che è stato rilevato un virus. All'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il proprio software antivirus.

> [!NOTE]
> È possibile utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell per impedire agli utenti di scaricare un file infetto, anche nella finestra di avviso antivirus.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?

Se gli utenti sincronizzano i file con il nuovo client di sincronizzazione di OneDrive (OneDrive. exe) o il client di sincronizzazione di OneDrive for business precedente (Groove. exe), se un file contiene un virus, il client di sincronizzazione non lo scaricherà. Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.
