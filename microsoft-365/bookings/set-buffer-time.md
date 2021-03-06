---
title: Impostare il tempo di buffer in Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Impostare il tempo di buffer prima o dopo un appuntamento in Microsoft Bookings per consentire il tempo necessario per la pulizia o la reimpostazione dell'attrezzatura.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962348"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Impostare il tempo di buffer in Microsoft Bookings

Alcuni appuntamenti potrebbero richiedere tempo prima o dopo l'incontro con il cliente per configurare, pulire o reimpostare la sala e l'attrezzatura. In caso contrario, se si è in viaggio tra gli appuntamenti dei clienti, potrebbe essere necessario del tempo per assicurarsi che tu e il tuo team possano passare da un appuntamento all'altro senza dover attendere il cliente.

È possibile impostare il tempo del buffer prima dell'inizio degli appuntamenti, dopo la fine degli appuntamenti o di entrambi per concedere al personale il tempo aggiuntivo necessario per prepararsi per l'appuntamento successivo.

## <a name="set-buffer-time-defaults"></a>Configurare le impostazioni predefinite del tempo di buffer

I valori predefiniti relativi al tempo del buffer sono impostati nella **pagina Dettagli** servizio in Bookings. Come tutte le impostazioni predefinite del servizio impostate in questa pagina, queste impostazioni predefinite possono essere modificate dall'utente per una prenotazione specifica per soddisfare esigenze specifiche dei clienti.

L'impostazione del tempo del buffer è disponibile appena sotto **la selezione durata** predefinita nella pagina Dettagli **servizio.** Prima di poter essere impostato per un determinato servizio, devi abilitare l'impostazione del tempo del buffer selezionando l'interruttore del tempo del buffer. In questo **modo** vengono visualizzati gli elenchi a discesa Prima e Dopo, che vengono utilizzati per selezionare la quantità di tempo predefinita da mantenere prima e dopo ogni prenotazione, come illustrato di seguito: 

   ![Immagine di Bookings con il tempo buffer abilitato](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tempo di buffer e tempo dell'appuntamento

Per evitare confusione sull'ora dell'appuntamento con il cliente, Bookings mostra il tempo di buffer e l'ora dell'appuntamento effettivo (ovvero, l'ora in cui è previsto l'incontro con il cliente) sul calendario dell'utente e nelle conferme di posta elettronica e nei promemoria inviati al personale interessato. Ad esempio, di seguito è riportato ciò che si potrebbe vedere in Prenotazioni per un appuntamento con un cliente che include 15 minuti di tempo di buffer pre-appuntamento.

L'evento, visualizzato a sinistra nell'immagine seguente, mostra un'ombreggiatura più chiara per il tempo di buffer e una più scura per l'appuntamento con il cliente effettivo. La chiamata all'appuntamento (che viene aperta quando si seleziona l'evento) indica in modo specifico che l'appuntamento è dalle 9.00 alle 10.00 con Katie Jordan e include 15 minuti di tempo buffer prima dell'appuntamento e 0 minuti dopo l'appuntamento. Le conferme e i promemoria al personale fanno riferimento allo stesso modo al buffer specifico e all'ora dell'appuntamento, mentre il cliente otterrà solo conferme e promemoria che fanno riferimento a un appuntamento dalle 9.00 alle 10.00.

   ![Immagine del call-out dell'appuntamento bookings con l'ora del buffer visualizzata](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tempo di buffer e disponibilità

I clienti non vedono direttamente e non possono modificare i tempi di buffer impostati. Tuttavia, poiché il tempo di buffer viene utilizzato per calcolare la durata complessiva del servizio, i clienti vedono te e il tuo personale pertinente come prenotati durante gli orari di appuntamento sia buffer che regolari. I clienti visualizzano anche la disponibilità per l'utente e il personale solo se c'è tempo sufficiente sia per l'appuntamento che per il relativo tempo buffer.

Ad esempio, un appuntamento di un'ora con un buffer di 15 minuti prima dell'appuntamento richiede un blocco di tempo disponibile di almeno 1 ora e 15 minuti. Un appuntamento per questo servizio pertanto riempie un blocco di 75 minuti di tempo nel calendario e richiede 75 minuti di disponibilità per prenotare senza conflitti.
