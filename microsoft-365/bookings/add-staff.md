---
title: Aggiungere personale a Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Utilizzare questa pagina per creare l'elenco del personale e gestire i dettagli dei membri del personale, ad esempio nome, numero di telefono e indirizzo di posta elettronica.
ms.openlocfilehash: 11d62cc34522de21e63b8bdf6e7e15729ac73dc1
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399194"
---
# <a name="add-staff-to-bookings"></a>Aggiungere personale a Bookings

Nella pagina Personale di Bookings è possibile creare l'elenco del personale e gestire i dettagli dei membri del personale, ad esempio nome, numero di telefono e indirizzo di posta elettronica. È inoltre possibile impostare l'orario di lavoro per ogni membro del personale da qui.

## <a name="add-staff"></a>Aggiungere personale

Anche se Bookings è una funzionalità di Microsoft 365, non tutti i membri del personale devono avere un account Di Microsoft 365. Tutti i membri del personale devono avere un indirizzo di posta elettronica valido per poter ricevere prenotazioni e pianificare le modifiche.

Guardare questo video o seguire i passaggi seguenti per aggiungere il personale.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Passare alla pagina [Gestisci personale e](https://outlook.office.com/bookings/staff) selezionare Aggiungi **personale**

2. Selezionare il **pulsante Aggiungi** personale.

3. Quando si aggiunge personale all'interno dell'organizzazione, digitarne il nome nel campo Aggiungi persone e selezionarlo quando vengono visualizzati nel menu a discesa.  Gli altri campi verranno compilati automaticamente.

    Dopo aver aggiunto un membro del personale, è possibile modificare il nome visualizzato in tutte le comunicazioni di Bookings selezionando la **x** accanto al nome e modificando il campo Aggiungi **utenti.** Ciò può essere utile se si desidera che i membri del personale possano visualizzare un titolo o un nome specifico per i clienti, ad esempio la presentazione di Adele Vance come "Dr. Vance, MD".

4. Per aggiungere personale esterno all'organizzazione, inserire manualmente la posta elettronica e altre informazioni.

    > [!NOTE]
    > Il personale esterno al tenant non sarà in grado di condividere le informazioni sulla disponibilità con Bookings.

5. Per ogni membro del personale, selezionare un ruolo: Amministratore, Visualizzatore o Guest.
    - **Gli** amministratori possono modificare tutte le impostazioni, aggiungere e rimuovere personale e creare, modificare o eliminare prenotazioni.
    - **I** visualizzatori possono visualizzare tutte le prenotazioni nel calendario, ma non possono modificarle o eliminarle. Hanno accesso in sola lettura alle impostazioni.
    - **Gli** utenti guest possono essere assegnati alle prenotazioni, ma non possono aprire la cassetta postale di prenotazione.

6. Selezionare **Notifica a tutto il personale tramite posta elettronica quando viene** creata o modificata una prenotazione assegnata per abilitare i messaggi di posta elettronica del personale. Di seguito è riportato un messaggio di posta elettronica di esempio:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un messaggio di posta elettronica di notifica da Bookings":::

7. Selezionare Gli eventi nel calendario di **Office 365** influiscono sulla disponibilità se si desidera che le informazioni sulla disponibilità dei calendari dei membri del personale influiscano sulla disponibilità dei servizi di prenotazione tramite Bookings.

    Ad esempio, se un membro del personale ha una riunione del team o un appuntamento personale programmato per le 15 di mercoledì, Bookings mostrerà che il membro del personale non sarà disponibile per essere prenotato in tale intervallo di tempo. Tale orario verrà visualizzato come occupato o provvisorio nella visualizzazione Calendario di Bookings, come illustrato nell'esempio seguente.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Visualizzazione di un calendario di Bookings":::

> [!IMPORTANT]
> È consigliabile lasciare attivata questa impostazione (attivata per impostazione predefinita) per evitare doppie prenotazioni e ottimizzare la disponibilità dei membri del personale.

8. Selezionare **Usa orario di** ufficio per impostare tutti gli orari prenotabili per i  membri del personale in modo che siano solo entro l'orario di ufficio impostato nella sezione Orario di ufficio della pagina Informazioni aziendali.

    Deselezionando questa casella, al personale possono essere date ore personalizzate che limitano ulteriormente la prenotazione. Ciò è utile per gli scenari in cui un membro del personale può essere in loco solo il martedì e il mercoledì oppure dedica la mattina per un tipo di appuntamento e il pomeriggi per altri tipi.

    > [!NOTE]
    > Quando si assegnano membri del personale a un servizio, verranno visualizzati solo i primi 31 membri del personale aggiunti alla pagina del personale.
