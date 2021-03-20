---
title: Protezione da virus incorporata in SharePoint Online, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Informazioni su come SharePoint Online rileva i virus nei file caricati dagli utenti e impedisce agli utenti di scaricare o sincronizzare i file.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a651d198f441c26525cbfb5d7406ae350db8b79e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908083"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Protezione da virus incorporata in SharePoint Online, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)

Microsoft 365 usa un motore di rilevamento virus comune per l'analisi dei file caricati dagli utenti in SharePoint Online, OneDrive e Microsoft Teams. Questa protezione è inclusa in tutte le sottoscrizioni che includono SharePoint Online, OneDrive e Microsoft Teams.

> [!IMPORTANT]
> Le funzionalità antivirus integrate consentono di contenere i virus. Non sono concepiti come un unico punto di difesa contro il malware per l'ambiente. Invitiamo tutti i clienti a analizzare e implementare la protezione antimalware a vari livelli e ad applicare le procedure consigliate per la protezione dell'infrastruttura aziendale. Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Cosa succede se un file infetto viene caricato in SharePoint Online?

Il motore di rilevamento virus di Microsoft 365 viene eseguito in modo asincrono (indipendente dai caricamenti di file) all'interno di SharePoint Online. **Tutti i file non vengono analizzati automaticamente.** L'euristica determina i file da analizzare. Quando viene rilevato che un file contiene un virus, il file viene contrassegnato. Ad aprile 2018, è stato rimosso il limite di 25 MB per i file analizzati.

Ecco cosa succede:

1. Un utente carica un file in SharePoint Online.
2. SharePoint Online, nell'ambito dei processi di ricerca virus, determina in un secondo momento se il file soddisfa i criteri per un'analisi.
3. Se il file soddisfa i criteri per un'analisi, il motore di rilevamento virus analizza il file.
4. Se viene rilevato un virus all'interno del file analizzato, il motore dei virus imposta una proprietà sul file che indica che è infetto.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Cosa succede quando un utente tenta di scaricare un file infetto utilizzando il browser?

Se un file è infetto, gli utenti non possono scaricarlo da SharePoint Online utilizzando un browser.

Ecco cosa succede:

1. Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.
2. All'utente viene visualizzato un avviso che indica che è stato rilevato un virus. Per impostazione predefinita, all'utente viene data la possibilità di scaricare il file e tentare di pulirlo utilizzando il software antivirus nel proprio dispositivo.

> [!NOTE]
>
> Gli amministratori possono utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) in PowerShell di SharePoint Online per impedire agli utenti di scaricare file infetti, anche nella finestra di avviso anti-virus. Per istruzioni, vedere [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Non appena si abilita il *parametro DisallowInfectedFileDownload,* l'accesso ai file rilevati/bloccati è completamente bloccato per gli utenti e gli amministratori.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?

I client di sincronizzazione di OneDrive non scaricano file contenenti virus. Il client di sincronizzazione visualizza una notifica che indica che il file non può essere sincronizzato.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Funzionalità estese con Microsoft Defender per Office 365

Le organizzazioni di Microsoft 365 con [Microsoft Defender per Office 365](office-365-atp.md) incluso nell'abbonamento o acquistate come componente aggiuntivo possono abilitare allegati sicuri per SharePoint, OneDrive e Microsoft Teams per la creazione di report e la protezione avanzate. Per ulteriori informazioni, vedere [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

## <a name="related-articles"></a>Articoli correlati

[Protezione da malware e ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Per ulteriori informazioni sull'antivirus in SharePoint Online, OneDrive e Microsoft Teams, vedere [Protect against threats](protect-against-threats.md) e Turn on Safe Attachments for [SharePoint, OneDrive, and Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)