---
title: Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come filtrare gli eventi imprevisti dalla coda degli eventi imprevisti in Microsoft 365 Defender
keywords: evento imprevisto, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929295"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



Microsoft 365 Defender applica l'analisi di correlazione e aggrega tutti gli avvisi e le indagini correlati da prodotti diversi in un unico evento imprevisto. Microsoft 365 Defender attiva inoltre avvisi univoci sulle attività che possono essere identificate come dannose solo in base alla visibilità end-to-end che Microsoft 365 Defender ha nell'intero patrimonio e nella famiglia di prodotti. Questa visualizzazione offre all'analista delle operazioni di sicurezza una storia di attacco più ampia, che consente di comprendere meglio e gestire le minacce complesse nell'organizzazione.


La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

Per impostazione predefinita, la coda nel Centro sicurezza Microsoft 365 visualizza gli eventi imprevisti visualizzati negli ultimi 30 giorni. L'evento imprevisto più recente si trova all'inizio dell'elenco, in modo da poterlo vedere per primo.

La coda degli eventi imprevisti espone colonne personalizzabili che offrono visibilità sulle diverse caratteristiche dell'incidente o sulle entità contenute. Ciò consente di prendere una decisione informata in merito alla definizione della priorità degli eventi imprevisti da gestire.

Per una maggiore visibilità a colpo d'occhio, la denominazione automatica degli eventi imprevisti genera nomi degli eventi imprevisti in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie. Ciò consente di comprendere rapidamente l'ambito dell'incidente.

Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*

> [!NOTE]
> Gli eventi imprevisti che si verificavano prima dell'implementazione della denominazione automatica degli eventi imprevisti non cambieranno il nome.

La coda degli eventi imprevisti espone inoltre più opzioni di filtro, che, se applicate, consentono di eseguire un'ampia gamma di tutti gli eventi imprevisti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario o una minaccia specifici. Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata. 

## <a name="available-filters"></a>Filtri disponibili

### <a name="assigned-to"></a>Assegnata a
Puoi scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione.

### <a name="categories"></a>Categorie
Scegli le categorie per concentrarti su tattiche, tecniche o componenti di attacco specifici. 

### <a name="classification"></a>Classificazione
Filtrare gli eventi imprevisti in base alle classificazioni impostate degli avvisi correlati. I valori includono avvisi true, falsi avvisi o non impostati.

### <a name="data-sensitivity"></a>Riservatezza dei dati
Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore. Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.

>[!NOTE]
>Applicabile solo se Microsoft Information Protection è attivo.

### <a name="device-group"></a>Gruppo di dispositivi
Filtra in base ai gruppi di dispositivi definiti.

### <a name="investigation-state"></a>Stato dell'indagine
Filtra gli eventi imprevisti in base allo stato dell'indagine automatizzata. 

### <a name="multiple-categories"></a>Più categorie 
È possibile scegliere di visualizzare solo gli eventi imprevisti mappati a più categorie e che possono quindi causare più danni. 

### <a name="multiple-service-sources"></a>Più servizi di origine 
Filtrare per visualizzare solo gli eventi imprevisti che contengono avvisi provenienti da origini diverse (Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender per Office 365).

### <a name="os-platform"></a>Piattaforma del sistema operativo
Limitare la visualizzazione della coda degli eventi imprevisti in base al sistema operativo.

### <a name="service-sources"></a>Servizi di origine
Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata. 

### <a name="severity"></a>Gravità
La gravità di un evento imprevisto è indicativa dell'impatto che può avere sulle risorse. Maggiore è la gravità, maggiore è l'impatto e in genere richiede l'attenzione più immediata. 

### <a name="status"></a>Stato
Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.




## <a name="next-steps"></a>Passaggi successivi
Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.
- [Indagare sugli eventi imprevisti](investigate-incidents.md)


## <a name="see-also"></a>Vedere anche
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
