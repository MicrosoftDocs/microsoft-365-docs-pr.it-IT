---
title: Riportare informazioni per Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Informazioni su come visualizzare una visualizzazione di 4 mesi dell'attività di Bookings
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887228"
---
# <a name="reporting-info-for-bookings"></a>Informazioni sulla creazione di report per Bookings

Ora puoi visualizzare una visualizzazione di quattro mesi del calendario di Bookings in un file TSV. Il file TSV mostrerà quattro mesi di dati, ma è possibile selezionare diversi periodi di quattro mesi nel corso di un anno.

Queste informazioni sul livello di appuntamento possono essere utilizzate per visualizzare l'attività del cliente attorno al calendario bookings. I file TSV sono file con valori separati da tabulazioni. Puoi visualizzare o modificare un file come questo con qualsiasi editor di testo o programma di foglio di calcolo, ad esempio Excel.

## <a name="see-four-months-of-booking-activity"></a>Vedi quattro mesi di attività di Booking

1. Nel dashboard del calendario di Bookings seleziona **Esporta altri dati come TSV.**

:::image type="content" source="../media/bookings-activities.png" alt-text="Screenshot: 4 mesi di attività bookings":::

1. Salvare il file con un nuovo nome e specificare .xls o xlsx.

1. Apri il file per visualizzare la visualizzazione di quattro mesi del calendario di Bookings.

1. Scegliere la data per il report e selezionare **Esporta**.

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Screenshot: Pick a time range and export data to TSV file.":::

1. Il report scaricato contiene un nuovo set di campi oltre ai campi esistenti.

Il report include i campi seguenti.

 - **Data e ora**
- **Nome cliente**
- **Posta elettronica cliente**
- **Cliente Telefono**
- **Indirizzo cliente**
- **Personale**
- **Servizio**
- **Posizione**
- **Durata (minuti)**
- **Tipo di evento**

Il report migliorato ora contiene i campi seguenti.

- **Tipo di prezzo**   Tipo di prezzo predefinito impostato per un servizio durante la creazione del servizio.
- **Price**   Prezzo corrispondente al tipo di prezzo scelto.
- **Valuta**   Tipo di valuta impostato per un'azienda.
- **Partecipanti Cc**   Destinatari che riceveranno le notifiche di posta elettronica per una prenotazione. Questo può essere specificato dall'app Teams durante la creazione di una prenotazione.
- **Conteggio partecipanti sottoscritti**   Numero di clienti che hanno prenotato un servizio di prenotazione di gruppo.
- **Notifiche di testo abilitate**   Indica se i clienti possono SMS notifiche correlate al testo.
- **Campi personalizzati**   In questo campo vengono combinate tutte le domande e le risposte relative a una singola prenotazione.
- **ID prenotazione**   Ciò è utile per identificare le stesse prenotazioni di un servizio di gruppo.
