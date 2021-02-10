---
title: Valori del livello di reclamo in blocco
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui valori del livello di conformità in blocco (BCL) utilizzati in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165968"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Livello di reclamo in blocco (BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP assegna un livello di conformità in blocco (BCL) ai messaggi in ingresso dai mailer in blocco. Il livello di probabilità di posta indesiderata viene aggiunto al messaggio in un X-header ed è simile al livello di probabilità di posta indesiderata [(SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata. Un livello di probabilità di posta indesiderata più alto indica che un messaggio in blocco è più probabile che generi reclami (ed è quindi più probabile che sia posta indesiderata). Microsoft usa sia origini interne che di terze parti per identificare la posta inviata in blocco e determinare il livello di probabilità di posta indesiderata appropriato.

I mailer in blocco variano in base ai modelli di invio, alla creazione di contenuto e alle procedure di acquisizione dei destinatari. I mailer in blocco possono inviare ai propri sottoscrittori i messaggi desiderati con contenuto pertinente. Questi messaggi generano pochi reclami dai destinatari. Altri mailer in blocco inviano messaggi indesiderati molto simili alla posta indesiderata e generano molti reclami da parte dei destinatari. I messaggi provenienti da un mailer in blocco sono noti come posta inviata in blocco o posta grigia.

 Il filtro della  posta indesiderata contrassegna i messaggi come posta elettronica in blocco in base alla soglia BCL (il valore predefinito o un valore specificato) ed eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio nella cartella Posta indesiderata del destinatario). Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Le soglie BCL sono descritte nella tabella seguente.

****

|BCL|Descrizione|
|:---:|---|
|0|Il messaggio non viene inviato da un mittente in blocco.|
|1, 2, 3|Il messaggio viene inviato da un mittente in blocco che genera pochi reclami.|
|4, 5, 6, 7<sup>\*</sup>|Il messaggio viene inviato da un mittente in blocco che genera un numero misto di reclami.|
|8, 9|Il messaggio viene inviato da un mittente in blocco che genera un numero elevato di reclami.|
|

<sup>\*</sup> Questo è il valore di soglia predefinito utilizzato nei criteri di protezione dalla posta indesiderata.
