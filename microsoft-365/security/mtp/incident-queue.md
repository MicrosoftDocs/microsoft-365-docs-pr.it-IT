---
title: Assegnare priorità agli eventi imprevisti in Microsoft Threat Protection
description: Come assegnare priorità agli eventi imprevisti nella relativa coda in Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 90f7aaf7eb4425dadeb27699654656c86d2b6263
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087301"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Assegnare priorità agli eventi imprevisti in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection applica analisi di correlazione e aggrega tutti gli avvisi e le indagini correlate di prodotti diversi in un unico evento imprevisto. Microsoft Threat Protection genera inoltre avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft Threat Protection ha su tutta la struttura e la famiglia di prodotti. In questo modo, Microsoft Threat Protection agisce in un ambito di attacco più ampio e consente agli analisti delle operazioni di sicurezza di comprendere e gestire minacce complesse nell'organizzazione.


La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

Per impostazione predefinita, la coda disponibile nel Centro sicurezza Microsoft 365 mostra gli eventi imprevisti verificatisi negli ultimi 30 giorni, con l'evento più recente visualizzato in testa all'elenco, consentendoti quindi di visualizzare prima gli eventi più recenti.

La coda degli eventi imprevisti dispone di colonne personalizzabili che rendono visibili le diverse caratteristiche dell'evento o delle entità che questo contiene e ti aiuta a scegliere in modo mirato gli eventi imprevisti a cui dare la priorità. 

La coda dispone anche di più opzioni di filtro, che, se applicate, consentono di avere un’idea globale di tutti gli eventi esistenti nell'ambiente o di concentrarsi su uno scenario o una minaccia specifici. Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata. 

## <a name="available-filters"></a>Filtri disponibili

### <a name="status"></a>Stato
Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.

### <a name="severity"></a>Gravità
Il livello di gravità di un evento indica l'impatto che questo può avere sulle risorse. Maggiore sarà la gravità, maggiore sarà l'impatto e in genere l’evento richiederà quindi attenzione immediata. 

### <a name="assigned-to-owner"></a>Assegnato a (proprietario)
Puoi scegliere di filtrare l'elenco selezionando gli eventi assegnati a un altro utente o quelli assegnati a te.

### <a name="multiple-alerts"></a>Più avvisi 
Applica un filtro per visualizzare solo gli eventi imprevisti che contengono più di un avviso. Potrebbe indicare un attacco più complesso o a uno stadio più avanzato nella kill chain. 


### <a name="multiple-service-sources"></a>Più servizi di origine 
Filtra in modo da visualizzare solo gli eventi che contengono avvisi provenienti da diverse origini (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Servizi di origine
Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata. 

### <a name="multiple-categories"></a>Più categorie 
Puoi scegliere di visualizzare solo gli eventi imprevisti associati a più categorie della kill chain e che potenzialmente possono causare più danni. 

### <a name="categories"></a>Categorie
Scegli delle categorie specifiche per concentrarti su un passaggio specifico della kill chain.

### <a name="data-sensitivity"></a>Riservatezza dei dati
Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore. Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.

>[!NOTE]
>Applicabile solo se Microsoft Information Protection è attivo.


## <a name="next-steps"></a>Passaggi successivi
Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.
- [Indagare sugli eventi imprevisti](investigate-incidents.md)


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
