---
title: Correggere informazioni dettagliate sulle regole del flusso di posta lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni dettagliate sulle regole del flusso di posta lente nel Centro sicurezza e conformità di & per identificare e correggere regole del flusso di posta inefficienti o interrotte (note anche come regole di trasporto) nell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205294"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Risolvere le lentezza delle regole del flusso di posta nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Le regole del flusso di posta inefficienti (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione. Queste informazioni dettagliate segnalano le regole del flusso di posta che influiscono sul flusso di posta dell'organizzazione. Di seguito sono riportati alcuni esempi di questi tipi di regole:

- Condizioni che utilizzano **Is membro di** per gruppi di grandi dimensioni.
- Condizioni che utilizzano criteri di ricerca di espressioni regolari complesse (regex).
- Condizioni che utilizzano l'archiviazione del contenuto negli allegati.

**L'analisi** delle regole del flusso di posta lento nell'area Consigliato per l'utente del [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità notifica quando il completamento di una regola del flusso di posta sta prendendo troppo tempo. 

Questa analisi viene visualizzata solo dopo che la condizione è stata rilevata (se non sono presenti loop di posta, non verranno visualizzate le informazioni dettagliate).

È possibile utilizzare questa notifica per identificare e ottimizzare le regole del flusso di posta per ridurre i ritardi del flusso di posta.

![Correggere le informazioni dettagliate sulle regole del flusso di posta lento nell'area Consigliato per l'utente del dashboard del flusso di posta](../../media/mfi-fix-slow-mail-flow-rules.png)

Quando si fa **clic su Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:

- **Regola**: è possibile passare il mouse sul riepilogo per visualizzare tutte le condizioni, le eccezioni e le azioni della regola. È possibile fare clic sul riepilogo per modificare la regola nell'interfaccia di amministrazione di Exchange (EAC).
- **Numero di messaggi valutati**: è possibile [](message-trace-scc.md) fare clic su Visualizza messaggi di esempio per visualizzare i risultati della traccia dei messaggi per un esempio dei messaggi interessati dalla regola. 
- **Tempo medio dedicato a ogni messaggio**
- **Tempo medio dedicato a un messaggio:** valore intermedio che separa la metà superiore dai dati della metà inferiore del tempo.

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Visualizza dettagli nella finestra di dialogo Correggi informazioni sulle regole del flusso di posta lento](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Per ulteriori informazioni sulle condizioni e sulle eccezioni nelle regole del flusso di posta, vedere [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)