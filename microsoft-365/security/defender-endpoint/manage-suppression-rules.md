---
title: Gestire le regole di eliminazione di Microsoft Defender per endpoint
description: Potrebbe essere necessario impedire la visualizzazione degli avvisi nel portale utilizzando le regole di eliminazione. Scopri come gestire le regole di eliminazione in Microsoft Defender per Endpoint.
keywords: gestire l'eliminazione, le regole, il nome della regola, l'ambito, l'azione, gli avvisi, attivare, disattivare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454758"
---
# <a name="manage-suppression-rules"></a>Gestire le regole di eliminazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Potrebbero essere presenti scenari in cui è necessario eliminare la visualizzazione degli avvisi nel portale. È possibile creare regole di eliminazione per avvisi specifici noti come innocui, ad esempio strumenti o processi noti nell'organizzazione. Per ulteriori informazioni su come eliminare gli avvisi, vedere [Eliminazione di avvisi.](manage-alerts.md)

È possibile visualizzare un elenco di tutte le regole di eliminazione e gestirle in un'unica posizione. È inoltre possibile attivare o disattivare una regola di eliminazione degli avvisi.


1. Nel riquadro di spostamento, **selezionare** Impostazioni  >  **Endpoint Regole**  >    >  **Eliminazione avviso**. Viene visualizzato l'elenco delle regole di eliminazione create dagli utenti dell'organizzazione.

2. Selezionare una regola facendo clic sulla casella di controllo accanto al nome della regola.

3. Fare **clic su Attiva regola,** Modifica **regola** o **Elimina regola.** Quando si apportano modifiche a una regola, è possibile scegliere di rilasciare gli avvisi già eliminati, indipendentemente dal fatto che corrispondano o meno ai nuovi criteri. 


## <a name="view-details-of-a-suppression-rule"></a>Visualizzare i dettagli di una regola di eliminazione

1. Nel riquadro di spostamento, **selezionare** Impostazioni  >  **Endpoint Regole**  >    >  **Eliminazione avviso**. Viene visualizzato l'elenco delle regole di eliminazione create dagli utenti dell'organizzazione.

2. Fare clic sul nome di una regola. Vengono visualizzati i dettagli della regola. Verranno visualizzati i dettagli della regola, ad esempio stato, ambito, azione, numero di avvisi corrispondenti, creati da e data di creazione della regola. È inoltre possibile visualizzare gli avvisi associati e le condizioni della regola.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire gli avvisi](manage-alerts.md)
