---
title: Definire le offerte di servizio in Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Istruzioni per l'immissione di informazioni sulle offerte di servizio, tra cui nome del servizio, descrizione, posizione, durata e prezzi. È anche possibile contrassegnare i dipendenti qualificati per fornire il servizio.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962538"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definire le offerte di servizio in Bookings

Quando definisci le offerte di servizio in Microsoft Bookings, imposta un nome del servizio, una descrizione, una posizione (scegli se vuoi incontrare di persona o avere una riunione online), durata, promemoria predefiniti per clienti e personale, note interne sul servizio e prezzi. È anche possibile contrassegnare i dipendenti qualificati per fornire il servizio. Quindi, quando i clienti visitano il sito Web dell'azienda per prenotare un appuntamento, possono vedere esattamente quali tipi di appuntamenti sono disponibili, scegliere la persona che desidera fornire il servizio e quanto costerà il servizio.

È inoltre possibile aggiungere informazioni e URL personalizzati alla conferma e ai promemoria di posta elettronica inviati quando un utente prenota un servizio tramite la pagina di prenotazione.

## <a name="create-the-service-details"></a>Creare i dettagli del servizio

1. Passare alla [pagina Gestisci servizi e](https://outlook.office.com/bookings/services) selezionare Aggiungi un **servizio.**

2. **Nome servizio**: immettere il nome del servizio. Questo è il nome che verrà visualizzato nel menu a discesa nella pagina Calendario. Questo nome verrà visualizzato anche quando qualcuno aggiunge manualmente un appuntamento nella pagina Calendario e verrà visualizzato come riquadro nella pagina Self-service.

3. **Descrizione:** la descrizione immessa è quella che verrà visualizzata quando un utente fa clic sull'icona delle informazioni nella pagina Self-service.

4. **Posizione predefinita:** questa posizione verrà visualizzata nei messaggi di posta elettronica di conferma e promemoria sia per il personale che per i clienti e verrà visualizzata nell'evento di calendario creato per la prenotazione.

5. **Aggiungi riunione online**: questa impostazione consente di abilitare o disabilitare le riunioni online per ogni appuntamento, tramite Teams o Skype, a seconda di quale viene configurato come client predefinito per il membro del personale.

    - Abilitato:

        - Un collegamento a una riunione di Teams o Skype, univoco per la prenotazione, verrà aggiunto all'evento di calendario nei calendari del personale e dei clienti, insieme alle informazioni di accesso esterno.
        - Il collegamento per partecipare alla riunione verrà aggiunto a tutti i messaggi di conferma e promemoria, come illustrato nell'esempio seguente:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Esempio di collegamento per partecipare Teams riunione in Bookings":::

        > [!NOTE]
        > Teams riunioni possono essere unite tramite l'app Teams per dispositivi mobili, l'app desktop Teams, in un Web browser o tramite l'accesso telefonico. È consigliabile abilitare Teams come servizio di riunione online predefinito per il tenant, per la migliore esperienza di prenotazione degli appuntamenti virtuali.

    - Disabilitato:
        - Gli appuntamenti non conterranno un'opzione di riunione e tutti i campi correlati alla riunione visualizzati quando è abilitato l'opzione Aggiungi riunione **online** non verranno visualizzati.

6. **Durata predefinita:** specifica per quanto tempo verranno prenotate tutte le riunioni. L'ora viene bloccata a partire dall'ora di inizio, che viene selezionata durante la prenotazione. L'orario dell'appuntamento completo verrà bloccato nei calendari del personale.

7. **Buffer time your customer can't book**: L'abilitazione di questa impostazione consente l'aggiunta di tempo aggiuntivo al calendario del personale ogni volta che viene prenotato un appuntamento.

    Il tempo verrà bloccato nel calendario del personale e avrà un impatto sulle informazioni sulla disponibilità. Ciò significa che se un appuntamento termina alle 15.00 e sono stati aggiunti 10 minuti di tempo buffer alla fine della riunione, il calendario del personale verrà visualizzato come occupato e non prenotabile fino alle 15.10. Ciò può essere utile se il personale ha bisogno di tempo prima di una riunione per prepararsi, ad esempio un medico che esamina il grafico di un paziente o un consulente finanziario che prepara le informazioni rilevanti sull'account. Può essere utile anche dopo una riunione, ad esempio quando qualcuno ha bisogno di tempo per recarsi in un'altra posizione.

8. **Consenti al cliente di** gestire la prenotazione: questa impostazione determina se il cliente può modificare o annullare la prenotazione, purché sia stata prenotata tramite la scheda Calendario dell'app Web Bookings.

    - Abilitato:

        Il **pulsante Gestisci prenotazione** viene visualizzato nel messaggio di posta elettronica di conferma del cliente. Quando questo pulsante viene selezionato dal cliente, vengono visualizzate tre opzioni:
        - **Ripianificare** Selezionando questa opzione, l'utente viene visualizzata una pagina di Self-Service specifica del servizio, in cui è possibile selezionare una nuova ora e/o una nuova data per lo stesso servizio e per lo stesso membro del personale dalla prenotazione originale. Tieni presente che, anche se il membro del personale originale è collegato alla prenotazione riprogrammata per impostazione predefinita, l'utente ha la possibilità di modificare anche il membro del personale.
        - **Annullare la prenotazione** In questo modo la prenotazione viene annullata e rimossa dal calendario del personale.
        - **Nuova prenotazione** Questa opzione consente all'utente di accedere alla Self-Service con tutti i servizi e il personale elencati, per pianificare una nuova prenotazione.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Pulsante Gestisci prenotazioni in Bookings":::

        È consigliabile lasciare abilitata questa impostazione solo se si ha familiarità con i clienti che accedono alla Self-Service pagina.

    - Disabilitato:

        L'utente non avrà la possibilità di riprogrammare o annullare la prenotazione quando prenota tramite la scheda Calendario dell'app Web Bookings. Durante la prenotazione tramite Self-Service, tuttavia, i  clienti avranno ancora il pulsante Gestisci prenotazione e tutte le relative opzioni, anche quando questa impostazione è disabilitata.

        È consigliabile disabilitare questa impostazione se si desidera limitare l'accesso alla Self-Service pagina. Inoltre, consigliamo di aggiungere testo ai messaggi di posta elettronica di conferma e promemoria che indicano ai clienti come apportare modifiche alla loro prenotazione tramite altri mezzi, ad esempio chiamando l'ufficio o inviando un'e-mail all'help desk.

9. **Numero massimo di partecipanti per evento** Questa impostazione consente di creare servizi che richiedono la possibilità per più persone di prenotare lo stesso appuntamento e lo stesso personale (ad esempio una classe di fitness). L'intervallo di tempo dell'appuntamento per il servizio, il personale e l'ora selezionati sarà disponibile per la prenotazione fino a quando non viene raggiunto il numero massimo di partecipanti specificato dall'utente. La capacità dell'appuntamento corrente e i partecipanti possono essere visualizzati nella scheda Calendario dell'app Web Prenotazioni.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Esempio di impostazione del numero massimo di partecipanti in Bookings":::

10. **Prezzo predefinito**  Questo è il prezzo che verrà visualizzato nella Self-Service pagina. Se **l'opzione Prezzo** non impostato è selezionata, non verrà visualizzato alcun prezzo o riferimento a costi o prezzi.

11. **Note** Questo campo viene visualizzato nell'evento di prenotazione per il personale prenotato e nell'evento visualizzato nella scheda Calendario dell'app Web Prenotazioni.

12. **Campi personalizzati** Questa sezione consente di aggiungere o rimuovere domande se il cliente deve rispondere a qualsiasi domanda per prenotare correttamente.

    - L'indirizzo di posta elettronica, il numero di telefono, l'indirizzo e le note del cliente sono campi non rimovibili, ma è possibile renderli facoltativi deselezionando **Obbligatorio** accanto a ogni campo.

    - È possibile aggiungere una domanda a scelta multipla o una risposta di testo selezionando **Aggiungi una domanda.**

        I campi personalizzati possono essere utili quando si raccolgono informazioni necessarie ogni volta che viene prenotato un appuntamento specifico. Alcuni esempi includono il provider di assicurazioni prima di una visita in una clinica, il tipo di prestito per le consultazioni sui mutui, il maggiore di studio per la consulenza accademica o l'ID candidato per i colloqui candidati.

13. **Promemoria e conferme** Entrambi i tipi di messaggi di posta elettronica vengono inviati a clienti, membri del personale o entrambi, in un periodo di tempo specificato prima dell'appuntamento. È possibile creare più messaggi per ogni appuntamento, in base alle proprie preferenze.

    - I messaggi di posta elettronica di conferma e promemoria predefiniti includono informazioni di base sull'appuntamento, ad esempio il nome del cliente/cliente, il nome del membro del personale, il servizio o l'appuntamento prenotato e l'ora dell'appuntamento. Per le riunioni online, verrà incluso anche un collegamento per partecipare. La possibilità di gestire la prenotazione può essere inclusa anche se questa impostazione è abilitata (come descritto in precedenza nel passaggio 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Un'e-mail di conferma da Bookings":::

    - Facoltativamente, è possibile includere qualsiasi testo aggiuntivo che si desidera qui, ad esempio informazioni sulla riprogrammazione o su cosa i clienti devono portare per l'appuntamento. Di seguito è riportato un esempio di testo personalizzato aggiunto all'e-mail di conferma originale, visualizzato nel **campo Ulteriori informazioni per la** conferma della posta elettronica:

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Informazioni aggiuntive in un messaggio di posta elettronica di Bookings":::

14. **Abilitare le notifiche tramite SMS per il cliente** Se selezionata, SMS messaggi vengono inviati al cliente, ma solo se acconsente esplicitamente.

    - Casella di consenso esplicito nella pagina di prenotazione Self-Service manuale:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Casella di consenso esplicito in Bookings":::

    - Le notifiche sms saranno simili alle seguenti (si noti che SMS notifiche sono attualmente disponibili solo in Nord America):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Una notifica di testo da Bookings":::

15. **Opzioni di pubblicazione** Scegliere se visualizzare il servizio come prenotabile nella pagina Self-Service oppure rendere il servizio prenotabile solo nella scheda Calendario dell'app Web Bookings.

16. **Criteri di pianificazione** Questa impostazione determina la modalità di visualizzazione degli orari degli appuntamenti e il periodo di tempo in cui le prenotazioni possono essere effettuate o annullate.

17. **Notifiche tramite posta elettronica** Imposta quando i messaggi di posta elettronica vengono inviati al personale dell'organizzazione e ai clienti o ai clienti.

18. **Personale** La selezione di questa casella di controllo consente ai clienti o ai clienti di scegliere un membro del personale specifico per l'appuntamento.

    - Abilitato:

        I clienti possono scegliere tra tutto il personale assegnato all'appuntamento al momento della prenotazione nella Self-Service pagina. Selezionando l'opzione **Chiunque,** Bookings sceglierà casualmente un membro del personale disponibile da assegnare all'appuntamento.

    - Disabilitato:

        I clienti che prenotano tramite Self-Service possono selezionare un servizio e un'ora e una data. Il personale disponibile verrà prenotato a caso. Tieni presente che è comunque possibile selezionare personale specifico al momento della prenotazione tramite la scheda Calendario nell'app Web Bookings.

19. **Disponibilità** Le opzioni seguenti determinano quando è possibile prenotare il servizio:

    - **Prenotabile quando il personale è gratuito** Il servizio mantiene la disponibilità in base al momento in cui il personale è gratuito entro l'orario di ufficio, senza limitazioni di tempo aggiuntivo.

    - **Ore personalizzate (ricorrenti settimanali)** Il servizio ha un ulteriore livello di disponibilità che può essere ulteriormente limitato (oltre a limitarsi in base all'orario di ufficio o al personale). Utilizzare questa opzione quando il servizio può essere fornito o eseguito solo in un momento specifico.

    - **Impostare una disponibilità diversa per un intervallo di date** Questa impostazione influisce sulla disponibilità in un determinato momento, anziché su base ricorrente. Ad esempio, può essere utilizzato quando un computer necessario per il servizio viene temporaneamente utilizzato e non disponibile o quando un'organizzazione viene chiusa per una festività.

20. **Assegnare personale** Selezionare il personale (purché siano stati aggiunti membri del personale alla scheda Personale) che sarà prenotabile per quel servizio specifico. Se si seleziona nessun singolo personale, tutto il personale verrà assegnato al servizio.