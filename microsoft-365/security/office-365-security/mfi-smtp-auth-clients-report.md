---
title: Report sui client di autenticazione SMTP
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sul rapporto client auth SMTP nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: 7d3977293b0456b9ab3d383c1a41be9858a66028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084653"
---
# <a name="smtp-auth-clients-report"></a>Report sui client di autenticazione SMTP

Il rapporto **client auth SMTP** evidenzia l'utilizzo del protocollo di invio client auth SMTP da parte degli utenti o degli account di sistema nell'organizzazione. Questo protocollo legacy (che utilizza l'endpoint smtp.office365.com) offre solo l'autenticazione di base ed è suscettibile di essere utilizzato dagli account compromessi per inviare messaggi di posta elettronica.  Questo rapporto consente di verificare la possibilità di attività inusuali. Vengono inoltre visualizzati i dati di utilizzo di TLS per client o dispositivi che utilizzano l'autenticazione SMTP.

Il widget visualizzato nel dashboard del flusso di posta indica il numero di utenti o di account di servizio che hanno utilizzato il protocollo di autenticazione SMTP negli ultimi 7 giorni.

![Il rapporto client auth SMTP nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../media/smtp-auth-clients-report-selected.png)

Se si fa clic sul widget, verrà aperto un riquadro a comparsa che fornisce una visualizzazione aggregata dell'utilizzo e dei volumi TLS per l'ultima settimana.

![Il riquadro a comparsa nel rapporto client auth SMTP](../media/smtp-auth-clients-flyout.png)

Quando si fa clic sul collegamento del **rapporto client auth SMTP** , vengono visualizzati due pivot di dati principali e due visualizzazioni di dati. I pivot di dati sono il **volume di invio** e l' **utilizzo di TLS**. Le visualizzazioni dati sono il grafico e la tabella details.

La visualizzazione **volume di invio** Mostra il numero di messaggi che sono stati inviati utilizzando l'autenticazione SMTP per l'intervallo di tempo specificato. È possibile modificare l'intervallo facendo clic su **filtri**. Il grafico è organizzato dal dominio del mittente. È possibile visualizzare i dati separati per ogni dominio selezionando il dominio nell'elenco a discesa **Mostra dati per** .

![Invio di volume nel rapporto client auth SMTP](../media/smtp-auth-clients-report-sending-volume.png)

È possibile visualizzare informazioni dettagliate sui mittenti e sui relativi conteggi dei messaggi facendo clic su **Visualizza tabella dettagli**. Per tornare al grafico, fare clic su **Visualizza report**.

![Tabella dei dettagli per l'invio del volume nel rapporto client auth SMTP](../media/smtp-auth-clients-report-details-sending-volume.png)

Il pivot **utilizzo TLS** è importante a causa dell'imminente deprecazione di TLS 1.0 e TLS 1.1 in Office 365. Molti dispositivi e applicazioni legacy non saranno in grado di inviare messaggi di posta elettronica se sono in grado di utilizzare solo TLS 1.0 con l'autenticazione SMTP. In questo pivot è possibile identificare ed eseguire azioni su utenti e account di sistema che continuano a utilizzare versioni precedenti di TLS.

![Utilizzo di TLS nel rapporto client auth SMTP](../media/smtp-auth-clients-report-tls-usage.png)

È possibile visualizzare informazioni dettagliate sui mittenti, sulle versioni di TLS che utilizzano con l'autenticazione SMTP e sui conteggi dei messaggi facendo clic su **Visualizza tabella dettagli**. Per tornare al grafico, fare clic su **Visualizza report**.

È inoltre possibile scaricare una versione più dettagliata del rapporto facendo clic su Richiedi report.

![Tabella dei dettagli per l'utilizzo di TLS nel rapporto client auth SMTP](../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
