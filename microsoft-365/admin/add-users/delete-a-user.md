---
title: Eliminare un utente dall'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Informazioni su come eliminare un account utente. Decidere cosa fare con l'indirizzo di posta elettronica dell'utente, il contenuto di OneDrive e se mantenere la licenza del prodotto o smettere di pagarla.
ms.openlocfilehash: 2c87f04675ec92e964acb6fc9aef7171b6d7d510
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353137"
---
# <a name="delete-a-user-from-your-organization"></a>Eliminare un utente dall'organizzazione
  
||
|:-----|
|**Per informazioni su come *eliminare l'account* utente di Office 365 utilizzato al lavoro o all'Istituto di istruzione? Rivolgersi al supporto tecnico del proprio lavoro o dell'Università per eseguire queste operazioni.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>Informazioni necessarie relative all'eliminazione degli utenti

- Solo le persone con autorizzazioni di [amministratore globale di Office 365](about-admin-roles.md) o di gestione degli utenti per l'azienda o l'istituto di istruzione possono eliminare gli account utente. 
    
- Si hanno a disposizione 30 giorni per [ripristinare](restore-user.md) l'account prima che i dati dell'utente vengano eliminati definitivamente. 
    
- Se si vogliono mantenere i dati di OneDrive dell'utente, spostarli in una posizione diversa. È possibile eseguire questa operazione fino a 30 giorni dopo l'eliminazione dell'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md). Non è necessario spostare i file di SharePoint dell'utente, perché saranno ancora accessibili.
    
- Se si vuole mantenere la posta elettronica dell'utente, **PRIMA** di eliminare l'account spostarla in una posizione diversa. Se l'account è già stato eliminato, è possibile ripristinarlo entro 30 giorni, spostare i dati della posta elettronica e quindi eliminare l'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md).
    
