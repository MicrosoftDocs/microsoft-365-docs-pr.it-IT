---
title: Resilienza dei dati in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni sulla progettazione e sui principi di resilienza e ripristino dei dati in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691143"
---
# <a name="data-resiliency-in-microsoft-365"></a>Resilienza dei dati in Microsoft 365

Data la complessità del cloud computing, Microsoft è consapevole del fatto che non si tratta di un caso in cui le cose andranno male, ma piuttosto quando. È possibile progettare i servizi cloud per massimizzare l'affidabilità e ridurre al minimo gli effetti negativi sui clienti quando si verifica un errore. Ci siamo spostati oltre la strategia tradizionale di fare affidamento sull'infrastruttura fisica complessa e abbiamo creato la ridondanza direttamente nei nostri servizi cloud. Viene utilizzata una combinazione di infrastruttura fisica meno complessa e software più intelligente che genera la resilienza dei dati nei servizi e garantisce una disponibilità elevata ai clienti. 

## <a name="resiliency-and-recoverability-are-built-in"></a>La resilienza e la recuperabilità sono incorporate 

La creazione di resilienza e ripristino inizia con l'assunto che l'infrastruttura e i processi sottostanti avranno esito negativo a un certo punto: l'hardware (infrastruttura) avrà esito negativo, gli esseri umani commetteranno errori e il software avrà bug. Anche se non è corretto dire che gli sviluppatori di software non stavano pensando a queste operazioni prima del cloud, in che modo questi problemi sono stati gestiti in una tipica implementazione IT è stato molto diverso prima del cloud:

- In primo luogo, le protezioni per l'hardware e l'infrastruttura sono state significative. Questo significava che i datacenter con 99,99% di affidabilità richiedevano una notevole quantità di energia e ridondanza di rete e che i server sono stati implementati con il clustering basato su hardware, alimentatori duali, interfacce di rete duali e così. 
- In secondo luogo, il processo è stato fondamentale. I team operativi hanno mantenuto procedure rigorose, sono state apportate modifiche alle finestre e spesso sono stati significativi overhead per la gestione dei progetti. 
- Terza, la distribuzione ha avuto luogo a ritmi glaciali. La distribuzione del codice senza possedere l'origine significava in attesa di rilasci delle patch e la versione principale rilasciava la sostituzione hardware e una significativa spesa di capitale. Inoltre, l'unico modo per correggere un problema è stato quello di eseguire il rollback. In questo modo, la maggior parte delle organizzazioni IT distribuirà solo i rilasci importanti per evitare che il lavoro venga mantenuto aggiornato. 
- Infine, la scala dei sistemi distribuiti, così come il livello di interconnessione, era storicamente molto più piccola di quanto non lo sia ora. 

Oggi, i clienti si aspettano un'innovazione continua da Microsoft senza compromettere la qualità e questo è uno dei motivi per cui i servizi e il software di Microsoft sono stati creati con resilienza e ripristino in mente. 

## <a name="microsoft-365-data-resiliency-principles"></a>Principi di resilienza dei dati di Microsoft 365

La resilienza si riferisce alla capacità di un servizio basato sul cloud di resistere a determinati tipi di errori, ma rimane completamente funzionante dalla prospettiva dei clienti. La resilienza dei dati significa che non importa quali errori si verificano in Microsoft 365, i dati critici dei clienti restano intatti e inalterati. A tal fine, i servizi Microsoft 365 sono stati disegnati attorno a cinque specifici principi di resilienza:

- Sono presenti dati critici e non critici. I dati non critici, ad esempio l'eventuale lettura di un messaggio, possono essere eliminati in scenari di errore rari. I dati critici (ad esempio, i dati dei clienti come i messaggi di posta elettronica) devono essere protetti a costi estremi. Come obiettivo di progettazione, i messaggi di posta elettronica recapitati sono sempre importanti e gli elementi come se un messaggio è stato letto non sono critici. 
- Le copie dei dati del cliente devono essere separate in aree di errore diverse o come molti domini di errore possibili (ad esempio, Datacenter, accessibili tramite credenziali singole (processo, server o operatore)) per fornire l'isolamento degli errori. 
- I dati critici dei clienti devono essere monitorati per la mancanza di qualsiasi parte dell'atomicità, della coerenza, dell'isolamento e della durata (acido). 
- I dati dei clienti devono essere protetti dal danneggiamento. Deve essere analizzato o monitorato attivamente, ripristinabile e ripristinabile. 
- La maggior parte delle perdite di dati risulta dalle azioni dei clienti, quindi consente ai clienti di eseguire il ripristino autonomo utilizzando una GUI che consente di ripristinare accidentalmente gli elementi eliminati. 
 
Tramite la creazione dei servizi cloud a questi principi, insieme a testing e convalida robusti, Microsoft 365 è in grado di soddisfare e superare i requisiti dei clienti garantendo una piattaforma per l'innovazione continua e il miglioramento. 

## <a name="related-links"></a>Collegamenti correlati

- [Gestione della corruzione dei dati](microsoft-365-dealing-with-data-corruption.md)
- [Protezione malware e ransomware](microsoft-365-malware-and-ransomware-protection.md)
- [Il monitoraggio e la riparazione automatica](microsoft-365-monitoring-and-self-healing.md)
- [Resilienza dei dati di Exchange](microsoft-365-exchange-data-resiliency.md)
