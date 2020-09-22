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
description: Informazioni sul modo in cui SharePoint Online rileva i virus nei file che gli utenti caricano e impediscono agli utenti di scaricare o sincronizzare i file.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196512"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Rilevamento di virus in SharePoint Online, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online, OneDrive e Microsoft teams. I file possono essere analizzati per i virus dopo che sono stati caricati. Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.

> [!IMPORTANT]
> Queste funzionalità antivirus in SharePoint Online sono un modo per contenere virus. Non sono intese come un singolo punto di difesa contro il malware per l'ambiente. Si consiglia a tutti i clienti di valutare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale. Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Cosa succede quando un file infetto viene caricato in SharePoint Online?

Microsoft 365 utilizza un motore di rilevamento virus comune. Il motore viene eseguito in modo asincrono all'interno di SharePoint Online e analizza alcuni file dopo che sono stati caricati. Per determinare quali file vengono analizzati, è possibile utilizzare l'euristica. Quando un file viene trovato per contenere un virus, viene contrassegnato in modo che non possa essere scaricato di nuovo. Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.

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
>
> È possibile utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell per impedire agli utenti di scaricare un file infetto, anche nella finestra di avviso antivirus.
>
> Tenere presente, inoltre, che non appena si Abilita il parametro *DisallowInfectedFileDownload* , l'accesso ai file rilevati/bloccati è completamente bloccato per gli utenti e gli amministratori.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?

Se gli utenti sincronizzano i file con il nuovo client di sincronizzazione di OneDrive (OneDrive.exe) o con il client di sincronizzazione di OneDrive for business precedente (Groove.exe), se un file contiene un virus, il client di sincronizzazione non lo scaricherà. Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.

## <a name="extended-capabilities-with-office-365-atp"></a>Funzionalità estese con Office 365 ATP

I clienti che hanno abilitato Office 365 ATP per SharePoint, OneDrive e Microsoft teams [attivano ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) sono in grado di utilizzare il centro sicurezza & Compliance per gestire i file in quarantena per i rilevamenti AV e ATP. [Solo ATP: utilizzare il Centro sicurezza & Compliance per gestire i file in quarantena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Ulteriori informazioni

Vedere [protezione dalle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) e [attivazione di ATP per SharePoint, OneDrive e Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) per ulteriori informazioni su come configurare il programma antivirus di SharePoint Online.


