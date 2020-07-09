---
title: Cambiare un nome utente e un indirizzo e-mail
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: "Informazioni su come un amministratore globale può modificare il nome visualizzato e l'indirizzo e-mail di un utente. "
ms.openlocfilehash: fedc1532bfec246392180d386a6960dbb08bd137
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079714"
---
# <a name="change-a-user-name-and-email-address"></a>Cambiare un nome utente e un indirizzo e-mail

Potrebbe essere necessario modificare l'indirizzo e-mail e il nome visualizzato di una persona che, ad esempio, si è sposata e ha cambiato cognome.

Guardare un breve video su come modificare l'indirizzo di posta elettronica di un utente. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="change-a-users-email-address"></a>Cambiare l'indirizzo di posta elettronica di un utente

Per eseguire questi passaggi, è necessario essere un [amministratore globale](about-admin-roles.md). 

::: moniker range="o365-worldwide"
 
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Selezionare il nome dell'utente e quindi, nella scheda **Account**, selezionare **Gestisci nome utente**.
    
3. Nella prima casella digitare la prima parte del nuovo indirizzo di posta elettronica. Se si è aggiunto il proprio dominio a Microsoft 365, specificarlo per il nuovo alias di posta elettronica usando l'elenco a discesa. 

4. Selezionare **Salva modifiche**.

   
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Nella prima casella digitare la prima parte del nuovo indirizzo di posta elettronica. Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.

4. Seleziona **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Nella prima casella digitare la prima parte del nuovo indirizzo di posta elettronica. Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.

4. Seleziona **Salva**.

::: moniker-end

**IMPORTANTE**: se si riceve un messaggio di errore, consultare [Risolvere messaggi di errore](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Impostare l'indirizzo di posta elettronica principale

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Selezionare il nome dell'utente e quindi, nella scheda **Account**, selezionare **Gestisci alias di posta elettronica**.

3. Selezionare **Imposta come principale** per l'indirizzo di posta elettronica da impostare come indirizzo principale per la persona specificata. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - Che il cambiamento potrebbe richiedere del tempo.
  
  - Their new username. They'll need it to sign in to Microsoft 365.
    
  - Se l'utente usa Skype for Business online, informarlo che dovrà ripianificare le eventuali riunioni di Skype for Business online organizzate e avvisare i contatti esterni di aggiornare le proprie informazioni di contatto.

  - Se l'utente usa OneDrive, informarlo che l'URL di questa posizione è cambiato. Se l'utente ha blocchi appunti di OneNote in OneDrive, potrebbe doverli chiudere e riaprire in OneNote. Se l'utente ha file condivisi da OneDrive, i collegamenti ai file potrebbero non funzionare e l'utente può ricondividere i file.    
  
  - Se è stata cambiata anche la password, informarlo che gli verrà chiesto di immettere la nuova password nel dispositivo mobile, altrimenti non verrà sincronizzato.
  
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Selezionare **Imposta come principale** per l'indirizzo di posta elettronica da impostare come indirizzo principale per la persona specificata. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - L'applicazione di questa modifica può richiedere un po' di tempo.
  
  - What their new username is. They'll need it to sign in to Microsoft 365.
    
  - Se l'utente usa Skype for Business online, informarlo che dovrà ripianificare le eventuali riunioni Skype for Business online organizzate e avvisare i contatti esterni di aggiornare le vecchie informazioni di contatto.

  - Se l'utente usa OneDrive, informarlo che l'URL di questa posizione è stata modificata. Se l'utente dispone di blocchi appunti di OneNote in OneDrive, potrebbe doverli chiudere e riaprire in OneNote. Se l'utente dispone di file condivisi da OneDrive, i collegamenti ai file potrebbero non funzionare e l'utente può ricondividere i file.    
  
  - Se è stata cambiata anche la password, informarlo che gli verrà chiesto di immettere la nuova password nel dispositivo mobile, altrimenti non verrà sincronizzato.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Selezionare **Imposta come principale** per l'indirizzo di posta elettronica da impostare come indirizzo principale per la persona specificata. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Microsoft 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - L'applicazione di questa modifica può richiedere un po' di tempo.
  
  - What their new username is. They'll need it to sign in to Microsoft 365.
    
  - Se l'utente usa Skype for Business online, informarlo che dovrà ripianificare le eventuali riunioni Skype for Business online organizzate e avvisare i contatti esterni di aggiornare le vecchie informazioni di contatto.

  - Se l'utente usa OneDrive, informarlo che l'URL di questa posizione è stata modificata. Se l'utente dispone di blocchi appunti di OneNote in OneDrive, potrebbe doverli chiudere e riaprire in OneNote. Se l'utente dispone di file condivisi da OneDrive, i collegamenti ai file potrebbero non funzionare e l'utente può ricondividere i file.    
  
  - Se è stata cambiata anche la password, informarlo che gli verrà chiesto di immettere la nuova password nel dispositivo mobile, altrimenti non verrà sincronizzato.

::: moniker-end
  
## <a name="change-a-users-display-name"></a>Cambiare il nome visualizzato di un utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome dell'utente e quindi, nella scheda **Account**, selezionare **Gestisci informazioni sul contatto**.

3. Nella casella **Nome visualizzato**, digitare un nuovo nome per l'utente, quindi selezionare **Salva**.

    Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**, consultare [Risolvere messaggi di errore](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Informazioni contatto**, selezionare **Modifica**.

3. Nella casella **Nome visualizzato**, digitare un nuovo nome per l'utente, quindi selezionare **Salva**.

    Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**, consultare [Risolvere messaggi di errore](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Informazioni contatto**, selezionare **Modifica**.

3. Nella casella **Nome visualizzato**, digitare un nuovo nome per l'utente, quindi selezionare **Salva**.

    Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**, consultare [Risolvere messaggi di errore](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>Risolvere messaggi di errore

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Non è possibile trovare un parametro corrispondente al nome 'EmailAddresses'"

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call [support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) and ask them to do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare"

Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**", significa che non si è un amministratori globali e non si hanno le autorizzazioni per modificare il nome dell'utente. Chiedere all'amministratore globale dell'organizzazione di apportare la modifica.


## <a name="what-to-do-with-old-email-addresses"></a>Cosa fare con gli indirizzi di posta elettronica precedenti

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people might continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft automatically routes it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>Che succede se la rubrica offline dell'utente non si sincronizza con l'elenco indirizzi globale?

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you might see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Microsoft 365. You can subsequently change the username in the Active Directory, but it doesn't change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
Per risolvere il problema, accedere al [Modulo di Azure Active Directory per PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) con le credenziali di amministratore di Microsoft 365. Utilizzare la sintassi seguente: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> In questo modo l'attributo **userPrincipalName** dell'utente verrà cambiato e non avrà nessun rapporto con l'indirizzo di posta elettronica di Microsoft Online Email Routing Address (MOERA) dell'utente. È tuttavia consigliabile che il nome UPN di accesso dell'utente corrisponda al suo indirizzo SMTP principale. 
  
Per informazioni su come cambiare il nome di un utente in Active Directory, vedere [Rinominare un account utente](https://go.microsoft.com/fwlink/?LinkId=809091) in Windows Server 2003 e versioni precedenti.
  
## <a name="related-articles"></a>Articoli correlati

[Amministratori: Reimpostare la password di uno o più utenti](reset-passwords.md)
  
[Aggiungere un altro indirizzo di posta elettronica a un utente](../email/add-another-email-alias-for-a-user.md)
