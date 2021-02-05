---
title: Risoluzione dei conflitti di licenze
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Informazioni su come risolvere i conflitti di licenza con l'abbonamento a Microsoft 365 per le aziende.
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114454"
---
# <a name="resolve-license-conflicts"></a>Risoluzione dei conflitti di licenze

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

È consigliabile acquistare le licenze necessarie per l'abbonamento prima di creare nuovi utenti. In questo modo, quando si creano gli account utente sarà possibile assegnare una licenza ai nuovi utenti. Se tutte le licenze disponibili sono già state assegnate agli utenti, ma alcune di esse sono scadute, oppure se si prova a rimuovere una licenza già assegnata a un utente, si verificheranno conflitti di licenza. Per ulteriori informazioni, vedere [Rimuovere licenze dall'abbonamento.](../../commerce/licenses/remove-licenses-from-subscription.md)
  
## <a name="how-do-i-view-license-conflicts"></a>Come si visualizzano i conflitti di licenza?

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenze</a>.

::: moniker-end

2. Osservare la colonna **Stato** per informazioni sul conflitto. In caso di conflitto, verrà visualizzato un messaggio di avviso che indica che uno o più utenti necessitano di una licenza valida.

    > [!NOTE]
    > Se non è presente alcun conflitto, la colonna **Stato** non viene visualizzata.

## <a name="how-do-i-resolve-license-conflicts"></a>Come si risolvono i conflitti di licenza?

È possibile risolvere i conflitti di licenza [acquistando](../../commerce/licenses/buy-licenses.md) altre licenze o rimuovendo le licenze dagli utenti [che non ne hanno più bisogno.](remove-licenses-from-users.md) È possibile [eliminare un account utente per liberare una licenza](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Articoli correlati

[Assegnazione licenze agli utenti](assign-licenses-to-users.md).
  
[Rimuovere licenze dagli utenti](remove-licenses-from-users.md)
