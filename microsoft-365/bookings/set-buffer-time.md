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
description: Impostare il tempo di buffer prima o dopo un appuntamento in Microsoft bookings per consentire il tempo necessario per la pulizia o la reimpostazione delle apparecchiature.
ms.openlocfilehash: dceb777f9ddba9f1ddabfee00608813afae57a86
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419740"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Impostare il tempo di buffer in Microsoft Bookings

Alcuni degli appuntamenti potrebbero richiedere tempo prima o dopo aver incontrato il cliente per impostare, pulire o reimpostare la propria sala e attrezzatura. Oppure, se si è in viaggio tra appuntamenti dei clienti, potrebbe essere necessario tempo per garantire che l'utente e il team possano viaggiare tra gli appuntamenti senza che il cliente sia in attesa.

È possibile impostare il tempo di buffer prima dell'inizio degli appuntamenti, dopo la fine degli appuntamenti o entrambi per fornire al personale il tempo supplementare necessario per prepararsi per il successivo appuntamento.

> [!NOTE]
> La prenotazione è attivata per impostazione predefinita per i clienti che hanno gli abbonamenti Microsoft 365 business standard, Microsoft 365 a3 o Microsoft 365 a5. La prenotazione è disponibile anche per i clienti che dispongono di Office 365 Enterprise E3 e Office 365 Enterprise E5, ma è disattivata per impostazione predefinita. Per iniziare, vedere [accesso a Microsoft bookings](get-access.md). Per abilitare o disabilitare le prenotazioni, vedere [attivazione o disattivazione delle prenotazioni per l'organizzazione](turn-bookings-on-or-off.md).

## <a name="set-buffer-time-defaults"></a>Configurare le impostazioni predefinite del tempo di buffer

Le impostazioni predefinite del tempo di buffer sono impostate nella pagina dei **Dettagli del servizio** in bookings. Come tutte le impostazioni predefinite del servizio impostate in questa pagina, queste impostazioni predefinite possono essere modificate dall'utente per una prenotazione specifica per soddisfare esigenze specifiche dei clienti.

L'impostazione relativa all'ora del buffer è disponibile solo al di sotto dei selezionatori di **durata predefiniti** nella pagina dei **Dettagli del servizio** . Prima di poter essere impostato per un determinato servizio, è necessario abilitare l'impostazione relativa all'ora del buffer selezionando l'opzione intervallo di tempo del buffer. In questo modo vengono visualizzati i menu a discesa **prima** e **dopo** , che vengono utilizzati per scegliere il periodo di tempo predefinito per il blocco prima e dopo ogni prenotazione, come illustrato di seguito:

   ![Immagine delle prenotazioni con tempo di buffer abilitato](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tempo di buffer e tempo dell'appuntamento

Per evitare confusione sull'ora dell'appuntamento con il cliente, Bookings mostra il tempo di buffer e l'ora dell'appuntamento effettivo (ovvero, l'ora in cui è previsto l'incontro con il cliente) sul calendario dell'utente e nelle conferme di posta elettronica e nei promemoria inviati al personale interessato. Ad esempio, di seguito è riportato ciò che si vedrebbe nelle prenotazioni di un appuntamento con un cliente che include 15 minuti di tempo di buffer del preappuntamento.

L'evento, visualizzato a sinistra nell'immagine seguente, mostra un'ombreggiatura più chiara per il tempo di buffer e una più scura per l'appuntamento con il cliente effettivo. La chiamata all'appuntamento (aperta quando si seleziona l'evento) indica in modo specifico che l'appuntamento è dalle 9.00 alle 10.00 con Katie Jordan e include 15 minuti di tempo di buffer prima dell'appuntamento e 0 minuti dopo l'appuntamento. Conferme e promemoria al personale di riferimento in modo analogo al buffer e al tempo di appuntamento, mentre il cliente riceverà solo conferme e promemoria che fanno riferimento alle ore di appuntamento dalle 9.00 alle 10.00.

   ![Immagine della chiamata di prenotazione appuntamenti con il tempo di buffer visualizzato](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tempo di buffer e disponibilità

I clienti non vedono direttamente e non possono modificare i tempi di buffer impostati. Tuttavia, poiché il tempo di buffer viene utilizzato per calcolare la durata complessiva del servizio, i clienti vedranno che l'utente e il personale pertinente sono prenotati durante gli orari del buffer e degli appuntamenti regolari. I clienti possono vedere solo la disponibilità per te e per il tuo personale, se il tempo necessario sia per l'appuntamento che per il tempo di buffer.

Ad esempio, un appuntamento di un'ora con un tempo di buffer preappuntamento di 15 minuti richiede un blocco di tempo disponibile di almeno 1 ora e 15 minuti. Un appuntamento per questo servizio pertanto comporterà un blocco di tempo di 75 minuti nel calendario e avrà bisogno di 75 minuti di disponibilità per la prenotazione senza conflitti.
