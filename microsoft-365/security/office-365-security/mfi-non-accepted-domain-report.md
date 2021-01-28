---
title: Rapporto di dominio non accettato nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare il rapporto di dominio non accettato nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità per monitorare i messaggi provenienti dall'organizzazione locale in cui il dominio del mittente non è configurato in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 401d566158ca3f730af94fab60c471484e244a16
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029847"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Rapporto di dominio non accettato nel centro sicurezza & Compliance

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Il rapporto di **dominio non accettato** nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) Visualizza informazioni sui messaggi provenienti dall'organizzazione di posta elettronica locale, in cui il dominio del mittente non è configurato come dominio accettato nell'organizzazione Microsoft 365.

Microsoft 365 potrebbe limitare tali messaggi se si dispone di dati per dimostrare che l'intento di questi messaggi è dannoso. Pertanto, è importante capire cosa succede e risolvere il problema.

![Widget del dominio non accettato nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Visualizzazione report per il rapporto di dominio non accettato

Se si fa clic sul grafico sul widget di **dominio non accettato** , verrà eseguito il rapporto di **dominio non accettato** .

Per impostazione predefinita, viene visualizzata l'attività per tutti i connettori coinvolti. Se si fa clic su **Mostra dati per**, è possibile selezionare un connettore specifico dall'elenco a discesa.

Se si posiziona il puntatore del mouse su un punto dati (giorno) nel grafico, verrà visualizzato il numero totale di messaggi per il connettore.

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Visualizzazione della tabella dei dettagli per il rapporto di dominio non accettato

Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Nome del connettore in ingresso**
- **Dominio del mittente**
- **Numero di messaggi**
- **Messaggi di esempio**: ID del messaggio di un esempio di messaggi coinvolti.

Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.

Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le seguenti informazioni:

- **Data**
- **Nome del connettore in ingresso**
- **Dominio del mittente**
- **Numero di messaggi**
- **Messaggi di esempio**: è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati della [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi coinvolti.

![Riquadro a comparsa dettagli dopo aver selezionato una riga nella visualizzazione tabella dettagli del rapporto di dominio non accettato](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
