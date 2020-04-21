---
title: Rimuovere un ex dipendente
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Seguire questo elenco di controllo per rimuovere un dipendente da Microsoft 365 e proteggere i dati. '
ms.openlocfilehash: 593460c2e49b7136972c084a9927544e6194cb90
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617123"
---
# <a name="remove-a-former-employee"></a>Rimuovere un ex dipendente
  
## <a name="sign-out-now"></a>Disconnessione immediata

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

Guardare un breve video sulla rimozione di un dipendente. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Per rimuovere un dipendente:

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password**.

3. Immettere una nuova password e quindi fare clic su **Reimposta**. (Non inviarlo a tali messaggi).
    
4. Selezionare il nome dell'utente da passare al riquadro delle proprietà e nella scheda **OneDrive** selezionare **Avvia disconnessione**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare l'utente e quindi selezionare **Reimposta password**.

3. Immettere una nuova password e quindi fare clic su **Reimposta**. (Non inviarlo a tali messaggi).

4. Selezionare di nuovo l'utente, espandere **impostazioni di OneDrive**e quindi fare clic su **Avvia** accanto a **disconnessione**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare l'utente e quindi selezionare **Reimposta password**.

3. Immettere una nuova password e quindi fare clic su **Reimposta**. (Non inviarlo a tali messaggi).

4. Selezionare di nuovo l'utente, espandere **impostazioni di OneDrive**e quindi fare clic su **Avvia** accanto a **disconnessione**.

::: moniker-end

    
Entro un'ora o dopo che hanno lasciato la pagina Microsoft 365 corrente in cui si trovano, verrà richiesto di eseguire nuovamente l'accesso. (Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende da quanto tempo è rimasto su quel token e se si spostano fuori dalla pagina Web corrente).
  
 **AVVERTENZA**: Se l'utente è in Outlook sul Web e fa semplicemente clic all'interno della cassetta postale, potrebbe non essere espulso immediatamente. Non appena si seleziona una tessera diversa, ad esempio OneDrive, oppure si aggiorna il browser, viene avviata la disconnessione. 
  
