---
title: Aggiungere personale alle prenotazioni
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Utilizzare questa pagina per creare l'elenco personale e per gestire i dettagli dei membri del personale, quali nome, numero di telefono e indirizzo di posta elettronica.
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419810"
---
# <a name="add-staff-to-bookings"></a>Aggiungere personale alle prenotazioni

La pagina del personale nelle prenotazioni è la posizione in cui è possibile creare l'elenco di personale e gestire i dettagli dei membri del personale, come nome, numero di telefono e indirizzo di posta elettronica. È inoltre possibile impostare l'orario di lavoro per ogni membro del personale da qui.

> [!NOTE]
> La prenotazione è attivata per impostazione predefinita per i clienti che hanno gli abbonamenti Microsoft 365 business standard, Microsoft 365 a3 o Microsoft 365 a5. La prenotazione è disponibile anche per i clienti che dispongono di Office 365 Enterprise E3 e Office 365 Enterprise E5, ma è disattivata per impostazione predefinita. Per iniziare, vedere [accesso a Microsoft bookings](get-access.md). Per abilitare o disabilitare le prenotazioni, vedere [attivazione o disattivazione delle prenotazioni per l'organizzazione](turn-bookings-on-or-off.md).

## <a name="add-staff"></a>Aggiungere personale

Anche se Bookings è una funzionalità di Microsoft 365, non tutti i membri del personale sono tenuti a disporre di un account Microsoft 365. Tutti i membri del personale devono disporre di un indirizzo di posta elettronica valido in modo che possano ricevere prenotazioni e programmare le modifiche.

Guardare questo video o seguire la procedura seguente per aggiungere il proprio personale.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Passare alla [pagina Gestisci personale](https://outlook.office.com/bookings/staff) e selezionare **Aggiungi personale**

2. Selezionare il pulsante **Aggiungi pentagrammi** .

3. Quando si aggiungono personale all'interno del tenant, digitare il proprio nome nel campo **Aggiungi utenti** e selezionarli quando vengono visualizzati nel menu a discesa. Gli altri campi verranno inseriti automaticamente.

    Dopo aver aggiunto un membro del personale, è possibile modificare il nome visualizzato in tutte le comunicazioni di prenotazione selezionando **x** accanto al nome e modificando il campo **Aggiungi utenti** . Questo può essere utile se si desidera che i membri del personale abbiano un titolo o un nome specifico visualizzato per i clienti, ad esempio l'elenco di Adele Vance come "Dr. Vance, MD".

4. Per aggiungere personale dall'esterno del tenant, compilare manualmente la posta elettronica e altre informazioni.

    > [!NOTE]
    > Il personale proveniente dall'esterno del tenant non sarà in grado di condividere le informazioni sulla disponibilità con le prenotazioni.

5. Per ogni membro del personale, selezionare un ruolo: Administrator, Viewer o Guest.
    - Gli **amministratori** possono modificare tutte le impostazioni, aggiungere e rimuovere personale e creare, modificare o eliminare le prenotazioni.
    - Gli **utenti** possono visualizzare tutte le prenotazioni del calendario, ma non possono modificarle o eliminarle. Dispongono dell'accesso in sola lettura alle impostazioni.
    - **Gli ospiti** possono essere assegnati a prenotazioni, ma non possono aprire la cassetta postale di prenotazione.

6. Seleziona **notifica a tutto il personale tramite posta elettronica quando viene creata o modificata una prenotazione** , per abilitare i messaggi di posta elettronica del personale. Di seguito è riportato un messaggio di posta elettronica di esempio:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un messaggio di posta elettronica di notifica da bookings":::

7. Selezionare **gli eventi nel calendario di Office 365 influire sulla disponibilità** se si desidera che le informazioni sulla disponibilità da calendari dei membri del personale siano influire sulla disponibilità dei servizi di prenotazione tramite prenotazioni.

    Ad esempio, se un membro del personale ha una riunione del team o un appuntamento personale programmato per le 15.00 di mercoledì, la prenotazione mostrerà che il membro del personale non è disponibile per essere prenotato in questo intervallo di tempo. Tale tempo verrà visualizzato come occupato o provvisorio nella visualizzazione calendario delle prenotazioni, come illustrato nell'esempio seguente.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Visualizzazione del calendario delle prenotazioni":::

> [!IMPORTANT]
> È consigliabile lasciare questa impostazione su (è attivata per impostazione predefinita) per evitare il doppio-bookings e per ottimizzare la disponibilità dei membri del personale.

8. Selezionare **Usa orario di ufficio** per impostare tutti i tempi prenotabili per i membri del personale solo entro gli orari di ufficio impostati nella sezione **orario di ufficio** nella pagina informazioni business.

    Deselezionando questa casella, al personale possono essere assegnati orari personalizzati che possono essere prenotati ulteriormente. Ciò è utile per gli scenari in cui un membro del personale può essere presente solo nel sito martedì e mercoledì oppure dedicare le proprie mattine a un tipo di appuntamenti e ai pomeriggi per gli altri tipi.