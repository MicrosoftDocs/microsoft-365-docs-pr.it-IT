---
title: Valori di livello di reclamo in blocco, messaggi di posta in blocco, livelli di BCL, come funziona BCL, valutazioni BCL, antispam, intestazione antispam, filtro posta in blocco, Interrompi posta in blocco
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Informazioni sui valori di livello bomplain (BCL) in Office 365.
ms.openlocfilehash: 6b90064db7dd9b27fdc729b65fb798dfbe756da7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895394"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Livello di reclamo in blocco (BCL) in Office 365

I messaggi di posta elettronica in blocco variano nei modelli di invio, nella creazione di contenuto e nelle procedure di acquisizione dei destinatari. Alcuni sono buoni mailer che inviano i messaggi desiderati con contenuti rilevanti ai propri abbonati. Questi messaggi generano alcuni reclami dai destinatari. Altri messaggi di posta elettronica in blocco inviano messaggio non richiesti che assomigliano molto alla posta indesiderata e generano numerosi reclami dai destinatari. I messaggi provenienti da un mailer di posta in blocco sono noti come posta in blocco o posta grigia.

Per distinguere i messaggi provenienti da diversi tipi di posta in blocco, la posta elettronica in ingresso dai mailer di posta in arrivo a Office 365 (Exchange Online o standalone Exchange Online Protection (EOP) senza le cassette postali di Exchange Online) viene assegnata a un livello di reclamo in blocco (BCL) aggiunto a il messaggio in un X-header. La BCL è simile al [livello di probabilità di posta indesiderata (SCL)](spam-confidence-levels.md) utilizzato per identificare i messaggi come posta indesiderata. Una BCL superiore indica che è più probabile che un messaggio in blocco generi reclami (ed è pertanto più probabile che sia posta indesiderata). Microsoft utilizza le origini sia interne che di terze parti per identificare la posta in blocco e determinare la BCL appropriata.

 Il filtro posta indesiderata consente di contrassegnare i messaggi come **posta elettronica in blocco** in base alla soglia BCL (valore predefinito o valore specificato) e di eseguire l'azione specificata sul messaggio (l'azione predefinita è recapitare il messaggio alla cartella posta indesiderata del destinatario). Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md) e [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

Le soglie BCL sono descritte nella tabella seguente.

|||
|:---:|---|
|**BCL**|**Descrizione**|
|0|Il messaggio non viene da un mittente in blocco.|
|1, 2, 3|Il messaggio è proveniente da un mittente in blocco che genera alcuni reclami.|
|4, 5, 6, 7|Il messaggio è proveniente da un mittente in blocco che genera un numero misto di denunce.|
|8, 9|Il messaggio è proveniente da un mittente in blocco che genera un numero elevato di denunce.|
|
