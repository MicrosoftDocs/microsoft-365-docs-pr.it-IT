---
title: Rimuovere licenze dall'abbonamento a Office 365 per le aziende
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
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: Informazioni su come rimuovere una licenza dall'abbonamento a Office 365 for business quando la licenza è già assegnata a un utente.
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242327"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>Rimuovere licenze dall'abbonamento a Office 365 per le aziende

Non è possibile rimuovere una licenza da un abbonamento se è assegnata a un utente. Se si desidera rimuovere una licenza che è attualmente assegnata a un utente, sarà necessario [rimuovere-licenze-da-utenti](../../admin/manage/remove-licenses-from-users.md)) prima di poter rimuovere la licenza dall'abbonamento.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

## <a name="remove-licenses"></a>Remove licenses

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prodotti e servizi</a>.

2. Nella pagina **prodotti & Servizi** individuare la sottoscrizione da cui si desidera rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi selezionare **Invia modifica**. Ad esempio, se si hanno 110 licenze e occorre rimuoverne 5, immettere 105.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abbonamenti</a> di fatturazione.

2. Nella pagina **abbonamenti** selezionare l'abbonamento da cui si desidera rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi selezionare **Invia**. Ad esempio, se si hanno 110 licenze e occorre rimuoverne 5, immettere 105.


::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">abbonamenti</a> di fatturazione.

2. Nella pagina **abbonamenti** selezionare l'abbonamento da cui si desidera rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi selezionare **Invia**. Ad esempio, se si hanno 110 licenze e occorre rimuoverne 5, immettere 105.

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?

Questa sezione descrive i motivi per cui il collegamento **Aggiungi/Rimuovi licenze** potrebbe non essere disponibile e spiega cosa è possibile fare.
  
### <a name="a-credit-check-is-pending"></a>È in sospeso una verifica del credito

Se è in sospeso una verifica del credito, verrà visualizzato il messaggio "Verifica del credito in sospes"o e non sarà possibile rimuovere licenze finché non viene completata. Attendere e quindi controllare se la verifica del credito è stata completata. In genere sono necessari fino a due giorni lavorativi.
  
Una volta completata la verifica del credito, il collegamento **Aggiungi/rimuovi licenze** dovrebbe comparire nella sezione **Utenti**. In caso affermativo, andare a [rimuovere le licenze dall'abbonamento a Office 365 for business](#remove-licenses-from-your-office-365-for-business-subscription).
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>L'abbonamento è stato attivato usando un codice Product Key

Se l'abbonamento è stato acquistato e attivato usando un codice Product Key di 25 caratteri, verrà visualizzato il messaggio "Prepagato". Se l'abbonamento è stato prepagato usando un codice Product Key, non è possibile rimuovere licenze, in quanto sono già state pagate. È tuttavia possibile rimuovere le licenze aggiuntive quando si rinnova l'abbonamento.
  
### <a name="you-bought-your-subscription-through-a-partner"></a>L'abbonamento è stato acquistato tramite un partner

Se l'abbonamento è stato acquistato tramite un provider o un partner, non è possibile rimuovere le licenze. Contattare il provider di servizi di crittografia o utilizzare il collegamento VLSC (Volume Licensing Service Center) per contattare il partner per ottenere assistenza.
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>Informazioni utili sulla rimozione di licenze dagli utenti Office 365 per le aziende

- È necessario essere un amministratore globale o un amministratore di gestione utenti. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Usare questa procedura per aggiungere una licenza a un account utente esistente. [Come aggiungere un account utente e al contempo assegnargli una licenza](../../admin/add-users/add-users.md).

## <a name="articles-about-managing-licenses-for-your-subscription"></a>Articoli sulla gestione delle licenze per l'abbonamento

- [Informazioni su abbonamenti e licenze](subscriptions-and-licenses.md)

- [Rimuovere licenze dagli utenti](../../admin/manage/remove-licenses-from-users.md)

- [Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md)

- [Acquistare le licenze per l'abbonamento](buy-licenses.md)

- [Acquistare un altro abbonamento](../buy-another-subscription.md)

- [Acquistare o modificare un componente aggiuntivo](../buy-or-edit-an-add-on.md)

- [Gestire le licenze utente di Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>Collegamenti correlati

[Annullare l'abbonamento](../subscriptions/cancel-your-subscription.md)
