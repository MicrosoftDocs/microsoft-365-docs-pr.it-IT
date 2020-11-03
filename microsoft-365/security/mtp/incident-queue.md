---
title: Assegnare la priorità agli incidenti in Microsoft 365 Defender
description: Informazioni su come definire la priorità degli incidenti dalla coda degli incidenti in Microsoft 365 Defender
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
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846713"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Assegnare la priorità agli incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



Microsoft 365 Defender applica l'analisi della correlazione e aggrega tutti gli avvisi e le indagini correlati provenienti da prodotti diversi in un unico evento. Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera proprietà e nella famiglia di prodotti. In questo modo, Microsoft 365 Defender narra la storia degli attacchi più ampia, consentendo a un analista delle operazioni di sicurezza di comprendere e gestire le minacce complesse all'interno dell'organizzazione.


La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

Per impostazione predefinita, la coda disponibile nel Centro sicurezza Microsoft 365 mostra gli eventi imprevisti verificatisi negli ultimi 30 giorni, con l'evento più recente visualizzato in testa all'elenco, consentendoti quindi di visualizzare prima gli eventi più recenti.

La coda degli eventi imprevisti dispone di colonne personalizzabili che rendono visibili le diverse caratteristiche dell'evento o delle entità che questo contiene e ti aiuta a scegliere in modo mirato gli eventi imprevisti a cui dare la priorità.

Per una maggiore visibilità a colpo d'occhio, la denominazione degli incidenti automatici genera nomi degli incidenti in base agli attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.

Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*

> [!NOTE]
> Gli incidenti che sono stati precedenti all'implementazione della denominazione degli incidenti automatici non avranno il nome modificato.

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
Filtro per visualizzare solo gli incidenti che contengono avvisi provenienti da origini diverse (Microsoft Defender per endpoint, Microsoft cloud app Security, Microsoft Defender for Identity, Microsoft Defender per Office 365)
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
