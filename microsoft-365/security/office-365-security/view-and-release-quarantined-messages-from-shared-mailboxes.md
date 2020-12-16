---
title: Visualizzare e rilasciare i messaggi in quarantena dalle cassette postali condivise
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gli utenti possono imparare a visualizzare e ad agire sui messaggi in quarantena inviati alle cassette postali condivise a cui hanno le autorizzazioni.
ms.openlocfilehash: 34a401d3bff66926acd3e04d7144ce465dfa3dbb
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688030"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Visualizzare e rilasciare i messaggi in quarantena dalle cassette postali condivise

> [!NOTE]
> Le funzionalità descritte in questo articolo sono attualmente in anteprima, non sono disponibili per tutti gli utenti e sono soggette a modifiche.

Gli utenti possono gestire i messaggi in quarantena in cui sono uno dei destinatari, come descritto in [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md). Ma che dire delle cassette postali condivise in cui l'utente ha accesso completo e Invia come o Invia per conto di le autorizzazioni alla cassetta postale come descritto in [cassette postali condivise in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?

In precedenza, la possibilità per gli utenti di gestire i messaggi in quarantena inviati a una cassetta postale condivisa richiedeva agli amministratori di lasciare l'automapping abilitato per la cassetta postale condivisa (abilitata per impostazione predefinita quando un amministratore fornisce a un utente l'accesso a un'altra cassetta postale). Tuttavia, a seconda delle dimensioni e del numero di cassette postali a cui l'utente ha accesso, le prestazioni possono subire un tentativo di apertura di *tutte* le cassette postali a cui l'utente ha accesso. Per questo motivo, molti amministratori scelgono di [rimuovere la mappatura automapping per le cassette postali condivise](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).

A questo punto, la mappatura automapping non è più necessaria per consentire agli utenti di gestire i messaggi in quarantena inviati alle cassette postali condivise. Funziona solo. Sono disponibili due metodi diversi per accedere ai messaggi in quarantena inviati a una cassetta postale condivisa:

- Se l'amministratore ha [abilitato le notifiche di posta indesiderata dell'utente finale](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) nei criteri di protezione da posta indesiderata, qualsiasi utente che ha accesso alle notifiche di posta indesiderata dell'utente finale nella cassetta postale condivisa può fare clic sul pulsante **Verifica** nella notifica per passare alla quarantena nel centro sicurezza & conformità. Si noti che questo metodo consente solo agli utenti di gestire i messaggi in quarantena che sono stati inviati alla cassetta postale condivisa. Gli utenti non possono gestire i propri messaggi in quarantena in questo contesto.

- L'utente può [accedere alla quarantena nel centro sicurezza & conformità](find-and-release-quarantined-messages-as-a-user.md). Per impostazione predefinita, vengono visualizzati solo i messaggi inviati all'utente. Tuttavia, l'utente può modificare i **risultati dell'ordinamento** (il **pulsante ID messaggio** per impostazione predefinita) nell' **indirizzo di posta elettronica del destinatario**, immettere l'indirizzo di posta elettronica della cassetta postale condivisa e quindi fare clic su **Aggiorna** per visualizzare i messaggi in quarantena inviati alla cassetta postale condivisa.

  ![Ordinamento dei messaggi in quarantena in base all'indirizzo di posta elettronica del destinatario.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Indipendentemente dal metodo, gli utenti possono evitare confusione includendo la colonna **destinatario** per i messaggi in quarantena. Il numero massimo di colonne da visualizzare è 7, quindi l'utente dovrà fare clic su **modifica colonne**, rimuovere una colonna esistente (ad esempio, **tipo di criterio**), **selezionare destinatario** e quindi fare clic su **Salva** o **Salva con nome predefinito**.

  ![Rimuovere la colonna tipo di criterio e aggiungere la colonna destinatario alla quarantena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Considerazioni importanti

- Il primo utente che agisce sul messaggio in quarantena decide il destino del messaggio per tutti gli utenti che utilizzano la cassetta postale condivisa. Ad esempio, se si accede a una cassetta postale condivisa da 10 utenti e un utente decide di eliminare il messaggio di quarantena, il messaggio viene eliminato per tutti e 10 gli utenti. Analogamente, se un utente decide di rilasciare il messaggio, viene rilasciato alla cassetta postale condivisa ed è accessibile da tutti gli altri utenti della cassetta postale condivisa.

- Attualmente, il pulsante **Blocca mittente** non è disponibile nel riquadro a comparsa **Dettagli** per i messaggi in quarantena che sono stati inviati alla cassetta postale condivisa.

- Per gestire i messaggi in quarantena per la cassetta postale condivisa in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), l'utente finale dovrà utilizzare il cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) con l'indirizzo di posta elettronica della cassetta postale condivisa per il valore del parametro _RecipientAddress_ per identificare i messaggi. Ad esempio:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  L'utente finale può quindi selezionare un messaggio in quarantena dall'elenco per visualizzare o eseguire un'azione.

  In questo esempio vengono visualizzati tutti i messaggi in quarantena inviati alla cassetta postale condivisa e quindi il primo messaggio viene rilasciato dall'elenco dalla quarantena (il primo messaggio nell'elenco è 0, il secondo è 1 e così via).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Per ulteriori informazioni sulla sintassi e sui parametri, vedere:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Anteprima-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
