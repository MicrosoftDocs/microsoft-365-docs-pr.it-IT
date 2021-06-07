---
title: Dati analitici sugli aggiornamenti della sicurezza di Windows
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739836"
---
# <a name="windows-security-update-insights"></a>Dati analitici sugli aggiornamenti della sicurezza di Windows
Questa visualizzazione fornisce una panoramica dello stato degli aggiornamenti della sicurezza per i Microsoft Managed Desktop dispositivi. 

Per visualizzare i dati di utilizzo, selezionare la <strong>Windows aggiornamenti della</strong> sicurezza.

![Windows riquadro degli aggiornamenti della sicurezza: grafici a barre dello stato del dispositivo e della versione dell'aggiornamento nella colonna sinistra, lo stato di avanzamento della distribuzione degli aggiornamenti nel tempo nella colonna centrale e la percentuale di dispositivi attivi per gruppo di distribuzione, nonché il numero di giorni necessari per raggiungere la destinazione di distribuzione del 95% nella colonna destra.](../../media/update-insights.jpg)

## <a name="device-status"></a>Stato del dispositivo

Per aggiornare i dispositivi tramite Windows Update, devono essere connessi a Internet e non ibernazione per un minimo di sei ore, due delle quali devono essere continue. Anche se è possibile che un dispositivo che non soddisfa questi requisiti venga aggiornato, i dispositivi che li soddisfano hanno la maggiore probabilità di essere aggiornati. 

Categorizziamo l'attività dei dispositivi nel contesto di Windows Update con questi termini:

- <strong>Attivo:</strong> Dispositivi che hanno soddisfatto i criteri minimi di attività (sei ore, due continui) per la versione più recente dell'aggiornamento della sicurezza e che hanno archiviato con Microsoft Intune almeno ogni cinque giorni
- <strong>Sincronizzato:</strong> Dispositivi archiviati con Intune negli ultimi 28 giorni
- <strong>Non sincronizzato:</strong> Dispositivi che <i>non hanno</i> archiviato con Intune negli ultimi 28 giorni




## <a name="update-version-status"></a>Stato della versione dell'aggiornamento

Microsoft rilascia gli aggiornamenti della sicurezza ogni secondo martedì del mese. Ogni versione aggiunge aggiornamenti importanti per le vulnerabilità della sicurezza note. Microsoft Managed Desktop il 95% dei dispositivi gestiti viene aggiornato con l'aggiornamento della sicurezza più recente disponibile ogni mese. Gli aggiornamenti della sicurezza vengono talvolta rilasciati in altri casi per affrontare con urgenza nuove minacce. Microsoft Managed Desktop questi aggiornamenti vengono distribuiti in modo analogo.

Microsoft classifica lo stato delle versioni degli aggiornamenti della sicurezza con i termini seguenti:

- <strong>Corrente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese corrente
- <strong>Precedente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese precedente
- <strong>Meno recente:</strong> Dispositivi che eseguono qualsiasi aggiornamento della sicurezza rilasciato prima del mese precedente

Dovrebbero essere visualizzati pochi <strong></strong> dispositivi nella categoria Precedente: una popolazione grande o in crescita probabilmente indica un problema sistemico da segnalare a Microsoft Managed Desktop in modo da poter analizzare.


## <a name="deployment-progress"></a>Avanzamento della distribuzione

All'inizio di ogni ciclo di rilascio degli aggiornamenti della sicurezza, Microsoft Managed Desktop uno snapshot della popolazione di dispositivi e imposta la destinazione di distribuzione al 95% di tale popolazione. <strong>L'area Stato</strong> distribuzione mostra una tendenza cronologica, aggiornata ogni giorno, che monitora la frequenza con cui la distribuzione degli aggiornamenti soddisfa questa destinazione per ogni versione. Questo grafico mostra solo i dispositivi con stato Attivo.

Puoi visualizzare questi dati per i cicli di aggiornamento precedenti usando il menu a discesa in alto a destra. Il periodo selezionato in questo menu si applica a tutte le informazioni dell'intera pagina.

<strong>L'area Dispositivi attivi aggiornati</strong> per gruppo di distribuzione offre una visualizzazione diversa mostrando l'avanzamento dell'installazione dell'aggiornamento per ognuno dei Microsoft Managed Desktop di distribuzione.

<strong>Nell'area Giorni per raggiungere</strong> l'obiettivo viene visualizzato il tempo necessario per l'aggiornamento del 95% del numero totale di dispositivi con l'aggiornamento della sicurezza corrente. Mentre è in corso la distribuzione, in quest'area viene visualizzato Ancora <strong>aggiornamento</strong> fino a quando non viene raggiunta la destinazione del 95% per l'aggiornamento selezionato.

## <a name="device-details-area"></a>Area Dettagli dispositivo

La parte inferiore del dashboard è una tabella che mostra informazioni dettagliate per i dispositivi, tra cui lo stato del [dispositivo](#device-status) e [lo stato della versione di aggiornamento.](#update-version-status) È possibile cercare questo elenco o filtrarlo in base a qualsiasi valore elencato.


![Tabella dettagli dispositivo che mostra le colonne relative al nome del dispositivo, all'utente assegnato, allo stato del dispositivo, alla versione di aggiornamento, alla versione del sistema operativo e alla data dell'ultima sincronizzazione del dispositivo.](../../media/security-update-insights-device-table-sterile.png)
