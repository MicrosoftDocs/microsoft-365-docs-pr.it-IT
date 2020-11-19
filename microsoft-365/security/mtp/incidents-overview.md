---
title: Panoramica degli incidenti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357612"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Panoramica degli incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? È possibile [valutarla in un ambiente lab](https://aka.ms/mtp-trial-lab) o [eseguire il progetto pilota in produzione](https://aka.ms/m365d-pilotplaybook).
>


Gli eventi non consentiti sono basati su avvisi correlati. Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete. Gli avvisi singoli forniscono indizi utili su un attacco in uscita. Tuttavia, gli attacchi in genere utilizzano vettori e tecniche diverse per eseguire una violazione. Il riattacco di singoli indizi può essere impegnativo e richiede molto tempo.

In questo breve video viene fornita una panoramica delle operazioni non consentite in Microsoft 365 Defender.
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Un evento imprevisto è una raccolta di avvisi correlati che compongono la storia di un attacco. Gli eventi dannosi e sospetti che si trovano in diverse entità del dispositivo, degli utenti e delle cassette postali nella rete vengono aggregati automaticamente da Microsoft 365 Defender. Raggruppare gli avvisi correlati in un evento imprevisto fornisce ai difensori della sicurezza una panoramica complessiva di un attacco. 

Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state utilizzate e in che misura l'attacco è andato in rete. È inoltre possibile visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali a cui è stato applicato un impatto, la gravità dell'impatto e altre informazioni sulle entità interessate.

Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale. I difensori della sicurezza possono inoltre eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla visualizzazione eventi non consentiti. 

Gli incidenti degli ultimi 30 giorni sono visualizzati nella coda degli incidenti. Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori. 

I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per una migliore e più personalizzata esperienza di gestione degli incidenti.



## <a name="see-also"></a>Vedere anche
- [Assegnare priorità agli eventi imprevisti](incident-queue.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
