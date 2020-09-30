---
title: Livello di probabilità di posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sul livello di probabilità di posta indesiderata applicato ai messaggi in Exchange Online Protection (EOP).
ms.openlocfilehash: 51d00b36ae826676f436c0a74617ddbbadf7a30a
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318241"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Livello di probabilità di posta indesiderata (SCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi in ingresso passano attraverso il filtro posta indesiderata in EOP e vengono assegnati un punteggio di posta indesiderata. Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) aggiunto al messaggio in un X-header. Un livello SCL superiore indica che un messaggio è più probabile che sia posta indesiderata. EOP esegue un'azione sul messaggio in base al livello SCL.

La modalità SCL e le azioni predefinite eseguite nei messaggi sono descritte nella tabella seguente. Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro della posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

****

|SCL|Definizione|Azione predefinita|
|:---:|---|---|
|-1|Il messaggio ha ignorato il filtro della posta indesiderata. Ad esempio, il messaggio è proveniente da un mittente sicuro, è stato inviato a un destinatario sicuro oppure è da un server di origine posta elettronica nell'elenco indirizzi IP consentiti. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Filtro posta indesiderata determinato il messaggio non era posta indesiderata.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Filtro posta indesiderata contrassegnata come **posta indesiderata**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|9 |Filtro posta indesiderata contrassegnata come **posta indesiderata con elevata sicurezza**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|

Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro per la posta indesiderata.

È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per contrassegnare il livello SCL nei messaggi. Se si utilizza una regola del flusso di posta per impostare SCL, i valori 5 o 6 attivano l'azione del filtro posta indesiderata per la **posta indesiderata**e i valori 7, 8 o 9 attivano l'azione del filtro posta indesiderata per la posta indesiderata **elevata**. Per ulteriori informazioni, vedere [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Analogamente a SCL, il livello di reclamo in blocco (BCL) identifica la posta elettronica di massa non valida (nota anche come _posta grigia_). Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata. È possibile configurare la soglia BCL nei criteri di protezione da posta indesiderata. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md), [livello di reclamo in blocco (BCL) in EOP)](bulk-complaint-level-values.md)e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per **Microsoft 365 Admins e professionisti it**, offerti da LinkedIn Learning.
