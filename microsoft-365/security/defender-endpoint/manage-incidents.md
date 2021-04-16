---
title: Gestire gli eventi imprevisti di Microsoft Defender for Endpoint
description: Gestire gli eventi imprevisti assegnandolo, aggiornandone lo stato o impostandone la classificazione.
keywords: incidenti, gestire, assegnare, stato, classificazione, avviso vero, falso avviso
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: abb538972b48f8790286c0a546eecdd69fc83fb5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862140"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Gestire gli eventi imprevisti di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La gestione degli incidenti è una parte importante di ogni operazione di cybersecurity. È possibile gestire gli eventi imprevisti selezionando un evento imprevisto nella coda Eventi imprevisti **o** nel **riquadro Gestione eventi imprevisti.** 


Se si seleziona un evento imprevisto dalla **coda** Eventi imprevisti, viene visualizzato il **riquadro Gestione** eventi imprevisti in cui è possibile aprire la pagina dell'evento imprevisto per i dettagli.


![Immagine del riquadro di gestione degli eventi imprevisti](images/atp-incidents-mgt-pane-updated.png)

È possibile assegnare eventi imprevisti a se stessi, modificare lo stato e la classificazione, rinominare o commentarli per tenere traccia dello stato.

> [!TIP]
> Per un'ulteriore visibilità a colpo d'occhio, i nomi degli eventi imprevisti vengono generati automaticamente in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.
>
> Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*
>
> Gli eventi imprevisti esistenti prima dell'implementazione della denominazione automatica degli eventi imprevisti manterranno i nomi.
>


![Immagine della pagina dei dettagli dell'evento imprevisto](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Assegnare gli eventi imprevisti
Se non è stato ancora assegnato un evento imprevisto, è possibile selezionare Assegna a **me** per assegnare l'evento a se stessi. In questo modo si assume la proprietà non solo dell'evento, ma anche di tutti gli avvisi associati.

## <a name="set-status-and-classification"></a>Impostare lo stato e la classificazione
### <a name="incident-status"></a>Stato di un evento imprevisto
È possibile categorizzare gli eventi imprevisti, ad esempio **Attivo** oppure **Risolto**, modificando lo stato durante il corso dell'analisi. Questo consente di organizzare e gestire il modo in cui il team può rispondere agli eventi imprevisti.

Ad esempio, l'analista  SoC può esaminare gli incidenti attivi urgenti del giorno e decidere di assegnarli a se stesso per le indagini.

In alternativa, l'analista SoC potrebbe impostare l'evento come **Risolto** se l'evento è stato risolto. 

### <a name="classification"></a>Classificazione
È possibile scegliere di non impostare una classificazione oppure decidere di specificare se un evento è vero o falso. Così facendo, il team può visualizzare i criteri e imparare a usarli.

### <a name="add-comments"></a>Aggiungere commenti
È possibile aggiungere commenti e visualizzare gli eventi cronologici relativi a un imprevisto per visualizzare le precedenti modifiche apportate.

Ogni volta che viene apportata una modifica o aggiunto un commento a un avviso, l'evento viene registrato nella sezione Commenti e cronologia.

I commenti aggiunti vengono visualizzati istantaneamente nel pannello.



## <a name="related-topics"></a>Argomenti correlati
- [Coda incidenti](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Visualizzare e organizzare la coda degli incidenti](view-incidents-queue.md)
- [Indagare sugli incidenti](investigate-incidents.md)
