---
title: Rapporto di mancato recapito nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il report dettagli di mancato recapito nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i codici di errore riscontrati più di frequente nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) dai mittenti dell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af4beefb8ba15fd7d98b11ec2571eee65a99e4e3
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150160"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapporto di mancato recapito nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Il **rapporto** di mancato recapito nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità mostra i codici di errore più rilevati nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) per gli utenti dell'organizzazione. Questo report mostra i dettagli dei rapporti di mancato recapito in modo da poter risolvere i problemi di recapito della posta elettronica.

![Widget report di mancato recapito nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Visualizzazione report per il rapporto di mancato recapito

Se si fa clic sul widget **Rapporto di** mancato recapito, verrà visualizzato il rapporto di mancato **recapito.**

Per impostazione predefinita, viene visualizzata l'attività per tutti i codici di errore. Se fai clic **su Mostra dati per**, puoi selezionare un codice di errore specifico nell'elenco a discesa.

Se si passa il mouse su un colore specifico (codice di errore) in un giorno specifico del grafico, verrà visualizzato il numero totale di messaggi per l'errore.

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Visualizzazione tabella dettagli per il rapporto di mancato recapito

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Codice rapporto di mancato recapito**
- **Numero**
- **Messaggi di esempio**: ID messaggio di un campione di messaggi interessati.

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le informazioni seguenti:

- **Data**
- **Codice del rapporto di mancato** recapito: è possibile fare clic sul collegamento per trovare ulteriori informazioni sulle cause e le soluzioni per il codice di errore specifico.
- **Numero**
- **Messaggi di esempio:** è possibile fare clic **su Visualizza** messaggi di esempio per visualizzare i risultati [della](message-trace-scc.md) traccia dei messaggi per un campione dei messaggi interessati.

![Riquadro a comparsa Dettagli dopo aver selezionato una riga nella visualizzazione Tabella dettagli nel rapporto di mancato recapito](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
