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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere il livello di probabilità di posta indesiderata (SCL) applicato ai messaggi in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625282"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Livello di probabilità di posta indesiderata (SCL) in EOP

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi in ingresso passano attraverso il filtro della posta indesiderata in EOP e vengono assegnati un punteggio di posta indesiderata. Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) che viene aggiunto al messaggio in un X-header. Un livello di probabilità di posta indesiderata più alto indica che è più probabile che un messaggio sia posta indesiderata. EOP adotta un'azione sul messaggio in base al SCL.

Il significato del livello di probabilità di posta elettronica (SCL) e le azioni predefinite eseguite sui messaggi sono descritti nella tabella seguente. Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

****

|SCL|Definizione|Azione predefinita|
|:---:|---|---|
|-1|Il messaggio ha ignorato il filtro posta indesiderata. Ad esempio, il messaggio viene inviato da un mittente sicuro, è stato inviato a un destinatario sicuro o da un server di origine della posta elettronica nell'elenco indirizzi IP consentiti. Per ulteriori informazioni, vedere [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Il filtro posta indesiderata ha determinato che il messaggio non era posta indesiderata.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Il filtro posta indesiderata ha contrassegnato il messaggio come **Posta indesiderata**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|9 |Il filtro posta indesiderata ha contrassegnato il messaggio come **posta indesiderata ad alta probabilità**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|

Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro posta indesiderata.

È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per impostare il livello di probabilità di posta indesiderata sui messaggi. Se si utilizza una regola del flusso di posta per impostare il livello di probabilità di posta indesiderata, i valori 5 o 6 attivano l'azione di filtro della posta indesiderata per Posta indesiderata e i valori 7, 8 o 9 attivano l'azione di filtro della posta indesiderata per Posta indesiderata alta **confidenza.** Per ulteriori informazioni, vedere [Use mail flow rules to set the spam confidence level (SCL) in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

Analogamente al livello di probabilità di posta indesiderata, il livello di reclamo in blocco (BCL) identifica la posta elettronica in blocco non erta (nota anche come _posta grigia)._ Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata. Configurare la soglia BCL nei criteri di protezione da posta indesiderata. Per ulteriori informazioni, vedere [Configure anti-spam policies in EOP,](configure-your-spam-filter-policies.md) [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md)e Qual è la differenza tra posta indesiderata e posta [elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per Microsoft 365 amministratori e **professionisti IT,** portati da LinkedIn Learning.
