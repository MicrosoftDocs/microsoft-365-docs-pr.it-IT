---
title: Valori di livello di reclamo in blocco
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui valori del livello di conformità di massa (BCL) utilizzati in Exchange Online Protection (EOP).
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827434"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Livello di reclamo in blocco (BCL) in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP assegna un livello di conformità alla massa (BCL, bulk compliant Level) ai messaggi in ingresso provenienti da Mailer in blocco. La BCL viene aggiunta al messaggio in un X-header ed è simile al livello di [probabilità di posta indesiderata (SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata. Una BCL superiore indica che è più probabile che un messaggio in blocco generi reclami (ed è pertanto più probabile che sia posta indesiderata). Microsoft utilizza le origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata.

I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dei destinatari. I messaggi di posta elettronica in blocco ottimali inviano il contenuto desiderato ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. I messaggi provenienti da un mailer di posta in blocco sono noti come posta in blocco o posta grigia.

 Il filtro posta indesiderata consente di contrassegnare i messaggi come **posta elettronica in blocco** in base alla soglia BCL (valore predefinito o valore specificato) e di eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio alla cartella posta indesiderata del destinatario). Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla posta [indesiderata](configure-your-spam-filter-policies.md) e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Le soglie BCL sono descritte nella tabella seguente.

****

|BCL|Descrizione|
|:---:|---|
|0|Il messaggio non viene da un mittente in blocco.|
|1, 2, 3|Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.|
|4, 5, 6, 7|Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.|
|8, 9|Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce.|
|
