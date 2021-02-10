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
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167156"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Livello di probabilità di posta indesiderata (SCL) in EOP

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi in ingresso passano attraverso il filtro posta indesiderata in EOP e vengono assegnati un punteggio di posta indesiderata. Tale punteggio viene mappato a un singolo livello di probabilità di posta indesiderata (SCL) che viene aggiunto al messaggio in un X-header. Un livello di probabilità di posta indesiderata più alto indica che è più probabile che un messaggio sia posta indesiderata. EOP adotta un'azione sul messaggio in base al SCL.

Il significato del livello di probabilità di posta elettronica e le azioni predefinite eseguite sui messaggi sono descritti nella tabella seguente. Per ulteriori informazioni sulle azioni che è possibile eseguire sui messaggi in base al verdetto del filtro posta indesiderata, vedere Configurare i criteri di protezione da posta indesiderata [in EOP.](configure-your-spam-filter-policies.md)

****

|SCL|Definizione|Azione predefinita|
|:---:|---|---|
|-1|Il messaggio ha ignorato il filtro posta indesiderata. Ad esempio, il messaggio deriva da un mittente sicuro, è stato inviato a un destinatario sicuro o da un server di origine della posta elettronica nell'elenco indirizzi IP consentiti. Per ulteriori informazioni, vedere [Creare elenchi di mittenti attendibili in EOP.](create-safe-sender-lists-in-office-365.md)|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Il filtro posta indesiderata ha determinato che il messaggio non era posta indesiderata.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Il filtro posta indesiderata ha contrassegnato il messaggio come **posta indesiderata**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|9 |Il filtro posta indesiderata ha contrassegnato il messaggio come **posta indesiderata con alta probabilità**|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|

Si noterà che SCL 2, 3, 4, 7 e 8 non vengono utilizzati dal filtro posta indesiderata.

È possibile utilizzare le regole del flusso di posta (note anche come regole di trasporto) per impostare il livello di probabilità di posta indesiderata sui messaggi. Se si utilizza una regola del flusso di posta per impostare il livello di probabilità di posta indesiderata, i valori 5 o 6 attivano l'azione di filtro della posta indesiderata per la posta indesiderata **e** i valori 7, 8 o 9 attivano l'azione di filtro della posta indesiderata per alta probabilità di posta **indesiderata.** Per ulteriori informazioni, vedere Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata [(SCL) nei messaggi.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Analogamente al livello di probabilità di posta indesiderata, il livello di reclamo in blocco (BCL, Bulk Complaint Level) identifica la posta elettronica inviata in blocco (nota anche come _posta grigia)._ Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata. La soglia BCL viene configurata nei criteri di protezione dalla posta indesiderata. Per ulteriori informazioni, vedere Configure [anti-spam policies in EOP,](configure-your-spam-filter-policies.md) [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md)e Qual è la differenza tra posta indesiderata e posta [elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per amministratori di **Microsoft 365** e professionisti IT, grazie a LinkedIn Learning.
