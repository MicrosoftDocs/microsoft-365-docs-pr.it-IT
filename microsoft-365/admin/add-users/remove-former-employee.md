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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Seguire questo elenco di controllo per rimuovere un dipendente da Microsoft 365 e proteggere i dati. '
ms.openlocfilehash: adf5c683828b30a978199145fa2c54f17d1b6b37
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780578"
---
# <a name="remove-a-former-employee"></a>Rimuovere un ex dipendente

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Disconnessione immediata

::: moniker range="o365-worldwide"

Guardare un breve video sulla rimozione di un dipendente. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

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
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Passaggio** <br/> |**Perché eseguire questa operazione** <br/> |
|1. [Salvare il contenuto della cassetta postale di un ex dipendente](#save-the-contents-of-a-former-employees-mailbox) <br/> |È un'operazione utile per la persona che prenderà il posto del dipendente o in caso di controversie.  <br/> |
|2. [Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirla in una cassetta postale condivisa](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Cancellare i dati e bloccare il dispositivo mobile di un ex dipendente](#wipe-and-block-a-former-employees-mobile-device) <br/> |Rimuove i dati aziendali dal telefono o dal tablet.  <br/> |
|4. [bloccare l'accesso di un ex dipendente ai dati di Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Impedisce all'utente di accedere alla vecchia cassetta postale e ai dati di Microsoft 365.  <br/><br/> **Suggerimento**: quando si blocca l'accesso di un utente, si sta ancora pagando la propria licenza. Per interromperlo, è necessario eliminare la licenza dall'abbonamento (passaggio 5).           |
|5. [Spostare il contenuto di OneDrive del dipendente](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Se si rimuove solo la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Se ha usato un computer personale anziché un computer fornito dalla società per scaricare file da OneDrive e SharePoint, non esiste alcun modo per cancellare i file che vi ha archiviato.  <br/><br/> Continuerà ad accedere a tutti i file che sono stati sincronizzati con il suo computer.  <br/> |
|6. [rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Eliminare l'account utente di un ex dipendente.](#delete-a-former-employees-user-account)<br/> |Questo rimuove l'account dall'interfaccia di amministrazione. Consente di tenere tutto in ordine.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Salvare il contenuto della cassetta postale di un ex dipendente
<a name="bkmk_preserve"> </a>

Il contenuto della cassetta postale dell'ex dipendente può essere salvato in due modi:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    O
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Dopo aver convertito la cassetta postale in "cassetta postale inattiva", gli amministratori, i responsabili della conformità o i responsabili della gestione dei record possono usare gli strumenti eDiscovery sul posto in Exchange Online per accedere al contenuto ed eseguire ricerche.
    
    Le cassette postali inattive non possono ricevere posta elettronica e non vengono visualizzate nella rubrica condivisa o in altri elenchi dell'organizzazione.
    
    Per informazioni su come applicare un'esenzione su una cassetta postale, vedere [gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirla in una cassetta postale condivisa
<a name="bkmk_forward"> </a>

In questo passaggio, l'indirizzo di posta elettronica dell'ex dipendente viene assegnato a un altro dipendente o si [converte la cassetta postale dell'utente in una cassetta postale condivisa](../email/convert-user-mailbox-to-shared-mailbox.md) creata. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Se si configura l'inoltro della posta elettronica, ora solo i  *nuovi*  messaggi di posta elettronica inviati all'ex dipendente vengono inviati al dipendente corrente. 
    
- L'inoltro della posta elettronica richiede che l'account dell'ex dipendente abbia una licenza.
    
 > [!IMPORTANT] 
 > Se si sta configurando l'inoltro della posta elettronica o una cassetta postale condivisa, alla fine non eliminare l'account dell'ex dipendente. L'account deve restare valido per poter ancorare l'inoltro della posta elettronica o la cassetta postale condivisa. 

::: moniker range="o365-worldwide"  

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome del dipendente che si desidera bloccare, quindi selezionare la scheda **posta** .

3. In **inoltro della posta elettronica**, selezionare **Gestisci inoltro della posta elettronica**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.
 
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare ed espandere **impostazioni di posta elettronica**.

3. Accanto a **inoltro della posta elettronica**, selezionare **modifica**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare il dipendente che si desidera bloccare ed espandere **impostazioni di posta elettronica**.

3. Accanto a **inoltro della posta elettronica**, selezionare **modifica**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selezionare **Salva**. 
    
6. Ricordare di non eliminare l'account dell'ex dipendente.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Cancellare i dati e bloccare il dispositivo mobile di un ex dipendente
<a name="bkmk_mobile"> </a>

Se l'ex dipendente aveva un telefono aziendale, è possibile usare Office 365 per cancellare i dati e bloccare il dispositivo, in modo che tutti i dati dell'organizzazione vengano rimossi dal dispositivo e quest'ultimo non possa più connettersi all'Interfaccia di amministrazione di Exchange.
  

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

3. Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**. 
    
4. Selezionare l'utente e in **dispositivi mobili**selezionare **Visualizza dettagli**. 
    
5. Nella pagina **Dettagli dispositivo mobile** , in **dispositivi mobili**, selezionare il dispositivo mobile, selezionare **wipe data** ![ Wipe Device ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) , quindi selezionare **blocca**. 
    
6. Selezionare **Salva**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Bloccare l'accesso di un ex dipendente ai dati di Microsoft 365
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Il blocco di un account può richiedere fino a 24 ore. Se è necessario impedire immediatamente l'accesso di un utente, è necessario [reimpostare la password](reset-passwords.md) e quindi avviare un evento di una tantum che li disfirmerà dalle sessioni di Microsoft 365 su tutti i dispositivi. Vedere [Disconnessione immediata](#sign-out-now)
 

::: moniker range="o365-worldwide"

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



1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.


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

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Eliminare l'account utente di un ex dipendente.
<a name="bkmk_delete"> </a>

Dopo il salvataggio e l'accesso ai dati utente dell'ex dipendente, è possibile eliminare l'account corrispondente.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

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

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
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
|Terminare una sessione e bloccare l'accesso a sessioni future (per tutti i protocolli)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Terminare la sessione per un particolare protocollo, ad esempio ActiveSync  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Le operazioni precedenti possono essere eseguite in 3 posizioni:
  
|||
|:-----|:-----|
|**Se si termina la sessione qui** <br/> |**Quanto tempo occorre** <br/> |
|Nell'interfaccia di amministrazione di Exchange o con PowerShell  <br/> |Il ritardo massimo previsto è di 30 minuti  <br/> |
|Nell'interfaccia di amministrazione di Azure Active Directory  <br/> |Il ritardo previsto è di 60 minuti  <br/> |
|In un ambiente locale  <br/> |Il ritardo previsto è di 3 ore o più  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Come ottenere la risposta più rapida per la chiusura di un account

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)
  