- Se si dispone di un abbonamento Enterprise come Office 365 Enterprise E3, è possibile conservare i dati delle cassette postali di un account utente di Office 365 eliminato trasformandola in una *cassetta postale inattiva*. Per saperne di più, vedere [Gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Amministratore globale: eliminare un utente, smettere di pagare la propria licenza e scegliere cosa fare con i propri messaggi di posta elettronica e contenuti di OneDrive

Se si è un amministratore globale, quando si elimina un utente, è anche possibile concedere a un altro utente l'accesso al proprio indirizzo di posta elettronica e scegliere cosa fare con il contenuto di OneDrive. 

  
### <a name="things-to-consider"></a>Aspetti da considerare

Prima di iniziare, considerare cosa si vuole fare con la posta elettronica e il contenuto di OneDrive dell'utente e se si desidera mantenere la licenza o smettere di pagarla.
  
|||
|:-----|:-----|
|Licenze per i prodotti  <br/> |È possibile rimuovere la licenza dall'utente e rimuoverla dagli abbonamenti per interrompere il pagamento per la licenza. Se si seleziona questa opzione, la licenza verrà rimossa automaticamente dagli abbonamenti.  <br/><br/> **Non è possibile rimuovere la licenza** se è stata acquistata tramite un partner o un contratto multilicenza. Se si paga un piano annuale o si è nel mezzo di un ciclo di fatturazione, non sarà possibile rimuovere la licenza dall'abbonamento fino a quando non viene completato l'impegno.  <br/> |
|Contenuto di OneDrive  <br/> |Se l'utente ha salvato i propri file in OneDrive, è possibile concedere a un altro utente l'accesso a questi file.  <br/><br/> Sarà necessario spostare i file che si desidera conservare entro il periodo di conservazione impostato per i file di OneDrive. **Per impostazione predefinita, il periodo di conservazione è di 30 giorni.** Se non si spostano i file entro il periodo di conservazione dopo l'eliminazione dell'utente, il contenuto di OneDrive verrà eliminato definitivamente. Per aumentare il numero di giorni di conservazione dei file di OneDrive per gli account eliminati, vedere [set the OneDrive retention for deleted Users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  <br/><br/> **Importante!** Se l'utente eliminato ha utilizzato un computer personale per scaricare i file da SharePoint e OneDrive, non è possibile cancellare i file archiviati nel computer in uso. Continueranno ad avere accesso a tutti i file che sono stati sincronizzati da OneDrive.           |
|Posta elettronica  <br/> | Se si concede a un altro utente l'accesso alla posta elettronica dell'utente eliminato, la cassetta postale dell'utente eliminato verrà convertita in una cassetta postale condivisa. Il nuovo proprietario della cassetta postale può quindi accedere alla cassetta postale e monitorare il nuovo messaggio di posta elettronica. Sono inoltre disponibili le opzioni seguenti:  <br/>  <br/>Modificare il nome visualizzato: si consiglia di modificare il nome visualizzato in modo che sia possibile identificare facilmente la cassetta postale condivisa nell'elenco utenti attivi.  <br/>  Attiva risposte automatiche-abbiamo già scritto una cortese risposta automatica per te. È possibile inviare una risposta automatica diversa alle persone all'interno dell'organizzazione e persone esterne all'organizzazione.  <br/> <br/> Pulizia degli alias-gli alias sono indirizzi di posta elettronica aggiuntivi per gli utenti. Alcune organizzazioni non le utilizzano, quindi se non si dispone di alcuna operazione non è necessario eseguire altre operazione. Se l'utente dispone di alias, è consigliabile rimuoverli in modo che sia possibile riutilizzare tali indirizzi di posta elettronica. In caso contrario, non è possibile riutilizzare tali indirizzi di posta elettronica fino al termine del periodo di conservazione per le cassette postali eliminate. Per impostazione predefinita, una cassetta postale eliminata è ripristinabile per 30 giorni. Per ulteriori informazioni, vedere [eliminare o ripristinare le cassette postali degli utenti in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Se l'organizzazione usa **Active Directory** che si sincronizza con Azure AD, è necessario eliminare l'account utente da Active Directory. Non è possibile farlo da Office 365. Per istruzioni, vedere [eliminare un account utente](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |
   
### <a name="get-started"></a>Per iniziare

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

::: moniker-end

Poiché l'esperienza guidata illustra i passaggi necessari per eliminare un utente, ecco come iniziare.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Selezionare l'utente che si desidera eliminare, quindi selezionare **Elimina utente**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Amministratore Gestione utenti: eliminare uno o più utenti da Office 365


 **IMPORTANTE**: Non eliminare l'account di un utente se è stato [convertito in una cassetta postale condivisa](../email/convert-user-mailbox-to-shared-mailbox.md) o se è stato configurato l'inoltro della posta elettronica. Per queste funzioni è necessario mantenere l'account. Se è stato convertito in una cassetta postale condivisa, è possibile [Interrompere il pagamento per la licenza](#stop-paying-for-the-license) dall'account in modo da interrompere il pagamento. Se si imposta l'inoltro della posta elettronica, non è possibile rimuovere la licenza. La rimozione, infatti, interrompe l'inoltro della posta elettronica e disattiva la cassetta postale. 
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  

2. Selezionare i nomi degli utenti che si desidera eliminare, selezionare **altre opzioni** (..**.**) e quindi scegliere **Elimina utente**.

   Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**. Vedere la procedura successiva per interrompere il pagamento per la licenza.  In alternativa, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare i nomi degli utenti che si desidera eliminare e, nel riquadro azioni in **blocco** , scegliere **Elimina utenti**.

   Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**. Vedere la procedura successiva per interrompere il pagamento per la licenza.  In alternativa, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare i nomi degli utenti che si desidera eliminare e, nel riquadro azioni in **blocco** , scegliere **Elimina utenti**.

   Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**. Vedere la procedura successiva per interrompere il pagamento per la licenza.  In alternativa, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Interrompere il pagamento per la licenza

La riduzione del numero di licenze è un passaggio separato che può essere eseguito solo dall'amministratore globale o dall'amministratore della fatturazione. 
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prodotti e servizi</a>. Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.

2. Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.  

   Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abbonamenti</a> di fatturazione. Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.

2. Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.  

   Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">abbonamenti</a> di fatturazione. Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.

2. Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.  

   Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a>Eliminare contemporaneamente numerosi utenti

Vedere il cmdlet [Remove-MsolUser di](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Risolvere i problemi relativi all'eliminazione di un utente

Di seguito sono rilevati i problemi più comuni che si verificano durante l'eliminazione di un utente:
  
- **Viene visualizzato un messaggio di errore lungo le righe di "l'utente non può essere eliminato. Provare di nuovo in un secondo momento.** Controllare se l'account è configurato per l'inoltro della posta elettronica o se è stato convertito in una cassetta postale condivisa. Entrambe queste cause causano tale errore. Non eliminare l'account se ha l'inoltro della posta elettronica o se è stato convertito in una cassetta postale condivisa.

- **Non si hanno le autorizzazioni appropriate per eliminare un utente**. Solo gli amministratori [globali di Office 365 o gli amministratori di gestione utenti](about-admin-roles.md) possono eliminare gli utenti. Si tratta in genere del supporto tecnico dell'istituto di istruzione o dell'azienda.

- **L'utente viene eliminato, ma il nome continua a comparire nella Rubrica globale**. Questo accade quando un'azienda usa Active Directory. È necessario eliminare l'account utente da Active Directory. Per istruzioni, vedere l'articolo di TechNet: [Eliminare un account utente.](https://go.microsoft.com/fwlink/p/?linkid=841808)

||
|:-----|
|**Eliminare Office 365 dal computer? Passare a [Annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).**|
   
## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)
  
[Eliminare definitivamente una cassetta postale](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Rimuovere un ex dipendente da Office 365](remove-former-employee.md)

[Aggiungere un nuovo dipendente a Office 365](add-new-employee.md)

[Eliminare un account utente](https://go.microsoft.com/fwlink/p/?linkid=841808): utilizzare queste istruzioni se la propria azienda utilizza **Active Directory** che esegue la sincronizzazione con Azure ad. Non è possibile farlo da Office 365.
