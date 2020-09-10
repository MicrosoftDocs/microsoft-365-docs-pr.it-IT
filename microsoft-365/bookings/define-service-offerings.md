---
title: Definire le offerte di servizi nelle prenotazioni
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Istruzioni per immettere informazioni sulle offerte di servizi, tra cui nome del servizio, descrizione, posizione, durata e prezzi. È anche possibile contrassegnare i dipendenti qualificati per fornire il servizio.
ms.openlocfilehash: 60b77633b9845b3c269f6773c1fb8a26256fbdc5
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419779"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definire le offerte di servizi nelle prenotazioni

Quando si definiscono le offerte di servizi in Microsoft bookings, è possibile impostare un nome di servizio, una descrizione, un percorso (scegliere se si desidera incontrare di persona o una riunione online), la durata, i promemoria predefiniti per i clienti e il personale, le note interne relative al servizio e i prezzi. È anche possibile contrassegnare i dipendenti qualificati per fornire il servizio. Successivamente, quando i clienti giungono al sito Web aziendale per prenotare un appuntamento, possono vedere esattamente quali tipi di appuntamenti sono disponibili, scegliere la persona che vuole fornire il servizio e quanto costerà il servizio.

È inoltre possibile aggiungere informazioni e URL personalizzati alla conferma di posta elettronica e ai promemoria inviati quando un utente Prenota un servizio tramite la pagina di prenotazione.

