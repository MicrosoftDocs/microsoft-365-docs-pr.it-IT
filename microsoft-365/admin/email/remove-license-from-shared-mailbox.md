---
title: Rimuovere una licenza da cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Rimuovere la licenza da una cassetta postale condivisa per assegnarla a un altro utente. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698304"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Rimuovere una licenza da una cassetta postale condivisa

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Le cassette postali condivise in genere non richiedono una licenza. Seguire queste istruzioni per rimuovere una licenza da una cassetta postale condivisa, in modo da poterla assegnare a un utente o restituire la licenza in modo da non pagare una licenza non necessaria.

> [!NOTE]
> Una licenza è necessaria negli scenari seguenti:
> 1. La cassetta postale condivisa dispone di più di 50 GB di spazio di archiviazione in uso.
> 2. La cassetta postale condivisa utilizza l'archiviazione sul posto.
> 3. La cassetta postale condivisa viene conservata per controversia legale.
> 4. Alla cassetta postale condivisa è assegnata una licenza di Microsoft Defender.

  
## <a name="remove-the-license"></a>Rimuovere la licenza

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

   > [!NOTE]
   > È necessario rimuovere la licenza dalla pagina Utenti attivi. Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente. 
  
2. Selezionare la cassetta postale condivisa.

3. Nella scheda **Licenze e app** espandi **Licenze** e deseleziona la casella per la licenza che vuoi rimuovere.

4. Selezionare **Salva modifiche**.

5. Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**

6. Stai ancora pagando la licenza. Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

    > [!NOTE]
    > È necessario rimuovere la licenza dalla pagina Utenti attivi. Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.

2. Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze di prodotto.**

3. Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.

4. Selezionare **Salva**.

5. Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**

6. Stai ancora pagando la licenza. Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

    > [!NOTE]
    > È necessario rimuovere la licenza dalla pagina Utenti attivi. Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.

2. Selezionare la cassetta postale condivisa, quindi selezionare **Modifica** accanto a **Licenze di prodotto.**

3. Nella pagina **Licenze di** prodotto imposta l'interruttore su **Disattivato** per la licenza che vuoi rimuovere.

4. Selezionare **Salva**.

5. Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**

6. Stai ancora pagando la licenza. Per interrompere il pagamento, [rimuovere la licenza dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)

::: moniker-end 

 

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
