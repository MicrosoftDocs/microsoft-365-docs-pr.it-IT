---
title: Assegnare la priorità agli incidenti in Microsoft 365 Defender
description: Informazioni su come filtrare gli incidenti dalla coda degli incidenti in Microsoft 365 Defender
keywords: evento imprevisto, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti
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
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409256"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Assegnare la priorità agli incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



Microsoft 365 Defender applica l'analisi della correlazione e aggrega tutti gli avvisi e le indagini correlati provenienti da prodotti diversi in un unico evento. Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera proprietà e nella famiglia di prodotti. Questa visualizzazione fornisce all'analista delle operazioni di sicurezza la storia degli attacchi più ampia, che li aiuta a comprendere meglio e a gestire le minacce complesse nell'organizzazione.


La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

Per impostazione predefinita, la coda nel centro sicurezza Microsoft 365 Visualizza gli incidenti riscontrati negli ultimi 30 giorni. L'evento più recente si trova nella parte superiore dell'elenco, in modo che sia possibile visualizzarlo per primo.

La coda di eventi non consentiti espone colonne personalizzabili che consentono di visualizzare le diverse caratteristiche dell'evento Incident o delle entità contenute. In questo modo è possibile prendere una decisione informata in merito alle priorità degli incidenti da gestire.

Per una maggiore visibilità a colpo d'occhio, la denominazione degli incidenti automatici genera nomi degli incidenti in base agli attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.

Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*

> [!NOTE]
> Gli incidenti che sono stati precedenti all'implementazione della denominazione degli incidenti automatici non avranno il nome modificato.

La coda degli incidenti espone anche più opzioni di filtro, che quando vengono applicate, consentono di eseguire un'ampia gamma di tutti gli incidenti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario specifico o una minaccia. Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata. 

## <a name="available-filters"></a>Filtri disponibili

### <a name="assigned-to"></a>Assegnata a
È possibile scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.

### <a name="categories"></a>Categorie
Scegliere categorie per concentrarsi su specifiche tattiche, tecniche o componenti di attacco visibili. 

### <a name="classification"></a>Classificazione
Filtrare gli eventi non consentiti in base alla classificazione impostata degli avvisi correlati. I valori includono avvisi veri, falsi avvisi o non impostati.

### <a name="data-sensitivity"></a>Riservatezza dei dati
Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore. Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.

>[!NOTE]
>Applicabile solo se Microsoft Information Protection è attivo.

### <a name="device-group"></a>Gruppo di dispositivi
Filtrare in base ai gruppi di dispositivi definiti.

### <a name="investigation-state"></a>Stato di indagine
Filtrare gli incidenti in base allo stato dell'analisi automatizzata. 

### <a name="multiple-categories"></a>Più categorie 
È possibile scegliere di visualizzare solo gli incidenti che sono stati mappati a più categorie e pertanto possono causare più danni. 

### <a name="multiple-service-sources"></a>Più servizi di origine 
Filtro per visualizzare solo gli incidenti che contengono avvisi provenienti da origini diverse (Microsoft Defender per endpoint, Microsoft cloud app Security, Microsoft Defender for Identity, Microsoft Defender per Office 365).

### <a name="os-platform"></a>Piattaforma OS
Limitare la visualizzazione delle code degli incidenti in base al sistema operativo.

### <a name="service-sources"></a>Servizi di origine
Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata. 

### <a name="severity"></a>Gravità
La gravità di un evento imprevisto è indicativa dell'impatto che può avere sui cespiti. Maggiore è la gravità, maggiore è l'impatto e in genere è necessaria l'attenzione più immediata. 

### <a name="status"></a>Stato
Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.




## <a name="next-steps"></a>Passaggi successivi
Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.
- [Indagare sugli eventi imprevisti](investigate-incidents.md)


## <a name="see-also"></a>Vedere anche
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
