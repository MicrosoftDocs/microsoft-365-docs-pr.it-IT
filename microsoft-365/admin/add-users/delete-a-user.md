---
title: Eliminare un utente dall'organizzazione
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
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Informazioni su come eliminare un account utente. Decidere cosa fare con la posta elettronica e il contenuto di OneDrive dell'utente. E decidi se mantenere la licenza del prodotto o smettere di pagarla.
ms.openlocfilehash: d40f70534499b08073278ffc2bed2b098ae1c4da
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860738"
---
# <a name="delete-a-user-from-your-organization"></a>Eliminare un utente dall'organizzazione
  
**Per informazioni su come eliminare il *proprio* account utente di Microsoft 365 che usi a scuola o al lavoro? Per eseguire questa procedura, contattare il supporto tecnico presso il proprio lavoro o l'università.**

## <a name="what-you-need-to-know-about-deleting-users"></a>Informazioni necessarie relative all'eliminazione degli utenti

- Solo le persone con autorizzazioni di amministratore globale o gestione utenti di [Microsoft 365](about-admin-roles.md) per l'azienda o l'istituto di istruzione possono eliminare gli account utente.
- Si hanno a disposizione 30 giorni per [ripristinare](restore-user.md) l'account prima che i dati dell'utente vengano eliminati definitivamente.
- Se si vogliono mantenere i dati di OneDrive dell'utente, spostarli in una posizione diversa. È anche possibile spostare i dati fino a 30 giorni dopo l'eliminazione dell'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md). Non è necessario spostare i file di SharePoint dell'utente, perché saranno ancora accessibili.
- Se si vuole mantenere la posta elettronica dell'utente, **PRIMA** di eliminare l'account spostarla in una posizione diversa. Se l'account è già stato eliminato, è possibile ripristinarlo entro 30 giorni, spostare i dati della posta elettronica e quindi eliminare l'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md).
- Se si dispone di un abbonamento Enterprise come Office 365 Enterprise E3, è possibile conservare i dati della cassetta postale di un account utente eliminato trasformandolo in una cassetta postale *inattiva.* Per saperne di più, vedere [Gestire le cassette postali inattive in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Amministratore globale: eliminare un utente, interrompere il pagamento della licenza e scegliere cosa fare con la posta elettronica e il contenuto di OneDrive

Se si è un amministratore globale, quando si elimina un utente è anche possibile concedere a un altro utente l'accesso alla posta elettronica e scegliere cosa fare con il contenuto di OneDrive.

### <a name="things-to-consider"></a>Aspetti da considerare

Prima di iniziare, pensa a cosa vuoi fare con la posta elettronica e il contenuto di OneDrive dell'utente e se vuoi mantenere la licenza o smettere di pagarla.
  
|Elemento | Descrizione |
|:-----|:-----|
|Licenze di prodotto  <br/> |Puoi rimuovere la licenza dall'utente e rimuoverla dalle sottoscrizioni per interrompere il pagamento per tale licenza. Se si seleziona questa opzione, la licenza verrà rimossa automaticamente dalle sottoscrizioni.  <br/><br/> **Non puoi rimuovere la licenza se l'hai** acquistata tramite un partner o contratti multilicenza. Se stai pagando un piano annuale o sei nel bel mezzo di un ciclo di fatturazione, non potrai rimuovere la licenza dall'abbonamento fino al completamento dell'impegno.  <br/> |
|Contenuto di OneDrive  <br/> |Se l'utente ha salvato i propri file in OneDrive, è possibile concedere a un altro utente l'accesso a questi file.  <br/><br/> Dovrai spostare i file che vuoi mantenere entro il periodo di conservazione impostato per i file di OneDrive. **Per impostazione predefinita, il periodo di conservazione è 30 giorni.** Se non si spostano i file entro il periodo di conservazione dopo l'eliminazione dell'utente, il contenuto di OneDrive verrà eliminato definitivamente. Per aumentare il numero di giorni di conservazione dei file di OneDrive per gli account eliminati, vedere Impostare la conservazione di [OneDrive per gli utenti eliminati.](/onedrive/set-retention)  <br/><br/> **Importante!** Se l'utente eliminato ha usato un personal computer per scaricare i file da SharePoint e OneDrive, non è possibile cancellare i file archiviati nel computer. Continueranno ad avere accesso ai file sincronizzati da OneDrive.           |
|Posta elettronica  <br/> | Se si consente a un altro utente di accedere alla posta elettronica dell'utente eliminato, la cassetta postale dell'utente eliminato verrà convertita in una cassetta postale condivisa. Il nuovo proprietario della cassetta postale può quindi accedere alla cassetta postale e monitorare la nuova posta elettronica. Sono disponibili anche le opzioni seguenti:  <br/>  <br/>Modificare il nome visualizzato- È consigliabile modificare il nome visualizzato in modo che sia facile identificare la cassetta postale condivisa **nell'elenco Utenti** attivi.  <br/>  Attivare le risposte automatiche: è già stata scritta una risposta automatica educata. È possibile inviare risposte automatiche diverse a persone all'interno dell'organizzazione e a persone esterne all'organizzazione.  <br/> <br/> Pulire gli alias: gli alias sono indirizzi di posta elettronica aggiuntivi per gli utenti. Alcune organizzazioni non le usano, quindi se non hai bisogno di fare altre cose qui. Se l'utente dispone di alias, è consigliabile rimuoverli in modo da poter riutilizzare tali indirizzi di posta elettronica. In caso contrario, non è possibile riutilizzare tali indirizzi di posta elettronica fino al termine del periodo di conservazione per le cassette postali eliminate. Per impostazione predefinita, una cassetta postale eliminata è recuperabile per 30 giorni. Per ulteriori informazioni, vedere [Delete or restore user mailboxes in Exchange Online.](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|Active Directory  <br/> |Se l'organizzazione usa **Active Directory** che si sincronizza con Azure AD, è necessario eliminare l'account utente da Active Directory. Non è possibile farlo da Office 365. Per istruzioni, vedere [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))  <br/> |

### <a name="get-started"></a>Introduzione

Poiché l'esperienza guidata illustra i passaggi per eliminare un utente, ecco come iniziare.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Selezionare l'utente che si desidera eliminare e quindi selezionare **Elimina utente**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Amministratore gestione utenti: eliminare uno o più utenti da Office 365

> [!IMPORTANT]
> Non eliminare l'account di un utente [](../email/convert-user-mailbox-to-shared-mailbox.md) se è stato convertito in una cassetta postale condivisa o se è stato configurato l'inoltro della posta elettronica nell'account. Queste funzioni necessitano ancora dell'account. Una cassetta postale condivisa non richiede una licenza. Se l'account è stato convertito in una cassetta postale condivisa, è possibile interrompere [il pagamento per la licenza](#stop-paying-for-the-license). Se è stato configurato l'inoltro della posta elettronica nell'account, non è possibile rimuovere la licenza. In questo modo verrà interrotta l'inoltro della posta elettronica e la cassetta postale verrà disattivata.
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  

2. Selezionare i nomi degli utenti che si desidera eliminare, selezionare **Altre opzioni** (**...**) e quindi scegliere  **Elimina utente**.

   Anche se hai eliminato l'account **dell'utente, stai ancora pagando per la licenza**. Per interrompere il pagamento della licenza, vedere la procedura successiva.  In caso contrario, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare i nomi degli utenti che si desidera eliminare e nel riquadro **Azioni** in blocco scegliere **Elimina utenti**.

   Anche se hai eliminato l'account **dell'utente, stai ancora pagando per la licenza**. Per interrompere il pagamento della licenza, vedere la procedura successiva.  In caso contrario, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare i nomi degli utenti che si desidera eliminare e nel riquadro **Azioni** in blocco scegliere **Elimina utenti**.

   Anche se hai eliminato l'account **dell'utente, stai ancora pagando per la licenza**. Per interrompere il pagamento della licenza, vedere la procedura successiva.  In caso contrario, è possibile assegnare la licenza a un altro utente. Non verrà assegnato automaticamente a un utente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Interrompere il pagamento per la licenza

La riduzione del numero di licenze è un passaggio separato che può essere eseguito solo dall'amministratore globale o dall'amministratore della fatturazione.
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>. Se non vedi questa opzione, non sei un amministratore globale o un amministratore della fatturazione e non puoi eseguire questo passaggio.

2. Nella scheda **Prodotti** selezionare l'abbonamento per cui si desidera rimuovere le licenze.

3. Nella pagina dei dettagli dell’abbonamento selezionare **Rimuovi licenze**.

4. Nel riquadro **Rimuovi licenze,** in **Nuova** quantità, nella casella **Totale** licenze immettere il numero totale di licenze desiderate per l'abbonamento. Ad esempio, se si dispone di 100 licenze e si desidera rimuoverle cinque, immettere 95.

5. Selezionare **Salva**.

In seguito, quando si esegue la procedura per aggiungere un'altra persona all'azienda, verrà richiesto di acquistare una licenza contemporaneamente, con un solo passaggio.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>. Se non vedi questa opzione, non sei un amministratore globale o un amministratore della fatturazione e non puoi eseguire questo passaggio.

2. Seleziona la sottoscrizione (se ne hai più di una) e quindi seleziona **Aggiungi/Rimuovi** licenze per eliminare la licenza in modo da non pagare finché non assumi un'altra persona.  

   In seguito, quando si esegue la procedura per aggiungere un'altra persona all'azienda, verrà richiesto di acquistare una licenza contemporaneamente, con un solo passaggio.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>. Se non vedi questa opzione, non sei un amministratore globale o un amministratore della fatturazione e non puoi eseguire questo passaggio.

2. Seleziona la sottoscrizione (se ne hai più di una) e quindi seleziona **Aggiungi/Rimuovi** licenze per eliminare la licenza in modo da non pagare finché non assumi un'altra persona.  

   In seguito, quando si esegue la procedura per aggiungere un'altra persona all'azienda, verrà richiesto di acquistare una licenza contemporaneamente, con un solo passaggio.

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Eliminare più utenti contemporaneamente

Vedere il cmdlet [Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) di PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Risolvere i problemi relativi all'eliminazione di un utente

Ecco i problemi più comuni che si verificano quando si elimina un utente:
  
- **Viene visualizzato un messaggio di errore che indica che l'utente non può essere eliminato. Riprovare più tardi."** Verificare se l'account è configurato per l'inoltro della posta elettronica oppure se è stato convertito in una cassetta postale condivisa. Entrambi causeranno l'errore. Non eliminare l'account se ha inoltrato la posta elettronica o se è stato convertito in una cassetta postale condivisa.

- **Non si hanno le autorizzazioni appropriate per eliminare un utente**. Solo gli utenti che sono amministratori globali [di Microsoft 365](about-admin-roles.md) o amministratori di gestione degli utenti possono eliminare gli utenti. Si tratta in genere del supporto tecnico dell'istituto di istruzione o dell'azienda.

- **L'utente viene eliminato, ma il nome continua a comparire nella Rubrica globale**. Questo accade quando un'azienda usa Active Directory. È necessario eliminare l'account utente da Active Directory. Per istruzioni, vedere [Eliminare un account utente.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Si desidera eliminare Microsoft 365 dal computer? Passare a [Annulla l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)
  
[Eliminare definitivamente una cassetta postale](/exchange/permanently-delete-a-mailbox-exchange-2013-help)

[Rimuovere un ex dipendente da Office 365](remove-former-employee.md)

[Aggiungere un nuovo dipendente a Office 365](add-new-employee.md)

[Eliminare un account utente:](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))seguire queste istruzioni se l'azienda usa **Active Directory** che esegue la sincronizzazione con Azure AD. Non è possibile farlo da Office 365.