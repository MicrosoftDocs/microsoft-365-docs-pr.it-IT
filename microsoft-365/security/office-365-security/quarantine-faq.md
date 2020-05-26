---
title: Domande frequenti sui messaggi in quarantena
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
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sui messaggi in quarantena in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a231e363d5764465547ee1e80cc080c3d7c006c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351096"
---
# <a name="quarantined-messages-faq"></a>Domande frequenti sui messaggi in quarantena

In questo argomento vengono fornite domande e risposte frequenti sui messaggi di posta elettronica in quarantena per le organizzazioni Microsoft 365 con cassette postali in Exchange Online o organizzazioni di Exchange Online Protection (EOP) indipendenti senza cassette postali di Exchange Online.

Per domande e risposte sulla protezione dalla posta indesiderata, vedere [domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md).

Per domande e risposte sulla protezione anti-malware, vedere [anti-malware Protection FAQ](anti-malware-protection-faq-eop.md).

Per domande e risposte sulla protezione anti-spoofing, vedere domande [frequenti sulla protezione anti-spoofing](anti-spoofing-protection-faq.md).

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Come si gestiscono i messaggi che sono stati messi in quarantena per malware?

Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena per malware. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Come si esegue la quarantena della posta indesiderata?

Per impostazione predefinita, i messaggi che vengono classificati come posta indesiderata o in blocco tramite filtro posta indesiderata vengono recapitati alla cassetta postale dell'utente e vengono spostati nella cartella posta indesiderata. Tuttavia, è possibile creare e configurare criteri di protezione dalla posta indesiderata per la quarantena di posta indesiderata o messaggi di posta elettronica. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>In che modo è possibile consentire agli utenti di accedere alla quarantena?

Un utente deve disporre di un account valido per accedere ai propri messaggi in quarantena. EOP autonomo richiede che gli utenti siano rappresentati come utenti di posta elettronica in EOP (creato manualmente o creato tramite la sincronizzazione della directory). Per ulteriori informazioni sulla gestione degli utenti in ambienti EOP autonomi, vedere [Manage mail Users in EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Quali messaggi possono accedere all'accesso degli utenti in quarantena?

Gli utenti possono accedere alla posta indesiderata, all'invio in massa e ai messaggi di phishing (da aprile 2020) dove sono destinatari. Gli utenti finali non possono accedere ai messaggi di posta elettronica in quarantena, al phishing ad alta sicurezza o ai messaggio che sono stati messi in quarantena a causa del **recapito dell'azione di quarantena ospitata** nelle regole del flusso di mail (note anche come regole Per ulteriori informazioni sugli utenti che accedono ai messaggi in quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente](find-and-release-quarantined-messages-as-a-user.md).

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Per quanto tempo i messaggi vengono mantenuti in quarantena?

È possibile configurare la durata della disattivazione della posta indesiderata, del phishing e della posta elettronica in blocco utilizzando i criteri di protezione da posta indesiderata. Il valore predefinito è 30 giorni, che è anche il numero massimo. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)

Per i messaggi che sono stati messi in quarantena dall'azione della regola del flusso di posta **recapitare il messaggio alla quarantena ospitata**, i messaggi vengono mantenuti in quarantena per 30 giorni. Non è possibile configurare questa durata.

Dopo la scadenza del periodo di tempo, i messaggi vengono eliminati e non possono essere recuperati.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?

Nel centro sicurezza & conformità, è possibile selezionare e rilasciare fino a 100 messaggi alla volta.

Gli amministratori possono utilizzare i cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell o standalone EOP PowerShell per individuare e rilasciare i messaggi in quarantena in blocco e per segnalare falsi positivi in blocco.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Sono supportati i caratteri jolly nella ricerca dei messaggi in quarantena? Posso cercare i messaggi in quarantena in base a un dominio specifico?

I caratteri jolly non sono supportati nel centro sicurezza & conformità. Ad esempio, quando si esegue la ricerca di un mittente, è necessario specificare l'indirizzo di posta elettronica completo. Tuttavia, è possibile utilizzare i caratteri jolly in PowerShell di Exchange Online o in EOP PowerShell autonomo.

Ad esempio, utilizzare il seguente comando per trovare messaggi di posta indesiderata in quarantena da tutti i mittenti nel dominio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Successivamente, eseguire il seguente comando per rilasciare tali messaggi a tutti i destinatari originali:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Dopo aver rilasciato un messaggio, non è possibile rilasciarlo.
