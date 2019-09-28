---
title: Gestione autorizzazioni gruppo di ruoli di amministratore in EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Gli amministratori possono imparare a assegnare o rimuovere le autorizzazioni nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online Protection.
ms.openlocfilehash: 9b82836b5f9f28c3055e540890771def28382d2b
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306130"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="95702-103">Gestire autorizzazioni gruppo di ruoli di amministratore in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="95702-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="95702-p101">In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="95702-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95702-106">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="95702-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95702-107">Tempo stimato per il completamento: 5-10 minuti</span><span class="sxs-lookup"><span data-stu-id="95702-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="95702-108">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="95702-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="95702-p102">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Utenti, contatti e gruppi di ruoli" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="95702-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="95702-111">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="95702-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="95702-112">Problemi?</span><span class="sxs-lookup"><span data-stu-id="95702-112">Having problems?</span></span> <span data-ttu-id="95702-113">Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="95702-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="95702-114">Aggiunta dei membri a gruppi di ruoli tramite EAC</span><span class="sxs-lookup"><span data-stu-id="95702-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="95702-115">Nell'interfaccia di amministrazione di Exchange, andare a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli a cui si desidera aggiungere l'utente o gli utenti](../media/ITPro-EAC-EditIcon.gif), quindi fare clic su **modifica** ![icona modifica.</span><span class="sxs-lookup"><span data-stu-id="95702-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="95702-116">In membri fare clic su **Aggiungi** ![icona](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="95702-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="95702-117">Viene visualizzata la finestra Seleziona membri.</span><span class="sxs-lookup"><span data-stu-id="95702-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="95702-118">Cercare l'utente o gli utenti da aggiungere o selezionarli dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="95702-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="95702-p105">Una volta selezionati gli utenti che si desidera aggiungere, fare clic su **Aggiungi**, quindi fare clic su **OK**. La finestra Seleziona membri si chiude.</span><span class="sxs-lookup"><span data-stu-id="95702-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="95702-p106">L'utente sarà stato aggiunto al riquadro **Membri**. Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95702-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95702-123">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="95702-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="95702-124">Rimozione di membri da un gruppo di ruoli di amministratore tramite EAC</span><span class="sxs-lookup"><span data-stu-id="95702-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="95702-125">Nell'interfaccia di amministrazione di Exchange, andare a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli da cui si desidera rimuovere un utente o utenti e](../media/ITPro-EAC-EditIcon.gif)quindi fare clic su **modifica** ![icona modifica.</span><span class="sxs-lookup"><span data-stu-id="95702-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="95702-126">In membri, selezionare l'utente o gli utenti che si desidera rimuovere e fare \*\*\*\* ![clic su Rimuovi](../media/ITPro-EAC-RemoveIcon.gif)icona Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="95702-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="95702-p107">Fare clic su **Salva** per salvare la modifica al gruppo di ruoli e tornare alla pagina **Ruoli amministratore**. Per verificare di aver rimosso correttamente l'utente dal gruppo di ruoli amministratore, assicurarsi che il membro non venga più visualizzato in Membri nel riquadro dei dettagli del gruppo di ruoli selezionato.</span><span class="sxs-lookup"><span data-stu-id="95702-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95702-129">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="95702-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="95702-130">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="95702-130">For more information</span></span>

[<span data-ttu-id="95702-131">Autorizzazioni di funzionalità in EOP</span><span class="sxs-lookup"><span data-stu-id="95702-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
