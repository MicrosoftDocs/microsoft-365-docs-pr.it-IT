---
title: Aggiungere domande personalizzate e obbligatorie alla pagina delle prenotazioni
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Se è necessario porre domande ai clienti quando prenotano un appuntamento online, è possibile aggiungere domande personalizzate e domande necessarie alla pagina di prenotazione.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419807"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Aggiungere domande personalizzate e obbligatorie alla pagina delle prenotazioni

Bookings consente di creare domande da porre ai clienti quando prenotano appuntamenti. Consente inoltre di scegliere le domande necessarie.

Le domande vengono associate a un servizio, in modo che ogni servizio possa avere un set di domande diverso. Ad esempio, un hair stylist può chiedere ai clienti che prenotano un appuntamento per la colorazione dei capelli se hanno allergie note a sbianchetti o tinte. Ciò consente a te e ai tuoi clienti di risparmiare tempo quando arrivano per l'appuntamento.

I clienti visualizzano le domande personalizzate quando creano l'appuntamento nella pagina di prenotazione. Il personale visualizzerà le domande personalizzate quando crea una nuova prenotazione dal calendario Prenotazioni o quando visualizza un appuntamento esistente. Bookings salva tutte le domande in un elenco principale in modo che non sia necessario creare di nuovo le stesse domande per ogni servizio. È inoltre possibile scegliere se le domande sono obbligatorie o facoltative.

> [!NOTE]
> Le risposte del cliente alle domande possono essere visibili quando si osserva l'appuntamento nel calendario di prenotazione.

Per ulteriori informazioni su come personalizzare e personalizzare la pagina di prenotazione, vedi [Personalizzare la pagina di prenotazione.](customize-booking-page.md)

## <a name="add-custom-questions-to-your-services"></a>Aggiungere domande personalizzate ai servizi

1. Accedi a Microsoft 365 e vai a **Prenotazioni**.

1. Passare a **Servizi** e modificare un servizio esistente o **Aggiungi servizio**.

1. Scorrere verso il basso **fino alla sezione Campi** personalizzati e quindi selezionare **Modifica.**

   Abbiamo già aggiunto alcune domande di base sulle informazioni dei clienti: e-mail del cliente, numero di telefono, indirizzo del cliente e note del cliente. La prima volta che si fa questo, le domande sulle informazioni del cliente vengono evidenziate in grigio. Ciò significa che l'utente riceverà questa domanda. Se si seleziona la domanda, la casella di evidenziazione che la circonda scomparirà e al cliente non verrà chiesta la domanda.

   In questo esempio, il numero di telefono e le note dei clienti sono stati disattivati e sono state create due nuove domande personalizzate da porre.

   ![Immagine della schermata delle domande personalizzate](../media/bookings-questions-custom-fields.png)

1. Per rendere necessaria la domanda, selezionare la **casella di controllo** Obbligatorio. Il cliente non sarà in grado di completare la prenotazione fino a quando non risponderà alle domande necessarie.

1. Per creare una domanda personalizzata, seleziona **Aggiungi una domanda** nella parte superiore del pannello. Scrivi la domanda e quindi seleziona **Salva**.

1. Fare clic sulla domanda per abilitarla. Attorno a essa viene visualizzata una casella evidenziata e la domanda è abilitata.

1. Fare clic su **OK** nella parte superiore della pagina e quindi su Salva **il servizio.**

Bookings salverà tutte le domande personalizzate in un elenco principale in modo da poter aggiungere facilmente domande a ogni servizio senza dover digitare ripetutamente le stesse domande. Ad esempio, se si apre un servizio diverso, la domanda creata per il primo servizio verrà mostrata nella sezione Campi personalizzati, ma sarà disabilitata. Fare clic sulla domanda in modo che sia visualizzato un rettangolo evidenziato e che la domanda sia abilitata.

In questo esempio, è possibile vedere che le domande aggiunte per il primo servizio sono disponibili per questo servizio. Tutte le domande create per questo servizio saranno disponibili per tutti i servizi.

   ![Immagine delle domande visualizzate per più servizi](../media/bookings-questions-services.png)

Se la pagina di prenotazione è già stata pubblicata, non è necessario eseguire altre operazione. I clienti potranno vedere le domande la prossima volta che prenotano con te. Se la pagina di prenotazione non  è ancora stata pubblicata, passare alla pagina di prenotazione da Outlook sul Web e quindi selezionare **Salva e pubblica**.

> [!WARNING]
> È inoltre possibile eliminare le domande dall'elenco principale. Tuttavia, se si elimina una domanda, questa verrà eliminata da ogni servizio. È consigliabile disabilitare la domanda selezionandola per assicurarsi di non influire sugli altri servizi. Puoi vedere che una domanda è disabilitata se non è circondata da un rettangolo evidenziato.

## <a name="customer-experience"></a>Esperienza cliente

Quando i clienti prenotano un appuntamento con te, le domande di base sulle informazioni sui clienti verranno visualizzate nella **sezione Aggiungere i dettagli.** Tutte le domande personalizzate che aggiungi saranno disponibili nella **sezione Fornire ulteriori** informazioni.

![Immagine di ciò che i clienti vedono quando le domande sono abilitate](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Esperienza del personale

Quando i clienti prenotano un appuntamento con te, il personale visualizza le domande e le risposte del cliente nel calendario di prenotazione. Per vederla, passare a **Calendario prenotazioni** e quindi aprire \>  un appuntamento.

![Immagine di ciò che il personale visualizza quando le domande sono abilitate](../media/bookings-questions-staff.png)
