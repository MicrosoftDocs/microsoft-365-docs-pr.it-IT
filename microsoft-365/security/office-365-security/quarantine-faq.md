---
title: Domande frequenti sulla quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Domande frequenti e risposte sulla quarantena per le cassette postali di Office 365 in Exchange Online o EOP standalone senza cassette postali di Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c5d7f426701ebc9a546a86a4fccbd7015fc0e49
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033855"
---
# <a name="quarantine-faq"></a>Domande frequenti sulla quarantena

In questo argomento sono riportate le domande frequenti e le risposte sulla quarantena per i clienti di Microsoft 365 con cassette postali in Exchange Online o autonomo Exchange Online Protection (EOP) clienti senza cassette postali di Exchange Online.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>D: come si gestiscono i messaggi che sono stati messi in quarantena per malware?

Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena per malware. Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

## <a name="q-how-do-i-quarantine-spam"></a>D: come si esegue la quarantena della posta indesiderata?

R. Per impostazione predefinita, i messaggi che vengono classificati come posta indesiderata o in blocco tramite filtro posta indesiderata vengono recapitati alla cassetta postale dell'utente e vengono spostati nella cartella posta indesiderata. Tuttavia, è possibile creare e configurare criteri di protezione dalla posta indesiderata per la quarantena di posta indesiderata o messaggi di posta elettronica. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>D: in che modo è possibile concedere agli utenti l'accesso alla quarantena?

R. Un utente deve disporre di un account valido per accedere ai propri messaggi in quarantena. EOP autonomo richiede che gli utenti siano rappresentati come utenti di posta elettronica in EOP (creato manualmente o creato tramite la sincronizzazione della directory). Per ulteriori informazioni sulla gestione degli utenti in ambienti EOP autonomi, vedere [Manage mail Users in EOP](manage-mail-users-in-eop.md).

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>D: quali messaggi possono essere consentiti per l'accesso degli utenti in quarantena?

R. Gli utenti possono accedere alla posta indesiderata, alla massa e ai messaggi di phishing di aprile 2020 in cui si trova un destinatario. Gli utenti finali non possono accedere ai messaggi di posta elettronica in quarantena, al phishing ad alta sicurezza o ai messaggio che sono stati messi in quarantena a causa del **recapito dell'azione di quarantena ospitata** nelle regole del flusso di mail (note anche come regole Per ulteriori informazioni sugli utenti che accedono ai messaggi in quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>D: per quanto tempo i messaggi vengono mantenuti in quarantena?

R. È possibile configurare la durata della disattivazione della posta indesiderata, del phishing e della posta elettronica in blocco utilizzando i criteri di protezione da posta indesiderata. Il valore predefinito è 30 giorni, che è anche il numero massimo. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)

Per i messaggi che sono stati messi in quarantena dall'azione della regola del flusso di posta **recapitare il messaggio alla quarantena ospitata**, i messaggi vengono mantenuti in quarantena per 30 giorni. Non è possibile configurare questa durata.

Dopo la scadenza del periodo di tempo, i messaggi vengono eliminati e non possono essere recuperati.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>D: è possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?

R. Nel centro sicurezza & conformità, è possibile selezionare e rilasciare fino a 100 messaggi alla volta.

Gli amministratori possono utilizzare i cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) in PowerShell di Exchange Online o PowerShell autonomo di Exchange Online Protection per individuare e rilasciare i messaggi in quarantena in blocco e per segnalare falsi positivi in blocco.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>D: i caratteri jolly sono supportati durante la ricerca di messaggi in quarantena? Posso cercare i messaggi in quarantena in base a un dominio specifico?

R. I caratteri jolly non sono supportati nel centro sicurezza & conformità. Ad esempio, quando si esegue la ricerca di un mittente, è necessario specificare l'indirizzo di posta elettronica completo. Tuttavia, è possibile utilizzare i caratteri jolly in PowerShell di Exchange Online o Exchange Online Protection PowerShell.

Ad esempio, utilizzare il seguente comando per trovare messaggi di posta indesiderata in quarantena da tutti i mittenti nel dominio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Successivamente, eseguire il seguente comando per rilasciare tali messaggi a tutti i destinatari originali:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Dopo aver rilasciato un messaggio, non è possibile rilasciarlo.
