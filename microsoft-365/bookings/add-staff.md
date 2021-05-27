---
title: Aggiungere personale a Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Utilizzare questa pagina per creare l'elenco del personale e per gestire i dettagli dei membri del personale, ad esempio nome, numero di telefono e indirizzo di posta elettronica.
ms.openlocfilehash: 7fd19e3281b3dc075b5f72ca0471f5c66f93752d
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683320"
---
# <a name="add-staff-to-bookings"></a>Aggiungere personale a Bookings

La pagina Personale in Bookings consente di creare l'elenco di personale e gestire i dettagli dei membri del personale, ad esempio nome, numero di telefono e indirizzo di posta elettronica. Da qui è anche possibile impostare l'orario di lavoro per ogni membro del personale.

## <a name="before-you-begin"></a>Informazioni preliminari

Sebbene Bookings sia una funzionalità di Microsoft 365, non tutti i membri del personale devono disporre di un account Microsoft 365 personale. Tutti i membri del personale devono avere un indirizzo di posta elettronica valido per poter ricevere prenotazioni e pianificare le modifiche.

## <a name="watch-add-your-staff-in-microsoft-bookings"></a>Watch: Add your staff in Microsoft Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Passaggi

1. Vai alla pagina [Gestisci personale e](https://outlook.office.com/bookings/staff) seleziona Aggiungi **personale**

2. Seleziona il **pulsante Aggiungi** staff.

3. Quando si aggiunge personale all'interno dell'organizzazione, digitarne il nome nel campo **Aggiungi** persone e selezionarli quando vengono visualizzati nel menu a discesa. Gli altri campi verranno compilati automaticamente.

    Una volta aggiunto un membro del personale, è possibile modificare il nome visualizzato in tutte le comunicazioni di Bookings selezionando la **x** accanto al nome e modificando il **campo Aggiungi** persone. Ciò può essere utile se si desidera che ai membri del personale sia visualizzato un titolo o un nome specifico per i clienti, ad esempio la presentazione di Adele Vance come "Dr. Vance, MD".

4. Per aggiungere personale esterno all'organizzazione, compilare manualmente la posta elettronica e altre informazioni.

    > [!NOTE]
    > Il personale esterno al tenant non sarà in grado di condividere le informazioni sulla disponibilità con Bookings.

5. Per ogni membro del personale, selezionare un ruolo: Amministratore, Visualizzatore o Guest.
    - **Gli** amministratori possono modificare tutte le impostazioni, aggiungere e rimuovere personale e creare, modificare o eliminare prenotazioni.
    - **I** visualizzatori possono visualizzare tutte le prenotazioni nel calendario, ma non possono modificarle o eliminarle. Hanno accesso in sola lettura alle impostazioni.
    - **Gli** utenti guest possono essere assegnati alle prenotazioni, ma non possono aprire la cassetta postale di prenotazione.

6. Selezionare **Notifica a tutto il personale tramite posta elettronica quando viene** creata o modificata una prenotazione a loro assegnata per abilitare i messaggi di posta elettronica del personale. Di seguito è riportato un messaggio di posta elettronica di esempio:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Un messaggio di posta elettronica di notifica da Bookings":::

7. Selezionare **Eventi nel Office 365** influiscono sulla disponibilità se si desidera che le informazioni sulla disponibilità dei calendari dei membri del personale influiscano sulla disponibilità dei servizi di prenotazione tramite Bookings.

    Ad esempio, se un membro del personale ha una riunione del team o un appuntamento personale programmato per le 15 di mercoledì, Bookings mostrerà che il membro del personale non è disponibile per essere prenotato in tale intervallo di tempo. Tale ora verrà visualizzata come occupata o provvisoria nella visualizzazione Calendario di Bookings, come illustrato nell'esempio seguente.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Visualizzazione di un calendario di Bookings":::

> [!IMPORTANT]
> È consigliabile lasciare questa impostazione attivata (attivata per impostazione predefinita) per evitare prenotazioni doppie e ottimizzare la disponibilità dei membri del personale.

8. Selezionare **Usa orario di** ufficio per impostare tutti gli orari prenotabili per i membri del personale solo entro l'orario di ufficio impostato nella sezione **Orario** di ufficio della pagina Informazioni aziendali.

    Deselezionando questa casella, al personale possono essere date ore personalizzate che limitano ulteriormente la prenotazione. Ciò è utile per gli scenari in cui un membro del personale può essere presente solo il martedì e il mercoledì del sito oppure dedica le proprie mattine per un tipo di appuntamento e i pomeriggi per altri tipi.

    > [!NOTE]
    > Solo i primi 31 membri del personale aggiunti alla pagina del personale verranno visualizzati quando si assegnano membri del personale a un servizio.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver aggiunto i membri del personale, è possibile pianificare [le chiusure](schedule-closures-time-off-vacation.md) aziendali e i tempi di inazione e [impostare i criteri di pianificazione.](set-scheduling-policies.md)

## <a name="related-content"></a>Contenuto correlato

[Microsoft Bookings](bookings-overview.md)

[Pianificare chiusure aziendali, permessi e ferie](schedule-closures-time-off-vacation.md)

[Impostare i criteri di pianificazione](set-scheduling-policies.md)
