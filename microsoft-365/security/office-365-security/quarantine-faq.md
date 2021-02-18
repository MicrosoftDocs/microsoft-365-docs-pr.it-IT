---
title: Domande frequenti sui messaggi in quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sui messaggi in quarantena in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8496ae4f1702bb63328be0c494d8829c9ddd8cf2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289402"
---
# <a name="quarantined-messages-faq"></a>Domande frequenti sui messaggi in quarantena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In questo argomento vengono fornite le domande frequenti e le risposte sui messaggi di posta elettronica in quarantena per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online o organizzazioni exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online.

Per domande e risposte sulla protezione da posta indesiderata, vedere Domande frequenti [sulla protezione da posta indesiderata.](anti-spam-protection-faq.md)

Per domande e risposte sulla protezione antimalware, vedere [Domande frequenti sulla protezione antimalware.](anti-malware-protection-faq-eop.md)

Per domande e risposte sulla protezione anti-spoofing, vedere Domande frequenti sulla protezione [anti-spoofing.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Come si gestiscono i messaggi messi in quarantena per malware?

Solo gli amministratori possono gestire i messaggi messi in quarantena per malware. Per ulteriori informazioni, vedere Gestire i messaggi e i file in quarantena [come amministratore.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Come mettere in quarantena la posta indesiderata?

Per impostazione predefinita, i messaggi classificati come posta indesiderata o posta inviata in blocco dal filtro della posta indesiderata vengono recapitati nella cassetta postale dell'utente e spostati nella cartella Posta indesiderata. Tuttavia, è possibile creare e configurare criteri di protezione dalla posta indesiderata per mettere in quarantena la posta indesiderata o i messaggi di posta elettronica in blocco. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Come si consente agli utenti di accedere alla quarantena?

Un utente deve disporre di un account valido per accedere ai propri messaggi in quarantena. EOP autonomo richiede che gli utenti siano rappresentati come utenti di posta elettronica in EOP (creati manualmente o creati tramite la sincronizzazione della directory). Per ulteriori informazioni sulla gestione degli utenti in ambienti EOP autonomi, vedere [Manage mail users in EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>A quali messaggi possono accedere gli utenti finali in quarantena?

Gli utenti possono accedere alla posta indesiderata, alla posta elettronica in blocco e (a partire da aprile 2020) ai messaggi di phishing in cui sono destinatari. Gli utenti finali non possono accedere al malware in quarantena, al  phishing ad alta probabilità o ai messaggi messi in quarantena a causa dell'azione Recapita il messaggio all'azione di quarantena ospitata nelle regole del flusso di posta (note anche come regole di trasporto). Per ulteriori informazioni sugli utenti che accedono ai messaggi in quarantena, vedere Trovare e [rilasciare i messaggi in quarantena come utente.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Per quanto tempo i messaggi vengono mantenuti in quarantena?

È possibile configurare per quanto tempo i messaggi di posta indesiderata, phishing e posta elettronica in blocco vengono mantenuti in quarantena utilizzando i criteri di protezione da posta indesiderata. Il valore predefinito è 30 giorni, che è anche il massimo. Per ulteriori informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)

Per i messaggi messi in quarantena dall'azione della regola del flusso di posta Recapitare il messaggio alla quarantena ospitata, i messaggi vengono mantenuti in quarantena per 30 giorni. Non è possibile configurare questa durata.

Dopo la scadenza del periodo di tempo, i messaggi vengono eliminati e non sono ripristinabili.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?

Nel Centro sicurezza & conformità è possibile selezionare e rilasciare fino a 100 messaggi alla volta.

Gli amministratori possono utilizzare i cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in PowerShell di Exchange Online o EOP PowerShell autonomo per trovare e rilasciare i messaggi in quarantena in blocco e per segnalare i falsi positivi in blocco.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Sono supportati i caratteri jolly nella ricerca dei messaggi in quarantena? Posso cercare i messaggi in quarantena in base a un dominio specifico?

I caratteri jolly non sono supportati nel Centro sicurezza & conformità. Ad esempio, quando si cerca un mittente, è necessario specificare l'indirizzo di posta elettronica completo. Tuttavia, è possibile utilizzare i caratteri jolly in PowerShell di Exchange Online o in PowerShell EOP autonomo.

Ad esempio, copia il codice di PowerShell seguente in NotePad e salva il file con estensione ps1 in un percorso facile da trovare (ad esempio, C:\Data\QuarantineRelease.ps1).

Quindi, dopo aver eseguito la connessione a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) o [PowerShell per Exchange Online Protection,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)eseguire il comando seguente per eseguire lo script:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Lo script esegue le azioni seguenti:

- Individuare i messaggi non ricevuti messi in quarantena come posta indesiderata da tutti i mittenti nel dominio fabrikam. Il numero massimo di risultati è 50.000 (50 pagine di 1000 risultati).
- Salvare i risultati in un file CSV.
- Rilasciare i messaggi in quarantena corrispondenti a tutti i destinatari originali.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

Dopo aver rilasciato un messaggio, non è possibile rilasciarlo di nuovo.
