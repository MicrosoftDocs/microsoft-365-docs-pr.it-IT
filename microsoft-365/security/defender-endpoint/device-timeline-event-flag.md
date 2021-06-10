---
title: Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint
description: Usare i flag di evento della sequenza temporale di Microsoft Defender per il dispositivo endpoint per
keywords: Defender for Endpoint device timeline, event flags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165154"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

I flag di evento nella sequenza temporale del dispositivo Defender for Endpoint ti aiutano a filtrare e organizzare eventi specifici quando stai analizzando potenziali attacchi.

La sequenza temporale del dispositivo Defender for Endpoint fornisce una visualizzazione cronologica degli eventi e degli avvisi associati osservati in un dispositivo. Questo elenco di eventi offre visibilità completa su eventi, file e indirizzi IP osservati nel dispositivo. L'elenco può talvolta essere lungo. I flag degli eventi della sequenza temporale del dispositivo consentono di tenere traccia degli eventi che potrebbero essere correlati. 

Dopo aver attraversato una sequenza temporale del dispositivo, puoi ordinare, filtrare ed esportare gli eventi specifici contrassegnati.

Durante l'esplorazione della sequenza temporale del dispositivo, puoi cercare e filtrare eventi specifici. Puoi impostare i flag di evento: 

- Evidenziazione degli eventi più importanti 
- Contrassegno di eventi che richiedono un'immersione approfondita 
- Creazione di una sequenza temporale di violazione pulita



## <a name="flag-an-event"></a>Contrassegnare un evento
1. Trovare l'evento che si desidera contrassegnare
2. Fare clic sull'icona del contrassegno nella colonna Contrassegno. 
![Immagine del contrassegno sequenza temporale del dispositivo](images/device-flags.png)

## <a name="view-flagged-events"></a>Visualizzare gli eventi contrassegnati  
1. Nella sezione Filtri **sequenza temporale** abilita **Eventi contrassegnati.**
2. Fare clic su **Applica**. Vengono visualizzati solo gli eventi contrassegnati.
È possibile applicare filtri aggiuntivi facendo clic sulla barra del tempo. Verranno visualizzati solo gli eventi prima dell'evento contrassegnato.  
![Immagine del contrassegno della sequenza temporale del dispositivo con filtro su](images/device-flag-filter.png)
