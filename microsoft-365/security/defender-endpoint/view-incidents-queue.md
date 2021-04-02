---
title: Visualizzare e organizzare la coda degli incidenti
ms.reviewer: ''
description: Vedi l'elenco degli eventi imprevisti e scopri come applicare filtri per limitare l'elenco e ottenere una visualizzazione più mirata.
keywords: visualizzazione, organizzazione, eventi imprevisti, aggregazione, indagini, coda, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499929"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Visualizzare e organizzare la coda eventi imprevisti di Microsoft Defender per endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

La **coda Eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati dai dispositivi della rete. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.

Per impostazione predefinita, nella coda vengono visualizzati gli eventi imprevisti visualizzati negli ultimi 30 giorni, con l'evento imprevisto più recente visualizzato all'inizio dell'elenco, consentendo di visualizzare prima gli eventi imprevisti più recenti.

Sono disponibili diverse opzioni tra cui scegliere per personalizzare la visualizzazione della coda eventi imprevisti. 

Nella barra di spostamento superiore è possibile:
- Personalizzare le colonne per aggiungere o rimuovere colonne 
- Modificare il numero di elementi da visualizzare per pagina
- Selezionare gli elementi da visualizzare per pagina
- Selezionare in batch gli eventi imprevisti da assegnare 
- Spostarsi tra le pagine
- Applicazione di filtri

![Immagine della coda eventi imprevisti](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>Ordinare e filtrare la coda degli eventi imprevisti
È possibile applicare i filtri seguenti per limitare l'elenco degli eventi imprevisti e ottenere una visualizzazione più mirata.

### <a name="severity"></a>Gravità

Gravità evento imprevisto | Descrizione
:---|:---
Alta </br>(Rosso) | Minacce spesso associate a minacce persistenti avanzate (APT). Questi eventi imprevisti indicano un rischio elevato a causa della gravità dei danni che possono infliggere ai dispositivi.
Medio </br>(Arancione) | Minacce raramente osservate nell'organizzazione, ad esempio modifiche anomali del Registro di sistema, esecuzione di file sospetti e comportamenti osservati tipici delle fasi di attacco.
Bassa </br>(Giallo) | Minacce associate a malware e strumenti di hacking prevalenti che non indicano necessariamente una minaccia avanzata per l'organizzazione.
Informativo </br>(Grigio) | Gli incidenti in informazioni potrebbero non essere considerati dannosi per la rete, ma potrebbero essere utili da tenere traccia.

## <a name="assigned-to"></a>Assegnata a
Puoi scegliere di filtrare l'elenco selezionando gli eventi assegnati a un altro utente o quelli assegnati a te.

### <a name="category"></a>Categoria
Gli incidenti vengono categorizzati in base alla descrizione della fase in cui si trova la catena di kill chain della sicurezza informatica. Questa visualizzazione consente all'analista delle minacce di determinare la priorità, l'urgenza e la strategia di risposta corrispondente da distribuire in base al contesto.

### <a name="status"></a>Stato
Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.

### <a name="data-sensitivity"></a>Riservatezza dei dati
Utilizzare questo filtro per visualizzare gli eventi imprevisti che contengono etichette di riservatezza.

## <a name="incident-naming"></a>Denominazione degli eventi imprevisti

Per comprendere a colpo d'occhio l'ambito dell'evento imprevisto, i nomi degli eventi imprevisti vengono generati automaticamente in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.

Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*

> [!NOTE]
> Gli eventi imprevisti esistenti prima dell'implementazione della denominazione automatica degli eventi imprevisti manterranno il nome.


## <a name="see-also"></a>Vedere anche
- [Coda incidenti](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Gestire gli incidenti](manage-incidents.md)
- [Indagare sugli incidenti](investigate-incidents.md)

