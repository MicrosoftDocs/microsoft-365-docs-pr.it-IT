---
title: Livello di probabilità di posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo, gli amministratori possono ottenere informazioni su come il livello di probabilità di posta indesiderata (SCL) determina la verosimiglianza di un messaggio come posta indesiderata.
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035249"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Livello di probabilità di posta indesiderata (SCL) in Office 365

Quando Microsoft 365 (Exchange Online o standalone Exchange Online Protection (EOP) senza cassette postali di Exchange Online) riceve un messaggio di posta elettronica in ingresso, il messaggio passa attraverso il filtro della posta indesiderata e viene assegnato un punteggio di posta indesiderata. Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) aggiunto al messaggio in un X-header. Un livello SCL superiore indica che un messaggio è più probabile che sia posta indesiderata. Il servizio esegue un'azione sul messaggio in base al livello SCL.

La modalità SCL e le azioni predefinite eseguite nei messaggi sono descritte nella tabella seguente. Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro della posta indesiderata, vedere [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**Livello di probabilità di posta indesiderata**|**Definizione**|**Azione predefinita**|
|-1|Il messaggio ha ignorato il filtro della posta indesiderata. Ad esempio, il messaggio è proveniente da un mittente sicuro, è stato inviato a un destinatario sicuro oppure è da un server di origine posta elettronica nell'elenco indirizzi IP consentiti. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md).|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Filtro posta indesiderata determinato il messaggio non era posta indesiderata.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Filtro posta indesiderata contrassegnata come **posta indesiderata**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|9 |Filtro posta indesiderata contrassegnata come **posta indesiderata con elevata sicurezza**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|

Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro per la posta indesiderata.

È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per contrassegnare il livello SCL nei messaggi. Se si utilizza una regola del flusso di posta per impostare SCL, i valori 5 o 6 attivano l'azione del filtro posta indesiderata per la **posta indesiderata**e i valori 7, 8 o 9 attivano l'azione del filtro posta indesiderata per la posta indesiderata **elevata**. Per ulteriori informazioni, vedere [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Analogamente a SCL, il livello di reclamo in blocco (BCL) identifica la posta elettronica di massa non valida (nota anche come _posta grigia_). Una BCL superiore indica che è più probabile che un messaggio di posta in blocco generi reclami (ed è pertanto più probabile che sia posta indesiderata). È possibile configurare la soglia BCL nei criteri di protezione da posta indesiderata. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in office 365](configure-your-spam-filter-policies.md), il [livello di reclamo in blocco (BCL) in Office 365)](bulk-complaint-level-values.md)e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![Piccola icona per LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Scopri i corsi video gratuiti per **Microsoft 365 Admins e professionisti it**, offerti da LinkedIn Learning.|
