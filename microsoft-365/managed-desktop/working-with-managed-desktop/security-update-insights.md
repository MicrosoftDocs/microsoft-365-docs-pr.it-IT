---
title: Dati analitici sugli aggiornamenti della sicurezza di Windows
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341264"
---
# <a name="windows-security-update-insights"></a>Dati analitici sugli aggiornamenti della sicurezza di Windows
In questa visualizzazione viene fornita una panoramica dello stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop. 

Per visualizzare i dati di utilizzo, selezionare la scheda aggiornamenti per la <strong>sicurezza di Windows</strong> .

![Riquadro degli aggiornamenti della sicurezza di Windows: grafici a barre dello stato del dispositivo e della versione di aggiornamento nella colonna a sinistra, avanzamento della distribuzione dell'aggiornamento nel tempo nella colonna centrale e percentuale di dispositivi attivi per gruppo di distribuzione, nonché il numero di giorni per cui è stata eseguita la distribuzione del 95%. destinazione nella colonna a destra.](../../media/update-insights.jpg)

## <a name="device-status"></a>Stato del dispositivo

Affinché i dispositivi vengano aggiornati da Windows Update, è necessario che siano connessi a Internet e che non siano in letargo per un minimo di sei ore, due dei quali devono essere continue. A condizione che un dispositivo sia connesso e che non sia in modalità ibernazione, viene considerato "in uso". Anche se è possibile che un dispositivo che non soddisfa questi requisiti venga aggiornato, i dispositivi che li soddisfano hanno la maggiore probabilità di essere aggiornati. 

La categorizzazione dell'attività del dispositivo nel contesto di Windows Update viene confrontata con questi termini:

- <strong>Attivo:</strong> Dispositivi che soddisfano i criteri di utilizzo minimi (sei ore, due continue) per la versione più recente dell'aggiornamento della sicurezza e che hanno eseguito l'archiviazione con Microsoft Intune almeno ogni cinque giorni
- <strong>Sincronizzati:</strong> Dispositivi che sono stati archiviati con Intune negli ultimi 28 giorni
- Non <strong>sincronizzato:</strong> Dispositivi che <i>non</i> sono stati archiviati con Intune negli ultimi 28 giorni




## <a name="update-version-status"></a>Stato versione aggiornamento

Microsoft rilascia gli aggiornamenti della sicurezza ogni secondo martedi del mese. Ogni versione aggiunge aggiornamenti importanti per vulnerabilità note sulla sicurezza. Microsoft Managed Desktop garantisce che il 95% dei suoi dispositivi gestiti venga aggiornato con l'aggiornamento della sicurezza più recente disponibile ogni mese. Gli aggiornamenti della sicurezza vengono talvolta rilasciati in altri casi per affrontare con urgenza nuove minacce. Microsoft Managed Desktop distribuisce questi aggiornamenti in modo analogo.

Categorizzare lo stato delle versioni degli aggiornamenti per la sicurezza con questi termini:

- <strong>Corrente:</strong> Dispositivi che eseguono l'aggiornamento rilasciati nel mese corrente
- <strong>Previous:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese precedente
- <strong>Precedente:</strong> Dispositivi che eseguono tutti gli aggiornamenti della sicurezza rilasciati prima del mese precedente

Si dovrebbe vedere alcuni dispositivi nella categoria <strong>precedente</strong> --una popolazione di grandi dimensioni o in crescita indica probabilmente un problema sistemico che è necessario segnalare a Microsoft Managed Desktop in modo da poter indagare.


## <a name="deployment-progress"></a>Stato di avanzamento della distribuzione

All'inizio di ogni ciclo di rilascio degli aggiornamenti per la sicurezza, Microsoft Managed Desktop acquisisce un'istantanea del popolamento del dispositivo e imposta la propria destinazione di distribuzione al 95% di quella popolazione. L'area di <strong>avanzamento della distribuzione</strong> presenta una tendenza storica, aggiornata giornalmente, tracciando la conformità della distribuzione degli aggiornamenti a questa destinazione per ogni versione. Questo grafico Visualizza solo i dispositivi con stato attivo.

È possibile visualizzare i dati per i cicli di aggiornamento precedenti utilizzando il menu a discesa in alto a destra. Il periodo selezionato in questo menu si applica a tutte le informazioni dell'intera pagina.

L'area dei <strong>dispositivi attivi aggiornati in base al gruppo di distribuzione</strong> offre una visualizzazione diversa mostrando lo stato di avanzamento dell'installazione dell'aggiornamento per ogni gruppo di distribuzione di Microsoft Managed Desktop.

I <strong>giorni per raggiungere</strong> l'area di destinazione Visualizza il tempo impiegato per il 95% del numero totale di dispositivi da aggiornare con l'aggiornamento della sicurezza corrente. Durante la fase di distribuzione, quest'area Visualizza l' <strong>aggiornamento</strong> fino a quando non viene raggiunta la destinazione 95% per l'aggiornamento selezionato.

## <a name="device-details-area"></a>Area dettagli dispositivo

La parte inferiore del dashboard è una tabella che mostra informazioni dettagliate sui dispositivi, tra cui lo stato del [dispositivo](#device-status) e lo [stato della versione dell'aggiornamento](#update-version-status). È possibile eseguire una ricerca nell'elenco o filtrarlo in base a qualsiasi valore elencato.


![Tabella dei dettagli del dispositivo che mostra le colonne per il nome del dispositivo, l'utente assegnato, lo stato del dispositivo, la versione dell'aggiornamento, la versione del sistema operativo e la data di sincronizzazione dell'ultimo dispositivo.](../../media/security-update-insights-device-table-sterile.png)
