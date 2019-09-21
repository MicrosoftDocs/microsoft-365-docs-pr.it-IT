---
title: Gestire gli elenchi di mittenti attendibili per messaggi inviati in blocco
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: "Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio rispetta i mittenti e i domini attendibili esaminando l'indirizzo RFC 5321. MailFrom e l'indirizzo RFC 5322. from, mentre Outlook aggiunge l'indirizzo RFC 5322. from all'elenco dei mittenti attendibili di un utente. Nota: il servizio controlla sia l'indirizzo 5321. MailFrom sia l'indirizzo 5322. from per i mittenti e i domini bloccati."
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084713"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Gestire gli elenchi di mittenti attendibili per messaggi inviati in blocco

Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio Office 365 rispetta i mittenti e i domini attendibili esaminando l'indirizzo RFC 5321. MailFrom e l'indirizzo RFC 5322. from, mentre Outlook aggiunge l'indirizzo RFC 5322. from all'elenco dei mittenti attendibili di un utente. Nota: il servizio controlla sia l'indirizzo 5321. MailFrom sia l'indirizzo 5322. from per i mittenti e i domini bloccati.
  
L'indirizzo di posta elettronica SMTP, altrimenti noto come indirizzo RFC 5321. MailFrom, è l'indirizzo di posta elettronica utilizzato per eseguire i controlli SPF e, se non è possibile recapitare la posta, il percorso in cui viene recapitato il messaggio. Si tratta di questo indirizzo di posta elettronica che viene inserito nel percorso di ritorno nelle intestazioni del messaggio per impostazione predefinita, sebbene sia possibile che il mittente designi un indirizzo diverso per il percorso restituito.
  
L'indirizzo da: nelle intestazioni del messaggio, altrimenti noto come indirizzo RFC 5322. from, è l'indirizzo di posta elettronica visualizzato nel client di posta elettronica, ad esempio Outlook.
  
La maggior parte delle volte, gli indirizzi 5321. MailFrom e 5322. from sono gli stessi. Questa è la caratteristica tipica della comunicazione da persona a persona. Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi sono spesso diversi. Questo accade solitamente più spesso per i messaggi di posta elettronica in blocco.
  
Si supponga, ad esempio, che la compagnia aerea Blue laggiù abbia stipulato un contratto con Margie ' s Travel per inviare la propria pubblicità tramite posta elettronica. È quindi possibile ottenere un messaggio nella posta in arrivo dal mittente blueyonder@news.blueyonderairlines.com. In questo caso, l'indirizzo 5321. MailFrom è blueyonder.airlines@margiestravel.com e blueyonder@news.blueyonderairlines.com è l'indirizzo 5322. from che è quello visualizzato in Outlook. Poiché il servizio rispetta l'indirizzo RFC 5322. from, per evitare che questo messaggio venga filtrato, è possibile aggiungere l'indirizzo RFC 5322. from come mittente sicuro in Outlook (come utente) oppure, se si è un amministratore impostare una regola del flusso di posta come mostrato nella barra di protezione [ Sezione Protection](anti-spam-protection.md) .
  

