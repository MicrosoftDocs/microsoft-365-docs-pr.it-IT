---
title: Dati analitici sugli aggiornamenti della sicurezza di Windows
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941442"
---
# <a name="windows-security-update-insights"></a>Dati analitici sugli aggiornamenti della sicurezza di Windows
Questa visualizzazione offre una panoramica dello stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop. 

Per visualizzare i dati di utilizzo, selezionare la <strong>scheda Aggiornamenti della sicurezza di Windows.</strong>

![Riquadro degli aggiornamenti della sicurezza di Windows: grafici a barre dello stato del dispositivo e della versione di aggiornamento nella colonna sinistra, avanzamento della distribuzione degli aggiornamenti nel tempo nella colonna centrale e percentuale di dispositivi attivi in base al gruppo di distribuzione, nonché numero di giorni necessari per raggiungere la destinazione di distribuzione del 95% nella colonna destra.](../../media/update-insights.jpg)

## <a name="device-status"></a>Stato del dispositivo

Per poter essere aggiornati da Windows Update, i dispositivi devono essere connessi a Internet e non ibernazione per un minimo di sei ore, due dei quali devono essere continui. Anche se è possibile che un dispositivo che non soddisfa questi requisiti venga aggiornato, i dispositivi che soddisfano tali requisiti hanno la massima probabilità di essere aggiornati. 

Categorizziamo l'attività dei dispositivi nel contesto di Windows Update con questi termini:

- <strong>Attivo:</strong> Dispositivi che hanno soddisfatto i criteri di attività minimi (sei ore, due continui) per la versione più recente dell'aggiornamento della sicurezza e che hanno archiviato con Microsoft Intune almeno ogni cinque giorni
- <strong>Sincronizzato:</strong> Dispositivi che hanno archiviato con Intune negli ultimi 28 giorni
- <strong>Non sincronizzato:</strong> Dispositivi che <i>non hanno</i> archiviato con Intune negli ultimi 28 giorni




## <a name="update-version-status"></a>Aggiornare lo stato della versione

Microsoft rilascia gli aggiornamenti della sicurezza ogni secondo martedì del mese. Ogni versione aggiunge aggiornamenti importanti per le vulnerabilità di sicurezza note. Microsoft Managed Desktop garantisce che il 95% dei dispositivi gestiti sia aggiornato con l'aggiornamento della sicurezza più recente disponibile ogni mese. Gli aggiornamenti della sicurezza vengono talvolta rilasciati in altri momenti per affrontare con urgenza nuove minacce. Microsoft Managed Desktop distribuisce questi aggiornamenti in modo simile.

Lo stato delle versioni degli aggiornamenti della sicurezza viene classificato con le condizioni seguenti:

- <strong>Corrente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese corrente
- <strong>Precedente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese precedente
- <strong>Meno recente:</strong> Dispositivi che eseguono qualsiasi aggiornamento della sicurezza rilasciato prima del mese precedente

Dovrebbero essere visualizzati pochi <strong></strong> dispositivi nella categoria Meno recente. Una popolazione di grandi dimensioni o in crescita probabilmente indica un problema sistemico che è necessario segnalare a Microsoft Managed Desktop in modo da poter analizzare.


## <a name="deployment-progress"></a>Avanzamento della distribuzione

All'inizio di ogni ciclo di rilascio degli aggiornamenti della sicurezza, Microsoft Managed Desktop prende uno snapshot della popolazione di dispositivi e imposta l'obiettivo di distribuzione sul 95% della popolazione. <strong>L'area di avanzamento</strong> della distribuzione mostra una tendenza cronologica aggiornata ogni giorno, verificando la frequenza con cui la distribuzione dell'aggiornamento soddisfa questo obiettivo per ogni versione. Questo grafico mostra solo i dispositivi con stato Attivo.

Puoi visualizzare questi dati per i cicli di aggiornamento precedenti usando il menu a discesa in alto a destra. Il periodo selezionato in questo menu si applica a tutte le informazioni nell'intera pagina.

<strong>L'area Dispositivi attivi aggiornati in</strong> base al gruppo di distribuzione offre una visualizzazione diversa mostrando l'avanzamento dell'installazione dell'aggiornamento per ogni gruppo di distribuzione di Microsoft Managed Desktop.

<strong>Nell'area Giorni per raggiungere</strong> l'area di destinazione viene visualizzato il tempo impiegato per il 95% del numero totale di dispositivi da aggiornare con l'aggiornamento della sicurezza corrente. Mentre è in corso la distribuzione, in quest'area viene visualizzato l'opzione Ancora <strong>aggiornamento</strong> fino a quando non viene raggiunta la destinazione del 95% per l'aggiornamento selezionato.

## <a name="device-details-area"></a>Area dettagli dispositivo

Nella parte inferiore del dashboard è disponibile una tabella che mostra informazioni dettagliate per i dispositivi, tra cui lo stato del [dispositivo](#device-status) e [lo stato della versione di aggiornamento.](#update-version-status) È possibile cercare questo elenco o filtrarlo in base a qualsiasi valore elencato.


![Tabella dettagli dispositivo che mostra le colonne relative al nome del dispositivo, all'utente assegnato, allo stato del dispositivo, alla versione di aggiornamento, alla versione del sistema operativo e alla data dell'ultima sincronizzazione del dispositivo.](../../media/security-update-insights-device-table-sterile.png)
