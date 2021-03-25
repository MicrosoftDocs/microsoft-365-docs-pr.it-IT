---
title: Correggere possibili informazioni dettagliate sul ciclo di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni sulla correzione dei possibili loop di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità per identificare e correggere i loop di posta nell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206343"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Risolvere le possibili informazioni dettagliate sul ciclo di posta nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I cicli di posta non sono erri perché:

- Sprecano risorse di sistema.
- Utilizzano la quota del volume di posta dell'organizzazione.
- Inviano rapporti di mancato recapito confusi (noti anche come rapporti di mancato recapito o messaggi di mancato recapito) ai mittenti dei messaggi originali.

**L'analisi fix possible mail loop** nell'area Recommended for **you** del [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità notifica quando viene rilevato un ciclo di posta nell'organizzazione.

Questa analisi viene visualizzata solo dopo che la condizione è stata rilevata (se non sono presenti loop di posta, non verranno visualizzate le informazioni dettagliate).

![Correggere le informazioni dettagliate sulle regole del flusso di posta lento nell'area Consigliato per l'utente del dashboard del flusso di posta](../../media/mfi-fix-possible-mail-loop.png)

Quando si fa **clic su Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:

- **Dominio**
- **Numero di messaggi**: è possibile **fare** clic su Visualizza messaggi di esempio per visualizzare i risultati della traccia dei messaggi per un esempio dei messaggi interessati dal ciclo. [](message-trace-scc.md)
- **Tipo di** dominio " Ad esempio Autorevole o Non autorevole.
- **Record MX**: l'host (**Server** di posta ) e i valori **priority** del record MX per il dominio.
- **Motivo del** ciclo **e Come risolvere**: identificheremo gli scenari di ciclo di posta più comuni e forniremo le azioni consigliate per correggere il ciclo.

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Visualizza dettagli nella finestra di dialogo Correggi possibile informazioni dettagliate sul ciclo di posta](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
