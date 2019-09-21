---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Se l'amministratore abilita le notifiche per gli utenti, riceverà un messaggio di notifica che elenca i messaggi inviati alla cassetta postale che sono stati identificati come posta indesiderata, in blocco o in messaggi di phishing. È possibile rilasciare o segnalare i messaggi dopo la notifica.
ms.openlocfilehash: 499af3ae2934eed19e421918af07a45b72fe2518
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084338"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365

Se l'amministratore abilita le notifiche di posta indesiderata per gli utenti, riceverà un messaggio di notifica che elenca i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata e in quarantena
  
> [!TIP]
> Se si è un amministratore e si desidera abilitare questa funzionalità, è possibile scegliere l'opzione quando si [modifica un criterio di protezione da posta indesiderata predefinito](https://go.microsoft.com/fwlink/?LinkId=800313). 
  
Il messaggio ricevuto include il numero di messaggi di posta indesiderata in quarantena e la data e l'ora (in formato UTC (Universal Coordinated Time) dell'ultimo messaggio nell'elenco. L'elenco include quanto segue per ogni messaggio:
  
- **Mittente** Il nome e l'indirizzo di posta elettronica del messaggio in quarantena. 
    
- **Oggetto** Oggetto del messaggio in quarantena. 
    
- **Data** Data e ora (in formato UTC) del messaggio in quarantena. 
    
- **Dimensioni** Le dimensioni del messaggio, in kilobyte (KB). 
    
Di seguito sono riportate le azioni che è possibile eseguire con un messaggio in quarantena:

- **Visualizzare in anteprima** il messaggio se si desidera visualizzare in anteprima il contenuto o l'intestazione prima di eseguire l'azione.

- **Scaricare** il messaggio se si desidera esaminare il messaggio e gli allegati (se presenti) del dispositivo prima di eseguire l'azione.

- **Rilascia** se il messaggio non è posta indesiderata e si desidera che Office 365 invii il messaggio alla cassetta postale.

- **Rilascia & Consenti al mittente** se il messaggio non è posta indesiderata e si desidera che Office 365 aggiunga il mittente all'elenco Mittenti attendibili e destinatari per i messaggi di posta elettronica futuri. Tenere presente che l'amministratore può disporre di altre configurazioni Consenti/blocca a livello di organizzazione che sostituiscono l'elenco dei mittenti attendibili.

- **Rilascia & report**, se il messaggio non è posta indesiderata e si desidera inviare il messaggio alla cassetta postale e segnalarlo a Microsoft per l'analisi.

- **Blocca mittente** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.

Tenere presente quanto segue:
  
- I messaggi in quarantena perché hanno trovato una regola del flusso di posta non sono inclusi nei messaggi in quarantena dell'utente. Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena.
    
- È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.
    