> [!NOTE]
> La prenotazione è attivata per impostazione predefinita per i clienti che hanno gli abbonamenti Microsoft 365 business standard, Microsoft 365 a3 o Microsoft 365 a5. La prenotazione è disponibile anche per i clienti che dispongono di Office 365 Enterprise E3 e Office 365 Enterprise E5, ma è disattivata per impostazione predefinita. Per iniziare, vedere [accesso a Microsoft bookings](get-access.md). Per abilitare o disabilitare le prenotazioni, vedere [attivazione o disattivazione delle prenotazioni per l'organizzazione](turn-bookings-on-or-off.md).

## <a name="create-the-service-details"></a>Creare i dettagli del servizio

1. Passare alla [pagina Gestisci servizi](https://outlook.office.com/bookings/services) e selezionare **Aggiungi un servizio**.

2. **Nome servizio**: immettere il nome del servizio. Questo è il nome che verrà visualizzato nel menu a discesa della pagina del calendario. Questo nome verrà visualizzato anche quando un utente aggiunge manualmente un appuntamento nella pagina del calendario e verrà visualizzato come riquadro nella pagina self-service.

3. **Descrizione**: la descrizione immessa è ciò che verrà visualizzato quando un utente fa clic sull'icona informazioni nella pagina self-service.

4. **Percorso predefinito**: questo percorso è quello che verrà visualizzato nei messaggi di conferma e di sollecito per il personale e per i clienti e verrà visualizzato nell'evento calendario creato per la prenotazione.

5. **Aggiungere una riunione online**: questa impostazione consente di abilitare o disabilitare le riunioni online per ogni appuntamento, tramite team o Skype, a seconda di quale si configura come client predefinito per il membro del personale.

    - Abilitato

        - Un collegamento a un team o a una riunione Skype, univoco per la prenotazione, verrà aggiunto all'evento del calendario sia nei calendari del personale che dei clienti, insieme alle informazioni di accesso esterno.
        - Il collegamento a partecipare alla riunione verrà aggiunto a tutti i messaggi di conferma e di sollecito, come illustrato nell'esempio seguente:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Esempio di collegamento a join teams meeting in bookings":::

        > [!NOTE]
        > Le riunioni di team possono essere unite tramite l'app teams mobile, l'app desktop teams, in un Web browser o tramite la chiamata telefonica. È consigliabile abilitare i team come servizio di riunione online predefinito per il tenant, per offrire agli appuntamenti virtuali la migliore esperienza di prenotazione.

    - Disabili
        - Gli appuntamenti non conterranno un'opzione di riunione e tutti i campi relativi alla riunione visualizzati quando è abilitata l' **aggiunta di riunioni online** non verranno visualizzati.

6. **Durata predefinita**: questo è il periodo di tempo in cui verranno prenotate tutte le riunioni. L'ora è bloccata a partire dall'ora di inizio, selezionata durante la prenotazione. L'orario di appuntamento completo verrà bloccato nei calendari del personale.

7. **Tempo di buffer il cliente non**è in grado di prenotare: l'abilitazione di questa impostazione consente l'aggiunta di tempo supplementare al calendario del personale ogni volta che viene prenotato un appuntamento.

    L'ora sarà bloccata sul calendario del personale e sulle informazioni sulla disponibilità dell'impatto. Questo significa che se un appuntamento termina alle 3:00 e 10 minuti di tempo di buffer è stato aggiunto alla fine della riunione, il calendario del personale verrà visualizzato come occupato e non prenotabile fino a 3:22. Questo può essere utile se il personale ha bisogno di tempo prima che una riunione venga preparata, ad esempio un medico che esamina il grafico di un paziente o un consulente finanziario per la preparazione di informazioni rilevanti sull'account. Può essere utile anche dopo una riunione, ad esempio quando qualcuno ha bisogno di tempo per viaggiare in un'altra posizione.

8. **Consentire al cliente di gestire la propria prenotazione**: questa impostazione determina se il cliente può modificare o annullare la prenotazione, purché sia stata prenotata tramite la scheda calendario nell'app Web bookings.

    - Abilitato

        Il pulsante **Gestisci prenotazione** viene visualizzato nel messaggio di posta elettronica di conferma del cliente. Quando il cliente seleziona questo pulsante, vengono visualizzate tre opzioni:
        - **Riprogrammazione** Selezionando questa opzione, l'utente viene portato a una pagina Self-Service specifica del servizio, in cui è possibile selezionare una nuova data e ora per lo stesso servizio e lo stesso membro del personale dalla prenotazione originale. Si noti che, anche se il membro del personale originale è collegato alla prenotazione ripianificata per impostazione predefinita, l'utente ha la possibilità di cambiare anche il membro del personale.
        - **Annullamento della prenotazione** La prenotazione viene annullata e rimossa dal calendario del personale.
        - **Nuova prenotazione** Questa opzione consente di portare l'utente alla pagina self-service con tutti i servizi e i membri del personale elencati, per la pianificazione di una nuova prenotazione.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Il pulsante Gestisci prenotazioni nelle prenotazioni":::

        È consigliabile lasciare questa impostazione abilitata solo se si ha dimestichezza con i clienti che accedono alla pagina self-service.

    - Disabili

        L'utente non sarà in grado di riprogrammare o annullare la prenotazione quando prenoterà tramite la scheda calendario nell'app Web bookings. Quando si prenota tramite la pagina self-service, tuttavia, i clienti avranno comunque il pulsante **Gestisci prenotazione** e tutte le relative opzioni, anche se questa impostazione è disattivata.

        Se si desidera limitare l'accesso alla pagina self-service, è consigliabile disabilitare questa impostazione. Inoltre, si consiglia di aggiungere testo ai messaggi di conferma e di sollecito che indicano ai clienti come apportare modifiche alla propria prenotazione tramite altri strumenti, ad esempio chiamando l'ufficio o inviando una e-mail all'help desk.

9. **Numero massimo di partecipanti per evento** Questa impostazione consente di creare servizi che richiedono la possibilità per più utenti di prenotare lo stesso tempo di appuntamento e lo stesso personale (ad esempio, una classe di fitness). L'intervallo di tempo di appuntamento per il servizio selezionato, il personale e l'ora saranno disponibili per la prenotazione fino a quando non è stato raggiunto il numero massimo di partecipanti specificato dall'utente. La capacità di appuntamento corrente e i partecipanti possono essere visualizzati nella scheda calendario dell'app Web bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Esempio di impostazione dei partecipanti massimi nelle prenotazioni":::

10. **Prezzo predefinito**  Questo è il prezzo che verrà visualizzato nella pagina self-service. Se il **prezzo non impostato** è selezionato, non verrà visualizzato alcun prezzo o riferimento ai costi o ai prezzi.

11. **Note** Questo campo viene visualizzato nell'evento Booking per il personale prenotato, nonché sull'evento che viene visualizzato nella scheda calendario dell'app Web bookings.

12. **Campi personalizzati** Questa sezione consente di aggiungere o rimuovere domande, se il cliente deve rispondere a qualsiasi operazione per poter prenotare correttamente.

    - I messaggi di posta elettronica, il numero di telefono, l'indirizzo e le note del cliente sono campi non rimovibili, ma è possibile renderli facoltativi deselezionando **required** accanto a ogni campo.

    - È possibile aggiungere una domanda di risposta a più opzioni o di testo selezionando **Aggiungi una domanda**.

        I campi personalizzati possono essere utili quando si raccolgono informazioni necessarie ogni volta che viene prenotato l'appuntamento specifico. Tra gli esempi sono inclusi i provider di assicurazioni prima di una visita clinica, tipo di prestito per consulenze di prestito, maggiore di studio per consulenza accademica o ID candidato per interviste ai candidati.

13. **Promemoria e conferme** Entrambi i tipi di messaggi di posta elettronica vengono inviati ai clienti, ai membri del personale o a entrambi, a un determinato periodo di tempo prima dell'appuntamento. È possibile creare più messaggi per ogni appuntamento, in base alle proprie preferenze.

    - I messaggi di posta elettronica di conferma e di sollecito predefiniti includono informazioni di base sull'appuntamento, ad esempio il nome del cliente/cliente, il nome del membro del personale, il servizio o l'appuntamento prenotato e l'ora dell'appuntamento. Per le riunioni online, verrà incluso anche un collegamento al join. La possibilità di gestire la prenotazione può anche essere inclusa, se questa impostazione è abilitata, come descritto in sopra nel passaggio 8.

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Un messaggio di posta elettronica di conferma da bookings":::

    - Facoltativamente, è possibile includere qualsiasi altro testo che si desidera qui, ad esempio le informazioni sulla ripianificazione o i clienti che dovrebbero portare all'appuntamento. Di seguito è riportato un esempio di testo personalizzato aggiunto al messaggio di posta elettronica di conferma originale, visualizzato nel campo **informazioni aggiuntive per la conferma della posta elettronica** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Ulteriori informazioni in un messaggio di posta elettronica di prenotazione":::

14. **Abilitare le notifiche dei messaggi di testo per il cliente** Se si seleziona questa opzione, i messaggi SMS vengono inviati al cliente, ma solo se sono stati scelti come opt-in.

    - Casella opt-in della pagina di prenotazione manuale e del servizio self-service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="La casella di opt-in in bookings":::

    - Le notifiche dei messaggi di testo avranno l'aspetto seguente (si noti che le notifiche SMS sono attualmente disponibili solo in Nord America):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notifica di testo da bookings":::

15. **Opzioni di pubblicazione** Scegliere se il servizio deve essere visualizzato come prenotabile nella pagina self-service oppure per rendere il servizio prenotabile solo nella scheda calendario all'interno dell'applicazione Web bookings.

16. **Criteri di pianificazione** Questa impostazione determina il modo in cui vengono visualizzati i tempi di appuntamento e il periodo di tempo in cui le prenotazioni possono essere effettuate o annullate.

17. **Notifiche tramite posta elettronica** Consente di impostare quando i messaggi di posta elettronica vengono inviati al personale dell'organizzazione e ai clienti o clienti.

18. **Personale** La selezione di questa casella di controllo consente ai clienti o ai client di scegliere un determinato membro del personale per l'appuntamento.

    - Abilitato

        I clienti possono scegliere tra tutti i membri del personale assegnati all'appuntamento al momento della prenotazione sulla pagina self-service. Se si seleziona l'opzione di **tutti gli utenti** , è possibile scegliere un membro del personale disponibile in modo casuale per assegnare l'appuntamento.

    - Disabili

        La prenotazione dei clienti tramite la pagina self-service è in grado di selezionare un servizio e una data e un'ora. Il personale disponibile sarà prenotato a caso. Si noti che il personale specifico può ancora essere selezionato se prenotato tramite la scheda calendario nell'app Web bookings.

19. **Disponibilità** Le opzioni seguenti determinano quando il servizio può essere prenotato:

    - **Prenotabile quando il personale è libero** Il servizio gestisce la disponibilità in base al momento in cui il personale è libero all'interno dell'orario di ufficio, senza restrizioni temporali aggiuntive.

    - **Orari personalizzati (periodico settimanale)** Il servizio dispone di un ulteriore livello di disponibilità che può essere ulteriormente limitato (oltre a limitare l'orario di ufficio o l'orario del personale). Utilizzare questa opzione se il servizio può essere fornito o eseguito solo in un momento specifico.

    - **Impostare una disponibilità diversa per un intervallo di date** Questa impostazione incide sulla disponibilità in un determinato momento, anziché su una base ricorrente. È possibile, ad esempio, essere utilizzato quando un computer necessario per il servizio viene temporaneamente gestito e non disponibile oppure quando un'organizzazione viene chiusa per una festività.

20. **Assegnazione del personale** Selezionare il pentagramma (purché siano stati aggiunti membri del personale alla scheda personale) che saranno prenotabili per il servizio specifico. Se si seleziona nessun singolo personale, tutto il personale viene assegnato al servizio.