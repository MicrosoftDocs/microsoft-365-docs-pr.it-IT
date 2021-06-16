---
title: Visualizzare e rilasciare i messaggi in quarantena dalle cassette postali condivise
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gli utenti possono imparare a visualizzare e agire sui messaggi in quarantena inviati alle cassette postali condivise per cui dispongono delle autorizzazioni.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d6aed4a6e3bc725635558a5e8394b671d11f47c
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929852"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Visualizzare e rilasciare i messaggi in quarantena dalle cassette postali condivise

> [!NOTE]
> Le funzionalità descritte in questo articolo sono attualmente disponibili in Anteprima, non sono disponibili per tutti e sono soggette a modifiche.

Gli utenti possono gestire i messaggi in quarantena in cui sono uno dei destinatari, come descritto in Trovare e rilasciare i messaggi in quarantena [come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md) Ma per quanto riguarda le cassette postali condivise in cui l'utente dispone delle autorizzazioni Accesso completo e Invia come o Invia per conto della cassetta postale, come descritto in Cassette postali condivise [in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)?

In precedenza, la possibilità per gli utenti di gestire i messaggi in quarantena inviati a una cassetta postale condivisa richiedeva agli amministratori di lasciare abilitato il mapping automatico per la cassetta postale condivisa (è abilitato per impostazione predefinita quando un amministratore concede a un utente l'accesso a un'altra cassetta postale). Tuttavia, a seconda delle dimensioni e del numero di cassette postali a cui  l'utente ha accesso, le prestazioni possono risentirne quando Outlook tenta di aprire tutte le cassette postali a cui l'utente ha accesso. Per questo motivo, molti amministratori scelgono di rimuovere [il mapping automatico per le cassette postali condivise.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

A questo punto, il mapping automatico non è più necessario per consentire agli utenti di gestire i messaggi in quarantena inviati alle cassette postali condivise. Funziona solo. Esistono due metodi diversi per accedere ai messaggi in quarantena inviati a una cassetta postale condivisa:

- Se l'amministratore ha abilitato le notifiche di posta indesiderata dell'utente finale nei criteri di protezione da  posta [indesiderata,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)qualsiasi utente che ha accesso alle notifiche di posta indesiderata dell'utente finale nella cassetta postale condivisa può fare clic sul pulsante Revisione nella notifica per andare in quarantena nel portale di Microsoft 365 Defender. Si noti che questo metodo consente solo agli utenti di gestire i messaggi in quarantena inviati alla cassetta postale condivisa. Gli utenti non possono gestire i propri messaggi di quarantena in questo contesto.

- L'utente [può passare alla quarantena nel portale Microsoft 365 Defender.](find-and-release-quarantined-messages-as-a-user.md) Per impostazione predefinita, vengono visualizzati solo i messaggi inviati all'utente. Tuttavia, l'utente può modificare i risultati dell'ordinamento **(il** pulsante **ID** messaggio per impostazione  predefinita) in Indirizzo di posta elettronica **destinatario,** immettere l'indirizzo di posta elettronica della cassetta postale condivisa e quindi fare clic su Aggiorna per visualizzare i messaggi in quarantena inviati alla cassetta postale condivisa.

  ![Ordinamento dei messaggi in quarantena in base all'indirizzo di posta elettronica del destinatario.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Indipendentemente dal metodo, gli utenti possono evitare confusione includendo la **colonna Destinatario** per i messaggi in quarantena. Il numero massimo di colonne da visualizzare è 7, quindi l'utente dovrà fare clic su Modifica **colonne,** rimuovere una colonna esistente (ad **esempio,** Tipo di criterio), selezionare  **Destinatario** e quindi fare clic su Salva o Salva come **predefinita.**

  ![Rimuovere la colonna Tipo di criterio e aggiungere la colonna Destinatario in quarantena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Considerazioni importanti

- Il primo utente che agisce sul messaggio in quarantena decide la sorte del messaggio per tutti gli utenti che utilizzano la cassetta postale condivisa. Ad esempio, se si accede a una cassetta postale condivisa da 10 utenti e un utente decide di eliminare il messaggio di quarantena, il messaggio viene eliminato per tutti e 10 gli utenti. Analogamente, se un utente decide di rilasciare il messaggio, viene rilasciato nella cassetta postale condivisa ed è accessibile da tutti gli altri utenti della cassetta postale condivisa.

- Attualmente, il **pulsante Blocca** mittente  non è disponibile nel riquadro a comparsa Dettagli per i messaggi in quarantena inviati alla cassetta postale condivisa.

- Per quanto riguarda le operazioni di quarantena per le cassette postali condivise, se si utilizzano gruppi di sicurezza annidati per concedere l'accesso a una cassetta postale condivisa, è consigliabile non più di due livelli di gruppi annidati. Ad esempio, il gruppo A è un membro del Gruppo B, membro del Gruppo C. Per assegnare le autorizzazioni a una cassetta postale condivisa, non aggiungere l'utente al gruppo A e quindi assegnare il gruppo C alla cassetta postale condivisa.  

- Per gestire i messaggi in quarantena per la cassetta postale condivisa in [Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell)l'utente finale dovrà utilizzare il cmdlet [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) con l'indirizzo di posta elettronica della cassetta postale condivisa per il valore del parametro _RecipientAddress_ per identificare i messaggi. Ad esempio:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  L'utente finale può quindi selezionare un messaggio in quarantena dall'elenco per visualizzare o eseguire un'azione.

  In questo esempio vengono visualizzati tutti i messaggi in quarantena inviati alla cassetta postale condivisa e quindi il primo messaggio nell'elenco viene rilasciato dalla quarantena (il primo messaggio nell'elenco è 0, il secondo è 1 e così via).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Per ulteriori informazioni sulla sintassi e sui parametri, vedere:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
