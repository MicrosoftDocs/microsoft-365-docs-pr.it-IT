---
title: Domande frequenti sulla quarantena
ms.author: tracyp
author: MSFTTracyP
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
description: In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting.
ms.openlocfilehash: d275a919e58d2a908fb10d4dff412ebe0859662f
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021842"
---
# <a name="quarantine-faq"></a>Domande frequenti sulla quarantena

In questo argomento vengono riportate le domande frequenti e le risposte sulla quarantena in hosting. Le risposte sono applicabili a clienti Microsoft Exchange Online e Exchange Online Protection.

 **D. come è la gestione dei messaggi in quarantena per i malware?**

È necessario utilizzare il Centro sicurezza & conformità per visualizzare e utilizzare i messaggi inviati alla quarantena perché contengono malware. For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).

 **D. Come configurare il servizio per inviare messaggi di posta indesiderata in quarantena?**

R. Per impostazione predefinita, i messaggi sottoposti a filtro contenuto vengono inviati alla cartella Posta indesiderata dei destinatari. Tuttavia, gli amministratori possono configurare i criteri del filtro contenuto per inviare invece i messaggi di posta indesiderata in quarantena. Per ulteriori informazioni sulle azioni che possono essere intraprese sui messaggi a contenuto filtrato, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).

 **D. Il servizio consente ad amministratori e utenti finali di gestire i messaggi di posta indesiderata messi in quarantena?**

R. In qualità di amministratore, è possibile cercare e visualizzare i dettagli su tutti i messaggi di posta elettronica in quarantena nel centro sicurezza e conformità (SCC). Dopo aver individuato il messaggio, è possibile rilasciarlo a specifici utenti e segnalarlo come falso positivo (non indesiderato) al team di analisi di posta indesiderata di Microsoft. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

Gli utenti finali possono gestire i propri messaggi messi in quarantena tramite gli strumenti indicati di seguito:

- Interfaccia utente per la quarantena della posta indesiderata. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).

 **D. come si concede l'accesso alla quarantena per gli utenti finali?**

R. Per accedere alla quarantena della posta indesiderata dell'utente finale, gli utenti finali devono disporre di un ID utente e una password di Office 365 validi. I clienti di EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi creati tramite la sincronizzazione della directory o EAC. Per ulteriori informazioni sulla gestione degli utenti, gli amministratori di EOP possono fare riferimento per [gestire gli utenti di posta elettronica in EOP](manage-mail-users-in-eop.md). Per i clienti autonomi di EOP, si consiglia di utilizzare la sincronizzazione della directory e di abilitare il blocco Edge basato su directory. Per ulteriori informazioni, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

 **D. quali messaggi possono essere consentiti per l'accesso degli utenti in quarantena?**

R. Gli utenti finali possono accedere ai propri phishing, alla posta indesiderata e ai messaggi in blocco. Gli utenti finali non possono accedere al proprio malware, ad alta sicurezza phishing, o ai messaggi che corrispondono a una regola del flusso di posta (nota anche come regola di trasporto). Questi sono disponibili solo nella quarantena di amministratore. 

 **Q. Per quanto tempo i messaggi vengono tenuti in quarantena?**

R. Per impostazione predefinita, i messaggi in quarantena della posta indesiderata vengono mantenuti in quarantena per 30 giorni, mentre i messaggi in quarantena che corrispondono a una regola del flusso di posta vengono mantenuti in quarantena per un massimo di 30 giorni in base al periodo di conservazione impostato nel criterio di filtro del contenuto predefinito. Dopo questo periodo di tempo i messaggi sono eliminati e non recuperabili. Il periodo di conservazione per i messaggi in quarantena che corrispondono a una regola del flusso di posta elettronica non è configurabile. Tuttavia, il periodo di conservazione può essere ridotto con l'impostazione **Conserva posta indesiderata per (giorni)** nei criteri di filtro contenuto. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).

 **D. È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?**

R. Sì, possono essere rilasciati fino a 100 messaggi contemporaneamente nel portale di quarantena. Gli amministratori possono inoltre creare uno script di Windows PowerShell remoto per eseguire questa attività. Utilizzare il cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) per ricercare messaggi e il cmdlet [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) per rilasciarli.

 **D. Sono supportati i caratteri jolly nella ricerca dei messaggi in quarantena? Posso cercare i messaggi in quarantena in base a un dominio specifico?**

R. I caratteri jolly non sono supportati quando si specificano i criteri di ricerca nell'interfaccia di amministrazione di Exchange. Ad esempio, quando si cerca un mittente, è necessario specificare l'indirizzo di posta elettronica completo.

Utilizzando Windows PowerShell remoto, gli amministratori possono specificare il cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) per cercare i messaggi in quarantena per un dominio specifico (ad esempio contoso.com):

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

I risultati possono essere passati al cmdlet [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage). Includere il parametro -ReleaseToAll per rilasciare il messaggio a tutti i destinatari. Una volta che il messaggio viene rilasciato, non può essere rilasciato nuovamente.

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
