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
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570962"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="6a903-103">Visualizzare e rilasciare i messaggi in quarantena dalle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="6a903-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="6a903-104">Le funzionalità descritte in questo articolo sono attualmente in anteprima, non sono disponibili per tutti gli utenti e sono soggette a modifiche.</span><span class="sxs-lookup"><span data-stu-id="6a903-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="6a903-105">Gli utenti possono gestire i messaggi in quarantena in cui sono uno dei destinatari, come descritto in [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6a903-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6a903-106">Ma che dire delle cassette postali condivise in cui l'utente ha accesso completo e Invia come o Invia per conto di le autorizzazioni alla cassetta postale come descritto in [cassette postali condivise in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span><span class="sxs-lookup"><span data-stu-id="6a903-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="6a903-107">In precedenza, la possibilità per gli utenti di gestire i messaggi in quarantena inviati a una cassetta postale condivisa richiedeva agli amministratori di lasciare l'automapping abilitato per la cassetta postale condivisa (abilitata per impostazione predefinita quando un amministratore fornisce a un utente l'accesso a un'altra cassetta postale).</span><span class="sxs-lookup"><span data-stu-id="6a903-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="6a903-108">Tuttavia, a seconda delle dimensioni e del numero di cassette postali a cui l'utente ha accesso, le prestazioni possono subire un tentativo di apertura di *tutte* le cassette postali a cui l'utente ha accesso.</span><span class="sxs-lookup"><span data-stu-id="6a903-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="6a903-109">Per questo motivo, molti amministratori scelgono di [rimuovere la mappatura automapping per le cassette postali condivise](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6a903-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6a903-110">A questo punto, la mappatura automapping non è più necessaria per consentire agli utenti di gestire i messaggi in quarantena inviati alle cassette postali condivise.</span><span class="sxs-lookup"><span data-stu-id="6a903-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="6a903-111">Funziona solo.</span><span class="sxs-lookup"><span data-stu-id="6a903-111">It just works.</span></span> <span data-ttu-id="6a903-112">Sono disponibili due metodi diversi per accedere ai messaggi in quarantena inviati a una cassetta postale condivisa:</span><span class="sxs-lookup"><span data-stu-id="6a903-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="6a903-113">Se l'amministratore ha [abilitato le notifiche di posta indesiderata dell'utente finale](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) nei criteri di protezione da posta indesiderata, qualsiasi utente che ha accesso alle notifiche di posta indesiderata dell'utente finale nella cassetta postale condivisa può fare clic sul pulsante **Verifica** nella notifica per passare alla quarantena nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="6a903-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="6a903-114">Si noti che questo metodo consente solo agli utenti di gestire i messaggi in quarantena che sono stati inviati alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6a903-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="6a903-115">Gli utenti non possono gestire i propri messaggi in quarantena in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="6a903-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="6a903-116">L'utente può [accedere alla quarantena nel centro sicurezza & conformità](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6a903-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="6a903-117">Per impostazione predefinita, vengono visualizzati solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="6a903-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="6a903-118">Tuttavia, l'utente può modificare i **risultati dell'ordinamento** (il **pulsante ID messaggio** per impostazione predefinita) nell' **indirizzo di posta elettronica del destinatario**, immettere l'indirizzo di posta elettronica della cassetta postale condivisa e quindi fare clic su **Aggiorna** per visualizzare i messaggi in quarantena inviati alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6a903-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![Ordinamento dei messaggi in quarantena in base all'indirizzo di posta elettronica del destinatario.](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="6a903-120">Indipendentemente dal metodo, gli utenti possono evitare confusione includendo la colonna **destinatario** per i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="6a903-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="6a903-121">Il numero massimo di colonne da visualizzare è 7, quindi l'utente dovrà fare clic su **modifica colonne**, rimuovere una colonna esistente (ad esempio, **tipo di criterio**), **selezionare destinatario** e quindi fare clic su **Salva** o **Salva con nome predefinito**.</span><span class="sxs-lookup"><span data-stu-id="6a903-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![Rimuovere la colonna tipo di criterio e aggiungere la colonna destinatario alla quarantena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="6a903-123">Considerazioni importanti</span><span class="sxs-lookup"><span data-stu-id="6a903-123">Things to keep in mind</span></span>

- <span data-ttu-id="6a903-124">Il primo utente che agisce sul messaggio in quarantena decide il destino del messaggio per tutti gli utenti che utilizzano la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6a903-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="6a903-125">Ad esempio, se si accede a una cassetta postale condivisa da 10 utenti e un utente decide di eliminare il messaggio di quarantena, il messaggio viene eliminato per tutti e 10 gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6a903-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="6a903-126">Analogamente, se un utente decide di rilasciare il messaggio, viene rilasciato alla cassetta postale condivisa ed è accessibile da tutti gli altri utenti della cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6a903-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="6a903-127">Attualmente, se un utente seleziona più messaggi in quarantena inviati alla cassetta postale condivisa, quando l'utente fa clic su **rilascia i** messaggi o **Elimina i messaggi** nel riquadro a comparsa azioni in **blocco** , vengono restituiti i seguenti errori di errore.</span><span class="sxs-lookup"><span data-stu-id="6a903-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="6a903-128">Non si dispone dell'autorizzazione per rilasciare tutti i messaggi in quarantena selezionati.</span><span class="sxs-lookup"><span data-stu-id="6a903-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="6a903-129">Non si dispone dell'autorizzazione necessaria per eliminare tutti i messaggi in quarantena selezionati.</span><span class="sxs-lookup"><span data-stu-id="6a903-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="6a903-130">Indipendentemente dall'errore, l'azione viene eseguita sui messaggi e l'errore può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="6a903-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![Errore false quando si rilascia o si eliminano i messaggi in quarantena inviati a una cassetta postale condivisa.](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="6a903-132">Attualmente, il pulsante **Blocca mittente** non è disponibile nel riquadro a comparsa **Dettagli** per i messaggi in quarantena che sono stati inviati alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6a903-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="6a903-133">Per gestire i messaggi in quarantena per la cassetta postale condivisa in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), l'utente finale dovrà utilizzare il cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) con l'indirizzo di posta elettronica della cassetta postale condivisa per il valore del parametro _RecipientAddress_ per identificare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a903-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="6a903-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6a903-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="6a903-135">L'utente finale può quindi selezionare un messaggio in quarantena dall'elenco per visualizzare o eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="6a903-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="6a903-136">In questo esempio vengono visualizzati tutti i messaggi in quarantena inviati alla cassetta postale condivisa e quindi il primo messaggio viene rilasciato dall'elenco dalla quarantena (il primo messaggio nell'elenco è 0, il secondo è 1 e così via).</span><span class="sxs-lookup"><span data-stu-id="6a903-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="6a903-137">Per ulteriori informazioni sulla sintassi e sui parametri, vedere:</span><span class="sxs-lookup"><span data-stu-id="6a903-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="6a903-138">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6a903-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="6a903-139">Get-QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="6a903-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="6a903-140">Anteprima-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6a903-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="6a903-141">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6a903-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
