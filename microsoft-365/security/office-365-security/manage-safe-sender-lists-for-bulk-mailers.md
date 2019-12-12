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
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970302"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Gestire gli elenchi di mittenti attendibili per messaggi inviati in blocco

Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio Office 365 rispetta i mittenti e i domini attendibili esaminando `RFC 5321.MailFrom` l'indirizzo e `RFC 5322.From` l'indirizzo, mentre Outlook aggiunge `RFC 5322.From` l'indirizzo all'elenco dei mittenti attendibili di un utente. (Nota: il servizio controlla sia l' `5321.MailFrom` indirizzo che `5322.From` l'indirizzo per i mittenti e i domini bloccati).

L' `SMTP MAIL FROM` indirizzo, altrimenti noto come `RFC 5321.MailFrom address`, è l'indirizzo di posta elettronica utilizzato per eseguire i controlli SPF e, se non è possibile recapitare la posta, il percorso in cui il messaggio è stato recapitato. Si tratta di questo indirizzo di posta elettronica che viene `Return-Path` inserito nelle intestazioni del messaggio per impostazione predefinita, anche se è possibile che il mittente designi un `Return-Path` indirizzo diverso.

L' `From:` indirizzo nelle intestazioni del messaggio, altrimenti noto come `RFC 5322.From` indirizzo, è l'indirizzo di posta elettronica visualizzato nel client di posta elettronica, ad esempio Outlook.

La maggior parte del tempo, `5321.MailFrom` gli `5322.From` indirizzi e sono gli stessi. Questa è la caratteristica tipica della comunicazione da persona a persona. Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi sono spesso diversi. Questo accade solitamente più spesso per i messaggi di posta elettronica in blocco.

Si supponga, ad esempio, che la compagnia aerea Blu laggiù abbia assunto Margie ' s Travel per inviare la propria pubblicità tramite posta elettronica. È quindi possibile ottenere un messaggio nella posta in arrivo dal mittente blueyonder@news.blueyonderairlines.com. In questo esempio:

- L' `5321.MailFrom` indirizzo è blueyonder.Airlines@margiestravel.com.

- L' `5322.From` indirizzo è blueyonder@news.blueyonderairlines.com, che è quello che vedrai in Outlook.

Per evitare che il messaggio venga filtrato, è possibile eseguire le operazioni seguenti:

- **Come utente**: aggiungere l' `RFC 5322.From` indirizzo come mittente attendibile in Outlook.

- **Come amministratore**: impostare una regola del [flusso di posta](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (nota anche come regola di trasporto).
