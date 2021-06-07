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
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768946"
---
# <a name="add-staff-to-bookings"></a>Aggiungere personale a Bookings

La pagina Personale in Bookings consente di creare l'elenco di personale e gestire i dettagli dei membri del personale, ad esempio nome, numero di telefono e indirizzo di posta elettronica. Da qui è anche possibile impostare l'orario di lavoro per ogni membro del personale.

## <a name="before-you-begin"></a>Prima di iniziare

Sebbene Bookings sia una funzionalità di Microsoft 365, non tutti i membri del personale devono disporre di un account Microsoft 365 personale. Tutti i membri del personale devono avere un indirizzo di posta elettronica valido per poter ricevere prenotazioni e pianificare le modifiche.

## <a name="watch-add-your-staff-to-bookings"></a>Watch: Add your staff to Bookings

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

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Impostare un utente di Bookings come utente con privilegi super senza aggiungerli come personale in Bookings

Potresti voler aggiungere una persona all'elenco del personale in Bookings senza renderla disponibile per i clienti o i clienti. Dopo essere diventato un utente con privilegi di amministratore, diventerà un amministratore della cassetta postale di prenotazione. Essere un amministratore di una cassetta postale di prenotazione è definito come disporre di autorizzazioni di accesso completo e di invio come per la cassetta postale di prenotazione.

> [!NOTE]
> Questi passaggi funzionano solo se all'utente aggiunto non è già assegnato **un** ruolo visualizzatore in Bookings.

1. [Connessione per Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Usando PowerShell, assegnare l'accesso completo con i comandi seguenti:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Eseguire quindi questo comando per assegnare le autorizzazioni send-as.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Ecco un esempio di comando di PowerShell per aggiungere Allie Bellew alla cassetta postale di prenotazione dell'assistenza all'infanzia di Contoso.

1. Eseguire innanzitutto questo comando:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. Eseguire quindi questo comando:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** ora ha accesso come amministratore, ma non viene visualizzato come personale prenotabile in Bookings.
