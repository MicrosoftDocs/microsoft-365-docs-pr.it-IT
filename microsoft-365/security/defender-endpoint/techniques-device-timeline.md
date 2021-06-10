---
title: Tecniche nella sequenza temporale del dispositivo
description: Informazioni sulla sequenza temporale del dispositivo in Microsoft Defender for Endpoint
keywords: sequenza temporale del dispositivo, endpoint, MITRE, MITRE ATT&CK, tecniche, tattiche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185468"
---
# <a name="techniques-in-the-device-timeline"></a>Tecniche nella sequenza temporale del dispositivo


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Puoi ottenere maggiori informazioni in un'indagine analizzando gli eventi che si sono verificati in un dispositivo specifico. Prima di tutto, seleziona il dispositivo di interesse [nell'elenco Dispositivi](machines-view-overview.md). Nella pagina del dispositivo puoi selezionare la scheda **Sequenza** temporale per visualizzare tutti gli eventi che si sono verificati nel dispositivo.

## <a name="understand-techniques-in-the-timeline"></a>Comprendere le tecniche nella sequenza temporale

>[!IMPORTANT]
>Alcune informazioni riguardano una funzionalità di prodotto pre-rilasciata in anteprima pubblica che potrebbe essere sostanzialmente modificata prima che venga rilasciata commercialmente. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

In Microsoft Defender per **Endpoint, le tecniche sono** un tipo di dati aggiuntivo nella sequenza temporale dell'evento. Le tecniche forniscono maggiori informazioni sulle attività associate a [MITRE ATT&tecniche CK](https://attack.mitre.org/) o sub-tecniche. 

Questa funzionalità semplifica l'esperienza di indagine aiutando gli analisti a comprendere le attività osservate in un dispositivo. Gli analisti possono quindi decidere di approfondire le indagini.

Per l'anteprima pubblica, le tecniche sono disponibili per impostazione predefinita e vengono visualizzate insieme agli eventi quando viene visualizzata la sequenza temporale di un dispositivo. 

![Tecniche nello screenshot della sequenza temporale del dispositivo](images/device-timeline-2.png)

Le tecniche sono evidenziate in grassetto e vengono visualizzate con un'icona blu a sinistra. Il nome della tecnica e l'ID CK&MITRE ATT corrispondenti vengono visualizzati anche come tag in Informazioni aggiuntive. 

Le opzioni di ricerca ed esportazione sono disponibili anche per Tecniche.

## <a name="investigate-using-the-side-pane"></a>Analizzare usando il riquadro laterale

Selezionare una tecnica per aprire il riquadro laterale corrispondente. Qui puoi visualizzare ulteriori informazioni e informazioni dettagliate, ad esempio tecniche, tattiche e descrizioni ATT correlate&CK. 

Seleziona la tecnica *di attacco* specifica per aprire la pagina relativa alla tecnica ATT&CK in cui puoi trovare ulteriori informazioni su di essa.

È possibile copiare i dettagli di un'entità quando viene visualizzata un'icona blu a destra. Ad esempio, per copiare sha1 di un file correlato, selezionare l'icona pagina blu.

![Copiare i dettagli dell'entità](images/techniques-side-pane-clickable.png)

È possibile eseguire la stessa operazione per le righe di comando.

![Copia riga di comando](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a>Analizzare gli eventi correlati

Per utilizzare [la ricerca avanzata](advanced-hunting-overview.md) per trovare gli eventi correlati alla tecnica selezionata, selezionare Cerca eventi **correlati.** In questo modo viene visualizzata la pagina di ricerca avanzata con una query per trovare gli eventi correlati alla tecnica.

![Ricerca di eventi correlati](images/techniques-hunt-for-related-events.png)

>[!NOTE]
>L'esecuzione  di query tramite il pulsante Cerca eventi correlati da un riquadro laterale Tecnica visualizza tutti gli eventi correlati alla tecnica identificata, ma non include la tecnica stessa nei risultati della query.


## <a name="customize-your-device-timeline"></a>Personalizzare la sequenza temporale del dispositivo

Nella parte superiore destra della sequenza temporale del dispositivo puoi scegliere un intervallo di date per limitare il numero di eventi e tecniche nella sequenza temporale. 

È possibile personalizzare le colonne da esporre. È inoltre possibile filtrare gli eventi contrassegnati in base al tipo di dati o al gruppo di eventi.

### <a name="choose-columns-to-expose"></a>Scegliere le colonne da esporre
Puoi scegliere le colonne da esporre nella sequenza temporale selezionando il **pulsante Scegli** colonne.

![Personalizzare le colonne](images/filter-customize-columns.png)

Da qui è possibile selezionare il set di informazioni da includere.

### <a name="filter-to-view-techniques-or-events-only"></a>Filtrare per visualizzare solo tecniche o eventi

Per visualizzare solo gli eventi o le tecniche, seleziona **Filtri** dalla sequenza temporale del dispositivo e scegli il tipo di dati preferito da visualizzare.

![Screenshot dei filtri](images/device-timeline-filters.png)



## <a name="see-also"></a>Vedere anche
- [Visualizzare e organizzare l’elenco dispositivi](machines-view-overview.md)
- [Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint](device-timeline-event-flag.md) 


 
