---
title: Creare e usare un modello per aggiungere utenti
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: È possibile creare e utilizzare un modello per risparmiare tempo e standardizzare le impostazioni quando si aggiungono più utenti.
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579387"
---
# <a name="create-and-use-a-template-to-add-users"></a>Creare e usare un modello per aggiungere utenti

È possibile creare e utilizzare un modello per risparmiare tempo e standardizzare le impostazioni quando si aggiungono più utenti. I modelli sono particolarmente utili se si dispone di utenti che condividono molte proprietà comuni, come quelli che hanno lo stesso ruolo e lavorano nella stessa posizione e quelli che richiedono lo stesso software. Ad esempio, potrebbe essere presente un team di tecnici del supporto tecnico che lavorano nello stesso ufficio.  

## <a name="create-a-template"></a>Creare un modello

I modelli sono facili da creare è possibile selezionare Utenti Modelli utente e quindi selezionare Aggiungi un modello dall'elenco a discesa oppure aggiungere un nuovo utente e, al termine, sarà possibile salvare la voce come &mdash;   >    >  modello. 

Quando si crea un modello dopo l'aggiunta di un utente, nel modello vengono salvati i valori che si scelgono per le impostazioni seguenti:

- Nome di dominio
- Scelta delle impostazioni delle password: puoi scegliere di creare password o di crearle automaticamente
- Scelta una sola password: è possibile richiedere all'utente di creare una nuova password dopo il primo accesso
- Percorso della licenza
- Scelte di licenza
- Scelte dell'applicazione
- Ruolo
- La maggior parte delle informazioni del profilo, ad esempio **Profilo** processo, **Reparto,** **Office,** **Office telefono** e **indirizzo** 

Le informazioni seguenti sono specifiche dell'utente e non vengono salvate nel modello:

- Nome e cognome
- Nome visualizzato
- Nome utente
- Scelta di inviare la password tramite posta elettronica e a chi viene inviata la password
- Numero di cellulare

Se si sceglie di non immettere informazioni per un'impostazione all'interno di una sezione, tale valore sarà vuoto e tale impostazione non verrà visualizzata nel modello. Ad esempio, se si **lascia** vuota la posizione, quando si rivede il modello e quando si utilizza il modello, **la** posizione non verrà visualizzata affatto. Se si lasciano vuote tutte **le impostazioni** della sezione Profilo, nella sezione **Profilo** verrà visualizzato **Nessuno fornito** nel modello finale.

Quando crei un modello selezionando **l'opzione Aggiungi** un modello, puoi scegliere i valori da completare. Tutto ciò che viene lasciato vuoto verrà visualizzato **come Nessuno fornito** nel modello.

## <a name="use-a-template-to-add-a-user"></a>Usare un modello per aggiungere un utente

Per usare un modello esistente per aggiungere un utente:

1. Nell'interfaccia di amministrazione, selezionare **Utenti**  >  **Utenti attivi**.

2. Selezionare **Modelli utente** e quindi selezionare un modello nell'elenco a discesa. L'elenco conterrà solo i modelli creati, non quelli creati da altri amministratori.

   > [!NOTE]
   > È inoltre possibile utilizzare un modello per aggiungere un utente selezionando Modelli utente Gestisci modelli, selezionando un modello e quindi  >  selezionando **Usa modello.**

3. Seguire la procedura per creare un utente dal modello selezionato.

   > [!NOTE]
   > Se non hai licenze sufficienti per un utente aggiunto e le informazioni di pagamento sono disponibili, tenteremo di acquistare un'altra licenza usando le informazioni di pagamento esistenti. Se le informazioni di pagamento non sono disponibili, l'utente verrà creato come utente senza licenza.

## <a name="manage-templates"></a>Gestire i modelli

È possibile eliminare solo i modelli non più necessari e aggiungerne di nuovi. Per eliminare un modello:

1. Nell'interfaccia di amministrazione, selezionare **Utenti**  >  **Utenti attivi**.

2. Selezionare **Modelli** e quindi **Gestisci modelli nell'elenco** a discesa.

3. Verrà visualizzato un elenco di modelli. È possibile eliminare un modello eseguendo una delle operazioni seguenti:
    - Selezionare uno o più modelli e quindi selezionare **Elimina.** 
    - Selezionare i tre punti a destra del nome del modello e quindi selezionare **Elimina.**
    - Selezionare il nome del modello. Quando i dettagli del modello vengono visualizzati sul lato destro dello schermo, selezionare **Elimina modello.**

## <a name="related-articles"></a>Articoli correlati

[Aggiungere utenti e assegnare licenze contemporaneamente](add-users.md)

[Rimuovere un ex dipendente da Microsoft 365](remove-former-employee.md)
  
