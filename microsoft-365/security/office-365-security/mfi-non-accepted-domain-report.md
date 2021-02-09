---
title: Rapporto dominio non accettato nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare il report dominio non accettato nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i messaggi dall'organizzazione locale in cui il dominio del mittente non è configurato in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150821"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Report dominio non accettato nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Il **report** Dominio non accettato nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità visualizza informazioni sui messaggi provenienti dall'organizzazione di posta elettronica locale in cui il dominio del mittente non è configurato come dominio accettato nell'organizzazione di Microsoft 365.

Microsoft 365 potrebbe limitazione di questi messaggi se si dispone di dati per dimostrare che l'intento di questi messaggi è dannoso. Pertanto, è importante comprendere cosa sta succedendo e risolvere il problema.

![Widget Dominio non accettato nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Visualizzazione report per il rapporto dominio non accettato

Se si fa clic sul grafico **nel** widget Dominio non accettato, verrà visualizzato il report **Dominio non** accettato.

Per impostazione predefinita, viene visualizzata l'attività per tutti i connettori interessati. Se si fa **clic su Mostra dati per**, è possibile selezionare un connettore specifico nell'elenco a discesa.

Se si passa il mouse su un punto dati (giorno) nel grafico, viene visualizzato il numero totale di messaggi per il connettore.

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Visualizzazione della tabella dei dettagli per il report dominio non accettato

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Nome connettore in ingresso**
- **Dominio del mittente**
- **Numero messaggi**
- **Messaggi di esempio**: ID messaggio di un campione di messaggi interessati.

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le informazioni seguenti:

- **Data**
- **Nome connettore in ingresso**
- **Dominio del mittente**
- **Numero messaggi**
- **Messaggi di esempio:** è possibile fare clic **su Visualizza** messaggi di esempio per visualizzare i risultati [della](message-trace-scc.md) traccia dei messaggi per un campione dei messaggi interessati.

![Riquadro a comparsa Dettagli dopo aver selezionato una riga nella visualizzazione Tabella dettagli nel report Dominio non accettato](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
