---
title: Analizzare gli avvisi in Microsoft 365 Defender
description: Analizzare gli avvisi visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500940"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Analizzare gli avvisi in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Gli avvisi sono alla base di tutti gli eventi imprevisti e indicano il verificarsi di eventi dannosi o sospetti nell'ambiente. Gli avvisi fanno in genere parte di un attacco più ampio e forniscono indizi su un incidente.

In Microsoft 365 Defender, gli avvisi correlati vengono aggregati insieme per formare eventi imprevisti. Gli incidenti forniscono sempre il contesto più ampio di un attacco, tuttavia, l'analisi degli avvisi può essere utile quando è necessaria un'analisi più approfondita. 



## <a name="using-alert-pages-in-investigations"></a>Utilizzo delle pagine di avviso nelle indagini

Nella scheda Avvisi di qualsiasi evento imprevisto, selezionando un avviso si visualizzano le singole pagine di avviso. Una pagina di avviso è costituita da tre sezioni: asset interessati, storia di avviso e riquadro dei dettagli.

![Immagine della pagina di avviso di esempio](../../media/new-alert-page2.png)

In tutta una pagina di avviso puoi selezionare l'icona a tre punti (**...**) accanto a qualsiasi entità in modo da visualizzare le azioni disponibili, ad esempio l'apertura della pagina di asset specifica o la procedura di correzione specifica.

### <a name="analyze-affected-assets"></a>Analizzare gli asset interessati
Nella sezione asset interessati sono elencate le cassette postali, i dispositivi e gli utenti interessati da questo avviso. Se si seleziona una delle schede delle risorse, nel riquadro laterale dei dettagli vengono visualizzate informazioni, inclusi gli eventuali altri avvisi che hanno coinvolto gli asset.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>Tracciare il ruolo di un avviso nella storia di avviso
La storia dell'avviso visualizza tutti gli asset o le entità correlati all'avviso in una visualizzazione albero del processo. L'avviso nel titolo è quello a fuoco quando si atterra per la prima volta nella pagina dell'avviso selezionato. Gli asset nella storia di avviso sono espandibili e selezionabili. Forniscono informazioni aggiuntive e velocizzano la risposta consentendoti di eseguire azioni direttamente nel contesto della pagina di avviso. 

> [!NOTE]
> La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.

### <a name="view-more-alert-information-in-the-details-pane"></a>Visualizzare ulteriori informazioni sugli avvisi nel riquadro dei dettagli

Il riquadro dei dettagli mostra i dettagli dell'avviso selezionato in un primo momento, con i dettagli e le azioni ad esso correlati. Se si seleziona una delle risorse o entità interessate nella storia di avviso, il riquadro dei dettagli cambia per fornire informazioni contestuali e azioni per l'oggetto selezionato.

Dopo aver selezionato un'entità di interesse, il riquadro dei dettagli cambia per visualizzare le informazioni sul tipo di entità selezionato, le informazioni storiche quando è disponibile e le opzioni per eseguire un'azione su questa entità direttamente dalla pagina di avviso.

### <a name="manage-alerts"></a>Gestire gli avvisi

Una volta completata l'analisi degli avvisi, è possibile tornare all'avviso avviato, contrassegnare lo stato dell'avviso come Risolto e classificarlo come avviso False o True. La classificazione degli avvisi consente di ottimizzare il prodotto per fornire avvisi più veri e meno falsi.

> [!NOTE]
> Un modo per gestire gli avvisi tramite l'uso di tag. La funzionalità di tagging per Microsoft Defender per Office 365 in fase di implementazione incrementale ed è attualmente in anteprima. <br>
> Attualmente, i nomi dei tag modificati vengono applicati solo agli avvisi creati *dopo l'aggiornamento.* Gli avvisi generati prima della modifica non rifletteranno il nome del tag aggiornato. 


## <a name="manage-the-unified-alert-queue"></a>Gestire la coda di avvisi unificati

Selezionando Avvisi in Eventi imprevisti & avvisi nel riquadro di spostamento del Centro sicurezza Microsoft 365, viene visualizzata la coda degli avvisi unificati. Gli avvisi di diverse soluzioni di sicurezza Microsoft come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft 365 Defender vengono visualizzati in questa sezione. 

![Immagine della pagina di avviso di esempio](../../media/unified-alert-queue.png)

La coda avvisi mostra un elenco di avvisi contrassegnati nella rete. Per impostazione predefinita, nella coda vengono visualizzati gli avvisi visualizzati negli ultimi 30 giorni. Gli avvisi più recenti vengono visualizzati all'inizio dell'elenco per visualizzare prima gli avvisi più recenti.

> [!NOTE]
> Al momento dell'avvio, la coda degli avvisi unificati avrà a disposizione solo 7 giorni di avvisi di Microsoft Defender per Office 365. La coda continuerà a essere compilata nel tempo. Se è necessario eseguire la valutazione degli avvisi prima dell'avvio della coda di avvisi unificati, utilizzare la coda degli avvisi nel [Centro sicurezza e conformità.](https://protection.office.com/viewalerts)


Nella barra di spostamento superiore è possibile:

- Applicazione di filtri
- Personalizzare le colonne per aggiungere o rimuovere colonne
- Esportare dati

È inoltre possibile filtrare gli avvisi in base a criteri diversi:

- Gravità
- Stato
- Categoria
- Origine di rilevamento
- Criteri
- Asset influenzati
- Prima attività
- Ultima attività


Per avviare un'indagine su un evento imprevisto, leggere [Analizzare gli incidenti in Microsoft 365 Defender](investigate-incidents.md)
## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