Per usare PowerShell per disconnettere immediatamente un utente, vedere il cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Per altre informazioni sul tempo necessario per rimuovere un dipendente dalla posta elettronica, vedere [Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Panoramica della procedura completa per rimuovere un dipendente e proteggere i dati
<a name="bkmk_now"> </a>

Una domanda che spesso si ottiene è: "cosa devo fare per proteggere i dati quando un dipendente lascia l'organizzazione?" In questo articolo viene illustrato come bloccare l'accesso a Microsoft 365 e i passaggi da eseguire per garantire la protezione dei dati.
  
> [!NOTE]
> Se si è un amministratore globale, è possibile eliminare il dipendente, inoltrare il proprio indirizzo di posta elettronica, scegliere cosa fare con il proprio contenuto di OneDrive utilizzando la nuova esperienza guidata. Per ulteriori informazioni, vedere [Global Admin: Delete a user](remove-former-employee.md). Tuttavia, è consigliabile completare tutti i passaggi aggiuntivi riportati di seguito per verificare che il dipendente non abbia accesso ai dati della società. 
  
Ecco una rapida panoramica. Ogni passaggio è spiegato in dettaglio in questo articolo.
  
|||
|:-----|:-----|
|**Passaggio** <br/> |**Perché eseguire questa operazione** <br/> |
|1. [Salvare il contenuto della cassetta postale di un ex dipendente](#save-the-contents-of-a-former-employees-mailbox) <br/> |È un'operazione utile per la persona che prenderà il posto del dipendente o in caso di controversie.  <br/> |
|2. [Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirla in una cassetta postale condivisa](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |Consente di mantenere attivo l'indirizzo di posta elettronica dell'ex dipendente. Se i clienti o i partner continuano a inviare la posta elettronica all'indirizzo dell'ex dipendente, questa operazione consente di inoltrare i messaggi alla persona che ne prende il posto.  <br/> |
|3. [Cancellare i dati e bloccare il dispositivo mobile di un ex dipendente](#wipe-and-block-a-former-employees-mobile-device) <br/> |Rimuove i dati aziendali dal telefono o dal tablet.  <br/> |
|4. [bloccare l'accesso di un ex dipendente ai dati di Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Impedisce all'utente di accedere alla vecchia cassetta postale e ai dati di Microsoft 365.  <br/><br/> **Suggerimento**: quando si blocca l'accesso di un utente, si sta ancora pagando la propria licenza. Per interromperlo, è necessario eliminare la licenza dall'abbonamento (passaggio 5).           |
|5. [Spostare il contenuto di OneDrive del dipendente](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Se si rimuove solo la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.  <br/><br/> Prima di eliminare l'account, occorre spostare il contenuto del suo OneDrive in un'altra posizione facilmente accessibile. Dopo aver eliminato l'account di un dipendente, il contenuto del suo OneDrive viene conservato per **30** giorni. Durante questo periodo di tempo, tuttavia, è possibile ripristinare l'account dell'utente e ottenere l'accesso al contenuto del suo OneDrive. Se l'account viene ripristinato, il contenuto di OneDrive resterà accessibile anche dopo i 30 giorni.  <br/> |
|5a. Cosa accade se la persona ha usato il suo computer personale per accedere a OneDrive e SharePoint?  <br/> |Se ha usato un computer personale anziché un computer fornito dalla società per scaricare file da OneDrive e SharePoint, non esiste alcun modo per cancellare i file che vi ha archiviato.  <br/><br/> Continuerà ad accedere a tutti i file che sono stati sincronizzati con il suo computer.  <br/> |
|6. [rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |Quando si rimuove una licenza, è possibile assegnarla a un'altra persona. In alternativa, è possibile eliminare la licenza in modo da interromperne il pagamento finché non si assume un'altra persona.  <br/><br/> Quando si rimuove o si elimina una licenza, la posta elettronica, i contatti e il calendario dell'utente vengono conservati per **30 giorni**, quindi eliminati definitivamente. Se si rimuove o si elimina la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.  <br/> |
|7. [Eliminare l'account utente di un ex dipendente.](#delete-a-former-employees-user-account)<br/> |Questo rimuove l'account dall'interfaccia di amministrazione. Consente di tenere tutto in ordine.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Salvare il contenuto della cassetta postale di un ex dipendente
<a name="bkmk_preserve"> </a>

Il contenuto della cassetta postale dell'ex dipendente può essere salvato in due modi:
  
1. Aggiungere l'indirizzo di posta elettronica dell'ex dipendente alla versione di Outlook 2013 o 2016 e quindi esportare i dati in un file PST. I dati possono essere importati in un altro account di posta elettronica, se necessario. Per informazioni sulla procedura, vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md).
    
    O
    
2. Inserire un blocco per controversia legale o un blocco sul posto nella cassetta postale prima di eliminare l'account utente. È una procedura molto più complessa rispetto alla prima opzione, ma fondamentale se: il piano aziendale include l'archiviazione e il blocco a fini giudiziari, è possibile che si apra una controversia e si ha un reparto IT tecnicamente solido.
    
    Dopo aver convertito la cassetta postale in "cassetta postale inattiva", gli amministratori, i responsabili della conformità o i responsabili della gestione dei record possono usare gli strumenti eDiscovery sul posto in Exchange Online per accedere al contenuto ed eseguire ricerche.
    
    Le cassette postali inattive non possono ricevere posta elettronica e non vengono visualizzate nella rubrica condivisa o in altri elenchi dell'organizzazione.
    
    Per informazioni su come applicare un'esenzione su una cassetta postale, vedere [gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/office365/securitycompliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirla in una cassetta postale condivisa
<a name="bkmk_forward"> </a>

In questo passaggio, l'indirizzo di posta elettronica dell'ex dipendente viene assegnato a un altro dipendente o si [converte la cassetta postale dell'utente in una cassetta postale condivisa](../email/convert-user-mailbox-to-shared-mailbox.md) creata. 
  
- La creazione di una cassetta postale condivisa è la soluzione meno dispendiosa perché non è necessario acquistare una licenza **a condizione che la cassetta postale sia minore di 50 GB**. Se si superano i 50 GB è necessario assegnare una licenza. 
    
- Se si converte la cassetta postale in una cassetta postale condivisa, saranno disponibili anche tutti i vecchi messaggi di posta elettronica. Questa operazione può richiedere molto spazio.
    
- Se si configura l'inoltro della posta elettronica, ora solo i  *nuovi*  messaggi di posta elettronica inviati all'ex dipendente vengono inviati al dipendente corrente. 
    
- L'inoltro della posta elettronica richiede che l'account dell'ex dipendente abbia una licenza.
    
 > [!IMPORTANT] 
 > Se si sta configurando l'inoltro della posta elettronica o una cassetta postale condivisa, alla fine non eliminare l'account dell'ex dipendente. L'account deve restare valido per poter ancorare l'inoltro della posta elettronica o la cassetta postale condivisa. 

::: moniker range="o365-worldwide"  

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera bloccare, quindi selezionare la scheda **posta** .

3. In **inoltro della posta elettronica**, selezionare **Gestisci inoltro della posta elettronica**.

4. Attivare **Inoltra tutta la posta elettronica inviata a questa cassetta postale**. Nella casella **Indirizzo di inoltro** digitare l'indirizzo di posta elettronica del dipendente corrente o della cassetta postale condivisa a cui verranno inviati i messaggi. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.
 
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare ed espandere **impostazioni di posta elettronica**.

3. Accanto a **inoltro della posta elettronica**, selezionare **modifica**.

4. Attivare **Inoltra tutta la posta elettronica inviata a questa cassetta postale**. Nella casella **Indirizzo di inoltro** digitare l'indirizzo di posta elettronica del dipendente corrente o della cassetta postale condivisa a cui verranno inviati i messaggi. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare ed espandere **impostazioni di posta elettronica**.

3. Accanto a **inoltro della posta elettronica**, selezionare **modifica**.

4. Attivare **Inoltra tutta la posta elettronica inviata a questa cassetta postale**. Nella casella **Indirizzo di inoltro** digitare l'indirizzo di posta elettronica del dipendente corrente o della cassetta postale condivisa a cui verranno inviati i messaggi. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Cancellare i dati e bloccare il dispositivo mobile di un ex dipendente
<a name="bkmk_mobile"> </a>

Se l'ex dipendente aveva un telefono aziendale, è possibile usare Office 365 per cancellare i dati e bloccare il dispositivo, in modo che tutti i dati dell'organizzazione vengano rimossi dal dispositivo e quest'ultimo non possa più connettersi all'Interfaccia di amministrazione di Exchange.
  

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

3. Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**. 
    
4. Selezionare l'utente e in **dispositivi mobili**selezionare **Visualizza dettagli**. 
    
5. Nella pagina **Dettagli dispositivo mobile** , in **dispositivi mobili**, selezionare il dispositivo mobile, selezionare **wipe data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), quindi selezionare **blocca**. 
    
6. Selezionare **Salva**. 
    
    **Suggerimento**: assicurarsi di rimuovere o disabilitare l'utente dal servizio Blackberry Enterprise locale. Occorre anche disabilitare gli eventuali dispositivi Blackberry per l'utente. Per informazioni sui passaggi specifici da eseguire per disabilitare l'utente, vedere la guida all'amministrazione di Blackberry Business Cloud Services. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Bloccare l'accesso di un ex dipendente ai dati di Microsoft 365
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Il blocco di un account può richiedere fino a 24 ore. Se è necessario impedire immediatamente l'accesso di un utente, è necessario [reimpostare la password](reset-passwords.md) e quindi avviare un evento di una tantum che li disfirmerà dalle sessioni di Microsoft 365 su tutti i dispositivi. Vedere [Disconnessione immediata](#sign-out-now)
 

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera bloccare e, sotto il nome dell'utente, selezionare il simbolo per bloccare l' **utente**.

3. Selezionare **blocca l'accesso dell'utente**e quindi fare clic su **Salva**. 

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare, quindi selezionare Blocca l' **accesso**.

3. Selezionare **blocca l'accesso dell'utente**e quindi fare clic su **Salva**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare, quindi selezionare Blocca l' **accesso**.

3. Selezionare **blocca l'accesso dell'utente**e quindi fare clic su **Salva**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloccare l'accesso alla posta elettronica (Exchange Online) di un ex dipendente
<a name="bkmk_block_email"> </a>

Se si dispone di posta elettronica come parte dell'abbonamento a Microsoft 365, è necessario eseguire l'accesso all'interfaccia di amministrazione di Exchange per eseguire questa procedura per impedire all'ex dipendente di accedere al proprio indirizzo di posta elettronica.
  

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.
     
2. Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**. 
    
3. Fare doppio clic sull'utente e passare alla pagina **funzionalità delle cassette postali** . In **dispositivi mobili**selezionare **Disattiva Exchange ActiveSync** e **Disabilita OWA per i dispositivi** e rispondere **Sì** a entrambi quando richiesto. 
    
4. In **connettività posta elettronica**, selezionare **Disattiva** e Rispondi **Sì** quando richiesto. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente
<a name="bkmk_remove"> </a>

Pertanto, non continuare a pagare per una licenza dopo che un utente lascia l'organizzazione, è necessario rimuovere la propria licenza Microsoft 365 e quindi eliminarla dall'abbonamento. Se si sceglie di non eliminare la licenza dal proprio abbonamento, è possibile assegnarla a un altro utente.
  
Quando si rimuove la licenza, tutti i dati dell'utente vengono conservati per 30 giorni. È possibile [accedere](get-access-to-and-back-up-a-former-user-s-data.md) ai dati o [ripristinare](restore-user.md) l'account se l'utente ritorna. Dopo 30 giorni, tutti i dati dell'utente (ad eccezione dei documenti archiviati in SharePoint Online) vengono eliminati definitivamente da Microsoft 365 e non possono essere recuperati. 

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera bloccare, quindi selezionare la scheda **licenze e app** .

4. Deselezionare le caselle di controllo relative alle licenze che si desidera rimuovere, quindi selezionare **Salva modifiche**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente da bloccare e quindi fare clic su **modifica**accanto a **licenze di prodotto**.

3. Nella pagina **licenze di prodotto** , disattivare le licenze che si desidera rimuovere, quindi selezionare **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente da bloccare e quindi fare clic su **modifica**accanto a **licenze di prodotto**.

3. Nella pagina **licenze di prodotto** , disattivare le licenze che si desidera rimuovere, quindi selezionare **Salva**.

::: moniker-end


**Per ridurre il numero di licenze pagate** finché non viene assunta un'altra persona, seguire questa procedura: 

::: moniker range="o365-worldwide"



1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prodotti e servizi</a>.


::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.

::: moniker-end
    
2. Selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo che non venga pagata fino a quando non si assume un'altra persona.

Quando si [aggiunge](add-users.md) un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.
    
Per ulteriori informazioni sulla gestione delle licenze utente per Microsoft 365 for business, vedere [assegnare licenze agli utenti in microsoft 365 for business](../manage/assign-licenses-to-users.md)e [rimuovere le licenze dagli utenti in Microsoft 365 for business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Quali effetti hanno gli account dei dipendenti eliminati su Skype for Business?
<a name="bkmk_remove"> </a>

Quando si rimuove una licenza utente da Office 365, il numero chiamata PSTN associato all'utente viene rilasciato e può essere assegnato a un altro utente.
  
Se l'utente appartiene a un gruppo di coda, non sarà più contattato dagli agenti della coda di chiamata. Per questo motivo, si consiglia la rimozione dell'utente anche dai gruppi associati alla coda di chiamata. 
  
## <a name="delete-a-former-employees-user-account"></a>Eliminare l'account utente di un ex dipendente.
<a name="bkmk_delete"> </a>

Dopo il salvataggio e l'accesso ai dati utente dell'ex dipendente, è possibile eliminare l'account corrispondente.
  
Non eliminare l'account se è stato configurato l'inoltro della posta elettronica o se l'account è stato convertito in una cassetta postale condivisa. In entrambi i casi è necessario l'account per ancorare l'inoltro o la cassetta postale condivisa.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera eliminare.

3. Sotto il nome dell'utente, selezionare il simbolo per **eliminare l'utente**. Scegliere le opzioni desiderate per questo utente, quindi selezionare **Elimina utente**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera eliminare.

3. Nella parte superiore della pagina, selezionare **Elimina utente**. Scegliere le opzioni desiderate per questo utente, quindi selezionare **Elimina utente**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera eliminare.

3. Nella parte superiore della pagina, selezionare **Elimina utente**. Scegliere le opzioni desiderate per questo utente, quindi selezionare **Elimina utente**.

::: moniker-end

Quando si elimina un utente, il suo account diventa inattivo per circa 30 giorni. Si ha quindi a disposizione questo periodo di tempo per ripristinare l'account prima che venga eliminato definitivamente.
  
### <a name="does-your-organization-use-active-directory"></a>L'organizzazione usa Active Directory?

Se l'organizzazione Sincronizza gli account utente a Microsoft 365 da un ambiente Active Directory locale, è necessario eliminare e ripristinare gli account utente nel servizio Active Directory locale. Non è possibile eliminarli o ripristinarli in Office 365.
  
Per istruzioni, vedere questo articolo: [eliminare un account utente](https://go.microsoft.com/fwlink/?linkid=841808).
  
Se si usa Azure Active Directory, vedere il cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) di PowerShell. 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente
<a name="bkmk_session"> </a>

Informazioni su come rimuovere un dipendente dalla posta elettronica (Exchange).
  
|||
|:-----|:-----|
|**Cosa è possibile fare** <br/> |**Come farlo** <br/> |
|Terminare una sessione (ad esempio Outlook sul Web, Outlook, Exchange ActiveSync e così via) e forzare l'apertura di una nuova sessione  <br/> |Reimpostare la password  <br/> |
|Terminare una sessione e bloccare l'accesso a sessioni future (per tutti i protocolli)  <br/> |Disabilitare l'account. Ad esempio, nell'interfaccia di amministrazione di Exchange o con PowerShell:  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Terminare la sessione per un particolare protocollo, ad esempio ActiveSync  <br/> |Disabilitare il protocollo. Ad esempio, nell'interfaccia di amministrazione di Exchange o con PowerShell:  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Le operazioni precedenti possono essere eseguite in 3 posizioni:
  
|||
|:-----|:-----|
|**Se si termina la sessione qui** <br/> |**Quanto tempo occorre** <br/> |
|Nell'interfaccia di amministrazione di Exchange o con PowerShell  <br/> |Il ritardo massimo previsto è di 30 minuti  <br/> |
|Nell'interfaccia di amministrazione di Azure Active Directory  <br/> |Il ritardo previsto è di 60 minuti  <br/> |
|In un ambiente locale  <br/> |Il ritardo previsto è di 3 ore o più  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Come ottenere la risposta più rapida per la chiusura di un account

 **Metodo più rapido**: usare l'interfaccia di amministrazione di Exchange (usare PowerShell) oppure l'interfaccia di amministrazione di Azure Active Directory. In un ambiente locale, la sincronizzazione delle modifiche con DirSync può richiedere diverse ore. 
  
 **Metodo più rapido per utenti con presenza locale e nel data center di Exchange**: terminare la sessione con l'interfaccia di amministrazione di Exchange o di Azure Active Directory E apportare le modifiche anche nell'ambiente locale. In caso contrario, le modifiche nell'interfaccia di amministrazione di Exchange o di Azure Active Directory verranno sovrascritte da DirSync. 
  
## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)
  