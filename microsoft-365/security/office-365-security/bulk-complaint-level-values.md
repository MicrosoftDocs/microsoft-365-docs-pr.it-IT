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
description: Gli amministratori possono ottenere informazioni sui valori BCL (Bulk Compliance Level) utilizzati in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205084"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Livello di reclamo in blocco (BCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP assegna un livello di conformità in blocco (BCL) ai messaggi in ingresso dai mailer in blocco. Il livello di probabilità di posta indesiderata viene aggiunto al messaggio in un X-header ed è simile al livello di probabilità di posta indesiderata [(SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata. Un livello di probabilità di posta indesiderata più elevato indica che un messaggio in blocco è più probabile che generi reclami (ed è quindi più probabile che sia posta indesiderata). Microsoft usa sia origini interne che di terze parti per identificare la posta in blocco e determinare il BCL appropriato.

I mailer in blocco variano in base ai modelli di invio, alla creazione di contenuto e alle procedure di acquisizione dei destinatari. I mailer in blocco inviano ai propri sottoscrittori i messaggi desiderati con contenuto pertinente. Questi messaggi generano pochi reclami da parte dei destinatari. Altri mailer in blocco inviano messaggi indesiderati che assomigliano molto alla posta indesiderata e generano molti reclami da parte dei destinatari. I messaggi provenienti da un mailer in blocco sono noti come posta in blocco o posta grigia.

 Il filtro della  posta indesiderata contrassegna i messaggi come posta elettronica in blocco in base alla soglia BCL (il valore predefinito o un valore specificato) ed eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio nella cartella Posta indesiderata del destinatario). Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) e [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Le soglie BCL sono descritte nella tabella seguente.

****

|BCL|Descrizione|
|:---:|---|
|0|Il messaggio non viene inviato da un mittente in blocco.|
|1, 2, 3|Il messaggio viene inviato da un mittente in blocco che genera pochi reclami.|
|4, 5, 6, 7<sup>\*</sup>|Il messaggio viene inviato da un mittente in blocco che genera un numero misto di reclami.|
|8, 9|Il messaggio viene inviato da un mittente in blocco che genera un numero elevato di reclami.|
|

<sup>\*</sup> Si tratta del valore di soglia predefinito utilizzato nei criteri di protezione da posta indesiderata.
