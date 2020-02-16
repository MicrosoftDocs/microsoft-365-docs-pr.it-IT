---
title: Gestione autorizzazioni gruppo di ruoli di amministratore in EOP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 01676fab3ed69120a35687d1c6939cb466b8d672
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082915"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>Gestire autorizzazioni gruppo di ruoli di amministratore in Exchange Online Protection

In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 5-10 minuti

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Utenti, contatti e gruppi di ruoli" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Aggiunta dei membri a gruppi di ruoli tramite EAC

1. Nell'interfaccia di amministrazione di Exchange, andare a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli a cui si desidera aggiungere l'utente o gli utenti](../../media/ITPro-EAC-EditIcon.gif), quindi fare clic su **modifica** ![icona modifica.

2. In membri fare clic su **Aggiungi** ![icona](../../media/ITPro-EAC-AddIcon.gif). Viene visualizzata la finestra Seleziona membri.

3. Cercare l'utente o gli utenti da aggiungere o selezionarli dall'elenco.

4. Una volta selezionati gli utenti che si desidera aggiungere, fare clic su **Aggiungi**, quindi fare clic su **OK**. La finestra Seleziona membri si chiude.

5. L'utente sarà stato aggiunto al riquadro **Membri**. Fare clic su **Salva**.

   > [!NOTE]
   > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Rimozione di membri da un gruppo di ruoli di amministratore tramite EAC

1. Nell'interfaccia di amministrazione di Exchange, andare a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli da cui si desidera rimuovere un utente o utenti e](../../media/ITPro-EAC-EditIcon.gif)quindi fare clic su **modifica** ![icona modifica.

2. In membri, selezionare l'utente o gli utenti che si desidera rimuovere e fare **** ![clic su Rimuovi](../../media/ITPro-EAC-RemoveIcon.gif)icona Rimuovi.

3. Fare clic su **Salva** per salvare la modifica al gruppo di ruoli e tornare alla pagina **Ruoli amministratore**. Per verificare di aver rimosso correttamente l'utente dal gruppo di ruoli amministratore, assicurarsi che il membro non venga più visualizzato in Membri nel riquadro dei dettagli del gruppo di ruoli selezionato.

   > [!NOTE]
   > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.

## <a name="for-more-information"></a>Ulteriori informazioni

[Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md)
