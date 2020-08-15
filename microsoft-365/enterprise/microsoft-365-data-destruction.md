---
title: Microsoft 365 distruzione dei dati
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
description: Una panoramica dei criteri Microsoft relativi al riciclo, allo smaltimento o alla distruzione di unità disco e server del centro dati di Microsoft 365.
ms.openlocfilehash: bd5afd427f55952066bac06d2bd4e61f45a4562f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691160"
---
# <a name="microsoft-365-data-destruction"></a>Microsoft 365 distruzione dei dati

## <a name="physical-data-destruction"></a>Distruzione fisica dei dati

Microsoft dispone di criteri standard per la gestione dei dati che soddisfano il riciclo e lo smaltimento di unità disco e server non riusciti o in pensione. Prima di riutilizzare le unità disco Microsoft 365, Microsoft esegue un processo di disinfezione fisica coerente con l'Istituto nazionale di Standards and Technology Special Publication 800-88 ([NIST SP 800-88 Guidelines for Media sanification](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). Poiché tutte le unità disco in Microsoft 365 vengono crittografate utilizzando la crittografia a livello di volume di BitLocker, la cancellazione del NIST SP 800-88 conforme non è tecnicamente necessaria. Tuttavia, Microsoft esegue questo processo.

I dischi non riusciti utilizzati all'interno dei datacenter Microsoft 365 vengono distrutti fisicamente e controllati tramite il processo ISO. Il tipo di risorsa determina il metodo di eliminazione appropriato. Per i dischi rigidi che non possono essere cancellati, Microsoft utilizza un processo di distruzione per distruggere i contenuti multimediali e rendere impossibile il ripristino delle informazioni. Ad esempio, i dischi vengono eliminati fisicamente, polverizzati o inceneriti. Microsoft conserva tutti i record della distruzione ed esegue un processo di sanificazione simile nei server riutilizzati in Microsoft 365. Queste linee guida comprendono sia la sanificazione elettronica sia quella fisica.

Ogni Data Center utilizza un processo di distruzione fisica sul posto per eliminare i dischi. Le collocazioni sicure per i supporti di archiviazione designate per lo smaltimento del disco sono disponibili in ogni area del datacenter. Ogni Secure bin Station ha video monitoring Surveillance. Una volta che un cassetto di eliminazione raggiunge circa 50% di capacità, il team di servizi del sito contatta il team di sicurezza fisica per coordinare la rimozione. Il personale dei servizi sito e un ufficio di sicurezza rimuovono il contenitore di eliminazione sicuro e lo inseriscono in un'area di archiviazione protetta designata. I criteri e le procedure che regolano la gestione dei dispositivi di supporto per i dati durante lo smaltimento sono testati di routine, incluse le procedure per garantire la condizione del macchinario approvato per la distruzione.

Nel processo di distruzione dei dati, i dischi vengono cancellati in modo conforme al NIST 800-88 (se possibile) e quindi inseriti in un trituratore industriale e demoliti fisicamente. Microsoft mantiene la responsabilità per le risorse che lasciano il datacenter usando il NIST SP 800-88 per la pulizia/eliminazione coerente, la distruzione delle risorse, la crittografia, l'inventario accurato, il monitoraggio e la protezione della catena di custodia durante il trasporto. Questo processo viene monitorato tramite la televisione a circuito chiuso e viene emesso un certificato di distruzione al termine del completamento.

Microsoft utilizza unità di cancellazione dei dati da [Extreme Protocol Solutions](https://www.enterprisedataerasure.com/) (EPS). Il software EPS supporta i requisiti del NIST SP 800-88 per la pulizia e l'eliminazione/cancellazione sicura. Prima di procedere con la pulizia o la distruzione, viene creato un inventario da Microsoft Asset Manager. Se un fornitore viene utilizzato per la distruzione, il fornitore fornisce un certificato di distruzione per ogni risorsa distrutta, convalidata dall'Asset Manager.

## <a name="virtual-data-destruction"></a>Distruzione dei dati virtuali

Microsoft dispone di criteri e procedure di gestione dei dati che interessano la distruzione virtuale effettiva dei dati in modo da proteggersi dalla possibilità che i dati vengano condivisi in modo inappropriato tra i tenant dei servizi o che siano accessibili dopo l'eliminazione definitiva del servizio. I dati eliminati dal servizio in un tenant non sono accessibili a un altro tenant del servizio, anche se viene riassegnato uno spazio di archiviazione fisico sottostante. Si tratta di un risultato degli effetti aggravati di più tecnologie di virtualizzazione e frammentazione utilizzate per la scalabilità degli ambienti virtuali, dei comportamenti di eliminazione attivi delle applicazioni all'interno di ogni tenant del servizio (ad esempio, l' [azzeramento delle pagine](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)) e dei processi di crittografia del contenuto multimediale e dell'applicazione necessari.