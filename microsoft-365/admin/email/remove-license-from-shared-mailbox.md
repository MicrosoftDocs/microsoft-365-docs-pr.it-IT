---
title: Rimuovere una licenza da cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Rimuovere una licenza da una cassetta postale condivisa per assegnarla a un altro utente o restituire la licenza in modo da non pagarla. '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706287"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Rimuovere una licenza da una cassetta postale condivisa

Le cassette postali condivise in genere non richiedono una licenza. Seguire queste istruzioni per rimuovere una licenza da una cassetta postale condivisa in modo che sia possibile assegnarla a un utente o restituire la licenza in modo che non si paga per una licenza non necessaria.

> [!NOTE]
>
> Una licenza è necessaria negli scenari seguenti:
>
> 1. La cassetta postale condivisa dispone di più di 50 GB di spazio di archiviazione in uso.
> 2. La cassetta postale condivisa utilizza l'archiviazione sul posto.
> 3. La cassetta postale condivisa viene messa in conservazione per controversia legale.
> 4. Alla cassetta postale condivisa è assegnata una licenza di Microsoft Defender.

## <a name="remove-the-license"></a>Rimuovere la licenza

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

   > [!NOTE]
   > È necessario rimuovere la licenza dalla pagina Utenti attivi. Non è possibile rimuovere la licenza dalla pagina Cassetta postale condivisa perché le licenze sono impostazioni utente.
  
2. Selezionare la cassetta postale condivisa.

3. Nella scheda **Licenze e app** espandi **Licenze** e deseleziona la casella per la licenza che vuoi rimuovere.

4. Selezionare **Salva modifiche**.

5. Quando si torna alla **pagina Utenti** attivi, lo stato della cassetta postale condivisa sarà **Senza licenza.**

6. Stai ancora pagando la licenza. Per interrompere il pagamento, [rimuovi la licenza dall'abbonamento.](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>Contenuto correlato

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)\
[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)\
[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md) (articolo)\
[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)\
[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md) (articolo)
