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
    
    **IMPORTANTE**: l'opzione Imposta come principale non è visualizzata se Microsoft 365 è stato acquistato presso GoDaddy o un altro partner che fornisce una console di gestione. In questo caso, per impostare l'alias principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - Che il cambiamento potrebbe richiedere del tempo.
  
  - Il nuovo nome utente, che sarà necessario per accedere a Microsoft 365.
    
  - Se l'utente usa Skype for Business online, informarlo che dovrà ripianificare le eventuali riunioni di Skype for Business online organizzate e avvisare i contatti esterni di aggiornare le proprie informazioni di contatto.

  - Se l'utente usa OneDrive, informarlo che l'URL di questa posizione è cambiato. Se l'utente ha blocchi appunti di OneNote in OneDrive, potrebbe doverli chiudere e riaprire in OneNote. Se l'utente ha file condivisi da OneDrive, i collegamenti ai file potrebbero non funzionare e l'utente può ricondividere i file.    
  
  - Se è stata cambiata anche la password, informarlo che gli verrà chiesto di immettere la nuova password nel dispositivo mobile, altrimenti non verrà sincronizzato.
  
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Selezionare **Imposta come principale** per l'indirizzo di posta elettronica da impostare come indirizzo principale per la persona specificata. 
    
    **IMPORTANTE**: l'opzione Imposta come principale non è visualizzata se Microsoft 365 è stato acquistato presso GoDaddy o un altro partner che fornisce una console di gestione. In questo caso, per impostare l'alias principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - L'applicazione di questa modifica può richiedere un po' di tempo.
  
  - Il nuovo nome utente, che sarà necessario per accedere a Microsoft 365.
    
  - Se l'utente usa Skype for Business online, informarlo che dovrà ripianificare le eventuali riunioni Skype for Business online organizzate e avvisare i contatti esterni di aggiornare le vecchie informazioni di contatto.

  - Se l'utente usa OneDrive, informarlo che l'URL di questa posizione è stata modificata. Se l'utente dispone di blocchi appunti di OneNote in OneDrive, potrebbe doverli chiudere e riaprire in OneNote. Se l'utente dispone di file condivisi da OneDrive, i collegamenti ai file potrebbero non funzionare e l'utente può ricondividere i file.    
  
  - Se è stata cambiata anche la password, informarlo che gli verrà chiesto di immettere la nuova password nel dispositivo mobile, altrimenti non verrà sincronizzato.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Nome utente/Indirizzo di posta elettronica**, selezionare **Modifica**.

3. Selezionare **Imposta come principale** per l'indirizzo di posta elettronica da impostare come indirizzo principale per la persona specificata. 
    
    **IMPORTANTE**: l'opzione Imposta come principale non è visualizzata se Microsoft 365 è stato acquistato presso GoDaddy o un altro partner che fornisce una console di gestione. In questo caso, per impostare l'alias principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
    
    Inoltre, questa opzione viene visualizzata solo se si è amministratori globali. Se l'opzione non è visualizzata, non si hanno le autorizzazioni per modificare il nome e l'indirizzo e-mail principale di un utente.
  
4. Viene visualizzato un grande simbolo di avvertenza giallo che segnala che si stanno per modificare le informazioni di accesso dell'utente. Selezionare **Salva**, quindi **Chiudi**.
    
5. Comunicare le informazioni seguenti:
 
  - L'applicazione di questa modifica può richiedere un po' di tempo.
  
  - Il nuovo nome utente, che sarà necessario per accedere a Microsoft 365.
    
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

Potrebbero essere necessarie fino a 24 ore prima che la modifica diventi effettiva per tutti i servizi. Dopo l'applicazione della modifica, l'utente dovrà accedere a Outlook, Skype for Business e SharePoint con il nome utente aggiornato.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Informazioni contatto**, selezionare **Modifica**.

3. Nella casella **Nome visualizzato**, digitare un nuovo nome per l'utente, quindi selezionare **Salva**.

    Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**, consultare [Risolvere messaggi di errore](#resolve-error-messages).

Potrebbero essere necessarie fino a 24 ore prima che la modifica diventi effettiva per tutti i servizi. Dopo l'applicazione della modifica, l'utente dovrà accedere a Outlook, Skype for Business e SharePoint con il nome utente aggiornato. Assicurarsi quindi di comunicare la modifica all'utente.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente. Nel riquadro a comparsa, accanto a **Informazioni contatto**, selezionare **Modifica**.

3. Nella casella **Nome visualizzato**, digitare un nuovo nome per l'utente, quindi selezionare **Salva**.

    Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**, consultare [Risolvere messaggi di errore](#resolve-error-messages).

Potrebbero essere necessarie fino a 24 ore prima che la modifica diventi effettiva per tutti i servizi. Dopo l'applicazione della modifica, l'utente dovrà accedere a Outlook, Skype for Business e SharePoint con il nome utente aggiornato. Assicurarsi quindi di comunicare la modifica all'utente.

::: moniker-end

## <a name="resolve-error-messages"></a>Risolvere messaggi di errore

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Non è possibile trovare un parametro corrispondente al nome 'EmailAddresses'"

Se viene visualizzato il messaggio di errore **Non è possibile trovare un parametro corrispondente al nome "EmailAddresses"**, significa che l'operazione sta impiegando più tempo del previsto per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il [supporto](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products), che provvederà a eseguire una sincronizzazione completa.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare"

Se viene visualizzato il messaggio di errore "**Non è stato possibile modificare l'utente. Controllare le informazioni sull'utente e riprovare**", significa che non si è un amministratori globali e non si hanno le autorizzazioni per modificare il nome dell'utente. Chiedere all'amministratore globale dell'organizzazione di apportare la modifica.


## <a name="what-to-do-with-old-email-addresses"></a>Cosa fare con gli indirizzi di posta elettronica precedenti

L'indirizzo di posta elettronica principale precedente dell'utente viene mantenuto come indirizzo di posta elettronica aggiuntivo. **È consigliabile non rimuovere l'indirizzo di posta elettronica precedente.**
  
Alcune persone potrebbero continuare a inviare e-mail al vecchio indirizzo e, se viene eliminato, potrebbero verificarsi errori di mancato recapito. Microsoft instrada automaticamente i messaggi al nuovo indirizzo. Inoltre, non riutilizzare i vecchi indirizzi di posta elettronica SMTP per applicarli a nuovi account. Anche questo può causare errori di mancato recapito o la consegna a una cassetta postale sbagliata.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>Che succede se la rubrica offline dell'utente non si sincronizza con l'elenco indirizzi globale?

Se l'utente usa Exchange Online oppure se il suo account è collegato all'ambiente di Exchange locale dell'organizzazione, potrebbe essere visualizzato questo messaggio di errore se si prova a cambiare un nome utente e un indirizzo di posta elettronica: "Questo utente è sincronizzato con Active Directory locale. Alcuni dettagli possono essere modificati solo tramite Active Directory locale".
  
La causa è da attribuire al MOERA (Microsoft Online Email Routing Address). Il MOERA viene creato dall'attributo _userPrincipalName_ dell'utente in Active Directory e viene automaticamente assegnato all'account del cloud durante la sincronizzazione iniziale. Una volta creato, non può essere modificato o rimosso in Microsoft 365. È possibile in seguito cambiare il nome utente in Active Directory, ma la modifica non verrà applicata al MOERA e si potrebbero verificare errori durante la visualizzazione del nome appena cambiato nell'elenco indirizzi globale. 
  
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
