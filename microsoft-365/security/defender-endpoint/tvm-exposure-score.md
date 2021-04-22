---
title: Punteggio di esposizione nella gestione delle minacce e delle vulnerabilità
description: Il punteggio di esposizione alla gestione delle minacce e delle vulnerabilità riflette la vulnerabilità dell'organizzazione alle minacce di cybersecurity.
keywords: punteggio di esposizione, Punteggio di esposizione di Microsoft Defender for Endpoint, Punteggio di esposizione tvm di Microsoft Defender for Endpoint, punteggio di esposizione dell'organizzazione, punteggio di esposizione dell'organizzazione tvm, gestione delle minacce e delle vulnerabilità, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934106"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>Punteggio di esposizione - Gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Il punteggio di esposizione è visibile nel [dashboard di gestione](tvm-dashboard-insights.md) delle minacce e delle vulnerabilità di Microsoft Defender Security Center. Riflette la vulnerabilità dell'organizzazione alle minacce alla cybersecurity. Il punteggio di esposizione basso indica che i dispositivi sono meno vulnerabili dallo sfruttamento.

- Comprendere e identificare rapidamente le informazioni di alto livello sullo stato di sicurezza nell'organizzazione.
- Rilevare e rispondere alle aree che richiedono indagini o azioni per migliorare lo stato corrente.
- Comunicare con i peer e la gestione sull'impatto degli sforzi di sicurezza.

La scheda offre una visualizzazione di alto livello della tendenza del punteggio di esposizione nel tempo. Eventuali picchi nel grafico offrono un'indicazione visiva di un'elevata esposizione alle minacce di cybersecurity che è possibile analizzare ulteriormente.

![Scheda punteggio esposizione](images/tvm_exp_score.png)

## <a name="how-it-works"></a>Funzionamento

Il punteggio di esposizione è suddiviso nei livelli seguenti:

- 0-29: punteggio di esposizione basso
- 30-69: punteggio di esposizione medio
- 70-100: punteggio di esposizione elevata

È possibile correggere i problemi in base ai consigli di sicurezza con priorità [per](tvm-security-recommendation.md) ridurre il punteggio di esposizione. Ogni software presenta punti deboli che vengono trasformati in consigli e classificati in ordine di priorità in base ai rischi per l'organizzazione.

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>Ridurre la minaccia e l'esposizione alle vulnerabilità

Ridurre l'esposizione alle minacce e alle vulnerabilità corredando i [suggerimenti per la sicurezza.](tvm-security-recommendation.md) Per ottenere il massimo impatto sul punteggio di esposizione, correggere i principali suggerimenti per la sicurezza, che possono essere visualizzati nel dashboard di gestione delle minacce [e delle vulnerabilità.](tvm-dashboard-insights.md)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Punteggio di sicurezza Microsoft per dispositivi](tvm-microsoft-secure-score-devices.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Sequenza temporale eventi](threat-and-vuln-mgt-event-timeline.md)
