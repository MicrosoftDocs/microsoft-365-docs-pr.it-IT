---
title: Protezione antivirus integrata in SharePoint Online, OneDrive e Microsoft Teams
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
description: Informazioni sul modo in cui SharePoint Online rileva i virus nei file che gli utenti caricano e impediscono agli utenti di scaricare o sincronizzare i file.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844237"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protezione antivirus integrata in SharePoint Online, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 utilizza un motore di rilevamento virus comune per l'analisi dei file caricati dagli utenti in SharePoint Online, OneDrive e Microsoft teams. Questa protezione è inclusa in tutti gli abbonamenti che includono SharePoint Online, OneDrive e Microsoft teams.

> [!IMPORTANT]
> Le funzionalità di protezione da virus predefinite sono un modo per contribuire a contenere virus. Non sono intese come un singolo punto di difesa contro il malware per l'ambiente. Si consiglia a tutti i clienti di analizzare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale. Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Cosa succede quando un file infetto viene caricato in SharePoint Online?

Il motore di rilevamento virus Microsoft 365 viene eseguito in modo asincrono all'interno di SharePoint Online. **Tutti i file non vengono analizzati automaticamente al momento del caricamento**. Gli euristici determinano i file da analizzare. Quando viene trovato un file che contiene un virus, il file viene contrassegnato in modo che non possa essere scaricato di nuovo. Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.

Ecco cosa succede:

1. Un utente carica un file in SharePoint Online.
2. SharePoint Online determina se il file soddisfa i criteri per un'analisi.
3. Il motore di rilevamento dei virus analizza il file.
4. Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?

Se un file è infetto, gli utenti non possono scaricare il file da SharePoint Online utilizzando un browser.

Ecco cosa succede:

1. Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.
2. All'utente viene fornito un avviso che è stato rilevato un virus. Per impostazione predefinita, all'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il software antivirus sul proprio dispositivo.

> [!NOTE]
>
> Gli amministratori possono utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in PowerShell di SharePoint Online per impedire agli utenti di scaricare file infetti, anche nella finestra di avviso antivirus. Per istruzioni, vedere [utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Non appena si Abilita il parametro *DisallowInfectedFileDownload* , l'accesso ai file rilevati o bloccati viene completamente bloccato per gli utenti e gli amministratori.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?

I client di sincronizzazione di OneDrive non scaricheranno file che contengono virus. Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funzionalità estese con Microsoft Defender per Office 365

Microsoft 365 organizzazioni che dispongono di [Microsoft Defender per Office 365](office-365-atp.md) incluse nell'abbonamento o acquistate come componente aggiuntivo possono abilitare ATP per SharePoint, OneDrive e Microsoft teams per la creazione di report e la protezione avanzata. Per ulteriori informazioni, vedere [ATP for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sull'antivirus in SharePoint Online, OneDrive e Microsoft teams, vedere [protezione dalle minacce](protect-against-threats.md) e attivazione di [ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).
