---
title: Utilizzare le notifiche di posta indesiderata dell'utente finale per segnalare i messaggi di posta indesiderata in quarantena
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: "Gli utenti che visualizzano un messaggio di notifica di posta indesiderata dell'utente finale dall'amministratore relativo alla posta in quarantena possono eseguire queste azioni nei messaggi. "
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598083"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a>Utilizzare le notifiche di posta indesiderata dell'utente finale per segnalare i messaggi di posta indesiderata in quarantena

Se l'amministratore abilita le notifiche di posta indesiderata dell'utente finale, si riceve un messaggio di notifica in cui vengono elencati i messaggi destinati alla propria cassetta postale che sono stati identificati come posta indesiderata e messi in quarantena. Nel messaggio verrà incluso il numero di messaggi di posta indesiderata e in quarantena e il giorno e l'ora, in formato UTC (Coordinated Universal Time) dell'ultimo messaggio presente nell'elenco. Dall'elenco, è possibile visualizzare le seguenti informazioni su ciascun messaggio:

- **Sender**: il nome del mittente e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.

- **Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.

- **Dimensioni**: la dimensione del messaggio in quarantena, espressa in kilobyte (KB).

È possibile eseguire le seguenti azioni sul ciascun messaggio:

- **Rilascia in posta in arrivo**: facendo clic su questo collegamento, il messaggio viene inviato alla posta in arrivo in cui è possibile visualizzarla.

- **Segnala come non indesiderato: se**si fa clic su questo collegamento, viene inviata una copia del messaggio a Microsoft per l'analisi. Il team di analisi di posta indesiderata, valuta e analizza il messaggio e a seconda dei risultati dell'analisi, regola il filtro di protezione da posta indesiderata per consentire l'inoltro del messaggio.

> [!NOTE]
> I messaggi messi in quarantena a causa di una regola del flusso di posta (nota anche come a) non sono inclusi nei messaggi di posta indesiderata in quarantena dell'utente finale. Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena. <br/><br/>  È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.
